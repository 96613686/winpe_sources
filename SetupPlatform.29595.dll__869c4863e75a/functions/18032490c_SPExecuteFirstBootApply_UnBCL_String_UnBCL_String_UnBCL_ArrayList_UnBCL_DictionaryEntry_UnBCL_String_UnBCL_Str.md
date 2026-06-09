# SPExecuteFirstBootApply(UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *> *,SetupPlatform::SP_MIG_SCOPE,UnBCL::String *,int,int,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<CWIMBootData *> *,UnBCL::String *,int,int *,ISPTelemetryData * *,ISPMigProgress *,long *)

- ea: `0x18032490c`
- end: `0x180325405`
- name: `?SPExecuteFirstBootApply@@YA?AW4MIGSTATUS@@PEAVString@UnBCL@@0PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@3@W4SP_MIG_SCOPE@SetupPlatform@@0HH00000000PEAV?$ArrayList@PEAVCWIMBootData@@@3@0HPEAHPEAPEAUISPTelemetryData@@PEAUISPMigProgress@@PEAJ@Z`
- size: `2809`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, struct UnBCL::String *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801efeb0`
- `0x1801f65a0`
- `0x18020f27c`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x18005dd24`
- `0x18005dd8c`
- `0x18010f64c`
- `0x1803012ec`
- `0x18030158c`
- `0x180302f18`
- `0x18032490c`
- `0x180337d2c`
- `0x18033e844`
- `0x1803404d8`
- `0x18044fd18`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180324a51`
- `ADVAPI32!RegCloseKey` at `0x180324b11`
- `ADVAPI32!RegCloseKey` at `0x18032524f`
- `ADVAPI32!RegCloseKey` at `0x180324a51`
- `ADVAPI32!RegCloseKey` at `0x180324b11`
- `ADVAPI32!RegCloseKey` at `0x18032524f`
- `ADVAPI32!RegSetValueExW` at `0x180324b05`
- `ADVAPI32!RegSetValueExW` at `0x180324b05`
- `ADVAPI32!RegCreateKeyExW` at `0x180324ad9`
- `ADVAPI32!RegCreateKeyExW` at `0x180324ad9`
- `ADVAPI32!RegOpenKeyExW` at `0x180324a1b`
- `ADVAPI32!RegOpenKeyExW` at `0x18032522c`
- `ADVAPI32!RegOpenKeyExW` at `0x180324a1b`
- `ADVAPI32!RegOpenKeyExW` at `0x18032522c`
- `ADVAPI32!RegQueryValueExW` at `0x180324a45`
- `ADVAPI32!RegQueryValueExW` at `0x180324a45`
- `ADVAPI32!RegDeleteValueW` at `0x180325243`
- `ADVAPI32!RegDeleteValueW` at `0x180325243`
- `KERNEL32!GetLastError` at `0x180324966`
- `KERNEL32!GetLastError` at `0x180324b2f`
- `KERNEL32!GetLastError` at `0x180324b40`
- `KERNEL32!GetLastError` at `0x180324bd9`
- `KERNEL32!GetLastError` at `0x180324f45`
- `KERNEL32!GetLastError` at `0x180324fd1`
- `KERNEL32!GetLastError` at `0x180325043`
- `KERNEL32!GetLastError` at `0x18032515f`
- `KERNEL32!GetLastError` at `0x18032525d`
- `KERNEL32!GetLastError` at `0x180324966`
- `KERNEL32!GetLastError` at `0x180324b2f`
- `KERNEL32!GetLastError` at `0x180324b40`
- `KERNEL32!GetLastError` at `0x180324bd9`
- `KERNEL32!GetLastError` at `0x180324f45`
- `KERNEL32!GetLastError` at `0x180324fd1`
- `KERNEL32!GetLastError` at `0x180325043`
- `KERNEL32!GetLastError` at `0x18032515f`
- `KERNEL32!GetLastError` at `0x18032525d`
- `KERNEL32!SetLastError` at `0x180324a59`
- `KERNEL32!SetLastError` at `0x180324a8a`
- `KERNEL32!SetLastError` at `0x180324b19`
- `KERNEL32!SetLastError` at `0x180325257`
- `KERNEL32!SetLastError` at `0x180324a59`
- `KERNEL32!SetLastError` at `0x180324a8a`
- `KERNEL32!SetLastError` at `0x180324b19`
- `KERNEL32!SetLastError` at `0x180325257`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180324d20`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180324d66`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180324d20`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180324d66`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324db7`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324db7`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180324c75`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180324c75`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180324c82`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180324c82`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x180324c8d`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x180324c8d`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1803250fa`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1803250fa`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1803250c6`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1803250c6`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18032531b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180325374`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803253cd`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18032531b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180325374`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803253cd`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180324c5f`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180324c5f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180324d90`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180324d90`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180324cfc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180324d49`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180324cfc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180324d49`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180324cbb`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180324cbb`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180324cd8`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180324cd8`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180324ce7`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180324ce7`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324cf2`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324f2c`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324cf2`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180324f2c`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180324c45`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180324c45`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180324dea`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180324dea`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180324de0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180324f21`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180324de0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180324f21`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180324dc8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180324f0a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180324dc8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180324f0a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180324a68`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180324ca1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803252ff`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180325358`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803253b1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180324a68`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180324ca1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803252ff`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180325358`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803253b1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18032497a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18032497a`
- `unbcl!?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z` at `0x180324dd5`
- `unbcl!?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z` at `0x180324f16`
- `unbcl!?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z` at `0x180324dd5`
- `unbcl!?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z` at `0x180324f16`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803249e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180324bad`
- `WDSCORE!WdsSetupLogMessageW` at `0x180324faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180325031`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803250a3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803251cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803252c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803249e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180324bad`
- `WDSCORE!WdsSetupLogMessageW` at `0x180324faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180325031`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803250a3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803251cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803252c7`
- `WDSCORE!CurrentIP` at `0x18032496e`
- `WDSCORE!CurrentIP` at `0x180324b37`
- `WDSCORE!CurrentIP` at `0x180324be1`
- `WDSCORE!CurrentIP` at `0x180324f4d`
- `WDSCORE!CurrentIP` at `0x180324fd9`
- `WDSCORE!CurrentIP` at `0x18032504b`
- `WDSCORE!CurrentIP` at `0x180325167`
- `WDSCORE!CurrentIP` at `0x180325265`
- `WDSCORE!CurrentIP` at `0x18032496e`
- `WDSCORE!CurrentIP` at `0x180324b37`
- `WDSCORE!CurrentIP` at `0x180324be1`
- `WDSCORE!CurrentIP` at `0x180324f4d`
- `WDSCORE!CurrentIP` at `0x180324fd9`
- `WDSCORE!CurrentIP` at `0x18032504b`
- `WDSCORE!CurrentIP` at `0x180325167`
- `WDSCORE!CurrentIP` at `0x180325265`

