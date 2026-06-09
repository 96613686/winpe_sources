# ESESession::DeleteRecords(_INDEXTABLE_ID,void *,ulong)

- ea: `0x180016b68`
- end: `0x180016da9`
- name: `?DeleteRecords@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEAXK@Z`
- size: `577`
- prototype: `__int64 __fastcall(__int64, int, const void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001cec0`

## callees

- `0x180002da8`
- `0x180010638`
- `0x180013678`
- `0x180013f14`
- `0x180016860`
- `0x180016b68`
- `0x1800179c8`
- `0x180017b04`
- `0x180017d74`

## import_xrefs

- `ESENT!JetMove` at `0x180016ca5`
- `ESENT!JetMove` at `0x180016ca5`
- `ESENT!JetMakeKey` at `0x180016c4c`
- `ESENT!JetMakeKey` at `0x180016c4c`
- `ESENT!JetDelete` at `0x180016c87`
- `ESENT!JetDelete` at `0x180016c87`
- `ESENT!JetSetCurrentIndexA` at `0x180016c24`
- `ESENT!JetSetCurrentIndexA` at `0x180016c24`
- `ESENT!JetSeek` at `0x180016c69`
- `ESENT!JetSeek` at `0x180016c69`

## string_xrefs

- `0x180016d05`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180016d83`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180016bc3`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180016d60`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::DeleteRecords(__int64 a1, int a2, const void *a3)
{
  __int64 v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  int started; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 TableDefinitionFromTableId; // rax
  JET_ERR v13; // eax
  JET_ERR Key; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v21; // eax
  int v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h]
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+48h] [rbp-18h]
  __int64 v26; // [rsp+50h] [rbp-10h]

  v24 = *(_QWORD *)(a1 + 56);
  v5 = a2;
  v26 = a1 + 64;
  v25 = 0;
  v6 = auto_SessionContext::SetContext((auto_SessionContext *)&v24);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 481;
LABEL_5:
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v8);
LABEL_30:
    auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v24);
    return v7;
  }
  v6 = ESESession::OpenTable(a1, (unsigned int)v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 484;
    goto LABEL_5;
  }
  v22 = 0;
  v23 = a1;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v22);
  v7 = started;
  if ( started < 0 )
  {
    v10 = 490;
LABEL_8:
    v11 = 1;
    goto LABEL_28;
  }
  TableDefinitionFromTableId = GetTableDefinitionFromTableId((unsigned int)v5);
  v13 = JetSetCurrentIndexA(
          *(_QWORD *)(a1 + 56),
          *(_QWORD *)(a1 + 48 * v5 + 112),
          *(JET_PCSTR *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 56LL));
  if ( v13 < 0 )
  {
    started = MakeHresultFromJetError(v13);
    v10 = 498;
    goto LABEL_27;
  }
  Key = JetMakeKey(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v5 + 112), a3, 4u, 1u);
  if ( Key < 0 )
  {
    started = MakeHresultFromJetError(Key);
    v10 = 506;
    goto LABEL_27;
  }
  v15 = JetSeek(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v5 + 112), 0x21u);
  if ( v15 != -1601 )
  {
    if ( v15 >= 0 )
    {
      do
      {
        v16 = JetDelete(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v5 + 112));
        if ( v16 < 0 )
        {
          started = MakeHresultFromJetError(v16);
          v10 = 530;
          goto LABEL_27;
        }
        v17 = JetMove(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v5 + 112), 1, 0);
      }
      while ( !v17 );
      v18 = 0x80000000LL;
      if ( (int)(v17 + 0x80000000) >= 0 && v17 != -1603 )
      {
        started = MakeHresultFromJetError(v17);
        v10 = 544;
        goto LABEL_27;
      }
      LOBYTE(v18) = 1;
      started = ScopedEndTransaction<ESESession>::EndTransaction(&v22, v18);
      v7 = started;
      if ( started < 0 )
      {
        v10 = 549;
        goto LABEL_8;
      }
      goto LABEL_20;
    }
    started = MakeHresultFromJetError(v15);
    v10 = 522;
LABEL_27:
    v11 = 0;
    v7 = started;
LABEL_28:
    Log_HREvent(
      (unsigned int)started,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v10);
    v21 = ScopedEndTransaction<ESESession>::EndTransaction(&v22, 0);
    if ( v21 < 0 )
      Log_HREvent(
        (unsigned int)v21,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
        57);
    goto LABEL_30;
  }
LABEL_20:
  v19 = ScopedEndTransaction<ESESession>::EndTransaction(&v22, 0);
  if ( v19 < 0 )
    Log_HREvent(
      (unsigned int)v19,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v24);
  return 0;
}

```

