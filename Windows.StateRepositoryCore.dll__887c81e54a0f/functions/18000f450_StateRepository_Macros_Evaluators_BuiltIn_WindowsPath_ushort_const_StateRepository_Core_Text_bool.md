# StateRepository::Macros::Evaluators::BuiltIn::WindowsPath(ushort const *,StateRepository::Core::Text &,bool &)

- ea: `0x18000f450`
- end: `0x18000f511`
- name: `?WindowsPath@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@AEA_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(StateRepository::Macros::Evaluators::BuiltIn *this, StateRepository::Core::Text *, struct StateRepository::Core::Text *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f228`

## callees

- `0x180001ed0`
- `0x180002878`
- `0x1800093ec`
- `0x18000940c`
- `0x18000e760`
- `0x18000f450`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000f495`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000f495`

## pseudocode

```c
__int64 __fastcall StateRepository::Macros::Evaluators::BuiltIn::WindowsPath(
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
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5F,
             (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
             v6);
  *(_BYTE *)a3 = 1;
  v8 = StateRepository::Core::Text::Append(a2, Buffer);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x61,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
    (const char *)(unsigned int)v8);
  return v9;
}

```

## disassembly

```asm
0x18000f450  mov     [rsp+arg_0], rbx
0x18000f455  push    rdi
0x18000f456  sub     rsp, 240h
0x18000f45d  mov     rax, cs:__security_cookie
0x18000f464  xor     rax, rsp
0x18000f467  mov     [rsp+248h+var_18], rax
0x18000f46f  mov     rbx, r8
0x18000f472  mov     byte ptr [r8], 0
0x18000f476  mov     rdi, rdx
0x18000f479  lea     rcx, [rsp+248h+Buffer]; void *
0x18000f47e  xor     edx, edx; Val
0x18000f480  mov     r8d, 208h; Size
0x18000f486  call    memset_0
0x18000f48b  mov     edx, 104h; uSize
0x18000f490  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000f495  call    cs:__imp_GetWindowsDirectoryW
0x18000f49b  test    eax, eax
0x18000f49d  jnz     short loc_18000F4B8
0x18000f49f  mov     rcx, [rsp+248h]; this
0x18000f4a7  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f4ae  lea     edx, [rax+5Fh]; void *
0x18000f4b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f4b6  jmp     short loc_18000F4F0
0x18000f4b8  lea     rdx, [rsp+248h+Buffer]; unsigned __int16 *
0x18000f4bd  mov     byte ptr [rbx], 1
0x18000f4c0  mov     rcx, rdi; this
0x18000f4c3  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG@Z; StateRepository::Core::Text::Append(ushort const *)
0x18000f4c8  mov     ebx, eax
0x18000f4ca  test    eax, eax
0x18000f4cc  jns     short loc_18000F4EE
0x18000f4ce  mov     rcx, [rsp+248h]; this
0x18000f4d6  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f4dd  mov     r9d, eax; char *
0x18000f4e0  mov     edx, 61h ; 'a'; void *
0x18000f4e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4ea  mov     eax, ebx
0x18000f4ec  jmp     short loc_18000F4F0
0x18000f4ee  xor     eax, eax
0x18000f4f0  mov     rcx, [rsp+248h+var_18]
0x18000f4f8  xor     rcx, rsp; StackCookie
0x18000f4fb  call    __security_check_cookie
0x18000f500  mov     rbx, [rsp+248h+arg_0]
0x18000f508  add     rsp, 240h
0x18000f50f  pop     rdi
0x18000f510  retn
```
