# IndexedFiltering::IndexManager::_ProcessTransactionUpdates(IndexedFiltering::IIndexManagerClient *,IndexedFiltering::PendingUpdates &)

- ea: `0x1800148a8`
- end: `0x180014c4a`
- name: `?_ProcessTransactionUpdates@IndexManager@IndexedFiltering@@AEAAJPEAUIIndexManagerClient@2@AEAVPendingUpdates@2@@Z`
- size: `930`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *this, struct IndexedFiltering::IIndexManagerClient *, struct IndexedFiltering::PendingUpdates *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180014810`

## callees

- `0x180002da8`
- `0x18000d63c`
- `0x180012c9c`
- `0x1800130b8`
- `0x180013678`
- `0x180013e40`
- `0x180013f14`
- `0x180013fac`
- `0x1800148a8`
- `0x180014d5c`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800148fb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x18001496d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014aff`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x18001499d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180014b2b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180014c11`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::_ProcessTransactionUpdates(
        IndexedFiltering::IndexManager *this,
        struct IndexedFiltering::IIndexManagerClient *a2,
        struct IndexedFiltering::PendingUpdates *a3)
{
  __int64 v3; // r12
  struct IndexedFiltering::PendingUpdates *v4; // rbx
  __int64 v5; // r14
  struct IndexedFiltering::IIndexManagerClient *v6; // rsi
  int v8; // eax
  int started; // edi
  __int64 v10; // r9
  const char *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // eax
  unsigned __int64 v21; // r12
  unsigned __int64 i; // r13
  struct IndexedFiltering::BulkUpdateEntry *v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  struct IndexedFiltering::BulkUpdateEntry *v26; // rax
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, __int64 *, _QWORD, _QWORD); // rdi
  unsigned __int16 v29; // bx
  struct IndexedFiltering::BulkUpdateEntry *v30; // rax
  int v31; // ebx
  __int64 v32; // r9
  int v33; // eax
  unsigned int j; // edi
  __int64 (__fastcall *v35)(IndexedFiltering::IndexManager *, _QWORD, struct IndexedFiltering::BulkUpdateEntry *, unsigned __int64); // rbx
  struct IndexedFiltering::BulkUpdateEntry *v36; // rax
  int v37; // eax
  int v38; // [rsp+30h] [rbp-39h] BYREF
  __int64 v39; // [rsp+38h] [rbp-31h]
  _QWORD v40[2]; // [rsp+40h] [rbp-29h] BYREF
  int v41; // [rsp+50h] [rbp-19h]
  int v42; // [rsp+54h] [rbp-15h]
  IndexedFiltering::PendingUpdates *v43; // [rsp+58h] [rbp-11h]
  struct IndexedFiltering::IIndexManagerClient *v44; // [rsp+60h] [rbp-9h]
  __int64 v45; // [rsp+68h] [rbp-1h] BYREF
  int v46; // [rsp+70h] [rbp+7h]
  __int64 v47; // [rsp+78h] [rbp+Fh] BYREF
  int v48; // [rsp+80h] [rbp+17h]

  v3 = *((_QWORD *)a3 + 1);
  v4 = a3;
  v5 = *(_QWORD *)a3;
  v6 = a2;
  v43 = a3;
  v44 = a2;
  v8 = IndexedFiltering::IndexManager::CacheIndexSources(this);
  started = v8;
  if ( v8 < 0 )
  {
    v10 = 403;
    v11 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp";
    v12 = 1;
    v13 = (unsigned int)v8;
    goto LABEL_3;
  }
  v15 = *((_QWORD *)this + 3);
  v16 = *((_QWORD *)this + 15);
  v17 = *((_DWORD *)this + 28);
  v38 = 0;
  v39 = v16;
  v40[0] = v15;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v41 = v17;
  v40[1] = (char *)this + 72;
  v42 = 0;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v38);
  if ( started < 0 )
  {
    v19 = 413;
LABEL_9:
    Log_HREvent(
      (unsigned int)started,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      v19);
    IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v40);
    v20 = ScopedEndTransaction<ESESession>::EndTransaction(&v38, 0);
    if ( v20 >= 0 )
      return (unsigned int)started;
    v10 = 57;
    v11 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h";
    v12 = 0;
    v13 = (unsigned int)v20;
LABEL_3:
    Log_HREvent(v13, v12, v11, v10);
    return (unsigned int)started;
  }
  v21 = 0xCCCCCCCCCCCCCCCDuLL * ((v3 - v5) >> 3);
  if ( *((_QWORD *)this + 3) )
  {
    started = IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v40);
    if ( started < 0 )
    {
      v19 = 418;
      goto LABEL_9;
    }
    for ( i = 0; i < v21; ++i )
    {
      started = FailOnServiceShutdown();
      if ( started < 0 )
      {
        v19 = 422;
        goto LABEL_9;
      }
      if ( !*((_DWORD *)IndexedFiltering::PendingUpdates::item(v4, i) + 8) )
      {
        if ( *((_DWORD *)IndexedFiltering::PendingUpdates::item(v4, i) + 3) == 1 )
        {
          v45 = 0;
          v46 = 0;
          v23 = IndexedFiltering::PendingUpdates::item(v4, i);
          v24 = *((_QWORD *)this + 3);
          v45 = *(_QWORD *)v23;
          v46 = *((_DWORD *)v23 + 2);
          v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 32LL))(v24, &v45);
          started = v25;
          if ( ((v25 + 0x80000000) & 0x80000000) == 0 && v25 != -2147023728 )
          {
            v19 = 439;
            goto LABEL_9;
          }
        }
        else
        {
          v47 = 0;
          v48 = 0;
          v26 = IndexedFiltering::PendingUpdates::item(v4, i);
          v27 = *((_QWORD *)this + 3);
          v47 = *(_QWORD *)v26;
          v48 = *((_DWORD *)v26 + 2);
          v28 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL);
          v29 = *((_WORD *)IndexedFiltering::PendingUpdates::item(v4, i) + 12);
          v30 = IndexedFiltering::PendingUpdates::item(v43, i);
          v31 = v28(v27, &v47, *((_QWORD *)v30 + 2), v29);
          if ( v31 < 0 )
          {
            v32 = 452;
            goto LABEL_26;
          }
          v4 = v43;
        }
      }
    }
    v6 = v44;
  }
  for ( j = 0; j < *((_DWORD *)this + 28); ++j )
  {
    v35 = *(__int64 (__fastcall **)(IndexedFiltering::IndexManager *, _QWORD, struct IndexedFiltering::BulkUpdateEntry *, unsigned __int64))(*(_QWORD *)this + 112LL);
    v36 = IndexedFiltering::PendingUpdates::item(v43, 0);
    v31 = v35(this, j, v36, v21);
    if ( v31 < 0 )
    {
      v32 = 464;
      goto LABEL_26;
    }
  }
  if ( v6 )
  {
    v31 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManagerClient *))(*(_QWORD *)v6 + 24LL))(v6);
    if ( v31 < 0 )
    {
      v32 = 471;
LABEL_26:
      Log_HREvent(
        (unsigned int)v31,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        v32);
      IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v40);
      v33 = ScopedEndTransaction<ESESession>::EndTransaction(&v38, 0);
      if ( v33 < 0 )
        Log_HREvent(
          (unsigned int)v33,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      return (unsigned int)v31;
    }
  }
  LOBYTE(v18) = 1;
  v31 = ScopedEndTransaction<ESESession>::EndTransaction(&v38, v18);
  if ( v31 < 0 )
  {
    v32 = 474;
    goto LABEL_26;
  }
  v31 = IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(
          (IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v40,
          1);
  if ( v31 < 0 )
  {
    v32 = 475;
    goto LABEL_26;
  }
  IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v40);
  v37 = ScopedEndTransaction<ESESession>::EndTransaction(&v38, 0);
  if ( v37 < 0 )
    Log_HREvent(
      (unsigned int)v37,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  return 0;
}

```

