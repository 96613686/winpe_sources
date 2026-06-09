# SerializedRegistryKey::GetSystemPath(std::unique_ptr<void,std::tr1::function<void * (void *)>>)

- ea: `0x180021bc4`
- end: `0x180021cf2`
- name: `?GetSystemPath@SerializedRegistryKey@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@3@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ea98`

## callees

- `0x180009bf8`
- `0x18000d8f8`
- `0x180013294`
- `0x180016cc8`
- `0x18001ebec`
- `0x180021bc4`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180021cbe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180021c4a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180021cbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021c17`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021c17`

## string_xrefs

- `0x180021c73`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SerializedRegistryKey::GetSystemPath(__int64 a1, WCHAR *a2)
{
  int Error; // eax
  LPWSTR v5; // rsi
  int v6; // eax
  __int64 pExceptionObject; // [rsp+48h] [rbp-C0h] BYREF
  LPWSTR StringSid[7]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 v10[264]; // [rsp+88h] [rbp-80h] BYREF

  StringSid[2] = (LPWSTR)-2LL;
  StringSid[5] = a2;
  StringSid[0] = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)a2, StringSid) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LODWORD(pExceptionObject) = Error;
      throw (long *)&pExceptionObject;
    }
  }
  v5 = StringSid[0];
  StringSid[3] = StringSid[0];
  StringSid[4] = (LPWSTR)LocalFree;
  v6 = StringCchPrintfW(
         v10,
         0x104u,
         L"%s\\%s\\%s\\%s",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
         StringSid[0],
         L"AnyoneRead",
         L"LanguageProfile");
  if ( v6 < 0 )
  {
    LODWORD(pExceptionObject) = v6;
    throw (long *)&pExceptionObject;
  }
  std::wstring::wstring(a1, v10);
  if ( v5 )
    LocalFree(v5);
  std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(a2);
  return a1;
}

```

## disassembly

```asm
0x180021bc4  mov     rax, rsp
0x180021bc7  push    rbp
0x180021bc8  push    rsi
0x180021bc9  push    rdi
0x180021bca  lea     rbp, [rax-1B8h]
0x180021bd1  sub     rsp, 2A0h
0x180021bd8  mov     [rsp+2B0h+var_258], 0FFFFFFFFFFFFFFFEh
0x180021be1  mov     [rax+18h], rbx
0x180021be5  mov     rax, cs:__security_cookie
0x180021bec  xor     rax, rsp
0x180021bef  mov     [rbp+1B0h+var_20], rax
0x180021bf6  mov     rdi, rdx
0x180021bf9  mov     rbx, rcx
0x180021bfc  mov     [rsp+2B0h+StringSid], rcx
0x180021c01  mov     [rsp+70h], rdx
0x180021c06  mov     [rsp+2B0h+StringSid], 0
0x180021c0f  lea     rdx, [rsp+2B0h+StringSid]; StringSid
0x180021c14  mov     rcx, [rdi]; Sid
0x180021c17  call    cs:__imp_ConvertSidToStringSidW
0x180021c1d  test    eax, eax
0x180021c1f  jnz     short loc_180021C40
0x180021c21  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021c26  test    eax, eax
0x180021c28  jns     short loc_180021C40
0x180021c2a  mov     dword ptr [rsp+2B0h+pExceptionObject], eax
0x180021c2e  lea     rdx, _TI1J; pThrowInfo
0x180021c35  lea     rcx, [rsp+2B0h+pExceptionObject]; pExceptionObject
0x180021c3a  call    _CxxThrowException_0
0x180021c40  mov     rsi, [rsp+2B0h+StringSid]
0x180021c45  mov     [rsp+2B0h+var_250], rsi
0x180021c4a  mov     rax, cs:__imp_LocalFree
0x180021c51  mov     [rsp+2B0h+var_248], rax
0x180021c56  lea     rax, ?SYSTEM_LANGUAGE_PROFILE_SUBKEY_NAME@Internal@Windows@@3QBGB; "LanguageProfile"
0x180021c5d  mov     [rsp+30h], rax
0x180021c62  mov     rax, cs:off_180026238; "AnyoneRead"
0x180021c69  mov     [rsp+2B0h+var_288], rax
0x180021c6e  mov     [rsp+2B0h+var_290], rsi
0x180021c73  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180021c7a  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180021c81  mov     edx, 104h; unsigned __int64
0x180021c86  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x180021c8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021c8f  test    eax, eax
0x180021c91  jns     short loc_180021CA9
0x180021c93  mov     dword ptr [rsp+2B0h+pExceptionObject], eax
0x180021c97  lea     rdx, _TI1J; pThrowInfo
0x180021c9e  lea     rcx, [rsp+2B0h+pExceptionObject]; pExceptionObject
0x180021ca3  call    _CxxThrowException_0
0x180021ca9  lea     rdx, [rbp+1B0h+var_230]
0x180021cad  mov     rcx, rbx
0x180021cb0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180021cb5  nop
0x180021cb6  test    rsi, rsi
0x180021cb9  jz      short loc_180021CC5
0x180021cbb  mov     rcx, rsi; hMem
0x180021cbe  call    cs:__imp_LocalFree
0x180021cc4  nop
0x180021cc5  mov     rcx, rdi
0x180021cc8  call    ??1?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(void)
0x180021ccd  mov     rax, rbx
0x180021cd0  mov     rcx, [rbp+1B0h+var_20]
0x180021cd7  xor     rcx, rsp; StackCookie
0x180021cda  call    __security_check_cookie
0x180021cdf  mov     rbx, [rsp+2B0h+arg_10]
0x180021ce7  add     rsp, 2A0h
0x180021cee  pop     rdi
0x180021cef  pop     rsi
0x180021cf0  pop     rbp
0x180021cf1  retn
```
