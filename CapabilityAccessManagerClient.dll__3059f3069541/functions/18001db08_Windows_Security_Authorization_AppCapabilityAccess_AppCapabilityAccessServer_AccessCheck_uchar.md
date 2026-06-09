# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::AccessCheck(uchar)

- ea: `0x18001db08`
- end: `0x18001dbfc`
- name: `?AccessCheck@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAA?AW4AppCapabilityAccessStatus@2345@E@Z`
- size: `244`
- prototype: `enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus __high(unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d7c4`
- `0x18001de40`

## callees

- `0x18000c6c8`
- `0x18001b5ac`
- `0x18001c4dc`
- `0x18001db08`
- `0x18001de08`
- `0x180039010`

## string_xrefs

- `0x18001dbab`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dbc0`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dbd5`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dbea`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::AccessCheck(
        __int64 a1,
        char a2)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  unsigned int v9; // [rsp+38h] [rbp+18h] BYREF
  void *v10; // [rsp+40h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a2 )
  {
    v2 = Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(
           (Microsoft::WRL::AgileRef *)(a1 + 88),
           &v10);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v2,
        savedregs);
    v3 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v10 + 152LL))(v10, &v9);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v3,
        savedregs);
  }
  else
  {
    v4 = Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(
           (Microsoft::WRL::AgileRef *)(a1 + 80),
           &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v4,
        savedregs);
    v5 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v10 + 152LL))(v10, &v9);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v5,
        savedregs);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  return Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::CapabilityAccessStatusToAppCapabilityAccessStatus(v9);
}

```

## disassembly

```asm
0x18001db08  push    rbp; int
0x18001db0a  mov     rbp, rsp
0x18001db0d  sub     rsp, 20h
0x18001db11  mov     [rbp+arg_8], 0
0x18001db18  mov     [rbp+arg_10], 0
0x18001db20  test    dl, dl
0x18001db22  jz      short loc_18001DB5E
0x18001db24  add     rcx, 58h ; 'X'; this
0x18001db28  lea     rdx, [rbp+arg_10]; void **
0x18001db2c  call    ??$As@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccess>>)
0x18001db31  mov     rcx, [rbp+8]; this
0x18001db35  test    eax, eax
0x18001db37  js      loc_18001DBBD
0x18001db3d  mov     rcx, [rbp+arg_10]
0x18001db41  mov     rax, [rcx]
0x18001db44  lea     rdx, [rbp+arg_8]
0x18001db48  mov     rax, [rax+98h]
0x18001db4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db54  mov     rcx, [rbp+8]; this
0x18001db58  test    eax, eax
0x18001db5a  js      short loc_18001DBD2
0x18001db5c  jmp     short loc_18001DB92
0x18001db5e  add     rcx, 50h ; 'P'; this
0x18001db62  lea     rdx, [rbp+arg_10]; void **
0x18001db66  call    ??$As@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccess>>)
0x18001db6b  mov     rcx, [rbp+8]; this
0x18001db6f  test    eax, eax
0x18001db71  js      short loc_18001DBE7
0x18001db73  mov     rcx, [rbp+arg_10]
0x18001db77  mov     rax, [rcx]
0x18001db7a  lea     rdx, [rbp+arg_8]
0x18001db7e  mov     rax, [rax+98h]
0x18001db85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db8a  mov     rcx, [rbp+8]; this
0x18001db8e  test    eax, eax
0x18001db90  js      short loc_18001DBA8
0x18001db92  lea     rcx, [rbp+arg_10]
0x18001db96  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001db9b  mov     ecx, [rbp+arg_8]
0x18001db9e  add     rsp, 20h
0x18001dba2  pop     rbp
0x18001dba3  jmp     ?CapabilityAccessStatusToAppCapabilityAccessStatus@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@SA?AW4AppCapabilityAccessStatus@2345@W4CapabilityAccessStatus@CapabilityAccess@Internal@5@@Z; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::CapabilityAccessStatusToAppCapabilityAccessStatus(Windows::Internal::CapabilityAccess::CapabilityAccessStatus)
0x18001dba8  mov     r9d, eax; char *
0x18001dbab  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dbb2  mov     edx, 162h; void *
0x18001dbb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dbbd  mov     r9d, eax; char *
0x18001dbc0  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dbc7  mov     edx, 15Bh; void *
0x18001dbcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dbd2  mov     r9d, eax; char *
0x18001dbd5  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dbdc  mov     edx, 15Ch; void *
0x18001dbe1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dbe7  mov     r9d, eax; char *
0x18001dbea  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dbf1  mov     edx, 161h; void *
0x18001dbf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
