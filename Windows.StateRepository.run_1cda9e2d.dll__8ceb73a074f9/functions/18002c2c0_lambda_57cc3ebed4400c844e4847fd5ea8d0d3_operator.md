# _lambda_57cc3ebed4400c844e4847fd5ea8d0d3_::operator()

- ea: `0x18002c2c0`
- end: `0x18002c46e`
- name: `_lambda_57cc3ebed4400c844e4847fd5ea8d0d3_::operator()`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002c2b0`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x18002c2c0`
- `0x18002c6b8`
- `0x18002c824`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002c39d`
- `ntdll!RtlLengthSid` at `0x18002c39d`
- `ntdll!RtlValidSid` at `0x18002c37b`
- `ntdll!RtlValidSid` at `0x18002c38c`
- `ntdll!RtlValidSid` at `0x18002c37b`
- `ntdll!RtlValidSid` at `0x18002c38c`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002c3c0`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002c3c0`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002c357`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002c357`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002c3d7`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002c3d7`

## string_xrefs

- `0x18002c2ff`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c402`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c42a`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c44b`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c322`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation-custom.cpp`

## pseudocode

```c
__int64 __fastcall lambda_57cc3ebed4400c844e4847fd5ea8d0d3_::operator()(__int64 a1, StateRepository::Statement *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  ULONG v8; // eax
  unsigned __int8 IsMultiUsersInSessionSku; // al
  int v10; // eax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = StateRepository::Statement::Bind(a2, 1, **(void *const **)a1);
  if ( v4 < 0 )
  {
    v5 = 1175;
    goto LABEL_5;
  }
  if ( !*(_QWORD *)a2 )
  {
    v4 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v11);
LABEL_4:
    v5 = 1176;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation-custom.cpp",
      (const char *)(unsigned int)v4,
      v11);
    return (unsigned int)v4;
  }
  v11 = -1;
  v7 = sqlite3_bind_text16(*(_QWORD *)a2, 2, **(_QWORD **)(a1 + 8));
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_4;
  if ( !RtlValidSid(&unk_1804E01E0) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8000FFFFLL,
      -1);
  if ( !RtlValidSid(&unk_1804E01E0) )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v11);
    goto LABEL_22;
  }
  v8 = RtlLengthSid(&unk_1804E01E0);
  v4 = StateRepository::Statement::BindAddress(a2, 3, v8, &unk_1804E01E0);
  if ( v4 < 0 )
  {
LABEL_22:
    v5 = 1177;
    goto LABEL_5;
  }
  IsMultiUsersInSessionSku = RtlIsMultiUsersInSessionSku();
  if ( !*(_QWORD *)a2 )
  {
    v4 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v11);
LABEL_20:
    v5 = 1178;
    goto LABEL_5;
  }
  v10 = sqlite3_bind_int(*(_QWORD *)a2, 4, IsMultiUsersInSessionSku);
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_20;
  return 0;
}

```

## disassembly

