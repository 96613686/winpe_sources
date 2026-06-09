# _lambda_4a36cf2eba089cc10d3a208328bbd820_::operator()

- ea: `0x18002ce20`
- end: `0x18002cfc7`
- name: `_lambda_4a36cf2eba089cc10d3a208328bbd820_::operator()`
- size: `423`
- prototype: `__int64 __fastcall(__int64 **, StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cdc0`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x18002c824`
- `0x18002ce20`
- `0x18002e574`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002cf00`
- `ntdll!RtlLengthSid` at `0x18002cf00`
- `ntdll!RtlValidSid` at `0x18002cede`
- `ntdll!RtlValidSid` at `0x18002ceef`
- `ntdll!RtlValidSid` at `0x18002cede`
- `ntdll!RtlValidSid` at `0x18002ceef`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002cf23`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002cf23`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002ceba`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002ceba`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002cf3a`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002cf3a`

## string_xrefs

- `0x18002ce5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cf5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cf83`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cfa4`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002ce85`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol-custom.cpp`

## pseudocode

```c
__int64 __fastcall lambda_4a36cf2eba089cc10d3a208328bbd820_::operator()(__int64 **a1, StateRepository::Statement *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  ULONG v8; // eax
  unsigned __int8 IsMultiUsersInSessionSku; // al
  int v10; // eax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = StateRepository::Statement::Bind(a2, 1, **a1);
  if ( v4 < 0 )
  {
    v5 = 184;
    goto LABEL_6;
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
    v5 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol-custom.cpp",
      (const char *)(unsigned int)v4,
      v11);
    return (unsigned int)v4;
  }
  v11 = -1;
  v7 = sqlite3_bind_text16(*(_QWORD *)a2, 2, *a1[1]);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x87AF0000;
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
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      -1);
    goto LABEL_22;
  }
  v8 = RtlLengthSid(qword_1804E01E0);
  v4 = StateRepository::Statement::BindAddress(a2, 3, v8, qword_1804E01E0);
  if ( v4 < 0 )
  {
LABEL_22:
    v5 = 186;
    goto LABEL_6;
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
      -1);
LABEL_20:
    v5 = 187;
    goto LABEL_6;
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
0x18002ce20  mov     [rsp+arg_0], rbx
0x18002ce25  mov     [rsp+arg_8], rsi
0x18002ce2a  push    rdi
0x18002ce2b  sub     rsp, 30h
0x18002ce2f  mov     r8, [rcx]
0x18002ce32  mov     rdi, rdx
0x18002ce35  mov     rsi, rcx
0x18002ce38  mov     edx, 1; int
0x18002ce3d  mov     rcx, rdi; this
0x18002ce40  mov     r8, [r8]; __int64
0x18002ce43  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18002ce48  mov     ebx, eax
0x18002ce4a  test    eax, eax
0x18002ce4c  js      short loc_18002CE7B
0x18002ce4e  mov     rcx, [rdi]
0x18002ce51  test    rcx, rcx
0x18002ce54  jnz     short loc_18002CEA6
0x18002ce56  mov     rcx, [rsp+38h]; this
0x18002ce5b  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002ce62  mov     ebx, 8007139Fh
0x18002ce67  mov     edx, 13Bh; void *
0x18002ce6c  mov     r9d, ebx; char *
0x18002ce6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce74  mov     edx, 0B9h
0x18002ce79  jmp     short loc_18002CE80
0x18002ce7b  mov     edx, 0B8h; void *
0x18002ce80  mov     rcx, [rsp+38h]; this
0x18002ce85  lea     r8, aOnecoreBaseApp_109; "onecore\\base\\appmodel\\staterepositor"...
0x18002ce8c  mov     r9d, ebx; char *
0x18002ce8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce94  mov     eax, ebx
0x18002ce96  mov     rbx, [rsp+38h+arg_0]
0x18002ce9b  mov     rsi, [rsp+38h+arg_8]
0x18002cea0  add     rsp, 30h
0x18002cea4  pop     rdi
0x18002cea5  retn
0x18002cea6  mov     r8, [rsi+8]
0x18002ceaa  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ceae  mov     qword ptr [rsp+38h+var_18], r9; int
0x18002ceb3  mov     r8, [r8]
0x18002ceb6  lea     edx, [r9+3]
0x18002ceba  call    cs:__imp_sqlite3_bind_text16
0x18002cec0  mov     ebx, eax
0x18002cec2  mov     esi, 87AF0000h
0x18002cec7  test    eax, eax
0x18002cec9  jle     short loc_18002CED0
0x18002cecb  movzx   ebx, ax
0x18002cece  or      ebx, esi
0x18002ced0  test    ebx, ebx
0x18002ced2  js      short loc_18002CE74
0x18002ced4  lea     rbx, qword_1804E01E0
0x18002cedb  mov     rcx, rbx; Sid
0x18002cede  call    cs:__imp_RtlValidSid
0x18002cee4  test    al, al
0x18002cee6  jz      loc_18002CF7E
0x18002ceec  mov     rcx, rbx; Sid
0x18002ceef  call    cs:__imp_RtlValidSid
0x18002cef5  test    al, al
0x18002cef7  jz      loc_18002CF9F
0x18002cefd  mov     rcx, rbx; Sid
0x18002cf00  call    cs:__imp_RtlLengthSid
0x18002cf06  mov     r8d, eax; unsigned __int64
0x18002cf09  mov     r9, rbx; void *
0x18002cf0c  mov     edx, 3; int
0x18002cf11  mov     rcx, rdi; this
0x18002cf14  call    ?BindAddress@Statement@StateRepository@@QEAAJH_KPEBX@Z; StateRepository::Statement::BindAddress(int,unsigned __int64,void const *)
0x18002cf19  mov     ebx, eax
0x18002cf1b  test    eax, eax
0x18002cf1d  js      loc_18002CFBD
0x18002cf23  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002cf29  mov     rcx, [rdi]
0x18002cf2c  test    rcx, rcx
0x18002cf2f  jz      short loc_18002CF56
0x18002cf31  movzx   r8d, al
0x18002cf35  mov     edx, 4
0x18002cf3a  call    cs:__imp_sqlite3_bind_int
0x18002cf40  mov     ebx, eax
0x18002cf42  test    eax, eax
0x18002cf44  jle     short loc_18002CF4B
0x18002cf46  movzx   ebx, ax
0x18002cf49  or      ebx, esi
0x18002cf4b  test    ebx, ebx
0x18002cf4d  js      short loc_18002CF74
0x18002cf4f  xor     eax, eax
0x18002cf51  jmp     loc_18002CE96
0x18002cf56  mov     rcx, [rsp+38h]; this
0x18002cf5b  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002cf62  mov     ebx, 8007139Fh
0x18002cf67  mov     edx, 0A3h; void *
0x18002cf6c  mov     r9d, ebx; char *
0x18002cf6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf74  mov     edx, 0BBh
0x18002cf79  jmp     loc_18002CE80
0x18002cf7e  mov     rcx, [rsp+38h]; this
0x18002cf83  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002cf8a  mov     r9d, 8000FFFFh; char *
0x18002cf90  mov     edx, 203h; void *
0x18002cf95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cf9a  jmp     loc_18002CEEC
0x18002cf9f  mov     rcx, [rsp+38h]; this
0x18002cfa4  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002cfab  mov     ebx, 80070057h
0x18002cfb0  mov     edx, 204h; void *
0x18002cfb5  mov     r9d, ebx; char *
0x18002cfb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfbd  mov     edx, 0BAh
0x18002cfc2  jmp     loc_18002CE80
```
