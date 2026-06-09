# CNewSystem::QueueOperations(CImageInfo *,__int64,ushort const *,_FIRMWARE_TYPE,ushort const *,int)

- ea: `0x1800f2a50`
- end: `0x1800fc9cc`
- name: `?QueueOperations@CNewSystem@@MEAAJPEAVCImageInfo@@_JPEBGW4_FIRMWARE_TYPE@@2H@Z`
- size: `40828`
- prototype: `void __fastcall __noreturn(CNewSystem *__hidden this, struct CImageInfo *, __int64, const unsigned __int16 *, enum _FIRMWARE_TYPE, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `113`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180013804`
- `0x18001413d`
- `0x1800197c0`
- `0x180044820`
- `0x18004d46c`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae6b4`
- `0x1800afd98`
- `0x1800b1404`
- `0x1800b2ed8`
- `0x1800b9c80`
- `0x1800f2a50`
- `0x180106a00`
- `0x180106ac0`
- `0x18010f584`
- `0x180115b04`
- `0x180115c44`
- `0x180115ce4`
- `0x180115d84`
- `0x18012b2c4`
- `0x18012b894`
- `0x18012cfd4`
- `0x18012d3a0`
- `0x18012dce0`
- `0x18012e2b8`
- `0x18012e780`
- `0x18012efa0`
- `0x18012f3cc`
- `0x18012f68c`
- `0x18012fce4`
- `0x18013011c`
- `0x180130548`
- `0x180130980`
- `0x180130d00`
- `0x180131270`
- `0x180156600`
- `0x18015698c`
- `0x180156c7c`
- `0x180157328`
- `0x180157c98`
- `0x180158628`
- `0x180158fe8`
- `0x18015928c`
- `0x18015a44c`
- `0x18015ae04`
- `0x18015aff8`
- `0x18015b3e0`
- `0x18015b864`
- `0x18015cb20`

## import_xrefs

- `msvcrt!iswalpha` at `0x1800fbba8`
- `msvcrt!iswalpha` at `0x1800fbba8`
- `ADVAPI32!RegGetValueW` at `0x1800fa506`
- `ADVAPI32!RegGetValueW` at `0x1800fa506`
- `KERNEL32!GetLastError` at `0x1800f2b99`
- `KERNEL32!GetLastError` at `0x1800f2c33`
- `KERNEL32!GetLastError` at `0x1800f2d25`
- `KERNEL32!GetLastError` at `0x1800f2db8`
- `KERNEL32!GetLastError` at `0x1800f2e75`
- `KERNEL32!GetLastError` at `0x1800f2f0d`
- `KERNEL32!GetLastError` at `0x1800f2f90`
- `KERNEL32!GetLastError` at `0x1800f300a`
- `KERNEL32!GetLastError` at `0x1800f31fa`
- `KERNEL32!GetLastError` at `0x1800f328a`
- `KERNEL32!GetLastError` at `0x1800f3349`
- `KERNEL32!GetLastError` at `0x1800f33a4`
- `KERNEL32!GetLastError` at `0x1800f3537`
- `KERNEL32!GetLastError` at `0x1800f367f`
- `KERNEL32!GetLastError` at `0x1800f3755`
- `KERNEL32!GetLastError` at `0x1800f3a9f`
- `KERNEL32!GetLastError` at `0x1800f3baf`
- `KERNEL32!GetLastError` at `0x1800f3f0c`
- `KERNEL32!GetLastError` at `0x1800f405f`
- `KERNEL32!GetLastError` at `0x1800f40ea`
- `KERNEL32!GetLastError` at `0x1800f419d`
- `KERNEL32!GetLastError` at `0x1800f421b`
- `KERNEL32!GetLastError` at `0x1800f4767`
- `KERNEL32!GetLastError` at `0x1800f47f1`
- `KERNEL32!GetLastError` at `0x1800f48be`
- `KERNEL32!GetLastError` at `0x1800f498c`
- `KERNEL32!GetLastError` at `0x1800f4a2b`
- `KERNEL32!GetLastError` at `0x1800f4ac2`
- `KERNEL32!GetLastError` at `0x1800f4b6a`
- `KERNEL32!GetLastError` at `0x1800f4c36`
- `KERNEL32!GetLastError` at `0x1800f4cc7`
- `KERNEL32!GetLastError` at `0x1800f4fbf`
- `KERNEL32!GetLastError` at `0x1800f504d`
- `KERNEL32!GetLastError` at `0x1800f50bd`
- `KERNEL32!GetLastError` at `0x1800f512d`
- `KERNEL32!GetLastError` at `0x1800f519d`
- `KERNEL32!GetLastError` at `0x1800f5223`
- `KERNEL32!GetLastError` at `0x1800f52c9`
- `KERNEL32!GetLastError` at `0x1800f53b6`
- `KERNEL32!GetLastError` at `0x1800f5b9d`
- `KERNEL32!GetLastError` at `0x1800f6536`
- `KERNEL32!GetLastError` at `0x1800f664f`
- `KERNEL32!GetLastError` at `0x1800f6eda`
- `KERNEL32!GetLastError` at `0x1800f70c4`
- `KERNEL32!GetLastError` at `0x1800f70dc`
- `KERNEL32!GetLastError` at `0x1800f70f4`
- `KERNEL32!GetLastError` at `0x1800f725c`
- `KERNEL32!GetLastError` at `0x1800f72d1`
- `KERNEL32!GetLastError` at `0x1800f75bb`
- `KERNEL32!GetLastError` at `0x1800f7665`
- `KERNEL32!GetLastError` at `0x1800f789b`
- `KERNEL32!GetLastError` at `0x1800f7a59`
- `KERNEL32!GetLastError` at `0x1800f7b8f`
- `KERNEL32!GetLastError` at `0x1800f7ca1`
- `KERNEL32!GetLastError` at `0x1800f7f1c`
- `KERNEL32!GetLastError` at `0x1800f804c`
- `KERNEL32!GetLastError` at `0x1800f8158`
- `KERNEL32!GetLastError` at `0x1800f82a0`
- `KERNEL32!GetLastError` at `0x1800f83b6`
- `KERNEL32!GetLastError` at `0x1800f9e43`
- `KERNEL32!GetLastError` at `0x1800f9eb8`
- `KERNEL32!GetLastError` at `0x1800f9f4a`
- `KERNEL32!GetLastError` at `0x1800f9fdd`
- `KERNEL32!GetLastError` at `0x1800fa0ff`
- `KERNEL32!GetLastError` at `0x1800fa174`
- `KERNEL32!GetLastError` at `0x1800fa21e`
- `KERNEL32!GetLastError` at `0x1800fa2dc`
- `KERNEL32!GetLastError` at `0x1800fa364`
- `KERNEL32!GetLastError` at `0x1800fa416`
- `KERNEL32!GetLastError` at `0x1800fa557`
- `KERNEL32!GetLastError` at `0x1800fa663`
- `KERNEL32!GetLastError` at `0x1800fa955`
- `KERNEL32!GetLastError` at `0x1800fa9d9`
- `KERNEL32!GetLastError` at `0x1800faa72`
- `KERNEL32!GetLastError` at `0x1800fab13`
- `KERNEL32!GetLastError` at `0x1800fabd7`
- `KERNEL32!GetLastError` at `0x1800fac54`
- `KERNEL32!GetLastError` at `0x1800fad13`
- `KERNEL32!GetLastError` at `0x1800faddc`
- `KERNEL32!GetLastError` at `0x1800fae59`
- `KERNEL32!GetLastError` at `0x1800faf26`
- `KERNEL32!GetLastError` at `0x1800fb020`
- `KERNEL32!GetLastError` at `0x1800fbf3e`
- `KERNEL32!GetLastError` at `0x1800fbfd3`
- `KERNEL32!GetLastError` at `0x1800fc077`
- `KERNEL32!GetLastError` at `0x1800fc11a`
- `KERNEL32!GetLastError` at `0x1800fc187`
- `KERNEL32!GetLastError` at `0x1800fc275`
- `KERNEL32!GetLastError` at `0x1800fc388`
- `KERNEL32!GetLastError` at `0x1800fc4bb`
- `KERNEL32!GetLastError` at `0x1800fc5c0`
- `KERNEL32!GetLastError` at `0x1800f2b99`
- `KERNEL32!GetLastError` at `0x1800f2c33`
- `KERNEL32!GetLastError` at `0x1800f2d25`
- `KERNEL32!GetLastError` at `0x1800f2db8`
- `KERNEL32!GetLastError` at `0x1800f2e75`
- `KERNEL32!GetLastError` at `0x1800f2f0d`
- `KERNEL32!GetLastError` at `0x1800f2f90`
- `KERNEL32!GetLastError` at `0x1800f300a`
- `KERNEL32!GetLastError` at `0x1800f31fa`
- `KERNEL32!GetLastError` at `0x1800f328a`
- `KERNEL32!GetLastError` at `0x1800f3349`
- `KERNEL32!GetLastError` at `0x1800f33a4`
- `KERNEL32!GetLastError` at `0x1800f3537`
- `KERNEL32!GetLastError` at `0x1800f367f`
- `KERNEL32!GetLastError` at `0x1800f3755`
- `KERNEL32!GetLastError` at `0x1800f3a9f`
- `KERNEL32!GetLastError` at `0x1800f3baf`
- `KERNEL32!GetLastError` at `0x1800f3f0c`
- `KERNEL32!GetLastError` at `0x1800f405f`
- `KERNEL32!GetLastError` at `0x1800f40ea`
- `KERNEL32!GetLastError` at `0x1800f419d`
- `KERNEL32!GetLastError` at `0x1800f421b`
- `KERNEL32!GetLastError` at `0x1800f4767`
- `KERNEL32!GetLastError` at `0x1800f47f1`
- `KERNEL32!GetLastError` at `0x1800f48be`
- `KERNEL32!GetLastError` at `0x1800f498c`
- `KERNEL32!GetLastError` at `0x1800f4a2b`
- `KERNEL32!GetLastError` at `0x1800f4ac2`
- `KERNEL32!GetLastError` at `0x1800f4b6a`
- `KERNEL32!GetLastError` at `0x1800f4c36`
- `KERNEL32!GetLastError` at `0x1800f4cc7`
- `KERNEL32!GetLastError` at `0x1800f4fbf`
- `KERNEL32!GetLastError` at `0x1800f504d`
- `KERNEL32!GetLastError` at `0x1800f50bd`
- `KERNEL32!GetLastError` at `0x1800f512d`
- `KERNEL32!GetLastError` at `0x1800f519d`
- `KERNEL32!GetLastError` at `0x1800f5223`
- `KERNEL32!GetLastError` at `0x1800f52c9`
- `KERNEL32!GetLastError` at `0x1800f53b6`
- `KERNEL32!GetLastError` at `0x1800f5b9d`
- `KERNEL32!GetLastError` at `0x1800f6536`
- `KERNEL32!GetLastError` at `0x1800f664f`
- `KERNEL32!GetLastError` at `0x1800f6eda`
- `KERNEL32!GetLastError` at `0x1800f70c4`
- `KERNEL32!GetLastError` at `0x1800f70dc`
- `KERNEL32!GetLastError` at `0x1800f70f4`
- `KERNEL32!GetLastError` at `0x1800f725c`
- `KERNEL32!GetLastError` at `0x1800f72d1`
- `KERNEL32!GetLastError` at `0x1800f75bb`
- `KERNEL32!GetLastError` at `0x1800f7665`
- `KERNEL32!GetLastError` at `0x1800f789b`
- `KERNEL32!GetLastError` at `0x1800f7a59`
- `KERNEL32!GetLastError` at `0x1800f7b8f`
- `KERNEL32!GetLastError` at `0x1800f7ca1`
- `KERNEL32!GetLastError` at `0x1800f7f1c`
- `KERNEL32!GetLastError` at `0x1800f804c`
- `KERNEL32!GetLastError` at `0x1800f8158`
- `KERNEL32!GetLastError` at `0x1800f82a0`
- `KERNEL32!GetLastError` at `0x1800f83b6`
- `KERNEL32!GetLastError` at `0x1800f9e43`
- `KERNEL32!GetLastError` at `0x1800f9eb8`
- `KERNEL32!GetLastError` at `0x1800f9f4a`
- `KERNEL32!GetLastError` at `0x1800f9fdd`
- `KERNEL32!GetLastError` at `0x1800fa0ff`
- `KERNEL32!GetLastError` at `0x1800fa174`
- `KERNEL32!GetLastError` at `0x1800fa21e`
- `KERNEL32!GetLastError` at `0x1800fa2dc`
- `KERNEL32!GetLastError` at `0x1800fa364`
- `KERNEL32!GetLastError` at `0x1800fa416`
- `KERNEL32!GetLastError` at `0x1800fa557`
- `KERNEL32!GetLastError` at `0x1800fa663`
- `KERNEL32!GetLastError` at `0x1800fa955`
- `KERNEL32!GetLastError` at `0x1800fa9d9`
- `KERNEL32!GetLastError` at `0x1800faa72`
- `KERNEL32!GetLastError` at `0x1800fab13`
- `KERNEL32!GetLastError` at `0x1800fabd7`
- `KERNEL32!GetLastError` at `0x1800fac54`
- `KERNEL32!GetLastError` at `0x1800fad13`
- `KERNEL32!GetLastError` at `0x1800faddc`
- `KERNEL32!GetLastError` at `0x1800fae59`
- `KERNEL32!GetLastError` at `0x1800faf26`
- `KERNEL32!GetLastError` at `0x1800fb020`
- `KERNEL32!GetLastError` at `0x1800fbf3e`
- `KERNEL32!GetLastError` at `0x1800fbfd3`
- `KERNEL32!GetLastError` at `0x1800fc077`
- `KERNEL32!GetLastError` at `0x1800fc11a`
- `KERNEL32!GetLastError` at `0x1800fc187`
- `KERNEL32!GetLastError` at `0x1800fc275`
- `KERNEL32!GetLastError` at `0x1800fc388`
- `KERNEL32!GetLastError` at `0x1800fc4bb`
- `KERNEL32!GetLastError` at `0x1800fc5c0`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800fc30c`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800fc30c`
- `ole32!StringFromGUID2` at `0x1800f70b6`
- `ole32!StringFromGUID2` at `0x1800f70b6`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1800fbc6b`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1800fbc6b`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f87e3`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f8cb2`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f910b`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f95cf`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f87e3`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f8cb2`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f910b`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800f95cf`

## string_xrefs

- `0x1800f6b51`: `Windows.old`
- `0x1800f6d3f`: `Windows.old`
- `0x1800fa7af`: `Windows.old`
- `0x1800fb5d3`: `Windows.old`
- `0x1800f2bd3`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2c77`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2d85`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2e06`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2eb6`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2f4e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f2fd1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f304b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f325c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f32d8`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f3383`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f33de`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f3599`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f36ca`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f37af`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f3af4`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f3c1e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f3f4d`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f40bc`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4135`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f41e5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f425c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f47c1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4838`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f48ff`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f49cd`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4a6c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4b0b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4bb2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4c7b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f4d0b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f5019`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f508e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f5105`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f5175`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f51e5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f5267`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f530a`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f53f7`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f5c13`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f657d`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f6697`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f6f1b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7138`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f72a0`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f732b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7607`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f76ae`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f78d5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7acb`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7c01`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7ce3`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f7f8f`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f80bf`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f81b5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f82f9`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f840c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f9ce3`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa258`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa316`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa3a5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa457`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa59c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa5f8`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa69d`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fa996`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800faa1a`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800faab3`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fab6d`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fac1b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fac95`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fad54`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fae16`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fae48`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fb061`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fbf98`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc014`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc0b8`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc171`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc1cb`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc2c8`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc3e2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc516`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800fc604`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800f9df5`: `ExternalRollback`
- `0x1800fb2b2`: `ExternalRollback`
- `0x1800f2b59`: `SP_ENV_DISABLE_READING_ONESETTING`
- `0x1800f2c47`: `Failed to create OneSettings infrastructure. Error: 0x%08X`
- `0x1800f86a7`: `PathForNewOSFile%d`
- `0x1800f8fcf`: `PathForNewOSFile%d`
- `0x1800f87b9`: `PathForNewOSFile`
- `0x1800f8947`: `PathForNewOSFile`
- `0x1800f90e1`: `PathForNewOSFile`
- `0x1800f9265`: `PathForNewOSFile`
- `0x1800f6b35`: `OsPaths`
- `0x1800f351b`: `MonitoringExtraPaths`
- `0x1800f3562`: `MonitoringExtraPaths`
- `0x1800f3693`: `MonitoringExtraPaths`
- `0x1800f39e9`: `MonitoringExtraPaths`
- `0x1800f377f`: `Found environment variable value [%s] for monitoring extra paths; overriding all other input`
- `0x1800f3703`: `SP_ENV_MONITORING_EXTRA_PATHS`
- `0x1800f3ac5`: `OEM folder [%s] is inside the root folder, no need to copy it`
- `0x1800f3bed`: `OEM folder is outside the root folder, copying [%s] to [%s]`
- `0x1800f3c9b`: `Copy OEM folder`
- `0x1800f454b`: `SafeOS.Mount`
- `0x1800f4382`: `Copy Setup Platform footprint`
- `0x1800f654d`: `Could not copy partition name to extend %s; partition will not be extended. Error: 0x%08X`
- `0x1800f6467`: `Request extension of partition name %s`
- `0x1800f6774`: `CompressHelper`
- `0x1800f685f`: `CompressHelper`
- `0x1800f6667`: `%hs: Low disk space policy in place, adding compress operation.`
- `0x1800f6ba0`: `Reserved.Recompress`
- `0x1800f6eeb`: `Will skip installing WinRE operations.`
- `0x1800f72fb`: `Will cleanup the installed WinRE for the target OS [%s].`
- `0x1800f79dc`: `$1\Windows\System32\Recovery\winre.wim`
- `0x1800f7c2d`: `$1\Windows\System32\Recovery\winre.wim`
- `0x1800f7992`: `$$\System32\Recovery\winre.wim`
- `0x1800f7af7`: `$$\System32\Recovery\winre.wim`
- `0x1800f83dc`: `OEM folder [%s] does not contain WinRE, skip copying it for Safe OS`
- `0x1800f7a9b`: `OEM folder [%s] contains WinRE at [%s], copy it for Safe OS`
- `0x1800f7bd1`: `OEM folder [%s] contains WinRE at [%s], copy it for Safe OS`
- `0x1800f7cb2`: `Copy Safe OS from OEM folder`
- `0x1800f82c6`: `OEM folder [%s] does not contain boot.sdi, skip copying it for Safe OS`
- `0x1800f7f5e`: `OEM folder [%s] contains boot.sdi at [%s], copy it for Safe OS`
- `0x1800f808e`: `OEM folder [%s] contains boot.sdi at [%s], copy it for Safe OS`
- `0x1800f8182`: `Copy boot.sdi for Safe OS from OEM folder`
- `0x1800f8535`: `\Windows\System32\Recovery\winre.wim`
- `0x1800f8ab3`: `\Windows\System32\Recovery\winre.wim`
- `0x1800f8e5d`: `\Windows\System32\Recovery\winre.wim`
- `0x1800f93d2`: `\Windows\System32\Recovery\winre.wim`
- `0x1800f786d`: `SetupPlatform.exe /rollback`
- `0x1800f9c46`: `SetupPlatform.exe /rollback`
- `0x1800f78ac`: `Not extracting the WinRE system, there is no need for it during the installation`
- `0x1800f7878`: `Windows Rollback`
- `0x1800f9cab`: `Windows Rollback`
- `0x1800f9ec9`: `FLOWTRACK: Turning ON SafeOS boot removal per install flow requirement`
- `0x1800f9f5b`: `FLOWTRACK: Reading OneSetting for SafeOS boot removal`
- `0x1800fa185`: `FLOWTRACK: Turning ON SafeOS boot removal per install flow desire`
- `0x1800fa375`: `FLOWTRACK: Cannot attempt SafeOS boot removal, NEO path is disabled`
- `0x1800fa427`: `FLOWTRACK: Cannot attempt SafeOS boot removal, source is a WIMBoot system`
- `0x1800fa5cd`: `FLOWTRACK: Will not attempt SafeOS boot removal, maximum attempts reached`
- `0x1800fa571`: `FLOWTRACK: SafeOS boot removal maximum attempts reached, will continue due to force environment variable.`
- `0x1800fa674`: `FLOWTRACK: Will attempt SafeOS boot removal`
- `0x1800fa638`: `MaxFailureAttempt`
- `0x1800fa9ea`: `FLOWTRACK: Turning ON First boot removal per install flow requirement`
- `0x1800faa83`: `FLOWTRACK: Reading OneSetting for First boot removal`
- `0x1800fac65`: `FLOWTRACK: Turning ON First boot removal per install flow desire`
- `0x1800fae6a`: `FLOWTRACK: Will attempt First boot removal`
- `0x1800fb038`: `FLOWTRACK(SAFEOS): Failing installation due to scenario constraint (%d). Skip SafeOS boot is turned off.`
- `0x1800faf3e`: `FLOWTRACK(FIRST): Failing installation due to scenario constraint (%d). Skip First boot is turned off.`
- `0x1800fb500`: `Cleanup caches in low-disk space`
- `0x1800fb225`: `/executeInstall`
- `0x1800fbd5a`: `Cleanup Windows.old at end`
- `0x1800fbc5c`: `Windows.old\`
- `0x1800fbdd5`: `%SystemDrive%\Windows.old\$WINDOWS.~BT`
- `0x1800fbfe4`: `Turning ON offline user migration per install flow constraint`
- `0x1800fc088`: `Reading onesetting for offline user migration`
- `0x1800fc49f`: `RegistryRemapExceptions`
- `0x1800fc3b2`: `Found environment variable value [%s] for registry remapping exceptions; skipping all other queries`
- `0x1800fc5d4`: `Failed to get registry remapping exceptions, 0x%x`
- `0x1800fc4e6`: `Got registry remapping exceptions: %s`
- `0x1800fc770`: `StartServices`
- `0x1800fc7d8`: `StartServices`
- `0x1800fc769`: `Start system services for online actions`
- `0x1800fc7d1`: `Ensure system services are running for OOBE boot`

## pseudocode

```c
// Hidden C++ exception states: #wind=263
void __fastcall __noreturn CNewSystem::QueueOperations(
        CNewSystem *this,
        struct CImageInfo *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        enum _FIRMWARE_TYPE a5,
        const unsigned __int16 *a6,
        int a7)
{
  UnBCL::String *P; // rax
  const unsigned __int16 *CString; // rax
  UnBCL::String *v11; // rax
  const unsigned __int16 *v12; // rax
  const struct UnBCL::String *v13; // rax
  int IsEnvironmentVarSetTrue; // ebx
  DWORD LastError; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  struct ISetupOneSettings **v18; // rax
  int SetupOneSettings; // esi
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  int v23; // esi
  int *v24; // r15
  unsigned __int8 (__fastcall *v25)(_QWORD *, __int64 *); // rax
  __int64 (__fastcall ***v26)(_QWORD, const wchar_t *, char *); // rax
  int v27; // r12d
  DWORD v28; // edi
  __int64 v29; // rbx
  const wchar_t *v30; // r9
  struct tagLOG_PARTIAL_MSG *v31; // rax
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  const struct UnBCL::String *v35; // rax
  int v36; // ebx
  DWORD v37; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  const struct UnBCL::String *v40; // rax
  int v41; // ebx
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  DWORD v48; // edi
  __int64 v49; // rbx
  struct tagLOG_PARTIAL_MSG *v50; // rax
  void (__fastcall *v51)(CNewSystem *, __int64, char *); // rdi
  CBool *v52; // rax
  CBool *v53; // rdx
  char *v54; // rbx
  __int64 v55; // rax
  void (__fastcall *v56)(CNewSystem *, __int64, char *); // rdi
  CBool *v57; // rax
  CBool *v58; // rdx
  char *v59; // rbx
  __int64 v60; // rax
  __int64 v61; // rdx
  unsigned __int8 (__fastcall *v62)(_QWORD *, __int64 *); // rax
  __int64 (__fastcall ***v63)(_QWORD, const wchar_t *, char *); // rax
  int v64; // esi
  DWORD v65; // edi
  __int64 v66; // rbx
  const wchar_t *v67; // r9
  struct tagLOG_PARTIAL_MSG *v68; // rax
  DWORD v69; // edi
  __int64 v70; // rbx
  struct tagLOG_PARTIAL_MSG *v71; // rax
  int v72; // ebx
  const struct UnBCL::String *v73; // rax
  int v74; // ebx
  int v75; // eax
  DWORD v76; // edi
  __int64 v77; // rbx
  struct tagLOG_PARTIAL_MSG *v78; // rax
  DWORD v79; // edi
  __int64 v80; // rbx
  struct tagLOG_PARTIAL_MSG *v81; // rax
  void (__fastcall *v82)(CNewSystem *, __int64, char *); // rdi
  CBool *v83; // rax
  CBool *v84; // rdx
  char *v85; // rbx
  __int64 v86; // rax
  unsigned __int8 (__fastcall *v87)(_QWORD *, __int64 *); // rax
  __int64 v88; // rdi
  __int64 (__fastcall *v89)(__int64, const wchar_t *, __int64, int *); // rbx
  __int64 v90; // rax
  int v91; // esi
  DWORD v92; // edi
  __int64 v93; // rbx
  const char *v94; // rax
  struct tagLOG_PARTIAL_MSG *v95; // rax
  UnBCL::String *v96; // rbx
  const unsigned __int16 *v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  DWORD v100; // edi
  __int64 v101; // rbx
  struct tagLOG_PARTIAL_MSG *v102; // rax
  const struct UnBCL::String *v103; // rcx
  struct UnBCL::String *EnvironmentVar; // rax
  DWORD v105; // edi
  __int64 v106; // rbx
  UnBCL::String *v107; // rax
  const char *v108; // rax
  struct tagLOG_PARTIAL_MSG *v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  _QWORD *v112; // rax
  _QWORD *v113; // rbx
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rdi
  void (__fastcall *v117)(__int64, struct UnBCL::String *); // rbx
  UnBCL::String *v118; // rax
  const unsigned __int16 *v119; // rax
  struct UnBCL::String *v120; // rax
  int i; // ebx
  __int64 v122; // rax
  int (__fastcall ***v123)(_QWORD); // rcx
  CStoredString *v124; // rdi
  __int64 v125; // rax
  __int64 v126; // rcx
  struct UnBCL::String **v127; // rax
  CStoredString *v128; // rdx
  struct UnBCL::ISerializable *v129; // rdi
  struct UnBCL::String *v130; // rax
  struct UnBCL::String *v131; // rbx
  struct UnBCL::String *v132; // rax
  __int64 v133; // rbx
  void (__fastcall *v134)(__int64, __int64); // rdi
  void *v135; // rax
  __int64 v136; // rax
  __int64 v137; // rcx
  DWORD v138; // edi
  __int64 v139; // rbx
  struct tagLOG_PARTIAL_MSG *v140; // rax
  __int64 v141; // rdi
  void (__fastcall *v142)(__int64, __int64); // rsi
  void *v143; // rbx
  UnBCL::String *v144; // rax
  const unsigned __int16 *v145; // rax
  __int64 v146; // rax
  int *v147; // rsi
  unsigned __int8 (__fastcall *v148)(_QWORD *, __int64 *); // rax
  __int64 (__fastcall ***v149)(_QWORD, const wchar_t *, char *); // rax
  int v150; // r15d
  DWORD v151; // edi
  __int64 v152; // rbx
  const wchar_t *v153; // r9
  struct tagLOG_PARTIAL_MSG *v154; // rax
  DWORD v155; // edi
  __int64 v156; // rbx
  struct tagLOG_PARTIAL_MSG *v157; // rax
  int v158; // ebx
  const struct UnBCL::String *v159; // rax
  int v160; // ebx
  DWORD v161; // edi
  __int64 v162; // rbx
  struct tagLOG_PARTIAL_MSG *v163; // rax
  DWORD v164; // edi
  __int64 v165; // rbx
  struct tagLOG_PARTIAL_MSG *v166; // rax
  struct UnBCL::String *v167; // rbx
  struct UnBCL::String *v168; // rax
  UnBCL::ArgumentNullException *v169; // rax
  UnBCL::ArgumentNullException *v170; // rbx
  UnBCL::ArgumentNullException *v171; // rax
  UnBCL::ArgumentNullException *v172; // rbx
  _QWORD v173[2]; // [rsp+B0h] [rbp-50h] BYREF
  enum _FIRMWARE_TYPE v174; // [rsp+C4h] [rbp-3Ch]
  const unsigned __int16 *v175; // [rsp+C8h] [rbp-38h]
  CNewSystem *v176; // [rsp+108h] [rbp+8h]
  int v177; // [rsp+110h] [rbp+10h]
  struct CImageInfo *v178; // [rsp+150h] [rbp+50h]
  _QWORD v179[2]; // [rsp+190h] [rbp+90h] BYREF
  int v180; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v181[16]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v182; // [rsp+350h] [rbp+250h] BYREF
  __int64 v183; // [rsp+358h] [rbp+258h] BYREF
  __int64 v184; // [rsp+360h] [rbp+260h] BYREF
  __int64 pExceptionObject; // [rsp+368h] [rbp+268h] BYREF
  __int64 v186; // [rsp+370h] [rbp+270h] BYREF
  __int64 v187; // [rsp+378h] [rbp+278h] BYREF
  _BYTE v188[16]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v189[16]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v190[16]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v191[16]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v192; // [rsp+620h] [rbp+520h]
  _BYTE v193[24]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v194[24]; // [rsp+658h] [rbp+558h] BYREF
  _BYTE v195[24]; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v196[24]; // [rsp+688h] [rbp+588h] BYREF
  _BYTE v197[24]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v198[24]; // [rsp+6B8h] [rbp+5B8h] BYREF
  _BYTE v199[24]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v200[24]; // [rsp+6E8h] [rbp+5E8h] BYREF
  _BYTE v201[24]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v202[24]; // [rsp+730h] [rbp+630h] BYREF

  v192 = -2;
  v175 = a4;
  v178 = a2;
  v176 = this;
  v174 = a5;
  if ( !a2 )
  {
    v171 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v172 = v171;
    if ( v171 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v171, L"ImageInfo");
      *(_QWORD *)v172 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v172 = 0;
    }
    v186 = AddStackTraceToException<UnBCL::InvalidOperationException>(
             v172,
             "long __cdecl CNewSystem::QueueOperations(class CImageInfo *,__int64,const unsigned short *,enum _FIRMWARE_T"
             "YPE,const unsigned short *,int)");
    throw (UnBCL::ArgumentNullException **)&v186;
  }
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a2 + 392) )
  {
    v169 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v170 = v169;
    if ( v169 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v169, L"ImageInfo->SystemDrive");
      *(_QWORD *)v170 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v170 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v170,
                         "long __cdecl CNewSystem::QueueOperations(class CImageInfo *,__int64,const unsigned short *,enum"
                         " _FIRMWARE_TYPE,const unsigned short *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a2 + 224);
  CString = UnBCL::String::get_CString(P);
  if ( !UnBCL::String::Compare(CString, L"IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE", 0)
    || (v177 = 0,
        v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a2 + 224),
        v12 = UnBCL::String::get_CString(v11),
        !UnBCL::String::Compare(v12, L"IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT", 0)) )
  {
    v177 = 1;
  }
  v173[1] = 0;
  v173[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
  v13 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v193, L"SP_ENV_DISABLE_READING_ONESETTING");
  IsEnvironmentVarSetTrue = UnBCL::Environment::IsEnvironmentVarSetTrue(v13, 0);
  UnBCL::String::~String((UnBCL::String *)v193);
  if ( IsEnvironmentVarSetTrue )
  {
    LastError = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(0x4000000u, "OneSettings is disabled, will not query");
    WdsSetupLogMessageW(
      v17,
      819200,
      L"D",
      0,
      5694,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueOperations",
      v16,
      LastError,
      0,
      0);
  }
  else
  {
    v18 = (struct ISetupOneSettings **)(*(__int64 (__fastcall **)(_QWORD *))(v173[0] + 8LL))(v173);
    SetupOneSettings = CreateSetupOneSettings(L"WSD", L"SetupPlatform", v18);
    if ( SetupOneSettings < 0 )
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = ConstructPartialMsgW(
              0x3000000u,
              "Failed to create OneSettings infrastructure. Error: 0x%08X",
              SetupOneSettings);
      WdsSetupLogMessageW(
        v22,
        819200,
        L"D",
        0,
        5701,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v21,
        v20,
        0,
        0);
      (*(void (__fastcall **)(_QWORD *, _QWORD))(v173[0] + 48LL))(v173, 0);
    }
  }
  v23 = 0;
  v24 = (int *)((char *)this + 904);
  if ( !*((_DWORD *)this + 226) )
  {
    v25 = *(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v173[0] + 64LL);
    v184 = 0;
    if ( v25(v173, &v184) )
    {
      v26 = (__int64 (__fastcall ***)(_QWORD, const wchar_t *, char *))(*(__int64 (__fastcall **)(_QWORD *))(v173[0] + 24LL))(v173);
      v27 = (**v26)(v26, L"UseMonitoringDriver", (char *)this + 904);
      if ( v27 < 0 )
      {
        v32 = GetLastError();
        v33 = CurrentIP();
        v34 = ConstructPartialMsgW(
                0x3000000u,
                "SETUPMON: Failed to get OneSettings value for %s. Error: 0x%08X",
                (const char *)L"UseMonitoringDriver",
                v27);
        WdsSetupLogMessageW(
          v34,
          819200,
          L"D",
          0,
          5723,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v33,
          v32,
          0,
          0);
      }
      else
      {
        v28 = GetLastError();
        v29 = CurrentIP();
        v30 = L"TRUE";
        if ( !*v24 )
          v30 = L"FALSE";
        v31 = ConstructPartialMsgW(
                0x4000000u,
                "SETUPMON: OneSettings value for %s: %s",
                (const char *)L"UseMonitoringDriver",
                (const char *)v30);
        WdsSetupLogMessageW(
          v31,
          819200,
          L"D",
          0,
          5718,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v29,
          v28,
          0,
          0);
        v23 = 1;
      }
    }
  }
  v35 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v194, L"SP_ENV_ENABLE_MONITORING_DRIVER");
  v36 = UnBCL::Environment::IsEnvironmentVarSetTrue(v35, 0);
  UnBCL::String::~String((UnBCL::String *)v194);
  if ( v36 )
  {
    if ( !*v24 )
    {
      *v24 = 1;
      v37 = GetLastError();
      v38 = CurrentIP();
      v39 = ConstructPartialMsgW(0x4000000u, "SETUPMON: Use of monitoring driver is enabled by environment variable");
      WdsSetupLogMessageW(
        v39,
        819200,
        L"D",
        0,
        5734,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v38,
        v37,
        0,
        0);
    }
  }
  else
  {
    v40 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v195, L"SP_ENV_ENABLE_MONITORING_DRIVER");
    v41 = UnBCL::Environment::IsEnvironmentVarSetTrue(v40, 1);
    UnBCL::String::~String((UnBCL::String *)v195);
    if ( v41 )
      goto LABEL_24;
    if ( *v24 )
    {
      *v24 = 0;
      v42 = GetLastError();
      v43 = CurrentIP();
      v44 = ConstructPartialMsgW(0x4000000u, "SETUPMON: Use of monitoring driver is disabled by environment variable");
      WdsSetupLogMessageW(
        v44,
        819200,
        L"D",
        0,
        5743,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v43,
        v42,
        0,
        0);
    }
  }
  v23 = 1;
