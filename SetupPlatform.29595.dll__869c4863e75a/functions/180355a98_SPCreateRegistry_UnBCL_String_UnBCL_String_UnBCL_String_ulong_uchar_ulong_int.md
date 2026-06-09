# SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)

- ea: `0x180355a98`
- end: `0x180356acc`
- name: `?SPCreateRegistry@@YAJPEAVString@UnBCL@@00KPEAEKH@Z`
- size: `4148`
- prototype: `void __fastcall __noreturn(struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *, unsigned int, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180163d00`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x180355a98`
- `0x18035734c`
- `0x180404554`
- `0x1804bbfa0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18035641d`
- `ADVAPI32!RegSetValueExW` at `0x18035641d`
- `ADVAPI32!RegCreateKeyExW` at `0x180356315`
- `ADVAPI32!RegCreateKeyExW` at `0x180356315`
- `ADVAPI32!RegOpenKeyExW` at `0x1803560cd`
- `ADVAPI32!RegOpenKeyExW` at `0x1803560cd`
- `ADVAPI32!RegQueryValueExW` at `0x18035610f`
- `ADVAPI32!RegQueryValueExW` at `0x18035610f`
- `ADVAPI32!RegDeleteValueW` at `0x1803563d2`
- `ADVAPI32!RegDeleteValueW` at `0x1803563d2`
- `KERNEL32!GetLastError` at `0x180355b38`
- `KERNEL32!GetLastError` at `0x180355bb6`
- `KERNEL32!GetLastError` at `0x180355c42`
- `KERNEL32!GetLastError` at `0x180355cb9`
- `KERNEL32!GetLastError` at `0x180355e83`
- `KERNEL32!GetLastError` at `0x180356017`
- `KERNEL32!GetLastError` at `0x18035611d`
- `KERNEL32!GetLastError` at `0x18035624c`
- `KERNEL32!GetLastError` at `0x18035632e`
- `KERNEL32!GetLastError` at `0x180356473`
- `KERNEL32!GetLastError` at `0x18035648a`
- `KERNEL32!GetLastError` at `0x1803564aa`
- `KERNEL32!GetLastError` at `0x18035654b`
- `KERNEL32!GetLastError` at `0x180356561`
- `KERNEL32!GetLastError` at `0x180356581`
- `KERNEL32!GetLastError` at `0x180356626`
- `KERNEL32!GetLastError` at `0x18035676a`
- `KERNEL32!GetLastError` at `0x180356827`
- `KERNEL32!GetLastError` at `0x1803568d1`
- `KERNEL32!GetLastError` at `0x180356977`
- `KERNEL32!GetLastError` at `0x180356a37`
- `KERNEL32!GetLastError` at `0x180355b38`
- `KERNEL32!GetLastError` at `0x180355bb6`
- `KERNEL32!GetLastError` at `0x180355c42`
- `KERNEL32!GetLastError` at `0x180355cb9`
- `KERNEL32!GetLastError` at `0x180355e83`
- `KERNEL32!GetLastError` at `0x180356017`
- `KERNEL32!GetLastError` at `0x18035611d`
- `KERNEL32!GetLastError` at `0x18035624c`
- `KERNEL32!GetLastError` at `0x18035632e`
- `KERNEL32!GetLastError` at `0x180356473`
- `KERNEL32!GetLastError` at `0x18035648a`
- `KERNEL32!GetLastError` at `0x1803564aa`
- `KERNEL32!GetLastError` at `0x18035654b`
- `KERNEL32!GetLastError` at `0x180356561`
- `KERNEL32!GetLastError` at `0x180356581`
- `KERNEL32!GetLastError` at `0x180356626`
- `KERNEL32!GetLastError` at `0x18035676a`
- `KERNEL32!GetLastError` at `0x180356827`
- `KERNEL32!GetLastError` at `0x1803568d1`
- `KERNEL32!GetLastError` at `0x180356977`
- `KERNEL32!GetLastError` at `0x180356a37`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180355f63`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180355f63`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180355fd5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180355fd5`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355d84`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355d99`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355dcc`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355f8a`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180356169`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18035617e`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355d84`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355d99`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355dcc`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180355f8a`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180356169`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18035617e`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180355d3f`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180355d3f`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18035643a`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18035643a`
- `unbcl!?IndexOf@String@UnBCL@@QEBAHPEBG@Z` at `0x1803561ce`
- `unbcl!?IndexOf@String@UnBCL@@QEBAHPEBG@Z` at `0x1803561ce`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180355b21`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180355b21`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180355e31`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1803561e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180355e31`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1803561e1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180355e02`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18035619f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180355e02`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18035619f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180355e65`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180355ffa`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180356218`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180355e65`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180355ffa`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180356218`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180355f76`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180355fb9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18035602d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803560a5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180356262`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803562d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180356780`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18035698d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180355f76`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180355fb9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18035602d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803560a5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180356262`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1803562d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180356780`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18035698d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355b4c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355bcf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355e1d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355f00`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355fc2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356036`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803560ae`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803560f1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035613d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803561bb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035626b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803562e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356347`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803563bf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803563ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803566c4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356789`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035683b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356996`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355b4c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355bcf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355e1d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355f00`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180355fc2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356036`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803560ae`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803560f1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035613d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803561bb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035626b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803562e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356347`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803563bf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803563ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803566c4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356789`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18035683b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180356996`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180355e74`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356009`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356227`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356446`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180355e74`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356009`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356227`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180356446`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180355e51`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180355fe6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180356204`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180355e51`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180355fe6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180356204`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355bb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355c3c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355cb3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355d2c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355ef2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035609a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803562ce`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803563ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035651c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803565ef`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035668b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035672c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803567e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803568a2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180356935`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803569fd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180356a9b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355bb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355c3c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355cb3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355d2c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180355ef2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035609a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803562ce`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803563ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035651c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803565ef`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035668b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18035672c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803567e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803568a2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180356935`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803569fd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180356a9b`
- `WDSCORE!CurrentIP` at `0x180355b40`
- `WDSCORE!CurrentIP` at `0x180355bbe`
- `WDSCORE!CurrentIP` at `0x180355c4a`
- `WDSCORE!CurrentIP` at `0x180355cc1`
- `WDSCORE!CurrentIP` at `0x180355e8b`
- `WDSCORE!CurrentIP` at `0x18035601f`
- `WDSCORE!CurrentIP` at `0x180356125`
- `WDSCORE!CurrentIP` at `0x180356254`

## string_xrefs

- `0x180355b8d`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180355c19`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180355c90`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180355d09`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180355ecf`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356077`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x1803562ab`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356389`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x1803564f9`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x1803565cc`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356668`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356709`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x1803567c6`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x18035687f`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356912`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x1803569da`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180356a78`: `base\ntsetup\setupplatform\lib\util\registryutils.cpp`
- `0x180355b5c`: `%hs: Registry key: %s`
- `0x180355b55`: `SPCreateRegistry`
- `0x180355be1`: `SPCreateRegistry`
- `0x180355c56`: `SPCreateRegistry`
- `0x180355cd2`: `SPCreateRegistry`
- `0x180355e97`: `SPCreateRegistry`
- `0x18035603f`: `SPCreateRegistry`
- `0x180356274`: `SPCreateRegistry`
- `0x180356359`: `SPCreateRegistry`
- `0x1803564c2`: `SPCreateRegistry`
- `0x180356595`: `SPCreateRegistry`
- `0x1803566d2`: `SPCreateRegistry`
- `0x180356796`: `SPCreateRegistry`
- `0x180356848`: `SPCreateRegistry`
- `0x1803568e2`: `SPCreateRegistry`
- `0x1803569a3`: `SPCreateRegistry`
- `0x180355b81`: `SPCreateRegistry`
- `0x180355c0d`: `SPCreateRegistry`
- `0x180355c84`: `SPCreateRegistry`
- `0x180355cfd`: `SPCreateRegistry`
- `0x180355ec3`: `SPCreateRegistry`
- `0x18035606b`: `SPCreateRegistry`
- `0x18035629f`: `SPCreateRegistry`
- `0x180356327`: `SPCreateRegistry`
- `0x1803564ed`: `SPCreateRegistry`
- `0x1803565c0`: `SPCreateRegistry`
- `0x18035665c`: `SPCreateRegistry`
- `0x1803566fd`: `SPCreateRegistry`
- `0x180356873`: `SPCreateRegistry`
- `0x1803569ce`: `SPCreateRegistry`
- `0x180356a6c`: `SPCreateRegistry`
- `0x180355c5d`: `%hs: Registry Type: %d`
- `0x1803569aa`: `%hs: Cannot open subkey %s. Error: 0x%08X`
- `0x18035679d`: `%hs: Cannot create subkey %s. Error: 0x%08X`
- `0x18035627b`: `%hs: Create subkey %s`
- `0x1803566d9`: `%hs: %s [%s] is already present, we were asked to not overwrite`
- `0x180356046`: `%hs: Open subkey %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
void __fastcall __noreturn SPCreateRegistry(
        struct UnBCL::String *a1,
        struct UnBCL::String *a2,
        struct UnBCL::String *a3,
        DWORD a4,
        unsigned __int8 *a5,
        DWORD a6,
        int a7)
{
  BYTE *v11; // r13
  DWORD LastError; // edi
  __int64 v13; // rbx
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // ebx
  __int64 v17; // rdi
  const wchar_t *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  int v23; // r12d
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  __int64 v27; // rdi
  const char *v28; // r12
  const unsigned __int16 *v29; // r13
  __int64 v30; // rbx
  UnBCL::String *v31; // rdi
  const unsigned __int16 *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  const unsigned __int16 *v36; // rax
  HKEY v37; // rdi
  UnBCL::String *v38; // rax
  unsigned int Dword; // ebx
  UnBCL::String *v40; // rax
  const unsigned __int16 *v41; // rax
  struct UnBCL::String *v42; // rax
  DWORD v43; // ebx
  __int64 v44; // r12
  UnBCL::String *v45; // rax
  const char *v46; // rax
  struct tagLOG_PARTIAL_MSG *v47; // rax
  UnBCL::String *v48; // rax
  const WCHAR *v49; // rax
  LSTATUS v50; // eax
  unsigned int v51; // ebx
  const WCHAR *v52; // rax
  DWORD v53; // edi
  __int64 v54; // r12
  const wchar_t *v55; // rbx
  int i; // edi
  __int64 v57; // r12
  UnBCL::String *v58; // rbx
  const unsigned __int16 *v59; // r12
  int v60; // eax
  DWORD v61; // ebx
  __int64 v62; // r15
  UnBCL::String *v63; // rax
  const char *v64; // rax
  struct tagLOG_PARTIAL_MSG *v65; // rax
  UnBCL::String *v66; // rax
  const WCHAR *v67; // rax
  LSTATUS v68; // eax
  unsigned int v69; // ebx
  DWORD v70; // ebx
  __int64 v71; // rdi
  const wchar_t *v72; // rax
  struct tagLOG_PARTIAL_MSG *v73; // rax
  const WCHAR *v74; // rax
  int v75; // ebx
  const WCHAR *v76; // rax
  signed int v77; // eax
  bool v78; // sf
  signed int v79; // eax
  unsigned int v80; // esi
  DWORD v81; // edi
  __int64 v82; // rbx
  struct tagLOG_PARTIAL_MSG *v83; // rax
  signed int v84; // eax
  bool v85; // sf
  signed int v86; // eax
  unsigned int v87; // esi
  DWORD v88; // edi
  __int64 v89; // rbx
  struct tagLOG_PARTIAL_MSG *v90; // rax
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  const char *v94; // rax
  struct tagLOG_PARTIAL_MSG *v95; // rax
  DWORD v96; // edi
  __int64 v97; // rsi
  UnBCL::String *v98; // rax
  const char *v99; // rax
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // r15
  const char *v103; // rax
  struct tagLOG_PARTIAL_MSG *v104; // rax
  DWORD v105; // edi
  __int64 v106; // rbx
  struct tagLOG_PARTIAL_MSG *v107; // rax
  DWORD v108; // edi
  __int64 v109; // rsi
  UnBCL::String *v110; // rax
  const char *v111; // rax
  struct tagLOG_PARTIAL_MSG *v112; // rax
  DWORD v113; // edi
  __int64 v114; // rbx
  struct tagLOG_PARTIAL_MSG *v115; // rax
  HKEY hKey; // [rsp+68h] [rbp-160h] BYREF
  _BYTE v117[16]; // [rsp+70h] [rbp-158h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-148h]
  HKEY v119; // [rsp+88h] [rbp-140h]
  _BYTE v120[16]; // [rsp+90h] [rbp-138h] BYREF
  DWORD dwType; // [rsp+A0h] [rbp-128h]
  BYTE *lpData; // [rsp+A8h] [rbp-120h]
  __int64 v123; // [rsp+B0h] [rbp-118h]
  const unsigned __int16 *v124; // [rsp+B8h] [rbp-110h]
  UnBCL::String *v125; // [rsp+C0h] [rbp-108h]
  _QWORD *pExceptionObject; // [rsp+C8h] [rbp-100h] BYREF
  _QWORD *v127; // [rsp+D0h] [rbp-F8h] BYREF
  _QWORD *v128; // [rsp+D8h] [rbp-F0h] BYREF
  _QWORD *v129; // [rsp+E0h] [rbp-E8h] BYREF
  _QWORD *v130; // [rsp+E8h] [rbp-E0h] BYREF
  _QWORD *v131; // [rsp+F0h] [rbp-D8h] BYREF
  _QWORD *v132; // [rsp+F8h] [rbp-D0h] BYREF
  _QWORD *v133; // [rsp+100h] [rbp-C8h] BYREF
  _QWORD v134[2]; // [rsp+108h] [rbp-C0h] BYREF
  UnBCL::String *v135; // [rsp+118h] [rbp-B0h]
  _QWORD v136[8]; // [rsp+120h] [rbp-A8h] BYREF
  _OWORD v137[2]; // [rsp+160h] [rbp-68h] BYREF
  int v138; // [rsp+180h] [rbp-48h]

  v136[7] = -2;
  dwType = a4;
  v125 = a1;
  v134[1] = a1;
  v11 = a5;
  lpData = a5;
  cbData = a6;
  v119 = 0;
  hKey = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v117);
  v123 = 0;
  v124 = 0;
  LastError = GetLastError();
  v13 = CurrentIP();
  CString = (const char *)UnBCL::String::get_CString(a2);
  v15 = ConstructPartialMsgW(0x4000000u, "%hs: Registry key: %s", "SPCreateRegistry", CString);
  WdsSetupLogMessageW(
    v15,
    0,
    L"D",
    0,
    505,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v13,
    LastError,
    0,
    0);
  v16 = GetLastError();
  v17 = CurrentIP();
  if ( a3 )
    v18 = UnBCL::String::get_CString(a3);
  else
    v18 = L"NULL";
  v19 = ConstructPartialMsgW(0x4000000u, "%hs: Value name: %s", "SPCreateRegistry", (const char *)v18);
  WdsSetupLogMessageW(
    v19,
    0,
    L"D",
    0,
    506,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v17,
    v16,
    0,
    0);
  v20 = GetLastError();
  v21 = CurrentIP();
  v22 = ConstructPartialMsgW(0x4000000u, "%hs: Registry Type: %d", "SPCreateRegistry", a4);
  v23 = 0;
  WdsSetupLogMessageW(
    v22,
    0,
    L"D",
    0,
    507,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v21,
    v20,
    0,
    0);
  v24 = GetLastError();
  v25 = CurrentIP();
  v26 = ConstructPartialMsgW(0x4000000u, "%hs: Data size: %d", "SPCreateRegistry", cbData);
  WdsSetupLogMessageW(
    v26,
    0,
    L"D",
    0,
    508,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v25,
    v24,
    0,
    0);
  UnBCL::Exception::Exception((UnBCL::Exception *)v136);
  v136[0] = &`SPCreateRegistry'::`3'::CXXXXXHandledException::`vftable';
  if ( a1 )
  {
    while ( 1 )
    {
      if ( (unsigned __int64)v23 >= 3 )
        goto LABEL_71;
      v27 = 5LL * v23;
      if ( UnBCL::String::StartsWith(a2, (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + 5 * v23), 1)
        || UnBCL::String::StartsWith(a2, (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + 5 * v23 + 1), 1) )
      {
        break;
      }
      ++v23;
    }
    v28 = (const char *)*(&g_QueueCreateRegistryMap + 5 * v23 + 3);
    v123 = (__int64)*(&g_QueueCreateRegistryMap + v27 + 3);
    v29 = (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + v27 + 4);
    v124 = v29;
    if ( UnBCL::String::StartsWith(a2, (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + v27), 1) )
    {
      v30 = -1;
      do
        ++v30;
      while ( *((_WORD *)*(&g_QueueCreateRegistryMap + v27) + v30) );
    }
    else
    {
      v30 = -1;
      do
        ++v30;
      while ( *((_WORD *)*(&g_QueueCreateRegistryMap + v27 + 1) + v30) );
    }
    v31 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v135 = v31;
    if ( v31 )
    {
      v32 = UnBCL::String::get_CString(a2);
      UnBCL::String::String(v31, &v32[(int)v30 + 1]);
      *(_QWORD *)v31 = &UnBCL::String::`local vftable';
    }
    else
    {
      v31 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v120, v31);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v117, v120);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v120);
    if ( !v28 )
    {
LABEL_71:
      v91 = GetLastError();
      v92 = CurrentIP();
      v93 = ConstructPartialMsgW(0x2000000u, "The specified key is invalid");
      WdsSetupLogMessageW(
        v93,
        0,
        L"D",
        0,
        533,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v92,
        v91,
        0,
        0);
      v128 = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v128;
    }
    v33 = GetLastError();
    v34 = CurrentIP();
    v35 = ConstructPartialMsgW(0x4000000u, "%hs: Load hive %s", "SPCreateRegistry", v28);
    WdsSetupLogMessageW(
      v35,
      0,
      L"D",
      0,
      537,
      L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
      L"SPCreateRegistry",
      v34,
      v33,
      0,
      0);
    v36 = UnBCL::String::get_CString(v125);
    v37 = SPMountOfflineHive(v36, (const unsigned __int16 *)v28, v29);
    v119 = v37;
    if ( !v37 )
    {
      v77 = GetLastError();
      v78 = v77 < 0;
      if ( v77 > 0 )
        v78 = 1;
      if ( v78 )
      {
        v79 = GetLastError();
        v80 = v79;
        if ( v79 > 0 )
          v80 = (unsigned __int16)v79 | 0x80070000;
      }
      else
      {
        v80 = -2147467259;
      }
      v81 = GetLastError();
      v82 = CurrentIP();
      v83 = ConstructPartialMsgW(
              0x2000000u,
              "%hs: Cannot load the hive %s for the offline OS. Error: 0x%08X",
              "SPCreateRegistry",
              v28,
              v80);
      WdsSetupLogMessageW(
        v83,
        0,
        L"D",
        0,
        544,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v82,
        v81,
        0,
        0);
      pExceptionObject = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&pExceptionObject;
    }
    v137[0] = *(_OWORD *)L"CurrentControlSet";
    v137[1] = *(_OWORD *)L"ontrolSet";
    v138 = *(_DWORD *)L"t";
    if ( !UnBCL::String::Compare((const unsigned __int16 *)v28, L"SYSTEM", 1) )
    {
      v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
      if ( UnBCL::String::StartsWith(v38, (const unsigned __int16 *)v137, 1) )
      {
        Dword = RegGetDword(v37, L"Select", L"Current");
        if ( !Dword )
        {
          v84 = GetLastError();
          v85 = v84 < 0;
          if ( v84 > 0 )
            v85 = 1;
          if ( v85 )
          {
            v86 = GetLastError();
            v87 = v86;
            if ( v86 > 0 )
              v87 = (unsigned __int16)v86 | 0x80070000;
          }
          else
          {
            v87 = -2147467259;
          }
          v88 = GetLastError();
          v89 = CurrentIP();
          v90 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: Cannot determine current control set for the offline OS. Error: 0x%08X",
                  "SPCreateRegistry",
                  v87);
          WdsSetupLogMessageW(
            v90,
            0,
            L"D",
            0,
            558,
            L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
            L"SPCreateRegistry",
            v89,
            v88,
            0,
            0);
          v127 = v136;
          throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v127;
        }
        v40 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
        v41 = UnBCL::String::get_CString(v40);
        v42 = UnBCL::String::Format(L"ControlSet%03u%s", Dword, v41 + 17);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v120, v42);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v117, v120);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v120);
      }
    }
    v11 = lpData;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      if ( (unsigned __int64)i >= 3 )
        goto LABEL_84;
      v57 = 5LL * i;
      if ( UnBCL::String::StartsWith(a2, (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + 5 * i), 1)
        || UnBCL::String::StartsWith(a2, (const unsigned __int16 *)*(&g_QueueCreateRegistryMap + 5 * i + 1), 1) )
      {
        break;
      }
    }
    v37 = (HKEY)*(&g_QueueCreateRegistryMap + 5 * i + 2);
    v119 = (HKEY)*(&g_QueueCreateRegistryMap + v57 + 2);
    v58 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v135 = v58;
    if ( v58 )
    {
      v59 = UnBCL::String::get_CString(a2);
      v60 = UnBCL::String::IndexOf(a2, L"\\");
      UnBCL::String::String(v58, &v59[v60 + 1]);
      *(_QWORD *)v58 = &UnBCL::String::`local vftable';
    }
    else
    {
      v58 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v120, v58);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v117, v120);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v120);
    v119 = v37;
    if ( !v37 )
    {
LABEL_84:
      v113 = GetLastError();
      v114 = CurrentIP();
      v115 = ConstructPartialMsgW(0x2000000u, "The specified key is invalid");
      WdsSetupLogMessageW(
        v115,
        0,
        L"D",
        0,
        582,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v114,
        v113,
        0,
        0);
      v134[0] = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)v134;
    }
  }
  v43 = GetLastError();
  v44 = CurrentIP();
  v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
  v46 = (const char *)UnBCL::String::get_CString(v45);
  v47 = ConstructPartialMsgW(0x4000000u, "%hs: Open subkey %s", "SPCreateRegistry", v46);
  WdsSetupLogMessageW(
    v47,
    0,
    L"D",
    0,
    587,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v44,
    v43,
    0,
    0);
  v48 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
  v49 = UnBCL::String::get_CString(v48);
  v50 = RegOpenKeyExW(v37, v49, 0, 0x2001Fu, &hKey);
  v51 = v50;
  if ( v50 )
  {
    if ( v50 != 2 )
    {
      if ( v50 > 0 )
        v51 = (unsigned __int16)v50 | 0x80070000;
      v108 = GetLastError();
      v109 = CurrentIP();
      v110 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
      v111 = (const char *)UnBCL::String::get_CString(v110);
      v112 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Cannot open subkey %s. Error: 0x%08X",
               "SPCreateRegistry",
               v111,
               v51);
      WdsSetupLogMessageW(
        v112,
        0,
        L"D",
        0,
        650,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v109,
        v108,
        0,
        0);
      v133 = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v133;
    }
    v61 = GetLastError();
    v62 = CurrentIP();
    v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
    v64 = (const char *)UnBCL::String::get_CString(v63);
    v65 = ConstructPartialMsgW(0x4000000u, "%hs: Create subkey %s", "SPCreateRegistry", v64);
    WdsSetupLogMessageW(
      v65,
      0,
      L"D",
      0,
      626,
      L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
      L"SPCreateRegistry",
      v62,
      v61,
      0,
      0);
    v66 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
    v67 = UnBCL::String::get_CString(v66);
    v68 = RegCreateKeyExW(v37, v67, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    v69 = v68;
    if ( v68 )
    {
      if ( v68 > 0 )
        v69 = (unsigned __int16)v68 | 0x80070000;
      v96 = GetLastError();
      v97 = CurrentIP();
      v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
      v99 = (const char *)UnBCL::String::get_CString(v98);
      v100 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Cannot create subkey %s. Error: 0x%08X",
               "SPCreateRegistry",
               v99,
               v69);
      WdsSetupLogMessageW(
        v100,
        0,
        L"D",
        0,
        643,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v97,
        v96,
        0,
        0);
      v130 = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v130;
    }
  }
  else if ( !a7 )
  {
    v52 = UnBCL::String::get_CString(a3);
    if ( !RegQueryValueExW(hKey, v52, 0, 0, 0, 0) )
    {
      v53 = GetLastError();
      v54 = CurrentIP();
      if ( a3 )
        v55 = UnBCL::String::get_CString(a3);
      else
        v55 = &cchOriginalDestLength;
      v94 = (const char *)UnBCL::String::get_CString(a2);
      v95 = ConstructPartialMsgW(
              0x3000000u,
              "%hs: %s [%s] is already present, we were asked to not overwrite",
              "SPCreateRegistry",
              v94,
              (const char *)v55);
      WdsSetupLogMessageW(
        v95,
        0,
        L"D",
        0,
        617,
        L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
        L"SPCreateRegistry",
        v54,
        v53,
        0,
        0);
      v129 = v136;
      throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v129;
    }
  }
  v70 = GetLastError();
  v71 = CurrentIP();
  if ( a3 )
    v72 = UnBCL::String::get_CString(a3);
  else
    v72 = L"NULL";
  v73 = ConstructPartialMsgW(0x4000000u, "%hs: Set key value %s", "SPCreateRegistry", (const char *)v72);
  WdsSetupLogMessageW(
    v73,
    0,
    L"D",
    0,
    655,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v71,
    v70,
    0,
    0);
  if ( v11 )
  {
    if ( a3 )
      v76 = UnBCL::String::get_CString(a3);
    else
      v76 = 0;
    v75 = RegSetValueExW(hKey, v76, 0, dwType, v11, cbData);
  }
  else
  {
    if ( a3 )
      v74 = UnBCL::String::get_CString(a3);
    else
      v74 = 0;
    v75 = RegDeleteValueW(hKey, v74);
    if ( (unsigned int)(v75 - 2) <= 1 )
      v75 = 0;
  }
  if ( v75 )
  {
    if ( v75 > 0 )
      v75 = (unsigned __int16)v75 | 0x80070000;
    v101 = GetLastError();
    v102 = CurrentIP();
    v103 = (const char *)UnBCL::String::get_CString(a3);
    v104 = ConstructPartialMsgW(
             0x2000000u,
             "%hs: Cannot set key value %s. Error: 0x%08X",
             "SPCreateRegistry",
             v103,
             v75);
    WdsSetupLogMessageW(
      v104,
      0,
      L"D",
      0,
      682,
      L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
      L"SPCreateRegistry",
      v102,
      v101,
      0,
      0);
    v131 = v136;
    throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v131;
  }
  v105 = GetLastError();
  v106 = CurrentIP();
  v107 = ConstructPartialMsgW(0x4000000u, "%hs: Key value set", "SPCreateRegistry");
  WdsSetupLogMessageW(
    v107,
    0,
    L"D",
    0,
    686,
    L"base\\ntsetup\\setupplatform\\lib\\util\\registryutils.cpp",
    L"SPCreateRegistry",
    v106,
    v105,
    0,
    0);
  v132 = v136;
  throw (`SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException **)&v132;
}

```

## disassembly

```asm
0x180355a98  mov     rax, rsp
0x180355a9b  push    rbx
0x180355a9c  push    rsi
0x180355a9d  push    rdi
0x180355a9e  push    r12
0x180355aa0  push    r13
0x180355aa2  push    r14
0x180355aa4  push    r15
0x180355aa6  sub     rsp, 190h
0x180355aad  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFEh
0x180355ab5  mov     rax, cs:__security_cookie
0x180355abc  xor     rax, rsp
0x180355abf  mov     [rsp+1C8h+var_40], rax
0x180355ac7  mov     r12d, r9d
0x180355aca  mov     [rsp+1C8h+dwType], r9d
0x180355ad2  mov     rsi, r8
0x180355ad5  mov     r15, rdx
0x180355ad8  mov     r14, rcx
0x180355adb  mov     [rsp+1C8h+var_108], rcx
0x180355ae3  mov     [rsp+1C8h+var_B8], rcx
0x180355aeb  mov     r13, [rsp+1C8h+arg_20]
0x180355af3  mov     [rsp+1C8h+lpData], r13
0x180355afb  mov     eax, [rsp+1C8h+arg_28]
0x180355b02  mov     [rsp+1C8h+cbData], eax
0x180355b09  xor     ebx, ebx
0x180355b0b  mov     [rsp+1C8h+var_164], ebx
0x180355b0f  mov     [rsp+1C8h+var_140], rbx
0x180355b17  mov     [rsp+1C8h+hKey], rbx
0x180355b1c  lea     rcx, [rsp+1C8h+var_158]
0x180355b21  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180355b27  nop
0x180355b28  mov     [rsp+1C8h+var_118], rbx
0x180355b30  mov     [rsp+1C8h+var_110], rbx
0x180355b38  call    cs:__imp_GetLastError
0x180355b3e  mov     edi, eax
0x180355b40  call    cs:__imp_CurrentIP
0x180355b46  mov     rbx, rax
0x180355b49  mov     rcx, r15
0x180355b4c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180355b52  mov     r9, rax
0x180355b55  lea     r8, aSpcreateregist_0; "SPCreateRegistry"
0x180355b5c  lea     rdx, aHsRegistryKeyS; "%hs: Registry key: %s"
0x180355b63  mov     ecx, 4000000h; unsigned int
0x180355b68  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180355b6d  xor     ecx, ecx
0x180355b6f  mov     [rsp+1C8h+var_178], ecx
0x180355b73  mov     [rsp+1C8h+var_180], rcx
0x180355b78  mov     dword ptr [rsp+1C8h+lpdwDisposition], edi
0x180355b7c  mov     [rsp+1C8h+var_190], rbx
0x180355b81  lea     rcx, aSpcreateregist; "SPCreateRegistry"
0x180355b88  mov     [rsp+1C8h+lpSecurityAttributes], rcx
0x180355b8d  lea     rcx, aBaseNtsetupSet_50; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180355b94  mov     [rsp+1C8h+lpcbData], rcx
0x180355b99  mov     dword ptr [rsp+1C8h+phkResult], 1F9h
0x180355ba1  xor     r9d, r9d
0x180355ba4  lea     r8, aD_0; "D"
0x180355bab  xor     edx, edx
0x180355bad  mov     rcx, rax
0x180355bb0  call    cs:__imp_WdsSetupLogMessageW
0x180355bb6  call    cs:__imp_GetLastError
0x180355bbc  mov     ebx, eax
0x180355bbe  call    cs:__imp_CurrentIP
0x180355bc4  mov     rdi, rax
0x180355bc7  test    rsi, rsi
0x180355bca  jz      short loc_180355BD7
0x180355bcc  mov     rcx, rsi
0x180355bcf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180355bd5  jmp     short loc_180355BDE
0x180355bd7  lea     rax, aNull_5; "NULL"
0x180355bde  mov     r9, rax
0x180355be1  lea     r8, aSpcreateregist_0; "SPCreateRegistry"
0x180355be8  lea     rdx, aHsValueNameS; "%hs: Value name: %s"
0x180355bef  mov     ecx, 4000000h; unsigned int
0x180355bf4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180355bf9  xor     ecx, ecx
0x180355bfb  mov     [rsp+1C8h+var_178], ecx
0x180355bff  mov     [rsp+1C8h+var_180], rcx
0x180355c04  mov     dword ptr [rsp+1C8h+lpdwDisposition], ebx
0x180355c08  mov     [rsp+1C8h+var_190], rdi
0x180355c0d  lea     rcx, aSpcreateregist; "SPCreateRegistry"
0x180355c14  mov     [rsp+1C8h+lpSecurityAttributes], rcx
0x180355c19  lea     rcx, aBaseNtsetupSet_50; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180355c20  mov     [rsp+1C8h+lpcbData], rcx
0x180355c25  mov     dword ptr [rsp+1C8h+phkResult], 1FAh
0x180355c2d  xor     r9d, r9d
0x180355c30  lea     r8, aD_0; "D"
0x180355c37  xor     edx, edx
0x180355c39  mov     rcx, rax
0x180355c3c  call    cs:__imp_WdsSetupLogMessageW
0x180355c42  call    cs:__imp_GetLastError
0x180355c48  mov     edi, eax
0x180355c4a  call    cs:__imp_CurrentIP
0x180355c50  mov     rbx, rax
0x180355c53  mov     r9d, r12d
0x180355c56  lea     r8, aSpcreateregist_0; "SPCreateRegistry"
0x180355c5d  lea     rdx, aHsRegistryType; "%hs: Registry Type: %d"
0x180355c64  mov     ecx, 4000000h; unsigned int
0x180355c69  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180355c6e  xor     r12d, r12d
0x180355c71  mov     [rsp+1C8h+var_178], r12d
0x180355c76  mov     [rsp+1C8h+var_180], r12
0x180355c7b  mov     dword ptr [rsp+1C8h+lpdwDisposition], edi
0x180355c7f  mov     [rsp+1C8h+var_190], rbx
0x180355c84  lea     rcx, aSpcreateregist; "SPCreateRegistry"
0x180355c8b  mov     [rsp+1C8h+lpSecurityAttributes], rcx
0x180355c90  lea     rcx, aBaseNtsetupSet_50; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180355c97  mov     [rsp+1C8h+lpcbData], rcx
0x180355c9c  mov     dword ptr [rsp+1C8h+phkResult], 1FBh
0x180355ca4  xor     r9d, r9d
0x180355ca7  lea     r8, aD_0; "D"
0x180355cae  xor     edx, edx
0x180355cb0  mov     rcx, rax
0x180355cb3  call    cs:__imp_WdsSetupLogMessageW
0x180355cb9  call    cs:__imp_GetLastError
0x180355cbf  mov     edi, eax
0x180355cc1  call    cs:__imp_CurrentIP
0x180355cc7  mov     rbx, rax
0x180355cca  mov     r9d, [rsp+1C8h+cbData]
0x180355cd2  lea     r8, aSpcreateregist_0; "SPCreateRegistry"
0x180355cd9  lea     rdx, aHsDataSizeD; "%hs: Data size: %d"
0x180355ce0  mov     ecx, 4000000h; unsigned int
0x180355ce5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180355cea  mov     [rsp+1C8h+var_178], r12d
0x180355cef  mov     [rsp+1C8h+var_180], r12
0x180355cf4  mov     dword ptr [rsp+1C8h+lpdwDisposition], edi
0x180355cf8  mov     [rsp+1C8h+var_190], rbx
0x180355cfd  lea     rcx, aSpcreateregist; "SPCreateRegistry"
0x180355d04  mov     [rsp+1C8h+lpSecurityAttributes], rcx
0x180355d09  lea     rcx, aBaseNtsetupSet_50; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180355d10  mov     [rsp+1C8h+lpcbData], rcx
0x180355d15  mov     dword ptr [rsp+1C8h+phkResult], 1FCh
0x180355d1d  xor     r9d, r9d
0x180355d20  lea     r8, aD_0; "D"
0x180355d27  xor     edx, edx
0x180355d29  mov     rcx, rax
0x180355d2c  call    cs:__imp_WdsSetupLogMessageW
0x180355d32  mov     [rsp+1C8h+var_168], r12d
0x180355d37  lea     rcx, [rsp+1C8h+var_A8]
0x180355d3f  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180355d45  lea     rax, ??_7CXXXXXHandledException@?2??SPCreateRegistry@@YAJPEAVString@UnBCL@@00KPEAEKH@Z@6B@; const `SPCreateRegistry(UnBCL::String *,UnBCL::String *,UnBCL::String *,ulong,uchar *,ulong,int)'::`3'::CXXXXXHandledException::`vftable'
0x180355d4c  mov     [rsp+1C8h+var_A8], rax
0x180355d54  lea     rbx, ?g_QueueCreateRegistryMap@@3PAU_unnamed_type_g_QueueCreateRegistryMap_@@A; _unnamed_type_g_QueueCreateRegistryMap_ near * g_QueueCreateRegistryMap
0x180355d5b  test    r14, r14
0x180355d5e  lea     r14d, [r12+1]
0x180355d63  jz      loc_18035614B
0x180355d69  movsxd  rax, r12d
0x180355d6c  cmp     rax, 3
0x180355d70  jnb     loc_18035661E
0x180355d76  lea     rdi, [rax+rax*4]
0x180355d7a  mov     r8d, r14d
0x180355d7d  mov     rdx, [rbx+rdi*8]
0x180355d81  mov     rcx, r15
0x180355d84  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180355d8a  test    eax, eax
0x180355d8c  jnz     short loc_180355DA8
0x180355d8e  mov     r8d, r14d
0x180355d91  mov     rdx, [rbx+rdi*8+8]
0x180355d96  mov     rcx, r15
0x180355d99  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180355d9f  test    eax, eax
0x180355da1  jnz     short loc_180355DA8
0x180355da3  add     r12d, r14d
0x180355da6  jmp     short loc_180355D69
0x180355da8  mov     r12, [rbx+rdi*8+18h]
0x180355dad  mov     [rsp+1C8h+var_118], r12
0x180355db5  mov     r13, [rbx+rdi*8+20h]
0x180355dba  mov     [rsp+1C8h+var_110], r13
0x180355dc2  mov     r8d, r14d
0x180355dc5  mov     rdx, [rbx+rdi*8]
0x180355dc9  mov     rcx, r15
0x180355dcc  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180355dd2  xor     ecx, ecx
0x180355dd4  test    eax, eax
0x180355dd6  jz      short loc_180355DEB
0x180355dd8  mov     rax, [rbx+rdi*8]
0x180355ddc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180355de0  inc     rbx
0x180355de3  cmp     [rax+rbx*2], cx
0x180355de7  jnz     short loc_180355DE0
0x180355de9  jmp     short loc_180355DFD
0x180355deb  mov     rax, [rbx+rdi*8+8]
0x180355df0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180355df4  inc     rbx
0x180355df7  cmp     [rax+rbx*2], cx
0x180355dfb  jnz     short loc_180355DF4
0x180355dfd  mov     ecx, 18h
0x180355e02  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180355e08  mov     rdi, rax
0x180355e0b  mov     [rsp+1C8h+var_B0], rax
0x180355e13  xor     eax, eax
0x180355e15  test    rdi, rdi
0x180355e18  jz      short loc_180355E43
0x180355e1a  mov     rcx, r15
0x180355e1d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180355e23  movsxd  rcx, ebx
0x180355e26  add     rax, 2
0x180355e2a  lea     rdx, [rax+rcx*2]
0x180355e2e  mov     rcx, rdi
0x180355e31  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180355e37  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180355e3e  mov     [rdi], rax
0x180355e41  jmp     short loc_180355E46
0x180355e43  mov     rdi, rax
0x180355e46  mov     rdx, rdi
0x180355e49  lea     rcx, [rsp+1C8h+var_138]
0x180355e51  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180355e57  nop
0x180355e58  lea     rdx, [rsp+1C8h+var_138]
0x180355e60  lea     rcx, [rsp+1C8h+var_158]
0x180355e65  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180355e6b  nop
0x180355e6c  lea     rcx, [rsp+1C8h+var_138]
0x180355e74  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180355e7a  test    r12, r12
0x180355e7d  jz      loc_18035661E
0x180355e83  call    cs:__imp_GetLastError
0x180355e89  mov     edi, eax
0x180355e8b  call    cs:__imp_CurrentIP
0x180355e91  mov     rbx, rax
0x180355e94  mov     r9, r12
0x180355e97  lea     r8, aSpcreateregist_0; "SPCreateRegistry"
0x180355e9e  lea     rdx, aHsLoadHiveS; "%hs: Load hive %s"
0x180355ea5  mov     ecx, 4000000h; unsigned int
0x180355eaa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180355eaf  xor     ecx, ecx
0x180355eb1  mov     [rsp+1C8h+var_178], ecx
0x180355eb5  mov     [rsp+1C8h+var_180], rcx
0x180355eba  mov     dword ptr [rsp+1C8h+lpdwDisposition], edi
0x180355ebe  mov     [rsp+1C8h+var_190], rbx
0x180355ec3  lea     rcx, aSpcreateregist; "SPCreateRegistry"
0x180355eca  mov     [rsp+1C8h+lpSecurityAttributes], rcx
0x180355ecf  lea     rcx, aBaseNtsetupSet_50; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180355ed6  mov     [rsp+1C8h+lpcbData], rcx
0x180355edb  mov     dword ptr [rsp+1C8h+phkResult], 219h
0x180355ee3  xor     r9d, r9d
0x180355ee6  lea     r8, aD_0; "D"
0x180355eed  xor     edx, edx
0x180355eef  mov     rcx, rax
0x180355ef2  call    cs:__imp_WdsSetupLogMessageW
0x180355ef8  mov     rcx, [rsp+1C8h+var_108]
0x180355f00  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180355f06  mov     r8, r13; unsigned __int16 *
0x180355f09  mov     rdx, r12; unsigned __int16 *
0x180355f0c  mov     rcx, rax; unsigned __int16 *
0x180355f0f  call    ?SPMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z; SPMountOfflineHive(ushort const *,ushort const *,ushort const *)
0x180355f14  mov     rdi, rax
0x180355f17  mov     [rsp+1C8h+var_140], rax
0x180355f1f  xor     r13d, r13d
0x180355f22  test    rax, rax
0x180355f25  jz      loc_180356473
0x180355f2b  movups  xmm0, xmmword ptr cs:aCurrentcontrol; "CurrentControlSet"
0x180355f32  movups  [rsp+1C8h+var_68], xmm0
0x180355f3a  movups  xmm1, xmmword ptr cs:aCurrentcontrol+10h; "ontrolSet"
0x180355f41  movups  [rsp+1C8h+var_58], xmm1
0x180355f49  mov     eax, dword ptr cs:aCurrentcontrol+20h; "t"
0x180355f4f  mov     [rsp+1C8h+var_48], eax
0x180355f56  mov     r8d, r14d
0x180355f59  lea     rdx, aSystem; "SYSTEM"
0x180355f60  mov     rcx, r12
0x180355f63  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x180355f69  test    eax, eax
0x180355f6b  jnz     loc_18035600F
0x180355f71  lea     rcx, [rsp+1C8h+var_158]
0x180355f76  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180355f7c  mov     r8d, r14d
0x180355f7f  lea     rdx, [rsp+1C8h+var_68]
0x180355f87  mov     rcx, rax
0x180355f8a  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180355f90  test    eax, eax
0x180355f92  jz      short loc_18035600F
0x180355f94  lea     r8, aCurrent_0; "Current"
0x180355f9b  lea     rdx, aSelect; "Select"
0x180355fa2  mov     rcx, rdi
0x180355fa5  call    RegGetDword
0x180355faa  mov     ebx, eax
0x180355fac  test    eax, eax
0x180355fae  jz      loc_18035654B
0x180355fb4  lea     rcx, [rsp+1C8h+var_158]
0x180355fb9  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180355fbf  mov     rcx, rax
0x180355fc2  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180355fc8  lea     r8, [rax+22h]
0x180355fcc  mov     edx, ebx
0x180355fce  lea     rcx, aControlset03uS; "ControlSet%03u%s"
0x180355fd5  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180355fdb  mov     rdx, rax
0x180355fde  lea     rcx, [rsp+1C8h+var_138]
0x180355fe6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180355fec  nop
0x180355fed  lea     rdx, [rsp+1C8h+var_138]
0x180355ff5  lea     rcx, [rsp+1C8h+var_158]
0x180355ffa  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180356000  nop
0x180356001  lea     rcx, [rsp+1C8h+var_138]
0x180356009  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18035600f  mov     r13, [rsp+1C8h+lpData]
0x180356017  call    cs:__imp_GetLastError
0x18035601d  mov     ebx, eax
0x18035601f  call    cs:__imp_CurrentIP
0x180356025  mov     r12, rax
  ... truncated ...
```
