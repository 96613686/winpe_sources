# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(void)

- ea: `0x18001def8`
- end: `0x18001dff6`
- name: `?EnsureAuditBehaviorIsDisabled@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ`
- size: `254`
- prototype: `void(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f014`
- `0x18001f424`

## callees

- `0x18000c6c8`
- `0x18001b5ac`
- `0x18001c4dc`
- `0x18001def8`
- `0x180039010`

## string_xrefs

- `0x18001dfa5`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dfba`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dfcf`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001dfe4`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(
        Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v2 = Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(
         (Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *)((char *)this + 80),
         &v9);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)(unsigned int)v2,
      v6);
  v3 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v9 + 144LL))(v9, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)(unsigned int)v3,
      v6);
  v8 = 0;
  v4 = Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(
         (Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *)((char *)this + 88),
         &v8);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)(unsigned int)v4,
      v6);
  v5 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v8 + 144LL))(v8, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)(unsigned int)v5,
      v6);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v9);
}

```

## disassembly

```asm
0x18001def8  push    rbx; int
0x18001defa  sub     rsp, 20h
0x18001defe  mov     rbx, rcx
0x18001df01  mov     [rsp+28h+arg_8], 0
0x18001df0a  add     rcx, 50h ; 'P'; this
0x18001df0e  lea     rdx, [rsp+28h+arg_8]; void **
0x18001df13  call    ??$As@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccess>>)
0x18001df18  mov     rcx, [rsp+28h]; this
0x18001df1d  test    eax, eax
0x18001df1f  js      loc_18001DFB7
0x18001df25  mov     rcx, [rsp+28h+arg_8]
0x18001df2a  mov     rax, [rcx]
0x18001df2d  xor     edx, edx
0x18001df2f  mov     rax, [rax+90h]
0x18001df36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df3b  mov     rcx, [rsp+28h]; this
0x18001df40  test    eax, eax
0x18001df42  js      loc_18001DFCC
0x18001df48  mov     [rsp+28h+arg_0], 0
0x18001df51  lea     rcx, [rbx+58h]; this
0x18001df55  lea     rdx, [rsp+28h+arg_0]; void **
0x18001df5a  call    ??$As@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICapabilityAccess@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<Windows::Internal::CapabilityAccess::ICapabilityAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccess>>)
0x18001df5f  mov     rcx, [rsp+28h]; this
0x18001df64  test    eax, eax
0x18001df66  js      short loc_18001DFE1
0x18001df68  mov     rcx, [rsp+28h+arg_0]
0x18001df6d  mov     rax, [rcx]
0x18001df70  xor     edx, edx
0x18001df72  mov     rax, [rax+90h]
0x18001df79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df7e  mov     rcx, [rsp+28h]; this
0x18001df83  test    eax, eax
0x18001df85  js      short loc_18001DFA2
0x18001df87  lea     rcx, [rsp+28h+arg_0]
0x18001df8c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001df91  nop
0x18001df92  lea     rcx, [rsp+28h+arg_8]
0x18001df97  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001df9c  add     rsp, 20h
0x18001dfa0  pop     rbx
0x18001dfa1  retn
0x18001dfa2  mov     r9d, eax; char *
0x18001dfa5  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dfac  mov     edx, 185h; void *
0x18001dfb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfb7  mov     r9d, eax; char *
0x18001dfba  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dfc1  mov     edx, 180h; void *
0x18001dfc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfcc  mov     r9d, eax; char *
0x18001dfcf  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dfd6  mov     edx, 181h; void *
0x18001dfdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfe1  mov     r9d, eax; char *
0x18001dfe4  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001dfeb  mov     edx, 184h; void *
0x18001dff0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
