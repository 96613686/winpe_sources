# CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)

- ea: `0x180292878`
- end: `0x180294e41`
- name: `?AddToImageInfoSet@CImageInfoSet@@SAJPEAV1@PEAVString@UnBCL@@PEAV?$ArrayList@PEAVString@UnBCL@@@3@KPEAV?$ArrayList@PEAVCImageInfo@@@3@PEBG4PEAUtagWDS_CLI_CRED@@W4IMAGE_TYPE@SetupPlatform@@@Z`
- size: `9673`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180297410`
- `0x180297e4c`

## callees

- `0x18001413d`
- `0x180044820`
- `0x18004d4b4`
- `0x180057dec`
- `0x1800b2f10`
- `0x18027d688`
- `0x18028f81c`
- `0x18028f84c`
- `0x18028f8c0`
- `0x1802912ec`
- `0x180291a88`
- `0x180292094`
- `0x1802920f0`
- `0x18029214c`
- `0x180292878`
- `0x18029a0fc`
- `0x1802d76cc`
- `0x1802d77bc`
- `0x1802db0f8`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x180292e98`
- `msvcrt!_wcstoui64` at `0x180292f29`
- `msvcrt!_wcstoui64` at `0x180292e98`
- `msvcrt!_wcstoui64` at `0x180292f29`
- `msvcrt!_wtoi` at `0x180293112`
- `msvcrt!_wtoi` at `0x180293112`
- `KERNEL32!GetProcessHeap` at `0x1802946b1`
- `KERNEL32!GetProcessHeap` at `0x1802946e2`
- `KERNEL32!GetProcessHeap` at `0x180294713`
- `KERNEL32!GetProcessHeap` at `0x180294744`
- `KERNEL32!GetProcessHeap` at `0x1802946b1`
- `KERNEL32!GetProcessHeap` at `0x1802946e2`
- `KERNEL32!GetProcessHeap` at `0x180294713`
- `KERNEL32!GetProcessHeap` at `0x180294744`
- `KERNEL32!HeapFree` at `0x1802946bf`
- `KERNEL32!HeapFree` at `0x1802946f0`
- `KERNEL32!HeapFree` at `0x180294721`
- `KERNEL32!HeapFree` at `0x180294752`
- `KERNEL32!HeapFree` at `0x1802946bf`
- `KERNEL32!HeapFree` at `0x1802946f0`
- `KERNEL32!HeapFree` at `0x180294721`
- `KERNEL32!HeapFree` at `0x180294752`
- `KERNEL32!GetLastError` at `0x180292937`
- `KERNEL32!GetLastError` at `0x1802929b5`
- `KERNEL32!GetLastError` at `0x180293909`
- `KERNEL32!GetLastError` at `0x180294943`
- `KERNEL32!GetLastError` at `0x1802949e1`
- `KERNEL32!GetLastError` at `0x1802949f7`
- `KERNEL32!GetLastError` at `0x180294a1a`
- `KERNEL32!GetLastError` at `0x180294ac9`
- `KERNEL32!GetLastError` at `0x180294adf`
- `KERNEL32!GetLastError` at `0x180294b02`
- `KERNEL32!GetLastError` at `0x180294bb2`
- `KERNEL32!GetLastError` at `0x180294bc8`
- `KERNEL32!GetLastError` at `0x180294beb`
- `KERNEL32!GetLastError` at `0x180294c9b`
- `KERNEL32!GetLastError` at `0x180294d40`
- `KERNEL32!GetLastError` at `0x180292937`
- `KERNEL32!GetLastError` at `0x1802929b5`
- `KERNEL32!GetLastError` at `0x180293909`
- `KERNEL32!GetLastError` at `0x180294943`
- `KERNEL32!GetLastError` at `0x1802949e1`
- `KERNEL32!GetLastError` at `0x1802949f7`
- `KERNEL32!GetLastError` at `0x180294a1a`
- `KERNEL32!GetLastError` at `0x180294ac9`
- `KERNEL32!GetLastError` at `0x180294adf`
- `KERNEL32!GetLastError` at `0x180294b02`
- `KERNEL32!GetLastError` at `0x180294bb2`
- `KERNEL32!GetLastError` at `0x180294bc8`
- `KERNEL32!GetLastError` at `0x180294beb`
- `KERNEL32!GetLastError` at `0x180294c9b`
- `KERNEL32!GetLastError` at `0x180294d40`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802935a7`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18029369a`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802935a7`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18029369a`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180292c71`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180292c71`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x18029343f`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x180293500`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802935f3`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802936e6`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x18029343f`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x180293500`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802935f3`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802936e6`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180292a24`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180292a24`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180294913`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180294913`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802938ae`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802938ae`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180292cf0`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180292cf0`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180292ccd`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180292ccd`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180292ca5`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180292ca5`
- `unbcl!?LoadXml@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x180292c28`
- `unbcl!?LoadXml@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x180292c28`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x180292ba1`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x180292ba1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292c99`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292e6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292efe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802930ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293364`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802933db`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802933f2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029349c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802934b3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029355d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293574`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293650`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293667`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029384c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293863`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029389f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802938c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802938d3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293ada`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293b86`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293bc2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293c46`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293cca`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293d4e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293d8a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293dc6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e3e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e7a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293eb6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293ee8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029410e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029414a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802941f6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294232`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802942b6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029433a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802943be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802943f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294422`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294454`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294486`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802944b3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802944e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294515`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292c99`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292e6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180292efe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802930ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293364`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802933db`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802933f2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029349c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802934b3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029355d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293574`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293650`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293667`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029384c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293863`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029389f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802938c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802938d3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293ada`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293b86`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293bc2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293c46`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293cca`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293d4e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293d8a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293dc6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e3e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293e7a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293eb6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180293ee8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029410e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029414a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802941f6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294232`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802942b6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029433a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802943be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802943f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294422`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294454`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294486`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802944b3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802944e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180294515`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292c37`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292d47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292d8d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292dd3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292e19`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292e5f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292ef0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292f81`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292fc7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029300d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180293053`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180293099`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802930df`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029316c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802931b2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802931f8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029323e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180293284`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802932ca`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180293310`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180293356`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029377b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802937e1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802937f0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802938fb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292c37`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292d47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180292d8d`

## string_xrefs

- `0x1802929c6`: `CImageInfoSet::AddToImageInfoSet: WinRE separate image not supported for WDS installation.`
- `0x180292948`: `CImageInfoSet::AddToImageInfoSet: Reference paths not supported for WDS installation.`
- `0x180294a3a`: `Failed to create WIM handle for %s. Error: 0x%08X`
- `0x180294958`: `CImageInfoSet::AddToImageInfoSet: Failed to initialize COM. Error: 0x%08X`
- `0x180292eb0`: `HARDLINKBYTES`
- `0x180293059`: `WINDOWS/INSTALLATIONTYPE`
- `0x180293929`: `Some image info for WIM %s, index %d is missing from WIM XML; trying to get it from registry.`

## pseudocode

```c
// Hidden C++ exception states: #wind=91 #try_helpers=2
__int64 __fastcall CImageInfoSet::AddToImageInfoSet(
        __int64 a1,
        UnBCL::String *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v10; // edi
  DWORD LastError; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  int v17; // esi
  const unsigned __int16 *CString; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  UnBCL::XmlDocument *v24; // rax
  UnBCL::XmlDocument *v25; // rbx
  const unsigned __int16 *v26; // rax
  UnBCL::XmlDocument *v27; // rbx
  struct UnBCL::String *v28; // rax
  unsigned int v29; // r13d
  struct UnBCL::String *v30; // rax
  UnBCL::XmlNode *v31; // rbx
  struct UnBCL::String *P; // rax
  struct UnBCL::XmlNodeList *v33; // rax
  struct UnBCL::XmlNode *Item; // rax
  struct UnBCL::String *v35; // rax
  struct UnBCL::String *v36; // rax
  struct UnBCL::String *v37; // rax
  struct UnBCL::String *v38; // rax
  struct UnBCL::String *v39; // rax
  struct UnBCL::String *v40; // rax
  struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  struct UnBCL::String *v43; // rax
  struct UnBCL::String *v44; // rax
  UnBCL::String *v45; // rax
  const wchar_t *v46; // rax
  struct UnBCL::String *v47; // rax
  struct UnBCL::String *v48; // rax
  UnBCL::String *v49; // rax
  const wchar_t *v50; // rax
  struct UnBCL::String *v51; // rax
  struct UnBCL::String *v52; // rax
  struct UnBCL::String *v53; // rax
  struct UnBCL::String *v54; // rax
  struct UnBCL::String *v55; // rax
  struct UnBCL::String *v56; // rax
  struct UnBCL::String *v57; // rax
  struct UnBCL::String *v58; // rax
  struct UnBCL::String *v59; // rax
  struct UnBCL::String *v60; // rax
  struct UnBCL::String *v61; // rax
  struct UnBCL::String *v62; // rax
  UnBCL::String *v63; // rax
  const wchar_t *v64; // rax
  struct UnBCL::String *v65; // rax
  struct UnBCL::String *v66; // rax
  struct UnBCL::String *v67; // rax
  struct UnBCL::String *v68; // rax
  struct UnBCL::String *v69; // rax
  struct UnBCL::String *v70; // rax
  struct UnBCL::String *v71; // rax
  struct UnBCL::String *v72; // rax
  struct UnBCL::String *v73; // rax
  struct UnBCL::String *v74; // rax
  struct UnBCL::String *v75; // rax
  struct UnBCL::String *v76; // rax
  struct UnBCL::String *v77; // rax
  struct UnBCL::String *v78; // rax
  struct UnBCL::String *v79; // rax
  struct UnBCL::String *v80; // rax
  UnBCL::String *v81; // rbx
  UnBCL::String *v82; // rax
  const unsigned __int16 *v83; // rax
  UnBCL::String *v84; // rax
  const unsigned __int16 *v85; // rbx
  UnBCL::String *v86; // rax
  const unsigned __int16 *v87; // rax
  struct UnBCL::String *v88; // rax
  UnBCL::String *v89; // rax
  const unsigned __int16 *v90; // rbx
  UnBCL::String *v91; // rax
  const unsigned __int16 *v92; // rax
  struct UnBCL::String *v93; // rax
  UnBCL::String *v94; // rax
  const unsigned __int16 *v95; // rax
  UnBCL::String *v96; // rax
  const unsigned __int16 *v97; // rbx
  UnBCL::String *v98; // rax
  const unsigned __int16 *v99; // rax
  struct UnBCL::String *v100; // rax
  UnBCL::String *v101; // rax
  const unsigned __int16 *v102; // rax
  UnBCL::String *v103; // rax
  const unsigned __int16 *v104; // rbx
  UnBCL::String *v105; // rax
  const unsigned __int16 *v106; // rax
  struct UnBCL::String *v107; // rax
  struct UnBCL::String *v108; // rax
  struct UnBCL::String *v109; // rax
  struct UnBCL::String *v110; // rbx
  struct UnBCL::String *v111; // rax
  const struct UnBCL::String *v112; // rbx
  const struct UnBCL::String *v113; // rax
  char v114; // bl
  DWORD v115; // ebx
  __int64 v116; // rdi
  const char *v117; // rax
  struct tagLOG_PARTIAL_MSG *v118; // rax
  __int64 v119; // rsi
  __int64 v120; // rdi
  __int64 v121; // rbx
  unsigned __int16 **v122; // rax
  DWORD v123; // edi
  __int64 v124; // rbx
  struct tagLOG_PARTIAL_MSG *v125; // rax
  signed int v126; // eax
  bool v127; // sf
  signed int v128; // eax
  unsigned int v129; // ebx
  DWORD v130; // edi
  __int64 v131; // rsi
  const char *v132; // rax
  struct tagLOG_PARTIAL_MSG *v133; // rax
  signed int v134; // eax
  bool v135; // sf
  signed int v136; // eax
  unsigned int v137; // ebx
  DWORD v138; // edi
  __int64 v139; // rsi
  const char *v140; // rax
  struct tagLOG_PARTIAL_MSG *v141; // rax
  signed int v142; // eax
  bool v143; // sf
  signed int v144; // eax
  unsigned int v145; // ebx
  DWORD v146; // edi
  __int64 v147; // rsi
  const char *v148; // rax
  struct tagLOG_PARTIAL_MSG *v149; // rax
  int v150; // [rsp+20h] [rbp-7D8h]
  __int64 v151; // [rsp+38h] [rbp-7C0h]
  DWORD v152; // [rsp+40h] [rbp-7B8h]
  _BYTE v153[8]; // [rsp+F8h] [rbp-700h] BYREF
  struct UnBCL::XmlNode *v154; // [rsp+100h] [rbp-6F8h]
  _BYTE v155[16]; // [rsp+108h] [rbp-6F0h] BYREF
  int v156; // [rsp+118h] [rbp-6E0h] BYREF
  __int64 v157; // [rsp+120h] [rbp-6D8h]
  int v158; // [rsp+128h] [rbp-6D0h] BYREF
  int v159; // [rsp+12Ch] [rbp-6CCh]
  unsigned int v160; // [rsp+130h] [rbp-6C8h]
  _QWORD v161[2]; // [rsp+150h] [rbp-6A8h] BYREF
  _QWORD v162[2]; // [rsp+160h] [rbp-698h] BYREF
  _QWORD v163[2]; // [rsp+170h] [rbp-688h] BYREF
  _QWORD v164[2]; // [rsp+180h] [rbp-678h] BYREF
  _BYTE v165[24]; // [rsp+190h] [rbp-668h] BYREF
  _BYTE v166[24]; // [rsp+1A8h] [rbp-650h] BYREF
  _DWORD v167[2]; // [rsp+1C0h] [rbp-638h] BYREF
  int v168; // [rsp+1C8h] [rbp-630h] BYREF
  _QWORD v169[5]; // [rsp+1E0h] [rbp-618h] BYREF
  int v170; // [rsp+208h] [rbp-5F0h]
  unsigned __int64 v171; // [rsp+210h] [rbp-5E8h]
  unsigned __int64 v172; // [rsp+218h] [rbp-5E0h]
  int v173[2]; // [rsp+220h] [rbp-5D8h]
  UnBCL::String *v174; // [rsp+228h] [rbp-5D0h]
  _BYTE v175[16]; // [rsp+248h] [rbp-5B0h] BYREF
  _BYTE v176[16]; // [rsp+258h] [rbp-5A0h] BYREF
  _BYTE v177[16]; // [rsp+268h] [rbp-590h] BYREF
  _BYTE v178[16]; // [rsp+278h] [rbp-580h] BYREF
  UnBCL::XmlDocument *v179; // [rsp+2A0h] [rbp-558h]
  __int64 v180; // [rsp+2A8h] [rbp-550h]
  __int64 v181; // [rsp+2B0h] [rbp-548h]
  _BYTE v182[16]; // [rsp+2B8h] [rbp-540h] BYREF
  _BYTE v183[16]; // [rsp+2D0h] [rbp-528h] BYREF
  _BYTE v184[16]; // [rsp+2E0h] [rbp-518h] BYREF
  _BYTE v185[16]; // [rsp+2F0h] [rbp-508h] BYREF
  _BYTE v186[16]; // [rsp+300h] [rbp-4F8h] BYREF
  _BYTE v187[16]; // [rsp+310h] [rbp-4E8h] BYREF
  _BYTE v188[16]; // [rsp+320h] [rbp-4D8h] BYREF
  _BYTE v189[16]; // [rsp+330h] [rbp-4C8h] BYREF
  _BYTE v190[16]; // [rsp+340h] [rbp-4B8h] BYREF
  _QWORD v191[2]; // [rsp+350h] [rbp-4A8h] BYREF
  _BYTE v192[16]; // [rsp+368h] [rbp-490h] BYREF
  _BYTE v193[16]; // [rsp+378h] [rbp-480h] BYREF
  _BYTE v194[16]; // [rsp+388h] [rbp-470h] BYREF
  _BYTE v195[8]; // [rsp+398h] [rbp-460h] BYREF
  UnBCL::XmlDocument *v196; // [rsp+3A0h] [rbp-458h]
  __int64 v197; // [rsp+3C0h] [rbp-438h]
  __int64 v198; // [rsp+3C8h] [rbp-430h]
  _QWORD *v199; // [rsp+3F8h] [rbp-400h] BYREF
  _QWORD *pExceptionObject; // [rsp+408h] [rbp-3F0h] BYREF
  _QWORD *v201; // [rsp+410h] [rbp-3E8h] BYREF
  _QWORD *v202; // [rsp+418h] [rbp-3E0h] BYREF
  _QWORD *v203; // [rsp+420h] [rbp-3D8h] BYREF
  _BYTE v204[16]; // [rsp+438h] [rbp-3C0h] BYREF
  _BYTE v205[16]; // [rsp+448h] [rbp-3B0h] BYREF
  _BYTE v206[16]; // [rsp+458h] [rbp-3A0h] BYREF
  _BYTE v207[16]; // [rsp+468h] [rbp-390h] BYREF
  _BYTE v208[16]; // [rsp+478h] [rbp-380h] BYREF
  _BYTE v209[8]; // [rsp+488h] [rbp-370h] BYREF
  UnBCL::XmlNodeList *v210; // [rsp+490h] [rbp-368h]
  __int64 v211; // [rsp+498h] [rbp-360h]
  __int64 v212; // [rsp+4A0h] [rbp-358h]
  _BYTE v213[24]; // [rsp+4A8h] [rbp-350h] BYREF
  _QWORD v214[7]; // [rsp+4C0h] [rbp-338h] BYREF
  _BYTE v215[16]; // [rsp+4F8h] [rbp-300h] BYREF
  _BYTE v216[16]; // [rsp+508h] [rbp-2F0h] BYREF
  _BYTE v217[16]; // [rsp+518h] [rbp-2E0h] BYREF
  _BYTE v218[16]; // [rsp+528h] [rbp-2D0h] BYREF
  _BYTE v219[48]; // [rsp+538h] [rbp-2C0h] BYREF
  __int64 v220; // [rsp+568h] [rbp-290h]
  _BYTE v221[536]; // [rsp+580h] [rbp-278h] BYREF
  unsigned int v222; // [rsp+798h] [rbp-60h]

  v220 = -2;
  v170 = a4;
  *(_QWORD *)v173 = a3;
  v174 = a2;
  v180 = a1;
  v212 = a5;
  v181 = a6;
  v211 = a6;
  v198 = a7;
  v197 = a8;
  v10 = 0;
  v160 = 0;
  LODWORD(v157) = 0;
  if ( a3 && a6 )
  {
    LastError = GetLastError();
    v12 = CurrentIP();
    v13 = ConstructPartialMsgW(
            0x2000000u,
            "CImageInfoSet::AddToImageInfoSet: Reference paths not supported for WDS installation.");
    v152 = LastError;
    v151 = v12;
    v150 = 1858;
  }
  else
  {
    if ( !a4 || !a6 )
    {
      v168 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v214);
      v214[0] = &`CImageInfoSet::AddToImageInfoSet'::`9'::CXXXXXHandledException::`vftable';
      v17 = SPInitializeCOM(&v168);
      if ( v17 >= 0 )
      {
        v169[1] = 0;
        v169[0] = &RAII::CAutoWimClose::`vftable';
        CString = UnBCL::String::get_CString(a2);
        v19 = v169[0];
        v20 = WIMCreateFile(CString, 0, 3, 0x20000000, 0, 0);
        (*(void (__fastcall **)(_QWORD *, __int64))(v19 + 48))(v169, v20);
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(v169[0] + 72LL))(v169) )
        {
          memset_0(v221, 0, 0x230u);
          v21 = (*(__int64 (__fastcall **)(_QWORD *))(v169[0] + 32LL))(v169);
          if ( (unsigned int)WIMGetAttributes(v21, v221, 560) )
          {
            v191[1] = 0;
            v191[0] = &RAII::CAutoLocalFree<void *>::`vftable';
            v167[0] = 0;
            v22 = RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(v191);
            v23 = (*(__int64 (__fastcall **)(_QWORD *))(v169[0] + 32LL))(v169);
            if ( (unsigned int)WIMGetImageInformation(v23, v22, v167) )
            {
              v24 = (UnBCL::XmlDocument *)UnBCL::Object::operator new(0x28u);
              v25 = v24;
              v179 = v24;
              if ( v24 )
              {
                UnBCL::XmlDocument::XmlDocument(v24);
                *(_QWORD *)v25 = &UnBCL::XmlDocument::`local vftable';
              }
              else
              {
                v25 = 0;
              }
              UnBCL::SmartPtr<UnBCL::XmlDocument>::SmartPtr<UnBCL::XmlDocument>(v195, v25);
              UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(a1 + 48, v196);
              if ( v167[0] )
              {
                v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))(v191[0] + 32LL))(v191);
                if ( *v26 == 0xFEFF )
                  ++v26;
                v27 = v196;
                v28 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v213, v26);
                UnBCL::XmlDocument::LoadXml(v27, v28);
                UnBCL::String::~String((UnBCL::String *)v213);
              }
              v29 = 0;
              while ( v29 < v222 )
              {
                v167[1] = ++v29;
                v30 = UnBCL::String::Format(L"/WIM/IMAGE[@INDEX=\"%d\"]", v29);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v213, v30);
                v31 = v196;
                P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v213);
                v33 = UnBCL::XmlNode::SelectNodes(v31, P);
                UnBCL::SmartPtr<UnBCL::XmlNodeList>::SmartPtr<UnBCL::XmlNodeList>(v209, v33);
                if ( v210 && (int)UnBCL::XmlNodeList::get_Count(v210) > 0 )
                {
                  v158 = 1;
                  Item = UnBCL::XmlNodeList::get_Item(v210, 0);
                  UnBCL::SmartPtr<UnBCL::XmlNode>::SmartPtr<UnBCL::XmlNode>(v153, Item);
                  v35 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"NAME");
                  v36 = SPGetNodeContent(v154, v35);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v190, v36);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v37 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"DISPLAYNAME");
                  v38 = SPGetNodeContent(v154, v37);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v192, v38);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v39 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"DESCRIPTION");
                  v40 = SPGetNodeContent(v154, v39);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v188, v40);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v41 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"DISPLAYDESCRIPTION");
                  v42 = SPGetNodeContent(v154, v41);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v187, v42);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v43 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"TOTALBYTES");
                  v44 = SPGetNodeContent(v154, v43);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v208, v44);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v208) )
                  {
                    v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v208);
                    v46 = UnBCL::String::get_CString(v45);
                    v172 = _wcstoui64(v46, 0, 10);
                  }
                  else
                  {
                    v172 = 0;
                  }
                  v47 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"HARDLINKBYTES");
                  v48 = SPGetNodeContent(v154, v47);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v207, v48);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v207) )
                  {
                    v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v207);
                    v50 = UnBCL::String::get_CString(v49);
                    v171 = _wcstoui64(v50, 0, 10);
                  }
                  else
                  {
                    v171 = 0;
                  }
                  v51 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/PRODUCTTYPE");
                  v52 = SPGetNodeContent(v154, v51);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v186, v52);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v53 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/PRODUCTNAME");
                  v54 = SPGetNodeContent(v154, v53);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v185, v54);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v55 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/PRODUCTSUITE");
                  v56 = SPGetNodeContent(v154, v55);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v184, v56);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v57 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/EDITIONID");
                  v58 = SPGetNodeContent(v154, v57);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v176, v58);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v59 = (struct UnBCL::String *)UnBCL::String::String(
                                                  (UnBCL::String *)v165,
                                                  L"WINDOWS/INSTALLATIONTYPE");
                  v60 = SPGetNodeContent(v154, v59);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v175, v60);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v61 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/ARCH");
                  v62 = SPGetNodeContent(v154, v61);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v206, v62);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v206) )
                  {
                    v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v206);
                    v64 = UnBCL::String::get_CString(v63);
                    v159 = _wtoi(v64);
                  }
                  else
                  {
                    v159 = 0xFFFF;
                  }
                  v65 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/VERSION/MAJOR");
                  v66 = SPGetNodeContent(v154, v65);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v66);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v67 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/VERSION/MINOR");
                  v68 = SPGetNodeContent(v154, v67);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v194, v68);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v69 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/VERSION/BUILD");
                  v70 = SPGetNodeContent(v154, v69);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v193, v70);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v71 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/VERSION/SPBUILD");
                  v72 = SPGetNodeContent(v154, v71);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v183, v72);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v73 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/VERSION/SPLEVEL");
                  v74 = SPGetNodeContent(v154, v73);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v189, v74);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v75 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"WINDOWS/VERSION/BRANCH");
                  v76 = SPGetNodeContent(v154, v75);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v178, v76);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v77 = (struct UnBCL::String *)UnBCL::String::String(
                                                  (UnBCL::String *)v165,
                                                  L"WINDOWS/SERVICINGDATA/GDRDUREVISION");
                  v78 = SPGetNodeContent(v154, v77);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v204, v78);
                  UnBCL::String::~String((UnBCL::String *)v165);
                  v79 = (struct UnBCL::String *)UnBCL::String::String(
                                                  (UnBCL::String *)v166,
                                                  L"WINDOWS/SERVICINGDATA/IMAGESTATE");
                  v80 = SPGetNodeContent(v154, v79);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v80);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v205) )
                  {
                    v81 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                    v169[2] = v81;
                    if ( v81 )
                    {
                      v82 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v205);
                      v83 = UnBCL::String::get_CString(v82);
                      UnBCL::String::String(v81, v83);
                      *(_QWORD *)v81 = &UnBCL::String::`local vftable';
                    }
                    else
                    {
                      v81 = 0;
                    }
                  }
                  else
                  {
                    v81 = 0;
                  }
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v155, v81);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v155) )
                  {
                    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v194) )
                    {
                      v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v194);
                      v85 = UnBCL::String::get_CString(v84);
                      v86 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v155);
                      v87 = UnBCL::String::get_CString(v86);
                      v88 = UnBCL::String::Concat(v87, L".", v85);
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v215, v88);
                      UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v215);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v215);
                    }
                  }
                  else
                  {
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v194);
                  }
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v155) )
                  {
                    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v193) )
                    {
                      v89 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v193);
                      v90 = UnBCL::String::get_CString(v89);
                      v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v155);
                      v92 = UnBCL::String::get_CString(v91);
                      v93 = UnBCL::String::Concat(v92, L".", v90);
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v216, v93);
                      UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v216);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v216);
                    }
                  }
                  else
                  {
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v193);
                  }
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v155) )
                  {
                    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v183) )
                    {
                      v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v183);
                      v95 = UnBCL::String::get_CString(v94);
                      if ( UnBCL::String::Compare(v95, L"0", 0) )
                      {
                        v96 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v183);
                        v97 = UnBCL::String::get_CString(v96);
                        v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v155);
                        v99 = UnBCL::String::get_CString(v98);
                        v100 = UnBCL::String::Concat(v99, L".", v97);
                        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v217, v100);
                        UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v217);
                        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v217);
                      }
                    }
                  }
                  else
                  {
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v183);
                  }
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v155) )
                  {
                    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v189) )
                    {
                      v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v189);
                      v102 = UnBCL::String::get_CString(v101);
                      if ( UnBCL::String::Compare(v102, L"0", 0) )
                      {
                        v103 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v189);
                        v104 = UnBCL::String::get_CString(v103);
                        v105 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v155);
                        v106 = UnBCL::String::get_CString(v105);
                        v107 = UnBCL::String::Concat(v106, L".", v104);
                        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v218, v107);
                        UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v218);
                        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v218);
                      }
                    }
                  }
                  else
                  {
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v155, v189);
                  }
                  v108 = (struct UnBCL::String *)UnBCL::String::String(
                                                   (UnBCL::String *)v166,
                                                   L"WINDOWS/LANGUAGES/DEFAULT");
                  v109 = SPGetNodeContent(v154, v108);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v182, v109);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v110 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v219, L"LANGUAGE");
                  v111 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v165, L"WINDOWS/LANGUAGES");
                  v169[4] = SPGetNodeMultiSz(v154, v111, v110);
                  v169[3] = &RAII::CAutoUnBCLFree<unsigned short const *>::`vftable';
                  UnBCL::String::~String((UnBCL::String *)v165);
                  UnBCL::String::~String((UnBCL::String *)v219);
                  v164[1] = 0;
                  v164[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
                  v163[1] = 0;
                  v163[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
                  v161[1] = 0;
                  v161[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
                  v162[1] = 0;
                  v162[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
                  v156 = 0;
                  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v175)
                    || !UnBCL::SmartPtr<UnBCL::String>::get_P(v155)
                    || (v112 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v219, L"WindowsPE"),
                        v10 = 1,
                        v160 = 1,
                        LODWORD(v157) = 1,
                        v113 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v176),
                        UnBCL::String::Compare(v113, v112, 0))
                    && !UnBCL::SmartPtr<UnBCL::String>::get_P(v177)
                    || (v114 = 0, !UnBCL::SmartPtr<UnBCL::String>::get_P(v178)) )
                  {
                    v114 = 1;
                  }
                  if ( (v10 & 1) != 0 )
                  {
                    v160 = v10 & 0xFFFFFFFE;
                    UnBCL::String::~String((UnBCL::String *)v219);
                  }
                  if ( v114 )
                  {
                    v115 = GetLastError();
                    v116 = CurrentIP();
                    v117 = (const char *)UnBCL::String::get_CString(a2);
                    v118 = ConstructPartialMsgW(
                             0x4000000u,
                             "Some image info for WIM %s, index %d is missing from WIM XML; trying to get it from registry.",
                             v117,
                             v29);
                    WdsSetupLogMessageW(
                      v118,
                      0,
                      L"D",
                      0,
                      2022,
                      L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
                      L"CImageInfoSet::AddToImageInfoSet",
                      v116,
                      v115,
                      0,
                      0);
                    v119 = (*(__int64 (__fastcall **)(_QWORD *))(v162[0] + 8LL))(v162);
                    v120 = (*(__int64 (__fastcall **)(_QWORD *))(v161[0] + 8LL))(v161);
                    v121 = (*(__int64 (__fastcall **)(_QWORD *))(v163[0] + 8LL))(v163);
                    v122 = (unsigned __int16 **)(*(__int64 (__fastcall **)(_QWORD *))(v164[0] + 8LL))(v164);
                    SPGetWIMImageInfo((int)a2, v173[0], v29, (int)&v156, (__int64)&v158, v122, v121, v120, v119);
                  }
                  SPGetWIMImageInfo((int)a2, v173[0], v29, (int)&v156, 0, 0, 0, 0, 0);
                }
                UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(v209);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v213);
              }
              UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(v195);
              RAII::CAutoLocalFree<void *>::~CAutoLocalFree<void *>(v191);
              RAII::CAutoWimClose::~CAutoWimClose((RAII::CAutoWimClose *)v169);
              v199 = v214;
              throw (`CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException **)&v199;
            }
            v142 = GetLastError();
            v143 = v142 < 0;
            if ( v142 > 0 )
              v143 = 1;
            if ( v143 )
            {
              v144 = GetLastError();
              v145 = v144;
              if ( v144 > 0 )
                v145 = (unsigned __int16)v144 | 0x80070000;
            }
            else
            {
              v145 = -2147467259;
            }
            v146 = GetLastError();
            v147 = CurrentIP();
            v148 = (const char *)UnBCL::String::get_CString(a2);
            v149 = ConstructPartialMsgW(
                     0x2000000u,
                     "Failed to get WIM image information for %s. Error: 0x%08X",
                     v148,
                     v145);
            WdsSetupLogMessageW(
              v149,
              0,
              L"D",
              0,
              1912,
              L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
              L"CImageInfoSet::AddToImageInfoSet",
              v147,
              v146,
              0,
              0);
            v203 = v214;
            throw (`CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException **)&v203;
          }
          v134 = GetLastError();
          v135 = v134 < 0;
          if ( v134 > 0 )
            v135 = 1;
          if ( v135 )
          {
            v136 = GetLastError();
            v137 = v136;
            if ( v136 > 0 )
              v137 = (unsigned __int16)v136 | 0x80070000;
          }
          else
          {
            v137 = -2147467259;
          }
          v138 = GetLastError();
          v139 = CurrentIP();
          v140 = (const char *)UnBCL::String::get_CString(a2);
          v141 = ConstructPartialMsgW(0x2000000u, "Failed to get WIM attributes for %s. Error: 0x%08X", v140, v137);
          WdsSetupLogMessageW(
            v141,
            0,
            L"D",
            0,
            1902,
            L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
            L"CImageInfoSet::AddToImageInfoSet",
            v139,
            v138,
            0,
            0);
          v202 = v214;
          throw (`CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException **)&v202;
        }
        v126 = GetLastError();
        v127 = v126 < 0;
        if ( v126 > 0 )
          v127 = 1;
        if ( v127 )
        {
          v128 = GetLastError();
          v129 = v128;
          if ( v128 > 0 )
            v129 = (unsigned __int16)v128 | 0x80070000;
        }
        else
        {
          v129 = -2147467259;
        }
        v130 = GetLastError();
        v131 = CurrentIP();
        v132 = (const char *)UnBCL::String::get_CString(a2);
        v133 = ConstructPartialMsgW(0x2000000u, "Failed to create WIM handle for %s. Error: 0x%08X", v132, v129);
        WdsSetupLogMessageW(
          v133,
          0,
          L"D",
          0,
          1893,
          L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
          L"CImageInfoSet::AddToImageInfoSet",
          v131,
          v130,
          0,
          0);
        v201 = v214;
        throw (`CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException **)&v201;
      }
      v123 = GetLastError();
      v124 = CurrentIP();
      v125 = ConstructPartialMsgW(
               0x2000000u,
               "CImageInfoSet::AddToImageInfoSet: Failed to initialize COM. Error: 0x%08X",
               v17);
      WdsSetupLogMessageW(
        v125,
        0,
        L"D",
        0,
        1876,
        L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
        L"CImageInfoSet::AddToImageInfoSet",
        v124,
        v123,
        0,
        0);
      pExceptionObject = v214;
      throw (`CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException **)&pExceptionObject;
    }
    v15 = GetLastError();
    v16 = CurrentIP();
    v13 = ConstructPartialMsgW(
            0x2000000u,
            "CImageInfoSet::AddToImageInfoSet: WinRE separate image not supported for WDS installation.");
    v152 = v15;
    v151 = v16;
    v150 = 1864;
  }
  WdsSetupLogMessageW(
    v13,
    0,
    L"D",
    0,
    v150,
    L"base\\ntsetup\\setupplatform\\lib\\imageinfo\\imageinfo.cpp",
    L"CImageInfoSet::AddToImageInfoSet",
    v151,
    v152,
    0,
    0);
  return 2147942450LL;
}

