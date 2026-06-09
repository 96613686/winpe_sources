# IndexedFiltering::IndexManager::ValueDeleted(USOID const &,IndexedFiltering::IIndexManagerClient *)

- ea: `0x1800144c0`
- end: `0x180014808`
- name: `?ValueDeleted@IndexManager@IndexedFiltering@@UEAAJAEBUUSOID@@PEAUIIndexManagerClient@2@@Z`
- size: `840`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *__hidden this, const struct USOID *, struct IndexedFiltering::IIndexManagerClient *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x180012c9c`
- `0x180012f68`
- `0x1800130b8`
- `0x180013678`
- `0x180013b80`
- `0x180013e00`
- `0x180013e40`
- `0x180013f14`
- `0x180013fac`
- `0x1800144c0`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x180014502`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014565`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014591`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800145d1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x18001464f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800146da`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014743`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800145f9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180014709`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x18001476f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x1800147db`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::ValueDeleted(
        IndexedFiltering::IndexManager *this,
        const struct USOID *a2,
        struct IndexedFiltering::IIndexManagerClient *a3)
{
  int *v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // ebx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // r14d
  __int64 v14; // r9
  const char *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  int started; // eax
  int v19; // eax
  __int64 v20; // rcx
  int v21; // ebx
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // xmm0_8
  unsigned int i; // r14d
  int v26; // eax
  unsigned int v27; // r15d
  int v28; // eax
  int v29; // esi
  __int64 v30; // r9
  int v31; // eax
  int v32; // eax
  int v33; // [rsp+30h] [rbp-40h] BYREF
  __int64 v34; // [rsp+38h] [rbp-38h]
  _QWORD v35[2]; // [rsp+40h] [rbp-30h] BYREF
  int v36; // [rsp+50h] [rbp-20h]
  int v37; // [rsp+54h] [rbp-1Ch]
  __int64 v38; // [rsp+58h] [rbp-18h] BYREF
  int v39; // [rsp+60h] [rbp-10h]

  if ( (unsigned int)IsEmptyUsOid(a2) )
  {
    v7 = 312;
    v8 = -2147024809;
LABEL_3:
    Log_HREvent(
      v8,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      v7);
    return v8;
  }
  if ( *((_DWORD *)this + 32) )
  {
    if ( a3 )
    {
      v7 = 316;
      v8 = -2147418113;
      goto LABEL_3;
    }
    v10 = IndexedFiltering::IndexManager::AddPendingUpdate((__int64)this, v6, 1, 0, 0, 0);
    v11 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        323);
      return v11;
    }
    return 0;
  }
  v12 = IndexedFiltering::IndexManager::CacheIndexSources(this);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 329;
    v15 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp";
    v16 = 1;
    v17 = (unsigned int)v12;
    goto LABEL_11;
  }
  v34 = *((_QWORD *)this + 15);
  v33 = 0;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v33);
  v13 = started;
  if ( started < 0 )
  {
    Log_HREvent(
      (unsigned int)started,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      334);
LABEL_15:
    v19 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v33, 0);
    if ( v19 >= 0 )
      return (unsigned int)v13;
    v14 = 57;
    v15 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h";
    v16 = 0;
    v17 = (unsigned int)v19;
