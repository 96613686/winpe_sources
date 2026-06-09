# Windows::Internal::FilePlaceholderHelper::_VerifyFilePlaceholderLocation(_GUID const &,ushort const *)

- ea: `0x180046bf8`
- end: `0x180046df8`
- name: `?_VerifyFilePlaceholderLocation@FilePlaceholderHelper@Internal@Windows@@YAJAEBU_GUID@@PEBG@Z`
- size: `512`
- prototype: `int(Windows::Internal::FilePlaceholderHelper *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044dd8`

## callees

- `0x180004a54`
- `0x18000b9b0`
- `0x18000c668`
- `0x180019680`
- `0x18001eaa0`
- `0x1800454a0`
- `0x180046bf8`
- `0x180089010`

## import_xrefs

- `Windows.Storage!STORAGE_PathIsEqualOrSubFolderOfKnownFolders` at `0x180046c4b`
- `Windows.Storage!STORAGE_PathIsEqualOrSubFolderOfKnownFolders` at `0x180046c4b`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x180046c2f`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x180046c2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046c91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046c91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d91`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180046d78`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180046d78`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::FilePlaceholderHelper::_VerifyFilePlaceholderLocation(
        Windows::Internal::FilePlaceholderHelper *this,
        const WCHAR *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rax
  HRESULT CurrentUserSid; // ebx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const WCHAR *, __int64 *, __int64 *, int *); // rbx
  int v8; // eax
  int v9; // ecx
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  __int64 v18; // [rsp+68h] [rbp-8h]
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+38h] BYREF

  v4 = *(_QWORD *)this - *(_QWORD *)&CLSID_CachedFileUpdaterPlaceholderStreamResolver.Data1;
  if ( *(_QWORD *)this == *(_QWORD *)&CLSID_CachedFileUpdaterPlaceholderStreamResolver.Data1 )
    v4 = *((_QWORD *)this + 1) - *(_QWORD *)CLSID_CachedFileUpdaterPlaceholderStreamResolver.Data4;
  if ( v4 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    CurrentUserSid = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
    if ( CurrentUserSid >= 0 )
    {
      v12 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v6 = ppv;
      v7 = *(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64 *, __int64 *, int *))(*(_QWORD *)ppv + 32LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      v17 = -1;
      v18 = -1;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v12);
      CurrentUserSid = v7(v6, a2, &v12, &v16, &v19);
      if ( CurrentUserSid == -2147023728 )
        CurrentUserSid = -2144927469;
      if ( CurrentUserSid >= 0 )
      {
        StringSid = 0;
        v14 = 0;
        v15 = 0;
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
        v14 = -1;
        v15 = -1;
        StringSid = 0;
        Sid = 0;
        CurrentUserSid = GetCurrentUserSid(&Sid);
        if ( CurrentUserSid >= 0 )
        {
          if ( ConvertSidToStringSidW(Sid, &StringSid) )
            CurrentUserSid = 0;
          else
            CurrentUserSid = ResultFromKnownLastError();
          LocalFree(Sid);
        }
        if ( CurrentUserSid >= 0 )
        {
          v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                 &v16,
                 StringSid,
                 -1);
          v9 = CurrentUserSid;
          if ( v8 != 2 )
            v9 = -2147024891;
          CurrentUserSid = v9;
        }
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
  }
  else
  {
    if ( PathIsNetworkPathW(a2) )
      return (unsigned int)-2147024891;
    CurrentUserSid = 0;
    if ( (unsigned int)STORAGE_PathIsEqualOrSubFolderOfKnownFolders(a2, 0, &off_18008E700, 1) )
      return (unsigned int)-2147024891;
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180046bf8  mov     [rsp-18h+arg_0], rbx
0x180046bfd  mov     [rsp-18h+arg_8], rsi
0x180046c02  push    rbp
0x180046c03  push    rdi
0x180046c04  push    r15
0x180046c06  mov     rbp, rsp
0x180046c09  sub     rsp, 70h
0x180046c0d  mov     rsi, rdx
0x180046c10  mov     rax, [rcx]
0x180046c13  sub     rax, qword ptr cs:CLSID_CachedFileUpdaterPlaceholderStreamResolver.Data1
0x180046c1a  jnz     short loc_180046C27
0x180046c1c  mov     rax, [rcx+8]
0x180046c20  sub     rax, qword ptr cs:CLSID_CachedFileUpdaterPlaceholderStreamResolver.Data4
0x180046c27  test    rax, rax
0x180046c2a  jnz     short loc_180046C63
0x180046c2c  mov     rcx, rsi; pszPath
0x180046c2f  call    cs:__imp_PathIsNetworkPathW
0x180046c35  test    eax, eax
0x180046c37  jnz     short loc_180046C59
0x180046c39  xor     ebx, ebx
0x180046c3b  lea     r9d, [rax+1]
0x180046c3f  lea     r8, off_18008E700
0x180046c46  xor     edx, edx
0x180046c48  mov     rcx, rsi
0x180046c4b  call    cs:__imp_STORAGE_PathIsEqualOrSubFolderOfKnownFolders
0x180046c51  test    eax, eax
0x180046c53  jz      loc_180046DE1
0x180046c59  mov     ebx, 80070005h
0x180046c5e  jmp     loc_180046DE1
0x180046c63  mov     [rbp+arg_18], 0
0x180046c6b  lea     rcx, [rbp+arg_18]
0x180046c6f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046c74  lea     rax, [rbp+arg_18]
0x180046c78  mov     [rsp+70h+ppv], rax; ppv
0x180046c7d  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180046c84  xor     edx, edx; pUnkOuter
0x180046c86  lea     r8d, [rdx+1]; dwClsContext
0x180046c8a  lea     rcx, CLSID_SyncRootManager; rclsid
0x180046c91  call    cs:__imp_CoCreateInstance
0x180046c97  mov     ebx, eax
0x180046c99  test    eax, eax
0x180046c9b  js      loc_180046DD8
0x180046ca1  mov     [rbp+var_38], 0
0x180046ca9  mov     [rbp+var_18], 0
0x180046cb1  mov     [rbp+var_10], 0
0x180046cb9  mov     [rbp+var_8], 0
0x180046cc1  mov     [rbp+arg_10], 0
0x180046cc8  mov     rdi, [rbp+arg_18]
0x180046ccc  mov     rax, [rdi]
0x180046ccf  mov     rbx, [rax+20h]
0x180046cd3  lea     rcx, [rbp+var_18]
0x180046cd7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180046cdc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180046ce0  mov     [rbp+var_10], r15
0x180046ce4  mov     [rbp+var_8], r15
0x180046ce8  lea     rcx, [rbp+var_38]
0x180046cec  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046cf1  lea     rax, [rbp+arg_10]
0x180046cf5  mov     [rsp+70h+ppv], rax
0x180046cfa  lea     r9, [rbp+var_18]
0x180046cfe  lea     r8, [rbp+var_38]
0x180046d02  mov     rdx, rsi
0x180046d05  mov     rcx, rdi
0x180046d08  mov     rax, rbx
0x180046d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d10  mov     ebx, eax
0x180046d12  mov     eax, 80270113h
0x180046d17  cmp     ebx, 80070490h
0x180046d1d  cmovz   ebx, eax
0x180046d20  test    ebx, ebx
0x180046d22  js      loc_180046DC4
0x180046d28  mov     [rbp+StringSid], 0
0x180046d30  mov     [rbp+var_28], 0
0x180046d38  mov     [rbp+var_20], 0
0x180046d40  lea     rcx, [rbp+StringSid]
0x180046d44  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180046d49  mov     [rbp+var_28], r15
0x180046d4d  mov     [rbp+var_20], r15
0x180046d51  mov     [rbp+StringSid], 0
0x180046d59  mov     [rbp+Sid], 0
0x180046d61  lea     rcx, [rbp+Sid]; void **
0x180046d65  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180046d6a  mov     ebx, eax
0x180046d6c  test    eax, eax
0x180046d6e  js      short loc_180046D97
0x180046d70  lea     rdx, [rbp+StringSid]; StringSid
0x180046d74  mov     rcx, [rbp+Sid]; Sid
0x180046d78  call    cs:__imp_ConvertSidToStringSidW
0x180046d7e  test    eax, eax
0x180046d80  jz      short loc_180046D86
0x180046d82  xor     ebx, ebx
0x180046d84  jmp     short loc_180046D8D
0x180046d86  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180046d8b  mov     ebx, eax
0x180046d8d  mov     rcx, [rbp+Sid]; hMem
0x180046d91  call    cs:__imp_LocalFree
0x180046d97  test    ebx, ebx
0x180046d99  js      short loc_180046DBA
0x180046d9b  mov     r8, r15
0x180046d9e  mov     rdx, [rbp+StringSid]
0x180046da2  lea     rcx, [rbp+var_18]
0x180046da6  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180046dab  mov     ecx, ebx
0x180046dad  mov     ebx, 80070005h
0x180046db2  cmp     eax, 2
0x180046db5  cmovnz  ecx, ebx
0x180046db8  mov     ebx, ecx
0x180046dba  lea     rcx, [rbp+StringSid]
0x180046dbe  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180046dc3  nop
0x180046dc4  lea     rcx, [rbp+var_18]
0x180046dc8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180046dcd  nop
0x180046dce  lea     rcx, [rbp+var_38]
0x180046dd2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046dd7  nop
0x180046dd8  lea     rcx, [rbp+arg_18]
0x180046ddc  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046de1  mov     eax, ebx
0x180046de3  lea     r11, [rsp+70h+var_s0]
0x180046de8  mov     rbx, [r11+20h]
0x180046dec  mov     rsi, [r11+28h]
0x180046df0  mov     rsp, r11
0x180046df3  pop     r15
0x180046df5  pop     rdi
0x180046df6  pop     rbp
0x180046df7  retn
```
