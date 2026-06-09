# pServicesKeyEnumCallback(HKEY__ *,ushort *,__int64)

- ea: `0x180366310`
- end: `0x180367a10`
- name: `?pServicesKeyEnumCallback@@YAHPEAUHKEY__@@PEAG_J@Z`
- size: `5888`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180057dec`
- `0x18005dd24`
- `0x18012b0a0`
- `0x180360180`
- `0x180366310`
- `0x1804041b0`
- `0x180404554`
- `0x1804048a0`
- `0x18040498c`
- `0x180404a78`
- `0x180404acc`
- `0x180404b5c`
- `0x1804bbf62`
- `0x180509010`

## import_xrefs

- `ADVAPI32!CreateServiceW` at `0x180366e02`
- `ADVAPI32!CreateServiceW` at `0x180366e02`
- `ADVAPI32!RegCloseKey` at `0x180366f41`
- `ADVAPI32!RegCloseKey` at `0x18036708f`
- `ADVAPI32!RegCloseKey` at `0x180366f41`
- `ADVAPI32!RegCloseKey` at `0x18036708f`
- `ADVAPI32!RegSetValueExW` at `0x180367083`
- `ADVAPI32!RegSetValueExW` at `0x1803670b5`
- `ADVAPI32!RegSetValueExW` at `0x180367083`
- `ADVAPI32!RegSetValueExW` at `0x1803670b5`
- `ADVAPI32!RegCreateKeyExW` at `0x180367054`
- `ADVAPI32!RegCreateKeyExW` at `0x180367054`
- `ADVAPI32!RegOpenKeyExW` at `0x180366f18`
- `ADVAPI32!RegOpenKeyExW` at `0x180366f18`
- `ADVAPI32!CloseServiceHandle` at `0x1803671b3`
- `ADVAPI32!CloseServiceHandle` at `0x1803671b3`
- `ADVAPI32!RegDeleteValueW` at `0x180366f32`
- `ADVAPI32!RegDeleteValueW` at `0x180366f57`
- `ADVAPI32!RegDeleteValueW` at `0x180366f32`
- `ADVAPI32!RegDeleteValueW` at `0x180366f57`
- `ADVAPI32!StartServiceW` at `0x18036713c`
- `ADVAPI32!StartServiceW` at `0x18036713c`
- `KERNEL32!GetLastError` at `0x180366344`
- `KERNEL32!GetLastError` at `0x1803663c3`
- `KERNEL32!GetLastError` at `0x1803664b2`
- `KERNEL32!GetLastError` at `0x180366525`
- `KERNEL32!GetLastError` at `0x1803665b0`
- `KERNEL32!GetLastError` at `0x180366634`
- `KERNEL32!GetLastError` at `0x1803666b8`
- `KERNEL32!GetLastError` at `0x18036673c`
- `KERNEL32!GetLastError` at `0x1803667c0`
- `KERNEL32!GetLastError` at `0x180366860`
- `KERNEL32!GetLastError` at `0x180366902`
- `KERNEL32!GetLastError` at `0x180366994`
- `KERNEL32!GetLastError` at `0x1803669ee`
- `KERNEL32!GetLastError` at `0x180366a4c`
- `KERNEL32!GetLastError` at `0x180366aaa`
- `KERNEL32!GetLastError` at `0x180366b08`
- `KERNEL32!GetLastError` at `0x180366b8a`
- `KERNEL32!GetLastError` at `0x180366be6`
- `KERNEL32!GetLastError` at `0x180366c59`
- `KERNEL32!GetLastError` at `0x1803670d7`
- `KERNEL32!GetLastError` at `0x180367146`
- `KERNEL32!GetLastError` at `0x180367157`
- `KERNEL32!GetLastError` at `0x1803671c9`
- `KERNEL32!GetLastError` at `0x1803671d1`
- `KERNEL32!GetLastError` at `0x1803672c3`
- `KERNEL32!GetLastError` at `0x1803672d4`
- `KERNEL32!GetLastError` at `0x180367365`
- `KERNEL32!GetLastError` at `0x180367376`
- `KERNEL32!GetLastError` at `0x180367447`
- `KERNEL32!GetLastError` at `0x180367458`
- `KERNEL32!GetLastError` at `0x1803674f9`
- `KERNEL32!GetLastError` at `0x18036750a`
- `KERNEL32!GetLastError` at `0x1803675e1`
- `KERNEL32!GetLastError` at `0x1803675f2`
- `KERNEL32!GetLastError` at `0x1803676c9`
- `KERNEL32!GetLastError` at `0x1803676da`
- `KERNEL32!GetLastError` at `0x180367774`
- `KERNEL32!GetLastError` at `0x180367785`
- `KERNEL32!GetLastError` at `0x180367840`
- `KERNEL32!GetLastError` at `0x180367851`
- `KERNEL32!GetLastError` at `0x1803678f7`
- `KERNEL32!GetLastError` at `0x180367908`
- `KERNEL32!GetLastError` at `0x180367985`
- `KERNEL32!GetLastError` at `0x180366344`
- `KERNEL32!GetLastError` at `0x1803663c3`
- `KERNEL32!GetLastError` at `0x1803664b2`
- `KERNEL32!GetLastError` at `0x180366525`
- `KERNEL32!GetLastError` at `0x1803665b0`
- `KERNEL32!GetLastError` at `0x180366634`
- `KERNEL32!GetLastError` at `0x1803666b8`
- `KERNEL32!GetLastError` at `0x18036673c`
- `KERNEL32!GetLastError` at `0x1803667c0`
- `KERNEL32!GetLastError` at `0x180366860`
- `KERNEL32!GetLastError` at `0x180366902`
- `KERNEL32!GetLastError` at `0x180366994`
- `KERNEL32!GetLastError` at `0x1803669ee`
- `KERNEL32!GetLastError` at `0x180366a4c`
- `KERNEL32!GetLastError` at `0x180366aaa`
- `KERNEL32!GetLastError` at `0x180366b08`
- `KERNEL32!GetLastError` at `0x180366b8a`
- `KERNEL32!GetLastError` at `0x180366be6`
- `KERNEL32!GetLastError` at `0x180366c59`
- `KERNEL32!GetLastError` at `0x1803670d7`
- `KERNEL32!GetLastError` at `0x180367146`
- `KERNEL32!GetLastError` at `0x180367157`
- `KERNEL32!GetLastError` at `0x1803671c9`
- `KERNEL32!GetLastError` at `0x1803671d1`
- `KERNEL32!GetLastError` at `0x1803672c3`
- `KERNEL32!GetLastError` at `0x1803672d4`
- `KERNEL32!GetLastError` at `0x180367365`
- `KERNEL32!GetLastError` at `0x180367376`
- `KERNEL32!GetLastError` at `0x180367447`
- `KERNEL32!GetLastError` at `0x180367458`
- `KERNEL32!GetLastError` at `0x1803674f9`
- `KERNEL32!GetLastError` at `0x18036750a`
- `KERNEL32!GetLastError` at `0x1803675e1`
- `KERNEL32!GetLastError` at `0x1803675f2`
- `KERNEL32!GetLastError` at `0x1803676c9`
- `KERNEL32!GetLastError` at `0x1803676da`
- `KERNEL32!GetLastError` at `0x180367774`
- `KERNEL32!GetLastError` at `0x180367785`
- `KERNEL32!GetLastError` at `0x180367840`
- `KERNEL32!GetLastError` at `0x180367851`
- `KERNEL32!GetLastError` at `0x1803678f7`
- `KERNEL32!GetLastError` at `0x180367908`
- `KERNEL32!GetLastError` at `0x180367985`
- `KERNEL32!SetLastError` at `0x180366e92`
- `KERNEL32!SetLastError` at `0x180366f61`
- `KERNEL32!SetLastError` at `0x180366fae`
- `KERNEL32!SetLastError` at `0x1803670bf`
- `KERNEL32!SetLastError` at `0x180366e92`
- `KERNEL32!SetLastError` at `0x180366f61`
- `KERNEL32!SetLastError` at `0x180366fae`
- `KERNEL32!SetLastError` at `0x1803670bf`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180367252`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180367252`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18036653a`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803665c5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366649`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803666cd`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366751`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803667d5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366b1d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366d15`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366d6d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180367587`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18036653a`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803665c5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366649`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803666cd`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366751`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1803667d5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366b1d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366d15`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180366d6d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180367587`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180366e35`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180366e35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366cc9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366cf1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366e4d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366f6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18036726b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180367574`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180367653`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803677e6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366cc9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366cf1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366e4d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180366f6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18036726b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180367574`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180367653`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803677e6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366420`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18036643a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366445`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366450`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18036645b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366466`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366471`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366420`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18036643a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366445`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366450`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18036645b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366466`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180366471`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366550`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803665d4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366658`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803666dc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366760`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803667e4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366b2c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366d24`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366d47`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366d7e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366d9d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366e1c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366e60`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366e76`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366ede`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366f7c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366f92`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180366ffc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367235`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18036727e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367295`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803672e0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367336`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367382`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803673d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367406`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367464`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803674c9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180367516`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18036759a`

## string_xrefs

- `0x180366ebc`: `ImagePath`
- `0x180366f24`: `ImagePath`
- `0x180366f49`: `ImagePath`
- `0x1803675c3`: `ImagePath`
- `0x180366384`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180366403`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803664f2`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180366355`: `Service data is NULL, cannot add pending services`
- `0x180366378`: `pServicesKeyEnumCallback`
- `0x1803663f7`: `pServicesKeyEnumCallback`
- `0x1803664e6`: `pServicesKeyEnumCallback`
- `0x180366777`: `Binary path (ORG): %s`
- `0x1803666f3`: `Binary path (SCM): %s`
- `0x1803664c3`: `Attempting to add service with data:`
- `0x1803663d4`: `Service data is incomplete, cannot add pending services`
- `0x180366abf`: `Service error control: %d`
- `0x180366a61`: `Service start type: %d`
- `0x180366a03`: `Service type: %d`
- `0x1803667fb`: `Binary path (WIN): %s`
- `0x180367160`: `Could not start service. Error: 0x%08X`
- `0x1803670e8`: `Starting service`
- `0x180366e2e`: `SYSTEM\CurrentControlSet\Services\`
- `0x180367996`: `Not enough information found to add this service`
- `0x180366c7c`: `Start service: %s`
- `0x180366c10`: `Delete image path: %s`
- `0x180367613`: `Cannot set ImagePath for %s, error: 0x%08X`
- `0x18036724b`: `%s\Services\%s`
- `0x1803671f8`: `Could not create the service, error: 0x%08X`
- `0x180367929`: `Cannot set DependOnService for %s, error: 0x%08X`
- `0x1803678d5`: `DependOnService`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall pServicesKeyEnumCallback(HKEY a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned int v4; // esi
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // ebx
  __int64 v16; // rdi
  const wchar_t *v17; // rsi
  UnBCL::String *v18; // rax
  const wchar_t *CString; // rax
  struct tagLOG_PARTIAL_MSG *v20; // rax
  DWORD v21; // ebx
  __int64 v22; // rdi
  UnBCL::String *v23; // rax
  const wchar_t *v24; // rax
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // ebx
  __int64 v27; // rdi
  UnBCL::String *v28; // rax
  const wchar_t *v29; // rax
  struct tagLOG_PARTIAL_MSG *v30; // rax
  DWORD v31; // ebx
  __int64 v32; // rdi
  UnBCL::String *v33; // rax
  const wchar_t *v34; // rax
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // ebx
  __int64 v37; // rdi
  UnBCL::String *v38; // rax
  const wchar_t *v39; // rax
  struct tagLOG_PARTIAL_MSG *v40; // rax
  DWORD v41; // ebx
  __int64 v42; // rdi
  UnBCL::String *v43; // rax
  const wchar_t *v44; // rax
  struct tagLOG_PARTIAL_MSG *v45; // rax
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  CHAR *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rsi
  DWORD v52; // edi
  __int64 v53; // rbx
  const char *v54; // rax
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  struct tagLOG_PARTIAL_MSG *v61; // rax
  DWORD v62; // edi
  __int64 v63; // rbx
  struct tagLOG_PARTIAL_MSG *v64; // rax
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  DWORD v68; // ebx
  __int64 v69; // rdi
  UnBCL::String *v70; // rax
  struct tagLOG_PARTIAL_MSG *v71; // rax
  DWORD v72; // edi
  __int64 v73; // rbx
  struct tagLOG_PARTIAL_MSG *v74; // rax
  DWORD v75; // edi
  __int64 v76; // rbx
  const unsigned __int16 *v77; // rsi
  const unsigned __int16 *v78; // r8
  struct tagLOG_PARTIAL_MSG *v79; // rax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  LPCWSTR v83; // rdi
  UnBCL::String *v84; // rax
  UnBCL::String *v85; // rax
  DWORD dwErrorControl; // esi
  UnBCL::String *v87; // rax
  UnBCL::String *v88; // rax
  const WCHAR *v89; // rax
  UnBCL::String *v90; // rax
  const unsigned __int16 *v91; // rax
  struct UnBCL::String *v92; // rax
  __int64 v93; // rdi
  UnBCL::String *v94; // rax
  const unsigned __int16 *v95; // rsi
  UnBCL::String *v96; // rax
  const unsigned __int16 *v97; // rdx
  __int64 v98; // rax
  UnBCL::String *v99; // rax
  const WCHAR *v100; // rax
  LSTATUS v101; // esi
  UnBCL::String *v102; // rax
  const unsigned __int16 *v103; // rsi
  UnBCL::String *v104; // rax
  const unsigned __int16 *v105; // rdx
  UnBCL::String *v106; // rax
  const WCHAR *v107; // rax
  LSTATUS Key; // ebx
  DWORD v109; // edi
  __int64 v110; // rbx
  struct tagLOG_PARTIAL_MSG *v111; // rax
  SC_HANDLE v112; // rsi
  DWORD v113; // edi
  __int64 v114; // rbx
  DWORD v115; // eax
  struct tagLOG_PARTIAL_MSG *v116; // rax
  DWORD v117; // ebx
  DWORD v118; // esi
  __int64 v119; // rdi
  unsigned int v120; // eax
  struct tagLOG_PARTIAL_MSG *v121; // rax
  UnBCL::String *v122; // rax
  const unsigned __int16 *v123; // rax
  struct UnBCL::String *v124; // rax
  UnBCL::String *v125; // rax
  const unsigned __int16 *v126; // rbx
  UnBCL::String *v127; // rax
  const unsigned __int16 *v128; // rax
  DWORD v129; // esi
  __int64 v130; // rdi
  DWORD v131; // ebx
  UnBCL::String *v132; // rax
  const char *v133; // rax
  struct tagLOG_PARTIAL_MSG *v134; // rax
  UnBCL::String *v135; // rax
  const unsigned __int16 *v136; // rax
  DWORD v137; // esi
  __int64 v138; // rdi
  DWORD v139; // ebx
  UnBCL::String *v140; // rax
  const char *v141; // rax
  struct tagLOG_PARTIAL_MSG *v142; // rax
  UnBCL::String *v143; // rax
  const unsigned __int16 *v144; // rax
  const WCHAR *v145; // rsi
  int Dword; // ebx
  DWORD v147; // edi
  UnBCL::String *v148; // rax
  const unsigned __int16 *v149; // rax
  __int64 v150; // r9
  LPCWSTR v151; // rdi
  DWORD v152; // esi
  __int64 v153; // rdi
  DWORD v154; // ebx
  UnBCL::String *v155; // rax
  const char *v156; // rax
  struct tagLOG_PARTIAL_MSG *v157; // rax
  DWORD v158; // ebx
  UnBCL::String *v159; // rax
  const unsigned __int16 *v160; // rax
  DWORD v161; // esi
  __int64 v162; // rdi
  DWORD v163; // ebx
  UnBCL::String *v164; // rax
  const char *v165; // rax
  struct tagLOG_PARTIAL_MSG *v166; // rax
  __int64 v167; // rax
  void *p_lpMachineName; // rcx
  UnBCL::String *v169; // rax
  const unsigned __int16 *v170; // rbx
  UnBCL::String *v171; // rax
  const unsigned __int16 *v172; // rax
  DWORD v173; // esi
  __int64 v174; // rdi
  DWORD v175; // ebx
  UnBCL::String *v176; // rax
  const char *v177; // rax
  struct tagLOG_PARTIAL_MSG *v178; // rax
  UnBCL::String *v179; // rax
  UnBCL::String *v180; // rax
  const unsigned __int16 *v181; // rbx
  UnBCL::String *v182; // rax
  const unsigned __int16 *v183; // rax
  DWORD v184; // esi
  __int64 v185; // rdi
  DWORD v186; // ebx
  UnBCL::String *v187; // rax
  const char *v188; // rax
  struct tagLOG_PARTIAL_MSG *v189; // rax
  UnBCL::String *v190; // rax
  const unsigned __int16 *v191; // rax
  DWORD v192; // esi
  __int64 v193; // rdi
  DWORD v194; // ebx
  UnBCL::String *v195; // rax
  const char *v196; // rax
  struct tagLOG_PARTIAL_MSG *v197; // rax
  UnBCL::String *v198; // rax
  const unsigned __int16 *v199; // rbx
  UnBCL::String *v200; // rax
  const unsigned __int16 *v201; // rax
  DWORD v202; // esi
  __int64 v203; // rdi
  DWORD v204; // ebx
  UnBCL::String *v205; // rax
  const char *v206; // rax
  struct tagLOG_PARTIAL_MSG *v207; // rax
  LPCWSTR v208; // rbx
  UnBCL::String *v209; // rax
  const unsigned __int16 *v210; // rax
  DWORD v211; // esi
  __int64 v212; // rdi
  DWORD v213; // ebx
  UnBCL::String *v214; // rax
  const char *v215; // rax
  struct tagLOG_PARTIAL_MSG *v216; // rax
  DWORD v217; // edi
  __int64 v218; // rbx
  struct tagLOG_PARTIAL_MSG *v219; // rax
  LPCWSTR lpDisplayName[2]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpBinaryPathName; // [rsp+80h] [rbp-80h] BYREF
  void **v222; // [rsp+88h] [rbp-78h] BYREF
  __int64 v223; // [rsp+90h] [rbp-70h]
  SERVICE_INFO v224; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v225[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v226[16]; // [rsp+100h] [rbp+0h] BYREF
  DWORD dwServiceType; // [rsp+110h] [rbp+10h]
  DWORD dwStartType; // [rsp+114h] [rbp+14h]
  DWORD v229; // [rsp+118h] [rbp+18h]
  _BYTE v230[16]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v231; // [rsp+130h] [rbp+30h]
  int v232; // [rsp+134h] [rbp+34h]
  int v233; // [rsp+138h] [rbp+38h]
  __int64 v234; // [rsp+140h] [rbp+40h]
  LPCWSTR lpLoadOrderGroup; // [rsp+1A0h] [rbp+A0h] BYREF
  LPCWSTR lpDependencies; // [rsp+1A8h] [rbp+A8h] BYREF

  lpLoadOrderGroup = (LPCWSTR)a3;
  v234 = -2;
  v4 = 0;
  if ( !a3 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x2000000u, "Service data is NULL, cannot add pending services");
    WdsSetupLogMessageW(
      v7,
      819200,
      L"D",
      0,
      954,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v6,
      LastError,
      0,
      0);
    return 0;
  }
  if ( !*(_QWORD *)(a3 + 24) && !*(_QWORD *)(a3 + 16) )
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(0x2000000u, "Service data is incomplete, cannot add pending services");
    WdsSetupLogMessageW(
      v11,
      819200,
      L"D",
      0,
      959,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v10,
      v9,
      0,
      0);
    return 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v224);
  v224.lpComment = (LPSTR)&UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable';
  v224.lpLocale = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v224.dwDisplayHint);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v224.lpMachineName);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v224.ServiceSpecificInfo);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v225);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v226);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v230);
  memset_0(&v224, 0, 0xA0u);
  dwServiceType = -1;
  dwStartType = -1;
  v229 = -1;
  if ( !(unsigned int)RegEnumValues(a1, 0, pServicesValueEnumCallback, &v224) )
  {
    LODWORD(lpLoadOrderGroup) = 0;
    goto LABEL_123;
  }
  v12 = GetLastError();
  v13 = CurrentIP();
  v14 = ConstructPartialMsgW(0x4000000u, "Attempting to add service with data:");
  WdsSetupLogMessageW(
    v14,
    819200,
    L"D",
    0,
    979,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v13,
    v12,
    0,
    0);
  v15 = GetLastError();
  v16 = CurrentIP();
  v17 = L"<<NULL>>";
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v224) )
  {
    v18 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
    CString = UnBCL::String::get_CString(v18);
  }
  else
  {
    CString = L"<<NULL>>";
  }
  v20 = ConstructPartialMsgW(0x4000000u, "Name: %s", (const char *)CString);
  WdsSetupLogMessageW(
    v20,
    819200,
    L"D",
    0,
    980,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v16,
    v15,
    0,
    0);
  v21 = GetLastError();
  v22 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v226) )
  {
    v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226);
    v24 = UnBCL::String::get_CString(v23);
  }
  else
  {
    v24 = L"<<NULL>>";
  }
  v25 = ConstructPartialMsgW(0x4000000u, "Display name: %s", (const char *)v24);
  WdsSetupLogMessageW(
    v25,
    819200,
    L"D",
    0,
    981,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v22,
    v21,
    0,
    0);
  v26 = GetLastError();
  v27 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v225) )
  {
    v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v225);
    v29 = UnBCL::String::get_CString(v28);
  }
  else
  {
    v29 = L"<<NULL>>";
  }
  v30 = ConstructPartialMsgW(0x4000000u, "Start name: %s", (const char *)v29);
  WdsSetupLogMessageW(
    v30,
    819200,
    L"D",
    0,
    982,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v27,
    v26,
    0,
    0);
  v31 = GetLastError();
  v32 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v224.dwDisplayHint) )
  {
    v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224.dwDisplayHint);
    v34 = UnBCL::String::get_CString(v33);
  }
  else
  {
    v34 = L"<<NULL>>";
  }
  v35 = ConstructPartialMsgW(0x4000000u, "Binary path (SCM): %s", (const char *)v34);
  WdsSetupLogMessageW(
    v35,
    819200,
    L"D",
    0,
    983,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v32,
    v31,
    0,
    0);
  v36 = GetLastError();
  v37 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v224.lpMachineName) )
  {
    v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224.lpMachineName);
    v39 = UnBCL::String::get_CString(v38);
  }
  else
  {
    v39 = L"<<NULL>>";
  }
  v40 = ConstructPartialMsgW(0x4000000u, "Binary path (ORG): %s", (const char *)v39);
  WdsSetupLogMessageW(
    v40,
    819200,
    L"D",
    0,
    984,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v37,
    v36,
    0,
    0);
  v41 = GetLastError();
  v42 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v224.ServiceSpecificInfo) )
  {
    v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224.ServiceSpecificInfo);
    v44 = UnBCL::String::get_CString(v43);
  }
  else
  {
    v44 = L"<<NULL>>";
  }
  v45 = ConstructPartialMsgW(0x4000000u, "Binary path (WIN): %s", (const char *)v44);
  WdsSetupLogMessageW(
    v45,
    819200,
    L"D",
    0,
    985,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v42,
    v41,
    0,
    0);
  if ( v224.lpLocale )
  {
    lpDependencies = UnBCL::MultiSz::get_Buffer((UnBCL::MultiSz *)v224.lpLocale);
    v46 = GetLastError();
    v47 = CurrentIP();
    v48 = ConstructPartialMsgW(0x4000000u, "Dependencies:");
    WdsSetupLogMessageW(
      v48,
      819200,
      L"D",
      0,
      991,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v47,
      v46,
      0,
      0);
    v49 = &v224.lpLocale[*(int *)(*(_QWORD *)v224.lpLocale + 8LL)];
    v50 = (**(__int64 (__fastcall ***)(CHAR *))v49)(v49);
    UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>(
      &v222,
      v50);
    if ( v223 )
    {
      v51 = v223;
      while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51) )
      {
        v52 = GetLastError();
        v53 = CurrentIP();
        v54 = (const char *)(**(__int64 (__fastcall ***)(__int64))v51)(v51);
        v55 = ConstructPartialMsgW(0x4000000u, "    %s", v54);
        WdsSetupLogMessageW(
          v55,
          819200,
          L"D",
          0,
          998,
          L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
          L"pServicesKeyEnumCallback",
          v53,
          v52,
          0,
          0);
      }
      v17 = L"<<NULL>>";
    }
    v222 = &UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v222);
  }
  else
  {
    lpDependencies = 0;
    v56 = GetLastError();
    v57 = CurrentIP();
    v58 = ConstructPartialMsgW(0x4000000u, "Dependencies: <<None>>");
    WdsSetupLogMessageW(
      v58,
      819200,
      L"D",
      0,
      1004,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v57,
      v56,
      0,
      0);
  }
  v59 = GetLastError();
  v60 = CurrentIP();
  v61 = ConstructPartialMsgW(0x4000000u, "Service type: %d", dwServiceType);
  WdsSetupLogMessageW(
    v61,
    819200,
    L"D",
    0,
    1006,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v60,
    v59,
    0,
    0);
  v62 = GetLastError();
  v63 = CurrentIP();
  v64 = ConstructPartialMsgW(0x4000000u, "Service start type: %d", dwStartType);
  WdsSetupLogMessageW(
    v64,
    819200,
    L"D",
    0,
    1007,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v63,
    v62,
    0,
    0);
  v65 = GetLastError();
  v66 = CurrentIP();
  v67 = ConstructPartialMsgW(0x4000000u, "Service error control: %d", v229);
  WdsSetupLogMessageW(
    v67,
    819200,
    L"D",
    0,
    1008,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v66,
    v65,
    0,
    0);
  v68 = GetLastError();
  v69 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v230) )
  {
    v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v230);
    v17 = UnBCL::String::get_CString(v70);
  }
  v71 = ConstructPartialMsgW(0x4000000u, "Load order group: %s", (const char *)v17);
  WdsSetupLogMessageW(
    v71,
    819200,
    L"D",
    0,
    1009,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v69,
    v68,
    0,
    0);
  v72 = GetLastError();
  v73 = CurrentIP();
  v74 = ConstructPartialMsgW(0x4000000u, "Tag ID: %d", v231);
  WdsSetupLogMessageW(
    v74,
    819200,
    L"D",
    0,
    1010,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v73,
    v72,
    0,
    0);
  v75 = GetLastError();
  v76 = CurrentIP();
  v77 = L"Yes";
  v78 = L"Yes";
  if ( !v232 )
    v78 = L"No";
  v79 = ConstructPartialMsgW(0x4000000u, "Delete image path: %s", (const char *)v78);
  WdsSetupLogMessageW(
    v79,
    819200,
    L"D",
    0,
    1011,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v76,
    v75,
    0,
    0);
  v80 = GetLastError();
  v81 = CurrentIP();
  if ( !v233 )
    v77 = L"No";
  v82 = ConstructPartialMsgW(0x4000000u, "Start service: %s", (const char *)v77);
  WdsSetupLogMessageW(
    v82,
    819200,
    L"D",
    0,
    1012,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"pServicesKeyEnumCallback",
    v81,
    v80,
    0,
    0);
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v224)
    || dwServiceType == -1
    || dwStartType == -1
    || !UnBCL::SmartPtr<UnBCL::String>::get_P(&v224.dwDisplayHint) )
  {
    v217 = GetLastError();
    v218 = CurrentIP();
    v219 = ConstructPartialMsgW(0x2000000u, "Not enough information found to add this service");
    WdsSetupLogMessageW(
      v219,
      819200,
      L"D",
      0,
      1019,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v218,
      v217,
      0,
      0);
LABEL_121:
    v4 = 1;
    goto LABEL_123;
  }
  v83 = lpLoadOrderGroup;
  if ( *((_QWORD *)lpLoadOrderGroup + 3) )
  {
    if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v230) )
    {
      v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v230);
      lpLoadOrderGroup = UnBCL::String::get_CString(v84);
    }
    else
    {
      lpLoadOrderGroup = 0;
    }
    v85 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224.dwDisplayHint);
    lpBinaryPathName = UnBCL::String::get_CString(v85);
    dwErrorControl = 1;
    if ( v229 != -1 )
      dwErrorControl = v229;
    if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v226) )
    {
      v87 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226);
      lpDisplayName[0] = UnBCL::String::get_CString(v87);
    }
    else
    {
      lpDisplayName[0] = 0;
    }
    v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
    v89 = UnBCL::String::get_CString(v88);
    lpDisplayName[0] = (LPCWSTR)CreateServiceW(
                                  *((SC_HANDLE *)v83 + 3),
                                  v89,
                                  lpDisplayName[0],
                                  0xF01FFu,
                                  dwServiceType,
                                  dwStartType,
                                  dwErrorControl,
                                  lpBinaryPathName,
                                  lpLoadOrderGroup,
                                  0,
                                  lpDependencies,
                                  0,
                                  0);
    if ( lpDisplayName[0] )
    {
      v90 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
      v91 = UnBCL::String::get_CString(v90);
      v92 = UnBCL::String::Concat(L"SYSTEM\\CurrentControlSet\\Services\\", v91);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v222, v92);
      v93 = -1;
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&v224.lpMachineName) )
      {
        v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224.lpMachineName);
        v95 = UnBCL::String::get_CString(v94);
        v96 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v222);
        v97 = UnBCL::String::get_CString(v96);
        if ( v95 )
        {
          v98 = -1;
          do
            ++v98;
          while ( v95[v98] );
          RegSetBinEx(-2147483646, v97, L"ImagePath", 2, v95, 2 * v98 + 2);
        }
        else
        {
          SetLastError(0x57u);
        }
      }
      if ( v232 )
      {
        v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v222);
        v100 = UnBCL::String::get_CString(v99);
        if ( v100 )
        {
          lpLoadOrderGroup = 0;
          v101 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v100, 0, 0x20006u, (PHKEY)&lpLoadOrderGroup);
          if ( !v101 )
          {
            v101 = RegDeleteValueW((HKEY)lpLoadOrderGroup, L"ImagePath");
            RegCloseKey((HKEY)lpLoadOrderGroup);
          }
        }
        else
        {
          v101 = RegDeleteValueW(HKEY_LOCAL_MACHINE, L"ImagePath");
        }
        SetLastError(v101);
      }
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v225) )
      {
        v102 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v225);
        v103 = UnBCL::String::get_CString(v102);
        v104 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v222);
        v105 = UnBCL::String::get_CString(v104);
        if ( v103 )
        {
          do
            ++v93;
          while ( v103[v93] );
          RegSetBinEx(-2147483646, v105, L"ObjectName", 1, v103, 2 * v93 + 2);
        }
        else
        {
          SetLastError(0x57u);
        }
      }
      if ( v231 )
      {
        LODWORD(lpLoadOrderGroup) = v231;
        v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v222);
        v107 = UnBCL::String::get_CString(v106);
        if ( v107 )
        {
          lpBinaryPathName = 0;
          LODWORD(lpDependencies) = 0;
          Key = RegCreateKeyExW(
                  HKEY_LOCAL_MACHINE,
                  v107,
                  0,
                  (LPWSTR)&Class,
                  0,
                  0x20006u,
                  0,
                  (PHKEY)&lpBinaryPathName,
                  (LPDWORD)&lpDependencies);
          if ( !Key )
          {
            Key = RegSetValueExW((HKEY)lpBinaryPathName, L"Tag", 0, 4u, (const BYTE *)&lpLoadOrderGroup, 4u);
            RegCloseKey((HKEY)lpBinaryPathName);
          }
        }
        else
        {
          Key = RegSetValueExW(HKEY_LOCAL_MACHINE, L"Tag", 0, 4u, (const BYTE *)&lpLoadOrderGroup, 4u);
        }
        SetLastError(Key);
      }
      if ( v233 && dwStartType )
      {
        v109 = GetLastError();
        v110 = CurrentIP();
        v111 = ConstructPartialMsgW(0x4000000u, "Starting service");
        WdsSetupLogMessageW(
          v111,
          819200,
          L"D",
          0,
          1065,
          L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
          L"pServicesKeyEnumCallback",
          v110,
          v109,
          0,
          0);
        v112 = (SC_HANDLE)lpDisplayName[0];
        if ( !StartServiceW((SC_HANDLE)lpDisplayName[0], 0, 0) )
        {
          v113 = GetLastError();
          v114 = CurrentIP();
          v115 = GetLastError();
          v116 = ConstructPartialMsgW(0x3000000u, "Could not start service. Error: 0x%08X", v115);
          WdsSetupLogMessageW(
            v116,
            819200,
            L"D",
            0,
            1068,
            L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
            L"pServicesKeyEnumCallback",
            v114,
            v113,
            0,
            0);
        }
      }
      else
      {
        v112 = (SC_HANDLE)lpDisplayName[0];
      }
      CloseServiceHandle(v112);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v222);
    }
    else
    {
      v117 = GetLastError();
      v118 = GetLastError();
      v119 = CurrentIP();
      v120 = 50331648;
      if ( v117 != 1073 )
        v120 = 0x2000000;
      v121 = ConstructPartialMsgW(v120, "Could not create the service, error: 0x%08X", v117);
      WdsSetupLogMessageW(
        v121,
        819200,
        L"D",
        0,
        1081,
        L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
        L"pServicesKeyEnumCallback",
        v119,
        v118,
        0,
        0);
    }
    goto LABEL_121;
  }
  v122 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
  v123 = UnBCL::String::get_CString(v122);
  v124 = UnBCL::String::Format(L"%s\\Services\\%s", *((_QWORD *)v83 + 2), v123);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(lpDisplayName, v124);
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v226)
    || (v125 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226),
        v126 = UnBCL::String::get_CString(v125),
        v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName),
        v128 = UnBCL::String::get_CString(v127),
        (unsigned int)RegSetString(*(_QWORD *)v83, v128, L"DisplayName", v126)) )
  {
    v135 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
    v136 = UnBCL::String::get_CString(v135);
    if ( (unsigned int)RegSetDword(*(_QWORD *)v83, v136, L"Type", dwServiceType) )
    {
      v143 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
      v144 = UnBCL::String::get_CString(v143);
      v145 = L"Start.Backup";
      Dword = RegGetDword(*(_QWORD *)v83, v144, L"Start.Backup");
      v147 = dwStartType;
      v148 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
      v149 = UnBCL::String::get_CString(v148);
      if ( Dword != -1 )
        v145 = L"Start";
      v150 = v147;
      v151 = lpLoadOrderGroup;
      if ( (unsigned int)RegSetDword(*(_QWORD *)lpLoadOrderGroup, v149, v145, v150) )
      {
        v4 = 1;
        v158 = 1;
        if ( v229 != -1 )
          v158 = v229;
        v159 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
        v160 = UnBCL::String::get_CString(v159);
        if ( (unsigned int)RegSetDword(*(_QWORD *)v151, v160, L"ErrorControl", v158) )
        {
          if ( v232 || !UnBCL::SmartPtr<UnBCL::String>::get_P(&v224.dwDisplayHint) )
            goto LABEL_126;
          v167 = UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v224.lpMachineName);
          p_lpMachineName = &v224.lpMachineName;
          if ( !v167 )
            p_lpMachineName = &v224.dwDisplayHint;
          v169 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(p_lpMachineName);
          v170 = UnBCL::String::get_CString(v169);
          v171 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
          v172 = UnBCL::String::get_CString(v171);
          if ( (unsigned int)RegSetExpand(*(_QWORD *)v151, v172, L"ImagePath", v170) )
          {
LABEL_126:
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v230)
              && (v179 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v230),
                  *UnBCL::String::get_CString(v179))
              && (v180 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v230),
                  v181 = UnBCL::String::get_CString(v180),
                  v182 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName),
                  v183 = UnBCL::String::get_CString(v182),
                  !(unsigned int)RegSetString(*(_QWORD *)v151, v183, L"Group", v181)) )
            {
              LODWORD(lpLoadOrderGroup) = 0;
              v184 = GetLastError();
              v185 = CurrentIP();
              v186 = GetLastError();
              v187 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
              v188 = (const char *)UnBCL::String::get_CString(v187);
              v189 = ConstructPartialMsgW(0x2000000u, "Cannot set Group for %s, error: 0x%08X", v188, v186);
              WdsSetupLogMessageW(
                v189,
                819200,
                L"D",
                0,
                1157,
                L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                L"pServicesKeyEnumCallback",
                v185,
                v184,
                0,
                0);
            }
            else if ( !v231
                   || (v190 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName),
                       v191 = UnBCL::String::get_CString(v190),
                       (unsigned int)RegSetDword(*(_QWORD *)v151, v191, L"Tag", v231)) )
            {
              if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v225)
                || (v198 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v225),
                    v199 = UnBCL::String::get_CString(v198),
                    v200 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName),
                    v201 = UnBCL::String::get_CString(v200),
                    (unsigned int)RegSetString(*(_QWORD *)v151, v201, L"ObjectName", v199)) )
              {
                v208 = lpDependencies;
                if ( !lpDependencies )
                  goto LABEL_119;
                v209 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpDisplayName);
                v210 = UnBCL::String::get_CString(v209);
                if ( (unsigned int)RegSetMultiSz(*(_QWORD *)v151, v210, L"DependOnService", v208) )
                  goto LABEL_119;
                LODWORD(lpLoadOrderGroup) = 0;
                v211 = GetLastError();
                v212 = CurrentIP();
                v213 = GetLastError();
                v214 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
                v215 = (const char *)UnBCL::String::get_CString(v214);
                v216 = ConstructPartialMsgW(0x2000000u, "Cannot set DependOnService for %s, error: 0x%08X", v215, v213);
                WdsSetupLogMessageW(
                  v216,
                  819200,
                  L"D",
                  0,
                  1184,
                  L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                  L"pServicesKeyEnumCallback",
                  v212,
                  v211,
                  0,
                  0);
              }
              else
              {
                LODWORD(lpLoadOrderGroup) = 0;
                v202 = GetLastError();
                v203 = CurrentIP();
                v204 = GetLastError();
                v205 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
                v206 = (const char *)UnBCL::String::get_CString(v205);
                v207 = ConstructPartialMsgW(0x2000000u, "Cannot set ObjectName for %s, error: 0x%08X", v206, v204);
                WdsSetupLogMessageW(
                  v207,
                  819200,
                  L"D",
                  0,
                  1175,
                  L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                  L"pServicesKeyEnumCallback",
                  v203,
                  v202,
                  0,
                  0);
              }
            }
            else
            {
              LODWORD(lpLoadOrderGroup) = 0;
              v192 = GetLastError();
              v193 = CurrentIP();
              v194 = GetLastError();
              v195 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
              v196 = (const char *)UnBCL::String::get_CString(v195);
              v197 = ConstructPartialMsgW(0x2000000u, "Cannot set Tag for %s, error: 0x%08X", v196, v194);
              WdsSetupLogMessageW(
                v197,
                819200,
                L"D",
                0,
                1166,
                L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                L"pServicesKeyEnumCallback",
                v193,
                v192,
                0,
                0);
            }
          }
          else
          {
            LODWORD(lpLoadOrderGroup) = 0;
            v173 = GetLastError();
            v174 = CurrentIP();
            v175 = GetLastError();
            v176 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
            v177 = (const char *)UnBCL::String::get_CString(v176);
            v178 = ConstructPartialMsgW(0x2000000u, "Cannot set ImagePath for %s, error: 0x%08X", v177, v175);
            WdsSetupLogMessageW(
              v178,
              819200,
              L"D",
              0,
              1148,
              L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
              L"pServicesKeyEnumCallback",
              v174,
              v173,
              0,
              0);
          }
        }
        else
        {
          LODWORD(lpLoadOrderGroup) = 0;
          v161 = GetLastError();
          v162 = CurrentIP();
          v163 = GetLastError();
          v164 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
          v165 = (const char *)UnBCL::String::get_CString(v164);
          v166 = ConstructPartialMsgW(0x2000000u, "Cannot set ErrorControl for %s, error: 0x%08X", v165, v163);
          WdsSetupLogMessageW(
            v166,
            819200,
            L"D",
            0,
            1133,
            L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
            L"pServicesKeyEnumCallback",
            v162,
            v161,
            0,
            0);
        }
      }
      else
      {
        LODWORD(lpLoadOrderGroup) = 0;
        v152 = GetLastError();
        v153 = CurrentIP();
        v154 = GetLastError();
        v155 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
        v156 = (const char *)UnBCL::String::get_CString(v155);
        v157 = ConstructPartialMsgW(0x2000000u, "Cannot set Start for %s, error: 0x%08X", v156, v154);
        WdsSetupLogMessageW(
          v157,
          819200,
          L"D",
          0,
          1123,
          L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
          L"pServicesKeyEnumCallback",
          v153,
          v152,
          0,
          0);
      }
    }
    else
    {
      LODWORD(lpLoadOrderGroup) = 0;
      v137 = GetLastError();
      v138 = CurrentIP();
      v139 = GetLastError();
      v140 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
      v141 = (const char *)UnBCL::String::get_CString(v140);
      v142 = ConstructPartialMsgW(0x2000000u, "Cannot set Type for %s, error: 0x%08X", v141, v139);
      WdsSetupLogMessageW(
        v142,
        819200,
        L"D",
        0,
        1109,
        L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
        L"pServicesKeyEnumCallback",
        v138,
        v137,
        0,
        0);
    }
  }
  else
  {
    LODWORD(lpLoadOrderGroup) = 0;
    v129 = GetLastError();
    v130 = CurrentIP();
    v131 = GetLastError();
    v132 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v224);
    v133 = (const char *)UnBCL::String::get_CString(v132);
    v134 = ConstructPartialMsgW(0x2000000u, "Cannot set DisplayName for %s, error: 0x%08X", v133, v131);
    WdsSetupLogMessageW(
      v134,
      819200,
      L"D",
      0,
      1100,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"pServicesKeyEnumCallback",
      v130,
      v129,
      0,
      0);
  }
  v4 = (unsigned int)lpLoadOrderGroup;
LABEL_119:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(lpDisplayName);
LABEL_123:
  SERVICE_INFO::~SERVICE_INFO(&v224);
  return v4;
}

```

