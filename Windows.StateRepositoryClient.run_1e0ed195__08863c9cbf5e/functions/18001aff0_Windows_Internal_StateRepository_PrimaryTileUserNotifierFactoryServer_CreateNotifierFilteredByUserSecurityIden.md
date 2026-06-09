# Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUserSecurityIdentifier(uint,uchar *,Windows::Internal::StateRepository::IPrimaryTileUserNotifier * *)

- ea: `0x18001aff0`
- end: `0x18001b0a4`
- name: `?CreateNotifierFilteredByUserSecurityIdentifier@PrimaryTileUserNotifierFactoryServer@StateRepository@Internal@Windows@@UEAAJIPEAEPEAPEAUIPrimaryTileUserNotifier@234@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *__hidden this, unsigned int, unsigned __int8 *, struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800075e4`
- `0x18001aff0`
- `0x180026110`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b093`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b093`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUserSecurityIdentifier(
        Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *this,
        unsigned int a2,
        unsigned __int8 *a3,
        struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **a4)
{
  unsigned int v8; // ebx
  HSTRING *v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  if ( a4 )
  {
    WindowsDeleteString(0);
    string = 0;
    v10 = StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(
            (StateRepository::WinRT::Client::User *)a2,
            a3,
            (unsigned __int8 *)&string,
            v9);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *, HSTRING, struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **))(*(_QWORD *)this + 56LL))(
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.prima"
                    "rytileusernotifierfactory.cpp",
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
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.primary"
                  "tileusernotifierfactory.cpp",
    (const char *)0x80004003LL,
    v13);
  return v8;
}

```

## disassembly

```asm
0x18001aff0  push    rbx
0x18001aff2  push    rbp
0x18001aff3  push    rsi
0x18001aff4  push    rdi
0x18001aff5  sub     rsp, 28h
0x18001aff9  mov     rdi, r9
0x18001affc  mov     rbx, r8
0x18001afff  mov     ebp, edx
0x18001b001  mov     rsi, rcx
0x18001b004  test    r9, r9
0x18001b007  jnz     short loc_18001B027
0x18001b009  mov     rcx, [rsp+48h]; this
0x18001b00e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18001b015  mov     ebx, 80004003h
0x18001b01a  lea     edx, [rdi+4Bh]; void *
0x18001b01d  mov     r9d, ebx; char *
0x18001b020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b025  jmp     short loc_18001B099
0x18001b027  xor     ecx, ecx; string
0x18001b029  call    cs:__imp_WindowsDeleteString
0x18001b02f  lea     r8, [rsp+48h+string]; unsigned __int8 *
0x18001b034  mov     [rsp+48h+string], 0
0x18001b03d  mov     rdx, rbx; unsigned int
0x18001b040  mov     ecx, ebp; this
0x18001b042  call    ?UserSecurityIdentifierToUserSid@User@Client@WinRT@StateRepository@@YAJIPEAEPEAPEAUHSTRING__@@@Z; StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(uint,uchar *,HSTRING__ * *)
0x18001b047  mov     ebx, eax
0x18001b049  test    eax, eax
0x18001b04b  jns     short loc_18001B054
0x18001b04d  mov     edx, 4Eh ; 'N'
0x18001b052  jmp     short loc_18001B076
0x18001b054  mov     rax, [rsi]
0x18001b057  mov     r8, rdi
0x18001b05a  mov     rdx, [rsp+48h+string]
0x18001b05f  mov     rcx, rsi
0x18001b062  mov     rax, [rax+38h]
0x18001b066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b06b  mov     ebx, eax
0x18001b06d  test    eax, eax
0x18001b06f  jns     short loc_18001B08C
0x18001b071  mov     edx, 50h ; 'P'; void *
0x18001b076  mov     rcx, [rsp+48h]; this
0x18001b07b  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18001b082  mov     r9d, eax; char *
0x18001b085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b08a  jmp     short loc_18001B08E
0x18001b08c  xor     ebx, ebx
0x18001b08e  mov     rcx, [rsp+48h+string]; string
0x18001b093  call    cs:__imp_WindowsDeleteString
0x18001b099  mov     eax, ebx
0x18001b09b  add     rsp, 28h
0x18001b09f  pop     rdi
0x18001b0a0  pop     rsi
0x18001b0a1  pop     rbp
0x18001b0a2  pop     rbx
0x18001b0a3  retn
```
