# StateRepository::Macros::Evaluators::BuiltIn::SystemPath(ushort const *,StateRepository::Core::Text &,bool &)

- ea: `0x18000f380`
- end: `0x18000f441`
- name: `?SystemPath@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@AEA_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(StateRepository::Macros::Evaluators::BuiltIn *this, StateRepository::Core::Text *, struct StateRepository::Core::Text *, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001ed0`
- `0x180002878`
- `0x1800093ec`
- `0x18000940c`
- `0x18000e760`
- `0x18000f380`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000f3c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000f3c5`

## pseudocode

```c
__int64 __fastcall StateRepository::Macros::Evaluators::BuiltIn::SystemPath(
        StateRepository::Macros::Evaluators::BuiltIn *this,
        StateRepository::Core::Text *a2,
        struct StateRepository::Core::Text *a3,
        bool *a4)
{
  const char *v6; // r9
  int v8; // eax
  unsigned int v9; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  *(_BYTE *)a3 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6E,
             (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
             v6);
  *(_BYTE *)a3 = 1;
  v8 = StateRepository::Core::Text::Append(a2, Buffer);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x70,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
    (const char *)(unsigned int)v8);
  return v9;
}

```

## disassembly

```asm
0x18000f380  mov     [rsp+arg_0], rbx
0x18000f385  push    rdi
0x18000f386  sub     rsp, 240h
0x18000f38d  mov     rax, cs:__security_cookie
0x18000f394  xor     rax, rsp
0x18000f397  mov     [rsp+248h+var_18], rax
0x18000f39f  mov     rbx, r8
0x18000f3a2  mov     byte ptr [r8], 0
0x18000f3a6  mov     rdi, rdx
0x18000f3a9  lea     rcx, [rsp+248h+Buffer]; void *
0x18000f3ae  xor     edx, edx; Val
0x18000f3b0  mov     r8d, 208h; Size
0x18000f3b6  call    memset_0
0x18000f3bb  mov     edx, 104h; uSize
0x18000f3c0  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000f3c5  call    cs:__imp_GetSystemDirectoryW
0x18000f3cb  test    eax, eax
0x18000f3cd  jnz     short loc_18000F3E8
0x18000f3cf  mov     rcx, [rsp+248h]; this
0x18000f3d7  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f3de  lea     edx, [rax+6Eh]; void *
0x18000f3e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f3e6  jmp     short loc_18000F420
0x18000f3e8  lea     rdx, [rsp+248h+Buffer]; unsigned __int16 *
0x18000f3ed  mov     byte ptr [rbx], 1
0x18000f3f0  mov     rcx, rdi; this
0x18000f3f3  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG@Z; StateRepository::Core::Text::Append(ushort const *)
0x18000f3f8  mov     ebx, eax
0x18000f3fa  test    eax, eax
0x18000f3fc  jns     short loc_18000F41E
0x18000f3fe  mov     rcx, [rsp+248h]; this
0x18000f406  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f40d  mov     r9d, eax; char *
0x18000f410  mov     edx, 70h ; 'p'; void *
0x18000f415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f41a  mov     eax, ebx
0x18000f41c  jmp     short loc_18000F420
0x18000f41e  xor     eax, eax
0x18000f420  mov     rcx, [rsp+248h+var_18]
0x18000f428  xor     rcx, rsp; StackCookie
0x18000f42b  call    __security_check_cookie
0x18000f430  mov     rbx, [rsp+248h+arg_0]
0x18000f438  add     rsp, 240h
0x18000f43f  pop     rdi
0x18000f440  retn
```
