# AppReadiness::User::GetWellKnownSid(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x180021bd4`
- end: `0x180021d30`
- name: `?GetWellKnownSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `348`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010454`
- `0x18002c0d0`
- `0x180059fb4`

## callees

- `0x18000c000`
- `0x180021bd4`
- `0x180027a4c`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021c27`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021c27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d0d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021c84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021c84`

## string_xrefs

- `0x180021c42`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180021c9f`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180021c4e`: `AppReadiness::User::GetWellKnownSid`
- `0x180021cab`: `AppReadiness::User::GetWellKnownSid`
- `0x180021cb2`: `ConvertSidToStringSid(reinterpret_cast<SID*>(sid), &rawSidStr)`
- `0x180021c55`: `CreateWellKnownSid(sidType, domainSid, reinterpret_cast<SID*>(sid), &sidLen)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppReadiness::User::GetWellKnownSid(__int64 a1, WELL_KNOWN_SID_TYPE a2, void *a3)
{
  int Error; // eax
  int v7; // eax
  LPWSTR v8; // rbx
  __int64 v9; // r8
  DWORD cbSid; // [rsp+30h] [rbp-79h] BYREF
  LPWSTR StringSid[3]; // [rsp+38h] [rbp-71h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE pSid[80]; // [rsp+80h] [rbp-29h] BYREF

  StringSid[0] = (LPWSTR)a1;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(a2, a3, pSid, &cbSid) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "CreateWellKnownSid(sidType, domainSid, reinterpret_cast<SID*>(sid), &sidLen)",
        "AppReadiness::User::GetWellKnownSid",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2520);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  StringSid[0] = 0;
  if ( !ConvertSidToStringSidW(pSid, StringSid) )
  {
    v7 = ResultFromKnownLastError();
    if ( v7 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v7,
        "ConvertSidToStringSid(reinterpret_cast<SID*>(sid), &rawSidStr)",
        "AppReadiness::User::GetWellKnownSid",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2523);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v8 = StringSid[0];
  StringSid[2] = StringSid[0];
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  std::wstring::_Construct<1,unsigned short const *>(a1);
  if ( v8 )
    LocalFree(v8);
  return a1;
}

```

## disassembly

```asm
0x180021bd4  push    rbp
0x180021bd6  push    rbx
0x180021bd7  push    rsi
0x180021bd8  push    rdi
0x180021bd9  push    r15
0x180021bdb  lea     rbp, [rsp-37h]
0x180021be0  sub     rsp, 0E0h
0x180021be7  mov     rax, cs:__security_cookie
0x180021bee  xor     rax, rsp
0x180021bf1  mov     [rbp+57h+var_30], rax
0x180021bf5  mov     rdi, r8
0x180021bf8  mov     ebx, edx
0x180021bfa  mov     rsi, rcx
0x180021bfd  mov     [rbp+57h+StringSid], rcx
0x180021c01  xor     r15d, r15d
0x180021c04  xor     edx, edx; Val
0x180021c06  lea     r8d, [r15+44h]; Size
0x180021c0a  lea     rcx, [rbp+57h+pSid]; void *
0x180021c0e  call    memset_0
0x180021c13  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180021c1a  lea     r9, [rbp+57h+cbSid]; cbSid
0x180021c1e  lea     r8, [rbp+57h+pSid]; pSid
0x180021c22  mov     rdx, rdi; DomainSid
0x180021c25  mov     ecx, ebx; WellKnownSidType
0x180021c27  call    cs:__imp_CreateWellKnownSid
0x180021c2d  test    eax, eax
0x180021c2f  jnz     short loc_180021C78
0x180021c31  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021c36  test    eax, eax
0x180021c38  jns     short loc_180021C78
0x180021c3a  mov     [rsp+100h+var_D8], 9D8h; int
0x180021c42  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180021c49  mov     [rsp+100h+var_E0], rcx; char *
0x180021c4e  lea     r9, aAppreadinessUs_11; "AppReadiness::User::GetWellKnownSid"
0x180021c55  lea     r8, aCreatewellknow; "CreateWellKnownSid(sidType, domainSid, "...
0x180021c5c  mov     edx, eax; int
0x180021c5e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021c62  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180021c67  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180021c6e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021c72  call    _CxxThrowException_0
0x180021c78  mov     [rbp+57h+StringSid], r15
0x180021c7c  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180021c80  lea     rcx, [rbp+57h+pSid]; Sid
0x180021c84  call    cs:__imp_ConvertSidToStringSidW
0x180021c8a  test    eax, eax
0x180021c8c  jnz     short loc_180021CD5
0x180021c8e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021c93  test    eax, eax
0x180021c95  jns     short loc_180021CD5
0x180021c97  mov     [rsp+100h+var_D8], 9DBh; int
0x180021c9f  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180021ca6  mov     [rsp+100h+var_E0], rcx; char *
0x180021cab  lea     r9, aAppreadinessUs_11; "AppReadiness::User::GetWellKnownSid"
0x180021cb2  lea     r8, aConvertsidtost_0; "ConvertSidToStringSid(reinterpret_cast<"...
0x180021cb9  mov     edx, eax; int
0x180021cbb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021cbf  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180021cc4  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180021ccb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021ccf  call    _CxxThrowException_0
0x180021cd5  mov     rbx, [rbp+57h+StringSid]
0x180021cd9  mov     [rbp+57h+var_B8], rbx
0x180021cdd  xorps   xmm0, xmm0
0x180021ce0  movups  xmmword ptr [rsi], xmm0
0x180021ce3  mov     [rsi+10h], r15
0x180021ce7  mov     [rsi+18h], r15
0x180021ceb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021cef  inc     r8
0x180021cf2  cmp     [rbx+r8*2], r15w
0x180021cf7  jnz     short loc_180021CEF
0x180021cf9  mov     rdx, rbx
0x180021cfc  mov     rcx, rsi
0x180021cff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021d04  nop
0x180021d05  test    rbx, rbx
0x180021d08  jz      short loc_180021D13
0x180021d0a  mov     rcx, rbx; hMem
0x180021d0d  call    cs:__imp_LocalFree
0x180021d13  mov     rax, rsi
0x180021d16  mov     rcx, [rbp+57h+var_30]
0x180021d1a  xor     rcx, rsp; StackCookie
0x180021d1d  call    __security_check_cookie
0x180021d22  add     rsp, 0E0h
0x180021d29  pop     r15
0x180021d2b  pop     rdi
0x180021d2c  pop     rsi
0x180021d2d  pop     rbx
0x180021d2e  pop     rbp
0x180021d2f  retn
```
