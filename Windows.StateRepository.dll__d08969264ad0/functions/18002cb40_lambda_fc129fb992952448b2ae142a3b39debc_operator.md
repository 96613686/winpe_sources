# _lambda_fc129fb992952448b2ae142a3b39debc_::operator()

- ea: `0x18002cb40`
- end: `0x18002cced`
- name: `_lambda_fc129fb992952448b2ae142a3b39debc_::operator()`
- size: `429`
- prototype: `__int64 __fastcall(__int64 **, StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002c290`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x18002c824`
- `0x18002cb40`
- `0x18002e574`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002cbdc`
- `ntdll!RtlLengthSid` at `0x18002cbdc`
- `ntdll!RtlValidSid` at `0x18002cbba`
- `ntdll!RtlValidSid` at `0x18002cbcb`
- `ntdll!RtlValidSid` at `0x18002cbba`
- `ntdll!RtlValidSid` at `0x18002cbcb`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002cbff`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002cbff`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002cb92`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18002cb92`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002cc8b`
- `StateRepository.Core!sqlite3_bind_int` at `0x18002cc8b`

## string_xrefs

- `0x18002cc12`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cc62`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cca9`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002ccca`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002cc3c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol-custom.cpp`

## pseudocode

```c
__int64 __fastcall lambda_fc129fb992952448b2ae142a3b39debc_::operator()(__int64 **a1, StateRepository::Statement *a2)
{
  int v4; // ebx
  int v5; // eax
  ULONG v6; // eax
  unsigned __int8 IsMultiUsersInSessionSku; // al
  __int64 v8; // rdx
  int v10; // eax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = StateRepository::Statement::Bind(a2, 1, **a1);
  if ( v4 < 0 )
  {
    v8 = 367;
    goto LABEL_14;
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
LABEL_16:
    v8 = 368;
    goto LABEL_14;
  }
  v11 = -1;
  v5 = sqlite3_bind_text16(*(_QWORD *)a2, 2, *a1[1]);
  v4 = v5;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_16;
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
  v6 = RtlLengthSid(qword_1804E01E0);
  v4 = StateRepository::Statement::BindAddress(a2, 3, v6, qword_1804E01E0);
  if ( v4 < 0 )
  {
LABEL_22:
    v8 = 369;
    goto LABEL_14;
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
LABEL_12:
    v8 = 370;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol-custom.cpp",
      (const char *)(unsigned int)v4,
      v11);
    return (unsigned int)v4;
  }
  v10 = sqlite3_bind_int(*(_QWORD *)a2, 4, IsMultiUsersInSessionSku);
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x87AF0000;
  if ( v4 < 0 )
    goto LABEL_12;
  return 0;
}

