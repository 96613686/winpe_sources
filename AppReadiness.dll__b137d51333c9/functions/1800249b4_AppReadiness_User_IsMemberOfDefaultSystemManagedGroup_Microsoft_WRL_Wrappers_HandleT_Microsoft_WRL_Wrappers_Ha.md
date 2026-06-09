# AppReadiness::User::IsMemberOfDefaultSystemManagedGroup(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x1800249b4`
- end: `0x180024ad3`
- name: `?IsMemberOfDefaultSystemManagedGroup@User@AppReadiness@@KA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010454`

## callees

- `0x1800249b4`
- `0x180027a4c`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800249fa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800249fa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024a5e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024a5e`

## string_xrefs

- `0x180024a0d`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180024a71`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180024a2e`: `CreateWellKnownSid(WinBuiltinDefaultSystemManagedGroupSid, nullptr, sidBuffer, &sidSize)`
- `0x180024a21`: `AppReadiness::User::IsMemberOfDefaultSystemManagedGroup`
- `0x180024a85`: `AppReadiness::User::IsMemberOfDefaultSystemManagedGroup`
- `0x180024a92`: `CheckTokenMembership(userToken.Get(), static_cast<PSID>(sidBuffer), &isMember)`

## pseudocode

```c
bool __fastcall AppReadiness::User::IsMemberOfDefaultSystemManagedGroup(__int64 a1)
{
  int Error; // eax
  void *v3; // rcx
  int v4; // eax
  WINBOOL IsMember; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-35h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, &cbSid) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "CreateWellKnownSid(WinBuiltinDefaultSystemManagedGroupSid, nullptr, sidBuffer, &sidSize)",
        "AppReadiness::User::IsMemberOfDefaultSystemManagedGroup",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2720);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v3 = *(void **)(a1 + 8);
  IsMember = 0;
  if ( !CheckTokenMembership(v3, pSid, &IsMember) )
  {
    v4 = ResultFromKnownLastError();
    if ( v4 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v4,
        "CheckTokenMembership(userToken.Get(), static_cast<PSID>(sidBuffer), &isMember)",
        "AppReadiness::User::IsMemberOfDefaultSystemManagedGroup",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2723);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  return IsMember != 0;
}

```

## disassembly

```asm
0x1800249b4  mov     [rsp-8+arg_8], rbx
0x1800249b9  push    rbp
0x1800249ba  lea     rbp, [rsp-57h]
0x1800249bf  sub     rsp, 0C0h
0x1800249c6  mov     rax, cs:__security_cookie
0x1800249cd  xor     rax, rsp
0x1800249d0  mov     [rbp+57h+var_10], rax
0x1800249d4  xor     edx, edx; Val
0x1800249d6  mov     rbx, rcx
0x1800249d9  lea     rcx, [rbp+57h+pSid]; void *
0x1800249dd  lea     r8d, [rdx+44h]; Size
0x1800249e1  call    memset_0
0x1800249e6  xor     edx, edx; DomainSid
0x1800249e8  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800249ef  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800249f3  lea     r8, [rbp+57h+pSid]; pSid
0x1800249f7  lea     ecx, [rdx+6Fh]; WellKnownSidType
0x1800249fa  call    cs:__imp_CreateWellKnownSid
0x180024a00  test    eax, eax
0x180024a02  jnz     short loc_180024A4B
0x180024a04  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024a09  test    eax, eax
0x180024a0b  jns     short loc_180024A4B
0x180024a0d  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180024a14  mov     [rsp+0C0h+var_98], 0AA0h; int
0x180024a1c  mov     [rsp+0C0h+var_A0], rcx; char *
0x180024a21  lea     r9, aAppreadinessUs; "AppReadiness::User::IsMemberOfDefaultSy"...
0x180024a28  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180024a2c  mov     edx, eax; int
0x180024a2e  lea     r8, aCreatewellknow_1; "CreateWellKnownSid(WinBuiltinDefaultSys"...
0x180024a35  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180024a3a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180024a41  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180024a45  call    _CxxThrowException_0
0x180024a4b  mov     rcx, [rbx+8]; TokenHandle
0x180024a4f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180024a53  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180024a57  mov     [rbp+57h+IsMember], 0
0x180024a5e  call    cs:__imp_CheckTokenMembership
0x180024a64  test    eax, eax
0x180024a66  jnz     short loc_180024AAF
0x180024a68  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024a6d  test    eax, eax
0x180024a6f  jns     short loc_180024AAF
0x180024a71  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180024a78  mov     [rsp+0C0h+var_98], 0AA3h; int
0x180024a80  mov     [rsp+0C0h+var_A0], rcx; char *
0x180024a85  lea     r9, aAppreadinessUs; "AppReadiness::User::IsMemberOfDefaultSy"...
0x180024a8c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180024a90  mov     edx, eax; int
0x180024a92  lea     r8, aChecktokenmemb; "CheckTokenMembership(userToken.Get(), s"...
0x180024a99  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180024a9e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180024aa5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180024aa9  call    _CxxThrowException_0
0x180024aaf  cmp     [rbp+57h+IsMember], 0
0x180024ab3  setnz   al
0x180024ab6  mov     rcx, [rbp+57h+var_10]
0x180024aba  xor     rcx, rsp; StackCookie
0x180024abd  call    __security_check_cookie
0x180024ac2  mov     rbx, [rsp+0C0h+arg_8]
0x180024aca  add     rsp, 0C0h
0x180024ad1  pop     rbp
0x180024ad2  retn
```
