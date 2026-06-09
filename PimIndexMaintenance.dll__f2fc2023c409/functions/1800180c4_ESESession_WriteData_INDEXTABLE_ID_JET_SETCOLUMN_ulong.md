# ESESession::WriteData(_INDEXTABLE_ID,JET_SETCOLUMN *,ulong)

- ea: `0x1800180c4`
- end: `0x1800183ac`
- name: `?WriteData@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEAUJET_SETCOLUMN@@K@Z`
- size: `744`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18001bd20`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x180013678`
- `0x180013f14`
- `0x180016860`
- `0x180017b04`
- `0x180017d20`
- `0x180017d74`
- `0x1800180c4`

## import_xrefs

- `ESENT!JetSetColumns` at `0x180018238`
- `ESENT!JetSetColumns` at `0x180018238`
- `ESENT!JetPrepareUpdate` at `0x1800181fd`
- `ESENT!JetPrepareUpdate` at `0x1800182e8`
- `ESENT!JetPrepareUpdate` at `0x180018348`
- `ESENT!JetPrepareUpdate` at `0x1800181fd`
- `ESENT!JetPrepareUpdate` at `0x1800182e8`
- `ESENT!JetPrepareUpdate` at `0x180018348`
- `ESENT!JetUpdate` at `0x180018287`
- `ESENT!JetUpdate` at `0x180018287`

## string_xrefs

- `0x180018183`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180018324`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180018384`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x18001811f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018157`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800181d3`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800182cc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018218`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x18001825e`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x1800182fb`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x18001835b`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
__int64 __fastcall ESESession::WriteData(__int64 a1, int a2, JET_SETCOLUMN *a3)
{
  __int64 v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  int started; // eax
  __int64 v10; // r9
  const char *v11; // r8
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v16; // r9
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  __int64 v19; // rcx
  int v20; // ebx
  JET_TABLEID v21; // rsi
  JET_SESID v22; // r14
  JET_ERR v23; // eax
  int v24; // eax
  unsigned int v25; // edi
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  JET_ERR v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  JET_ERR v32; // eax
  unsigned int v33; // eax
  int v34; // eax
  int v36; // [rsp+30h] [rbp-40h] BYREF
  __int64 v37; // [rsp+38h] [rbp-38h]
  JET_SESID sesid; // [rsp+40h] [rbp-30h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-28h]
  int v40; // [rsp+50h] [rbp-20h]
  __int64 v41; // [rsp+58h] [rbp-18h] BYREF
  int v42; // [rsp+60h] [rbp-10h]
  __int64 v43; // [rsp+68h] [rbp-8h]

  v41 = *(_QWORD *)(a1 + 56);
  v5 = a2;
  v43 = a1 + 64;
  v42 = 0;
  v6 = auto_SessionContext::SetContext((auto_SessionContext *)&v41);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 438;
LABEL_5:
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v8);
    goto LABEL_38;
  }
  v6 = ESESession::OpenTable(a1, (unsigned int)v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 441;
    goto LABEL_5;
  }
  v36 = 0;
  v37 = a1;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v36);
  v7 = started;
  if ( started < 0 )
  {
    v10 = 447;
    v11 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp";
    v12 = 1;
    goto LABEL_8;
  }
  sesid = *(_QWORD *)(a1 + 56);
  v40 = 0;
  tableid = *(_QWORD *)(a1 + 48 * v5 + 112);
  v14 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 0);
  if ( v14 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v14);
    v16 = 452;
    goto LABEL_13;
  }
  v18 = JetSetColumns(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v5 + 112), a3, 2u);
  if ( v18 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v18);
    v16 = 458;
LABEL_13:
    v7 = HresultFromJetError;
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v16);
    if ( !v40 || (v17 = JetPrepareUpdate(sesid, tableid, 3u), v17 >= 0) )
    {
LABEL_9:
      v13 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
      if ( v13 < 0 )
        Log_HREvent(
          (unsigned int)v13,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      goto LABEL_38;
    }
    started = MakeHresultFromJetError(v17);
    v10 = 577;
    v11 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h";
    v12 = 0;
LABEL_8:
    Log_HREvent((unsigned int)started, v12, v11, v10);
    goto LABEL_9;
  }
  v20 = v40;
  if ( !v40 )
    Log_AssertionEvent(v19, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 561);
  v21 = tableid;
  v22 = sesid;
  v23 = JetUpdate(sesid, tableid, 0, 0, 0);
  if ( v23 )
  {
    if ( v23 < 0 )
    {
      v25 = MakeHresultFromJetError(v23);
      v26 = 460;
      v27 = 0;
      v28 = v25;
LABEL_26:
      Log_HREvent(
        v28,
        v27,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        v26);
      if ( v20 )
      {
        v29 = JetPrepareUpdate(v22, v21, 3u);
        if ( v29 < 0 )
        {
          v30 = MakeHresultFromJetError(v29);
          Log_HREvent(v30, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 577);
        }
      }
      v31 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
      if ( v31 < 0 )
        Log_HREvent(
          (unsigned int)v31,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      v7 = v25;
      goto LABEL_38;
    }
  }
  else
  {
    v20 = 0;
  }
  v24 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 1u);
  v25 = v24;
  if ( v24 < 0 )
  {
    v26 = 463;
    v27 = 1;
    v28 = (unsigned int)v24;
    goto LABEL_26;
  }
  if ( v20 )
  {
    v32 = JetPrepareUpdate(v22, v21, 3u);
    if ( v32 < 0 )
    {
      v33 = MakeHresultFromJetError(v32);
      Log_HREvent(v33, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 577);
    }
  }
  v34 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
  if ( v34 < 0 )
    Log_HREvent(
      (unsigned int)v34,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  v7 = 0;
LABEL_38:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v41);
  return v7;
}