```

## disassembly

```asm
0x18002cb40  mov     [rsp+arg_0], rbx
0x18002cb45  mov     [rsp+arg_8], rsi
0x18002cb4a  push    rdi
0x18002cb4b  sub     rsp, 30h
0x18002cb4f  mov     r8, [rcx]
0x18002cb52  mov     rdi, rdx
0x18002cb55  mov     rsi, rcx
0x18002cb58  mov     edx, 1; int
0x18002cb5d  mov     rcx, rdi; this
0x18002cb60  mov     r8, [r8]; __int64
0x18002cb63  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18002cb68  mov     ebx, eax
0x18002cb6a  test    eax, eax
0x18002cb6c  js      loc_18002CC32
0x18002cb72  mov     rcx, [rdi]
0x18002cb75  test    rcx, rcx
0x18002cb78  jz      loc_18002CC5D
0x18002cb7e  mov     r8, [rsi+8]
0x18002cb82  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002cb86  mov     qword ptr [rsp+38h+var_18], r9; int
0x18002cb8b  mov     r8, [r8]
0x18002cb8e  lea     edx, [r9+3]
0x18002cb92  call    cs:__imp_sqlite3_bind_text16
0x18002cb98  mov     ebx, eax
0x18002cb9a  mov     esi, 87AF0000h
0x18002cb9f  test    eax, eax
0x18002cba1  jle     short loc_18002CBA8
0x18002cba3  movzx   ebx, ax
0x18002cba6  or      ebx, esi
0x18002cba8  test    ebx, ebx
0x18002cbaa  js      loc_18002CC7B
0x18002cbb0  lea     rbx, qword_1804E01E0
0x18002cbb7  mov     rcx, rbx; Sid
0x18002cbba  call    cs:__imp_RtlValidSid
0x18002cbc0  test    al, al
0x18002cbc2  jz      loc_18002CCA4
0x18002cbc8  mov     rcx, rbx; Sid
0x18002cbcb  call    cs:__imp_RtlValidSid
0x18002cbd1  test    al, al
0x18002cbd3  jz      loc_18002CCC5
0x18002cbd9  mov     rcx, rbx; Sid
0x18002cbdc  call    cs:__imp_RtlLengthSid
0x18002cbe2  mov     r8d, eax; unsigned __int64
0x18002cbe5  mov     r9, rbx; void *
0x18002cbe8  mov     edx, 3; int
0x18002cbed  mov     rcx, rdi; this
0x18002cbf0  call    ?BindAddress@Statement@StateRepository@@QEAAJH_KPEBX@Z; StateRepository::Statement::BindAddress(int,unsigned __int64,void const *)
0x18002cbf5  mov     ebx, eax
0x18002cbf7  test    eax, eax
0x18002cbf9  js      loc_18002CCE3
0x18002cbff  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002cc05  mov     rcx, [rdi]
0x18002cc08  test    rcx, rcx
0x18002cc0b  jnz     short loc_18002CC82
0x18002cc0d  mov     rcx, [rsp+38h]; this
0x18002cc12  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002cc19  mov     ebx, 8007139Fh
0x18002cc1e  mov     edx, 0A3h; void *
0x18002cc23  mov     r9d, ebx; char *
0x18002cc26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc2b  mov     edx, 172h
0x18002cc30  jmp     short loc_18002CC37
0x18002cc32  mov     edx, 16Fh; void *
0x18002cc37  mov     rcx, [rsp+38h]; this
0x18002cc3c  lea     r8, aOnecoreBaseApp_109; "onecore\\base\\appmodel\\staterepositor"...
0x18002cc43  mov     r9d, ebx; char *
0x18002cc46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc4b  mov     eax, ebx
0x18002cc4d  mov     rbx, [rsp+38h+arg_0]
0x18002cc52  mov     rsi, [rsp+38h+arg_8]
0x18002cc57  add     rsp, 30h
0x18002cc5b  pop     rdi
0x18002cc5c  retn
0x18002cc5d  mov     rcx, [rsp+38h]; this
0x18002cc62  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002cc69  mov     ebx, 8007139Fh
0x18002cc6e  mov     edx, 13Bh; void *
0x18002cc73  mov     r9d, ebx; char *
0x18002cc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc7b  mov     edx, 170h
0x18002cc80  jmp     short loc_18002CC37
0x18002cc82  movzx   r8d, al
0x18002cc86  mov     edx, 4
0x18002cc8b  call    cs:__imp_sqlite3_bind_int
0x18002cc91  mov     ebx, eax
0x18002cc93  test    eax, eax
0x18002cc95  jle     short loc_18002CC9C
0x18002cc97  movzx   ebx, ax
0x18002cc9a  or      ebx, esi
0x18002cc9c  test    ebx, ebx
0x18002cc9e  js      short loc_18002CC2B
0x18002cca0  xor     eax, eax
0x18002cca2  jmp     short loc_18002CC4D
0x18002cca4  mov     rcx, [rsp+38h]; this
0x18002cca9  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002ccb0  mov     r9d, 8000FFFFh; char *
0x18002ccb6  mov     edx, 203h; void *
0x18002ccbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ccc0  jmp     loc_18002CBC8
0x18002ccc5  mov     rcx, [rsp+38h]; this
0x18002ccca  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18002ccd1  mov     ebx, 80070057h
0x18002ccd6  mov     edx, 204h; void *
0x18002ccdb  mov     r9d, ebx; char *
0x18002ccde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cce3  mov     edx, 171h
0x18002cce8  jmp     loc_18002CC37
```
