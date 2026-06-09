# CPITRSettings::QuerySettingDWORD(ushort const *,ulong,PITR::PITR_SETTINGS_LEVEL,PITR::PITR_SETTINGS_LEVEL *)

- ea: `0x1800128b4`
- end: `0x180012bb5`
- name: `?QuerySettingDWORD@CPITRSettings@@IEAAKPEBGKW4PITR_SETTINGS_LEVEL@PITR@@PEAW423@@Z`
- size: `769`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, int, int *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180012650`
- `0x180012740`
- `0x1800127b0`
- `0x1800127e0`
- `0x180012850`
- `0x180012bc0`

## callees

- `0x180009e04`
- `0x18000f50c`
- `0x1800128b4`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800129a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800129a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac7`
- `WDSCORE!CurrentIP` at `0x1800129c8`
- `WDSCORE!CurrentIP` at `0x180012a48`
- `WDSCORE!CurrentIP` at `0x180012acf`
- `WDSCORE!CurrentIP` at `0x1800129c8`
- `WDSCORE!CurrentIP` at `0x180012a48`
- `WDSCORE!CurrentIP` at `0x180012acf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012b4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012b4e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001297e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800129de`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012a61`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012ae8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001297e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800129de`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012a61`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012ae8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012929`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012929`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18001290b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18001290b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180012943`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180012b78`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180012943`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180012b78`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180012938`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180012938`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012975`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800129d5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012a58`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012adf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012975`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800129d5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012a58`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180012adf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001294d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001294d`

## string_xrefs

- `0x180012a21`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180012aa4`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180012b2b`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`

## pseudocode

```c
__int64 __fastcall CPITRSettings::QuerySettingDWORD(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        int *a5)
{
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 SettingValueName; // rax
  UnBCL::String *v11; // rax
  const WCHAR *CString; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // esi
  DWORD LastError; // edi
  __int64 v16; // rbx
  UnBCL::String *v17; // rax
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // esi
  __int64 v21; // rdi
  DWORD v22; // ebx
  UnBCL::String *v23; // rax
  const char *v24; // rax
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // esi
  __int64 v27; // rdi
  DWORD v28; // ebx
  UnBCL::String *v29; // rax
  const char *v30; // rax
  struct tagLOG_PARTIAL_MSG *v31; // rax
  unsigned int v32; // ebx
  _BYTE v35[16]; // [rsp+68h] [rbp-19h] BYREF
  DWORD Type; // [rsp+78h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-5h] BYREF
  BYTE Data[8]; // [rsp+80h] [rbp-1h] BYREF
  _BYTE v39[16]; // [rsp+88h] [rbp+7h] BYREF

  v8 = a1;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v39);
  while ( 1 )
  {
    if ( a4 <= 1 )
    {
      if ( a5 )
        *a5 = 1;
      v32 = a3;
      goto LABEL_16;
    }
    SettingValueName = CPITRSettings::GetSettingValueName(v9, a2, a4);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v35, SettingValueName);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v39, v35);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v35);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v39) )
      break;
LABEL_11:
    --a4;
  }
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v39);
  CString = UnBCL::String::get_CString(v11);
  v13 = RegQueryValueExW(*(HKEY *)(v8 + 32), CString, 0, &Type, Data, &cbData);
  v14 = v13;
  if ( v13 )
  {
    v9 = (unsigned int)(v13 - 2);
    if ( (unsigned int)v9 <= 1 )
      goto LABEL_11;
    LastError = GetLastError();
    v16 = CurrentIP();
    v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v39);
    v18 = (const char *)UnBCL::String::get_CString(v17);
    v19 = ConstructPartialMsgW(0x3000000u, "Failed to retrieve setting %s. Error: 0x%08X", v18, v14);
    WdsSetupLogMessageW(
      v19,
      0,
      L"D",
      0,
      2342,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRSettings::QuerySettingDWORD",
      v16,
      LastError,
      0,
      0);
    goto LABEL_10;
  }
  if ( Type != 4 )
  {
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = Type;
    v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v39);
    v24 = (const char *)UnBCL::String::get_CString(v23);
    v25 = ConstructPartialMsgW(0x3000000u, "Setting %s had unexpected type: %d", v24, v22);
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      2348,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRSettings::QuerySettingDWORD",
      v21,
      v20,
      0,
      0);
LABEL_10:
    v8 = a1;
    goto LABEL_11;
  }
  if ( cbData != 4 )
  {
    v26 = GetLastError();
    v27 = CurrentIP();
    v28 = cbData;
    v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v39);
    v30 = (const char *)UnBCL::String::get_CString(v29);
    v31 = ConstructPartialMsgW(0x3000000u, "Setting %s had unexpected size: %d", v30, v28);
    WdsSetupLogMessageW(
      v31,
      0,
      L"D",
      0,
      2353,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRSettings::QuerySettingDWORD",
      v27,
      v26,
      0,
      0);
    goto LABEL_10;
  }
  if ( a5 )
    *a5 = a4;
  v32 = *(_DWORD *)Data;
