# Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUser(Windows::Internal::StateRepository::IUser *,Windows::Internal::StateRepository::ISecondaryTileUserNotifier * *)

- ea: `0x180019850`
- end: `0x18001991b`
- name: `?CreateNotifierFilteredByUser@SecondaryTileUserNotifierFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIUser@234@PEAPEAUISecondaryTileUserNotifier@234@@Z`
- size: `203`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *__hidden this, struct Windows::Internal::StateRepository::IUser *, struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800075e4`
- `0x180019850`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001989e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001989e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019909`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer::CreateNotifierFilteredByUser(
        Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *this,
        struct Windows::Internal::StateRepository::IUser *a2,
        struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **a3)
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
    v9 = (*(__int64 (__fastcall **)(Windows::Internal::StateRepository::SecondaryTileUserNotifierFactoryServer *, HSTRING, struct Windows::Internal::StateRepository::ISecondaryTileUserNotifier **))(*(_QWORD *)this + 56LL))(
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.secon"
                    "darytileusernotifierfactory.cpp",
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
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.seconda"
                  "rytileusernotifierfactory.cpp",
    (const char *)0x80004003LL,
    v12);
  return v6;
}

```

## disassembly

```asm
0x180019850  push    rbx
0x180019852  push    rsi
0x180019853  push    rdi
0x180019854  push    r14
0x180019856  sub     rsp, 28h
0x18001985a  mov     rsi, r8
0x18001985d  mov     rdi, rdx
0x180019860  mov     r14, rcx
0x180019863  test    r8, r8
0x180019866  jnz     short loc_180019889
0x180019868  mov     rcx, [rsp+48h]; this
0x18001986d  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\staterepositor"...
0x180019874  mov     ebx, 80004003h
0x180019879  lea     edx, [rsi+2Dh]; void *
0x18001987c  mov     r9d, ebx; char *
0x18001987f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019884  jmp     loc_18001990F
0x180019889  xor     edx, edx
0x18001988b  mov     [rsp+48h+string], rdx
0x180019890  test    rdi, rdi
0x180019893  jz      short loc_1800198CF
0x180019895  mov     rax, [rdi]
0x180019898  xor     ecx, ecx; string
0x18001989a  mov     rbx, [rax+40h]
0x18001989e  call    cs:__imp_WindowsDeleteString
0x1800198a4  lea     rdx, [rsp+48h+string]
0x1800198a9  mov     [rsp+48h+string], 0
0x1800198b2  mov     rcx, rdi
0x1800198b5  mov     rax, rbx
0x1800198b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198bd  mov     ebx, eax
0x1800198bf  test    eax, eax
0x1800198c1  jns     short loc_1800198CA
0x1800198c3  mov     edx, 32h ; '2'
0x1800198c8  jmp     short loc_1800198EC
0x1800198ca  mov     rdx, [rsp+48h+string]
0x1800198cf  mov     rax, [r14]
0x1800198d2  mov     r8, rsi
0x1800198d5  mov     rcx, r14
0x1800198d8  mov     rax, [rax+38h]
0x1800198dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198e1  mov     ebx, eax
0x1800198e3  test    eax, eax
0x1800198e5  jns     short loc_180019902
0x1800198e7  mov     edx, 35h ; '5'; void *
0x1800198ec  mov     rcx, [rsp+48h]; this
0x1800198f1  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\staterepositor"...
0x1800198f8  mov     r9d, eax; char *
0x1800198fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019900  jmp     short loc_180019904
0x180019902  xor     ebx, ebx
0x180019904  mov     rcx, [rsp+48h+string]; string
0x180019909  call    cs:__imp_WindowsDeleteString
0x18001990f  mov     eax, ebx
0x180019911  add     rsp, 28h
0x180019915  pop     r14
0x180019917  pop     rdi
0x180019918  pop     rsi
0x180019919  pop     rbx
0x18001991a  retn
```