## disassembly

```asm
0x1800148a8  mov     [rsp-8+arg_18], rbx
0x1800148ad  push    rbp
0x1800148ae  push    rsi
0x1800148af  push    rdi
0x1800148b0  push    r12
0x1800148b2  push    r13
0x1800148b4  push    r14
0x1800148b6  push    r15
0x1800148b8  lea     rbp, [rsp-27h]
0x1800148bd  sub     rsp, 90h
0x1800148c4  mov     rax, cs:__security_cookie
0x1800148cb  xor     rax, rsp
0x1800148ce  mov     [rbp+57h+var_38], rax
0x1800148d2  mov     r12, [r8+8]
0x1800148d6  mov     rbx, r8
0x1800148d9  mov     r14, [r8]
0x1800148dc  mov     rsi, rdx
0x1800148df  mov     [rbp+57h+var_68], rbx
0x1800148e3  mov     r15, rcx
0x1800148e6  mov     [rbp+57h+var_60], rdx
0x1800148ea  call    ?CacheIndexSources@IndexManager@IndexedFiltering@@AEAAJXZ; IndexedFiltering::IndexManager::CacheIndexSources(void)
0x1800148ef  mov     edi, eax
0x1800148f1  test    eax, eax
0x1800148f3  jns     short loc_180014915
0x1800148f5  mov     r9d, 193h
0x1800148fb  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014902  mov     edx, 1
0x180014907  mov     ecx, eax
0x180014909  call    Log_HREvent
0x18001490e  mov     eax, edi
0x180014910  jmp     loc_180014C23
0x180014915  mov     rcx, [r15+18h]
0x180014919  mov     rax, [r15+78h]
0x18001491d  mov     edi, [r15+70h]
0x180014921  mov     [rbp+57h+var_90], 0
0x180014928  mov     [rbp+57h+var_88], rax
0x18001492c  mov     [rbp+57h+var_80], rcx
0x180014930  test    rcx, rcx
0x180014933  jz      short loc_180014941
0x180014935  mov     rax, [rcx]
0x180014938  mov     rax, [rax+8]
0x18001493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014941  lea     rax, [r15+48h]
0x180014945  mov     [rbp+57h+var_70], edi
0x180014948  lea     rcx, [rbp+57h+var_90]
0x18001494c  mov     [rbp+57h+var_78], rax
0x180014950  mov     [rbp+57h+var_6C], 0
0x180014957  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x18001495c  mov     edi, eax
0x18001495e  test    eax, eax
0x180014960  jns     short loc_1800149AD
0x180014962  mov     r9d, 19Dh
0x180014968  mov     edx, 1
0x18001496d  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014974  mov     ecx, edi
0x180014976  call    Log_HREvent
0x18001497b  lea     rcx, [rbp+57h+var_80]; this
0x18001497f  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x180014984  xor     edx, edx
0x180014986  lea     rcx, [rbp+57h+var_90]
0x18001498a  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001498f  test    eax, eax
0x180014991  jns     loc_18001490E
0x180014997  mov     r9d, 39h ; '9'
0x18001499d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800149a4  xor     edx, edx
0x1800149a6  mov     ecx, eax
0x1800149a8  jmp     loc_180014909
0x1800149ad  sub     r12, r14
0x1800149b0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800149ba  sar     r12, 3
0x1800149be  mov     r14d, 1
0x1800149c4  imul    r12, rax
0x1800149c8  cmp     qword ptr [r15+18h], 0
0x1800149cd  jz      loc_180014B51
0x1800149d3  lea     rcx, [rbp+57h+var_80]; this
0x1800149d7  call    ?TakeLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJXZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock(void)
0x1800149dc  mov     edi, eax
0x1800149de  test    eax, eax
0x1800149e0  jns     short loc_1800149ED
0x1800149e2  mov     r9d, 1A2h
0x1800149e8  mov     edx, r14d
0x1800149eb  jmp     short loc_18001496D
0x1800149ed  xor     r13d, r13d
0x1800149f0  mov     esi, 80000000h
0x1800149f5  cmp     r13, r12
0x1800149f8  jnb     loc_180014B4D
0x1800149fe  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x180014a03  mov     edi, eax
0x180014a05  test    eax, eax
0x180014a07  js      loc_180014B42
0x180014a0d  mov     rdx, r13; unsigned __int64
0x180014a10  mov     rcx, rbx; this
0x180014a13  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014a18  cmp     dword ptr [rax+20h], 0
0x180014a1c  jnz     loc_180014AEE
0x180014a22  mov     rdx, r13; unsigned __int64
0x180014a25  mov     rcx, rbx; this
0x180014a28  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014a2d  mov     rdx, r13; unsigned __int64
0x180014a30  mov     rcx, rbx; this
0x180014a33  cmp     [rax+0Ch], r14d
0x180014a37  jnz     short loc_180014A85
0x180014a39  xor     eax, eax
0x180014a3b  mov     [rbp+57h+var_58], rax
0x180014a3f  mov     [rbp+57h+var_50], eax
0x180014a42  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014a47  mov     rcx, [r15+18h]
0x180014a4b  lea     rdx, [rbp+57h+var_58]
0x180014a4f  movsd   xmm0, qword ptr [rax]
0x180014a53  movsd   [rbp+57h+var_58], xmm0
0x180014a58  mov     eax, [rax+8]
0x180014a5b  mov     [rbp+57h+var_50], eax
0x180014a5e  mov     rax, [rcx]
0x180014a61  mov     rax, [rax+20h]
0x180014a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a6a  mov     edi, eax
0x180014a6c  lea     ecx, [rax+rsi]
0x180014a6f  test    esi, ecx
0x180014a71  jnz     short loc_180014AEE
0x180014a73  cmp     eax, 80070490h
0x180014a78  jz      short loc_180014AEE
0x180014a7a  mov     r9d, 1B7h
0x180014a80  jmp     loc_1800149E8
0x180014a85  xor     eax, eax
0x180014a87  mov     [rbp+57h+var_48], rax
0x180014a8b  mov     [rbp+57h+var_40], eax
0x180014a8e  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014a93  mov     rsi, [r15+18h]
0x180014a97  mov     rdx, r13; unsigned __int64
0x180014a9a  mov     rcx, rbx; this
0x180014a9d  movsd   xmm0, qword ptr [rax]
0x180014aa1  movsd   [rbp+57h+var_48], xmm0
0x180014aa6  mov     eax, [rax+8]
0x180014aa9  mov     [rbp+57h+var_40], eax
0x180014aac  mov     rax, [rsi]
0x180014aaf  mov     rdi, [rax+18h]
0x180014ab3  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014ab8  mov     rcx, [rbp+57h+var_68]; this
0x180014abc  mov     rdx, r13; unsigned __int64
0x180014abf  movzx   ebx, word ptr [rax+18h]
0x180014ac3  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014ac8  movzx   r9d, bx
0x180014acc  lea     rdx, [rbp+57h+var_48]
0x180014ad0  mov     rcx, rsi
0x180014ad3  mov     r8, [rax+10h]
0x180014ad7  mov     rax, rdi
0x180014ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014adf  mov     ebx, eax
0x180014ae1  test    eax, eax
0x180014ae3  js      short loc_180014AF6
0x180014ae5  mov     rbx, [rbp+57h+var_68]
0x180014ae9  mov     esi, 80000000h
0x180014aee  add     r13, r14
0x180014af1  jmp     loc_1800149F5
0x180014af6  mov     r9d, 1C4h
0x180014afc  mov     edx, r14d
0x180014aff  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014b06  mov     ecx, ebx
0x180014b08  call    Log_HREvent
0x180014b0d  lea     rcx, [rbp+57h+var_80]; this
0x180014b11  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x180014b16  xor     edx, edx
0x180014b18  lea     rcx, [rbp+57h+var_90]
0x180014b1c  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180014b21  test    eax, eax
0x180014b23  jns     short loc_180014B3B
0x180014b25  mov     r9d, 39h ; '9'
0x180014b2b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014b32  xor     edx, edx
0x180014b34  mov     ecx, eax
0x180014b36  call    Log_HREvent
0x180014b3b  mov     eax, ebx
0x180014b3d  jmp     loc_180014C23
0x180014b42  mov     r9d, 1A6h
0x180014b48  jmp     loc_1800149E8
0x180014b4d  mov     rsi, [rbp+57h+var_60]
0x180014b51  xor     edi, edi
0x180014b53  cmp     edi, [r15+70h]
0x180014b57  jnb     short loc_180014B94
0x180014b59  mov     rax, [r15]
0x180014b5c  xor     edx, edx; unsigned __int64
0x180014b5e  mov     rcx, [rbp+57h+var_68]; this
0x180014b62  mov     rbx, [rax+70h]
0x180014b66  call    ?item@PendingUpdates@IndexedFiltering@@QEAAAEAUBulkUpdateEntry@2@_K@Z; IndexedFiltering::PendingUpdates::item(unsigned __int64)
0x180014b6b  mov     r8, rax
0x180014b6e  mov     r9, r12
0x180014b71  mov     rax, rbx
0x180014b74  mov     edx, edi
0x180014b76  mov     rcx, r15
0x180014b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b7e  mov     ebx, eax
0x180014b80  test    eax, eax
0x180014b82  js      short loc_180014B89
0x180014b84  add     edi, r14d
0x180014b87  jmp     short loc_180014B53
0x180014b89  mov     r9d, 1D0h
0x180014b8f  jmp     loc_180014AFC
0x180014b94  test    rsi, rsi
0x180014b97  jz      short loc_180014BB9
0x180014b99  mov     rax, [rsi]
0x180014b9c  mov     rcx, rsi
0x180014b9f  mov     rax, [rax+18h]
0x180014ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ba8  mov     ebx, eax
0x180014baa  test    eax, eax
0x180014bac  jns     short loc_180014BB9
0x180014bae  mov     r9d, 1D7h
0x180014bb4  jmp     loc_180014AFC
0x180014bb9  mov     dl, r14b
0x180014bbc  lea     rcx, [rbp+57h+var_90]
0x180014bc0  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180014bc5  mov     ebx, eax
0x180014bc7  mov     edx, r14d; int
0x180014bca  test    eax, eax
0x180014bcc  jns     short loc_180014BD9
0x180014bce  mov     r9d, 1DAh
0x180014bd4  jmp     loc_180014AFF
0x180014bd9  lea     rcx, [rbp+57h+var_80]; this
0x180014bdd  call    ?ReleaseLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJH@Z; IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(int)
0x180014be2  mov     ebx, eax
0x180014be4  test    eax, eax
0x180014be6  jns     short loc_180014BF3
0x180014be8  mov     r9d, 1DBh
0x180014bee  jmp     loc_180014AFC
0x180014bf3  lea     rcx, [rbp+57h+var_80]; this
0x180014bf7  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x180014bfc  xor     edx, edx
0x180014bfe  lea     rcx, [rbp+57h+var_90]
0x180014c02  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180014c07  test    eax, eax
0x180014c09  jns     short loc_180014C21
0x180014c0b  mov     r9d, 39h ; '9'
0x180014c11  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014c18  xor     edx, edx
0x180014c1a  mov     ecx, eax
0x180014c1c  call    Log_HREvent
0x180014c21  xor     eax, eax
0x180014c23  mov     rcx, [rbp+57h+var_38]
0x180014c27  xor     rcx, rsp; StackCookie
0x180014c2a  call    __security_check_cookie
0x180014c2f  mov     rbx, [rsp+0C0h+arg_18]
0x180014c37  add     rsp, 90h
0x180014c3e  pop     r15
0x180014c40  pop     r14
0x180014c42  pop     r13
0x180014c44  pop     r12
0x180014c46  pop     rdi
0x180014c47  pop     rsi
0x180014c48  pop     rbp
0x180014c49  retn
```