## string_xrefs

- `0x180324fe2`: `Failed to reinstall .NET Framework`
- `0x180325054`: `.NET reinstallation succeeded`
- `0x180324dbd`: `MIG_UPGRADE_STORE_PATH`
- `0x180324eff`: `MIG_UPGRADE_STORE_PATH`
- `0x180324f56`: `Executing .NET reinstallation`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall SPExecuteFirstBootApply(
        __int64 a1,
        UnBCL::String *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        struct UnBCL::String *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        const struct UnBCL::String *a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        int a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22)
{
  unsigned int v22; // r14d
  const struct UnBCL::String *v25; // r15
  __int64 v26; // r13
  DWORD LastError; // edi
  __int64 v28; // rbx
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v30; // rax
  LSTATUS Value; // ebx
  CSPTelemetryData *v32; // rax
  CSPTelemetryData *v33; // rax
  LSTATUS v34; // ebx
  DWORD v35; // edi
  __int64 v36; // rbx
  DWORD v37; // eax
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v40; // edi
  __int64 v41; // rbx
  struct tagLOG_PARTIAL_MSG *v42; // rax
  const struct UnBCL::String *v43; // rsi
  __int64 Files; // rax
  HKEY v45; // rax
  HKEY v46; // rbx
  __int64 v47; // rax
  int i; // r14d
  __int64 v49; // rax
  int (__fastcall ***v50)(_QWORD); // rcx
  __int64 v51; // rax
  __int64 v52; // rdi
  void (__fastcall *v53)(__int64, struct UnBCL::String *); // rbx
  __int64 v54; // rax
  __int64 v55; // rcx
  const struct UnBCL::String **v56; // rax
  struct UnBCL::String *v57; // rax
  const struct UnBCL::String *v58; // rax
  __int64 P; // rax
  LSTATUS v60; // ebx
  DWORD v61; // edi
  __int64 v62; // rbx
  struct tagLOG_PARTIAL_MSG *v63; // rax
  UnBCL::ArgumentNullException *v64; // rax
  UnBCL::ArgumentNullException *v65; // rbx
  UnBCL::ArgumentNullException *v66; // rax
  UnBCL::ArgumentNullException *v67; // rbx
  UnBCL::ArgumentNullException *v68; // rax
  UnBCL::ArgumentNullException *v69; // rbx
  HKEY v70; // [rsp+E8h] [rbp-80h] BYREF
  HKEY hKey[2]; // [rsp+F8h] [rbp-70h] BYREF
  __int64 v72; // [rsp+108h] [rbp-60h] BYREF
  _QWORD v73[2]; // [rsp+118h] [rbp-50h] BYREF
  _BYTE v74[24]; // [rsp+128h] [rbp-40h] BYREF
  __int64 v75; // [rsp+140h] [rbp-28h]
  HKEY dwDisposition; // [rsp+1A0h] [rbp+38h] BYREF
  __int64 v78; // [rsp+1A8h] [rbp+40h]
  unsigned int v79; // [rsp+1B0h] [rbp+48h]

  v79 = a4;
  v78 = a3;
  v75 = -2;
  v22 = a4;
  if ( !a2 )
  {
    v66 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v67 = v66;
    v70 = (HKEY)v66;
    if ( v66 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v66, L"WindowsOldWinDir");
      *(_QWORD *)v67 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v67 = 0;
    }
    dwDisposition = (HKEY)AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v67,
                            "enum MIGSTATUS __cdecl SPExecuteFirstBootApply(class UnBCL::String *,class UnBCL::String *,c"
                            "lass UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String"
                            " *> *> *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,int,int,class UnBCL::String "
                            "*,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,cl"
                            "ass UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class"
                            " CWIMBootData *> *,class UnBCL::String *,int,int *,struct ISPTelemetryData **,struct ISPMigP"
                            "rogress *,long *)");
    throw (UnBCL::ArgumentNullException **)&dwDisposition;
  }
  v25 = a8;
  if ( !a8 )
  {
    v68 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v69 = v68;
    v70 = (HKEY)v68;
    if ( v68 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v68, L"StoreDir");
      *(_QWORD *)v69 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v69 = 0;
    }
    dwDisposition = (HKEY)AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v69,
                            "enum MIGSTATUS __cdecl SPExecuteFirstBootApply(class UnBCL::String *,class UnBCL::String *,c"
                            "lass UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String"
                            " *> *> *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,int,int,class UnBCL::String "
                            "*,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,cl"
                            "ass UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class"
                            " CWIMBootData *> *,class UnBCL::String *,int,int *,struct ISPTelemetryData **,struct ISPMigP"
                            "rogress *,long *)");
    throw (UnBCL::ArgumentNullException **)&dwDisposition;
  }
  v26 = a9;
  if ( !a9 )
  {
    v64 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v65 = v64;
    v70 = (HKEY)v64;
    if ( v64 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v64, L"WorkDir");
      *(_QWORD *)v65 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v65 = 0;
    }
    dwDisposition = (HKEY)AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v65,
                            "enum MIGSTATUS __cdecl SPExecuteFirstBootApply(class UnBCL::String *,class UnBCL::String *,c"
                            "lass UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String"
                            " *> *> *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,int,int,class UnBCL::String "
                            "*,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,cl"
                            "ass UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class"
                            " CWIMBootData *> *,class UnBCL::String *,int,int *,struct ISPTelemetryData **,struct ISPMigP"
                            "rogress *,long *)");
    throw (UnBCL::ArgumentNullException **)&dwDisposition;
  }
  LastError = GetLastError();
  v28 = CurrentIP();
  CString = (const char *)UnBCL::String::get_CString(a2);
  v30 = ConstructPartialMsgW(0x4000000u, "%hs: Begin run. WinOld: %s", "SPExecuteFirstBootApply", CString);
  WdsSetupLogMessageW(
    v30,
    819200,
    L"D",
    0,
    10591,
    L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
    L"SPExecuteFirstBootApply",
    v28,
    LastError,
    0,
    0);
  LODWORD(dwDisposition) = 0;
  if ( a1 )
    goto LABEL_8;
  hKey[0] = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, hKey) || !hKey[0] )
  {
    SetLastError(0);
  }
  else
  {
    Value = RegQueryValueExW(hKey[0], L"Upgrade", 0, 0, 0, 0);
    RegCloseKey(hKey[0]);
    SetLastError(0);
    if ( !Value )
      goto LABEL_8;
  }
  LODWORD(hKey[0]) = 1;
  v70 = 0;
  LODWORD(dwDisposition) = 0;
  v34 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\Setup",
          0,
          (LPWSTR)&Class,
          0,
          0x20006u,
          0,
          &v70,
          (LPDWORD)&dwDisposition);
  if ( !v34 )
  {
    v34 = RegSetValueExW(v70, L"Upgrade", 0, 4u, (const BYTE *)hKey, 4u);
    RegCloseKey(v70);
  }
  SetLastError(v34);
  if ( v34 )
  {
    v35 = GetLastError();
    v36 = CurrentIP();
    v37 = GetLastError();
    v38 = ConstructPartialMsgW(
            0x2000000u,
            "%hs: Cannot set upgrade value. Error: 0x%08X",
            "SPExecuteFirstBootApply",
            v37);
    WdsSetupLogMessageW(
      v38,
      819200,
      L"D",
      0,
      10604,
      L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
      L"SPExecuteFirstBootApply",
      v36,
      v35,
      0,
      0);
    return 7;
  }
  LODWORD(dwDisposition) = 1;