LABEL_16:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v39);
  return v32;
}

```

## disassembly

```asm
0x1800128b4  mov     [rsp-8+arg_10], rbx
0x1800128b9  push    rbp
0x1800128ba  push    rsi
0x1800128bb  push    rdi
0x1800128bc  push    r12
0x1800128be  push    r13
0x1800128c0  push    r14
0x1800128c2  push    r15
0x1800128c4  lea     rbp, [rsp-1Fh]
0x1800128c9  sub     rsp, 0A0h
0x1800128d0  mov     rax, cs:__security_cookie
0x1800128d7  xor     rax, rsp
0x1800128da  mov     [rbp+4Fh+var_38], rax
0x1800128de  mov     r14d, r9d
0x1800128e1  mov     r12d, r8d
0x1800128e4  mov     r13, rdx
0x1800128e7  mov     rbx, rcx
0x1800128ea  mov     [rbp+4Fh+var_70], rcx
0x1800128ee  mov     r15, [rbp+4Fh+arg_20]
0x1800128f2  mov     dword ptr [rbp+4Fh+Data], 0
0x1800128f9  mov     [rbp+4Fh+Type], 0
0x180012900  mov     [rbp+4Fh+cbData], 0
0x180012907  lea     rcx, [rbp+4Fh+var_48]
0x18001290b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180012911  nop
0x180012912  jmp     loc_180012B5B
0x180012917  mov     r8d, r14d
0x18001291a  mov     rdx, r13
0x18001291d  call    ?GetSettingValueName@CPITRSettings@@IEAAPEAVString@UnBCL@@PEBGW4PITR_SETTINGS_LEVEL@PITR@@@Z; CPITRSettings::GetSettingValueName(ushort const *,PITR::PITR_SETTINGS_LEVEL)
0x180012922  mov     rdx, rax
0x180012925  lea     rcx, [rbp+4Fh+var_68]
0x180012929  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18001292f  nop
0x180012930  lea     rdx, [rbp+4Fh+var_68]
0x180012934  lea     rcx, [rbp+4Fh+var_48]
0x180012938  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18001293e  nop
0x18001293f  lea     rcx, [rbp+4Fh+var_68]
0x180012943  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180012949  lea     rcx, [rbp+4Fh+var_48]
0x18001294d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012953  test    rax, rax
0x180012956  jz      loc_180012B58
0x18001295c  mov     dword ptr [rbp+4Fh+Data], 0
0x180012963  mov     [rbp+4Fh+Type], 0
0x18001296a  mov     [rbp+4Fh+cbData], 4
0x180012971  lea     rcx, [rbp+4Fh+var_48]
0x180012975  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18001297b  mov     rcx, rax
0x18001297e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180012984  lea     rcx, [rbp+4Fh+cbData]
0x180012988  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18001298d  lea     rcx, [rbp+4Fh+Data]
0x180012991  mov     [rsp+0D0h+lpData], rcx; lpData
0x180012996  lea     r9, [rbp+4Fh+Type]; lpType
0x18001299a  xor     r8d, r8d; lpReserved
0x18001299d  mov     rdx, rax; lpValueName
0x1800129a0  mov     rcx, [rbx+20h]; hKey
0x1800129a4  call    cs:__imp_RegQueryValueExW
0x1800129aa  mov     esi, eax
0x1800129ac  test    eax, eax
0x1800129ae  jz      loc_180012A3A
0x1800129b4  lea     ecx, [rax-2]
0x1800129b7  cmp     ecx, 1
0x1800129ba  jbe     loc_180012B58
0x1800129c0  call    cs:__imp_GetLastError
0x1800129c6  mov     edi, eax
0x1800129c8  call    cs:__imp_CurrentIP
0x1800129ce  mov     rbx, rax
0x1800129d1  lea     rcx, [rbp+4Fh+var_48]
0x1800129d5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800129db  mov     rcx, rax
0x1800129de  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800129e4  mov     r8, rax
0x1800129e7  mov     r9d, esi
0x1800129ea  lea     rdx, aFailedToRetrie_0; "Failed to retrieve setting %s. Error: 0"...
0x1800129f1  mov     ecx, 3000000h; unsigned int
0x1800129f6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800129fb  mov     [rsp+0D0h+var_80], 0
0x180012a03  mov     [rsp+0D0h+var_88], 0
0x180012a0c  mov     [rsp+0D0h+var_90], edi
0x180012a10  mov     [rsp+0D0h+var_98], rbx
0x180012a15  lea     rcx, aCpitrsettingsQ; "CPITRSettings::QuerySettingDWORD"
0x180012a1c  mov     [rsp+0D0h+var_A0], rcx
0x180012a21  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180012a28  mov     [rsp+0D0h+lpcbData], rcx
0x180012a2d  mov     dword ptr [rsp+0D0h+lpData], 926h
0x180012a35  jmp     loc_180012B3F
0x180012a3a  cmp     [rbp+4Fh+Type], 4
0x180012a3e  jz      short loc_180012ABD
0x180012a40  call    cs:__imp_GetLastError
0x180012a46  mov     esi, eax
0x180012a48  call    cs:__imp_CurrentIP
0x180012a4e  mov     rdi, rax
0x180012a51  mov     ebx, [rbp+4Fh+Type]
0x180012a54  lea     rcx, [rbp+4Fh+var_48]
0x180012a58  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180012a5e  mov     rcx, rax
0x180012a61  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180012a67  mov     r9d, ebx
0x180012a6a  mov     r8, rax
0x180012a6d  lea     rdx, aSettingSHadUne_0; "Setting %s had unexpected type: %d"
0x180012a74  mov     ecx, 3000000h; unsigned int
0x180012a79  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012a7e  mov     [rsp+0D0h+var_80], 0
0x180012a86  mov     [rsp+0D0h+var_88], 0
0x180012a8f  mov     [rsp+0D0h+var_90], esi
0x180012a93  mov     [rsp+0D0h+var_98], rdi
0x180012a98  lea     rcx, aCpitrsettingsQ; "CPITRSettings::QuerySettingDWORD"
0x180012a9f  mov     [rsp+0D0h+var_A0], rcx
0x180012aa4  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180012aab  mov     [rsp+0D0h+lpcbData], rcx
0x180012ab0  mov     dword ptr [rsp+0D0h+lpData], 92Ch
0x180012ab8  jmp     loc_180012B3F
0x180012abd  cmp     [rbp+4Fh+cbData], 4
0x180012ac1  jz      loc_180012BA7
0x180012ac7  call    cs:__imp_GetLastError
0x180012acd  mov     esi, eax
0x180012acf  call    cs:__imp_CurrentIP
0x180012ad5  mov     rdi, rax
0x180012ad8  mov     ebx, [rbp+4Fh+cbData]
0x180012adb  lea     rcx, [rbp+4Fh+var_48]
0x180012adf  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180012ae5  mov     rcx, rax
0x180012ae8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180012aee  mov     r9d, ebx
0x180012af1  mov     r8, rax
0x180012af4  lea     rdx, aSettingSHadUne; "Setting %s had unexpected size: %d"
0x180012afb  mov     ecx, 3000000h; unsigned int
0x180012b00  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012b05  mov     [rsp+0D0h+var_80], 0
0x180012b0d  mov     [rsp+0D0h+var_88], 0
0x180012b16  mov     [rsp+0D0h+var_90], esi
0x180012b1a  mov     [rsp+0D0h+var_98], rdi
0x180012b1f  lea     rcx, aCpitrsettingsQ; "CPITRSettings::QuerySettingDWORD"
0x180012b26  mov     [rsp+0D0h+var_A0], rcx
0x180012b2b  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180012b32  mov     [rsp+0D0h+lpcbData], rcx
0x180012b37  mov     dword ptr [rsp+0D0h+lpData], 931h
0x180012b3f  xor     r9d, r9d
0x180012b42  lea     r8, aD; "D"
0x180012b49  xor     edx, edx
0x180012b4b  mov     rcx, rax
0x180012b4e  call    cs:__imp_WdsSetupLogMessageW
0x180012b54  mov     rbx, [rbp+4Fh+var_70]
0x180012b58  dec     r14d
0x180012b5b  cmp     r14d, 1
0x180012b5f  jg      loc_180012917
0x180012b65  test    r15, r15
0x180012b68  jz      short loc_180012B71
0x180012b6a  mov     dword ptr [r15], 1
0x180012b71  mov     ebx, r12d
0x180012b74  lea     rcx, [rbp+4Fh+var_48]
0x180012b78  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180012b7e  mov     eax, ebx
0x180012b80  mov     rcx, [rbp+4Fh+var_38]
0x180012b84  xor     rcx, rsp; StackCookie
0x180012b87  call    __security_check_cookie
0x180012b8c  mov     rbx, [rsp+0D0h+arg_10]
0x180012b94  add     rsp, 0A0h
0x180012b9b  pop     r15
0x180012b9d  pop     r14
0x180012b9f  pop     r13
0x180012ba1  pop     r12
0x180012ba3  pop     rdi
0x180012ba4  pop     rsi
0x180012ba5  pop     rbp
0x180012ba6  retn
0x180012ba7  test    r15, r15
0x180012baa  jz      short loc_180012BAF
0x180012bac  mov     [r15], r14d
0x180012baf  mov     ebx, dword ptr [rbp+4Fh+Data]
0x180012bb2  jmp     short loc_180012B74
```
