# ESESession::FindFirst(_INDEXTABLE_ID,char const *,JET_RETRIEVECOLUMN *,ulong,void *,unsigned __int64,int,ulong,int *)

- ea: `0x1800173c4`
- end: `0x180017630`
- name: `?FindFirst@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEBDPEAUJET_RETRIEVECOLUMN@@KPEAX_KHKPEAH@Z`
- size: `620`
- prototype: `__int64 __fastcall(__int64, int, __int64, JET_RETRIEVECOLUMN *, unsigned int cbData, void *pvData, unsigned __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001cf00`

## callees

- `0x180002da8`
- `0x18000a998`
- `0x180010638`
- `0x180016860`
- `0x1800173c4`
- `0x180017b04`
- `0x180017d74`
- `0x18001848c`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800175f4`
- `ESENT!JetRetrieveColumns` at `0x1800175f4`
- `ESENT!JetMakeKey` at `0x180017537`
- `ESENT!JetMakeKey` at `0x1800175aa`
- `ESENT!JetMakeKey` at `0x180017537`
- `ESENT!JetMakeKey` at `0x1800175aa`
- `ESENT!JetSetCurrentIndexA` at `0x18001745e`
- `ESENT!JetSetCurrentIndexA` at `0x1800174cc`
- `ESENT!JetSetCurrentIndexA` at `0x18001745e`
- `ESENT!JetSetCurrentIndexA` at `0x1800174cc`
- `ESENT!JetSeek` at `0x180017562`
- `ESENT!JetSeek` at `0x180017562`
- `ESENT!JetSetIndexRange` at `0x1800175d5`
- `ESENT!JetSetIndexRange` at `0x1800175d5`

## string_xrefs

- `0x180017434`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017488`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017452`: `TokenIdx`
- `0x18001746b`: `TokenIdx`
- `0x1800174c1`: `TokenIdx`

## pseudocode

```c
__int64 __fastcall ESESession::FindFirst(
        __int64 a1,
        int a2,
        __int64 a3,
        JET_RETRIEVECOLUMN *a4,
        unsigned int cbData,
        void *pvData,
        unsigned __int64 a7,
        __int64 a8,
        __int64 a9,
        _DWORD *a10)
{
  _DWORD *v11; // r14
  __int64 v13; // rsi
  int HresultFromJetError; // eax
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rbx
  JET_ERR v19; // eax
  int v20; // esi
  __int64 v21; // r9
  JET_ERR v22; // eax
  JET_ERR Key; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  JET_ERR Columns; // eax
  __int64 v28; // [rsp+30h] [rbp-48h] BYREF
  int v29; // [rsp+38h] [rbp-40h]
  __int64 v30; // [rsp+40h] [rbp-38h]

  v11 = a10;
  v28 = *(_QWORD *)(a1 + 56);
  v30 = a1 + 64;
  v13 = a2;
  *a10 = 0;
  v29 = 0;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v28);
  v15 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    HresultFromJetError = ESESession::OpenTable(a1, (unsigned int)v13);
    v15 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v16 = 584;
      goto LABEL_5;
    }
    v18 = 6 * v13;
    v19 = JetSetCurrentIndexA(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 48 * v13 + 112), "TokenIdx");
    if ( v19 == -1404 )
    {
      v20 = ESESession::_AddIndex(a1, v13, (__int64)"TokenIdx");
      if ( v20 < 0 )
      {
        v21 = 596;
LABEL_10:
        Log_HREvent(
          (unsigned int)v20,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
          v21);
        v15 = v20;
        goto LABEL_30;
      }
    }
    else if ( v19 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v19);
      v16 = 600;
      goto LABEL_13;
    }
    v22 = JetSetCurrentIndexA(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), "TokenIdx");
    if ( v22 >= 0 )
    {
      cbData = 0;
      v20 = ULongLongToULong(a7, &cbData);
      if ( v20 < 0 )
      {
        v21 = 610;
        goto LABEL_10;
      }
      Key = JetMakeKey(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), pvData, cbData, 0x401u);
      if ( Key >= 0 )
      {
        v24 = JetSeek(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), 8u);
        if ( v24 == -1601 )
          goto LABEL_28;
        if ( v24 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v24);
          v16 = 633;
          goto LABEL_13;
        }
        v25 = JetMakeKey(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), pvData, cbData, 0x801u);
        if ( v25 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v25);
          v16 = 641;
          goto LABEL_13;
        }
        if ( JetSetIndexRange(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), 3u) == -1603 )
        {
LABEL_28:
          *v11 = 1;
        }
        else
        {
          Columns = JetRetrieveColumns(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 8 * v18 + 112), a4, 1u);
          if ( Columns < 0 )
          {
            HresultFromJetError = MakeHresultFromJetError(Columns);
            v16 = 661;
            goto LABEL_13;
          }
        }
        v15 = 0;
        goto LABEL_30;
      }
      HresultFromJetError = MakeHresultFromJetError(Key);
      v16 = 618;
    }
    else
    {
      HresultFromJetError = MakeHresultFromJetError(v22);
      v16 = 607;
    }
