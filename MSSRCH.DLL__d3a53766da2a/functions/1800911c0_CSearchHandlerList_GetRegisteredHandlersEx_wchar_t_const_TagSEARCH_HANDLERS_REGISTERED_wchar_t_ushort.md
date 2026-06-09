# CSearchHandlerList::GetRegisteredHandlersEx(wchar_t const *,TagSEARCH_HANDLERS_REGISTERED *,wchar_t * *,ushort *)

- ea: `0x1800911c0`
- end: `0x1800919ac`
- name: `?GetRegisteredHandlersEx@CSearchHandlerList@@UEAAJPEB_WPEAW4TagSEARCH_HANDLERS_REGISTERED@@PEAPEA_WPEAG@Z`
- size: `2028`
- prototype: `__int64 __fastcall(CSearchHandlerList *__hidden this, const wchar_t *, enum TagSEARCH_HANDLERS_REGISTERED *, wchar_t **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018e0c`
- `0x1800911c0`
- `0x1800919b4`
- `0x180091a78`
- `0x180092bc0`
- `0x180093494`
- `0x1800cf9a4`
- `0x1800e2374`
- `0x18010a2e4`
- `0x1801244c0`
- `0x180124b5c`
- `0x180124bc4`
- `0x180128f60`
- `0x1801299c7`
- `0x18013dd98`
- `0x180241010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180091864`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180091864`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180091726`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180091726`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180091322`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180091322`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800914f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180091608`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800914f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180091608`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009139c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009151b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009139c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009151b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800913a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800913a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091521`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800918c3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180091924`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800918c3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180091924`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091901`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091962`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091901`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091962`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180091416`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009158f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180091416`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009158f`

## string_xrefs

- `0x18009168a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180091878`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x18009189c`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CSearchHandlerList::GetRegisteredHandlersEx(
        CSearchHandlerList *this,
        const wchar_t *a2,
        enum TagSEARCH_HANDLERS_REGISTERED *a3,
        wchar_t **a4,
        unsigned __int16 *a5)
{
  CSearchHandlerList *v6; // r12
  int v7; // esi
  unsigned __int64 v8; // r14
  const wchar_t *last_trivial_2; // rax
  const wchar_t *v10; // r14
  unsigned __int64 v11; // rax
  __int64 v12; // r15
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  WCHAR *v16; // rcx
  RTL_SRWLOCK *v17; // rbx
  __int64 *v18; // r13
  __int64 *v19; // r14
  _DWORD *v20; // rdx
  const WCHAR *v21; // rcx
  int v22; // eax
  const WCHAR *v23; // r9
  char v24; // r10
  _QWORD *v25; // r14
  __int64 v26; // rax
  unsigned int Data1; // edx
  int v28; // ecx
  __int64 v29; // rax
  RTL_SRWLOCK *v30; // rbx
  __int64 v31; // rcx
  __int64 *v32; // r14
  __int64 *v33; // rsi
  _DWORD *v34; // r12
  const WCHAR *v35; // rcx
  int v36; // eax
  char v37; // r12
  unsigned __int16 *v38; // r13
  CSearchHandlerList *v39; // r14
  __int64 v40; // r8
  unsigned int v41; // r8d
  _QWORD *v43; // r8
  __int64 v44; // rax
  int v45; // eax
  _QWORD *v46; // r8
  __int64 v47; // r9
  int v48; // eax
  int v49; // eax
  int v50; // eax
  unsigned int v51; // [rsp+20h] [rbp-148h]
  int v52; // [rsp+20h] [rbp-148h]
  char v53; // [rsp+30h] [rbp-138h]
  char v54; // [rsp+31h] [rbp-137h]
  const WCHAR *v55; // [rsp+38h] [rbp-130h] BYREF
  unsigned int v56; // [rsp+40h] [rbp-128h]
  CSearchHandlerList *v57; // [rsp+48h] [rbp-120h]
  enum TagSEARCH_HANDLERS_REGISTERED *v58; // [rsp+50h] [rbp-118h]
  _DWORD *v59; // [rsp+58h] [rbp-110h]
  unsigned __int16 *v60; // [rsp+60h] [rbp-108h]
  enum TagSEARCH_HANDLERS_REGISTERED *v61; // [rsp+68h] [rbp-100h]
  wchar_t **v62; // [rsp+70h] [rbp-F8h]
  enum TagSEARCH_HANDLERS_REGISTERED *v63; // [rsp+78h] [rbp-F0h]
  __int128 v64; // [rsp+80h] [rbp-E8h] BYREF
  int v65; // [rsp+9Ch] [rbp-CCh]
  __int128 v66; // [rsp+A8h] [rbp-C0h] BYREF
  void **v67; // [rsp+C0h] [rbp-A8h] BYREF
  LPCWSTR lpString2; // [rsp+C8h] [rbp-A0h]
  int v69; // [rsp+D0h] [rbp-98h]
  int v70; // [rsp+D4h] [rbp-94h]
  _BYTE v71[72]; // [rsp+D8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v62 = a4;
  v58 = a3;
  v6 = this;
  v57 = this;
  v63 = a3;
  v61 = a3;
  v60 = a5;
  *a4 = 0;
  *(_DWORD *)a3 = 0;
  if ( a5 )
    *a5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 39) + 16LL))(*((_QWORD *)this + 39));
  v56 = 0;
  v7 = 0;
  v54 = 0;
  v53 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8
    || (last_trivial_2 = (const wchar_t *)_std_find_last_trivial_2(a2, &a2[v8], 46), last_trivial_2 == &a2[v8])
    || (v14 = last_trivial_2 - a2, v14 == -1) )
  {
    v10 = L".";
  }
  else
  {
    if ( v8 < v14 )
    {
      std::_Xout_of_range("invalid string_view position");
LABEL_93:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0x80070057LL,
        v51);
    }
    v10 = &a2[v14];
  }
  v67 = &CLMString::`vftable';
  lpString2 = (LPCWSTR)v71;
  v69 = 33;
  if ( !v10 )
    goto LABEL_93;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  if ( v11 > 0xFFFFFFFF )
    ((void (__noreturn *)(void))SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow)();
  v12 = (unsigned int)v11;
  v13 = (unsigned int)v11 + 1LL;
  if ( v13 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0xFFFFFFFFLL);
  if ( (unsigned int)v13 <= 0x21 )
  {
    v16 = (WCHAR *)v71;
  }
  else
  {
    v15 = 2LL * (unsigned int)v13;
    if ( v15 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0x80070216LL,
        v51);
    v16 = (WCHAR *)malloc((unsigned int)v15);
    lpString2 = v16;
    if ( !v16 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v51);
    v69 = v13;
  }
  if ( !is_mul_ok(2u, v12) )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v16);
  memcpy_0(v16, v10, (unsigned int)(2 * v12));
  v70 = v12;
  lpString2[v12] = 0;
  v67 = (void **)&TLMString<32,32,1024>::`vftable';
  CSearchHandlerList::LockAndLoadExtensionList(v6);
  v17 = (RTL_SRWLOCK *)((char *)v6 + 40);
  *(_QWORD *)&v64 = (char *)v6 + 40;
  AcquireSRWLockShared((PSRWLOCK)v6 + 5);
  *((_DWORD *)v6 + 13) = GetCurrentThreadId();
  v18 = (__int64 *)*((_QWORD *)v6 + 3);
  v19 = (__int64 *)v18[1];
  v65 = 0;
  if ( !*((_BYTE *)v19 + 25) )
  {
    v20 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
    v59 = v20;
    do
    {
      v21 = (const WCHAR *)v19[5];
      v55 = v21;
      if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA > *v20 )
      {
        Init_thread_header(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
        if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA == -1 )
        {
          `stringCmpI'::`2'::lcidSystem = GetSystemDefaultLCID();
          Init_thread_footer(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
        }
        v21 = v55;
      }
      if ( `stringCmpI'::`2'::lcidSystem == 1055 )
        v22 = CompareStringW(0x7Fu, 1u, v21, -1, lpString2, -1) - 2;
      else
        v22 = lstrcmpiW(v21, lpString2);
      if ( v22 < 0 )
        v19 += 2;
      else
        v18 = v19;
      v19 = (__int64 *)*v19;
      v20 = v59;
    }
    while ( !*((_BYTE *)v19 + 25) );
    v6 = v57;
  }
  if ( !*((_BYTE *)v18 + 25) && (int)stringCmpI(lpString2, (PCNZWCH)v18[5]) >= 0 && v18 != *((__int64 **)v6 + 3) )
  {
    v23 = (const WCHAR *)(v18 + 16);
    v55 = (const WCHAR *)(v18 + 16);
    v24 = v18[16] & 1;
    v54 = v24;
    v25 = (__int64 *)((char *)v18 + 132);
    v26 = *(__int64 *)((char *)v18 + 132) - *((_QWORD *)v6 + 11);
    if ( !v26 )
      v26 = *(__int64 *)((char *)v18 + 140) - *((_QWORD *)v6 + 12);
    Data1 = GUID_NULL.Data1;
    v28 = *(_DWORD *)GUID_NULL.Data4;
    if ( v26 )
    {
      v29 = *v25 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *v25 == *(_QWORD *)&GUID_NULL.Data1 )
        v29 = *(__int64 *)((char *)v18 + 140) - *(_QWORD *)GUID_NULL.Data4;
      if ( v29 )
        v7 = 1;
    }
    else
    {
      v7 = 2;
    }
    v43 = (__int64 *)((char *)v18 + 148);
    v59 = (_DWORD *)v18 + 37;
    v44 = *(__int64 *)((char *)v18 + 148) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v44 )
      v44 = *(__int64 *)((char *)v18 + 156) - *(_QWORD *)GUID_NULL.Data4;
    if ( v44 )
    {
      LOBYTE(Data1) = 1;
      v53 = 1;
      v45 = *(_DWORD *)v61;
      v28 = (int)v58;
      if ( v24 )
      {
        *(_DWORD *)v58 = v45 | 8;
        goto LABEL_80;
      }
      *(_DWORD *)v58 = v45 | 2;
    }
    else
    {
      LOBYTE(Data1) = 0;
      v53 = 0;
      if ( v24 )
      {
LABEL_80:
        v46 = v18 + 21;
        if ( (unsigned __int64)v18[24] > 7 )
          v46 = (_QWORD *)*v46;
        v47 = -1;
        do
          ++v47;
        while ( *((_WORD *)v46 + v47) );
        v48 = _AllocStringWorker<CTCoAllocPolicy>(v28, Data1, (_DWORD)v46, v47, v51, (__int64)v62);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x41E,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\handlerlist.cxx",
            (const char *)(unsigned int)v48,
            v52);
        v43 = v59;
        v23 = v55;
        LOBYTE(Data1) = v53;
      }
    }
    if ( v60 )
    {
      if ( (_BYTE)Data1 )
        v25 = v43;
      *v60 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, const WCHAR *))(**((_QWORD **)v6 + 39) + 8LL))(
               *((_QWORD *)v6 + 39),
               v25,
               v23);
    }
  }
  ReleaseSRWLockShared(v17);
  v66 = 0;
  if ( !v7 )
  {
    v30 = (RTL_SRWLOCK *)((char *)v6 + 72);
    *(_QWORD *)&v64 = (char *)v6 + 72;
    AcquireSRWLockShared((PSRWLOCK)v6 + 9);
    *((_DWORD *)v6 + 21) = GetCurrentThreadId();
    v32 = (__int64 *)*((_QWORD *)v6 + 7);
    v33 = (__int64 *)v32[1];
    v65 = 0;
    if ( !*((_BYTE *)v33 + 25) )
    {
      v34 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
      do
      {
        v35 = (const WCHAR *)v33[5];
        v55 = v35;
        if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA > *v34 )
        {
          Init_thread_header(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
          if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA == -1 )
          {
            `stringCmpI'::`2'::lcidSystem = GetSystemDefaultLCID();
            Init_thread_footer(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
          }
          v35 = v55;
        }
        if ( `stringCmpI'::`2'::lcidSystem == 1055 )
          v36 = CompareStringW(0x7Fu, 1u, v35, -1, lpString2, -1) - 2;
        else
          v36 = lstrcmpiW(v35, lpString2);
        if ( v36 >= 0 )
          v32 = v33;
        else
          v33 += 2;
        v33 = (__int64 *)*v33;
      }
      while ( !*((_BYTE *)v33 + 25) );
      v6 = v57;
    }
    if ( *((_BYTE *)v32 + 25) || (int)stringCmpI(lpString2, (PCNZWCH)v32[5]) < 0 || v32 == *((__int64 **)v6 + 7) )
    {
      v37 = 1;
      v7 = ((unsigned __int8)CSearchHandlerList::StorageClassHasIFilter(v31, &v67, &v66) ^ 1) + 1;
    }
    else
    {
      v37 = 0;
      v7 = 2 - (*((_BYTE *)v32 + 128) != 0);
    }
    v38 = v60;
    if ( !v60 || v53 )
    {
      v39 = v57;
    }
    else
    {
      v39 = v57;
      if ( v7 == 1 )
      {
        LODWORD(v55) = 0;
        *v38 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, const WCHAR **))(**((_QWORD **)v57 + 39) + 8LL))(
                 *((_QWORD *)v57 + 39),
                 &v66,
                 &v55);
      }
    }
    ReleaseSRWLockShared(v30);
    if ( v37 )
    {
      v64 = v66;
      LOBYTE(v40) = v7 == 1;
      CSearchHandlerList::LockInsertInClassNameMap(v39, &v67, v40, &v64);
    }
  }
  v67 = (void **)&TLMString<32,32,1024>::`vftable';
  if ( lpString2 && lpString2 != (LPCWSTR)v71 )
  {
    free((void *)lpString2);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
  }
  v41 = v56;
  if ( v7 != 2 )
  {
    v49 = *(_DWORD *)v61;
    if ( v54 )
      v50 = v49 | 4;
    else
      v50 = v49 | 1;
    *(_DWORD *)v58 = v50;
  }
  return v41;
}

```

