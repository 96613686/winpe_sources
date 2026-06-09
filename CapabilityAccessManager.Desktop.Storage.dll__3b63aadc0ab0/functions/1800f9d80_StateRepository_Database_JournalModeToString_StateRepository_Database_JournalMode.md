# StateRepository::Database::JournalModeToString(StateRepository::Database::JournalMode)

- ea: `0x1800f9d80`
- end: `0x1800f9e3e`
- name: `?JournalModeToString@Database@StateRepository@@CAPEBDW4JournalMode@12@@Z`
- size: `190`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800fbcb4`

## callees

- `0x1800f9d80`
- `0x1800fa538`
- `0x1800fa588`

## string_xrefs

- `0x1800f9d9b`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9dee`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9e32`: `DELETE`

## pseudocode

```c
const char *__fastcall StateRepository::Database::JournalModeToString(int a1)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // [rsp+20h] [rbp-18h]
  char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a1 )
  {
    LOBYTE(v8) = 1;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0xBCD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8000FFFFLL,
      v8,
      (bool)"GetDefaultJournalMode() cannot return Default",
      v10);
    return "WAL";
  }
  v3 = a1 - 1;
  if ( !v3 )
    return "DELETE";
  v4 = v3 - 1;
  if ( !v4 )
    return "TRUNCATE";
  v5 = v4 - 1;
  if ( !v5 )
    return "PERSIST";
  v6 = v5 - 1;
  if ( !v6 )
    return "MEMORY";
  v7 = v6 - 1;
  if ( !v7 )
    return "WAL";
  if ( v7 == 1 )
    return "OFF";
  LODWORD(v9) = a1;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xBD8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8000FFFFLL,
    (int)"Unknown JournalMode=%d",
    v9);
  return 0;
}

```

## disassembly

```asm
0x1800f9d80  sub     rsp, 38h
0x1800f9d84  mov     edx, ecx
0x1800f9d86  test    ecx, ecx
0x1800f9d88  jnz     short loc_1800F9DC0
0x1800f9d8a  mov     rcx, [rsp+38h]; this
0x1800f9d8f  lea     rax, aGetdefaultjour; "GetDefaultJournalMode() cannot return D"...
0x1800f9d96  mov     [rsp+38h+var_10], rax; bool
0x1800f9d9b  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9da2  mov     r9d, 8000FFFFh; char *
0x1800f9da8  mov     byte ptr [rsp+38h+var_18], 1; int
0x1800f9dad  mov     edx, 0BCDh; void *
0x1800f9db2  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800f9db7  lea     rax, aWal; "WAL"
0x1800f9dbe  jmp     short loc_1800F9E39
0x1800f9dc0  sub     ecx, 1
0x1800f9dc3  jz      short loc_1800F9E32
0x1800f9dc5  sub     ecx, 1
0x1800f9dc8  jz      short loc_1800F9E29
0x1800f9dca  sub     ecx, 1
0x1800f9dcd  jz      short loc_1800F9E20
0x1800f9dcf  sub     ecx, 1
0x1800f9dd2  jz      short loc_1800F9E17
0x1800f9dd4  sub     ecx, 1
0x1800f9dd7  jz      short loc_1800F9DB7
0x1800f9dd9  cmp     ecx, 1
0x1800f9ddc  jz      short loc_1800F9E0E
0x1800f9dde  mov     rcx, [rsp+38h]; this
0x1800f9de3  lea     rax, aUnknownJournal_0; "Unknown JournalMode=%d"
0x1800f9dea  mov     dword ptr [rsp+38h+var_10], edx; char *
0x1800f9dee  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9df5  mov     edx, 0BD8h; void *
0x1800f9dfa  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800f9dff  mov     r9d, 8000FFFFh; char *
0x1800f9e05  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f9e0a  xor     eax, eax
0x1800f9e0c  jmp     short loc_1800F9E39
0x1800f9e0e  lea     rax, aOff_0; "OFF"
0x1800f9e15  jmp     short loc_1800F9E39
0x1800f9e17  lea     rax, aMemory_0; "MEMORY"
0x1800f9e1e  jmp     short loc_1800F9E39
0x1800f9e20  lea     rax, aPersist; "PERSIST"
0x1800f9e27  jmp     short loc_1800F9E39
0x1800f9e29  lea     rax, aTruncate_0; "TRUNCATE"
0x1800f9e30  jmp     short loc_1800F9E39
0x1800f9e32  lea     rax, aDelete; "DELETE"
0x1800f9e39  add     rsp, 38h
0x1800f9e3d  retn
```