## disassembly

```asm
0x180016b68  push    rbp
0x180016b6a  push    rbx
0x180016b6b  push    rsi
0x180016b6c  push    rdi
0x180016b6d  push    r14
0x180016b6f  mov     rbp, rsp
0x180016b72  sub     rsp, 60h
0x180016b76  mov     rax, [rcx+38h]
0x180016b7a  mov     rdi, rcx
0x180016b7d  mov     [rbp+var_20], rax
0x180016b81  mov     r14, r8
0x180016b84  lea     rax, [rcx+40h]
0x180016b88  movsxd  rsi, edx
0x180016b8b  lea     rcx, [rbp+var_20]; this
0x180016b8f  mov     [rbp+var_10], rax
0x180016b93  mov     [rbp+var_18], 0
0x180016b9a  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180016b9f  mov     ebx, eax
0x180016ba1  test    eax, eax
0x180016ba3  jns     short loc_180016BAD
0x180016ba5  mov     r9d, 1E1h
0x180016bab  jmp     short loc_180016BC3
0x180016bad  mov     edx, esi
0x180016baf  mov     rcx, rdi
0x180016bb2  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x180016bb7  mov     ebx, eax
0x180016bb9  test    eax, eax
0x180016bbb  jns     short loc_180016BDB
0x180016bbd  mov     r9d, 1E4h
0x180016bc3  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016bca  mov     edx, 1
0x180016bcf  mov     ecx, eax
0x180016bd1  call    Log_HREvent
0x180016bd6  jmp     loc_180016D93
0x180016bdb  lea     rcx, [rbp+var_30]
0x180016bdf  mov     [rbp+var_30], 0
0x180016be6  mov     [rbp+var_28], rdi
0x180016bea  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x180016bef  mov     ebx, eax
0x180016bf1  test    eax, eax
0x180016bf3  jns     short loc_180016C05
0x180016bf5  mov     r9d, 1EAh
0x180016bfb  mov     edx, 1
0x180016c00  jmp     loc_180016D60
0x180016c05  mov     ecx, esi
0x180016c07  call    ?GetTableDefinitionFromTableId@@YAPEBUDatabaseTableDefinition@@W4_INDEXTABLE_ID@@@Z; GetTableDefinitionFromTableId(_INDEXTABLE_ID)
0x180016c0c  mov     rcx, [rdi+38h]; sesid
0x180016c10  lea     rbx, [rsi+rsi*2]
0x180016c14  add     rbx, rbx
0x180016c17  mov     r8, [rax+20h]
0x180016c1b  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180016c20  mov     r8, [r8+38h]; szIndexName
0x180016c24  call    cs:__imp_JetSetCurrentIndexA
0x180016c2a  test    eax, eax
0x180016c2c  js      loc_180016D4F
0x180016c32  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180016c37  mov     r9d, 4; cbData
0x180016c3d  mov     rcx, [rdi+38h]; sesid
0x180016c41  mov     r8, r14; pvData
0x180016c44  mov     [rsp+60h+grbit], 1; grbit
0x180016c4c  call    cs:__imp_JetMakeKey
0x180016c52  test    eax, eax
0x180016c54  js      loc_180016D40
0x180016c5a  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180016c5f  mov     r8d, 21h ; '!'; grbit
0x180016c65  mov     rcx, [rdi+38h]; sesid
0x180016c69  call    cs:__imp_JetSeek
0x180016c6f  cmp     eax, 0FFFFF9BFh
0x180016c74  jz      short loc_180016CF0
0x180016c76  test    eax, eax
0x180016c78  js      loc_180016D31
0x180016c7e  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180016c83  mov     rcx, [rdi+38h]; sesid
0x180016c87  call    cs:__imp_JetDelete
0x180016c8d  test    eax, eax
0x180016c8f  js      loc_180016D22
0x180016c95  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180016c9a  xor     r9d, r9d; grbit
0x180016c9d  mov     rcx, [rdi+38h]; sesid
0x180016ca1  lea     r8d, [r9+1]; cRow
0x180016ca5  call    cs:__imp_JetMove
0x180016cab  test    eax, eax
0x180016cad  jz      short loc_180016C7E
0x180016caf  mov     edx, 80000000h
0x180016cb4  lea     ecx, [rax+rdx]
0x180016cb7  test    edx, ecx
0x180016cb9  jnz     short loc_180016CD4
0x180016cbb  cmp     eax, 0FFFFF9BDh
0x180016cc0  jz      short loc_180016CD4
0x180016cc2  mov     ecx, eax; int
0x180016cc4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016cc9  mov     r9d, 220h
0x180016ccf  jmp     loc_180016D5C
0x180016cd4  mov     dl, 1
0x180016cd6  lea     rcx, [rbp+var_30]
0x180016cda  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016cdf  mov     ebx, eax
0x180016ce1  test    eax, eax
0x180016ce3  jns     short loc_180016CF0
0x180016ce5  mov     r9d, 225h
0x180016ceb  jmp     loc_180016BFB
0x180016cf0  xor     edx, edx
0x180016cf2  lea     rcx, [rbp+var_30]
0x180016cf6  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016cfb  test    eax, eax
0x180016cfd  jns     short loc_180016D15
0x180016cff  mov     r9d, 39h ; '9'
0x180016d05  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016d0c  xor     edx, edx
0x180016d0e  mov     ecx, eax
0x180016d10  call    Log_HREvent
0x180016d15  lea     rcx, [rbp+var_20]; this
0x180016d19  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180016d1e  xor     eax, eax
0x180016d20  jmp     short loc_180016D9E
0x180016d22  mov     ecx, eax; int
0x180016d24  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016d29  mov     r9d, 212h
0x180016d2f  jmp     short loc_180016D5C
0x180016d31  mov     ecx, eax; int
0x180016d33  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016d38  mov     r9d, 20Ah
0x180016d3e  jmp     short loc_180016D5C
0x180016d40  mov     ecx, eax; int
0x180016d42  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016d47  mov     r9d, 1FAh
0x180016d4d  jmp     short loc_180016D5C
0x180016d4f  mov     ecx, eax; int
0x180016d51  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016d56  mov     r9d, 1F2h
0x180016d5c  xor     edx, edx
0x180016d5e  mov     ebx, eax
0x180016d60  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016d67  mov     ecx, eax
0x180016d69  call    Log_HREvent
0x180016d6e  xor     edx, edx
0x180016d70  lea     rcx, [rbp+var_30]
0x180016d74  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016d79  test    eax, eax
0x180016d7b  jns     short loc_180016D93
0x180016d7d  mov     r9d, 39h ; '9'
0x180016d83  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016d8a  xor     edx, edx
0x180016d8c  mov     ecx, eax
0x180016d8e  call    Log_HREvent
0x180016d93  lea     rcx, [rbp+var_20]; this
0x180016d97  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180016d9c  mov     eax, ebx
0x180016d9e  add     rsp, 60h
0x180016da2  pop     r14
0x180016da4  pop     rdi
0x180016da5  pop     rsi
0x180016da6  pop     rbx
0x180016da7  pop     rbp
0x180016da8  retn
```
