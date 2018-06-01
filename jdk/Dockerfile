FROM centos:7.4.1708
RUN rm -rf /etc/yum.repos.d/* && curl -o /etc/yum.repos.d/CentOS7-Base.repo http://mirrors.163.com/.help/CentOS7-Base-163.repo
RUN yum -y install kde-l10n-Chinese wget iproute net-tools &&  yum clean all  && localedef -c -f UTF-8 -i zh_CN zh_CN.utf8   
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo "Asia/Shanghai" > /etc/timezone
ADD jdk-8u171-linux-x64.rpm /root/
RUN yum localinstall -y /root/jdk-8u171-linux-x64.rpm && yum clean all && rm -f /root/jdk-8u171-linux-x64.rpm
ENV JAVA_HOME /usr/java/jdk1.8.0_171-amd64
ENV LC_ALL "zh_CN.UTF-8" 
