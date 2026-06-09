# FetchingVisitor::CallRemoteAndMergeState(IUiaNode *,int,TraverseStateIn *,TraverseStateOut *)

- ea: `0x1800d2fa0`
- end: `0x1800d3642`
- name: `?CallRemoteAndMergeState@FetchingVisitor@@UEAAJPEAVIUiaNode@@HPEAUTraverseStateIn@@PEAUTraverseStateOut@@@Z`
- size: `1698`
- prototype: `__int64 __fastcall(FetchingVisitor *__hidden this, struct IUiaNode *, int, struct TraverseStateIn *, struct TraverseStateOut *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18002f580`
- `0x180047b70`
- `0x1800d2fa0`
- `0x1800d3648`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9240`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d310d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d31ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d310d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d31ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d306c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3175`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d306c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3175`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d30eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d31d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d30eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d31d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d30fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d31dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d30fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d31dd`

## string_xrefs

- `0x1800d3236`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800d33e2`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800d34a4`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800d34e1`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800d3356`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d337d`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d3394`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d33fa`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d34bc`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d359b`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d35c6`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d35fe`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800d324e`: `onecore\windows\accessibletech\uiautomationcore\bulkfetch.cpp`
- `0x1800d33b5`: `onecore\windows\accessibletech\uiautomationcore\bulkfetch.cpp`
- `0x1800d34f9`: `onecore\windows\accessibletech\uiautomationcore\bulkfetch.cpp`
- `0x1800d3521`: `onecore\windows\accessibletech\uiautomationcore\bulkfetch.cpp`
- `0x1800d361f`: `onecore\windows\accessibletech\uiautomationcore\bulkfetch.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FetchingVisitor::CallRemoteAndMergeState(
        RTL_SRWLOCK *this,
        struct IUiaNode *a2,
        unsigned int a3,
        struct TraverseStateIn *a4,
        struct TraverseStateOut *a5)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r12
  _BYTE *Ptr; // r13
  _BYTE *v10; // rsi
  __int64 Ptr_low; // r8
  char *v12; // rdi
  unsigned __int64 v13; // rdi
  char *v14; // r12
  unsigned int v15; // edi
  __int64 v16; // r15
  RTL_SRWLOCK *v17; // rbx
  _BYTE *v18; // r13
  unsigned __int64 v19; // rcx
  unsigned int v20; // esi
  _BYTE *v21; // r12
  unsigned __int64 v22; // rdi
  _BYTE *v23; // r13
  char *v24; // r14
  unsigned int v26; // eax
  unsigned int v27; // r15d
  unsigned __int64 v28; // rax
  char *v29; // rdi
  unsigned __int64 v30; // rsi
  PVOID v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // kr00_8
  char *v37; // rdi
  unsigned __int64 v38; // r13
  PVOID v39; // rcx
  int v40[2]; // [rsp+20h] [rbp-91h]
  int v41; // [rsp+20h] [rbp-91h]
  int v42; // [rsp+20h] [rbp-91h]
  int v43; // [rsp+20h] [rbp-91h]
  int v44; // [rsp+20h] [rbp-91h]
  int v45; // [rsp+20h] [rbp-91h]
  int v46; // [rsp+20h] [rbp-91h]
  int v47; // [rsp+20h] [rbp-91h]
  RTL_SRWLOCK *v48; // [rsp+70h] [rbp-41h] BYREF
  void *Src; // [rsp+80h] [rbp-31h] BYREF
  unsigned int v50; // [rsp+88h] [rbp-29h]
  void *v51; // [rsp+90h] [rbp-21h]
  int v52; // [rsp+98h] [rbp-19h]
  __int64 v53; // [rsp+A0h] [rbp-11h]
  __int64 v54; // [rsp+A8h] [rbp-9h]
  char v55; // [rsp+B0h] [rbp-1h]
  __int64 v56; // [rsp+B8h] [rbp+7h]
  int v57; // [rsp+C0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]
  RTL_SRWLOCK *v59; // [rsp+110h] [rbp+5Fh] BYREF
  _BYTE *v60; // [rsp+118h] [rbp+67h]

  v55 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  Src = 0;
  v50 = 0;
  v51 = 0;
  v56 = 0;
  v57 = 0;
  *(RTL_SRWLOCK *)v40 = this[2];
  v6 = (*(__int64 (__fastcall **)(struct IUiaNode *, _QWORD, struct TraverseStateIn *, struct TraverseStateOut *))(*(_QWORD *)a2 + 128LL))(
         a2,
         a3,
         a4,
         a5);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\bulkfetch.cpp",
      (const char *)(unsigned int)v6,
      v40[0]);
    AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
    return v7;
  }
  v8 = v50;
  AcquireSRWLockExclusive(this + 9);
  v59 = this + 9;
  Ptr = this[6].Ptr;
  v10 = this[8].Ptr;
  Ptr_low = LODWORD(this[7].Ptr);
  if ( (unsigned int)((__int64)&Ptr[24 * Ptr_low - (_QWORD)v10] / 24) < v50 )
  {
    if ( (_DWORD)Ptr_low )
    {
      v26 = 2 * Ptr_low;
      if ( (unsigned __int64)(2 * Ptr_low) > 0xFFFFFFFF )
      {
        v34 = 105;
        goto LABEL_38;
      }
    }
    else
    {
      v26 = 32;
    }
    v27 = v26 + v50;
    if ( v26 + v50 >= v26 )
    {
      v28 = 24LL * v27;
      if ( !is_mul_ok(v27, 0x18u) )
        v28 = -1;
      v29 = (char *)operator new[](v28, (const struct std::nothrow_t *)std::nothrow);
      if ( v29 )
      {
        v30 = 0xFFFFFFF800000008uLL * (unsigned int)((v10 - Ptr) >> 3);
        if ( v30 <= 0xFFFFFFFF )
        {
          memcpy_0(v29, this[6].Ptr, (unsigned int)v30);
          v31 = this[6].Ptr;
          if ( v31 && v31 != this[4].Ptr )
            operator delete(v31);
          this[6].Ptr = v29;
          LODWORD(this[7].Ptr) = v27;
          this[8].Ptr = &v29[v30];
          operator delete(0);
          goto LABEL_3;
        }
        v20 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
          (const char *)0x80070216LL,
          v40[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
          (const char *)0x80070216LL,
          v44);
        operator delete(v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
          (const char *)0x8007000ELL,
          v40[0]);
        operator delete(0);
        v20 = -2147024882;
      }
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
        (const char *)v20,
        v42);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v59);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\bulkfetch.cpp",
        (const char *)v20,
        v43);
      AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
      return v20;
    }
    v34 = 107;
LABEL_38:
    v20 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)0x80070216LL,
      v40[0]);
    goto LABEL_39;
  }
LABEL_3:
  v12 = (char *)this[8].Ptr;
  this[8].Ptr = &v12[24 * v8];
  v13 = 0xAAAAAAAAAAAAAAABuLL * ((v12 - (char *)this[6].Ptr) >> 3);
  if ( this != (RTL_SRWLOCK *)-72LL )
    ReleaseSRWLockExclusive(this + 9);
  AcquireSRWLockShared(this + 9);
  v14 = (char *)this[6].Ptr;
  if ( this != (RTL_SRWLOCK *)-72LL )
    ReleaseSRWLockShared(this + 9);
  if ( 24 * (unsigned __int64)v50 > 0xFFFFFFFF )
  {
    v20 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
      (const char *)0x80070216LL,
      v40[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\bulkfetch.cpp",
      (const char *)0x80070216LL,
      v41);
    AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
    return v20;
  }
  memcpy_0(&v14[24 * (unsigned int)v13], Src, 24 * v50);
  operator delete(Src);
  v15 = 0;
  Src = 0;
  v50 = 0;
  if ( v51 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v51 + v16) );
  }
  else
  {
    LODWORD(v16) = 0;
  }
  v17 = this + 16;
  AcquireSRWLockExclusive(this + 16);
  v48 = this + 16;
  v60 = this[13].Ptr;
  v18 = this[15].Ptr;
  v19 = 2LL * LODWORD(this[14].Ptr);
  v20 = -2147024362;
  if ( (unsigned int)((__int64)&v60[v19 - (_QWORD)v18] >> 1) < (unsigned int)v16 )
  {
    v21 = 0;
    if ( LODWORD(this[14].Ptr) )
    {
      if ( v19 > 0xFFFFFFFF )
      {
        v33 = 105;
        goto LABEL_35;
      }
    }
    else
    {
      LODWORD(v19) = 32;
    }
    v32 = v19 + v16;
    LODWORD(v59) = v19 + v16;
    if ( (int)v19 + (int)v16 >= (unsigned int)v19 )
    {
      v36 = v32;
      v35 = 2LL * v32;
      if ( !is_mul_ok(v36, 2u) )
        v35 = -1;
      v37 = (char *)operator new[](v35, (const struct std::nothrow_t *)std::nothrow);
      if ( !v37 )
      {
        v15 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
          (const char *)0x8007000ELL,
          v40[0]);
        operator delete(0);
        goto LABEL_13;
      }
      v38 = 2LL * (unsigned int)((v18 - v60) >> 1);
      if ( v38 <= 0xFFFFFFFF )
      {
        memcpy_0(v37, this[13].Ptr, (unsigned int)v38);
        v39 = this[13].Ptr;
        if ( v39 && v39 != this[11].Ptr )
          operator delete(v39);
        this[13].Ptr = v37;
        LODWORD(this[14].Ptr) = (_DWORD)v59;
        this[15].Ptr = &v37[v38];
        operator delete(0);
        v15 = 0;
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
        (const char *)0x80070216LL,
        v40[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
        (const char *)0x80070216LL,
        v45);
      operator delete(v37);
LABEL_36:
      v15 = -2147024362;
      goto LABEL_13;
    }
    v33 = 107;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)0x80070216LL,
      v40[0]);
    goto LABEL_36;
  }
LABEL_12:
  v21 = this[15].Ptr;
LABEL_13:
  if ( (v15 & 0x80000000) == 0 )
  {
    v22 = 2LL * (unsigned int)v16;
    this[15].Ptr = (char *)this[15].Ptr + v22;
    v23 = this[13].Ptr;
    if ( this != (RTL_SRWLOCK *)-128LL )
      ReleaseSRWLockExclusive(this + 16);
    AcquireSRWLockShared(this + 16);
    v24 = (char *)this[13].Ptr;
    if ( v17 )
      ReleaseSRWLockShared(v17);
    if ( v22 <= 0xFFFFFFFF )
    {
      memcpy_0(&v24[2 * (unsigned int)((v21 - v23) >> 1)], v51, (unsigned int)v22);
      AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
      (const char *)0x80070216LL,
      v40[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\bulkfetch.cpp",
      (const char *)0x80070216LL,
      v46);
    AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
    return v20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF4,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
    (const char *)v15,
    v40[0]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v48);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15D,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\bulkfetch.cpp",
    (const char *)v15,
    v47);
  AutoCleanupInfo<UiaCacheResponse>::SafeRelease(&Src);
  return v15;
}

```

