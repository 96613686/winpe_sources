# IndexedFiltering::IndexManager::ValueChanged(USOID const &,_SQLCEPROPVAL *,unsigned __int64,IndexedFiltering::IIndexManagerClient *,int)

- ea: `0x180014020`
- end: `0x180014397`
- name: `?ValueChanged@IndexManager@IndexedFiltering@@UEAAJAEBUUSOID@@PEAU_SQLCEPROPVAL@@_KPEAUIIndexManagerClient@2@H@Z`
- size: `887`
- prototype: `__int64 __usercall@<rax>(IndexedFiltering::IndexManager *__hidden this@<rcx>, const struct USOID *@<rdx>, struct _SQLCEPROPVAL *@<r8>, unsigned __int64@<r9>, struct IndexedFiltering::IIndexManagerClient *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x180012c9c`
- `0x180012f68`
- `0x1800130b8`
- `0x180013678`
- `0x180013e00`
- `0x180013e40`
- `0x180013f14`
- `0x180013fac`
- `0x180014020`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800140b5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800140e1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014121`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x18001419f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014242`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800142ab`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014365`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180014149`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180014271`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x1800142d7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180014346`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::ValueChanged(
        IndexedFiltering::IndexManager *this,
        const struct USOID *a2,
        struct _SQLCEPROPVAL *a3,
        __int64 a4,
        struct IndexedFiltering::IIndexManagerClient *a5,
        int a6)
{
  const struct USOID *v8; // r15
  __int64 v10; // r9
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // edi
  int v15; // eax
  int v16; // r14d
  __int64 v17; // r9
  const char *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  int started; // eax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // ebx
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // xmm0_8
  unsigned int i; // r14d
  int v29; // eax
  unsigned int v30; // r15d
  int v31; // eax
  int v32; // esi
  __int64 v33; // r9
  int v34; // eax
  int v35; // eax
  int v36; // [rsp+30h] [rbp-49h] BYREF
  __int64 v37; // [rsp+38h] [rbp-41h]
  _QWORD v38[2]; // [rsp+40h] [rbp-39h] BYREF
  int v39; // [rsp+50h] [rbp-29h]
  int v40; // [rsp+54h] [rbp-25h]
  const struct USOID *v41; // [rsp+58h] [rbp-21h]
  __int64 v42; // [rsp+60h] [rbp-19h] BYREF
  int v43; // [rsp+68h] [rbp-11h]

  v41 = a2;
  v8 = a2;
  if ( !a3 || !a4 )
  {
    v10 = 220;
    v11 = -2147024809;
    goto LABEL_46;
  }
  if ( *((_DWORD *)this + 32) )
  {
    if ( a5 )
    {
      v10 = 224;
      v11 = -2147418113;
LABEL_46:
      Log_HREvent(
        v11,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        v10);
      return v11;
    }
    v12 = IndexedFiltering::IndexManager::AddPendingUpdate((__int64)this, (int *)a2, 2, (__int64)a3, a4, a6);
    v13 = v12;
    if ( v12 < 0 )
    {
      Log_HREvent(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        231);
      return v13;
    }
    return 0;
  }
  v15 = IndexedFiltering::IndexManager::CacheIndexSources(this);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = 237;
    v18 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp";
    v19 = 1;
    v20 = (unsigned int)v15;
    goto LABEL_10;
  }
  v37 = *((_QWORD *)this + 15);
  v36 = 0;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v36);
  v16 = started;
  if ( started < 0 )
  {
    Log_HREvent(
      (unsigned int)started,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      242);
LABEL_14:
    v22 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
    if ( v22 >= 0 )
      return (unsigned int)v16;
    v17 = 57;
    v18 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h";
    v19 = 0;
    v20 = (unsigned int)v22;
LABEL_10:
    Log_HREvent(v20, v19, v18, v17);
    return (unsigned int)v16;
  }
  v23 = *((_QWORD *)this + 3);
  v24 = *((_DWORD *)this + 28);
  v38[0] = v23;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
  v39 = v24;
  v38[1] = (char *)this + 72;
  v40 = 0;
  if ( a5 )
  {
    v16 = IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38);
    if ( v16 < 0 )
    {
      v25 = 249;
LABEL_21:
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        v25);
      IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38);
      goto LABEL_14;
    }
  }
  if ( !a6 )
  {
    v26 = *((_QWORD *)this + 3);
    v27 = *(_QWORD *)v8;
    v43 = *((_DWORD *)v8 + 2);
    v42 = v27;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct _SQLCEPROPVAL *, _QWORD))(*(_QWORD *)v26 + 24LL))(
            v26,
            &v42,
            a3,
            (unsigned __int16)a4);
    if ( v16 < 0 )
    {
      v25 = 264;
      goto LABEL_21;
    }
  }
  for ( i = 0; i < *((_DWORD *)this + 28); ++i )
  {
    v29 = (*(__int64 (__fastcall **)(IndexedFiltering::IndexManager *, _QWORD, const struct USOID *, struct _SQLCEPROPVAL *, __int64))(*(_QWORD *)this + 96LL))(
            this,
            i,
            v8,
            a3,
            a4);
    v30 = v29;
    if ( v29 < 0 )
    {
      Log_HREvent(
        (unsigned int)v29,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        273);
      IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38);
      v31 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
      if ( v31 < 0 )
        Log_HREvent(
          (unsigned int)v31,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
          57);
      return v30;
    }
    v8 = v41;
  }
  if ( a5
    && (v32 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManagerClient *))(*(_QWORD *)a5 + 32LL))(a5),
        v32 < 0) )
  {
    v33 = 278;
  }
  else
  {
    v32 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 1u);
    if ( v32 >= 0 )
    {
      v32 = IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(
              (IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38,
              1);
      if ( v32 >= 0 )
      {
        IndexedFiltering::IndexManager::ReleaseIndexSourcesCache(this);
        IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38);
        v35 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
        if ( v35 < 0 )
          Log_HREvent(
            (unsigned int)v35,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
            57);
        return 0;
      }
      v33 = 283;
    }
    else
    {
      v33 = 282;
    }
  }
  Log_HREvent(
    (unsigned int)v32,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
    v33);
  IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction((IndexedFiltering::IndexManager::AutoDataSourceTransaction *)v38);
  v34 = ScopedEndTransaction<ESESession>::EndTransaction((__int64)&v36, 0);
  if ( v34 < 0 )
    Log_HREvent(
      (unsigned int)v34,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x180014020  push    rbp
0x180014022  push    rbx
0x180014023  push    rsi
0x180014024  push    rdi
0x180014025  push    r12
0x180014027  push    r13
0x180014029  push    r14
0x18001402b  push    r15
0x18001402d  lea     rbp, [rsp-0Fh]
0x180014032  sub     rsp, 88h
0x180014039  mov     rax, cs:__security_cookie
0x180014040  xor     rax, rsp
0x180014043  mov     [rbp+47h+var_50], rax
0x180014047  mov     rsi, [rbp+47h+arg_20]
0x18001404b  mov     r12, r9
0x18001404e  mov     [rbp+47h+var_68], rdx
0x180014052  mov     r13, r8
0x180014055  mov     r15, rdx
0x180014058  mov     rdi, rcx
0x18001405b  test    r8, r8
0x18001405e  jz      loc_18001435A
0x180014064  test    r9, r9
0x180014067  jz      loc_18001435A
0x18001406d  cmp     dword ptr [rcx+80h], 0
0x180014074  jz      short loc_1800140CF
0x180014076  test    rsi, rsi
0x180014079  jz      short loc_18001408B
0x18001407b  mov     r9d, 0E0h
0x180014081  mov     ebx, 8000FFFFh
0x180014086  jmp     loc_180014365
0x18001408b  mov     eax, [rbp+47h+arg_28]
0x18001408e  mov     r9, r13
0x180014091  mov     [rsp+0C0h+var_98], eax
0x180014095  mov     r8d, 2
0x18001409b  mov     [rsp+0C0h+var_A0], r12
0x1800140a0  call    ?AddPendingUpdate@IndexManager@IndexedFiltering@@AEAAJAEBUUSOID@@W4BulkUpdateEntryType@2@PEAU_SQLCEPROPVAL@@_KH@Z; IndexedFiltering::IndexManager::AddPendingUpdate(USOID const &,IndexedFiltering::BulkUpdateEntryType,_SQLCEPROPVAL *,unsigned __int64,int)
0x1800140a5  mov     edi, eax
0x1800140a7  test    eax, eax
0x1800140a9  jns     loc_180014356
0x1800140af  mov     r9d, 0E7h
0x1800140b5  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800140bc  mov     edx, 1
0x1800140c1  mov     ecx, eax
0x1800140c3  call    Log_HREvent
0x1800140c8  mov     eax, edi
0x1800140ca  jmp     loc_180014377
0x1800140cf  call    ?CacheIndexSources@IndexManager@IndexedFiltering@@AEAAJXZ; IndexedFiltering::IndexManager::CacheIndexSources(void)
0x1800140d4  mov     r14d, eax
0x1800140d7  test    eax, eax
0x1800140d9  jns     short loc_1800140FC
0x1800140db  mov     r9d, 0EDh
0x1800140e1  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800140e8  mov     edx, 1
0x1800140ed  mov     ecx, eax
0x1800140ef  call    Log_HREvent
0x1800140f4  mov     eax, r14d
0x1800140f7  jmp     loc_180014377
0x1800140fc  mov     rax, [rdi+78h]
0x180014100  lea     rcx, [rbp+47h+var_90]
0x180014104  mov     [rbp+47h+var_88], rax
0x180014108  mov     [rbp+47h+var_90], 0
0x18001410f  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x180014114  mov     r14d, eax
0x180014117  test    eax, eax
0x180014119  jns     short loc_180014156
0x18001411b  mov     r9d, 0F2h
0x180014121  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014128  mov     edx, 1
0x18001412d  mov     ecx, eax
0x18001412f  call    Log_HREvent
0x180014134  xor     edx, edx
0x180014136  lea     rcx, [rbp+47h+var_90]
0x18001413a  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001413f  test    eax, eax
0x180014141  jns     short loc_1800140F4
0x180014143  mov     r9d, 39h ; '9'
0x180014149  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014150  xor     edx, edx
0x180014152  mov     ecx, eax
0x180014154  jmp     short loc_1800140EF
0x180014156  mov     rcx, [rdi+18h]
0x18001415a  mov     ebx, [rdi+70h]
0x18001415d  mov     [rbp+47h+var_80], rcx
0x180014161  test    rcx, rcx
0x180014164  jz      short loc_180014172
0x180014166  mov     rax, [rcx]
0x180014169  mov     rax, [rax+8]
0x18001416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014172  mov     [rbp+47h+var_70], ebx
0x180014175  lea     rax, [rdi+48h]
0x180014179  mov     [rbp+47h+var_78], rax
0x18001417d  mov     [rbp+47h+var_6C], 0
0x180014184  test    rsi, rsi
0x180014187  jz      short loc_1800141C1
0x180014189  lea     rcx, [rbp+47h+var_80]; this
0x18001418d  call    ?TakeLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJXZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock(void)
0x180014192  mov     r14d, eax
0x180014195  test    eax, eax
0x180014197  jns     short loc_1800141C1
0x180014199  mov     r9d, 0F9h
0x18001419f  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800141a6  mov     edx, 1
0x1800141ab  mov     ecx, r14d
0x1800141ae  call    Log_HREvent
0x1800141b3  lea     rcx, [rbp+47h+var_80]; this
0x1800141b7  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x1800141bc  jmp     loc_180014134
0x1800141c1  cmp     [rbp+47h+arg_28], 0
0x1800141c5  jnz     short loc_180014202
0x1800141c7  mov     eax, [r15+8]
0x1800141cb  lea     rdx, [rbp+47h+var_60]
0x1800141cf  mov     rcx, [rdi+18h]
0x1800141d3  movzx   r9d, r12w
0x1800141d7  movsd   xmm0, qword ptr [r15]
0x1800141dc  mov     r8, r13
0x1800141df  mov     [rbp+47h+var_58], eax
0x1800141e2  movsd   [rbp+47h+var_60], xmm0
0x1800141e7  mov     rax, [rcx]
0x1800141ea  mov     rax, [rax+18h]
0x1800141ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141f3  mov     r14d, eax
0x1800141f6  test    eax, eax
0x1800141f8  jns     short loc_180014202
0x1800141fa  mov     r9d, 108h
0x180014200  jmp     short loc_18001419F
0x180014202  xor     r14d, r14d
0x180014205  lea     ebx, [r14+1]
0x180014209  cmp     r14d, [rdi+70h]
0x18001420d  jnb     short loc_180014289
0x18001420f  mov     rax, [rdi]
0x180014212  mov     r9, r13
0x180014215  mov     r8, r15
0x180014218  mov     [rsp+0C0h+var_A0], r12
0x18001421d  mov     edx, r14d
0x180014220  mov     rcx, rdi
0x180014223  mov     rax, [rax+60h]
0x180014227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422c  mov     r15d, eax
0x18001422f  test    eax, eax
0x180014231  js      short loc_18001423C
0x180014233  mov     r15, [rbp+47h+var_68]
0x180014237  add     r14d, ebx
0x18001423a  jmp     short loc_180014209
0x18001423c  mov     r9d, 111h
0x180014242  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014249  mov     edx, ebx
0x18001424b  mov     ecx, r15d
0x18001424e  call    Log_HREvent
0x180014253  lea     rcx, [rbp+47h+var_80]; this
0x180014257  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x18001425c  xor     edx, edx
0x18001425e  lea     rcx, [rbp+47h+var_90]
0x180014262  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180014267  test    eax, eax
0x180014269  jns     short loc_180014281
0x18001426b  mov     r9d, 39h ; '9'
0x180014271  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014278  xor     edx, edx
0x18001427a  mov     ecx, eax
0x18001427c  call    Log_HREvent
0x180014281  mov     eax, r15d
0x180014284  jmp     loc_180014377
0x180014289  test    rsi, rsi
0x18001428c  jz      short loc_1800142EE
0x18001428e  mov     rax, [rsi]
0x180014291  mov     rcx, rsi
0x180014294  mov     rax, [rax+20h]
0x180014298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001429d  mov     esi, eax
0x18001429f  test    eax, eax
0x1800142a1  jns     short loc_1800142EE
0x1800142a3  mov     r9d, 116h
0x1800142a9  mov     edx, ebx
0x1800142ab  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800142b2  mov     ecx, esi
0x1800142b4  call    Log_HREvent
0x1800142b9  lea     rcx, [rbp+47h+var_80]; this
0x1800142bd  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x1800142c2  xor     edx, edx
0x1800142c4  lea     rcx, [rbp+47h+var_90]
0x1800142c8  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800142cd  test    eax, eax
0x1800142cf  jns     short loc_1800142E7
0x1800142d1  mov     r9d, 39h ; '9'
0x1800142d7  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800142de  xor     edx, edx
0x1800142e0  mov     ecx, eax
0x1800142e2  call    Log_HREvent
0x1800142e7  mov     eax, esi
0x1800142e9  jmp     loc_180014377
0x1800142ee  mov     dl, bl
0x1800142f0  lea     rcx, [rbp+47h+var_90]
0x1800142f4  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x1800142f9  mov     esi, eax
0x1800142fb  mov     edx, ebx; int
0x1800142fd  test    eax, eax
0x1800142ff  jns     short loc_180014309
0x180014301  mov     r9d, 11Ah
0x180014307  jmp     short loc_1800142AB
0x180014309  lea     rcx, [rbp+47h+var_80]; this
0x18001430d  call    ?ReleaseLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJH@Z; IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(int)
0x180014312  mov     esi, eax
0x180014314  test    eax, eax
0x180014316  jns     short loc_180014320
0x180014318  mov     r9d, 11Bh
0x18001431e  jmp     short loc_1800142A9
0x180014320  mov     rcx, rdi; this
0x180014323  call    ?ReleaseIndexSourcesCache@IndexManager@IndexedFiltering@@AEAAXXZ; IndexedFiltering::IndexManager::ReleaseIndexSourcesCache(void)
0x180014328  lea     rcx, [rbp+47h+var_80]; this
0x18001432c  call    ??1AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAA@XZ; IndexedFiltering::IndexManager::AutoDataSourceTransaction::~AutoDataSourceTransaction(void)
0x180014331  xor     edx, edx
0x180014333  lea     rcx, [rbp+47h+var_90]
0x180014337  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x18001433c  test    eax, eax
0x18001433e  jns     short loc_180014356
0x180014340  mov     r9d, 39h ; '9'
0x180014346  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001434d  xor     edx, edx
0x18001434f  mov     ecx, eax
0x180014351  call    Log_HREvent
0x180014356  xor     eax, eax
0x180014358  jmp     short loc_180014377
0x18001435a  mov     r9d, 0DCh
0x180014360  mov     ebx, 80070057h
0x180014365  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001436c  xor     edx, edx
0x18001436e  mov     ecx, ebx
0x180014370  call    Log_HREvent
0x180014375  mov     eax, ebx
0x180014377  mov     rcx, [rbp+47h+var_50]
0x18001437b  xor     rcx, rsp; StackCookie
0x18001437e  call    __security_check_cookie
0x180014383  add     rsp, 88h
0x18001438a  pop     r15
0x18001438c  pop     r14
0x18001438e  pop     r13
0x180014390  pop     r12
0x180014392  pop     rdi
0x180014393  pop     rsi
0x180014394  pop     rbx
0x180014395  pop     rbp
0x180014396  retn
```