```

## disassembly

```asm
0x1800180c4  push    rbp
0x1800180c6  push    rbx
0x1800180c7  push    rsi
0x1800180c8  push    rdi
0x1800180c9  push    r14
0x1800180cb  mov     rbp, rsp
0x1800180ce  sub     rsp, 70h
0x1800180d2  mov     rax, [rcx+38h]
0x1800180d6  mov     rdi, rcx
0x1800180d9  mov     [rbp+var_18], rax
0x1800180dd  mov     r14, r8
0x1800180e0  lea     rax, [rcx+40h]
0x1800180e4  movsxd  rsi, edx
0x1800180e7  lea     rcx, [rbp+var_18]; this
0x1800180eb  mov     [rbp+var_8], rax
0x1800180ef  mov     [rbp+var_10], 0
0x1800180f6  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x1800180fb  mov     ebx, eax
0x1800180fd  test    eax, eax
0x1800180ff  jns     short loc_180018109
0x180018101  mov     r9d, 1B6h
0x180018107  jmp     short loc_18001811F
0x180018109  mov     edx, esi
0x18001810b  mov     rcx, rdi
0x18001810e  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x180018113  mov     ebx, eax
0x180018115  test    eax, eax
0x180018117  jns     short loc_180018137
0x180018119  mov     r9d, 1B9h
0x18001811f  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018126  mov     edx, 1
0x18001812b  mov     ecx, eax
0x18001812d  call    Log_HREvent
0x180018132  jmp     loc_180018396
0x180018137  lea     rcx, [rbp+var_40]
0x18001813b  mov     [rbp+var_40], 0
0x180018142  mov     [rbp+var_38], rdi
0x180018146  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x18001814b  mov     ebx, eax
0x18001814d  test    eax, eax
0x18001814f  jns     short loc_180018198
0x180018151  mov     r9d, 1BFh
0x180018157  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001815e  mov     edx, 1
0x180018163  mov     ecx, eax
0x180018165  call    Log_HREvent
0x18001816a  xor     edx, edx
0x18001816c  lea     rcx, [rbp+var_40]
0x180018170  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180018175  test    eax, eax
0x180018177  jns     loc_180018396
0x18001817d  mov     r9d, 39h ; '9'
0x180018183  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001818a  xor     edx, edx
0x18001818c  mov     ecx, eax
0x18001818e  call    Log_HREvent
0x180018193  jmp     loc_180018396
0x180018198  mov     rax, [rdi+38h]
0x18001819c  lea     rbx, [rsi+rsi*2]
0x1800181a0  mov     [rbp+sesid], rax
0x1800181a4  lea     rcx, [rbp+sesid]; this
0x1800181a8  add     rbx, rbx
0x1800181ab  mov     [rbp+var_20], 0
0x1800181b2  xor     edx, edx; unsigned int
0x1800181b4  mov     rax, [rdi+rbx*8+70h]
0x1800181b9  mov     [rbp+tableid], rax
0x1800181bd  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x1800181c2  test    eax, eax
0x1800181c4  jns     short loc_180018226
0x1800181c6  mov     ecx, eax; int
0x1800181c8  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800181cd  mov     r9d, 1C4h
0x1800181d3  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800181da  xor     edx, edx
0x1800181dc  mov     ecx, eax
0x1800181de  mov     ebx, eax
0x1800181e0  call    Log_HREvent
0x1800181e5  cmp     [rbp+var_20], 0
0x1800181e9  jz      loc_18001816A
0x1800181ef  mov     rdx, [rbp+tableid]; tableid
0x1800181f3  mov     r8d, 3; prep
0x1800181f9  mov     rcx, [rbp+sesid]; sesid
0x1800181fd  call    cs:__imp_JetPrepareUpdate
0x180018203  test    eax, eax
0x180018205  jns     loc_18001816A
0x18001820b  mov     ecx, eax; int
0x18001820d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018212  mov     r9d, 241h
0x180018218  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18001821f  xor     edx, edx
0x180018221  jmp     loc_180018163
0x180018226  mov     rdx, [rdi+rbx*8+70h]; tableid
0x18001822b  mov     r9d, 2; csetcolumn
0x180018231  mov     rcx, [rdi+38h]; sesid
0x180018235  mov     r8, r14; psetcolumn
0x180018238  call    cs:__imp_JetSetColumns
0x18001823e  test    eax, eax
0x180018240  jns     short loc_180018251
0x180018242  mov     ecx, eax; int
0x180018244  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018249  mov     r9d, 1CAh
0x18001824f  jmp     short loc_1800181D3
0x180018251  mov     ebx, [rbp+var_20]
0x180018254  test    ebx, ebx
0x180018256  jnz     short loc_18001826A
0x180018258  mov     r8d, 231h
0x18001825e  lea     rdx, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180018265  call    Log_AssertionEvent
0x18001826a  mov     rsi, [rbp+tableid]
0x18001826e  xor     r9d, r9d; cbBookmark
0x180018271  mov     r14, [rbp+sesid]
0x180018275  mov     rdx, rsi; tableid
0x180018278  mov     rcx, r14; sesid
0x18001827b  mov     [rsp+70h+pcbActual], 0; pcbActual
0x180018284  xor     r8d, r8d; pvBookmark
0x180018287  call    cs:__imp_JetUpdate
0x18001828d  test    eax, eax
0x18001828f  jnz     short loc_1800182B7
0x180018291  xor     ebx, ebx
0x180018293  mov     dl, 1
0x180018295  lea     rcx, [rbp+var_40]
0x180018299  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001829e  mov     edi, eax
0x1800182a0  test    eax, eax
0x1800182a2  jns     loc_180018338
0x1800182a8  mov     r9d, 1CFh
0x1800182ae  mov     edx, 1
0x1800182b3  mov     ecx, eax
0x1800182b5  jmp     short loc_1800182CC
0x1800182b7  jns     short loc_180018293
0x1800182b9  mov     ecx, eax; int
0x1800182bb  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800182c0  mov     edi, eax
0x1800182c2  mov     r9d, 1CCh
0x1800182c8  xor     edx, edx
0x1800182ca  mov     ecx, eax
0x1800182cc  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800182d3  call    Log_HREvent
0x1800182d8  test    ebx, ebx
0x1800182da  jz      short loc_18001830F
0x1800182dc  mov     r8d, 3; prep
0x1800182e2  mov     rdx, rsi; tableid
0x1800182e5  mov     rcx, r14; sesid
0x1800182e8  call    cs:__imp_JetPrepareUpdate
0x1800182ee  test    eax, eax
0x1800182f0  jns     short loc_18001830F
0x1800182f2  mov     ecx, eax; int
0x1800182f4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800182f9  mov     ecx, eax
0x1800182fb  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180018302  mov     r9d, 241h
0x180018308  xor     edx, edx
0x18001830a  call    Log_HREvent
0x18001830f  xor     edx, edx
0x180018311  lea     rcx, [rbp+var_40]
0x180018315  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001831a  test    eax, eax
0x18001831c  jns     short loc_180018334
0x18001831e  mov     r9d, 39h ; '9'
0x180018324  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001832b  xor     edx, edx
0x18001832d  mov     ecx, eax
0x18001832f  call    Log_HREvent
0x180018334  mov     ebx, edi
0x180018336  jmp     short loc_180018396
0x180018338  test    ebx, ebx
0x18001833a  jz      short loc_18001836F
0x18001833c  mov     r8d, 3; prep
0x180018342  mov     rdx, rsi; tableid
0x180018345  mov     rcx, r14; sesid
0x180018348  call    cs:__imp_JetPrepareUpdate
0x18001834e  test    eax, eax
0x180018350  jns     short loc_18001836F
0x180018352  mov     ecx, eax; int
0x180018354  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018359  mov     ecx, eax
0x18001835b  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180018362  mov     r9d, 241h
0x180018368  xor     edx, edx
0x18001836a  call    Log_HREvent
0x18001836f  xor     edx, edx
0x180018371  lea     rcx, [rbp+var_40]
0x180018375  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001837a  test    eax, eax
0x18001837c  jns     short loc_180018394
0x18001837e  mov     r9d, 39h ; '9'
0x180018384  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001838b  xor     edx, edx
0x18001838d  mov     ecx, eax
0x18001838f  call    Log_HREvent
0x180018394  xor     ebx, ebx
0x180018396  lea     rcx, [rbp+var_18]; this
0x18001839a  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x18001839f  mov     eax, ebx
0x1800183a1  add     rsp, 70h
0x1800183a5  pop     r14
0x1800183a7  pop     rdi
0x1800183a8  pop     rsi
0x1800183a9  pop     rbx
0x1800183aa  pop     rbp
0x1800183ab  retn
```
