# Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUserSecurityIdentifier(uint,uchar *,Windows::Internal::StateRepository::ISecondaryTileUserNotifier * *)

- ea: `0x180019930`
- end: `0x1800199e4`
- name: `?CreateNotifierFilteredByUserSecurityIdentifier@SecondaryTileUserNotifierFactoryServer@StateRepository@Internal@Windows@@UEAAJIPEAEPEAPEAUISecondaryTileUserNotifier@234@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *__hidden this, unsigned int, unsigned __int8 *, struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800075e4`
- `0x180019930`
- `0x180026110`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019969`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800199d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019969`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800199d3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUserSecurityIdentifier(
        Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *this,
        unsigned int a2,
        unsigned __int8 *a3,
        struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **a4)
{
  unsigned int v5; // ebx
  unsigned int v8; // ebx
  HSTRING *v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  v5 = (unsigned int)a3;
  if ( a4 )
  {
    WindowsDeleteString(0);
    string = 0;
    v10 = StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(
            (StateRepository::WinRT::Client::User *)a2,
            v5,
            (unsigned __int8 *)&string,
            v9);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *, HSTRING, struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **))(*(_QWORD *)this + 56LL))(
              this,
              string,
              a4);
      v8 = v10;
      if ( v10 >= 0 )
      {
        v8 = 0;
        goto LABEL_9;
      }
      v11 = 80;
    }
    else
    {
      v11 = 78;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.secon"
                    "darytileusernotifierfactory.cpp",
      (const char *)(unsigned int)v10,
      v13);
LABEL_9:
    WindowsDeleteString(string);
    return v8;
  }
  v8 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.seconda"
                  "rytileusernotifierfactory.cpp",
    (const char *)0x80004003LL,
    v13);
  return v8;
}

```

## disassembly

```asm
0x180019930  push    rbx
0x180019932  push    rbp
0x180019933  push    rsi
0x180019934  push    rdi
0x180019935  sub     rsp, 28h
0x180019939  mov     rdi, r9
0x18001993c  mov     rbx, r8
0x18001993f  mov     ebp, edx
0x180019941  mov     rsi, rcx
0x180019944  test    r9, r9
0x180019947  jnz     short loc_180019967
0x180019949  mov     rcx, [rsp+48h]; this
0x18001994e  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\staterepositor"...
0x180019955  mov     ebx, 80004003h
0x18001995a  lea     edx, [rdi+4Bh]; void *
0x18001995d  mov     r9d, ebx; char *
0x180019960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019965  jmp     short loc_1800199D9
0x180019967  xor     ecx, ecx; string
0x180019969  call    cs:__imp_WindowsDeleteString
0x18001996f  lea     r8, [rsp+48h+string]; unsigned __int8 *
0x180019974  mov     [rsp+48h+string], 0
0x18001997d  mov     rdx, rbx; unsigned int
0x180019980  mov     ecx, ebp; this
0x180019982  call    ?UserSecurityIdentifierToUserSid@User@Client@WinRT@StateRepository@@YAJIPEAEPEAPEAUHSTRING__@@@Z; StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(uint,uchar *,HSTRING__ * *)
0x180019987  mov     ebx, eax
0x180019989  test    eax, eax
0x18001998b  jns     short loc_180019994
0x18001998d  mov     edx, 4Eh ; 'N'
0x180019992  jmp     short loc_1800199B6
0x180019994  mov     rax, [rsi]
0x180019997  mov     r8, rdi
0x18001999a  mov     rdx, [rsp+48h+string]
0x18001999f  mov     rcx, rsi
0x1800199a2  mov     rax, [rax+38h]
0x1800199a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ab  mov     ebx, eax
0x1800199ad  test    eax, eax
0x1800199af  jns     short loc_1800199CC
0x1800199b1  mov     edx, 50h ; 'P'; void *
0x1800199b6  mov     rcx, [rsp+48h]; this
0x1800199bb  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\staterepositor"...
0x1800199c2  mov     r9d, eax; char *
0x1800199c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199ca  jmp     short loc_1800199CE
0x1800199cc  xor     ebx, ebx
0x1800199ce  mov     rcx, [rsp+48h+string]; string
0x1800199d3  call    cs:__imp_WindowsDeleteString
0x1800199d9  mov     eax, ebx
0x1800199db  add     rsp, 28h
0x1800199df  pop     rdi
0x1800199e0  pop     rsi
0x1800199e1  pop     rbp
0x1800199e2  pop     rbx
0x1800199e3  retn
```