LABEL_13:
    v15 = HresultFromJetError;
    v17 = 0;
    goto LABEL_6;
  }
  v16 = 581;
LABEL_5:
  v17 = 1;
LABEL_6:
  Log_HREvent(
    (unsigned int)HresultFromJetError,
    v17,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v16);
LABEL_30:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v28);
  return v15;
}

```

## disassembly

```asm
0x1800173c4  push    rbx
0x1800173c6  push    rbp
0x1800173c7  push    rsi
0x1800173c8  push    rdi
0x1800173c9  push    r14
0x1800173cb  sub     rsp, 50h
0x1800173cf  mov     rax, [rcx+38h]
0x1800173d3  mov     rdi, rcx
0x1800173d6  mov     r14, [rsp+78h+arg_48]
0x1800173de  mov     rbp, r9
0x1800173e1  mov     [rsp+78h+var_48], rax
0x1800173e6  lea     rax, [rcx+40h]
0x1800173ea  lea     rcx, [rsp+78h+var_48]; this
0x1800173ef  mov     [rsp+78h+var_38], rax
0x1800173f4  movsxd  rsi, edx
0x1800173f7  mov     dword ptr [r14], 0
0x1800173fe  mov     [rsp+78h+var_40], 0
0x180017406  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x18001740b  mov     ebx, eax
0x18001740d  test    eax, eax
0x18001740f  jns     short loc_180017419
0x180017411  mov     r9d, 245h
0x180017417  jmp     short loc_18001742F
0x180017419  mov     edx, esi
0x18001741b  mov     rcx, rdi
0x18001741e  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x180017423  mov     ebx, eax
0x180017425  test    eax, eax
0x180017427  jns     short loc_180017447
0x180017429  mov     r9d, 248h
0x18001742f  mov     edx, 1
0x180017434  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001743b  mov     ecx, eax
0x18001743d  call    Log_HREvent
0x180017442  jmp     loc_180017619
0x180017447  mov     rcx, [rdi+38h]; sesid
0x18001744b  lea     rbx, [rsi+rsi*2]
0x18001744f  add     rbx, rbx
0x180017452  lea     r8, ?PimIMIndexIdxName_TokenIdx@@3QBDB; "TokenIdx"
0x180017459  mov     rdx, [rdi+rbx*8+70h]; tableid
0x18001745e  call    cs:__imp_JetSetCurrentIndexA
0x180017464  cmp     eax, 0FFFFFA84h
0x180017469  jnz     short loc_1800174A2
0x18001746b  lea     r8, ?PimIMIndexIdxName_TokenIdx@@3QBDB; "TokenIdx"
0x180017472  mov     edx, esi
0x180017474  mov     rcx, rdi
0x180017477  call    ?_AddIndex@ESESession@@AEAAJW4_INDEXTABLE_ID@@PEBD@Z; ESESession::_AddIndex(_INDEXTABLE_ID,char const *)
0x18001747c  mov     esi, eax
0x18001747e  test    eax, eax
0x180017480  jns     short loc_1800174BC
0x180017482  mov     r9d, 254h
0x180017488  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001748f  mov     edx, 1
0x180017494  mov     ecx, esi
0x180017496  call    Log_HREvent
0x18001749b  mov     ebx, esi
0x18001749d  jmp     loc_180017619
0x1800174a2  test    eax, eax
0x1800174a4  jns     short loc_1800174BC
0x1800174a6  mov     ecx, eax; int
0x1800174a8  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800174ad  mov     r9d, 258h
0x1800174b3  mov     ebx, eax
0x1800174b5  xor     edx, edx
0x1800174b7  jmp     loc_180017434
0x1800174bc  mov     rdx, [rdi+rbx*8+70h]; tableid
0x1800174c1  lea     r8, ?PimIMIndexIdxName_TokenIdx@@3QBDB; "TokenIdx"
0x1800174c8  mov     rcx, [rdi+38h]; sesid
0x1800174cc  call    cs:__imp_JetSetCurrentIndexA
0x1800174d2  test    eax, eax
0x1800174d4  jns     short loc_1800174E5
0x1800174d6  mov     ecx, eax; int
0x1800174d8  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800174dd  mov     r9d, 25Fh
0x1800174e3  jmp     short loc_1800174B3
0x1800174e5  mov     rcx, [rsp+78h+arg_30]; unsigned __int64
0x1800174ed  lea     rdx, [rsp+78h+cbData]; unsigned int *
0x1800174f5  mov     [rsp+78h+cbData], 0
0x180017500  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180017505  mov     esi, eax
0x180017507  test    eax, eax
0x180017509  jns     short loc_180017516
0x18001750b  mov     r9d, 262h
0x180017511  jmp     loc_180017488
0x180017516  mov     r9d, [rsp+78h+cbData]; cbData
0x18001751e  mov     r8, [rsp+78h+pvData]; pvData
0x180017526  mov     rdx, [rdi+rbx*8+70h]; tableid
0x18001752b  mov     rcx, [rdi+38h]; sesid
0x18001752f  mov     [rsp+78h+grbit], 401h; grbit
0x180017537  call    cs:__imp_JetMakeKey
0x18001753d  test    eax, eax
0x18001753f  jns     short loc_180017553
0x180017541  mov     ecx, eax; int
0x180017543  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017548  mov     r9d, 26Ah
0x18001754e  jmp     loc_1800174B3
0x180017553  mov     rdx, [rdi+rbx*8+70h]; tableid
0x180017558  mov     r8d, 8; grbit
0x18001755e  mov     rcx, [rdi+38h]; sesid
0x180017562  call    cs:__imp_JetSeek
0x180017568  cmp     eax, 0FFFFF9BFh
0x18001756d  jz      loc_180017610
0x180017573  test    eax, eax
0x180017575  jns     short loc_180017589
0x180017577  mov     ecx, eax; int
0x180017579  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001757e  mov     r9d, 279h
0x180017584  jmp     loc_1800174B3
0x180017589  mov     r9d, [rsp+78h+cbData]; cbData
0x180017591  mov     r8, [rsp+78h+pvData]; pvData
0x180017599  mov     rdx, [rdi+rbx*8+70h]; tableid
0x18001759e  mov     rcx, [rdi+38h]; sesid
0x1800175a2  mov     [rsp+78h+grbit], 801h; grbit
0x1800175aa  call    cs:__imp_JetMakeKey
0x1800175b0  test    eax, eax
0x1800175b2  jns     short loc_1800175C6
0x1800175b4  mov     ecx, eax; int
0x1800175b6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800175bb  mov     r9d, 281h
0x1800175c1  jmp     loc_1800174B3
0x1800175c6  mov     rdx, [rdi+rbx*8+70h]; tableidSrc
0x1800175cb  mov     r8d, 3; grbit
0x1800175d1  mov     rcx, [rdi+38h]; sesid
0x1800175d5  call    cs:__imp_JetSetIndexRange
0x1800175db  cmp     eax, 0FFFFF9BDh
0x1800175e0  jz      short loc_180017610
0x1800175e2  mov     rdx, [rdi+rbx*8+70h]; tableid
0x1800175e7  mov     r9d, 1; cretrievecolumn
0x1800175ed  mov     rcx, [rdi+38h]; sesid
0x1800175f1  mov     r8, rbp; pretrievecolumn
0x1800175f4  call    cs:__imp_JetRetrieveColumns
0x1800175fa  test    eax, eax
0x1800175fc  jns     short loc_180017617
0x1800175fe  mov     ecx, eax; int
0x180017600  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017605  mov     r9d, 295h
0x18001760b  jmp     loc_1800174B3
0x180017610  mov     dword ptr [r14], 1
0x180017617  xor     ebx, ebx
0x180017619  lea     rcx, [rsp+78h+var_48]; this
0x18001761e  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180017623  mov     eax, ebx
0x180017625  add     rsp, 50h
0x180017629  pop     r14
0x18001762b  pop     rdi
0x18001762c  pop     rsi
0x18001762d  pop     rbp
0x18001762e  pop     rbx
0x18001762f  retn
```
