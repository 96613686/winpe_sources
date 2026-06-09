# Database::CreateTable(tagJET_TABLECREATE_W *)

- ea: `0x1800102d8`
- end: `0x1800104fa`
- name: `?CreateTable@Database@@QEAAJPEAUtagJET_TABLECREATE_W@@@Z`
- size: `546`
- prototype: `int(Database *__hidden this, struct tagJET_TABLECREATE_W *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800109d8`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c040`
- `0x1800100c4`
- `0x1800102d8`
- `0x1800114e4`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x180010485`
- `ESENT!JetOpenTableW` at `0x180010485`
- `ESENT!JetCreateTableColumnIndexW` at `0x18001049e`
- `ESENT!JetCreateTableColumnIndexW` at `0x18001049e`
- `ESENT!JetBeginSessionW` at `0x1800103cb`
- `ESENT!JetBeginSessionW` at `0x1800103cb`
- `ESENT!JetOpenDatabaseW` at `0x180010420`
- `ESENT!JetOpenDatabaseW` at `0x180010420`

## string_xrefs

- `0x180010320`: `Database::CreateTable`
- `0x18001033a`: `Database::CreateTable for db=%s, table=%s failed! hr=0x%x.`

## pseudocode

```c
__int64 __fastcall Database::CreateTable(Database *this, struct tagJET_TABLECREATE_W *a2)
{
  int v4; // ebx
  DSLogger *v5; // rax
  DSLogger *v7; // rax
  JET_ERR v8; // esi
  DSLogger *v9; // rax
  JET_ERR v10; // esi
  DSLogger *v11; // rax
  JET_ERR TableColumnIndexW; // esi
  DSLogger *v13; // rax
  unsigned int v14; // r8d
  JET_GRBIT grbit[2]; // [rsp+20h] [rbp-40h]
  JET_GRBIT grbita[2]; // [rsp+20h] [rbp-40h]
  JET_GRBIT grbitb[2]; // [rsp+20h] [rbp-40h]
  JET_TABLEID *ptableid; // [rsp+30h] [rbp-30h]
  _QWORD v19[3]; // [rsp+40h] [rbp-20h] BYREF
  char v20; // [rsp+58h] [rbp-8h]
  JET_DBID pdbid; // [rsp+98h] [rbp+38h] BYREF
  JET_SESID psesid; // [rsp+A0h] [rbp+40h] BYREF
  JET_TABLEID v23; // [rsp+A8h] [rbp+48h] BYREF

  pdbid = -1;
  v23 = -1;
  psesid = -1;
  v19[0] = &psesid;
  v19[1] = &v23;
  v19[2] = &pdbid;
  v20 = 1;
  if ( a2 && a2->rgcolumncreate && a2->rgindexcreate )
  {
    v4 = 0;
    v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    DSLogger::LogInformation(v7, L"Database::CreateTable", 0x14Fu, L"Creating table %s.", a2->szTableName);
    v8 = JetBeginSessionW(*((_QWORD *)this + 6), &psesid, &szUserName, &szUserName);
    if ( v8 >= 0
      || (v9 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(),
          grbit[0] = v8,
          DSLogger::LogError(v9, L"Database::CreateTable", 0x153u, L"JET_ERR : %d", *(_QWORD *)grbit),
          v4 = JetToHResult(v8),
          v4 >= 0) )
    {
      v10 = JetOpenDatabaseW(psesid, *((JET_PCWSTR *)this + 9), 0, &pdbid, 0);
      if ( v10 >= 0
        || (v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(),
            grbita[0] = v10,
            DSLogger::LogError(v11, L"Database::CreateTable", 0x154u, L"JET_ERR : %d", *(_QWORD *)grbita),
            v4 = JetToHResult(v10),
            v4 >= 0) )
      {
        TableColumnIndexW = JetOpenTableW(psesid, pdbid, a2->szTableName, 0, 0, 0, &v23);
        if ( TableColumnIndexW == -1305 )
        {
          TableColumnIndexW = JetCreateTableColumnIndexW(psesid, pdbid, a2);
          if ( TableColumnIndexW >= 0 )
            goto LABEL_4;
          v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
          v14 = 347;
        }
        else
        {
          if ( TableColumnIndexW >= 0 )
            goto LABEL_4;
          v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
          v14 = 352;
        }
        grbitb[0] = TableColumnIndexW;
        DSLogger::LogError(v13, L"Database::CreateTable", v14, L"JET_ERR : %d", *(_QWORD *)grbitb);
        v4 = JetToHResult(TableColumnIndexW);
        if ( v4 >= 0 )
          goto LABEL_4;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  v5 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  LODWORD(ptableid) = v4;
  DSLogger::LogError(
    v5,
    L"Database::CreateTable",
    0x167u,
    L"Database::CreateTable for db=%s, table=%s failed! hr=0x%x.",
    *((_QWORD *)this + 9),
    a2->szTableName,
    ptableid);
LABEL_4:
  tlx::_UndoSolo__lambda_82bef2c1280314a5e844aef45f71084d___::__UndoSolo__lambda_82bef2c1280314a5e844aef45f71084d___(v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800102d8  mov     [rsp-28h+arg_0], rbx
0x1800102dd  push    rbp
0x1800102de  push    rsi
0x1800102df  push    rdi
0x1800102e0  push    r12
0x1800102e2  push    r14
0x1800102e4  mov     rbp, rsp
0x1800102e7  sub     rsp, 60h
0x1800102eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800102ef  mov     [rbp+pdbid], 0FFFFFFFFh
0x1800102f6  mov     [rbp+arg_18], rax
0x1800102fa  mov     rdi, rdx
0x1800102fd  mov     [rbp+psesid], rax
0x180010301  lea     rax, [rbp+psesid]
0x180010305  mov     [rbp+var_20], rax
0x180010309  lea     rax, [rbp+arg_18]
0x18001030d  mov     [rbp+var_18], rax
0x180010311  lea     rax, [rbp+pdbid]
0x180010315  mov     [rbp+var_10], rax
0x180010319  mov     r14, rcx
0x18001031c  mov     [rbp+var_8], 1
0x180010320  lea     r12, aDatabaseCreate; "Database::CreateTable"
0x180010327  test    rdx, rdx
0x18001032a  jnz     short loc_180010383
0x18001032c  mov     ebx, 80070057h
0x180010331  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010336  mov     rcx, [rdi+8]
0x18001033a  lea     r9, aDatabaseCreate_1; "Database::CreateTable for db=%s, table="...
0x180010341  mov     dword ptr [rsp+60h+ptableid], ebx
0x180010345  mov     r8d, 167h; unsigned int
0x18001034b  mov     qword ptr [rsp+60h+var_38], rcx
0x180010350  mov     rdx, r12; unsigned __int16 *
0x180010353  mov     rcx, [r14+48h]
0x180010357  mov     qword ptr [rsp+60h+grbit], rcx
0x18001035c  mov     rcx, rax; this
0x18001035f  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010364  lea     rcx, [rbp+var_20]
0x180010368  call    tlx___UndoSolo__lambda_82bef2c1280314a5e844aef45f71084d_______UndoSolo__lambda_82bef2c1280314a5e844aef45f71084d___
0x18001036d  mov     eax, ebx
0x18001036f  mov     rbx, [rsp+60h+arg_0]
0x180010377  add     rsp, 60h
0x18001037b  pop     r14
0x18001037d  pop     r12
0x18001037f  pop     rdi
0x180010380  pop     rsi
0x180010381  pop     rbp
0x180010382  retn
0x180010383  cmp     qword ptr [rdx+20h], 0
0x180010388  jz      short loc_18001032C
0x18001038a  cmp     qword ptr [rdx+30h], 0
0x18001038f  jz      short loc_18001032C
0x180010391  xor     ebx, ebx
0x180010393  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010398  mov     rcx, rax; this
0x18001039b  lea     r9, aCreatingTableS; "Creating table %s."
0x1800103a2  mov     rax, [rdi+8]
0x1800103a6  mov     r8d, 14Fh; unsigned int
0x1800103ac  mov     rdx, r12; unsigned __int16 *
0x1800103af  mov     qword ptr [rsp+60h+grbit], rax
0x1800103b4  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x1800103b9  mov     rcx, [r14+30h]; instance
0x1800103bd  lea     r8, szUserName; szUserName
0x1800103c4  mov     r9, r8; szPassword
0x1800103c7  lea     rdx, [rbp+psesid]; psesid
0x1800103cb  call    cs:__imp_JetBeginSessionW
0x1800103d1  mov     esi, eax
0x1800103d3  test    eax, eax
0x1800103d5  jns     short loc_180010409
0x1800103d7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800103dc  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800103e3  mov     [rsp+60h+grbit], esi
0x1800103e7  mov     r8d, 153h; unsigned int
0x1800103ed  mov     rdx, r12; unsigned __int16 *
0x1800103f0  mov     rcx, rax; this
0x1800103f3  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800103f8  mov     ecx, esi; int
0x1800103fa  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800103ff  mov     ebx, eax
0x180010401  test    eax, eax
0x180010403  js      loc_180010331
0x180010409  mov     rdx, [r14+48h]; szFilename
0x18001040d  lea     r9, [rbp+pdbid]; pdbid
0x180010411  mov     rcx, [rbp+psesid]; sesid
0x180010415  xor     r8d, r8d; szConnect
0x180010418  mov     [rsp+60h+grbit], 0; grbit
0x180010420  call    cs:__imp_JetOpenDatabaseW
0x180010426  mov     esi, eax
0x180010428  test    eax, eax
0x18001042a  jns     short loc_18001045E
0x18001042c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010431  lea     r9, aJetErrD; "JET_ERR : %d"
0x180010438  mov     [rsp+60h+grbit], esi
0x18001043c  mov     r8d, 154h; unsigned int
0x180010442  mov     rdx, r12; unsigned __int16 *
0x180010445  mov     rcx, rax; this
0x180010448  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001044d  mov     ecx, esi; int
0x18001044f  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010454  mov     ebx, eax
0x180010456  test    eax, eax
0x180010458  js      loc_180010331
0x18001045e  mov     r8, [rdi+8]; szTableName
0x180010462  lea     rax, [rbp+arg_18]
0x180010466  mov     edx, [rbp+pdbid]; dbid
0x180010469  xor     r9d, r9d; pvParameters
0x18001046c  mov     rcx, [rbp+psesid]; sesid
0x180010470  mov     [rsp+60h+ptableid], rax; ptableid
0x180010475  mov     [rsp+60h+var_38], 0; grbit
0x18001047d  mov     [rsp+60h+grbit], 0; cbParameters
0x180010485  call    cs:__imp_JetOpenTableW
0x18001048b  mov     esi, eax
0x18001048d  cmp     eax, 0FFFFFAE7h
0x180010492  jnz     short loc_1800104E5
0x180010494  mov     edx, [rbp+pdbid]; dbid
0x180010497  mov     r8, rdi; ptablecreate
0x18001049a  mov     rcx, [rbp+psesid]; sesid
0x18001049e  call    cs:__imp_JetCreateTableColumnIndexW
0x1800104a4  mov     esi, eax
0x1800104a6  test    eax, eax
0x1800104a8  jns     loc_180010364
0x1800104ae  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800104b3  mov     r8d, 15Bh; unsigned int
0x1800104b9  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800104c0  mov     [rsp+60h+grbit], esi
0x1800104c4  mov     rdx, r12; unsigned __int16 *
0x1800104c7  mov     rcx, rax; this
0x1800104ca  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800104cf  mov     ecx, esi; int
0x1800104d1  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800104d6  mov     ebx, eax
0x1800104d8  test    eax, eax
0x1800104da  js      loc_180010331
0x1800104e0  jmp     loc_180010364
0x1800104e5  test    esi, esi
0x1800104e7  jns     loc_180010364
0x1800104ed  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800104f2  mov     r8d, 160h
0x1800104f8  jmp     short loc_1800104B9
```