LABEL_8:
  v32 = (CSPTelemetryData *)UnBCL::Object::operator new(0x80u);
  v70 = (HKEY)v32;
  if ( v32 )
    v33 = CSPTelemetryData::CSPTelemetryData(v32);
  else
    v33 = 0;
  UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(v73, v33);
  if ( (unsigned int)pSPRestoreEnvVars(v25) )
  {
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(hKey);
    v43 = a12;
    if ( a12 && UnBCL::Directory::Exists(a12) )
    {
      Files = UnBCL::Directory::GetFiles(v43, 0, 0);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(&v72, Files);
      if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(&v72) )
      {
        v45 = (HKEY)UnBCL::Object::operator new(0xB0u);
        v46 = v45;
        v70 = v45;
        if ( v45 )
        {
          UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v45, 1);
          *((_QWORD *)v46 + 6) = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
        }
        else
        {
          v46 = 0;
        }
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v74, v46);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(hKey, v74);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v74);
        v47 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(hKey);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 40LL))(v47, 1);
        for ( i = 0; ; ++i )
        {
          v49 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(&v72);
          v50 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v49 + 8) + 12LL) + v49 + 8);
          if ( i >= (**v50)(v50) )
            break;
          v51 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(hKey);
          v52 = v51 + *(int *)(*(_QWORD *)(v51 + 8) + 16LL);
          v53 = *(void (__fastcall **)(__int64, struct UnBCL::String *))(*(_QWORD *)(v52 + 8) + 40LL);
          v54 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(&v72);
          v55 = *(int *)(*(_QWORD *)(v54 + 8) + 16LL) + v54 + 8;
          v56 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v55 + 24LL))(
                                                 v55,
                                                 (unsigned int)i);
          v57 = UnBCL::Path::Combine(v43, *v56);
          v53(v52 + 8, v57);
        }
        v22 = v79;
      }
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(&v72);
    }
    v58 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v74, L"MIG_UPGRADE_STORE_PATH");
    UnBCL::Environment::SetEnvironmentVar(v58, v25);
    UnBCL::String::~String((UnBCL::String *)v74);
    P = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(hKey);
    pSPExecuteApply(
      v22,
      0,
      a5,
      1,
      1,
      a18 == 0,
      a6,
      a7,
      P,
      a1,
      a2,
      v78,
      v25,
      0,
      0,
      v26,
      a11,
      a13,
      a14,
      a15,
      a10,
      a16,
      a17,
      a19,
      v73[1],
      a21,
      a22);
  }
  v40 = GetLastError();
  v41 = CurrentIP();
  v42 = ConstructPartialMsgW(0x2000000u, "%hs: Cannot restore control environment variables", "SPExecuteFirstBootApply");
  WdsSetupLogMessageW(
    v42,
    819200,
    L"D",
    0,
    10620,
    L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
    L"SPExecuteFirstBootApply",
    v41,
    v40,
    0,
    0);
  if ( (_DWORD)dwDisposition )
  {
    dwDisposition = 0;
    v60 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20006u, &dwDisposition);
    if ( !v60 )
    {
      v60 = RegDeleteValueW(dwDisposition, L"Upgrade");
      RegCloseKey(dwDisposition);
    }
    SetLastError(v60);
  }
  v61 = GetLastError();
  v62 = CurrentIP();
  v63 = ConstructPartialMsgW(0x4000000u, "%hs: End run. Result: 0x%08X", "SPExecuteFirstBootApply", 5);
  WdsSetupLogMessageW(
    v63,
    819200,
    L"D",
    0,
    10731,
    L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
    L"SPExecuteFirstBootApply",
    v62,
    v61,
    0,
    0);
  v73[0] = &UnBCL::SmartPtr<CSPTelemetryData>::`vftable';
  UnBCL::SmartPtr<COperationsProgress>::DeAssign(v73);
  return 5;
}

```

