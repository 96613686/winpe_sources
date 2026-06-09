# _lambda_ea346bfdcf049c9e1412db4f509ea147_::operator()

- ea: `0x18002c490`
- end: `0x18002c6b2`
- name: `_lambda_ea346bfdcf049c9e1412db4f509ea147_::operator()`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002c480`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x18002c490`
- `0x18002c6b8`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002c59f`
- `ntdll!RtlLengthSid` at `0x18002c59f`
- `ntdll!RtlValidSid` at `0x18002c57d`
- `ntdll!RtlValidSid` at `0x18002c58e`
- `ntdll!RtlValidSid` at `0x18002c57d`
- `ntdll!RtlValidSid` at `0x18002c58e`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002c5ee`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002c5ee`
- `StateRepository.Core!sqlite3_bind_blob` at `0x18002c5d1`
- `StateRepository.Core!sqlite3_bind_blob` at `0x18002c5d1`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002c556`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002c556`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002c4f9`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002c4f9`

## string_xrefs

- `0x18002c4d0`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c605`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c623`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c651`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c67e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c520`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation-custom.cpp`
- `0x18002c697`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation-custom.cpp`

## pseudocode

```c
__int64 __fastcall lambda_ea346bfdcf049c9e1412db4f509ea147_::operator()(__int64 a1, StateRepository::Statement *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v8; // eax
  ULONG v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  unsigned __int8 IsMultiUsersInSessionSku; // al
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = StateRepository::Statement::Bind(a2, 1, **(void *const **)a1);
  if ( v4 < 0 )
  {
    v5 = 959;
    goto LABEL_9;
  }
  if ( !*(_QWORD *)a2 )
  {
    v4 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v14);
LABEL_4:
    v5 = 960;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation-custom.cpp",
      (const char *)(unsigned int)v4,
      v14);
    return (unsigned int)v4;
  }
  v14 = -1;
  v8 = sqlite3_bind_text16(*(_QWORD *)a2, 2, **(_QWORD **)(a1 + 8));
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_4;
  if ( !RtlValidSid(qword_1804E01E0) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x203,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8000FFFFLL);
  if ( !RtlValidSid(qword_1804E01E0) )
  {
    v13 = 516;
LABEL_28:
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      -1);
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation-custom.cpp",
      (const char *)v11,
      v14);
    return v11;
  }
  v9 = RtlLengthSid(qword_1804E01E0);
  if ( v9 == 0x7FFFFFFF )
  {
    v13 = 494;
    goto LABEL_28;
  }
  v4 = -2147019873;
  if ( *(_QWORD *)a2 )
  {
    v10 = sqlite3_bind_blob(*(_QWORD *)a2, 3, qword_1804E01E0, v9, 0);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
    v11 = -2147019873;
  }
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_29;
  IsMultiUsersInSessionSku = RtlIsMultiUsersInSessionSku();
  if ( !*(_QWORD *)a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v14);
LABEL_8:
    v5 = 962;
    goto LABEL_9;
  }
  v6 = sqlite3_bind_int(*(_QWORD *)a2, 4, IsMultiUsersInSessionSku);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x18002c490  mov     [rsp+arg_0], rbx
