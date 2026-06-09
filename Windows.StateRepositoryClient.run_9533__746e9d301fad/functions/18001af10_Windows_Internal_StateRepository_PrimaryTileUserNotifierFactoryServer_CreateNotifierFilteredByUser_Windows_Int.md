# Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUser(Windows::Internal::StateRepository::IUser *,Windows::Internal::StateRepository::IPrimaryTileUserNotifier * *)

- ea: `0x18001af10`
- end: `0x18001afdb`
- name: `?CreateNotifierFilteredByUser@PrimaryTileUserNotifierFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIUser@234@PEAPEAUIPrimaryTileUserNotifier@234@@Z`
- size: `203`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *__hidden this, struct Windows::Internal::StateRepository::IUser *, struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800075e4`
- `0x18001af10`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001af5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001afc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001af5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001afc9`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUser(
        Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *this,
        struct Windows::Internal::StateRepository::IUser *a2,
        struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **a3)
{
  unsigned int v6; // ebx
  HSTRING v7; // rdx
  __int64 (__fastcall *v8)(struct Windows::Internal::StateRepository::IUser *, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v7 = 0;
    string = 0;
    if ( a2 )
    {
      v8 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IUser *, HSTRING *))(*(_QWORD *)a2 + 64LL);
      WindowsDeleteString(0);
      string = 0;
      v9 = v8(a2, &string);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = 50;
        goto LABEL_9;
      }
      v7 = string;
    }
    v9 = (*(__int64 (__fastcall **)(Windows::Internal::StateRepository::PrimaryTileUserNotifierFactoryServer *, HSTRING, struct Windows::Internal::StateRepository::IPrimaryTileUserNotifier **))(*(_QWORD *)this + 56LL))(
           this,
           v7,
           a3);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v6 = 0;
      goto LABEL_11;
    }
    v10 = 53;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.prima"
                    "rytileusernotifierfactory.cpp",
      (const char *)(unsigned int)v9,
      v12);
LABEL_11:
    WindowsDeleteString(string);
    return v6;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.primary"
                  "tileusernotifierfactory.cpp",
    (const char *)0x80004003LL,
    v12);
  return v6;
}

```

## disassembly

```asm
0x18001af10  push    rbx
0x18001af12  push    rsi
0x18001af13  push    rdi
0x18001af14  push    r14
0x18001af16  sub     rsp, 28h
0x18001af1a  mov     rsi, r8
0x18001af1d  mov     rdi, rdx
0x18001af20  mov     r14, rcx
0x18001af23  test    r8, r8
0x18001af26  jnz     short loc_18001AF49
0x18001af28  mov     rcx, [rsp+48h]; this
0x18001af2d  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18001af34  mov     ebx, 80004003h
0x18001af39  lea     edx, [rsi+2Dh]; void *
0x18001af3c  mov     r9d, ebx; char *
0x18001af3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af44  jmp     loc_18001AFCF
0x18001af49  xor     edx, edx
0x18001af4b  mov     [rsp+48h+string], rdx
0x18001af50  test    rdi, rdi
0x18001af53  jz      short loc_18001AF8F
0x18001af55  mov     rax, [rdi]
0x18001af58  xor     ecx, ecx; string
0x18001af5a  mov     rbx, [rax+40h]
0x18001af5e  call    cs:__imp_WindowsDeleteString
0x18001af64  lea     rdx, [rsp+48h+string]
0x18001af69  mov     [rsp+48h+string], 0
0x18001af72  mov     rcx, rdi
0x18001af75  mov     rax, rbx
0x18001af78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af7d  mov     ebx, eax
0x18001af7f  test    eax, eax
0x18001af81  jns     short loc_18001AF8A
0x18001af83  mov     edx, 32h ; '2'
0x18001af88  jmp     short loc_18001AFAC
0x18001af8a  mov     rdx, [rsp+48h+string]
0x18001af8f  mov     rax, [r14]
0x18001af92  mov     r8, rsi
0x18001af95  mov     rcx, r14
0x18001af98  mov     rax, [rax+38h]
0x18001af9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afa1  mov     ebx, eax
0x18001afa3  test    eax, eax
0x18001afa5  jns     short loc_18001AFC2
0x18001afa7  mov     edx, 35h ; '5'; void *
0x18001afac  mov     rcx, [rsp+48h]; this
0x18001afb1  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18001afb8  mov     r9d, eax; char *
0x18001afbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001afc0  jmp     short loc_18001AFC4
0x18001afc2  xor     ebx, ebx
0x18001afc4  mov     rcx, [rsp+48h+string]; string
0x18001afc9  call    cs:__imp_WindowsDeleteString
0x18001afcf  mov     eax, ebx
0x18001afd1  add     rsp, 28h
0x18001afd5  pop     r14
0x18001afd7  pop     rdi
0x18001afd8  pop     rsi
0x18001afd9  pop     rbx
0x18001afda  retn
```