LABEL_11:
    Log_HREvent(v17, v16, v15, v14);
    return (unsigned int)v13;
  }
  v20 = *((_QWORD *)this + 3);
  v21 = *((_DWORD *)this + 28);
  v35[0] = v20;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  v36 = v21;
  v35[1] = (char *)this + 72;
  v37 = 0;
  if ( a3 )
  {
    v13 = IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35);
    if ( v13 < 0 )
    {
      v22 = 341;
LABEL_22:
      Log_HREvent(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        v22);
      IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35);
      goto LABEL_15;
    }
  }
  v23 = *((_QWORD *)this + 3);
  v24 = *(_QWORD *)a2;
  v39 = *((_DWORD *)a2 + 2);
  v38 = v24;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 32LL))(v23, &v38);
  if ( v13 < 0 )
  {
    v22 = 347;
    goto LABEL_22;
  }
  for ( i = 0; i < *((_DWORD *)this + 28); ++i )
  {
    v26 = (*(__int64 (__fastcall **)(IndexedFiltering::IndexManager *, _QWORD, const struct USOID *))(*(_QWORD *)this + 104LL))(
            this,
            i,
            a2);
    v27 = v26;
    if ( v26 < 0 )
    {
      Log_HREvent(
        (unsigned int)v26,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        352);
      IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35);
      v28 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v33, 0);
      if ( v28 < 0 )
        Log_HREvent(
          (unsigned int)v28,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      return v27;
    }
  }
  if ( a3
    && (v29 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManagerClient *))(*(_QWORD *)a3 + 32LL))(a3),
        v29 < 0) )
  {
    v30 = 357;
  }
  else
  {
    v29 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v33, 1u);
    if ( v29 >= 0 )
    {
      v29 = IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(
              (IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35,
              1);
      if ( v29 >= 0 )
      {
        IndexedFiltering::IndexManager::ReleaseIndexSourcesCache(this);
        IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35);
        v32 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v33, 0);
        if ( v32 < 0 )
          Log_HREvent(
            (unsigned int)v32,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
            57);
        return 0;
      }
      v30 = 362;
    }
    else
    {
      v30 = 361;
    }
  }
  Log_HREvent(
    (unsigned int)v29,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
    v30);
  IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v35);
  v31 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v33, 0);
  if ( v31 < 0 )
    Log_HREvent(
      (unsigned int)v31,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x1800144c0  push    rbp
0x1800144c2  push    rbx
0x1800144c3  push    rsi
0x1800144c4  push    rdi
0x1800144c5  push    r13
0x1800144c7  push    r14
0x1800144c9  push    r15
0x1800144cb  mov     rbp, rsp
0x1800144ce  sub     rsp, 70h
0x1800144d2  mov     rax, cs:__security_cookie
0x1800144d9  xor     rax, rsp
0x1800144dc  mov     [rbp+var_8], rax
0x1800144e0  mov     rdi, rcx
0x1800144e3  mov     rsi, r8
0x1800144e6  mov     rcx, rdx; struct USOID *
0x1800144e9  mov     r13, rdx
0x1800144ec  call    ?IsEmptyUsOid@@YAHAEBUUSOID@@@Z; IsEmptyUsOid(USOID const &)
0x1800144f1  test    eax, eax
0x1800144f3  jz      short loc_180014517
0x1800144f5  mov     r9d, 138h
0x1800144fb  mov     ebx, 80070057h
0x180014500  xor     edx, edx
0x180014502  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014509  mov     ecx, ebx
0x18001450b  call    Log_HREvent
0x180014510  mov     eax, ebx
0x180014512  jmp     loc_1800147ED
0x180014517  cmp     dword ptr [rdi+80h], 0
0x18001451e  jz      short loc_18001457C
0x180014520  test    rsi, rsi
0x180014523  jz      short loc_180014532
0x180014525  mov     r9d, 13Ch
0x18001452b  mov     ebx, 8000FFFFh
0x180014530  jmp     short loc_180014500
0x180014532  xor     r9d, r9d
0x180014535  mov     [rsp+70h+var_48], 0
0x18001453d  mov     rcx, rdi
0x180014540  mov     [rsp+70h+var_50], 0
0x180014549  lea     ebx, [r9+1]
0x18001454d  mov     r8d, ebx
0x180014550  call    ?AddPendingUpdate@IndexManager@IndexedFiltering@@AEAAJAEBUUSOID@@W4BulkUpdateEntryType@2@PEAU_SQLCEPROPVAL@@_KH@Z; IndexedFiltering::IndexManager::AddPendingUpdate(USOID const &,IndexedFiltering::BulkUpdateEntryType,_SQLCEPROPVAL *,unsigned __int64,int)
0x180014555  mov     edi, eax
0x180014557  test    eax, eax
0x180014559  jns     loc_1800147EB
0x18001455f  mov     r9d, 143h
0x180014565  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001456c  mov     edx, ebx
0x18001456e  mov     ecx, eax
0x180014570  call    Log_HREvent
0x180014575  mov     eax, edi
0x180014577  jmp     loc_1800147ED
0x18001457c  mov     rcx, rdi; this
0x18001457f  call    ?CacheIndexSources@IndexManager@IndexedFiltering@@AEAAJXZ; IndexedFiltering::IndexManager::CacheIndexSources(void)
0x180014584  mov     r14d, eax
0x180014587  test    eax, eax
0x180014589  jns     short loc_1800145AC
0x18001458b  mov     r9d, 149h
0x180014591  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014598  mov     edx, 1
0x18001459d  mov     ecx, eax
0x18001459f  call    Log_HREvent
0x1800145a4  mov     eax, r14d
0x1800145a7  jmp     loc_1800147ED
0x1800145ac  mov     rax, [rdi+78h]
0x1800145b0  lea     rcx, [rbp+var_40]
0x1800145b4  mov     [rbp+var_38], rax
0x1800145b8  mov     [rbp+var_40], 0
0x1800145bf  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x1800145c4  mov     r14d, eax
0x1800145c7  test    eax, eax
0x1800145c9  jns     short loc_180014606
0x1800145cb  mov     r9d, 14Eh
0x1800145d1  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800145d8  mov     edx, 1
0x1800145dd  mov     ecx, eax
0x1800145df  call    Log_HREvent
0x1800145e4  xor     edx, edx
0x1800145e6  lea     rcx, [rbp+var_40]
0x1800145ea  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800145ef  test    eax, eax
0x1800145f1  jns     short loc_1800145A4
0x1800145f3  mov     r9d, 39h ; '9'
0x1800145f9  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014600  xor     edx, edx
0x180014602  mov     ecx, eax
0x180014604  jmp     short loc_18001459F
0x180014606  mov     rcx, [rdi+18h]
0x18001460a  mov     ebx, [rdi+70h]
0x18001460d  mov     [rbp+var_30], rcx
0x180014611  test    rcx, rcx
0x180014614  jz      short loc_180014622
0x180014616  mov     rax, [rcx]
0x180014619  mov     rax, [rax+8]
0x18001461d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014622  mov     [rbp+var_20], ebx
0x180014625  lea     rax, [rdi+48h]
0x180014629  mov     [rbp+var_28], rax
0x18001462d  mov     [rbp+var_1C], 0
0x180014634  test    rsi, rsi
0x180014637  jz      short loc_180014671
0x180014639  lea     rcx, [rbp+var_30]; this
0x18001463d  call    ?TakeLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJXZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock(void)
0x180014642  mov     r14d, eax
0x180014645  test    eax, eax
0x180014647  jns     short loc_180014671
0x180014649  mov     r9d, 155h
0x18001464f  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014656  mov     edx, 1
0x18001465b  mov     ecx, r14d
0x18001465e  call    Log_HREvent
0x180014663  lea     rcx, [rbp+var_30]; this
0x180014667  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x18001466c  jmp     loc_1800145E4
0x180014671  mov     eax, [r13+8]
0x180014675  lea     rdx, [rbp+var_18]
0x180014679  mov     rcx, [rdi+18h]
0x18001467d  movsd   xmm0, qword ptr [r13+0]
0x180014683  mov     [rbp+var_10], eax
0x180014686  movsd   [rbp+var_18], xmm0
0x18001468b  mov     rax, [rcx]
0x18001468e  mov     rax, [rax+20h]
0x180014692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014697  mov     r14d, eax
0x18001469a  test    eax, eax
0x18001469c  jns     short loc_1800146A6
0x18001469e  mov     r9d, 15Bh
0x1800146a4  jmp     short loc_18001464F
0x1800146a6  xor     r14d, r14d
0x1800146a9  lea     ebx, [r14+1]
0x1800146ad  cmp     r14d, [rdi+70h]
0x1800146b1  jnb     short loc_180014721
0x1800146b3  mov     rax, [rdi]
0x1800146b6  mov     r8, r13
0x1800146b9  mov     edx, r14d
0x1800146bc  mov     rcx, rdi
0x1800146bf  mov     rax, [rax+68h]
0x1800146c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c8  mov     r15d, eax
0x1800146cb  test    eax, eax
0x1800146cd  js      short loc_1800146D4
0x1800146cf  add     r14d, ebx
0x1800146d2  jmp     short loc_1800146AD
0x1800146d4  mov     r9d, 160h
0x1800146da  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800146e1  mov     edx, ebx
0x1800146e3  mov     ecx, r15d
0x1800146e6  call    Log_HREvent
0x1800146eb  lea     rcx, [rbp+var_30]; this
0x1800146ef  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x1800146f4  xor     edx, edx
0x1800146f6  lea     rcx, [rbp+var_40]
0x1800146fa  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800146ff  test    eax, eax
0x180014701  jns     short loc_180014719
0x180014703  mov     r9d, 39h ; '9'
0x180014709  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014710  xor     edx, edx
0x180014712  mov     ecx, eax
0x180014714  call    Log_HREvent
0x180014719  mov     eax, r15d
0x18001471c  jmp     loc_1800147ED
0x180014721  test    rsi, rsi
0x180014724  jz      short loc_180014783
0x180014726  mov     rax, [rsi]
0x180014729  mov     rcx, rsi
0x18001472c  mov     rax, [rax+20h]
0x180014730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014735  mov     esi, eax
0x180014737  test    eax, eax
0x180014739  jns     short loc_180014783
0x18001473b  mov     r9d, 165h
0x180014741  mov     edx, ebx
0x180014743  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001474a  mov     ecx, esi
0x18001474c  call    Log_HREvent
0x180014751  lea     rcx, [rbp+var_30]; this
0x180014755  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x18001475a  xor     edx, edx
0x18001475c  lea     rcx, [rbp+var_40]
0x180014760  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180014765  test    eax, eax
0x180014767  jns     short loc_18001477F
0x180014769  mov     r9d, 39h ; '9'
0x18001476f  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014776  xor     edx, edx
0x180014778  mov     ecx, eax
0x18001477a  call    Log_HREvent
0x18001477f  mov     eax, esi
0x180014781  jmp     short loc_1800147ED
0x180014783  mov     dl, bl
0x180014785  lea     rcx, [rbp+var_40]
0x180014789  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001478e  mov     esi, eax
0x180014790  mov     edx, ebx; int
0x180014792  test    eax, eax
0x180014794  jns     short loc_18001479E
0x180014796  mov     r9d, 169h
0x18001479c  jmp     short loc_180014743
0x18001479e  lea     rcx, [rbp+var_30]; this
0x1800147a2  call    ?ReleaseLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJH@Z; IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(int)
0x1800147a7  mov     esi, eax
0x1800147a9  test    eax, eax
0x1800147ab  jns     short loc_1800147B5
0x1800147ad  mov     r9d, 16Ah
0x1800147b3  jmp     short loc_180014741
0x1800147b5  mov     rcx, rdi; this
0x1800147b8  call    ?ReleaseIndexSourcesCache@IndexManager@IndexedFiltering@@AEAAXXZ; IndexedFiltering::IndexManager::ReleaseIndexSourcesCache(void)
0x1800147bd  lea     rcx, [rbp+var_30]; this
0x1800147c1  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x1800147c6  xor     edx, edx
0x1800147c8  lea     rcx, [rbp+var_40]
0x1800147cc  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800147d1  test    eax, eax
0x1800147d3  jns     short loc_1800147EB
0x1800147d5  mov     r9d, 39h ; '9'
0x1800147db  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800147e2  xor     edx, edx
0x1800147e4  mov     ecx, eax
0x1800147e6  call    Log_HREvent
0x1800147eb  xor     eax, eax
0x1800147ed  mov     rcx, [rbp+var_8]
0x1800147f1  xor     rcx, rsp; StackCookie
0x1800147f4  call    __security_check_cookie
0x1800147f9  add     rsp, 70h
0x1800147fd  pop     r15
0x1800147ff  pop     r14
0x180014801  pop     r13
0x180014803  pop     rdi
0x180014804  pop     rsi
0x180014805  pop     rbx
0x180014806  pop     rbp
0x180014807  retn
```