```asm
0x18002c2c0  mov     [rsp+arg_0], rbx
0x18002c2c5  mov     [rsp+arg_8], rsi
0x18002c2ca  push    rdi
0x18002c2cb  sub     rsp, 30h
0x18002c2cf  mov     r8, [rcx]
0x18002c2d2  mov     rdi, rdx
0x18002c2d5  mov     rsi, rcx
0x18002c2d8  mov     edx, 1; int
0x18002c2dd  mov     rcx, rdi; this
0x18002c2e0  mov     r8, [r8]; void *
0x18002c2e3  call    ?Bind@Statement@StateRepository@@QEAAJHQEAX@Z; StateRepository::Statement::Bind(int,void * const)
0x18002c2e8  mov     ebx, eax
0x18002c2ea  test    eax, eax
0x18002c2ec  js      loc_18002C3F3
0x18002c2f2  mov     rcx, [rdi]
0x18002c2f5  test    rcx, rcx
0x18002c2f8  jnz     short loc_18002C343
0x18002c2fa  mov     rcx, [rsp+38h]; this
0x18002c2ff  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c306  mov     ebx, 8007139Fh
0x18002c30b  mov     edx, 13Bh; void *
0x18002c310  mov     r9d, ebx; char *
0x18002c313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c318  mov     edx, 498h; void *
0x18002c31d  mov     rcx, [rsp+38h]; this
0x18002c322  lea     r8, aOnecoreBaseApp_348; "onecore\\base\\appmodel\\staterepositor"...
0x18002c329  mov     r9d, ebx; char *
0x18002c32c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c331  mov     eax, ebx
0x18002c333  mov     rbx, [rsp+38h+arg_0]
0x18002c338  mov     rsi, [rsp+38h+arg_8]
0x18002c33d  add     rsp, 30h
0x18002c341  pop     rdi
0x18002c342  retn
0x18002c343  mov     r8, [rsi+8]
0x18002c347  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c34b  mov     qword ptr [rsp+38h+var_18], r9; int
0x18002c350  mov     r8, [r8]
0x18002c353  lea     edx, [r9+3]
0x18002c357  call    cs:__imp_sqlite3_bind_text16
0x18002c35d  mov     ebx, eax
0x18002c35f  mov     esi, 87AF0000h
0x18002c364  test    eax, eax
0x18002c366  jle     short loc_18002C36D
0x18002c368  movzx   ebx, ax
0x18002c36b  or      ebx, esi
0x18002c36d  test    ebx, ebx
0x18002c36f  js      short loc_18002C318
0x18002c371  lea     rbx, unk_1804E01E0
0x18002c378  mov     rcx, rbx; Sid
0x18002c37b  call    cs:__imp_RtlValidSid
0x18002c381  test    al, al
0x18002c383  jz      loc_18002C425
0x18002c389  mov     rcx, rbx; Sid
0x18002c38c  call    cs:__imp_RtlValidSid
0x18002c392  test    al, al
0x18002c394  jz      loc_18002C446
0x18002c39a  mov     rcx, rbx; Sid
0x18002c39d  call    cs:__imp_RtlLengthSid
0x18002c3a3  mov     r8d, eax; unsigned __int64
0x18002c3a6  mov     r9, rbx; void *
0x18002c3a9  mov     edx, 3; int
0x18002c3ae  mov     rcx, rdi; this
0x18002c3b1  call    ?BindAddress@Statement@StateRepository@@QEAAJH_KPEBX@Z; StateRepository::Statement::BindAddress(int,unsigned __int64,void const *)
0x18002c3b6  mov     ebx, eax
0x18002c3b8  test    eax, eax
0x18002c3ba  js      loc_18002C464
0x18002c3c0  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002c3c6  mov     rcx, [rdi]
0x18002c3c9  test    rcx, rcx
0x18002c3cc  jz      short loc_18002C3FD
0x18002c3ce  movzx   r8d, al
0x18002c3d2  mov     edx, 4
0x18002c3d7  call    cs:__imp_sqlite3_bind_int
0x18002c3dd  mov     ebx, eax
0x18002c3df  test    eax, eax
0x18002c3e1  jle     short loc_18002C3E8
0x18002c3e3  movzx   ebx, ax
0x18002c3e6  or      ebx, esi
0x18002c3e8  test    ebx, ebx
0x18002c3ea  js      short loc_18002C41B
0x18002c3ec  xor     eax, eax
0x18002c3ee  jmp     loc_18002C333
0x18002c3f3  mov     edx, 497h
0x18002c3f8  jmp     loc_18002C31D
0x18002c3fd  mov     rcx, [rsp+38h]; this
0x18002c402  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c409  mov     ebx, 8007139Fh
0x18002c40e  mov     edx, 0A3h; void *
0x18002c413  mov     r9d, ebx; char *
0x18002c416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c41b  mov     edx, 49Ah
0x18002c420  jmp     loc_18002C31D
0x18002c425  mov     rcx, [rsp+38h]; this
0x18002c42a  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c431  mov     r9d, 8000FFFFh; char *
0x18002c437  mov     edx, 203h; void *
0x18002c43c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c441  jmp     loc_18002C389
0x18002c446  mov     rcx, [rsp+38h]; this
0x18002c44b  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c452  mov     ebx, 80070057h
0x18002c457  mov     edx, 204h; void *
0x18002c45c  mov     r9d, ebx; char *
0x18002c45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c464  mov     edx, 499h
0x18002c469  jmp     loc_18002C31D
```
