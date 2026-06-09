# StateRepository::Database::SetLockingMode(StateRepository::Database::LockingMode)

- ea: `0x1800fbd64`
- end: `0x1800fbe46`
- name: `?SetLockingMode@Database@StateRepository@@QEAAJW4LockingMode@12@@Z`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800fa944`

## callees

- `0x1800eabf4`
- `0x1800f9934`
- `0x1800fa588`
- `0x1800fbd64`
- `0x1800fbe4c`

## string_xrefs

- `0x1800fbd9c`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fbdd6`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fbe2e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::SetLockingMode(StateRepository::Database *a1, int a2)
{
  int v2; // ebx
  int LockingMode; // eax
  unsigned int v5; // edi
  const char *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  char *v11; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v13; // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  v2 = 1;
  if ( a2 )
    v2 = a2;
  LockingMode = StateRepository::Database::GetLockingMode(a1, (enum StateRepository::Database::LockingMode *)&v13);
  v5 = LockingMode;
  if ( LockingMode < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)LockingMode,
      v10);
    return v5;
  }
  if ( v2 == v13 )
    return 0;
  if ( v2 == 1 )
  {
    v7 = "NORMAL";
  }
  else
  {
    if ( v2 != 2 )
    {
      LODWORD(v11) = v2;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xC39,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unknown LockingMode=%d",
        v11);
      return 0;
    }
    v7 = "EXCLUSIVE";
  }
  v8 = StateRepository::Database::SetPragma(a1, "locking_mode", v7);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4AF,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)(unsigned int)v8,
    v10);
  return v9;
}

```

## disassembly

```asm
0x1800fbd64  mov     rax, rsp
0x1800fbd67  mov     [rax+8], rbx
0x1800fbd6b  mov     [rax+18h], rsi
0x1800fbd6f  push    rdi
0x1800fbd70  sub     rsp, 30h
0x1800fbd74  test    edx, edx
0x1800fbd76  mov     dword ptr [rax+10h], 0
0x1800fbd7d  mov     ebx, 1
0x1800fbd82  mov     rsi, rcx
0x1800fbd85  cmovnz  ebx, edx
0x1800fbd88  lea     rdx, [rax+10h]; enum StateRepository::Database::LockingMode *
0x1800fbd8c  call    ?GetLockingMode@Database@StateRepository@@QEAAJPEAW4LockingMode@12@@Z; StateRepository::Database::GetLockingMode(StateRepository::Database::LockingMode *)
0x1800fbd91  mov     edi, eax
0x1800fbd93  test    eax, eax
0x1800fbd95  jns     short loc_1800FBDB4
0x1800fbd97  mov     rcx, [rsp+38h]; this
0x1800fbd9c  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fbda3  mov     r9d, eax; char *
0x1800fbda6  mov     edx, 4A9h; void *
0x1800fbdab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbdb0  mov     eax, edi
0x1800fbdb2  jmp     short loc_1800FBDF4
0x1800fbdb4  cmp     ebx, [rsp+38h+arg_8]
0x1800fbdb8  jz      short loc_1800FBDF2
0x1800fbdba  mov     ecx, ebx
0x1800fbdbc  sub     ecx, 1
0x1800fbdbf  jz      short loc_1800FBE0D
0x1800fbdc1  cmp     ecx, 1
0x1800fbdc4  jz      short loc_1800FBE04
0x1800fbdc6  mov     rcx, [rsp+38h]; this
0x1800fbdcb  lea     rax, aUnknownLocking_0; "Unknown LockingMode=%d"
0x1800fbdd2  mov     dword ptr [rsp+38h+var_10], ebx; char *
0x1800fbdd6  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fbddd  mov     r9d, 8000FFFFh; char *
0x1800fbde3  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800fbde8  mov     edx, 0C39h; void *
0x1800fbded  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fbdf2  xor     eax, eax
0x1800fbdf4  mov     rbx, [rsp+38h+arg_0]
0x1800fbdf9  mov     rsi, [rsp+38h+arg_10]
0x1800fbdfe  add     rsp, 30h
0x1800fbe02  pop     rdi
0x1800fbe03  retn
0x1800fbe04  lea     r8, aExclusive_0; "EXCLUSIVE"
0x1800fbe0b  jmp     short loc_1800FBE14
0x1800fbe0d  lea     r8, aNormal_0; "NORMAL"
0x1800fbe14  lea     rdx, aLockingMode; "locking_mode"
0x1800fbe1b  mov     rcx, rsi; this
0x1800fbe1e  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD0@Z; StateRepository::Database::SetPragma(char const *,char const *)
0x1800fbe23  mov     ebx, eax
0x1800fbe25  test    eax, eax
0x1800fbe27  jns     short loc_1800FBDF2
0x1800fbe29  mov     rcx, [rsp+38h]; this
0x1800fbe2e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fbe35  mov     r9d, eax; char *
0x1800fbe38  mov     edx, 4AFh; void *
0x1800fbe3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbe42  mov     eax, ebx
0x1800fbe44  jmp     short loc_1800FBDF4
```
