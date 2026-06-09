# ESESession::FindNext(_INDEXTABLE_ID,JET_RETRIEVECOLUMN *,ulong,int *)

- ea: `0x180017638`
- end: `0x180017743`
- name: `?FindNext@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEAUJET_RETRIEVECOLUMN@@KPEAH@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, int, JET_RETRIEVECOLUMN *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001cf00`

## callees

- `0x180002da8`
- `0x180010638`
- `0x180016860`
- `0x180017638`
- `0x180017b04`
- `0x180017d74`

## import_xrefs

- `ESENT!JetMove` at `0x1800176d5`
- `ESENT!JetMove` at `0x1800176d5`
- `ESENT!JetRetrieveColumns` at `0x18001772a`
- `ESENT!JetRetrieveColumns` at `0x18001772a`

## string_xrefs

- `0x1800176a7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::FindNext(__int64 a1, int a2, JET_RETRIEVECOLUMN *a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // rbp
  int HresultFromJetError; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  JET_ERR v12; // eax
  JET_ERR Columns; // eax
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  int v16; // [rsp+38h] [rbp-40h]
  __int64 v17; // [rsp+40h] [rbp-38h]

  v15 = *(_QWORD *)(a1 + 56);
  v17 = a1 + 64;
  v7 = a2;
  *a5 = 0;
  v16 = 0;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v15);
  v9 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    HresultFromJetError = ESESession::OpenTable(a1, (unsigned int)v7);
    v9 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v10 = 688;
      goto LABEL_5;
    }
    v12 = JetMove(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v7 + 112), 1, 0);
    if ( v12 == -1603 )
    {
      *a5 = 1;
LABEL_9:
      v9 = 0;
      goto LABEL_10;
    }
    if ( v12 >= 0 )
    {
      Columns = JetRetrieveColumns(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v7 + 112), a3, 1u);
      if ( Columns >= 0 )
        goto LABEL_9;
      HresultFromJetError = MakeHresultFromJetError(Columns);
      v10 = 712;
    }
    else
    {
      HresultFromJetError = MakeHresultFromJetError(v12);
      v10 = 705;
    }
    v9 = HresultFromJetError;
    v11 = 0;
    goto LABEL_6;
  }
  v10 = 685;
LABEL_5:
  v11 = 1;
LABEL_6:
  Log_HREvent(
    (unsigned int)HresultFromJetError,
    v11,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v10);
LABEL_10:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v15);
  return v9;
}

```

## disassembly

```asm
0x180017638  push    rbx
0x18001763a  push    rbp
0x18001763b  push    rsi
0x18001763c  push    rdi
0x18001763d  push    r14
0x18001763f  sub     rsp, 50h
0x180017643  mov     rax, [rcx+38h]
0x180017647  mov     rdi, rcx
0x18001764a  mov     rsi, [rsp+78h+arg_20]
0x180017652  mov     r14, r8
0x180017655  mov     [rsp+78h+var_48], rax
0x18001765a  lea     rax, [rcx+40h]
0x18001765e  lea     rcx, [rsp+78h+var_48]; this
0x180017663  mov     [rsp+78h+var_38], rax
0x180017668  movsxd  rbp, edx
0x18001766b  mov     dword ptr [rsi], 0
0x180017671  mov     [rsp+78h+var_40], 0
0x180017679  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x18001767e  mov     ebx, eax
0x180017680  test    eax, eax
0x180017682  jns     short loc_18001768C
0x180017684  mov     r9d, 2ADh
0x18001768a  jmp     short loc_1800176A2
0x18001768c  mov     edx, ebp
0x18001768e  mov     rcx, rdi
0x180017691  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x180017696  mov     ebx, eax
0x180017698  test    eax, eax
0x18001769a  jns     short loc_1800176B7
0x18001769c  mov     r9d, 2B0h
0x1800176a2  mov     edx, 1
0x1800176a7  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800176ae  mov     ecx, eax
0x1800176b0  call    Log_HREvent
0x1800176b5  jmp     short loc_1800176EA
0x1800176b7  mov     rcx, [rdi+38h]; sesid
0x1800176bb  lea     rbx, ds:0[rbp*2]
0x1800176c3  xor     r9d, r9d; grbit
0x1800176c6  add     rbx, rbp
0x1800176c9  add     rbx, rbx
0x1800176cc  lea     r8d, [r9+1]; cRow
0x1800176d0  mov     rdx, [rdi+rbx*8+70h]; tableid
0x1800176d5  call    cs:__imp_JetMove
0x1800176db  cmp     eax, 0FFFFF9BDh
0x1800176e0  jnz     short loc_180017701
0x1800176e2  mov     dword ptr [rsi], 1
0x1800176e8  xor     ebx, ebx
0x1800176ea  lea     rcx, [rsp+78h+var_48]; this
0x1800176ef  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x1800176f4  mov     eax, ebx
0x1800176f6  add     rsp, 50h
0x1800176fa  pop     r14
0x1800176fc  pop     rdi
0x1800176fd  pop     rsi
0x1800176fe  pop     rbp
0x1800176ff  pop     rbx
0x180017700  retn
0x180017701  test    eax, eax
0x180017703  jns     short loc_180017718
0x180017705  mov     ecx, eax; int
0x180017707  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001770c  mov     r9d, 2C1h
0x180017712  mov     ebx, eax
0x180017714  xor     edx, edx
0x180017716  jmp     short loc_1800176A7
0x180017718  mov     rdx, [rdi+rbx*8+70h]; tableid
0x18001771d  mov     r9d, 1; cretrievecolumn
0x180017723  mov     rcx, [rdi+38h]; sesid
0x180017727  mov     r8, r14; pretrievecolumn
0x18001772a  call    cs:__imp_JetRetrieveColumns
0x180017730  test    eax, eax
0x180017732  jns     short loc_1800176E8
0x180017734  mov     ecx, eax; int
0x180017736  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001773b  mov     r9d, 2C8h
0x180017741  jmp     short loc_180017712
```
