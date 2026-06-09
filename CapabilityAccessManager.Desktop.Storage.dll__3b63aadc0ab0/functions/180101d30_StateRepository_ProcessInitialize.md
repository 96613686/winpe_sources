# StateRepository::ProcessInitialize

- ea: `0x180101d30`
- end: `0x180101e5f`
- name: `StateRepository::ProcessInitialize`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18010165c`

## callees

- `0x18000f450`
- `0x1800bf820`
- `0x1800c0170`
- `0x1800eabf4`
- `0x1800f7630`
- `0x180101d30`
- `0x180107404`
- `0x180107580`

## string_xrefs

- `0x180101d79`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101dbc`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101e0e`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ProcessInitialize(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (a1 & 2) != 0 )
    return 0;
  v2 = 1;
  if ( _InterlockedIncrement(&dword_1801403A8) != 1 )
    return 0;
  v3 = sqlite3_initialize(a1, a2);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x87AF0000;
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x157,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v4);
    v5 = 346;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v4,
      v10);
    return v4;
  }
  v7 = StateRepository::VfsNoImpersonation::Register();
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15D,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v7);
    sqlite3_shutdown();
    v5 = 353;
    goto LABEL_7;
  }
  if ( (dword_18013F948 & 0x40) == 0 )
  {
    if ( (dword_18013F948 & 0x80u) == 0 )
      return 0;
    v2 = 0;
  }
  v8 = sqlite3_enable_shared_cache(v2);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x87AF0000;
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x168,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v4);
    v9 = StateRepository::VfsNoImpersonation::Unregister();
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16B,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v9);
    sqlite3_shutdown();
    v5 = 365;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x180101d30  mov     [rsp+arg_0], rbx
0x180101d35  push    rdi; int
0x180101d36  sub     rsp, 20h
0x180101d3a  test    cl, 2
0x180101d3d  jnz     loc_180101E52
0x180101d43  mov     edi, 1
0x180101d48  mov     eax, edi
0x180101d4a  lock xadd cs:dword_1801403A8, eax
0x180101d52  add     eax, edi
0x180101d54  cmp     eax, edi
0x180101d56  jnz     loc_180101E52
0x180101d5c  call    sqlite3_initialize
0x180101d61  mov     ebx, eax
0x180101d63  test    eax, eax
0x180101d65  jle     short loc_180101D70
0x180101d67  movzx   ebx, ax
0x180101d6a  or      ebx, 87AF0000h
0x180101d70  test    ebx, ebx
0x180101d72  jns     short loc_180101DAC
0x180101d74  mov     rcx, [rsp+28h]; this
0x180101d79  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101d80  mov     r8, rdi; unsigned int
0x180101d83  mov     r9d, ebx; char *
0x180101d86  mov     edx, 157h; void *
0x180101d8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101d90  mov     edx, 15Ah; void *
0x180101d95  mov     rcx, [rsp+28h]; this
0x180101d9a  mov     r9d, ebx; char *
0x180101d9d  mov     r8, rdi; unsigned int
0x180101da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101da5  mov     eax, ebx
0x180101da7  jmp     loc_180101E54
0x180101dac  call    ?Register@VfsNoImpersonation@StateRepository@@SAJXZ; StateRepository::VfsNoImpersonation::Register(void)
0x180101db1  mov     ebx, eax
0x180101db3  test    eax, eax
0x180101db5  jns     short loc_180101DDF
0x180101db7  mov     rcx, [rsp+28h]; this
0x180101dbc  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101dc3  mov     r8, rdi; unsigned int
0x180101dc6  mov     r9d, eax; char *
0x180101dc9  mov     edx, 15Dh; void *
0x180101dce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101dd3  call    sqlite3_shutdown
0x180101dd8  mov     edx, 161h
0x180101ddd  jmp     short loc_180101D95
0x180101ddf  mov     eax, cs:dword_18013F948
0x180101de5  test    al, 40h
0x180101de7  jnz     short loc_180101DEF
0x180101de9  test    al, al
0x180101deb  jns     short loc_180101E52
0x180101ded  xor     edi, edi
0x180101def  mov     ecx, edi
0x180101df1  call    sqlite3_enable_shared_cache
0x180101df6  mov     ebx, eax
0x180101df8  test    eax, eax
0x180101dfa  jle     short loc_180101E05
0x180101dfc  movzx   ebx, ax
0x180101dff  or      ebx, 87AF0000h
0x180101e05  test    ebx, ebx
0x180101e07  jns     short loc_180101E52
0x180101e09  mov     rcx, [rsp+28h]; this
0x180101e0e  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101e15  mov     r8, rdi; unsigned int
0x180101e18  mov     r9d, ebx; char *
0x180101e1b  mov     edx, 168h; void *
0x180101e20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101e25  call    ?Unregister@VfsNoImpersonation@StateRepository@@SAJXZ; StateRepository::VfsNoImpersonation::Unregister(void)
0x180101e2a  test    eax, eax
0x180101e2c  jns     short loc_180101E43
0x180101e2e  mov     rcx, [rsp+28h]; this
0x180101e33  mov     r9d, eax; char *
0x180101e36  mov     r8, rdi; unsigned int
0x180101e39  mov     edx, 16Bh; void *
0x180101e3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101e43  call    sqlite3_shutdown
0x180101e48  mov     edx, 16Dh
0x180101e4d  jmp     loc_180101D95
0x180101e52  xor     eax, eax
0x180101e54  mov     rbx, [rsp+28h+arg_0]
0x180101e59  add     rsp, 20h
0x180101e5d  pop     rdi
0x180101e5e  retn
```
