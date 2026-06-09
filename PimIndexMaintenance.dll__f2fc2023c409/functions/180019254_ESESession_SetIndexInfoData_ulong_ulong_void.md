# ESESession::_SetIndexInfoData(ulong,ulong,void *)

- ea: `0x180019254`
- end: `0x1800195c6`
- name: `?_SetIndexInfoData@ESESession@@AEAAJKKPEAX@Z`
- size: `882`
- prototype: `__int64 __fastcall(ESESession *this, JET_COLUMNID, unsigned int, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180017e2c`
- `0x1800183b4`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x180013678`
- `0x180013f14`
- `0x180016860`
- `0x180017d20`
- `0x180017d74`
- `0x180019254`

## import_xrefs

- `ESENT!JetMove` at `0x18001935b`
- `ESENT!JetMove` at `0x18001935b`
- `ESENT!JetPrepareUpdate` at `0x1800193b4`
- `ESENT!JetPrepareUpdate` at `0x1800194fd`
- `ESENT!JetPrepareUpdate` at `0x18001955d`
- `ESENT!JetPrepareUpdate` at `0x1800193b4`
- `ESENT!JetPrepareUpdate` at `0x1800194fd`
- `ESENT!JetPrepareUpdate` at `0x18001955d`
- `ESENT!JetSetColumn` at `0x18001944a`
- `ESENT!JetSetColumn` at `0x18001944a`
- `ESENT!JetUpdate` at `0x18001949c`
- `ESENT!JetUpdate` at `0x18001949c`

## string_xrefs

- `0x180019305`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180019539`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180019599`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x1800192a1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800192d9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x18001938a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800194e1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800193cf`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x180019473`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x180019510`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x180019570`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
__int64 __fastcall ESESession::_SetIndexInfoData(ESESession *this, JET_COLUMNID a2, unsigned int a3, void *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int started; // eax
  __int64 v11; // r9
  const char *v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  JET_ERR v16; // ebx
  int v17; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v19; // r9
  JET_ERR v20; // eax
  int v21; // eax
  JET_ERR v22; // eax
  __int64 v23; // rcx
  int v24; // ebx
  JET_TABLEID v25; // rsi
  JET_SESID v26; // r14
  JET_ERR v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  JET_ERR v34; // eax
  unsigned int v35; // eax
  int v36; // eax
  JET_ERR v37; // eax
  unsigned int v38; // eax
  int v39; // eax
  int v41; // [rsp+40h] [rbp-19h] BYREF
  ESESession *v42; // [rsp+48h] [rbp-11h]
  JET_SESID sesid; // [rsp+50h] [rbp-9h] BYREF
  JET_TABLEID tableid; // [rsp+58h] [rbp-1h]
  int v45; // [rsp+60h] [rbp+7h]
  __int64 v46; // [rsp+68h] [rbp+Fh] BYREF
  int v47; // [rsp+70h] [rbp+17h]
  char *v48; // [rsp+78h] [rbp+1Fh]

  v46 = *((_QWORD *)this + 7);
  v47 = 0;
  v48 = (char *)this + 64;
  v8 = auto_SessionContext::SetContext((auto_SessionContext *)&v46);
  v9 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      321);
    goto LABEL_43;
  }
  v41 = 0;
  v42 = this;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v41);
  v9 = started;
  if ( started < 0 )
  {
    v11 = 327;
    v12 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp";
    v13 = 1;
    goto LABEL_5;
  }
  sesid = *((_QWORD *)this + 7);
  tableid = *((_QWORD *)this + 5);
  v45 = 0;
  v15 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 2u);
  if ( v15 == -1603 )
  {
    v16 = JetMove(*((_QWORD *)this + 7), *((_QWORD *)this + 5), 0x80000000, 0);
    if ( v16 == -1603 )
    {
      v17 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 0);
      if ( v17 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v17);
        v19 = 350;
        goto LABEL_12;
      }
    }
    else
    {
      v21 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 2u);
      if ( v21 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v21);
        v19 = 357;
        goto LABEL_12;
      }
      if ( v16 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v16);
        v19 = 358;
        goto LABEL_12;
      }
    }
  }
  else if ( v15 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v15);
    v19 = 363;
    goto LABEL_12;
  }
  v22 = JetSetColumn(*((_QWORD *)this + 4), *((_QWORD *)this + 5), a2, a4, a3, 0, 0);
  if ( v22 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v22);
    v19 = 370;
LABEL_12:
    v9 = HresultFromJetError;
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v19);
    if ( !v45 || (v20 = JetPrepareUpdate(sesid, tableid, 3u), v20 >= 0) )
    {
LABEL_6:
      v14 = ScopedEndTransaction<ESESession>::EndTransaction(&v41, 0);
      if ( v14 < 0 )
        Log_HREvent(
          (unsigned int)v14,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      goto LABEL_43;
    }
    started = MakeHresultFromJetError(v20);
    v11 = 577;
    v12 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h";
    v13 = 0;
LABEL_5:
    Log_HREvent((unsigned int)started, v13, v12, v11);
    goto LABEL_6;
  }
  v24 = v45;
  if ( !v45 )
    Log_AssertionEvent(v23, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 561);
  v25 = tableid;
  v26 = sesid;
  v27 = JetUpdate(sesid, tableid, 0, 0, 0);
  if ( v27 )
  {
    if ( v27 < 0 )
    {
      v30 = MakeHresultFromJetError(v27);
      v31 = 372;
      v32 = 0;
      v33 = v30;
LABEL_31:
      Log_HREvent(
        v33,
        v32,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        v31);
      if ( v24 )
      {
        v34 = JetPrepareUpdate(v26, v25, 3u);
        if ( v34 < 0 )
        {
          v35 = MakeHresultFromJetError(v34);
          Log_HREvent(v35, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 577);
        }
      }
      v36 = ScopedEndTransaction<ESESession>::EndTransaction(&v41, 0);
      if ( v36 < 0 )
        Log_HREvent(
          (unsigned int)v36,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      v9 = v30;
      goto LABEL_43;
    }
  }
  else
  {
    v24 = 0;
  }
  LOBYTE(v28) = 1;
  v29 = ScopedEndTransaction<ESESession>::EndTransaction(&v41, v28);
  v30 = v29;
  if ( v29 < 0 )
  {
    v31 = 375;
    v32 = 1;
    v33 = (unsigned int)v29;
    goto LABEL_31;
  }
  if ( v24 )
  {
    v37 = JetPrepareUpdate(v26, v25, 3u);
    if ( v37 < 0 )
    {
      v38 = MakeHresultFromJetError(v37);
      Log_HREvent(v38, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 577);
    }
  }
  v39 = ScopedEndTransaction<ESESession>::EndTransaction(&v41, 0);
  if ( v39 < 0 )
    Log_HREvent(
      (unsigned int)v39,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  v9 = 0;
LABEL_43:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v46);
  return v9;
}

```

