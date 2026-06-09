# StateRepository::StatementExecution::PrepareAndBindAndTryGet(StateRepository::Database &,char const *,char const *,__int64,StateRepository::Statement &,bool &)

- ea: `0x18002a160`
- end: `0x18002a266`
- name: `?PrepareAndBindAndTryGet@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEAVStatement@2@AEA_N@Z`
- size: `262`
- prototype: `__int64 __usercall@<rax>(StateRepository::StatementExecution *__hidden this@<rcx>, struct StateRepository::Database *@<rdx>, const char *@<r8>, const char *@<r9>, __int64, struct StateRepository::Statement *, bool *)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f654`
- `0x18001ff88`
- `0x180020594`
- `0x180021b7c`
- `0x180025fb4`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180019614`
- `0x18001b64c`
- `0x18001b810`
- `0x18001b920`
- `0x18002a160`

## string_xrefs

- `0x18002a19c`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002a1f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002a246`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::StatementExecution::PrepareAndBindAndTryGet(
        StateRepository::StatementExecution *this,
        struct StateRepository::Database *a2,
        struct StateRepository::Database *a3,
        const char *a4,
        struct StateRepository::Statement *a5,
        struct StateRepository::Statement *a6)
{
  int v9; // esi
  __int64 v10; // rdx
  int Row; // ebx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( *((_QWORD *)this + 1) && a3 )
    a2 = a3;
  v9 = StateRepository::Database::PrepareFromCache(this, (const char *)a2, a5);
  if ( v9 < 0 )
  {
    v10 = 164;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)v9,
      v15);
    return (unsigned int)v9;
  }
  v9 = StateRepository::Statement::Bind(a5, 1, (__int64)a4);
  if ( v9 < 0 )
  {
    v10 = 165;
    goto LABEL_6;
  }
  if ( a3 )
  {
    Row = StateRepository::Statement::BindIfWorkInProgress(a5, 2, *((_QWORD *)this + 1));
    if ( Row < 0 )
    {
      v13 = 168;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)Row,
        v15);
      return (unsigned int)Row;
    }
  }
  Row = StateRepository::Statement::FetchRow(a5, (bool *)a6);
  if ( Row < 0 )
  {
    v13 = 171;
    goto LABEL_12;
  }
  if ( !*(_BYTE *)a6 )
  {
    v14 = StateRepository::Database::AddToCache(this, a5);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)v14,
        v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a160  push    rbx
0x18002a162  push    rbp
0x18002a163  push    rsi
0x18002a164  push    r14
0x18002a166  sub     rsp, 28h
0x18002a16a  cmp     qword ptr [rcx+8], 0
0x18002a16f  mov     r14, r9
0x18002a172  mov     rbx, r8
0x18002a175  mov     rbp, rcx
0x18002a178  jz      short loc_18002A182
0x18002a17a  test    rbx, rbx
0x18002a17d  jz      short loc_18002A182
0x18002a17f  mov     rdx, rbx; char *
0x18002a182  mov     r8, [rsp+48h+arg_20]; struct StateRepository::Statement *
0x18002a187  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18002a18c  mov     esi, eax
0x18002a18e  test    eax, eax
0x18002a190  jns     short loc_18002A1B2
0x18002a192  mov     edx, 0A4h; void *
0x18002a197  mov     rcx, [rsp+48h]; this
0x18002a19c  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\staterepositor"...
0x18002a1a3  mov     r9d, esi; char *
0x18002a1a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1ab  mov     eax, esi
0x18002a1ad  jmp     loc_18002A25C
0x18002a1b2  mov     rcx, [rsp+48h+arg_20]; this
0x18002a1b7  mov     r8, r14; __int64
0x18002a1ba  mov     edx, 1; int
0x18002a1bf  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18002a1c4  mov     esi, eax
0x18002a1c6  test    eax, eax
0x18002a1c8  jns     short loc_18002A1D1
0x18002a1ca  mov     edx, 0A5h
0x18002a1cf  jmp     short loc_18002A197
0x18002a1d1  test    rbx, rbx
0x18002a1d4  jz      short loc_18002A20C
0x18002a1d6  mov     r8, [rbp+8]; __int64
0x18002a1da  mov     edx, 2; int
0x18002a1df  mov     rcx, [rsp+48h+arg_20]; this
0x18002a1e4  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x18002a1e9  mov     ebx, eax
0x18002a1eb  test    eax, eax
0x18002a1ed  jns     short loc_18002A20C
0x18002a1ef  mov     edx, 0A8h; void *
0x18002a1f4  mov     rcx, [rsp+48h]; this
0x18002a1f9  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\staterepositor"...
0x18002a200  mov     r9d, ebx; char *
0x18002a203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a208  mov     eax, ebx
0x18002a20a  jmp     short loc_18002A25C
0x18002a20c  mov     rsi, [rsp+48h+arg_28]
0x18002a211  mov     rcx, [rsp+48h+arg_20]; this
0x18002a216  mov     rdx, rsi; bool *
0x18002a219  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x18002a21e  mov     ebx, eax
0x18002a220  test    eax, eax
0x18002a222  jns     short loc_18002A22B
0x18002a224  mov     edx, 0ABh
0x18002a229  jmp     short loc_18002A1F4
0x18002a22b  cmp     byte ptr [rsi], 0
0x18002a22e  jnz     short loc_18002A25A
0x18002a230  mov     rdx, [rsp+48h+arg_20]; struct StateRepository::Statement *
0x18002a235  mov     rcx, rbp; this
0x18002a238  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18002a23d  test    eax, eax
0x18002a23f  jns     short loc_18002A25A
0x18002a241  mov     rcx, [rsp+48h]; this
0x18002a246  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\staterepositor"...
0x18002a24d  mov     r9d, eax; char *
0x18002a250  mov     edx, 0AFh; void *
0x18002a255  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a25a  xor     eax, eax
0x18002a25c  add     rsp, 28h
0x18002a260  pop     r14
0x18002a262  pop     rsi
0x18002a263  pop     rbp
0x18002a264  pop     rbx
0x18002a265  retn
```