0x18002c495  mov     [rsp+arg_8], rdi
0x18002c49a  push    r14
0x18002c49c  sub     rsp, 30h
0x18002c4a0  mov     r8, [rcx]
0x18002c4a3  mov     r14, rdx
0x18002c4a6  mov     rdi, rcx
0x18002c4a9  mov     edx, 1; int
0x18002c4ae  mov     rcx, r14; this
0x18002c4b1  mov     r8, [r8]; void *
0x18002c4b4  call    ?Bind@Statement@StateRepository@@QEAAJHQEAX@Z; StateRepository::Statement::Bind(int,void * const)
0x18002c4b9  mov     ebx, eax
0x18002c4bb  test    eax, eax
0x18002c4bd  js      loc_18002C642
0x18002c4c3  mov     rcx, [r14]
0x18002c4c6  test    rcx, rcx
0x18002c4c9  jnz     short loc_18002C542
0x18002c4cb  mov     rcx, [rsp+38h]; this
0x18002c4d0  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c4d7  mov     ebx, 8007139Fh
0x18002c4dc  mov     edx, 13Bh; void *
0x18002c4e1  mov     r9d, ebx; char *
0x18002c4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4e9  mov     edx, 3C0h
0x18002c4ee  jmp     short loc_18002C51B
0x18002c4f0  movzx   r8d, al
0x18002c4f4  mov     edx, 4
0x18002c4f9  call    cs:__imp_sqlite3_bind_int
0x18002c4ff  mov     ebx, eax
0x18002c501  test    eax, eax
0x18002c503  jle     short loc_18002C50E
0x18002c505  movzx   ebx, ax
0x18002c508  or      ebx, 87AF0000h
0x18002c50e  test    ebx, ebx
0x18002c510  jns     loc_18002C63B
0x18002c516  mov     edx, 3C2h; void *
0x18002c51b  mov     rcx, [rsp+38h]; this
0x18002c520  lea     r8, aOnecoreBaseApp_348; "onecore\\base\\appmodel\\staterepositor"...
0x18002c527  mov     r9d, ebx; char *
0x18002c52a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c52f  mov     eax, ebx
0x18002c531  mov     rbx, [rsp+38h+arg_0]
0x18002c536  mov     rdi, [rsp+38h+arg_8]
0x18002c53b  add     rsp, 30h
0x18002c53f  pop     r14
0x18002c541  retn
0x18002c542  mov     r8, [rdi+8]
0x18002c546  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c54a  mov     qword ptr [rsp+38h+var_18], r9; int
0x18002c54f  mov     r8, [r8]
0x18002c552  lea     edx, [r9+3]
0x18002c556  call    cs:__imp_sqlite3_bind_text16
0x18002c55c  mov     ebx, eax
0x18002c55e  test    eax, eax
0x18002c560  jle     short loc_18002C56B
0x18002c562  movzx   ebx, ax
0x18002c565  or      ebx, 87AF0000h
0x18002c56b  test    ebx, ebx
0x18002c56d  js      loc_18002C4E9
0x18002c573  lea     rdi, qword_1804E01E0
0x18002c57a  mov     rcx, rdi; Sid
0x18002c57d  call    cs:__imp_RtlValidSid
0x18002c583  test    al, al
0x18002c585  jz      loc_18002C64C
0x18002c58b  mov     rcx, rdi; Sid
0x18002c58e  call    cs:__imp_RtlValidSid
0x18002c594  test    al, al
0x18002c596  jz      loc_18002C66D
0x18002c59c  mov     rcx, rdi; Sid
0x18002c59f  call    cs:__imp_RtlLengthSid
0x18002c5a5  cmp     eax, 7FFFFFFFh
0x18002c5aa  jz      loc_18002C674
0x18002c5b0  mov     rcx, [r14]
0x18002c5b3  mov     ebx, 8007139Fh
0x18002c5b8  test    rcx, rcx
0x18002c5bb  jz      short loc_18002C61E
0x18002c5bd  mov     r9d, eax
0x18002c5c0  mov     qword ptr [rsp+38h+var_18], 0; int
0x18002c5c9  mov     r8, rdi
0x18002c5cc  mov     edx, 3
0x18002c5d1  call    cs:__imp_sqlite3_bind_blob
0x18002c5d7  mov     edi, eax
0x18002c5d9  test    eax, eax
0x18002c5db  jle     short loc_18002C5E6
0x18002c5dd  movzx   edi, ax
0x18002c5e0  or      edi, 87AF0000h
0x18002c5e6  test    edi, edi
0x18002c5e8  js      loc_18002C692
0x18002c5ee  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002c5f4  mov     rcx, [r14]
0x18002c5f7  test    rcx, rcx
0x18002c5fa  jnz     loc_18002C4F0
0x18002c600  mov     rcx, [rsp+38h]; this
0x18002c605  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c60c  mov     r9d, ebx; char *
0x18002c60f  mov     edx, 0A3h; void *
0x18002c614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c619  jmp     loc_18002C516
0x18002c61e  mov     rcx, [rsp+38h]; this
0x18002c623  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c62a  mov     r9d, ebx; char *
0x18002c62d  mov     edx, 1E4h; void *
0x18002c632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c637  mov     edi, ebx
0x18002c639  jmp     short loc_18002C5E6
0x18002c63b  xor     eax, eax
0x18002c63d  jmp     loc_18002C531
0x18002c642  mov     edx, 3BFh
0x18002c647  jmp     loc_18002C51B
0x18002c64c  mov     rcx, [rsp+38h]; this
0x18002c651  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c658  mov     r9d, 8000FFFFh; char *
0x18002c65e  mov     edx, 203h; void *
0x18002c663  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c668  jmp     loc_18002C58B
0x18002c66d  mov     edx, 204h
0x18002c672  jmp     short loc_18002C679
0x18002c674  mov     edx, 1EEh; void *
0x18002c679  mov     rcx, [rsp+38h]; this
0x18002c67e  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002c685  mov     edi, 80070057h
0x18002c68a  mov     r9d, edi; char *
0x18002c68d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c692  mov     rcx, [rsp+38h]; this
0x18002c697  lea     r8, aOnecoreBaseApp_348; "onecore\\base\\appmodel\\staterepositor"...
0x18002c69e  mov     r9d, edi; char *
0x18002c6a1  mov     edx, 3C1h; void *
0x18002c6a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6ab  mov     eax, edi
0x18002c6ad  jmp     loc_18002C531
```
