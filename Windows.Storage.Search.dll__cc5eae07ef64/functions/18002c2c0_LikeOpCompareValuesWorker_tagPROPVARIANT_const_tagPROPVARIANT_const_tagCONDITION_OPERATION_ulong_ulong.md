# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x18002c2c0`
- end: `0x18002c960`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `1696`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002a880`
- `0x18002b760`
- `0x18002bec0`

## callees

- `0x180017114`
- `0x18002c2c0`
- `0x18002c968`
- `0x18002ca00`
- `0x18002ce88`
- `0x18002cff0`
- `0x18002d3a0`
- `0x18002d3d0`
- `0x18002e0ec`
- `0x180071df0`
- `0x180092188`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c78c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c78c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c32f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c32f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c31b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c31b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c482`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8d6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002c427`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002c427`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002c798`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002c798`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c440`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c440`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c6b4`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c70d`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c8b2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c91a`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c6b4`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c70d`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c8b2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002c91a`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002c75b`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002c75b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18002c80e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18002c80e`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18002c2f6`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18002c309`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18002c2f6`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18002c309`

## pseudocode

```c
__int64 __fastcall _LikeOpCompareValuesWorker(
        PROPVARIANT *propvarIn,
        PROPVARIANT *a2,
        enum tagCONDITION_OPERATION a3,
        LCID Locale,
        unsigned int a5)
{
  const unsigned __int16 *v8; // r15
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // r8
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax
  CWordMatch *v13; // rax
  const unsigned __int16 *v14; // r8
  CWordMatch *v15; // rbx
  __int64 v16; // rax
  unsigned int *v17; // r8
  __int64 v18; // rdx
  unsigned int *v19; // rcx
  __int64 v20; // rax
  DWORD v21; // r14d
  unsigned int v22; // r12d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v24; // rdi
  int v25; // r14d
  HRESULT v26; // r15d
  __int64 (__fastcall ***v27)(_QWORD, GUID *, LPCWSTR *); // rcx
  int v28; // edi
  unsigned __int32 v29; // edi
  void *v30; // rcx
  unsigned int v32; // r12d
  DWORD v33; // edx
  unsigned int NLSString; // edi
  CCachedSTAObject *v35; // rax
  CCachedSTAObject *v36; // rax
  CCachedSTAObject *v37; // r13
  int v38; // r13d
  WCHAR *v39; // rax
  WCHAR *v40; // rbx
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+40h] [rbp-31h] BYREF
  LPCWSTR lpStringSource; // [rsp+48h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-21h] BYREF
  LPCWSTR lpStringValue; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v45[2]; // [rsp+60h] [rbp-11h] BYREF
  int v46; // [rsp+70h] [rbp-1h]
  int v47; // [rsp+74h] [rbp+3h]
  APTTYPE pAptType; // [rsp+E0h] [rbp+6Fh] BYREF

  pAptType = APTTYPE_STA;
  v8 = PropVariantToStringWithDefault(a2, &pszFormat);
  v9 = PropVariantToStringWithDefault(propvarIn, &pszFormat);
  if ( a3 == COP_WORD_EQUAL )
  {
LABEL_2:
    ProcessHeap = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x230u);
    lpStringValue = v12;
    if ( !v12 )
      return (unsigned __int32)pAptType;
    v13 = CWordMatch::CWordMatch((CWordMatch *)v12, a3);
    v15 = v13;
    if ( !v13 )
      return (unsigned __int32)pAptType;
    *((_DWORD *)v13 + 138) = Locale;
    *((_DWORD *)v13 + 139) = a5;
    if ( Locale == 1042 && !(unsigned int)CScriptAutoDetection::HasScript(&g_scriptAutoDetection, v9, v14) )
      CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
        (CKoreanDecomposition *)g_koreanDecomposition,
        v9,
        (unsigned __int16 **)v15 + 67);
    v16 = 2147483646;
    v17 = (unsigned int *)((char *)v15 + 12);
    v18 = 260;
    do
    {
      if ( !v16 )
        break;
      if ( !*v9 )
        break;
      *(_WORD *)v17 = *v9++;
      v17 = (unsigned int *)((char *)v17 + 2);
      --v16;
      --v18;
    }
    while ( v18 );
    v19 = (unsigned int *)((char *)v17 - 2);
    if ( v18 )
      v19 = v17;
    *(_WORD *)v19 = 0;
    if ( !v18 )
    {
      v29 = pAptType;
LABEL_40:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
      {
        v30 = (void *)*((_QWORD *)v15 + 67);
        *(_QWORD *)v15 = &CWordMatch::`vftable';
        CoTaskMemFree(v30);
        CZeroInitNew::operator delete(v15);
      }
      return v29;
    }
    *((_DWORD *)v15 + 136) = 0;
    v45[0] = CWordMatch::s_FillTextBuffer;
    v20 = -1;
    v47 = 0;
    v45[1] = v8;
    do
      ++v20;
    while ( v8[v20] );
    v21 = g_tlsWBCache;
    v22 = *((_DWORD *)v15 + 138);
    v46 = v20;
    lpStringValue = 0;
    lpStringSource = 0;
    if ( g_tlsWBCache == -1 )
    {
      DelayAllocateTLS_AllocateInternal(v19, (const unsigned __int16 *)v18);
      v21 = g_tlsWBCache;
    }
    lpStringSource = 0;
    if ( v21 == -1 )
      goto LABEL_22;
    pAptType = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    if ( CoGetApartmentType(&pAptType, pAptQualifier) < 0 || pAptType != APTTYPE_MAINSTA && pAptType )
      goto LABEL_22;
    Value = (volatile signed __int32 *)TlsGetValue(v21);
    v24 = Value;
    if ( Value )
    {
      if ( !*((_DWORD *)Value + 10) )
      {
LABEL_22:
        v25 = 0;
LABEL_23:
        ppv = 0;
        if ( CoCreateInstance(
               &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
               0,
               1u,
               &GUID_b3ddac23_10ba_4407_98de_f5fef5db4629,
               &ppv) < 0 )
        {
LABEL_39:
          v29 = *((_DWORD *)v15 + 136);
          goto LABEL_40;
        }
        *(_QWORD *)pAptQualifier = 0;
        v26 = (*(__int64 (__fastcall **)(LPVOID, GUID *, APTTYPEQUALIFIER *))(*(_QWORD *)ppv + 80LL))(
                ppv,
                &GUID_7b732139_70db_4196_a7ae_5406ed4457c5,
                pAptQualifier);
        if ( v26 >= 0 )
        {
          if ( v25 )
            CachedSTAObject_SetObject(g_tlsWBCache, *(struct IUnknown **)pAptQualifier);
          v26 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPCWSTR *))pAptQualifier)(
                  *(_QWORD *)pAptQualifier,
                  &GUID_7b732139_70db_4196_a7ae_5406ed4457c5,
                  &lpStringSource);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_34:
        if ( v26 >= 0 )
        {
          ppv = 0;
          pAptType = APTTYPE_STA;
          v28 = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, __int64, __int64, GUID *, LPVOID *, APTTYPE *))(*(_QWORD *)lpStringSource + 24LL))(
                  lpStringSource,
                  v22,
                  4,
                  260,
                  &GUID_d53552c8_77e3_101a_b552_08002b33b0e6,
                  &ppv,
                  &pAptType);
          if ( v28 >= 0 )
          {
            v28 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LPCWSTR *))ppv)(
                    ppv,
                    &GUID_d53552c8_77e3_101a_b552_08002b33b0e6,
                    &lpStringValue);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpStringSource + 16LL))(lpStringSource);
          if ( v28 >= 0 )
          {
            (*(void (__fastcall **)(LPCWSTR, _QWORD *, CWordMatch *, _QWORD))(*(_QWORD *)lpStringValue + 32LL))(
              lpStringValue,
              v45,
              v15,
              0);
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpStringValue + 16LL))(lpStringValue);
          }
        }
        goto LABEL_39;
      }
      _InterlockedIncrement(Value + 2);
      v25 = 1;
      lpStringSource = 0;
      v27 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))*((_QWORD *)Value + 4);
      if ( v27 )
        v26 = (**v27)(v27, &GUID_7b732139_70db_4196_a7ae_5406ed4457c5, &lpStringSource);
      else
        v26 = 1;
    }
    else
    {
      v24 = 0;
      v35 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v35 && (v36 = CCachedSTAObject::CCachedSTAObject(v35), (v37 = v36) != 0) )
      {
        *((_DWORD *)v36 + 6) = v21;
        v26 = CoRegisterInitializeSpy((IInitializeSpy *)v36, (ULARGE_INTEGER *)v36 + 2);
        if ( v26 >= 0 )
        {
          *((_DWORD *)v37 + 10) = 1;
          if ( !CCachedSTAObject::s_hmod )
            GetModuleHandleExW(4u, (LPCWSTR)&CCachedSTAObject::s_hmod, &CCachedSTAObject::s_hmod);
          TlsSetValue(v21, v37);
          v24 = (volatile signed __int32 *)v37;
          _InterlockedIncrement((volatile signed __int32 *)v37 + 2);
          v26 = 1;
        }
        CCachedSTAObject::Release(v37);
      }
      else
      {
        v26 = -2147024882;
      }
      v25 = 0;
      if ( v26 < 0 )
        goto LABEL_23;
      v25 = 1;
    }
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      operator delete((void *)v24, (const struct std::nothrow_t *)0x30);
    if ( v26 != 1 )
      goto LABEL_34;
    goto LABEL_23;
  }
  switch ( a3 )
  {
    case COP_VALUE_STARTSWITH:
      v32 = a5;
      if ( Locale == 1042 && !(unsigned int)CScriptAutoDetection::HasScript(&g_scriptAutoDetection, v8, v10) )
      {
        lpStringSource = 0;
        v38 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                (CKoreanDecomposition *)g_koreanDecomposition,
                v8,
                (unsigned __int16 **)&lpStringSource);
        if ( v38 >= 0 )
        {
          lpStringValue = 0;
          v38 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                  (CKoreanDecomposition *)g_koreanDecomposition,
                  v9,
                  (unsigned __int16 **)&lpStringValue);
          v39 = (WCHAR *)lpStringSource;
          if ( v38 >= 0 )
          {
            v40 = (WCHAR *)lpStringValue;
            pAptType = FindNLSString(0x412u, v32 | 0x100000, lpStringSource, -1, lpStringValue, -1, 0);
            CoTaskMemFree(v40);
            pAptType = pAptType >= APTTYPE_STA;
            v39 = (WCHAR *)lpStringSource;
          }
          CoTaskMemFree(v39);
        }
        if ( !v38 )
          return (unsigned __int32)pAptType;
      }
      return FindNLSString(Locale, v32 | 0x100000, v8, -1, v9, -1, 0) >= 0;
    case COP_VALUE_ENDSWITH:
      v33 = a5 | 0x200000;
      goto LABEL_49;
    case COP_VALUE_CONTAINS:
      v33 = a5 | 0x400000;