LABEL_24:
  if ( !*((_DWORD *)this + 201) )
  {
    *v24 = 0;
    v23 = 1;
    v45 = GetLastError();
    v46 = CurrentIP();
    v47 = ConstructPartialMsgW(
            0x4000000u,
            "SETUPMON: Use of monitoring driver is disabled because we are not replacing an existing OS");
    WdsSetupLogMessageW(
      v47,
      819200,
      L"D",
      0,
      5753,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueOperations",
      v46,
      v45,
      0,
      0);
  }
  if ( !*v24 && !v23 )
  {
    v48 = GetLastError();
    v49 = CurrentIP();
    v50 = ConstructPartialMsgW(0x4000000u, "SETUPMON: Monitoring policy not set explicitly; enabling log-only mode");
    WdsSetupLogMessageW(
      v50,
      819200,
      L"D",
      0,
      5758,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueOperations",
      v49,
      v48,
      0,
      0);
    *v24 = 1;
    *((_DWORD *)this + 228) = 1;
  }
  v51 = *(void (__fastcall **)(CNewSystem *, __int64, char *))(*(_QWORD *)this + 96LL);
  v52 = (CBool *)UnBCL::Object::operator new(0x40u);
  if ( v52 )
    v53 = CBool::CBool(v52, *v24);
  else
    v53 = 0;
  if ( v53 )
    v54 = (char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 8LL) + 8;
  else
    v54 = 0;
  v55 = UnBCL::String::String((UnBCL::String *)v196, L"UseMonitoringDriver");
  v51(this, v55, v54);
  UnBCL::String::~String((UnBCL::String *)v196);
  v56 = *(void (__fastcall **)(CNewSystem *, __int64, char *))(*(_QWORD *)this + 96LL);
  v57 = (CBool *)UnBCL::Object::operator new(0x40u);
  if ( v57 )
    v58 = CBool::CBool(v57, *((_DWORD *)this + 228));
  else
    v58 = 0;
  if ( v58 )
    v59 = (char *)v58 + *(int *)(*((_QWORD *)v58 + 1) + 8LL) + 8;
  else
    v59 = 0;
  v60 = UnBCL::String::String((UnBCL::String *)v197, L"MonitoringDriverLogOnly");
  v56(this, v60, v59);
  UnBCL::String::~String((UnBCL::String *)v197);
  if ( *v24 )
  {
    v62 = *(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v173[0] + 64LL);
    v187 = 0;
    if ( v62(v173, &v187) )
    {
      v63 = (__int64 (__fastcall ***)(_QWORD, const wchar_t *, char *))(*(__int64 (__fastcall **)(_QWORD *))(v173[0] + 24LL))(v173);
      v64 = (**v63)(v63, L"MonitoringDriverCritical", (char *)this + 908);
      if ( v64 < 0 )
      {
        v69 = GetLastError();
        v70 = CurrentIP();
        v71 = ConstructPartialMsgW(
                0x3000000u,
                "SETUPMON: Failed to get OneSettings value for %s. Error: 0x%08X",
                (const char *)L"MonitoringDriverCritical",
                v64);
        WdsSetupLogMessageW(
          v71,
          819200,
          L"D",
          0,
          5782,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v70,
          v69,
          0,
          0);
      }
      else
      {
        v65 = GetLastError();
        v66 = CurrentIP();
        v67 = L"TRUE";
        if ( !*((_DWORD *)this + 227) )
          v67 = L"FALSE";
        v68 = ConstructPartialMsgW(
                0x4000000u,
                "SETUPMON: OneSettings value for %s: %s",
                (const char *)L"MonitoringDriverCritical",
                (const char *)v67);
        WdsSetupLogMessageW(
          v68,
          819200,
          L"D",
          0,
          5778,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v66,
          v65,
          0,
          0);
      }
    }
    v72 = *((_DWORD *)this + 227);
    v73 = (const struct UnBCL::String *)UnBCL::String::String(
                                          (UnBCL::String *)v198,
                                          L"SP_ENV_MONITORING_DRIVER_CRITICAL");
    v74 = UnBCL::Environment::IsEnvironmentVarSetTrue(v73, v72);
    UnBCL::String::~String((UnBCL::String *)v198);
    v75 = *((_DWORD *)this + 227);
    if ( v74 )
    {
      if ( !v75 )
      {
        *((_DWORD *)this + 227) = 1;
        v76 = GetLastError();
        v77 = CurrentIP();
        v78 = ConstructPartialMsgW(
                0x4000000u,
                "SETUPMON: Criticality of monitoring driver is enabled by environment variable");
        WdsSetupLogMessageW(
          v78,
          819200,
          L"D",
          0,
          5792,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v77,
          v76,
          0,
          0);
      }
    }
    else if ( v75 )
    {
      *((_DWORD *)this + 227) = 0;
      v79 = GetLastError();
      v80 = CurrentIP();
      v81 = ConstructPartialMsgW(
              0x4000000u,
              "SETUPMON: Criticality of monitoring driver is disabled by environment variable");
      WdsSetupLogMessageW(
        v81,
        819200,
        L"D",
        0,
        5800,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v80,
        v79,
        0,
        0);
    }
    v82 = *(void (__fastcall **)(CNewSystem *, __int64, char *))(*(_QWORD *)this + 96LL);
    v83 = (CBool *)UnBCL::Object::operator new(0x40u);
    if ( v83 )
      v84 = CBool::CBool(v83, *((_DWORD *)this + 227));
    else
      v84 = 0;
    if ( v84 )
      v85 = (char *)v84 + *(int *)(*((_QWORD *)v84 + 1) + 8LL) + 8;
    else
      v85 = 0;
    v86 = UnBCL::String::String((UnBCL::String *)v199, L"MonitoringDriverCritical");
    v82(this, v86, v85);
    UnBCL::String::~String((UnBCL::String *)v199);
    v87 = *(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v173[0] + 64LL);
    v183 = 0;
    if ( v87(v173, &v183) )
    {
      v180 = 0x10000;
      v179[1] = operator new[](0x20000u);
      v179[0] = &RAII::CAutoDeleteArray<unsigned short>::`vftable';
      v88 = (*(__int64 (__fastcall **)(_QWORD *))(v173[0] + 24LL))(v173);
      v89 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, int *))(*(_QWORD *)v88 + 16LL);
      v90 = (*(__int64 (__fastcall **)(_QWORD *))(v179[0] + 32LL))(v179);
      v91 = v89(v88, L"MonitoringExtraPaths", v90, &v180);
      if ( v91 < 0 )
      {
        v100 = GetLastError();
        v101 = CurrentIP();
        v102 = ConstructPartialMsgW(
                 0x3000000u,
                 "SETUPMON: Failed to get OneSettings value for %s. Error: 0x%08X",
                 (const char *)L"MonitoringExtraPaths",
                 v91);
        WdsSetupLogMessageW(
          v102,
          819200,
          L"D",
          0,
          5820,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v101,
          v100,
          0,
          0);
      }
      else
      {
        v92 = GetLastError();
        v93 = CurrentIP();
        v94 = (const char *)(*(__int64 (__fastcall **)(_QWORD *))(v179[0] + 32LL))(v179);
        v95 = ConstructPartialMsgW(
                0x4000000u,
                "SETUPMON: OneSettings value for %s: %s",
                (const char *)L"MonitoringExtraPaths",
                v94);
        WdsSetupLogMessageW(
          v95,
          819200,
          L"D",
          0,
          5814,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v93,
          v92,
          0,
          0);
        v96 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        if ( v96 )
        {
          v97 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))(v179[0] + 32LL))(v179);
          UnBCL::String::String(v96, v97);
          *(_QWORD *)v96 = &UnBCL::String::`local vftable';
        }
        else
        {
          v96 = 0;
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v188, v96);
        v98 = UnBCL::SmartPtr<UnBCL::String>::operator->(v188);
        v99 = UnBCL::String::Split(v98, L";");
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v191, v99);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=((char *)this + 920, v191);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v191);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v188);
      }
      RAII::CAutoDeleteArray<unsigned short>::~CAutoDeleteArray<unsigned short>(v179);
    }
    v103 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v200, L"SP_ENV_MONITORING_EXTRA_PATHS");
    EnvironmentVar = UnBCL::Environment::GetEnvironmentVar(v103);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v181, EnvironmentVar);
    UnBCL::String::~String((UnBCL::String *)v200);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v181) )
    {
      v105 = GetLastError();
      v106 = CurrentIP();
      v107 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v181);
      v108 = (const char *)UnBCL::String::get_CString(v107);
      v109 = ConstructPartialMsgW(
               0x4000000u,
               "Found environment variable value [%s] for monitoring extra paths; overriding all other input",
               v108);
      WdsSetupLogMessageW(
        v109,
        819200,
        L"D",
        0,
        5828,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v106,
        v105,
        0,
        0);
      v110 = UnBCL::SmartPtr<UnBCL::String>::operator->(v181);
      v111 = UnBCL::String::Split(v110, L";");
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v189, v111);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=((char *)this + 920, v189);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v189);
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216) )
    {
      if ( !UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P((char *)this + 920) )
      {
        v112 = UnBCL::Object::operator new(0xB0u);
        v113 = v112;
        if ( v112 )
        {
          UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v112, 1);
          v113[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
        }
        else
        {
          v113 = 0;
        }
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v190, v113);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=((char *)this + 920, v190);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v190);
        v114 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->((char *)this + 920);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v114 + 40LL))(v114, 1);
      }
      v115 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->((char *)this + 920);
      v116 = v115 + *(int *)(*(_QWORD *)(v115 + 8) + 16LL);
      v117 = *(void (__fastcall **)(__int64, struct UnBCL::String *))(*(_QWORD *)(v116 + 8) + 40LL);
      v118 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 216);
      v119 = UnBCL::String::get_CString(v118);
      v120 = UnBCL::String::Format(L"S,%s,S,,", v119);
      v117(v116 + 8, v120);
    }
    if ( UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P((char *)this + 920) )
    {
      for ( i = 0; ; ++i )
      {
        v122 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->((char *)this + 920);
        v123 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v122 + 8) + 12LL) + v122 + 8);
        if ( i >= (**v123)(v123) )
          break;
        v124 = (CStoredString *)UnBCL::Object::operator new(0x48u);
        if ( v124 )
        {
          v125 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->((char *)this + 920);
          v126 = *(int *)(*(_QWORD *)(v125 + 8) + 16LL) + v125 + 8;
          v127 = (struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v126 + 24LL))(
                                            v126,
                                            (unsigned int)i);
          v128 = CStoredString::CStoredString(v124, *v127);
        }
        else
        {
          v128 = 0;
        }
        if ( v128 )
          v129 = (CStoredString *)((char *)v128 + *(int *)(*((_QWORD *)v128 + 1) + 8LL) + 8);
        else
          v129 = 0;
        v130 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v201, L"MonitoringExtraPaths");
        SPAddToStoredObjectsGroup(this, v130, v129);
        UnBCL::String::~String((UnBCL::String *)v201);
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v181);
  }
  LOBYTE(v61) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Setup_EnableOEMFolderSupport>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_Setup_EnableOEMFolderSupport>::GetImpl'::`2'::impl,
    v61);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Setup_EnableOEMFolderSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Setup_EnableOEMFolderSupport>::GetImpl'::`2'::impl)
    && UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 712) )
  {
    v131 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 168);
    v132 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 712);
    SPIsPathInsideFolder(v132, v131);
  }
  if ( *v24 )
  {
    v133 = *((_QWORD *)this + 62) + *(int *)(*(_QWORD *)(*((_QWORD *)this + 62) + 8LL) + 16LL);
    v134 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v133 + 8) + 40LL);
    v135 = UnBCL::Object::operator new(0x118u);
    v136 = v135
         ? CInitializeMonitoringDriver::CInitializeMonitoringDriver(
             v135,
             0,
             1,
             0,
             *((_DWORD *)this + 227),
             1,
             3,
             2,
             2,
             1)
         : 0LL;
    v134(v133 + 8, v136);
    v137 = *((_QWORD *)this + 12);
    if ( v137 )
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v137 + 16LL))(
        v137,
        L"SP_SETUPMON_INFO",
        L"SPMonitoringDriverEnabled",
        L"TRUE");
  }
  if ( *((_DWORD *)this + 235) )
  {
    v138 = GetLastError();
    v139 = CurrentIP();
    v140 = ConstructPartialMsgW(0x4000000u, "Found disk is iSCSI, queueing iSCSI operation");
    WdsSetupLogMessageW(
      v140,
      819200,
      L"D",
      0,
      5928,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueOperations",
      v139,
      v138,
      0,
      0);
    v141 = *((_QWORD *)this + 62) + *(int *)(*(_QWORD *)(*((_QWORD *)this + 62) + 8LL) + 16LL);
    v142 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v141 + 8) + 40LL);
    v143 = UnBCL::Object::operator new(0x110u);
    if ( v143 )
    {
      v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 648);
      v145 = UnBCL::String::get_CString(v144);
      v146 = CAddIscsiBootDrivers::CAddIscsiBootDrivers(v143, v145, 75);
    }
    else
    {
      v146 = 0;
    }
    v142(v141 + 8, v146);
  }
  v147 = (int *)((char *)this + 936);
  if ( !*((_DWORD *)this + 234) )
  {
    v148 = *(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v173[0] + 64LL);
    v182 = 0;
    if ( v148(v173, &v182) )
    {
      v149 = (__int64 (__fastcall ***)(_QWORD, const wchar_t *, char *))(*(__int64 (__fastcall **)(_QWORD *))(v173[0] + 24LL))(v173);
      v150 = (**v149)(v149, L"AllowMigrationRetry", (char *)this + 936);
      if ( v150 < 0 )
      {
        v155 = GetLastError();
        v156 = CurrentIP();
        v157 = ConstructPartialMsgW(
                 0x3000000u,
                 "CNewSystem::QueueOperations: Failed to get OneSettings value for %s. Error: 0x%08X",
                 (const char *)L"AllowMigrationRetry",
                 v150);
        WdsSetupLogMessageW(
          v157,
          819200,
          L"D",
          0,
          5952,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v156,
          v155,
          0,
          0);
      }
      else
      {
        v151 = GetLastError();
        v152 = CurrentIP();
        v153 = L"TRUE";
        if ( !*v147 )
          v153 = L"FALSE";
        v154 = ConstructPartialMsgW(
                 0x4000000u,
                 "CNewSystem::QueueOperations: OneSettings value for %s: %s",
                 (const char *)L"AllowMigrationRetry",
                 (const char *)v153);
        WdsSetupLogMessageW(
          v154,
          819200,
          L"D",
          0,
          5948,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CNewSystem::QueueOperations",
          v152,
          v151,
          0,
          0);
      }
    }
  }
  v158 = *v147;
  v159 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v202, L"SP_ENV_ALLOW_MIGRATION_RETRY");
  v160 = UnBCL::Environment::IsEnvironmentVarSetTrue(v159, v158);
  UnBCL::String::~String((UnBCL::String *)v202);
  if ( v160 )
  {
    if ( !*v147 )
    {
      *v147 = 1;
      v161 = GetLastError();
      v162 = CurrentIP();
      v163 = ConstructPartialMsgW(
               0x4000000u,
               "CNewSystem::QueueOperations: %s is enabled by environment variable",
               (const char *)L"AllowMigrationRetry");
      WdsSetupLogMessageW(
        v163,
        819200,
        L"D",
        0,
        5963,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueOperations",
        v162,
        v161,
        0,
        0);
    }
  }
  else if ( *v147 )
  {
    *v147 = 0;
    v164 = GetLastError();
    v165 = CurrentIP();
    v166 = ConstructPartialMsgW(
             0x4000000u,
             "CNewSystem::QueueOperations: %s is disabled by environment variable",
             (const char *)L"AllowMigrationRetry");
    WdsSetupLogMessageW(
      v166,
      819200,
      L"D",
      0,
      5971,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueOperations",
      v165,
      v164,
      0,
      0);
  }
  v167 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 152);
  v168 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*((_QWORD *)this + 10) + 24LL);
  SPArePathsEqual(v168, v167);
}

