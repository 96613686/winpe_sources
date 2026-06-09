# StateRepository::ProcessInitialize

- ea: `0x1800a1a10`
- end: `0x1800a1b3a`
- name: `StateRepository::ProcessInitialize`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a1140`

## callees

- `0x18001ab9c`
- `0x1800210d4`
- `0x1800a1a10`
- `0x1800addec`
- `0x1800adf68`

## import_xrefs

- `winsqlite3!sqlite3_enable_shared_cache` at `0x1800a1aca`
- `winsqlite3!sqlite3_enable_shared_cache` at `0x1800a1aca`
- `winsqlite3!sqlite3_shutdown` at `0x1800a1aab`
- `winsqlite3!sqlite3_shutdown` at `0x1800a1b1d`
- `winsqlite3!sqlite3_shutdown` at `0x1800a1aab`
- `winsqlite3!sqlite3_shutdown` at `0x1800a1b1d`
- `winsqlite3!sqlite3_initialize` at `0x1800a1a33`
- `winsqlite3!sqlite3_initialize` at `0x1800a1a33`

## string_xrefs

- `0x1800a1a51`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800a1a94`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800a1ae8`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 StateRepository::ProcessInitialize()
{
  unsigned int v0; // edi
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = 1;
  if ( _InterlockedIncrement(&dword_180168E64) != 1 )
    return 0;
  v1 = sqlite3_initialize();
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x87AF0000;
  if ( (v2 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v2,
      v8);
    v3 = 346;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v2,
      v9);
    return v2;
  }
  v5 = StateRepository::VfsNoImpersonation::Register();
  v2 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v5,
      v8);
    sqlite3_shutdown();
    v3 = 353;
    goto LABEL_6;
  }
  if ( (dword_180166488 & 0x40) == 0 )
  {
    if ( (dword_180166488 & 0x80u) == 0 )
      return 0;
    v0 = 0;
  }
  v6 = sqlite3_enable_shared_cache(v0);
  v2 = v6;
  if ( v6 > 0 )
    v2 = (unsigned __int16)v6 | 0x87AF0000;
  if ( (v2 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v2,
      v8);
    v7 = StateRepository::VfsNoImpersonation::Unregister();
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v7,
        v9);
    sqlite3_shutdown();
    v3 = 365;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a1a10  mov     [rsp+arg_0], rbx
0x1800a1a15  push    rdi; int
0x1800a1a16  sub     rsp, 20h
0x1800a1a1a  mov     edi, 1
0x1800a1a1f  mov     eax, edi
0x1800a1a21  lock xadd cs:dword_180168E64, eax
0x1800a1a29  add     eax, edi
0x1800a1a2b  cmp     eax, edi
0x1800a1a2d  jnz     loc_1800A1B2D
0x1800a1a33  call    cs:__imp_sqlite3_initialize
0x1800a1a39  mov     ebx, eax
0x1800a1a3b  test    eax, eax
0x1800a1a3d  jle     short loc_1800A1A48
0x1800a1a3f  movzx   ebx, ax
0x1800a1a42  or      ebx, 87AF0000h
0x1800a1a48  test    ebx, ebx
0x1800a1a4a  jns     short loc_1800A1A84
0x1800a1a4c  mov     rcx, [rsp+28h]; this
0x1800a1a51  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1800a1a58  mov     r8, rdi; unsigned int
0x1800a1a5b  mov     r9d, ebx; char *
0x1800a1a5e  mov     edx, 157h; void *
0x1800a1a63  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a1a68  mov     edx, 15Ah; void *
0x1800a1a6d  mov     rcx, [rsp+28h]; this
0x1800a1a72  mov     r9d, ebx; char *
0x1800a1a75  mov     r8, rdi; unsigned int
0x1800a1a78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1a7d  mov     eax, ebx
0x1800a1a7f  jmp     loc_1800A1B2F
0x1800a1a84  call    ?Register@VfsNoImpersonation@StateRepository@@SAJXZ; StateRepository::VfsNoImpersonation::Register(void)
0x1800a1a89  mov     ebx, eax
0x1800a1a8b  test    eax, eax
0x1800a1a8d  jns     short loc_1800A1AB8
0x1800a1a8f  mov     rcx, [rsp+28h]; this
0x1800a1a94  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1800a1a9b  mov     r8, rdi; unsigned int
0x1800a1a9e  mov     r9d, eax; char *
0x1800a1aa1  mov     edx, 15Dh; void *
0x1800a1aa6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a1aab  call    cs:__imp_sqlite3_shutdown
0x1800a1ab1  mov     edx, 161h
0x1800a1ab6  jmp     short loc_1800A1A6D
0x1800a1ab8  mov     eax, cs:dword_180166488
0x1800a1abe  test    al, 40h
0x1800a1ac0  jnz     short loc_1800A1AC8
0x1800a1ac2  test    al, al
0x1800a1ac4  jns     short loc_1800A1B2D
0x1800a1ac6  xor     edi, edi
0x1800a1ac8  mov     ecx, edi
0x1800a1aca  call    cs:__imp_sqlite3_enable_shared_cache
0x1800a1ad0  mov     ebx, eax
0x1800a1ad2  test    eax, eax
0x1800a1ad4  jle     short loc_1800A1ADF
0x1800a1ad6  movzx   ebx, ax
0x1800a1ad9  or      ebx, 87AF0000h
0x1800a1adf  test    ebx, ebx
0x1800a1ae1  jns     short loc_1800A1B2D
0x1800a1ae3  mov     rcx, [rsp+28h]; this
0x1800a1ae8  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1800a1aef  mov     r8, rdi; unsigned int
0x1800a1af2  mov     r9d, ebx; char *
0x1800a1af5  mov     edx, 168h; void *
0x1800a1afa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a1aff  call    ?Unregister@VfsNoImpersonation@StateRepository@@SAJXZ; StateRepository::VfsNoImpersonation::Unregister(void)
0x1800a1b04  test    eax, eax
0x1800a1b06  jns     short loc_1800A1B1D
0x1800a1b08  mov     rcx, [rsp+28h]; this
0x1800a1b0d  mov     r9d, eax; char *
0x1800a1b10  mov     r8, rdi; unsigned int
0x1800a1b13  mov     edx, 16Bh; void *
0x1800a1b18  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a1b1d  call    cs:__imp_sqlite3_shutdown
0x1800a1b23  mov     edx, 16Dh
0x1800a1b28  jmp     loc_1800A1A6D
0x1800a1b2d  xor     eax, eax
0x1800a1b2f  mov     rbx, [rsp+28h+arg_0]
0x1800a1b34  add     rsp, 20h
0x1800a1b38  pop     rdi
0x1800a1b39  retn
```