## disassembly

```asm
0x1800d2fa0  mov     [rsp-8+arg_10], rbx
0x1800d2fa5  push    rbp
0x1800d2fa6  push    rsi
0x1800d2fa7  push    rdi
0x1800d2fa8  push    r12
0x1800d2faa  push    r13
0x1800d2fac  push    r14
0x1800d2fae  push    r15
0x1800d2fb0  lea     rbp, [rsp-1Fh]
0x1800d2fb5  sub     rsp, 0D0h
0x1800d2fbc  mov     r10, r9
0x1800d2fbf  mov     r11d, r8d
0x1800d2fc2  mov     rbx, rdx
0x1800d2fc5  mov     r14, rcx
0x1800d2fc8  xor     edi, edi
0x1800d2fca  mov     [rbp+4Fh+var_50], dil
0x1800d2fce  mov     [rbp+4Fh+var_68], edi
0x1800d2fd1  mov     [rbp+4Fh+var_60], rdi
0x1800d2fd5  mov     [rbp+4Fh+var_58], rdi
0x1800d2fd9  mov     [rbp+4Fh+Src], rdi
0x1800d2fdd  mov     [rbp+4Fh+var_78], edi
0x1800d2fe0  mov     [rbp+4Fh+var_70], rdi
0x1800d2fe4  mov     [rbp+4Fh+var_48], rdi
0x1800d2fe8  mov     [rbp+4Fh+var_40], edi
0x1800d2feb  lea     rdx, [rcx+90h]
0x1800d2ff2  lea     r8, [rcx+1Ch]
0x1800d2ff6  lea     r9, [rcx+18h]
0x1800d2ffa  mov     rax, [rbx]
0x1800d2ffd  lea     rcx, [rbp+4Fh+Src]
0x1800d3001  mov     [rsp+100h+var_A0], rcx
0x1800d3006  mov     [rsp+100h+var_A8], rdx
0x1800d300b  mov     [rsp+100h+var_B0], r8
0x1800d3010  mov     [rsp+100h+var_B8], r9
0x1800d3015  mov     rcx, [r14+98h]
0x1800d301c  mov     [rsp+100h+var_C0], rcx
0x1800d3021  mov     ecx, [rdx]
0x1800d3023  mov     [rsp+100h+var_C8], ecx
0x1800d3027  mov     ecx, [r8]
0x1800d302a  mov     [rsp+100h+var_D0], ecx
0x1800d302e  mov     ecx, [r9]
0x1800d3031  mov     [rsp+100h+var_D8], ecx
0x1800d3035  mov     rcx, [r14+10h]
0x1800d3039  mov     qword ptr [rsp+100h+var_E0], rcx; int
0x1800d303e  mov     r9, [rbp+4Fh+arg_20]
0x1800d3042  mov     r8, r10
0x1800d3045  mov     edx, r11d
0x1800d3048  mov     rcx, rbx
0x1800d304b  mov     rax, [rax+80h]
0x1800d3052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3057  mov     ebx, eax
0x1800d3059  test    eax, eax
0x1800d305b  js      loc_1800D351A
0x1800d3061  mov     r12d, [rbp+4Fh+var_78]
0x1800d3065  lea     rbx, [r14+48h]
0x1800d3069  mov     rcx, rbx; SRWLock
0x1800d306c  call    cs:__imp_AcquireSRWLockExclusive
0x1800d3072  mov     [rbp+4Fh+arg_0], rbx
0x1800d3076  mov     r13, [r14+30h]
0x1800d307a  mov     rsi, [r14+40h]
0x1800d307e  mov     r8d, [r14+38h]
0x1800d3082  lea     rcx, [r8+r8*2]
0x1800d3086  shl     rcx, 3
0x1800d308a  sub     rcx, rsi
0x1800d308d  add     rcx, r13
0x1800d3090  mov     rax, 2AAAAAAAAAAAAAABh
0x1800d309a  imul    rcx
0x1800d309d  sar     rdx, 2
0x1800d30a1  mov     rax, rdx
0x1800d30a4  shr     rax, 3Fh
0x1800d30a8  add     rdx, rax
0x1800d30ab  mov     ecx, 0FFFFFFFFh
0x1800d30b0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800d30b4  cmp     edx, r12d
0x1800d30b7  jb      loc_1800D3287
0x1800d30bd  mov     rdi, [r14+40h]
0x1800d30c1  lea     rcx, [r12+r12*2]
0x1800d30c5  lea     rax, [rdi+rcx*8]
0x1800d30c9  mov     [r14+40h], rax
0x1800d30cd  sub     rdi, [r14+30h]
0x1800d30d1  sar     rdi, 3
0x1800d30d5  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800d30df  imul    rdi, rax
0x1800d30e3  test    rbx, rbx
0x1800d30e6  jz      short loc_1800D30F1
0x1800d30e8  mov     rcx, rbx; SRWLock
0x1800d30eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d30f1  mov     esi, [rbp+4Fh+var_78]
0x1800d30f4  mov     r15, [rbp+4Fh+Src]
0x1800d30f8  mov     rcx, rbx; SRWLock
0x1800d30fb  call    cs:__imp_AcquireSRWLockShared
0x1800d3101  mov     r12, [r14+30h]
0x1800d3105  test    rbx, rbx
0x1800d3108  jz      short loc_1800D3113
0x1800d310a  mov     rcx, rbx; SRWLock
0x1800d310d  call    cs:__imp_ReleaseSRWLockShared
0x1800d3113  lea     rcx, [rsi+rsi*2]
0x1800d3117  shl     rcx, 3
0x1800d311b  mov     eax, 0FFFFFFFFh
0x1800d3120  cmp     rcx, rax
0x1800d3123  ja      loc_1800D322A
0x1800d3129  mov     r8d, ecx; Size
0x1800d312c  mov     eax, edi
0x1800d312e  lea     rcx, [rax+rax*2]
0x1800d3132  lea     rcx, [r12+rcx*8]; void *
0x1800d3136  mov     rdx, r15; Src
0x1800d3139  call    memcpy_0
0x1800d313e  mov     rcx, [rbp+4Fh+Src]; Block
0x1800d3142  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d3147  xor     edi, edi
0x1800d3149  mov     [rbp+4Fh+Src], rdi
0x1800d314d  mov     [rbp+4Fh+var_78], edi
0x1800d3150  mov     rax, [rbp+4Fh+var_70]
0x1800d3154  test    rax, rax
0x1800d3157  jz      loc_1800D3587
0x1800d315d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800d3161  inc     r15
0x1800d3164  cmp     [rax+r15*2], di
0x1800d3169  jnz     short loc_1800D3161
0x1800d316b  lea     rbx, [r14+80h]
0x1800d3172  mov     rcx, rbx; SRWLock
0x1800d3175  call    cs:__imp_AcquireSRWLockExclusive
0x1800d317b  mov     [rbp+4Fh+var_90], rbx
0x1800d317f  mov     r8, [r14+68h]
0x1800d3183  mov     [rbp+4Fh+arg_8], r8
0x1800d3187  mov     r13, [r14+78h]
0x1800d318b  mov     edx, [r14+70h]
0x1800d318f  mov     ecx, edx
0x1800d3191  add     rcx, rcx
0x1800d3194  mov     rax, rcx
0x1800d3197  sub     rax, r13
0x1800d319a  add     rax, r8
0x1800d319d  sar     rax, 1
0x1800d31a0  mov     esi, 80070216h
0x1800d31a5  cmp     eax, r15d
0x1800d31a8  jb      loc_1800D3334
0x1800d31ae  mov     r12, [r14+78h]
0x1800d31b2  test    edi, edi
0x1800d31b4  js      loc_1800D35F7
0x1800d31ba  mov     edi, r15d
0x1800d31bd  add     rdi, rdi
0x1800d31c0  add     [r14+78h], rdi
0x1800d31c4  mov     r13, [r14+68h]
0x1800d31c8  test    rbx, rbx
0x1800d31cb  jz      short loc_1800D31D6
0x1800d31cd  mov     rcx, rbx; SRWLock
0x1800d31d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d31d6  mov     r15, [rbp+4Fh+var_70]
0x1800d31da  mov     rcx, rbx; SRWLock
0x1800d31dd  call    cs:__imp_AcquireSRWLockShared
0x1800d31e3  mov     r14, [r14+68h]
0x1800d31e7  test    rbx, rbx
0x1800d31ea  jz      short loc_1800D31F5
0x1800d31ec  mov     rcx, rbx; SRWLock
0x1800d31ef  call    cs:__imp_ReleaseSRWLockShared
0x1800d31f5  mov     eax, 0FFFFFFFFh
0x1800d31fa  cmp     rdi, rax
0x1800d31fd  ja      loc_1800D34DA
0x1800d3203  sub     r12, r13
0x1800d3206  sar     r12, 1
0x1800d3209  mov     eax, r12d
0x1800d320c  mov     r8d, edi; Size
0x1800d320f  lea     rcx, [r14+rax*2]; void *
0x1800d3213  mov     rdx, r15; Src
0x1800d3216  call    memcpy_0
0x1800d321b  nop
0x1800d321c  lea     rcx, [rbp+4Fh+Src]
0x1800d3220  call    ?SafeRelease@?$AutoCleanupInfo@UUiaCacheResponse@@@@SAXAEAUUiaCacheResponse@@@Z; AutoCleanupInfo<UiaCacheResponse>::SafeRelease(UiaCacheResponse &)
0x1800d3225  nop
0x1800d3226  xor     eax, eax
0x1800d3228  jmp     short loc_1800D326C
0x1800d322a  mov     rcx, [rbp+57h]; this
0x1800d322e  mov     esi, 80070216h
0x1800d3233  mov     r9d, esi; char *
0x1800d3236  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d323d  mov     edx, 46h ; 'F'; void *
0x1800d3242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3247  mov     rcx, [rbp+57h]; this
0x1800d324b  mov     r9d, esi; char *
0x1800d324e  lea     r8, aOnecoreWindows_184; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d3255  mov     edx, 154h; void *
0x1800d325a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d325f  nop
0x1800d3260  lea     rcx, [rbp+4Fh+Src]
0x1800d3264  call    ?SafeRelease@?$AutoCleanupInfo@UUiaCacheResponse@@@@SAXAEAUUiaCacheResponse@@@Z; AutoCleanupInfo<UiaCacheResponse>::SafeRelease(UiaCacheResponse &)
0x1800d3269  nop
0x1800d326a  mov     eax, esi
0x1800d326c  mov     rbx, [rsp+100h+arg_10]
0x1800d3274  add     rsp, 0D0h
0x1800d327b  pop     r15
0x1800d327d  pop     r14
0x1800d327f  pop     r13
0x1800d3281  pop     r12
0x1800d3283  pop     rdi
0x1800d3284  pop     rsi
0x1800d3285  pop     rbp
0x1800d3286  retn
0x1800d3287  test    r8d, r8d
0x1800d328a  jnz     loc_1800D3544
0x1800d3290  lea     eax, [r8+20h]
0x1800d3294  lea     r15d, [rax+r12]
0x1800d3298  cmp     r15d, eax
0x1800d329b  jb      loc_1800D3370
0x1800d32a1  mov     ecx, r15d
0x1800d32a4  mov     eax, 18h
0x1800d32a9  mul     rcx
0x1800d32ac  cmovb   rax, r9
0x1800d32b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d32b7  mov     rcx, rax; unsigned __int64
0x1800d32ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d32bf  mov     rdi, rax
0x1800d32c2  test    rax, rax
0x1800d32c5  jz      loc_1800D358F
0x1800d32cb  sub     rsi, r13
0x1800d32ce  sar     rsi, 3
0x1800d32d2  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800d32dc  imul    rax, rsi
0x1800d32e0  mov     eax, eax
0x1800d32e2  lea     rcx, [rax+rax*2]
0x1800d32e6  lea     rsi, ds:0[rcx*8]
0x1800d32ee  mov     eax, 0FFFFFFFFh
0x1800d32f3  cmp     rsi, rax
0x1800d32f6  ja      loc_1800D33D6
0x1800d32fc  mov     r8d, esi; Size
0x1800d32ff  mov     rdx, [r14+30h]; Src
0x1800d3303  mov     rcx, rdi; void *
0x1800d3306  call    memcpy_0
0x1800d330b  mov     rcx, [r14+30h]; Block
0x1800d330f  test    rcx, rcx
0x1800d3312  jnz     loc_1800D3573
0x1800d3318  mov     [r14+30h], rdi
0x1800d331c  mov     [r14+38h], r15d
0x1800d3320  lea     rax, [rdi+rsi]
0x1800d3324  mov     [r14+40h], rax
0x1800d3328  xor     ecx, ecx; Block
0x1800d332a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d332f  jmp     loc_1800D30BD
0x1800d3334  mov     r12, rdi
0x1800d3337  test    edx, edx
0x1800d3339  jnz     loc_1800D355B
0x1800d333f  lea     ecx, [rdx+20h]
0x1800d3342  lea     eax, [rcx+r15]
0x1800d3346  mov     dword ptr [rbp+4Fh+arg_0], eax
0x1800d3349  cmp     eax, ecx
0x1800d334b  jnb     loc_1800D3418
0x1800d3351  mov     edx, 6Bh ; 'k'; void *
0x1800d3356  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800d335d  mov     r9d, esi; char *
0x1800d3360  mov     rcx, [rbp+57h]; this
0x1800d3364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3369  mov     edi, esi
0x1800d336b  jmp     loc_1800D31B2
0x1800d3370  mov     edx, 6Bh ; 'k'; void *
0x1800d3375  mov     esi, 80070216h
0x1800d337a  mov     r9d, esi; char *
0x1800d337d  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800d3384  mov     rcx, [rbp+57h]; this
0x1800d3388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d338d  mov     rcx, [rbp+57h]; this
0x1800d3391  mov     r9d, esi; char *
0x1800d3394  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800d339b  mov     edx, 0F4h; void *
0x1800d33a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d33a5  lea     rcx, [rbp+4Fh+arg_0]
0x1800d33a9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d33ae  mov     rcx, [rbp+57h]; this
0x1800d33b2  mov     r9d, esi; char *
0x1800d33b5  lea     r8, aOnecoreWindows_184; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d33bc  mov     edx, 153h; void *
0x1800d33c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d33c6  nop
0x1800d33c7  lea     rcx, [rbp+4Fh+Src]
0x1800d33cb  call    ?SafeRelease@?$AutoCleanupInfo@UUiaCacheResponse@@@@SAXAEAUUiaCacheResponse@@@Z; AutoCleanupInfo<UiaCacheResponse>::SafeRelease(UiaCacheResponse &)
0x1800d33d0  nop
0x1800d33d1  jmp     loc_1800D326A
0x1800d33d6  mov     rcx, [rbp+57h]; this
0x1800d33da  mov     esi, 80070216h
0x1800d33df  mov     r9d, esi; char *
0x1800d33e2  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d33e9  mov     edx, 46h ; 'F'; void *
0x1800d33ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d33f3  mov     rcx, [rbp+57h]; this
0x1800d33f7  mov     r9d, esi; char *
0x1800d33fa  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800d3401  mov     edx, 70h ; 'p'; void *
0x1800d3406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d340b  mov     rcx, rdi; Block
0x1800d340e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d3413  jmp     loc_1800D338D
0x1800d3418  mov     ecx, eax
0x1800d341a  mov     eax, 2
0x1800d341f  mul     rcx
0x1800d3422  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d3429  cmovb   rax, rcx
0x1800d342d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d3434  mov     rcx, rax; unsigned __int64
0x1800d3437  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d343c  mov     rdi, rax
0x1800d343f  test    rax, rax
0x1800d3442  jz      loc_1800D35BA
0x1800d3448  sub     r13, [rbp+4Fh+arg_8]
  ... truncated ...
```