```

## disassembly

```asm
0x1800f2a50  push    rbp
0x1800f2a52  push    rbx
0x1800f2a53  push    rsi
0x1800f2a54  push    rdi
0x1800f2a55  push    r12
0x1800f2a57  push    r13
0x1800f2a59  push    r14
0x1800f2a5b  push    r15
0x1800f2a5d  lea     rbp, [rsp-0F18h]
0x1800f2a65  mov     eax, 1018h
0x1800f2a6a  call    _alloca_probe
0x1800f2a6f  sub     rsp, rax
0x1800f2a72  mov     [rbp+0F50h+var_A30], 0FFFFFFFFFFFFFFFEh
0x1800f2a7d  mov     rax, cs:__security_cookie
0x1800f2a84  xor     rax, rsp
0x1800f2a87  mov     [rbp+0F50h+var_50], rax
0x1800f2a8e  mov     [rbp+0F50h+var_F88], r9
0x1800f2a92  mov     qword ptr [rbp+0F50h+var_FD0], r8
0x1800f2a96  mov     rbx, rdx
0x1800f2a99  mov     [rbp+0F50h+var_F00], rdx
0x1800f2a9d  mov     r14, rcx
0x1800f2aa0  mov     [rbp+0F50h+var_F48], rcx
0x1800f2aa4  mov     eax, [rbp+0F50h+arg_20]
0x1800f2aaa  mov     [rbp+0F50h+var_F8C], eax
0x1800f2aad  mov     rax, [rbp+0F50h+arg_28]
0x1800f2ab4  mov     [rbp+0F50h+var_FB0], rax
0x1800f2ab8  xor     r12d, r12d
0x1800f2abb  mov     r13d, r12d
0x1800f2abe  mov     [rbp+0F50h+var_FC8], r12d
0x1800f2ac2  mov     [rbp+0F50h+var_FB8], r12d
0x1800f2ac6  test    rdx, rdx
0x1800f2ac9  jz      loc_1800FC96C
0x1800f2acf  lea     rcx, [rdx+188h]
0x1800f2ad6  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800f2adc  test    rax, rax
0x1800f2adf  jz      loc_1800FC90C
0x1800f2ae5  lea     rcx, [rbx+0E0h]
0x1800f2aec  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800f2af2  mov     rcx, rax
0x1800f2af5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800f2afb  mov     rcx, rax
0x1800f2afe  xor     r8d, r8d
0x1800f2b01  lea     rdx, aImageStateGene; "IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE"
0x1800f2b08  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x1800f2b0e  test    eax, eax
0x1800f2b10  jz      short loc_1800F2B43
0x1800f2b12  mov     [rbp+0F50h+var_F40], r12d
0x1800f2b16  lea     rcx, [rbx+0E0h]
0x1800f2b1d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800f2b23  mov     rcx, rax
0x1800f2b26  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800f2b2c  mov     rcx, rax
0x1800f2b2f  xor     r8d, r8d
0x1800f2b32  lea     rdx, aImageStateGene_0; "IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT"
0x1800f2b39  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x1800f2b3f  test    eax, eax
0x1800f2b41  jnz     short loc_1800F2B4A
0x1800f2b43  mov     [rbp+0F50h+var_F40], 1
0x1800f2b4a  mov     [rbp+0F50h+var_F98], r12
0x1800f2b4e  lea     rax, ??_7?$CAutoRelease@PEAUISetupOneSettings@@@RAII@@6B@; const RAII::CAutoRelease<ISetupOneSettings *>::`vftable'
0x1800f2b55  mov     [rbp+0F50h+var_FA0], rax
0x1800f2b59  lea     rdx, aSpEnvDisableRe; "SP_ENV_DISABLE_READING_ONESETTING"
0x1800f2b60  lea     rcx, [rbp+0F50h+var_A10]
0x1800f2b67  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800f2b6d  nop
0x1800f2b6e  xor     edx, edx
0x1800f2b70  mov     rcx, rax
0x1800f2b73  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800f2b79  mov     ebx, eax
0x1800f2b7b  lea     rcx, [rbp+0F50h+var_A10]
0x1800f2b82  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800f2b88  lea     rsi, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2b8f  mov     r15d, 0C8000h
0x1800f2b95  test    ebx, ebx
0x1800f2b97  jz      short loc_1800F2C02
0x1800f2b99  call    cs:__imp_GetLastError
0x1800f2b9f  mov     edi, eax
0x1800f2ba1  call    cs:__imp_CurrentIP
0x1800f2ba7  mov     rbx, rax
0x1800f2baa  lea     rdx, aOnesettingsIsD; "OneSettings is disabled, will not query"
0x1800f2bb1  mov     ecx, 4000000h; unsigned int
0x1800f2bb6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2bbb  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2bc0  mov     [rsp+1050h+var_1008], r12
0x1800f2bc5  mov     [rsp+1050h+var_1010], edi
0x1800f2bc9  mov     [rsp+1050h+var_1018], rbx
0x1800f2bce  mov     [rsp+1050h+pcbData], rsi
0x1800f2bd3  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2bda  mov     [rsp+1050h+pvData], rcx
0x1800f2bdf  mov     dword ptr [rsp+1050h+pdwType], 163Eh
0x1800f2be7  xor     r9d, r9d
0x1800f2bea  lea     r8, aD_0; "D"
0x1800f2bf1  mov     edx, r15d
0x1800f2bf4  mov     rcx, rax
0x1800f2bf7  call    cs:__imp_WdsSetupLogMessageW
0x1800f2bfd  jmp     loc_1800F2CB4
0x1800f2c02  mov     rax, [rbp+0F50h+var_FA0]
0x1800f2c06  lea     rcx, [rbp+0F50h+var_FA0]
0x1800f2c0a  mov     rax, [rax+8]
0x1800f2c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2c13  mov     r8, rax; struct ISetupOneSettings **
0x1800f2c16  lea     rdx, aSetupplatform; "SetupPlatform"
0x1800f2c1d  lea     rcx, aWsd; "WSD"
0x1800f2c24  call    ?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z; CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)
0x1800f2c29  mov     esi, eax
0x1800f2c2b  test    eax, eax
0x1800f2c2d  jns     loc_1800F2CB4
0x1800f2c33  call    cs:__imp_GetLastError
0x1800f2c39  mov     edi, eax
0x1800f2c3b  call    cs:__imp_CurrentIP
0x1800f2c41  mov     rbx, rax
0x1800f2c44  mov     r8d, esi
0x1800f2c47  lea     rdx, aFailedToCreate_34; "Failed to create OneSettings infrastruc"...
0x1800f2c4e  mov     ecx, 3000000h; unsigned int
0x1800f2c53  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2c58  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2c5d  mov     [rsp+1050h+var_1008], r12
0x1800f2c62  mov     [rsp+1050h+var_1010], edi
0x1800f2c66  mov     [rsp+1050h+var_1018], rbx
0x1800f2c6b  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2c72  mov     [rsp+1050h+pcbData], rcx
0x1800f2c77  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2c7e  mov     [rsp+1050h+pvData], rcx
0x1800f2c83  mov     dword ptr [rsp+1050h+pdwType], 1645h
0x1800f2c8b  xor     r9d, r9d
0x1800f2c8e  lea     r8, aD_0; "D"
0x1800f2c95  mov     edx, r15d
0x1800f2c98  mov     rcx, rax
0x1800f2c9b  call    cs:__imp_WdsSetupLogMessageW
0x1800f2ca1  mov     rax, [rbp+0F50h+var_FA0]
0x1800f2ca5  xor     edx, edx
0x1800f2ca7  lea     rcx, [rbp+0F50h+var_FA0]
0x1800f2cab  mov     rax, [rax+30h]
0x1800f2caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2cb4  mov     esi, r12d
0x1800f2cb7  lea     r15, [r14+388h]
0x1800f2cbe  cmp     [r15], r12d
0x1800f2cc1  jnz     loc_1800F2E32
0x1800f2cc7  mov     rax, [rbp+0F50h+var_FA0]
0x1800f2ccb  mov     rax, [rax+40h]
0x1800f2ccf  mov     [rbp+0F50h+var_CF0], r12
0x1800f2cd6  lea     rdx, [rbp+0F50h+var_CF0]
0x1800f2cdd  lea     rcx, [rbp+0F50h+var_FA0]
0x1800f2ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2ce6  test    al, al
0x1800f2ce8  jz      loc_1800F2E32
0x1800f2cee  mov     rax, [rbp+0F50h+var_FA0]
0x1800f2cf2  lea     rcx, [rbp+0F50h+var_FA0]
0x1800f2cf6  mov     rax, [rax+18h]
0x1800f2cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2cff  mov     r9, rax
0x1800f2d02  mov     rcx, [rax]
0x1800f2d05  mov     rax, [rcx]
0x1800f2d08  mov     r8, r15
0x1800f2d0b  lea     rdx, aUsemonitoringd; "UseMonitoringDriver"
0x1800f2d12  mov     rcx, r9
0x1800f2d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2d1a  mov     r12d, eax
0x1800f2d1d  test    eax, eax
0x1800f2d1f  js      loc_1800F2DB8
0x1800f2d25  call    cs:__imp_GetLastError
0x1800f2d2b  mov     edi, eax
0x1800f2d2d  call    cs:__imp_CurrentIP
0x1800f2d33  mov     rbx, rax
0x1800f2d36  lea     r9, aTrue_1; "TRUE"
0x1800f2d3d  xor     r12d, r12d
0x1800f2d40  cmp     [r15], r12d
0x1800f2d43  lea     rax, aFalse_0; "FALSE"
0x1800f2d4a  cmovz   r9, rax
0x1800f2d4e  lea     r8, aUsemonitoringd; "UseMonitoringDriver"
0x1800f2d55  lea     rdx, aSetupmonOneset; "SETUPMON: OneSettings value for %s: %s"
0x1800f2d5c  mov     ecx, 4000000h; unsigned int
0x1800f2d61  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2d66  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2d6b  mov     [rsp+1050h+var_1008], r12
0x1800f2d70  mov     [rsp+1050h+var_1010], edi
0x1800f2d74  mov     [rsp+1050h+var_1018], rbx
0x1800f2d79  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2d80  mov     [rsp+1050h+pcbData], rcx
0x1800f2d85  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2d8c  mov     [rsp+1050h+pvData], rcx
0x1800f2d91  mov     dword ptr [rsp+1050h+pdwType], 1656h
0x1800f2d99  xor     r9d, r9d
0x1800f2d9c  lea     r8, aD_0; "D"
0x1800f2da3  mov     edx, 0C8000h
0x1800f2da8  mov     rcx, rax
0x1800f2dab  call    cs:__imp_WdsSetupLogMessageW
0x1800f2db1  lea     esi, [r12+1]
0x1800f2db6  jmp     short loc_1800F2E32
0x1800f2db8  call    cs:__imp_GetLastError
0x1800f2dbe  mov     edi, eax
0x1800f2dc0  call    cs:__imp_CurrentIP
0x1800f2dc6  mov     rbx, rax
0x1800f2dc9  mov     r9d, r12d
0x1800f2dcc  lea     r8, aUsemonitoringd; "UseMonitoringDriver"
0x1800f2dd3  lea     rdx, aSetupmonFailed_0; "SETUPMON: Failed to get OneSettings val"...
0x1800f2dda  mov     ecx, 3000000h; unsigned int
0x1800f2ddf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2de4  xor     r12d, r12d
0x1800f2de7  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2dec  mov     [rsp+1050h+var_1008], r12
0x1800f2df1  mov     [rsp+1050h+var_1010], edi
0x1800f2df5  mov     [rsp+1050h+var_1018], rbx
0x1800f2dfa  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2e01  mov     [rsp+1050h+pcbData], rcx
0x1800f2e06  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2e0d  mov     [rsp+1050h+pvData], rcx
0x1800f2e12  mov     dword ptr [rsp+1050h+pdwType], 165Bh
0x1800f2e1a  xor     r9d, r9d
0x1800f2e1d  lea     r8, aD_0; "D"
0x1800f2e24  mov     edx, 0C8000h
0x1800f2e29  mov     rcx, rax
0x1800f2e2c  call    cs:__imp_WdsSetupLogMessageW
0x1800f2e32  lea     rdx, aSpEnvEnableMon; "SP_ENV_ENABLE_MONITORING_DRIVER"
0x1800f2e39  lea     rcx, [rbp+0F50h+var_9F8]
0x1800f2e40  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800f2e46  nop
0x1800f2e47  xor     edx, edx
0x1800f2e49  mov     rcx, rax
0x1800f2e4c  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800f2e52  mov     ebx, eax
0x1800f2e54  lea     rcx, [rbp+0F50h+var_9F8]
0x1800f2e5b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800f2e61  test    ebx, ebx
0x1800f2e63  jz      short loc_1800F2ECF
0x1800f2e65  cmp     [r15], r12d
0x1800f2e68  jnz     loc_1800F2F7A
0x1800f2e6e  mov     dword ptr [r15], 1
0x1800f2e75  call    cs:__imp_GetLastError
0x1800f2e7b  mov     edi, eax
0x1800f2e7d  call    cs:__imp_CurrentIP
0x1800f2e83  mov     rbx, rax
0x1800f2e86  lea     rdx, aSetupmonUseOfM; "SETUPMON: Use of monitoring driver is e"...
0x1800f2e8d  mov     ecx, 4000000h; unsigned int
0x1800f2e92  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2e97  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2e9c  mov     [rsp+1050h+var_1008], r12
0x1800f2ea1  mov     [rsp+1050h+var_1010], edi
0x1800f2ea5  mov     [rsp+1050h+var_1018], rbx
0x1800f2eaa  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2eb1  mov     [rsp+1050h+pcbData], rcx
0x1800f2eb6  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2ebd  mov     [rsp+1050h+pvData], rcx
0x1800f2ec2  mov     dword ptr [rsp+1050h+pdwType], 1666h
0x1800f2eca  jmp     loc_1800F2F62
0x1800f2ecf  lea     rdx, aSpEnvEnableMon; "SP_ENV_ENABLE_MONITORING_DRIVER"
0x1800f2ed6  lea     rcx, [rbp+0F50h+var_9E0]
0x1800f2edd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800f2ee3  nop
0x1800f2ee4  mov     edx, 1
0x1800f2ee9  mov     rcx, rax
0x1800f2eec  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800f2ef2  mov     ebx, eax
0x1800f2ef4  lea     rcx, [rbp+0F50h+var_9E0]
0x1800f2efb  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800f2f01  test    ebx, ebx
0x1800f2f03  jnz     short loc_1800F2F7F
0x1800f2f05  cmp     [r15], r12d
0x1800f2f08  jz      short loc_1800F2F7A
0x1800f2f0a  mov     [r15], r12d
0x1800f2f0d  call    cs:__imp_GetLastError
0x1800f2f13  mov     edi, eax
0x1800f2f15  call    cs:__imp_CurrentIP
0x1800f2f1b  mov     rbx, rax
0x1800f2f1e  lea     rdx, aSetupmonUseOfM_1; "SETUPMON: Use of monitoring driver is d"...
0x1800f2f25  mov     ecx, 4000000h; unsigned int
0x1800f2f2a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2f2f  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2f34  mov     [rsp+1050h+var_1008], r12
0x1800f2f39  mov     [rsp+1050h+var_1010], edi
0x1800f2f3d  mov     [rsp+1050h+var_1018], rbx
0x1800f2f42  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2f49  mov     [rsp+1050h+pcbData], rcx
0x1800f2f4e  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800f2f55  mov     [rsp+1050h+pvData], rcx
0x1800f2f5a  mov     dword ptr [rsp+1050h+pdwType], 166Fh
0x1800f2f62  xor     r9d, r9d
0x1800f2f65  lea     r8, aD_0; "D"
0x1800f2f6c  mov     edx, 0C8000h
0x1800f2f71  mov     rcx, rax
0x1800f2f74  call    cs:__imp_WdsSetupLogMessageW
0x1800f2f7a  mov     esi, 1
0x1800f2f7f  cmp     [r14+324h], r12d
0x1800f2f86  jnz     short loc_1800F2FFD
0x1800f2f88  mov     [r15], r12d
0x1800f2f8b  mov     esi, 1
0x1800f2f90  call    cs:__imp_GetLastError
0x1800f2f96  mov     edi, eax
0x1800f2f98  call    cs:__imp_CurrentIP
0x1800f2f9e  mov     rbx, rax
0x1800f2fa1  lea     rdx, aSetupmonUseOfM_0; "SETUPMON: Use of monitoring driver is d"...
0x1800f2fa8  mov     ecx, 4000000h; unsigned int
0x1800f2fad  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800f2fb2  mov     dword ptr [rsp+1050h+var_1000], r12d
0x1800f2fb7  mov     [rsp+1050h+var_1008], r12
0x1800f2fbc  mov     [rsp+1050h+var_1010], edi
0x1800f2fc0  mov     [rsp+1050h+var_1018], rbx
0x1800f2fc5  lea     rcx, aCnewsystemQueu_50; "CNewSystem::QueueOperations"
0x1800f2fcc  mov     [rsp+1050h+pcbData], rcx
0x1800f2fd1  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
  ... truncated ...
```
