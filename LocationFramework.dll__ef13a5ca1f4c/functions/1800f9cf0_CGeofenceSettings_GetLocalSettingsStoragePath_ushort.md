# CGeofenceSettings::GetLocalSettingsStoragePath(ushort * *)

- ea: `0x1800f9cf0`
- end: `0x1800f9e35`
- name: `?GetLocalSettingsStoragePath@CGeofenceSettings@@UEAAJPEAPEAG@Z`
- size: `325`
- prototype: `__int64 __fastcall(CGeofenceSettings *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x1800136b8`
- `0x180018618`
- `0x18003e7a4`
- `0x18004735c`
- `0x180063528`
- `0x1800a98c0`
- `0x1800f9cf0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800f9dba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9df8`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f9d62`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f9d62`

## pseudocode

```c
__int64 __fastcall CGeofenceSettings::GetLocalSettingsStoragePath(CGeofenceSettings *this, unsigned __int16 **a2)
{
  HRESULT v5; // edi
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[16]; // [rsp+28h] [rbp-30h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v9,
    (char *)this + 72);
  if ( *((_QWORD *)this + 8) )
    goto LABEL_8;
  ppszPath = 0;
  v5 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x4000u, 0, &ppszPath);
  if ( v5 >= 0 )
  {
    v8 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v8);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v8,
      L"%s\\%s",
      ppszPath,
      L"\\Microsoft\\Windows\\LfSvc\\Geofence");
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v8);
    if ( *((_QWORD *)this + 8) != v6 )
    {
      SysFreeString(*((BSTR *)this + 8));
      *((_QWORD *)this + 8) = v6;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v8);
    CoTaskMemFree(ppszPath);
LABEL_8:
    v7 = ATL::CComBSTR::CopyTo((CGeofenceSettings *)((char *)this + 64), a2);
    if ( v7 >= 0 )
      v5 = 0;
    else
      v5 = v7;
    goto LABEL_12;
  }
  CoTaskMemFree(ppszPath);
  ppszPath = 0;
LABEL_12:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800f9cf0  mov     [rsp+arg_10], rsi
0x1800f9cf5  mov     [rsp+arg_18], rdi
0x1800f9cfa  push    r14
0x1800f9cfc  sub     rsp, 50h
0x1800f9d00  mov     rax, cs:__security_cookie
0x1800f9d07  xor     rax, rsp
0x1800f9d0a  mov     [rsp+58h+var_18], rax
0x1800f9d0f  mov     r14, rdx
0x1800f9d12  mov     rsi, rcx
0x1800f9d15  test    rdx, rdx
0x1800f9d18  jnz     short loc_1800F9D24
0x1800f9d1a  mov     eax, 80070057h
0x1800f9d1f  jmp     loc_1800F9E17
0x1800f9d24  mov     qword ptr [rdx], 0
0x1800f9d2b  lea     rdx, [rcx+48h]
0x1800f9d2f  lea     rcx, [rsp+58h+var_30]
0x1800f9d34  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800f9d39  nop
0x1800f9d3a  cmp     qword ptr [rsi+40h], 0
0x1800f9d3f  jnz     loc_1800F9DDA
0x1800f9d45  mov     [rsp+58h+ppszPath], 0
0x1800f9d4e  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x1800f9d53  xor     r8d, r8d; hToken
0x1800f9d56  mov     edx, 4000h; dwFlags
0x1800f9d5b  lea     rcx, FOLDERID_ProgramData; rfid
0x1800f9d62  call    cs:__imp_SHGetKnownFolderPath
0x1800f9d68  mov     edi, eax
0x1800f9d6a  test    eax, eax
0x1800f9d6c  js      loc_1800F9DF3
0x1800f9d72  mov     [rsp+58h+var_38], 0
0x1800f9d7b  lea     rcx, [rsp+58h+var_38]
0x1800f9d80  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800f9d85  nop
0x1800f9d86  lea     r9, aMicrosoftWindo_1; "\\Microsoft\\Windows\\LfSvc\\Geofence"
0x1800f9d8d  mov     r8, [rsp+58h+ppszPath]
0x1800f9d92  lea     rdx, aSS_0; "%s\\%s"
0x1800f9d99  lea     rcx, [rsp+58h+var_38]
0x1800f9d9e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800f9da3  lea     rcx, [rsp+58h+var_38]
0x1800f9da8  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x1800f9dad  mov     rdi, rax
0x1800f9db0  cmp     [rsi+40h], rax
0x1800f9db4  jz      short loc_1800F9DC4
0x1800f9db6  mov     rcx, [rsi+40h]; bstrString
0x1800f9dba  call    cs:__imp_SysFreeString
0x1800f9dc0  mov     [rsi+40h], rdi
0x1800f9dc4  lea     rcx, [rsp+58h+var_38]
0x1800f9dc9  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800f9dce  nop
0x1800f9dcf  mov     rcx, [rsp+58h+ppszPath]; pv
0x1800f9dd4  call    cs:__imp_CoTaskMemFree
0x1800f9dda  mov     rdx, r14; unsigned __int16 **
0x1800f9ddd  lea     rcx, [rsi+40h]; this
0x1800f9de1  call    ?CopyTo@CComBSTR@ATL@@QEAAJPEAPEAG@Z; ATL::CComBSTR::CopyTo(ushort * *)
0x1800f9de6  test    eax, eax
0x1800f9de8  jns     short loc_1800F9E09
0x1800f9dea  mov     edi, eax
0x1800f9dec  jmp     short loc_1800F9E0B
0x1800f9dee  mov     edi, 8007000Eh
0x1800f9df3  mov     rcx, [rsp+58h+ppszPath]; pv
0x1800f9df8  call    cs:__imp_CoTaskMemFree
0x1800f9dfe  mov     [rsp+58h+ppszPath], 0
0x1800f9e07  jmp     short loc_1800F9E0B
0x1800f9e09  xor     edi, edi
0x1800f9e0b  lea     rcx, [rsp+58h+var_30]
0x1800f9e10  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800f9e15  mov     eax, edi
0x1800f9e17  mov     rcx, [rsp+58h+var_18]
0x1800f9e1c  xor     rcx, rsp; StackCookie
0x1800f9e1f  call    __security_check_cookie
0x1800f9e24  mov     rsi, [rsp+58h+arg_10]
0x1800f9e29  mov     rdi, [rsp+58h+arg_18]
0x1800f9e2e  add     rsp, 50h
0x1800f9e32  pop     r14
0x1800f9e34  retn
```