## disassembly

```asm
0x18032490c  mov     rax, rsp
0x18032490f  mov     [rax+20h], r9d
0x180324913  mov     [rax+18h], r8
0x180324917  mov     [rax+8], rcx
0x18032491b  push    rbp
0x18032491c  push    rbx
0x18032491d  push    rsi
0x18032491e  push    rdi
0x18032491f  push    r12
0x180324921  push    r13
0x180324923  push    r14
0x180324925  push    r15
0x180324927  lea     rbp, [rax-28h]
0x18032492b  sub     rsp, 148h
0x180324932  mov     [rbp+20h+var_48], 0FFFFFFFFFFFFFFFEh
0x18032493a  mov     r14d, r9d
0x18032493d  mov     r12, rdx
0x180324940  mov     rsi, rcx
0x180324943  test    rdx, rdx
0x180324946  jz      loc_180325353
0x18032494c  mov     r15, [rbp+20h+arg_38]
0x180324950  test    r15, r15
0x180324953  jz      loc_1803253AC
0x180324959  mov     r13, [rbp+20h+arg_40]
0x18032495d  test    r13, r13
0x180324960  jz      loc_1803252FA
0x180324966  call    cs:__imp_GetLastError
0x18032496c  mov     edi, eax
0x18032496e  call    cs:__imp_CurrentIP
0x180324974  mov     rbx, rax
0x180324977  mov     rcx, r12
0x18032497a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180324980  mov     r9, rax
0x180324983  lea     r8, aSpexecutefirst_1; "SPExecuteFirstBootApply"
0x18032498a  lea     rdx, aHsBeginRunWino; "%hs: Begin run. WinOld: %s"
0x180324991  mov     ecx, 4000000h; unsigned int
0x180324996  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18032499b  mov     dword ptr [rsp+180h+var_130], 0
0x1803249a3  mov     [rsp+180h+var_138], 0
0x1803249ac  mov     dword ptr [rsp+180h+lpdwDisposition], edi
0x1803249b0  mov     [rsp+180h+var_148], rbx
0x1803249b5  lea     rcx, aSpexecutefirst_2; "SPExecuteFirstBootApply"
0x1803249bc  mov     [rsp+180h+lpSecurityAttributes], rcx
0x1803249c1  lea     rcx, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1803249c8  mov     [rsp+180h+lpcbData], rcx
0x1803249cd  mov     dword ptr [rsp+180h+phkResult], 295Fh
0x1803249d5  xor     r9d, r9d
0x1803249d8  lea     r8, aD_0; "D"
0x1803249df  mov     edx, 0C8000h
0x1803249e4  mov     rcx, rax
0x1803249e7  call    cs:__imp_WdsSetupLogMessageW
0x1803249ed  xor     edi, edi
0x1803249ef  mov     dword ptr [rbp+20h+dwDisposition], edi
0x1803249f2  test    rsi, rsi
0x1803249f5  jnz     short loc_180324A63
0x1803249f7  mov     [rbp+20h+hKey], rdi
0x1803249fb  lea     rax, [rbp+20h+hKey]
0x1803249ff  mov     [rsp+180h+phkResult], rax; phkResult
0x180324a04  mov     r9d, 20019h; samDesired
0x180324a0a  xor     r8d, r8d; ulOptions
0x180324a0d  lea     rdx, aSystemSetup_0; "SYSTEM\\Setup"
0x180324a14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180324a1b  call    cs:__imp_RegOpenKeyExW
0x180324a21  test    eax, eax
0x180324a23  jnz     short loc_180324A88
0x180324a25  mov     rcx, [rbp+20h+hKey]; hKey
0x180324a29  test    rcx, rcx
0x180324a2c  jz      short loc_180324A88
0x180324a2e  mov     [rsp+180h+lpcbData], rdi; lpcbData
0x180324a33  mov     [rsp+180h+phkResult], rdi; lpData
0x180324a38  xor     r9d, r9d; lpType
0x180324a3b  xor     r8d, r8d; lpReserved
0x180324a3e  lea     rdx, aUpgrade; "Upgrade"
0x180324a45  call    cs:__imp_RegQueryValueExW
0x180324a4b  mov     ebx, eax
0x180324a4d  mov     rcx, [rbp+20h+hKey]; hKey
0x180324a51  call    cs:__imp_RegCloseKey
0x180324a57  xor     ecx, ecx; dwErrCode
0x180324a59  call    cs:__imp_SetLastError
0x180324a5f  test    ebx, ebx
0x180324a61  jnz     short loc_180324A90
0x180324a63  mov     ecx, 80h
0x180324a68  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180324a6e  mov     [rbp+20h+var_A0], rax
0x180324a72  test    rax, rax
0x180324a75  jz      loc_180324BBD
0x180324a7b  mov     rcx, rax; this
0x180324a7e  call    ??0CSPTelemetryData@@QEAA@XZ; CSPTelemetryData::CSPTelemetryData(void)
0x180324a83  jmp     loc_180324BC0
0x180324a88  xor     ecx, ecx; dwErrCode
0x180324a8a  call    cs:__imp_SetLastError
0x180324a90  mov     dword ptr [rbp+20h+hKey], 1
0x180324a97  mov     [rbp+20h+var_A0], rdi
0x180324a9b  mov     dword ptr [rbp+20h+dwDisposition], edi
0x180324a9e  lea     rax, [rbp+20h+dwDisposition]
0x180324aa2  mov     [rsp+180h+lpdwDisposition], rax; lpdwDisposition
0x180324aa7  lea     rax, [rbp+20h+var_A0]
0x180324aab  mov     [rsp+180h+var_148], rax; phkResult
0x180324ab0  mov     [rsp+180h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180324ab5  mov     dword ptr [rsp+180h+lpcbData], 20006h; samDesired
0x180324abd  mov     dword ptr [rsp+180h+phkResult], edi; dwOptions
0x180324ac1  lea     r9, Class; lpClass
0x180324ac8  xor     r8d, r8d; Reserved
0x180324acb  lea     rdx, aSystemSetup_0; "SYSTEM\\Setup"
0x180324ad2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180324ad9  call    cs:__imp_RegCreateKeyExW
0x180324adf  mov     ebx, eax
0x180324ae1  test    eax, eax
0x180324ae3  jnz     short loc_180324B17
0x180324ae5  lea     r9d, [rax+4]; dwType
0x180324ae9  mov     dword ptr [rsp+180h+lpcbData], r9d; cbData
0x180324aee  lea     rax, [rbp+20h+hKey]
0x180324af2  mov     [rsp+180h+phkResult], rax; lpData
0x180324af7  xor     r8d, r8d; Reserved
0x180324afa  lea     rdx, aUpgrade; "Upgrade"
0x180324b01  mov     rcx, [rbp+20h+var_A0]; hKey
0x180324b05  call    cs:__imp_RegSetValueExW
0x180324b0b  mov     ebx, eax
0x180324b0d  mov     rcx, [rbp+20h+var_A0]; hKey
0x180324b11  call    cs:__imp_RegCloseKey
0x180324b17  mov     ecx, ebx; dwErrCode
0x180324b19  call    cs:__imp_SetLastError
0x180324b1f  test    ebx, ebx
0x180324b21  jnz     short loc_180324B2F
0x180324b23  mov     dword ptr [rbp+20h+dwDisposition], 1
0x180324b2a  jmp     loc_180324A63
0x180324b2f  call    cs:__imp_GetLastError
0x180324b35  mov     edi, eax
0x180324b37  call    cs:__imp_CurrentIP
0x180324b3d  mov     rbx, rax
0x180324b40  call    cs:__imp_GetLastError
0x180324b46  mov     r9d, eax
0x180324b49  lea     r8, aSpexecutefirst_1; "SPExecuteFirstBootApply"
0x180324b50  lea     rdx, aHsCannotSetUpg; "%hs: Cannot set upgrade value. Error: 0"...
0x180324b57  mov     ecx, 2000000h; unsigned int
0x180324b5c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180324b61  mov     dword ptr [rsp+180h+var_130], 0
0x180324b69  mov     [rsp+180h+var_138], 0
0x180324b72  mov     dword ptr [rsp+180h+lpdwDisposition], edi
0x180324b76  mov     [rsp+180h+var_148], rbx
0x180324b7b  lea     rcx, aSpexecutefirst_2; "SPExecuteFirstBootApply"
0x180324b82  mov     [rsp+180h+lpSecurityAttributes], rcx
0x180324b87  lea     rcx, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180324b8e  mov     [rsp+180h+lpcbData], rcx
0x180324b93  mov     dword ptr [rsp+180h+phkResult], 296Ch
0x180324b9b  xor     r9d, r9d
0x180324b9e  lea     r8, aD_0; "D"
0x180324ba5  mov     edx, 0C8000h
0x180324baa  mov     rcx, rax
0x180324bad  call    cs:__imp_WdsSetupLogMessageW
0x180324bb3  mov     eax, 7
0x180324bb8  jmp     loc_1803252E6
0x180324bbd  mov     rax, rdi
0x180324bc0  mov     rdx, rax
0x180324bc3  lea     rcx, [rbp+20h+var_70]
0x180324bc7  call    ??0?$SmartPtr@VCSPTelemetryData@@@UnBCL@@QEAA@PEAVCSPTelemetryData@@@Z; UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(CSPTelemetryData *)
0x180324bcc  nop
0x180324bcd  mov     rcx, r15; struct UnBCL::String *
0x180324bd0  call    ?pSPRestoreEnvVars@@YAHPEAVString@UnBCL@@@Z; pSPRestoreEnvVars(UnBCL::String *)
0x180324bd5  test    eax, eax
0x180324bd7  jnz     short loc_180324C41
0x180324bd9  call    cs:__imp_GetLastError
0x180324bdf  mov     edi, eax
0x180324be1  call    cs:__imp_CurrentIP
0x180324be7  mov     rbx, rax
0x180324bea  lea     r8, aSpexecutefirst_1; "SPExecuteFirstBootApply"
0x180324bf1  lea     rdx, aHsCannotRestor; "%hs: Cannot restore control environment"...
0x180324bf8  mov     ecx, 2000000h; unsigned int
0x180324bfd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180324c02  mov     dword ptr [rsp+180h+var_130], 0
0x180324c0a  mov     [rsp+180h+var_138], 0
0x180324c13  mov     dword ptr [rsp+180h+lpdwDisposition], edi
0x180324c17  mov     [rsp+180h+var_148], rbx
0x180324c1c  lea     r13, aSpexecutefirst_2; "SPExecuteFirstBootApply"
0x180324c23  mov     [rsp+180h+lpSecurityAttributes], r13
0x180324c28  lea     rsi, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180324c2f  mov     [rsp+180h+lpcbData], rsi
0x180324c34  mov     dword ptr [rsp+180h+phkResult], 297Ch
0x180324c3c  jmp     loc_1803251BB
0x180324c41  lea     rcx, [rbp+20h+hKey]
0x180324c45  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180324c4b  nop
0x180324c4c  mov     rsi, [rbp+20h+arg_58]
0x180324c53  test    rsi, rsi
0x180324c56  jz      loc_180324DBD
0x180324c5c  mov     rcx, rsi
0x180324c5f  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180324c65  test    eax, eax
0x180324c67  jz      loc_180324DBD
0x180324c6d  xor     r8d, r8d
0x180324c70  xor     edx, edx
0x180324c72  mov     rcx, rsi
0x180324c75  call    cs:__imp_?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z; UnBCL::Directory::GetFiles(UnBCL::String const *,UnBCL::String const *,int)
0x180324c7b  mov     rdx, rax
0x180324c7e  lea     rcx, [rbp+20h+var_80]
0x180324c82  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x180324c88  nop
0x180324c89  lea     rcx, [rbp+20h+var_80]
0x180324c8d  call    cs:__imp_?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(void)
0x180324c93  test    rax, rax
0x180324c96  jz      loc_180324DB3
0x180324c9c  mov     ecx, 0B0h
0x180324ca1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180324ca7  mov     rbx, rax
0x180324caa  mov     [rbp+20h+var_A0], rax
0x180324cae  test    rax, rax
0x180324cb1  jz      short loc_180324CCE
0x180324cb3  mov     edx, 1
0x180324cb8  mov     rcx, rax
0x180324cbb  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x180324cc1  lea     rax, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x180324cc8  mov     [rbx+30h], rax
0x180324ccc  jmp     short loc_180324CD1
0x180324cce  mov     rbx, rdi
0x180324cd1  mov     rdx, rbx
0x180324cd4  lea     rcx, [rbp+20h+var_60]
0x180324cd8  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x180324cde  nop
0x180324cdf  lea     rdx, [rbp+20h+var_60]
0x180324ce3  lea     rcx, [rbp+20h+hKey]
0x180324ce7  call    cs:__imp_??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> const &)
0x180324ced  nop
0x180324cee  lea     rcx, [rbp+20h+var_60]
0x180324cf2  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180324cf8  lea     rcx, [rbp+20h+hKey]
0x180324cfc  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180324d02  mov     r8, rax
0x180324d05  mov     rcx, [rax]
0x180324d08  mov     rax, [rcx+28h]
0x180324d0c  mov     edx, 1
0x180324d11  mov     rcx, r8
0x180324d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180324d19  mov     r14d, edi
0x180324d1c  lea     rcx, [rbp+20h+var_80]
0x180324d20  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x180324d26  mov     rcx, [rax+8]
0x180324d2a  movsxd  rdx, dword ptr [rcx+0Ch]
0x180324d2e  lea     rcx, [rax+8]
0x180324d32  add     rcx, rdx
0x180324d35  mov     rax, [rcx]
0x180324d38  mov     rax, [rax]
0x180324d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180324d40  cmp     r14d, eax
0x180324d43  jge     short loc_180324DAD
0x180324d45  lea     rcx, [rbp+20h+hKey]
0x180324d49  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180324d4f  mov     rcx, [rax+8]
0x180324d53  movsxd  rdi, dword ptr [rcx+10h]
0x180324d57  add     rdi, rax
0x180324d5a  mov     rax, [rdi+8]
0x180324d5e  mov     rbx, [rax+28h]
0x180324d62  lea     rcx, [rbp+20h+var_80]
0x180324d66  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x180324d6c  mov     rcx, [rax+8]
0x180324d70  movsxd  rdx, dword ptr [rcx+10h]
0x180324d74  lea     rcx, [rax+8]
0x180324d78  add     rcx, rdx
0x180324d7b  mov     rax, [rcx]
0x180324d7e  mov     edx, r14d
0x180324d81  mov     rax, [rax+18h]
0x180324d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180324d8a  mov     rdx, [rax]
0x180324d8d  mov     rcx, rsi
0x180324d90  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180324d96  mov     rdx, rax
0x180324d99  lea     rcx, [rdi+8]
0x180324d9d  mov     rax, rbx
0x180324da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180324da5  inc     r14d
0x180324da8  jmp     loc_180324D1C
0x180324dad  mov     r14d, [rbp+20h+arg_18]
0x180324db1  xor     edi, edi
0x180324db3  lea     rcx, [rbp+20h+var_80]
0x180324db7  call    cs:__imp_??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(void)
0x180324dbd  lea     rdx, aMigUpgradeStor; "MIG_UPGRADE_STORE_PATH"
0x180324dc4  lea     rcx, [rbp+20h+var_60]
0x180324dc8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180324dce  nop
0x180324dcf  mov     rdx, r15
0x180324dd2  mov     rcx, rax
0x180324dd5  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180324ddb  nop
0x180324ddc  lea     rcx, [rbp+20h+var_60]
0x180324de0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180324de6  lea     rcx, [rbp+20h+hKey]
0x180324dea  call    cs:__imp_?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(void)
0x180324df0  mov     r8, rax
0x180324df3  mov     r10d, edi
0x180324df6  cmp     [rbp+20h+arg_88], edi
0x180324dfc  setz    r10b
0x180324e00  mov     rcx, [rbp+20h+arg_A8]
0x180324e07  mov     [rsp+0D0h], rcx
0x180324e0f  mov     rsi, [rbp+20h+arg_A0]
0x180324e16  mov     [rsp+180h+var_B8], rsi
0x180324e1e  mov     rax, [rbp+20h+var_68]
0x180324e22  mov     [rsp+180h+var_C0], rax
0x180324e2a  mov     rcx, [rbp+20h+arg_90]
0x180324e31  mov     [rsp+180h+var_C8], rcx
0x180324e39  mov     rcx, [rbp+20h+arg_80]
0x180324e40  mov     [rsp+180h+var_D0], rcx
  ... truncated ...
```