## disassembly

```asm
0x180019254  push    rbp
0x180019256  push    rbx
0x180019257  push    rsi
0x180019258  push    rdi
0x180019259  push    r14
0x18001925b  push    r15
0x18001925d  lea     rbp, [rsp-2Fh]
0x180019262  sub     rsp, 88h
0x180019269  mov     rax, [rcx+38h]
0x18001926d  mov     rdi, rcx
0x180019270  mov     [rbp+57h+var_48], rax
0x180019274  mov     rsi, r9
0x180019277  lea     rax, [rcx+40h]
0x18001927b  mov     [rbp+57h+var_40], 0
0x180019282  lea     rcx, [rbp+57h+var_48]; this
0x180019286  mov     [rbp+57h+var_38], rax
0x18001928a  mov     r14d, r8d
0x18001928d  mov     r15d, edx
0x180019290  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180019295  mov     ebx, eax
0x180019297  test    eax, eax
0x180019299  jns     short loc_1800192B9
0x18001929b  mov     r9d, 141h
0x1800192a1  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800192a8  mov     edx, 1
0x1800192ad  mov     ecx, eax
0x1800192af  call    Log_HREvent
0x1800192b4  jmp     loc_1800195AB
0x1800192b9  lea     rcx, [rbp+57h+var_70]
0x1800192bd  mov     [rbp+57h+var_70], 0
0x1800192c4  mov     [rbp+57h+var_68], rdi
0x1800192c8  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x1800192cd  mov     ebx, eax
0x1800192cf  test    eax, eax
0x1800192d1  jns     short loc_18001931A
0x1800192d3  mov     r9d, 147h
0x1800192d9  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800192e0  mov     edx, 1
0x1800192e5  mov     ecx, eax
0x1800192e7  call    Log_HREvent
0x1800192ec  xor     edx, edx
0x1800192ee  lea     rcx, [rbp+57h+var_70]
0x1800192f2  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800192f7  test    eax, eax
0x1800192f9  jns     loc_1800195AB
0x1800192ff  mov     r9d, 39h ; '9'
0x180019305  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001930c  xor     edx, edx
0x18001930e  mov     ecx, eax
0x180019310  call    Log_HREvent
0x180019315  jmp     loc_1800195AB
0x18001931a  mov     rax, [rdi+38h]
0x18001931e  lea     rcx, [rbp+57h+sesid]; this
0x180019322  mov     [rbp+57h+sesid], rax
0x180019326  mov     edx, 2; unsigned int
0x18001932b  mov     rax, [rdi+28h]
0x18001932f  mov     [rbp+57h+tableid], rax
0x180019333  mov     [rbp+57h+var_50], 0
0x18001933a  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x18001933f  cmp     eax, 0FFFFF9BDh
0x180019344  jnz     loc_180019410
0x18001934a  mov     rdx, [rdi+28h]; tableid
0x18001934e  xor     r9d, r9d; grbit
0x180019351  mov     rcx, [rdi+38h]; sesid
0x180019355  mov     r8d, 80000000h; cRow
0x18001935b  call    cs:__imp_JetMove
0x180019361  lea     rcx, [rbp+57h+sesid]; this
0x180019365  mov     ebx, eax
0x180019367  cmp     eax, 0FFFFF9BDh
0x18001936c  jnz     short loc_1800193DD
0x18001936e  xor     edx, edx; unsigned int
0x180019370  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x180019375  test    eax, eax
0x180019377  jns     loc_180019426
0x18001937d  mov     ecx, eax; int
0x18001937f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180019384  mov     r9d, 15Eh
0x18001938a  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180019391  xor     edx, edx
0x180019393  mov     ecx, eax
0x180019395  mov     ebx, eax
0x180019397  call    Log_HREvent
0x18001939c  cmp     [rbp+57h+var_50], 0
0x1800193a0  jz      loc_1800192EC
0x1800193a6  mov     rdx, [rbp+57h+tableid]; tableid
0x1800193aa  mov     r8d, 3; prep
0x1800193b0  mov     rcx, [rbp+57h+sesid]; sesid
0x1800193b4  call    cs:__imp_JetPrepareUpdate
0x1800193ba  test    eax, eax
0x1800193bc  jns     loc_1800192EC
0x1800193c2  mov     ecx, eax; int
0x1800193c4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800193c9  mov     r9d, 241h
0x1800193cf  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800193d6  xor     edx, edx
0x1800193d8  jmp     loc_1800192E5
0x1800193dd  mov     edx, 2; unsigned int
0x1800193e2  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x1800193e7  test    eax, eax
0x1800193e9  jns     short loc_1800193FA
0x1800193eb  mov     ecx, eax; int
0x1800193ed  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800193f2  mov     r9d, 165h
0x1800193f8  jmp     short loc_18001938A
0x1800193fa  test    ebx, ebx
0x1800193fc  jns     short loc_180019426
0x1800193fe  mov     ecx, ebx; int
0x180019400  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180019405  mov     r9d, 166h
0x18001940b  jmp     loc_18001938A
0x180019410  test    eax, eax
0x180019412  jns     short loc_180019426
0x180019414  mov     ecx, eax; int
0x180019416  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001941b  mov     r9d, 16Bh
0x180019421  jmp     loc_18001938A
0x180019426  mov     rdx, [rdi+28h]; tableid
0x18001942a  mov     r9, rsi; pvData
0x18001942d  mov     rcx, [rdi+20h]; sesid
0x180019431  mov     r8d, r15d; columnid
0x180019434  mov     [rsp+0B0h+psetinfo], 0; psetinfo
0x18001943d  mov     [rsp+0B0h+grbit], 0; grbit
0x180019445  mov     [rsp+0B0h+cbData], r14d; cbData
0x18001944a  call    cs:__imp_JetSetColumn
0x180019450  test    eax, eax
0x180019452  jns     short loc_180019466
0x180019454  mov     ecx, eax; int
0x180019456  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001945b  mov     r9d, 172h
0x180019461  jmp     loc_18001938A
0x180019466  mov     ebx, [rbp+57h+var_50]
0x180019469  test    ebx, ebx
0x18001946b  jnz     short loc_18001947F
0x18001946d  mov     r8d, 231h
0x180019473  lea     rdx, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18001947a  call    Log_AssertionEvent
0x18001947f  mov     rsi, [rbp+57h+tableid]
0x180019483  xor     r9d, r9d; cbBookmark
0x180019486  mov     r14, [rbp+57h+sesid]
0x18001948a  mov     rdx, rsi; tableid
0x18001948d  mov     rcx, r14; sesid
0x180019490  mov     qword ptr [rsp+0B0h+cbData], 0; pcbActual
0x180019499  xor     r8d, r8d; pvBookmark
0x18001949c  call    cs:__imp_JetUpdate
0x1800194a2  test    eax, eax
0x1800194a4  jnz     short loc_1800194CC
0x1800194a6  xor     ebx, ebx
0x1800194a8  mov     dl, 1
0x1800194aa  lea     rcx, [rbp+57h+var_70]
0x1800194ae  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800194b3  mov     edi, eax
0x1800194b5  test    eax, eax
0x1800194b7  jns     loc_18001954D
0x1800194bd  mov     r9d, 177h
0x1800194c3  mov     edx, 1
0x1800194c8  mov     ecx, eax
0x1800194ca  jmp     short loc_1800194E1
0x1800194cc  jns     short loc_1800194A8
0x1800194ce  mov     ecx, eax; int
0x1800194d0  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800194d5  mov     edi, eax
0x1800194d7  mov     r9d, 174h
0x1800194dd  xor     edx, edx
0x1800194df  mov     ecx, eax
0x1800194e1  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800194e8  call    Log_HREvent
0x1800194ed  test    ebx, ebx
0x1800194ef  jz      short loc_180019524
0x1800194f1  mov     r8d, 3; prep
0x1800194f7  mov     rdx, rsi; tableid
0x1800194fa  mov     rcx, r14; sesid
0x1800194fd  call    cs:__imp_JetPrepareUpdate
0x180019503  test    eax, eax
0x180019505  jns     short loc_180019524
0x180019507  mov     ecx, eax; int
0x180019509  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001950e  mov     ecx, eax
0x180019510  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180019517  mov     r9d, 241h
0x18001951d  xor     edx, edx
0x18001951f  call    Log_HREvent
0x180019524  xor     edx, edx
0x180019526  lea     rcx, [rbp+57h+var_70]
0x18001952a  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001952f  test    eax, eax
0x180019531  jns     short loc_180019549
0x180019533  mov     r9d, 39h ; '9'
0x180019539  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180019540  xor     edx, edx
0x180019542  mov     ecx, eax
0x180019544  call    Log_HREvent
0x180019549  mov     ebx, edi
0x18001954b  jmp     short loc_1800195AB
0x18001954d  test    ebx, ebx
0x18001954f  jz      short loc_180019584
0x180019551  mov     r8d, 3; prep
0x180019557  mov     rdx, rsi; tableid
0x18001955a  mov     rcx, r14; sesid
0x18001955d  call    cs:__imp_JetPrepareUpdate
0x180019563  test    eax, eax
0x180019565  jns     short loc_180019584
0x180019567  mov     ecx, eax; int
0x180019569  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001956e  mov     ecx, eax
0x180019570  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180019577  mov     r9d, 241h
0x18001957d  xor     edx, edx
0x18001957f  call    Log_HREvent
0x180019584  xor     edx, edx
0x180019586  lea     rcx, [rbp+57h+var_70]
0x18001958a  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001958f  test    eax, eax
0x180019591  jns     short loc_1800195A9
0x180019593  mov     r9d, 39h ; '9'
0x180019599  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800195a0  xor     edx, edx
0x1800195a2  mov     ecx, eax
0x1800195a4  call    Log_HREvent
0x1800195a9  xor     ebx, ebx
0x1800195ab  lea     rcx, [rbp+57h+var_48]; this
0x1800195af  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x1800195b4  mov     eax, ebx
0x1800195b6  add     rsp, 88h
0x1800195bd  pop     r15
0x1800195bf  pop     r14
0x1800195c1  pop     rdi
0x1800195c2  pop     rsi
0x1800195c3  pop     rbx
0x1800195c4  pop     rbp
0x1800195c5  retn
```