```

## disassembly

```asm
0x180292878  push    rbx
0x18029287a  push    rsi
0x18029287b  push    rdi
0x18029287c  push    r12
0x18029287e  push    r13
0x180292880  push    r14
0x180292882  push    r15
0x180292884  sub     rsp, 7C0h
0x18029288b  mov     [rsp+7F8h+var_290], 0FFFFFFFFFFFFFFFEh
0x180292897  mov     rax, cs:__security_cookie
0x18029289e  xor     rax, rsp
0x1802928a1  mov     [rsp+7F8h+var_48], rax
0x1802928a9  mov     [rsp+7F8h+var_5F0], r9d
0x1802928b1  mov     qword ptr [rsp+7F8h+var_5D8], r8
0x1802928b9  mov     r12, rdx
0x1802928bc  mov     [rsp+7F8h+var_5D0], rdx
0x1802928c4  mov     r14, rcx
0x1802928c7  mov     [rsp+7F8h+var_550], rcx
0x1802928cf  mov     rax, [rsp+7F8h+arg_20]
0x1802928d7  mov     [rsp+7F8h+var_358], rax
0x1802928df  mov     rax, [rsp+7F8h+arg_28]
0x1802928e7  mov     [rsp+7F8h+var_548], rax
0x1802928ef  mov     [rsp+7F8h+var_360], rax
0x1802928f7  mov     rcx, [rsp+7F8h+arg_30]
0x1802928ff  mov     [rsp+7F8h+var_430], rcx
0x180292907  mov     rcx, [rsp+7F8h+arg_38]
0x18029290f  mov     [rsp+7F8h+var_438], rcx
0x180292917  xor     r15d, r15d
0x18029291a  mov     edi, r15d
0x18029291d  mov     [rsp+7F8h+var_6C8], r15d
0x180292925  mov     dword ptr [rsp+7F8h+var_6D8], r15d
0x18029292d  test    r8, r8
0x180292930  jz      short loc_1802929AB
0x180292932  test    rax, rax
0x180292935  jz      short loc_1802929AB
0x180292937  call    cs:__imp_GetLastError
0x18029293d  mov     edi, eax
0x18029293f  call    cs:__imp_CurrentIP
0x180292945  mov     rbx, rax
0x180292948  lea     rdx, aCimageinfosetA_3; "CImageInfoSet::AddToImageInfoSet: Refer"...
0x18029294f  mov     ecx, 2000000h; unsigned int
0x180292954  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180292959  mov     dword ptr [rsp+7F8h+var_7A8], r15d
0x18029295e  mov     [rsp+7F8h+var_7B0], r15
0x180292963  mov     dword ptr [rsp+7F8h+var_7B8], edi
0x180292967  mov     [rsp+7F8h+var_7C0], rbx
0x18029296c  lea     rcx, aCimageinfosetA; "CImageInfoSet::AddToImageInfoSet"
0x180292973  mov     [rsp+7F8h+var_7C8], rcx
0x180292978  lea     rcx, aBaseNtsetupSet_32; "base\\ntsetup\\setupplatform\\lib\\imag"...
0x18029297f  mov     [rsp+7F8h+var_7D0], rcx
0x180292984  mov     dword ptr [rsp+7F8h+var_7D8], 742h
0x18029298c  xor     r9d, r9d
0x18029298f  lea     r8, aD_0; "D"
0x180292996  xor     edx, edx
0x180292998  mov     rcx, rax
0x18029299b  call    cs:__imp_WdsSetupLogMessageW
0x1802929a1  mov     eax, 80070032h
0x1802929a6  jmp     loc_180294920
0x1802929ab  test    r9d, r9d
0x1802929ae  jz      short loc_180292A0C
0x1802929b0  test    rax, rax
0x1802929b3  jz      short loc_180292A0C
0x1802929b5  call    cs:__imp_GetLastError
0x1802929bb  mov     edi, eax
0x1802929bd  call    cs:__imp_CurrentIP
0x1802929c3  mov     rbx, rax
0x1802929c6  lea     rdx, aCimageinfosetA_2; "CImageInfoSet::AddToImageInfoSet: WinRE"...
0x1802929cd  mov     ecx, 2000000h; unsigned int
0x1802929d2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802929d7  mov     dword ptr [rsp+7F8h+var_7A8], r15d
0x1802929dc  mov     [rsp+7F8h+var_7B0], r15
0x1802929e1  mov     dword ptr [rsp+7F8h+var_7B8], edi
0x1802929e5  mov     [rsp+7F8h+var_7C0], rbx
0x1802929ea  lea     rcx, aCimageinfosetA; "CImageInfoSet::AddToImageInfoSet"
0x1802929f1  mov     [rsp+7F8h+var_7C8], rcx
0x1802929f6  lea     rcx, aBaseNtsetupSet_32; "base\\ntsetup\\setupplatform\\lib\\imag"...
0x1802929fd  mov     [rsp+7F8h+var_7D0], rcx
0x180292a02  mov     dword ptr [rsp+7F8h+var_7D8], 748h
0x180292a0a  jmp     short loc_18029298C
0x180292a0c  mov     [rsp+7F8h+var_630], r15d
0x180292a14  mov     [rsp+7F8h+var_704], r15d
0x180292a1c  lea     rcx, [rsp+7F8h+var_338]
0x180292a24  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180292a2a  lea     rax, ??_7CXXXXXHandledException@?8??AddToImageInfoSet@CImageInfoSet@@SAJPEAV2@PEAVString@UnBCL@@PEAV?$ArrayList@PEAVString@UnBCL@@@4@KPEAV?$ArrayList@PEAVCImageInfo@@@4@PEBG4PEAUtagWDS_CLI_CRED@@W4IMAGE_TYPE@SetupPlatform@@@Z@6B@; const `CImageInfoSet::AddToImageInfoSet(CImageInfoSet *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,UnBCL::ArrayList<CImageInfo *> *,ushort const *,ushort const *,tagWDS_CLI_CRED *,SetupPlatform::IMAGE_TYPE)'::`9'::CXXXXXHandledException::`vftable'
0x180292a31  mov     [rsp+7F8h+var_338], rax
0x180292a39  lea     rcx, [rsp+7F8h+var_630]; int *
0x180292a41  call    ?SPInitializeCOM@@YAJAEAH@Z; SPInitializeCOM(int &)
0x180292a46  mov     esi, eax
0x180292a48  mov     [rsp+7F8h+var_708], eax
0x180292a4f  test    eax, eax
0x180292a51  js      loc_180294943
0x180292a57  xor     esi, esi
0x180292a59  mov     [rsp+7F8h+var_610], rsi
0x180292a61  lea     rax, ??_7CAutoWimClose@RAII@@6B@; const RAII::CAutoWimClose::`vftable'
0x180292a68  mov     [rsp+7F8h+var_618], rax
0x180292a70  mov     rcx, r12
0x180292a73  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180292a79  mov     rbx, [rsp+7F8h+var_618]
0x180292a81  mov     [rsp+7F8h+var_7D0], rsi
0x180292a86  mov     dword ptr [rsp+7F8h+var_7D8], esi
0x180292a8a  xor     edx, edx
0x180292a8c  mov     r9d, 20000000h
0x180292a92  lea     r8d, [rsi+3]
0x180292a96  mov     rcx, rax
0x180292a99  call    cs:__imp_WIMCreateFile
0x180292a9f  mov     rdx, rax
0x180292aa2  lea     rcx, [rsp+7F8h+var_618]
0x180292aaa  mov     rax, [rbx+30h]
0x180292aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180292ab3  mov     rax, [rsp+7F8h+var_618]
0x180292abb  lea     rcx, [rsp+7F8h+var_618]
0x180292ac3  mov     rax, [rax+48h]
0x180292ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180292acc  test    al, al
0x180292ace  jnz     loc_1802949E1
0x180292ad4  mov     ebx, 230h
0x180292ad9  mov     r8d, ebx; Size
0x180292adc  xor     edx, edx; Val
0x180292ade  lea     rcx, [rsp+7F8h+var_278]; void *
0x180292ae6  call    memset_0
0x180292aeb  mov     rax, [rsp+7F8h+var_618]
0x180292af3  lea     rcx, [rsp+7F8h+var_618]
0x180292afb  mov     rax, [rax+20h]
0x180292aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180292b04  mov     r8d, ebx
0x180292b07  lea     rdx, [rsp+7F8h+var_278]
0x180292b0f  mov     rcx, rax
0x180292b12  call    cs:__imp_WIMGetAttributes
0x180292b18  test    eax, eax
0x180292b1a  jz      loc_180294AC9
0x180292b20  mov     [rsp+7F8h+var_4A0], rsi
0x180292b28  lea     rax, ??_7?$CAutoLocalFree@PEAX@RAII@@6B@; const RAII::CAutoLocalFree<void *>::`vftable'
0x180292b2f  mov     [rsp+7F8h+var_4A8], rax
0x180292b37  mov     [rsp+7F8h+var_638], esi
0x180292b3e  lea     rcx, [rsp+7F8h+var_4A8]
0x180292b46  call    ??I?$CAutoCleanupBase@PEAVVdsVolumePathEnumerator@@@RAII@@UEBAPEBQEAVVdsVolumePathEnumerator@@XZ; RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(void)
0x180292b4b  mov     rbx, rax
0x180292b4e  mov     rcx, [rsp+7F8h+var_618]
0x180292b56  mov     rax, [rcx+20h]
0x180292b5a  lea     rcx, [rsp+7F8h+var_618]
0x180292b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180292b67  lea     r8, [rsp+7F8h+var_638]
0x180292b6f  mov     rdx, rbx
0x180292b72  mov     rcx, rax
0x180292b75  call    cs:__imp_WIMGetImageInformation
0x180292b7b  test    eax, eax
0x180292b7d  jz      loc_180294BB2
0x180292b83  mov     ecx, 28h ; '('
0x180292b88  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180292b8e  mov     rbx, rax
0x180292b91  mov     [rsp+7F8h+var_558], rax
0x180292b99  test    rax, rax
0x180292b9c  jz      short loc_180292BB3
0x180292b9e  mov     rcx, rax
0x180292ba1  call    cs:__imp_??0XmlDocument@UnBCL@@QEAA@XZ; UnBCL::XmlDocument::XmlDocument(void)
0x180292ba7  lea     rax, ??_SXmlDocument@UnBCL@@6B@; const UnBCL::XmlDocument::`local vftable'
0x180292bae  mov     [rbx], rax
0x180292bb1  jmp     short loc_180292BB6
0x180292bb3  mov     rbx, rsi
0x180292bb6  mov     rdx, rbx
0x180292bb9  lea     rcx, [rsp+7F8h+var_460]
0x180292bc1  call    ??0?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@QEAA@PEAVXmlDocument@1@@Z; UnBCL::SmartPtr<UnBCL::XmlDocument>::SmartPtr<UnBCL::XmlDocument>(UnBCL::XmlDocument *)
0x180292bc6  nop
0x180292bc7  lea     rcx, [r14+30h]
0x180292bcb  mov     rdx, [rsp+7F8h+var_458]
0x180292bd3  call    ?Assign@?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@AEAAXPEAVXmlDocument@2@@Z; UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(UnBCL::XmlDocument *)
0x180292bd8  cmp     [rsp+7F8h+var_638], esi
0x180292bdf  jbe     short loc_180292C3D
0x180292be1  mov     rax, [rsp+7F8h+var_4A8]
0x180292be9  lea     rcx, [rsp+7F8h+var_4A8]
0x180292bf1  mov     rax, [rax+20h]
0x180292bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180292bfa  mov     ecx, 0FEFFh
0x180292bff  cmp     [rax], cx
0x180292c02  jnz     short loc_180292C08
0x180292c04  add     rax, 2
0x180292c08  mov     rbx, [rsp+7F8h+var_458]
0x180292c10  mov     rdx, rax
0x180292c13  lea     rcx, [rsp+7F8h+var_350]
0x180292c1b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292c21  nop
0x180292c22  mov     rdx, rax
0x180292c25  mov     rcx, rbx
0x180292c28  call    cs:__imp_?LoadXml@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z; UnBCL::XmlDocument::LoadXml(UnBCL::String *)
0x180292c2e  nop
0x180292c2f  lea     rcx, [rsp+7F8h+var_350]
0x180292c37  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292c3d  mov     r13d, esi
0x180292c40  lea     r14, aCimageinfosetA; "CImageInfoSet::AddToImageInfoSet"
0x180292c47  lea     r15, aBaseNtsetupSet_32; "base\\ntsetup\\setupplatform\\lib\\imag"...
0x180292c4e  cmp     r13d, [rsp+7F8h+var_60]
0x180292c56  jnb     loc_180294DE6
0x180292c5c  inc     r13d
0x180292c5f  mov     [rsp+7F8h+var_634], r13d
0x180292c67  mov     edx, r13d
0x180292c6a  lea     rcx, aWimImageIndexD_1; "/WIM/IMAGE[@INDEX=\"%d\"]"
0x180292c71  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180292c77  mov     rdx, rax
0x180292c7a  lea     rcx, [rsp+7F8h+var_350]
0x180292c82  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292c88  nop
0x180292c89  mov     rbx, [rsp+7F8h+var_458]
0x180292c91  lea     rcx, [rsp+7F8h+var_350]
0x180292c99  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180292c9f  mov     rdx, rax
0x180292ca2  mov     rcx, rbx
0x180292ca5  call    cs:__imp_?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z; UnBCL::XmlNode::SelectNodes(UnBCL::String *)
0x180292cab  mov     rdx, rax
0x180292cae  lea     rcx, [rsp+7F8h+var_370]
0x180292cb6  call    ??0?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@QEAA@PEAVXmlNodeList@1@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::SmartPtr<UnBCL::XmlNodeList>(UnBCL::XmlNodeList *)
0x180292cbb  nop
0x180292cbc  mov     rcx, [rsp+7F8h+var_368]
0x180292cc4  test    rcx, rcx
0x180292cc7  jz      loc_1802948EA
0x180292ccd  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x180292cd3  test    eax, eax
0x180292cd5  jle     loc_1802948EA
0x180292cdb  mov     dword ptr [rsp+7F8h+var_6D0], 1
0x180292ce6  xor     edx, edx
0x180292ce8  mov     rcx, [rsp+7F8h+var_368]
0x180292cf0  call    cs:__imp_?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z; UnBCL::XmlNodeList::get_Item(int)
0x180292cf6  mov     rdx, rax
0x180292cf9  lea     rcx, [rsp+7F8h+var_700]
0x180292d01  call    ??0?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@QEAA@PEAVXmlNode@1@@Z; UnBCL::SmartPtr<UnBCL::XmlNode>::SmartPtr<UnBCL::XmlNode>(UnBCL::XmlNode *)
0x180292d06  nop
0x180292d07  lea     rdx, aName_0; "NAME"
0x180292d0e  lea     rcx, [rsp+7F8h+var_668]
0x180292d16  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292d1c  nop
0x180292d1d  mov     rdx, rax; struct UnBCL::String *
0x180292d20  mov     rcx, [rsp+7F8h+var_6F8]; struct UnBCL::XmlNode *
0x180292d28  call    ?SPGetNodeContent@@YAPEAVString@UnBCL@@PEAVXmlNode@2@PEAV12@@Z; SPGetNodeContent(UnBCL::XmlNode *,UnBCL::String *)
0x180292d2d  mov     rdx, rax
0x180292d30  lea     rcx, [rsp+7F8h+var_4B8]
0x180292d38  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292d3e  nop
0x180292d3f  lea     rcx, [rsp+7F8h+var_668]
0x180292d47  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292d4d  lea     rdx, aDisplayname_1; "DISPLAYNAME"
0x180292d54  lea     rcx, [rsp+7F8h+var_650]
0x180292d5c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292d62  nop
0x180292d63  mov     rdx, rax; struct UnBCL::String *
0x180292d66  mov     rcx, [rsp+7F8h+var_6F8]; struct UnBCL::XmlNode *
0x180292d6e  call    ?SPGetNodeContent@@YAPEAVString@UnBCL@@PEAVXmlNode@2@PEAV12@@Z; SPGetNodeContent(UnBCL::XmlNode *,UnBCL::String *)
0x180292d73  mov     rdx, rax
0x180292d76  lea     rcx, [rsp+7F8h+var_490]
0x180292d7e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292d84  nop
0x180292d85  lea     rcx, [rsp+7F8h+var_650]
0x180292d8d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292d93  lea     rdx, aDescription_0; "DESCRIPTION"
0x180292d9a  lea     rcx, [rsp+7F8h+var_668]
0x180292da2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292da8  nop
0x180292da9  mov     rdx, rax; struct UnBCL::String *
0x180292dac  mov     rcx, [rsp+7F8h+var_6F8]; struct UnBCL::XmlNode *
0x180292db4  call    ?SPGetNodeContent@@YAPEAVString@UnBCL@@PEAVXmlNode@2@PEAV12@@Z; SPGetNodeContent(UnBCL::XmlNode *,UnBCL::String *)
0x180292db9  mov     rdx, rax
0x180292dbc  lea     rcx, [rsp+7F8h+var_4D8]
0x180292dc4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292dca  nop
0x180292dcb  lea     rcx, [rsp+7F8h+var_668]
0x180292dd3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292dd9  lea     rdx, aDisplaydescrip; "DISPLAYDESCRIPTION"
0x180292de0  lea     rcx, [rsp+7F8h+var_650]
0x180292de8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292dee  nop
0x180292def  mov     rdx, rax; struct UnBCL::String *
0x180292df2  mov     rcx, [rsp+7F8h+var_6F8]; struct UnBCL::XmlNode *
0x180292dfa  call    ?SPGetNodeContent@@YAPEAVString@UnBCL@@PEAVXmlNode@2@PEAV12@@Z; SPGetNodeContent(UnBCL::XmlNode *,UnBCL::String *)
0x180292dff  mov     rdx, rax
0x180292e02  lea     rcx, [rsp+7F8h+var_4E8]
0x180292e0a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292e10  nop
0x180292e11  lea     rcx, [rsp+7F8h+var_650]
0x180292e19  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292e1f  lea     rdx, aTotalbytes; "TOTALBYTES"
0x180292e26  lea     rcx, [rsp+7F8h+var_668]
0x180292e2e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180292e34  nop
0x180292e35  mov     rdx, rax; struct UnBCL::String *
0x180292e38  mov     rcx, [rsp+7F8h+var_6F8]; struct UnBCL::XmlNode *
0x180292e40  call    ?SPGetNodeContent@@YAPEAVString@UnBCL@@PEAVXmlNode@2@PEAV12@@Z; SPGetNodeContent(UnBCL::XmlNode *,UnBCL::String *)
0x180292e45  mov     rdx, rax
0x180292e48  lea     rcx, [rsp+7F8h+var_380]
0x180292e50  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180292e56  nop
0x180292e57  lea     rcx, [rsp+7F8h+var_668]
0x180292e5f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180292e65  lea     rcx, [rsp+7F8h+var_380]
0x180292e6d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180292e73  test    rax, rax
0x180292e76  jz      short loc_180292EA8
0x180292e78  lea     rcx, [rsp+7F8h+var_380]
0x180292e80  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180292e86  mov     rcx, rax
0x180292e89  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180292e8f  xor     edx, edx; EndPtr
0x180292e91  lea     r8d, [rdx+0Ah]; Radix
  ... truncated ...
```