## disassembly

```asm
0x1800911c0  push    rbx
0x1800911c2  push    rsi
0x1800911c3  push    rdi
0x1800911c4  push    r12
0x1800911c6  push    r13
0x1800911c8  push    r14
0x1800911ca  push    r15
0x1800911cc  sub     rsp, 130h
0x1800911d3  mov     rax, cs:__security_cookie
0x1800911da  xor     rax, rsp
0x1800911dd  mov     [rsp+168h+var_48], rax
0x1800911e5  mov     [rsp+168h+var_F8], r9
0x1800911ea  mov     rax, r8
0x1800911ed  mov     [rsp+168h+var_118], rax
0x1800911f2  mov     r15, rdx
0x1800911f5  mov     r12, rcx
0x1800911f8  mov     [rsp+168h+var_120], rcx
0x1800911fd  mov     [rsp+168h+var_F0], rax
0x180091202  mov     [rsp+168h+var_100], rax
0x180091207  mov     rbx, [rsp+168h+arg_20]
0x18009120f  mov     [rsp+168h+var_108], rbx
0x180091214  xor     edi, edi
0x180091216  mov     [r9], rdi
0x180091219  mov     [r8], edi
0x18009121c  test    rbx, rbx
0x18009121f  jz      short loc_180091237
0x180091221  mov     rcx, [rcx+138h]
0x180091228  mov     rax, [rcx]
0x18009122b  mov     rax, [rax+10h]
0x18009122f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091234  mov     [rbx], ax
0x180091237  mov     [rsp+168h+var_128], edi
0x18009123b  mov     esi, edi
0x18009123d  mov     [rsp+168h+var_134], edi
0x180091241  mov     [rsp+168h+var_137], dil
0x180091246  mov     [rsp+168h+var_138], dil
0x18009124b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18009124f  mov     r14, r13
0x180091252  inc     r14
0x180091255  cmp     [r15+r14*2], di
0x18009125a  jnz     short loc_180091252
0x18009125c  test    r14, r14
0x18009125f  jz      short loc_180091289
0x180091261  lea     rax, [r14-1]
0x180091265  cmp     rax, r13
0x180091268  cmovnb  rax, r13
0x18009126c  inc     rax
0x18009126f  lea     rbx, [r15+rax*2]
0x180091273  mov     r8d, 2Eh ; '.'
0x180091279  mov     rdx, rbx
0x18009127c  mov     rcx, r15
0x18009127f  call    __std_find_last_trivial_2
0x180091284  cmp     rax, rbx
0x180091287  jnz     short loc_1800912EF
0x180091289  lea     r14, Src; "."
0x180091290  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180091297  mov     [rsp+168h+var_A8], rax
0x18009129f  lea     rax, [rsp+168h+var_90]
0x1800912a7  mov     [rsp+168h+lpString2], rax
0x1800912af  mov     [rsp+168h+var_98], 21h ; '!'
0x1800912ba  test    r14, r14
0x1800912bd  jz      loc_18009186A
0x1800912c3  mov     rax, r13
0x1800912c6  inc     rax
0x1800912c9  cmp     [r14+rax*2], di
0x1800912ce  jnz     short loc_1800912C6
0x1800912d0  mov     ecx, 0FFFFFFFFh
0x1800912d5  cmp     rax, rcx
0x1800912d8  ja      loc_180091889
0x1800912de  mov     r15d, eax
0x1800912e1  lea     rbx, [r15+1]
0x1800912e5  cmp     rbx, rcx
0x1800912e8  jbe     short loc_180091309
0x1800912ea  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800912ef  sub     rax, r15
0x1800912f2  sar     rax, 1
0x1800912f5  cmp     rax, r13
0x1800912f8  jz      short loc_180091289
0x1800912fa  cmp     r14, rax
0x1800912fd  jb      loc_18009185D
0x180091303  lea     r14, [r15+rax*2]
0x180091307  jmp     short loc_180091290
0x180091309  cmp     ebx, 21h ; '!'
0x18009130c  jbe     loc_18009169B
0x180091312  mov     eax, ebx
0x180091314  add     rax, rax
0x180091317  cmp     rax, rcx
0x18009131a  ja      loc_18009167C
0x180091320  mov     ecx, eax; Size
0x180091322  call    cs:__imp_malloc
0x180091328  mov     rcx, rax; void *
0x18009132b  mov     [rsp+168h+lpString2], rax
0x180091333  test    rax, rax
0x180091336  jz      loc_18009188E
0x18009133c  mov     [rsp+168h+var_98], ebx
0x180091343  lea     rbx, [r15+r15]
0x180091347  mov     rax, rbx
0x18009134a  shr     rax, 20h
0x18009134e  test    eax, eax
0x180091350  jnz     loc_180091844
0x180091356  mov     r8d, ebx; Size
0x180091359  mov     rdx, r14; Src
0x18009135c  call    memcpy_0
0x180091361  mov     [rsp+168h+var_94], r15d
0x180091369  mov     rax, [rsp+168h+lpString2]
0x180091371  mov     [rax+rbx], di
0x180091375  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18009137c  mov     [rsp+168h+var_A8], rax
0x180091384  mov     rcx, r12; this
0x180091387  call    ?LockAndLoadExtensionList@CSearchHandlerList@@IEAA_NXZ; CSearchHandlerList::LockAndLoadExtensionList(void)
0x18009138c  lea     rbx, [r12+28h]
0x180091391  mov     qword ptr [rsp+168h+var_E8], rbx
0x180091399  mov     rcx, rbx; SRWLock
0x18009139c  call    cs:__imp_AcquireSRWLockShared
0x1800913a2  call    cs:__imp_GetCurrentThreadId
0x1800913a8  mov     [rbx+0Ch], eax
0x1800913ab  mov     r13, [r12+18h]
0x1800913b0  mov     r14, [r13+8]
0x1800913b4  xor     eax, eax
0x1800913b6  mov     [rsp+168h+var_CC], eax
0x1800913bd  lea     r15d, [rax+1]
0x1800913c1  cmp     [r14+19h], dil
0x1800913c5  jnz     short loc_18009143A
0x1800913c7  mov     ecx, cs:_tls_index
0x1800913cd  mov     rax, gs:58h
0x1800913d6  mov     edx, 4
0x1800913db  add     rdx, [rax+rcx*8]
0x1800913df  mov     [rsp+168h+var_110], rdx
0x1800913e4  mov     r12, [rsp+168h+lpString2]
0x1800913ec  mov     rcx, [r14+28h]; lpString1
0x1800913f0  mov     [rsp+168h+var_130], rcx
0x1800913f5  mov     eax, [rdx]
0x1800913f7  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, eax
0x1800913fd  jg      loc_1800918AE
0x180091403  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x18009140d  jz      loc_1800918E5
0x180091413  mov     rdx, r12; lpString2
0x180091416  call    cs:__imp_lstrcmpiW
0x18009141c  test    eax, eax
0x18009141e  js      loc_1800914C8
0x180091424  mov     r13, r14
0x180091427  mov     r14, [r14]
0x18009142a  cmp     [r14+19h], dil
0x18009142e  mov     rdx, [rsp+168h+var_110]
0x180091433  jz      short loc_1800913E4
0x180091435  mov     r12, [rsp+168h+var_120]
0x18009143a  cmp     [r13+19h], dil
0x18009143e  jnz     loc_1800914EF
0x180091444  mov     rdx, [r13+28h]; lpString2
0x180091448  mov     rcx, [rsp+168h+lpString2]; lpString1
0x180091450  call    ?stringCmpI@@YAHPEB_W0@Z; stringCmpI(wchar_t const *,wchar_t const *)
0x180091455  test    eax, eax
0x180091457  js      loc_1800914EF
0x18009145d  cmp     r13, [r12+18h]
0x180091462  jz      loc_1800914EF
0x180091468  lea     r9, [r13+80h]
0x18009146f  mov     [rsp+168h+var_130], r9
0x180091474  mov     r10b, [r9]
0x180091477  and     r10b, r15b
0x18009147a  mov     [rsp+168h+var_137], r10b
0x18009147f  lea     r14, [r9+4]
0x180091483  mov     rax, [r14]
0x180091486  sub     rax, [r12+58h]
0x18009148b  jnz     short loc_180091496
0x18009148d  mov     rax, [r14+8]
0x180091491  sub     rax, [r12+60h]
0x180091496  mov     rdx, qword ptr cs:GUID_NULL.Data1
0x18009149d  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x1800914a4  test    rax, rax
0x1800914a7  jz      loc_18009173D
0x1800914ad  mov     rax, [r14]
0x1800914b0  sub     rax, rdx
0x1800914b3  jnz     short loc_1800914BC
0x1800914b5  mov     rax, [r14+8]
0x1800914b9  sub     rax, rcx
0x1800914bc  test    rax, rax
0x1800914bf  cmovnz  esi, r15d
0x1800914c3  jmp     loc_180091742
0x1800914c8  add     r14, 10h
0x1800914cc  jmp     loc_180091427
0x1800914d1  mov     dl, dil
0x1800914d4  mov     [rsp+168h+var_138], dl
0x1800914d8  test    r10b, r10b
0x1800914db  jnz     loc_180091788
0x1800914e1  mov     r13, [rsp+168h+var_108]
0x1800914e6  test    r13, r13
0x1800914e9  jnz     loc_18009181A
0x1800914ef  mov     rcx, rbx; SRWLock
0x1800914f2  call    cs:__imp_ReleaseSRWLockShared
0x1800914f8  xorps   xmm0, xmm0
0x1800914fb  movups  [rsp+168h+var_C0], xmm0
0x180091503  test    esi, esi
0x180091505  jnz     loc_180091617
0x18009150b  lea     rbx, [r12+48h]
0x180091510  mov     qword ptr [rsp+168h+var_E8], rbx
0x180091518  mov     rcx, rbx; SRWLock
0x18009151b  call    cs:__imp_AcquireSRWLockShared
0x180091521  call    cs:__imp_GetCurrentThreadId
0x180091527  mov     [rbx+0Ch], eax
0x18009152a  mov     r14, [r12+38h]
0x18009152f  mov     rsi, [r14+8]
0x180091533  xor     eax, eax
0x180091535  mov     [rsp+168h+var_CC], eax
0x18009153c  cmp     [rsi+19h], dil
0x180091540  jnz     short loc_1800915AF
0x180091542  mov     ecx, cs:_tls_index
0x180091548  mov     rax, gs:58h
0x180091551  mov     r12d, 4
0x180091557  add     r12, [rax+rcx*8]
0x18009155b  mov     r13, [rsp+168h+lpString2]
0x180091563  mov     rcx, [rsi+28h]; lpString1
0x180091567  mov     [rsp+168h+var_130], rcx
0x18009156c  mov     eax, [r12]
0x180091570  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, eax
0x180091576  jg      loc_18009190F
0x18009157c  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180091586  jz      loc_180091946
0x18009158c  mov     rdx, r13; lpString2
0x18009158f  call    cs:__imp_lstrcmpiW
0x180091595  test    eax, eax
0x180091597  jns     loc_180091674
0x18009159d  add     rsi, 10h
0x1800915a1  mov     rsi, [rsi]
0x1800915a4  cmp     [rsi+19h], dil
0x1800915a8  jz      short loc_18009155B
0x1800915aa  mov     r12, [rsp+168h+var_120]
0x1800915af  cmp     [r14+19h], dil
0x1800915b3  jnz     loc_1800916A8
0x1800915b9  mov     rdx, [r14+28h]; lpString2
0x1800915bd  mov     rcx, [rsp+168h+lpString2]; lpString1
0x1800915c5  call    ?stringCmpI@@YAHPEB_W0@Z; stringCmpI(wchar_t const *,wchar_t const *)
0x1800915ca  test    eax, eax
0x1800915cc  js      loc_1800916A8
0x1800915d2  cmp     r14, [r12+38h]
0x1800915d7  jz      loc_1800916A8
0x1800915dd  mov     r12b, dil
0x1800915e0  mov     al, [r14+80h]
0x1800915e7  neg     al
0x1800915e9  sbb     esi, esi
0x1800915eb  add     esi, 2
0x1800915ee  mov     [rsp+168h+var_134], esi
0x1800915f2  mov     r13, [rsp+168h+var_108]
0x1800915f7  test    r13, r13
0x1800915fa  jnz     loc_1800916CE
0x180091600  mov     r14, [rsp+168h+var_120]
0x180091605  mov     rcx, rbx; SRWLock
0x180091608  call    cs:__imp_ReleaseSRWLockShared
0x18009160e  test    r12b, r12b
0x180091611  jnz     loc_1800917DB
0x180091617  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18009161e  mov     [rsp+168h+var_A8], rax
0x180091626  mov     rcx, [rsp+168h+lpString2]; Block
0x18009162e  test    rcx, rcx
0x180091631  jnz     loc_180091715
0x180091637  mov     rcx, [rsp+168h+var_118]
0x18009163c  mov     r8d, [rsp+168h+var_128]
0x180091641  mov     dl, [rsp+168h+var_137]
0x180091645  cmp     esi, 2
0x180091648  jnz     loc_180091992
0x18009164e  mov     eax, r8d
0x180091651  mov     rcx, [rsp+168h+var_48]
0x180091659  xor     rcx, rsp; StackCookie
0x18009165c  call    __security_check_cookie
0x180091661  add     rsp, 130h
0x180091668  pop     r15
0x18009166a  pop     r14
0x18009166c  pop     r13
0x18009166e  pop     r12
0x180091670  pop     rdi
0x180091671  pop     rsi
0x180091672  pop     rbx
0x180091673  retn
0x180091674  mov     r14, rsi
0x180091677  jmp     loc_1800915A1
0x18009167c  mov     rcx, [rsp+168h]; this
0x180091684  mov     r9d, 80070216h; char *
0x18009168a  lea     r8, aOnecoreuapBase_83; "onecoreuap\\base\\appmodel\\search\\com"...
0x180091691  mov     edx, 23h ; '#'; void *
0x180091696  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009169b  lea     rcx, [rsp+168h+var_90]
0x1800916a3  jmp     loc_180091343
0x1800916a8  lea     r8, [rsp+168h+var_C0]
0x1800916b0  lea     rdx, [rsp+168h+var_A8]
0x1800916b8  call    ?StorageClassHasIFilter@CSearchHandlerList@@IEAA_NAEAV?$TLMString@$0CA@$0CA@$0EAA@@@PEAU_GUID@@@Z; CSearchHandlerList::StorageClassHasIFilter(TLMString<32,32,1024> &,_GUID *)
0x1800916bd  mov     r12b, r15b
0x1800916c0  movzx   esi, al
0x1800916c3  xor     esi, r15d
0x1800916c6  add     esi, r15d
0x1800916c9  jmp     loc_1800915EE
0x1800916ce  cmp     [rsp+168h+var_138], dil
0x1800916d3  jnz     loc_180091600
0x1800916d9  mov     r14, [rsp+168h+var_120]
0x1800916de  cmp     esi, r15d
0x1800916e1  jnz     loc_180091605
0x1800916e7  mov     dword ptr [rsp+168h+var_130], edi
0x1800916eb  mov     rcx, [r14+138h]
0x1800916f2  mov     rax, [rcx]
0x1800916f5  lea     r8, [rsp+168h+var_130]
0x1800916fa  lea     rdx, [rsp+168h+var_C0]
0x180091702  mov     rax, [rax+8]
  ... truncated ...
```