## disassembly

```asm
0x180366310  mov     rax, rsp
0x180366313  mov     [rax+18h], r8
0x180366317  push    rbp
0x180366318  push    rsi
0x180366319  push    rdi
0x18036631a  push    r12
0x18036631c  push    r13
0x18036631e  push    r14
0x180366320  push    r15
0x180366322  lea     rbp, [rsp-50h]
0x180366327  sub     rsp, 150h
0x18036632e  mov     [rbp+80h+var_40], 0FFFFFFFFFFFFFFFEh
0x180366336  mov     [rax+8], rbx
0x18036633a  mov     rbx, rcx
0x18036633d  xor     esi, esi
0x18036633f  test    r8, r8
0x180366342  jnz     short loc_1803663B7
0x180366344  call    cs:__imp_GetLastError
0x18036634a  mov     edi, eax
0x18036634c  call    cs:__imp_CurrentIP
0x180366352  mov     rbx, rax
0x180366355  lea     rdx, aServiceDataIsN; "Service data is NULL, cannot add pendin"...
0x18036635c  mov     ecx, 2000000h; unsigned int
0x180366361  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180366366  mov     dword ptr [rsp+180h+lpDependencies], esi
0x18036636a  mov     [rsp+180h+lpdwTagId], rsi
0x18036636f  mov     dword ptr [rsp+180h+lpLoadOrderGroup], edi
0x180366373  mov     [rsp+180h+lpBinaryPathName], rbx
0x180366378  lea     r12, aPserviceskeyen; "pServicesKeyEnumCallback"
0x18036637f  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x180366384  lea     r13, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x18036638b  mov     qword ptr [rsp+180h+dwStartType], r13
0x180366390  mov     [rsp+180h+dwServiceType], 3BAh
0x180366398  xor     r9d, r9d
0x18036639b  lea     r8, aD_0; "D"
0x1803663a2  mov     edx, 0C8000h
0x1803663a7  mov     rcx, rax
0x1803663aa  call    cs:__imp_WdsSetupLogMessageW
0x1803663b0  xor     eax, eax
0x1803663b2  jmp     loc_1803679F5
0x1803663b7  cmp     [r8+18h], rsi
0x1803663bb  jnz     short loc_18036641C
0x1803663bd  cmp     [r8+10h], rsi
0x1803663c1  jnz     short loc_18036641C
0x1803663c3  call    cs:__imp_GetLastError
0x1803663c9  mov     edi, eax
0x1803663cb  call    cs:__imp_CurrentIP
0x1803663d1  mov     rbx, rax
0x1803663d4  lea     rdx, aServiceDataIsI; "Service data is incomplete, cannot add "...
0x1803663db  mov     ecx, 2000000h; unsigned int
0x1803663e0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803663e5  mov     dword ptr [rsp+180h+lpDependencies], esi
0x1803663e9  mov     [rsp+180h+lpdwTagId], rsi
0x1803663ee  mov     dword ptr [rsp+180h+lpLoadOrderGroup], edi
0x1803663f2  mov     [rsp+180h+lpBinaryPathName], rbx
0x1803663f7  lea     r12, aPserviceskeyen; "pServicesKeyEnumCallback"
0x1803663fe  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x180366403  lea     r13, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x18036640a  mov     qword ptr [rsp+180h+dwStartType], r13
0x18036640f  mov     [rsp+180h+dwServiceType], 3BFh
0x180366417  jmp     loc_180366398
0x18036641c  lea     rcx, [rbp+80h+var_E0]
0x180366420  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180366426  nop
0x180366427  lea     rax, ??_7?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable'
0x18036642e  mov     [rbp+80h+var_E0.lpComment], rax
0x180366432  mov     [rbp+80h+var_E0.lpLocale], rsi
0x180366436  lea     rcx, [rbp+80h+var_E0.dwDisplayHint]
0x18036643a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180366440  nop
0x180366441  lea     rcx, [rbp+80h+var_E0.lpMachineName]
0x180366445  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18036644b  nop
0x18036644c  lea     rcx, [rbp+80h+var_E0.ServiceSpecificInfo]
0x180366450  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180366456  nop
0x180366457  lea     rcx, [rbp+80h+var_90]
0x18036645b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180366461  nop
0x180366462  lea     rcx, [rbp+80h+var_80]
0x180366466  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18036646c  nop
0x18036646d  lea     rcx, [rbp+80h+var_60]
0x180366471  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180366477  nop
0x180366478  xor     edx, edx; Val
0x18036647a  mov     r8d, 0A0h; Size
0x180366480  lea     rcx, [rbp+80h+var_E0]; void *
0x180366484  call    memset_0
0x180366489  or      eax, 0FFFFFFFFh
0x18036648c  mov     [rbp+80h+var_70], eax
0x18036648f  mov     [rbp+80h+var_6C], eax
0x180366492  mov     [rbp+80h+var_68], eax
0x180366495  lea     r9, [rbp+80h+var_E0]
0x180366499  lea     r8, ?pServicesValueEnumCallback@@YAHPEAUHKEY__@@PEBG_J@Z; pServicesValueEnumCallback(HKEY__ *,ushort const *,__int64)
0x1803664a0  xor     edx, edx
0x1803664a2  mov     rcx, rbx
0x1803664a5  call    RegEnumValues
0x1803664aa  test    eax, eax
0x1803664ac  jz      loc_1803679E4
0x1803664b2  call    cs:__imp_GetLastError
0x1803664b8  mov     edi, eax
0x1803664ba  call    cs:__imp_CurrentIP
0x1803664c0  mov     rbx, rax
0x1803664c3  lea     rdx, aAttemptingToAd_0; "Attempting to add service with data:"
0x1803664ca  mov     ecx, 4000000h; unsigned int
0x1803664cf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803664d4  mov     dword ptr [rsp+180h+lpDependencies], esi
0x1803664d8  mov     [rsp+180h+lpdwTagId], rsi
0x1803664dd  mov     dword ptr [rsp+180h+lpLoadOrderGroup], edi
0x1803664e1  mov     [rsp+180h+lpBinaryPathName], rbx
0x1803664e6  lea     r12, aPserviceskeyen; "pServicesKeyEnumCallback"
0x1803664ed  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x1803664f2  lea     r13, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1803664f9  mov     qword ptr [rsp+180h+dwStartType], r13
0x1803664fe  mov     [rsp+180h+dwServiceType], 3D3h
0x180366506  xor     r9d, r9d
0x180366509  lea     r14, aD_0; "D"
0x180366510  mov     r8, r14
0x180366513  mov     r15d, 0C8000h
0x180366519  mov     edx, r15d
0x18036651c  mov     rcx, rax
0x18036651f  call    cs:__imp_WdsSetupLogMessageW
0x180366525  call    cs:__imp_GetLastError
0x18036652b  mov     ebx, eax
0x18036652d  call    cs:__imp_CurrentIP
0x180366533  mov     rdi, rax
0x180366536  lea     rcx, [rbp+80h+var_E0]
0x18036653a  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x180366540  lea     rsi, aNull_0; "<<NULL>>"
0x180366547  test    rax, rax
0x18036654a  jz      short loc_180366561
0x18036654c  lea     rcx, [rbp+80h+var_E0]
0x180366550  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180366556  mov     rcx, rax
0x180366559  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18036655f  jmp     short loc_180366564
0x180366561  mov     rax, rsi
0x180366564  mov     r8, rax
0x180366567  lea     rdx, aNameS; "Name: %s"
0x18036656e  mov     ecx, 4000000h; unsigned int
0x180366573  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180366578  xor     ecx, ecx
0x18036657a  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x18036657e  mov     [rsp+180h+lpdwTagId], rcx
0x180366583  mov     dword ptr [rsp+180h+lpLoadOrderGroup], ebx
0x180366587  mov     [rsp+180h+lpBinaryPathName], rdi
0x18036658c  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x180366591  mov     qword ptr [rsp+180h+dwStartType], r13
0x180366596  mov     [rsp+180h+dwServiceType], 3D4h
0x18036659e  xor     r9d, r9d
0x1803665a1  mov     r8, r14
0x1803665a4  mov     edx, r15d
0x1803665a7  mov     rcx, rax
0x1803665aa  call    cs:__imp_WdsSetupLogMessageW
0x1803665b0  call    cs:__imp_GetLastError
0x1803665b6  mov     ebx, eax
0x1803665b8  call    cs:__imp_CurrentIP
0x1803665be  mov     rdi, rax
0x1803665c1  lea     rcx, [rbp+80h+var_80]
0x1803665c5  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1803665cb  test    rax, rax
0x1803665ce  jz      short loc_1803665E5
0x1803665d0  lea     rcx, [rbp+80h+var_80]
0x1803665d4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1803665da  mov     rcx, rax
0x1803665dd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1803665e3  jmp     short loc_1803665E8
0x1803665e5  mov     rax, rsi
0x1803665e8  mov     r8, rax
0x1803665eb  lea     rdx, aDisplayNameS; "Display name: %s"
0x1803665f2  mov     ecx, 4000000h; unsigned int
0x1803665f7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803665fc  xor     ecx, ecx
0x1803665fe  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x180366602  mov     [rsp+180h+lpdwTagId], rcx
0x180366607  mov     dword ptr [rsp+180h+lpLoadOrderGroup], ebx
0x18036660b  mov     [rsp+180h+lpBinaryPathName], rdi
0x180366610  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x180366615  mov     qword ptr [rsp+180h+dwStartType], r13
0x18036661a  mov     [rsp+180h+dwServiceType], 3D5h
0x180366622  xor     r9d, r9d
0x180366625  mov     r8, r14
0x180366628  mov     edx, r15d
0x18036662b  mov     rcx, rax
0x18036662e  call    cs:__imp_WdsSetupLogMessageW
0x180366634  call    cs:__imp_GetLastError
0x18036663a  mov     ebx, eax
0x18036663c  call    cs:__imp_CurrentIP
0x180366642  mov     rdi, rax
0x180366645  lea     rcx, [rbp+80h+var_90]
0x180366649  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x18036664f  test    rax, rax
0x180366652  jz      short loc_180366669
0x180366654  lea     rcx, [rbp+80h+var_90]
0x180366658  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18036665e  mov     rcx, rax
0x180366661  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180366667  jmp     short loc_18036666C
0x180366669  mov     rax, rsi
0x18036666c  mov     r8, rax
0x18036666f  lea     rdx, aStartNameS; "Start name: %s"
0x180366676  mov     ecx, 4000000h; unsigned int
0x18036667b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180366680  xor     ecx, ecx
0x180366682  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x180366686  mov     [rsp+180h+lpdwTagId], rcx
0x18036668b  mov     dword ptr [rsp+180h+lpLoadOrderGroup], ebx
0x18036668f  mov     [rsp+180h+lpBinaryPathName], rdi
0x180366694  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x180366699  mov     qword ptr [rsp+180h+dwStartType], r13
0x18036669e  mov     [rsp+180h+dwServiceType], 3D6h
0x1803666a6  xor     r9d, r9d
0x1803666a9  mov     r8, r14
0x1803666ac  mov     edx, r15d
0x1803666af  mov     rcx, rax
0x1803666b2  call    cs:__imp_WdsSetupLogMessageW
0x1803666b8  call    cs:__imp_GetLastError
0x1803666be  mov     ebx, eax
0x1803666c0  call    cs:__imp_CurrentIP
0x1803666c6  mov     rdi, rax
0x1803666c9  lea     rcx, [rbp+80h+var_E0.dwDisplayHint]
0x1803666cd  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1803666d3  test    rax, rax
0x1803666d6  jz      short loc_1803666ED
0x1803666d8  lea     rcx, [rbp+80h+var_E0.dwDisplayHint]
0x1803666dc  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1803666e2  mov     rcx, rax
0x1803666e5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1803666eb  jmp     short loc_1803666F0
0x1803666ed  mov     rax, rsi
0x1803666f0  mov     r8, rax
0x1803666f3  lea     rdx, aBinaryPathScmS; "Binary path (SCM): %s"
0x1803666fa  mov     ecx, 4000000h; unsigned int
0x1803666ff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180366704  xor     ecx, ecx
0x180366706  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x18036670a  mov     [rsp+180h+lpdwTagId], rcx
0x18036670f  mov     dword ptr [rsp+180h+lpLoadOrderGroup], ebx
0x180366713  mov     [rsp+180h+lpBinaryPathName], rdi
0x180366718  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x18036671d  mov     qword ptr [rsp+180h+dwStartType], r13
0x180366722  mov     [rsp+180h+dwServiceType], 3D7h
0x18036672a  xor     r9d, r9d
0x18036672d  mov     r8, r14
0x180366730  mov     edx, r15d
0x180366733  mov     rcx, rax
0x180366736  call    cs:__imp_WdsSetupLogMessageW
0x18036673c  call    cs:__imp_GetLastError
0x180366742  mov     ebx, eax
0x180366744  call    cs:__imp_CurrentIP
0x18036674a  mov     rdi, rax
0x18036674d  lea     rcx, [rbp+80h+var_E0.lpMachineName]
0x180366751  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x180366757  test    rax, rax
0x18036675a  jz      short loc_180366771
0x18036675c  lea     rcx, [rbp+80h+var_E0.lpMachineName]
0x180366760  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180366766  mov     rcx, rax
0x180366769  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18036676f  jmp     short loc_180366774
0x180366771  mov     rax, rsi
0x180366774  mov     r8, rax
0x180366777  lea     rdx, aBinaryPathOrgS; "Binary path (ORG): %s"
0x18036677e  mov     ecx, 4000000h; unsigned int
0x180366783  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180366788  xor     ecx, ecx
0x18036678a  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x18036678e  mov     [rsp+180h+lpdwTagId], rcx
0x180366793  mov     dword ptr [rsp+180h+lpLoadOrderGroup], ebx
0x180366797  mov     [rsp+180h+lpBinaryPathName], rdi
0x18036679c  mov     qword ptr [rsp+180h+dwErrorControl], r12
0x1803667a1  mov     qword ptr [rsp+180h+dwStartType], r13
0x1803667a6  mov     [rsp+180h+dwServiceType], 3D8h
0x1803667ae  xor     r9d, r9d
0x1803667b1  mov     r8, r14
0x1803667b4  mov     edx, r15d
0x1803667b7  mov     rcx, rax
0x1803667ba  call    cs:__imp_WdsSetupLogMessageW
0x1803667c0  call    cs:__imp_GetLastError
0x1803667c6  mov     ebx, eax
0x1803667c8  call    cs:__imp_CurrentIP
0x1803667ce  mov     rdi, rax
0x1803667d1  lea     rcx, [rbp+80h+var_E0.ServiceSpecificInfo]
0x1803667d5  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1803667db  test    rax, rax
0x1803667de  jz      short loc_1803667F5
0x1803667e0  lea     rcx, [rbp+80h+var_E0.ServiceSpecificInfo]
0x1803667e4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1803667ea  mov     rcx, rax
0x1803667ed  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1803667f3  jmp     short loc_1803667F8
0x1803667f5  mov     rax, rsi
0x1803667f8  mov     r8, rax
0x1803667fb  lea     rdx, aBinaryPathWinS; "Binary path (WIN): %s"
0x180366802  mov     ecx, 4000000h; unsigned int
0x180366807  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18036680c  xor     ecx, ecx
0x18036680e  mov     dword ptr [rsp+180h+lpDependencies], ecx
0x180366812  mov     [rsp+180h+lpdwTagId], rcx
  ... truncated ...
```