LABEL_49:
      NLSString = ~FindNLSString(Locale, v33, v8, -1, v9, -1, 0);
      goto LABEL_50;
    case COP_VALUE_NOTCONTAINS:
      NLSString = FindNLSString(Locale, a5 | 0x400000, v8, -1, v9, -1, 0);
LABEL_50:
      v29 = NLSString >> 31;
      break;
    case COP_DOSWILDCARDS:
      v29 = PathMatchSpecExW(v8, v9, 0) == 0;
      break;
    case COP_WORD_STARTSWITH:
      goto LABEL_2;
    default:
      return (unsigned __int32)pAptType;
  }
  return v29;
}

```

## disassembly

```asm
0x18002c2c0  push    rbp
0x18002c2c2  push    rbx
0x18002c2c3  push    rsi
0x18002c2c4  push    rdi
0x18002c2c5  push    r12
0x18002c2c7  push    r13
0x18002c2c9  push    r14
0x18002c2cb  push    r15
0x18002c2cd  lea     rbp, [rsp-17h]
0x18002c2d2  sub     rsp, 88h
0x18002c2d9  mov     rax, rdx
0x18002c2dc  mov     rbx, rcx
0x18002c2df  xor     r13d, r13d
0x18002c2e2  lea     rdx, pszFormat; pszDefault
0x18002c2e9  mov     rcx, rax; propvarIn
0x18002c2ec  mov     [rbp+4Fh+pAptType], r13d
0x18002c2f0  mov     r14d, r9d
0x18002c2f3  mov     esi, r8d
0x18002c2f6  call    cs:__imp_PropVariantToStringWithDefault
0x18002c2fc  lea     rdx, pszFormat; pszDefault
0x18002c303  mov     rcx, rbx; propvarIn
0x18002c306  mov     r15, rax
0x18002c309  call    cs:__imp_PropVariantToStringWithDefault
0x18002c30f  mov     rdi, rax
0x18002c312  cmp     esi, 0Ch
0x18002c315  jnz     loc_18002C660
0x18002c31b  call    cs:__imp_GetProcessHeap; jumptable 000000018002C67B case 13
0x18002c321  mov     edx, 8; dwFlags
0x18002c326  mov     r8d, 230h; dwBytes
0x18002c32c  mov     rcx, rax; hHeap
0x18002c32f  call    cs:__imp_HeapAlloc
0x18002c335  mov     [rbp+4Fh+lpStringValue], rax
0x18002c339  test    rax, rax
0x18002c33c  jz      def_18002C67B; jumptable 000000018002C67B default case, case 12
0x18002c342  mov     edx, esi; enum tagCONDITION_OPERATION
0x18002c344  mov     rcx, rax; this
0x18002c347  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x18002c34c  mov     rbx, rax
0x18002c34f  test    rax, rax
0x18002c352  jz      def_18002C67B; jumptable 000000018002C67B default case, case 12
0x18002c358  mov     [rax+228h], r14d
0x18002c35f  mov     eax, [rbp+4Fh+arg_20]
0x18002c362  mov     [rbx+22Ch], eax
0x18002c368  cmp     r14d, 412h
0x18002c36f  jz      loc_18002C7C8
0x18002c375  mov     eax, 7FFFFFFEh
0x18002c37a  lea     r8, [rbx+0Ch]
0x18002c37e  mov     edx, 104h
0x18002c383  test    rax, rax
0x18002c386  jz      short loc_18002C3A5
0x18002c388  movzx   ecx, word ptr [rdi]
0x18002c38b  test    cx, cx
0x18002c38e  jz      short loc_18002C3A5
0x18002c390  mov     [r8], cx
0x18002c394  add     rdi, 2
0x18002c398  add     r8, 2
0x18002c39c  dec     rax
0x18002c39f  sub     rdx, 1; unsigned __int16 *
0x18002c3a3  jnz     short loc_18002C383
0x18002c3a5  test    rdx, rdx
0x18002c3a8  lea     rcx, [r8-2]
0x18002c3ac  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002c3b3  cmovnz  rcx, r8; unsigned int *
0x18002c3b7  mov     [rcx], r13w
0x18002c3bb  jz      loc_18002C822
0x18002c3c1  lea     rax, ?s_FillTextBuffer@CWordMatch@@CAJPEAUtagTEXT_SOURCE@@@Z; CWordMatch::s_FillTextBuffer(tagTEXT_SOURCE *)
0x18002c3c8  mov     [rbx+220h], r13d
0x18002c3cf  mov     [rbp+4Fh+var_60], rax
0x18002c3d3  mov     rax, rsi
0x18002c3d6  mov     [rbp+4Fh+var_4C], r13d
0x18002c3da  mov     [rbp+4Fh+var_58], r15
0x18002c3de  xchg    ax, ax
0x18002c3e0  inc     rax
0x18002c3e3  cmp     [r15+rax*2], r13w
0x18002c3e8  jnz     short loc_18002C3E0
0x18002c3ea  mov     r14d, cs:?g_tlsWBCache@@3KA; ulong g_tlsWBCache
0x18002c3f1  mov     r12d, [rbx+228h]
0x18002c3f8  mov     [rbp+4Fh+var_50], eax
0x18002c3fb  mov     [rbp+4Fh+lpStringValue], r13
0x18002c3ff  mov     [rbp+4Fh+lpStringSource], r13
0x18002c403  cmp     r14d, 0FFFFFFFFh
0x18002c407  jz      loc_18002C927
0x18002c40d  mov     [rbp+4Fh+lpStringSource], r13
0x18002c411  cmp     r14d, 0FFFFFFFFh
0x18002c415  jz      short loc_18002C45C
0x18002c417  lea     rdx, [rbp+4Fh+pAptQualifier]; pAptQualifier
0x18002c41b  mov     [rbp+4Fh+pAptType], r13d
0x18002c41f  lea     rcx, [rbp+4Fh+pAptType]; pAptType
0x18002c423  mov     [rbp+4Fh+pAptQualifier], r13d
0x18002c427  call    cs:__imp_CoGetApartmentType
0x18002c42d  test    eax, eax
0x18002c42f  js      short loc_18002C45C
0x18002c431  mov     eax, [rbp+4Fh+pAptType]
0x18002c434  cmp     eax, 3
0x18002c437  jz      short loc_18002C43D
0x18002c439  test    eax, eax
0x18002c43b  jnz     short loc_18002C45C
0x18002c43d  mov     ecx, r14d; dwTlsIndex
0x18002c440  call    cs:__imp_TlsGetValue
0x18002c446  mov     rdi, rax
0x18002c449  test    rax, rax
0x18002c44c  jz      loc_18002C71F
0x18002c452  cmp     [rax+28h], r13d
0x18002c456  jnz     loc_18002C509
0x18002c45c  mov     r14d, r13d
0x18002c45f  lea     rax, [rbp+4Fh+var_70]
0x18002c463  mov     [rbp+4Fh+var_70], r13
0x18002c467  lea     r9, _GUID_b3ddac23_10ba_4407_98de_f5fef5db4629; riid
0x18002c46e  mov     [rsp+0C0h+ppv], rax; ppv
0x18002c473  xor     edx, edx; pUnkOuter
0x18002c475  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x18002c47c  mov     r8d, 1; dwClsContext
0x18002c482  call    cs:__imp_CoCreateInstance
0x18002c488  test    eax, eax
0x18002c48a  js      loc_18002C61B
0x18002c490  mov     rcx, [rbp+4Fh+var_70]
0x18002c494  lea     r8, [rbp+4Fh+pAptQualifier]
0x18002c498  mov     qword ptr [rbp+4Fh+pAptQualifier], r13
0x18002c49c  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x18002c4a3  mov     rax, [rcx]
0x18002c4a6  mov     rax, [rax+50h]
0x18002c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4af  mov     r15d, eax
0x18002c4b2  test    eax, eax
0x18002c4b4  js      short loc_18002C4F7
0x18002c4b6  test    r14d, r14d
0x18002c4b9  jz      short loc_18002C4CA
0x18002c4bb  mov     rdx, qword ptr [rbp+4Fh+pAptQualifier]; struct IUnknown *
0x18002c4bf  mov     ecx, cs:?g_tlsWBCache@@3KA; unsigned int
0x18002c4c5  call    ?CachedSTAObject_SetObject@@YAJKPEAUIUnknown@@@Z; CachedSTAObject_SetObject(ulong,IUnknown *)
0x18002c4ca  mov     rcx, qword ptr [rbp+4Fh+pAptQualifier]
0x18002c4ce  lea     r8, [rbp+4Fh+lpStringSource]
0x18002c4d2  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x18002c4d9  mov     rax, [rcx]
0x18002c4dc  mov     rax, [rax]
0x18002c4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4e4  mov     rcx, qword ptr [rbp+4Fh+pAptQualifier]
0x18002c4e8  mov     r15d, eax
0x18002c4eb  mov     rax, [rcx]
0x18002c4ee  mov     rax, [rax+10h]
0x18002c4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4f7  mov     rcx, [rbp+4Fh+var_70]
0x18002c4fb  mov     rax, [rcx]
0x18002c4fe  mov     rax, [rax+10h]
0x18002c502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c507  jmp     short loc_18002C561
0x18002c509  lock inc dword ptr [rax+8]
0x18002c50d  mov     r14d, 1
0x18002c513  jmp     short loc_18002C51D
0x18002c515  mov     r14d, 1
0x18002c51b  jnz     short loc_18002C547
0x18002c51d  mov     [rbp+4Fh+lpStringSource], r13
0x18002c521  mov     rcx, [rdi+20h]
0x18002c525  test    rcx, rcx
0x18002c528  jz      loc_18002C938
0x18002c52e  mov     rax, [rcx]
0x18002c531  lea     r8, [rbp+4Fh+lpStringSource]
0x18002c535  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x18002c53c  mov     rax, [rax]
0x18002c53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c544  mov     r15d, eax
0x18002c547  mov     eax, esi
0x18002c549  lock xadd [rdi+8], eax
0x18002c54e  cmp     eax, 1
0x18002c551  jz      loc_18002C6D6
0x18002c557  cmp     r15d, 1
0x18002c55b  jz      loc_18002C45F
0x18002c561  test    r15d, r15d
0x18002c564  js      loc_18002C61B
0x18002c56a  mov     rcx, [rbp+4Fh+lpStringSource]
0x18002c56e  lea     rdx, [rbp+4Fh+pAptType]
0x18002c572  mov     [rsp+0C0h+pcchFound], rdx
0x18002c577  lea     r14, _GUID_d53552c8_77e3_101a_b552_08002b33b0e6
0x18002c57e  lea     rdx, [rbp+4Fh+var_70]
0x18002c582  mov     [rbp+4Fh+var_70], r13
0x18002c586  mov     qword ptr [rsp+0C0h+cchValue], rdx
0x18002c58b  mov     r9d, 104h
0x18002c591  mov     [rbp+4Fh+pAptType], r13d
0x18002c595  mov     r8d, 4
0x18002c59b  mov     rax, [rcx]
0x18002c59e  mov     edx, r12d
0x18002c5a1  mov     [rsp+0C0h+ppv], r14
0x18002c5a6  mov     rax, [rax+18h]
0x18002c5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5af  mov     edi, eax
0x18002c5b1  test    eax, eax
0x18002c5b3  js      short loc_18002C5DD
0x18002c5b5  mov     rcx, [rbp+4Fh+var_70]
0x18002c5b9  lea     r8, [rbp+4Fh+lpStringValue]
0x18002c5bd  mov     rdx, r14
0x18002c5c0  mov     rax, [rcx]
0x18002c5c3  mov     rax, [rax]
0x18002c5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5cb  mov     rcx, [rbp+4Fh+var_70]
0x18002c5cf  mov     edi, eax
0x18002c5d1  mov     rax, [rcx]
0x18002c5d4  mov     rax, [rax+10h]
0x18002c5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5dd  mov     rcx, [rbp+4Fh+lpStringSource]
0x18002c5e1  mov     rax, [rcx]
0x18002c5e4  mov     rax, [rax+10h]
0x18002c5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5ed  test    edi, edi
0x18002c5ef  js      short loc_18002C61B
0x18002c5f1  mov     rcx, [rbp+4Fh+lpStringValue]
0x18002c5f5  lea     rdx, [rbp+4Fh+var_60]
0x18002c5f9  xor     r9d, r9d
0x18002c5fc  mov     r8, rbx
0x18002c5ff  mov     rax, [rcx]
0x18002c602  mov     rax, [rax+20h]
0x18002c606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c60b  mov     rcx, [rbp+4Fh+lpStringValue]
0x18002c60f  mov     rax, [rcx]
0x18002c612  mov     rax, [rax+10h]
0x18002c616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c61b  mov     edi, [rbx+220h]
0x18002c621  lock xadd [rbx+8], esi
0x18002c626  cmp     esi, 1
0x18002c629  jnz     short loc_18002C64A
0x18002c62b  mov     rcx, [rbx+218h]; pv
0x18002c632  lea     rax, ??_7CWordMatch@@6B@; const CWordMatch::`vftable'
0x18002c639  mov     [rbx], rax
0x18002c63c  call    cs:__imp_CoTaskMemFree
0x18002c642  mov     rcx, rbx; lpMem
0x18002c645  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18002c64a  mov     eax, edi
0x18002c64c  add     rsp, 88h
0x18002c653  pop     r15
0x18002c655  pop     r14
0x18002c657  pop     r13
0x18002c659  pop     r12
0x18002c65b  pop     rdi
0x18002c65c  pop     rsi
0x18002c65d  pop     rbx
0x18002c65e  pop     rbp
0x18002c65f  retn
0x18002c660  lea     eax, [rsi-7]; switch 7 cases
0x18002c663  cmp     eax, 6
0x18002c666  ja      short def_18002C67B; jumptable 000000018002C67B default case, case 12
0x18002c668  lea     rdx, __ImageBase
0x18002c66f  cdqe
0x18002c671  mov     ecx, ds:(jpt_18002C67B - 180000000h)[rdx+rax*4]
0x18002c678  add     rcx, rdx
0x18002c67b  jmp     rcx; switch jump
0x18002c67d  mov     r12d, [rbp+4Fh+arg_20]; jumptable 000000018002C67B case 7
0x18002c681  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002c688  cmp     r14d, 412h
0x18002c68f  jz      loc_18002C82A
0x18002c695  mov     [rsp+0C0h+pcchFound], r13; pcchFound
0x18002c69a  bts     r12d, 14h
0x18002c69f  mov     edx, r12d; dwFindNLSStringFlags
0x18002c6a2  mov     [rsp+0C0h+cchValue], esi; cchValue
0x18002c6a6  mov     r9d, esi; cchSource
0x18002c6a9  mov     [rsp+0C0h+ppv], rdi; lpStringValue
0x18002c6ae  mov     r8, r15; lpStringSource
0x18002c6b1  mov     ecx, r14d; Locale
0x18002c6b4  call    cs:__imp_FindNLSString
0x18002c6ba  test    eax, eax
0x18002c6bc  mov     edi, r13d
0x18002c6bf  setns   dil
0x18002c6c3  jmp     short loc_18002C64A
0x18002c6c5  test    r13d, r13d
0x18002c6c8  jnz     loc_18002C8E1
0x18002c6ce  mov     edi, [rbp+4Fh+pAptType]; jumptable 000000018002C67B default case, case 12
0x18002c6d1  jmp     loc_18002C64A
0x18002c6d6  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18002c6db  mov     rcx, rdi; void *
0x18002c6de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c6e3  jmp     loc_18002C557
0x18002c6e8  mov     edx, [rbp+4Fh+arg_20]; jumptable 000000018002C67B case 9
0x18002c6eb  bts     edx, 16h; dwFindNLSStringFlags
0x18002c6ef  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002c6f6  mov     [rsp+0C0h+pcchFound], r13; pcchFound
0x18002c6fb  mov     [rsp+0C0h+cchValue], esi; cchValue
0x18002c6ff  mov     r9d, esi; cchSource
0x18002c702  mov     r8, r15; lpStringSource
0x18002c705  mov     [rsp+0C0h+ppv], rdi; lpStringValue
0x18002c70a  mov     ecx, r14d; Locale
0x18002c70d  call    cs:__imp_FindNLSString
0x18002c713  mov     edi, eax
0x18002c715  not     edi
0x18002c717  shr     edi, 1Fh
0x18002c71a  jmp     loc_18002C64A
0x18002c71f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c726  mov     ecx, 30h ; '0'; unsigned __int64
0x18002c72b  mov     rdi, r13
0x18002c72e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c733  test    rax, rax
0x18002c736  jz      loc_18002C7FD
0x18002c73c  mov     rcx, rax; this
0x18002c73f  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x18002c744  mov     r13, rax
0x18002c747  test    rax, rax
0x18002c74a  jz      loc_18002C7FA
0x18002c750  lea     rdx, [rax+10h]; puliCookie
0x18002c754  mov     [rax+18h], r14d
0x18002c758  mov     rcx, rax; pSpy
0x18002c75b  call    cs:__imp_CoRegisterInitializeSpy
0x18002c761  mov     r15d, eax
0x18002c764  test    eax, eax
  ... truncated ...
```
