# MediaFramePropertySetImpl::InsertUInt64<39>(ushort const (&)[39],unsigned __int64)

- ea: `0x18000d2f0`
- end: `0x18000dae6`
- name: `??$InsertUInt64@$0CH@@MediaFramePropertySetImpl@@AEAAXAEAY0CH@$$CBG_K@Z`
- size: `2038`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x1800019c0`
- `0x18000a930`
- `0x18000ca48`
- `0x18000ca64`
- `0x18000d2f0`
- `0x1800174dc`
- `0x180019420`
- `0x180022528`
- `0x180026920`
- `0x180026e0c`
- `0x180027490`
- `0x18002749c`
- `0x180027a20`
- `0x180032a9c`
- `0x18003a818`
- `0x18003d210`
- `0x180052010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d7ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d7ef`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d91d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d91d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d891`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d891`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d44a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d610`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000d392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000d392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d364`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d364`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d522`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HRESULT __fastcall MediaFramePropertySetImpl::InsertUInt64<39>(__int64 a1, const WCHAR *a2, __int64 a3)
{
  int v5; // eax
  __int64 v6; // rsi
  void *v7; // rbx
  HRESULT v8; // eax
  HSTRING v9; // rdi
  HRESULT v10; // edi
  void *v11; // r15
  char v12; // r13
  void *v13; // rcx
  void *v14; // r14
  char v15; // r12
  void *v16; // rdx
  char v17; // al
  RTL_SRWLOCK *v18; // rbx
  RTL_SRWLOCK *v19; // r13
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // rcx
  unsigned int v22; // edi
  unsigned __int64 i; // rdx
  __int64 v24; // r15
  __int64 j; // r15
  int v26; // edx
  __int64 v27; // rcx
  char v28; // di
  PCWSTR v29; // rax
  unsigned __int64 v30; // rdx
  int v31; // ebx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r15
  __int64 k; // r15
  __int64 v36; // r15
  bool v37; // cf
  HRESULT result; // eax
  void *v39; // rcx
  __int64 v40; // r8
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdi
  unsigned __int64 v43; // rax
  void *v44; // rax
  unsigned __int64 v45; // rax
  _QWORD *v46; // rax
  int v47; // r8d
  _QWORD *v48; // rcx
  unsigned int v49; // eax
  _DWORD *v50; // rax
  Windows::Internal::Details::Git *v51; // rcx
  void *v52; // r14
  _DWORD *v53; // rax
  _DWORD *v54; // rdi
  char v55; // [rsp+30h] [rbp-69h] BYREF
  char v56; // [rsp+31h] [rbp-68h]
  unsigned __int8 v57; // [rsp+32h] [rbp-67h] BYREF
  char v58; // [rsp+33h] [rbp-66h]
  void *v59; // [rsp+38h] [rbp-61h] BYREF
  UINT32 length; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v61; // [rsp+44h] [rbp-55h]
  HSTRING newString; // [rsp+48h] [rbp-51h] BYREF
  void *v63; // [rsp+50h] [rbp-49h]
  void *v64; // [rsp+58h] [rbp-41h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v66[5]; // [rsp+68h] [rbp-31h]
  __int16 v67; // [rsp+6Dh] [rbp-2Ch]
  char v68; // [rsp+6Fh] [rbp-2Ah]
  __int128 v69; // [rsp+70h] [rbp-29h]
  unsigned int v70; // [rsp+80h] [rbp-19h]
  HSTRING v71; // [rsp+88h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF

  v64 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, void **))(**(_QWORD **)(a1 + 112) + 104LL))(
         *(_QWORD *)(a1 + 112),
         a3,
         &v64);
  if ( v5 < 0 )
  {
LABEL_88:
    pExceptionObject = &_com_error::`vftable';
    *(_DWORD *)v66 = v5;
    v69 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v6 = *(_QWORD *)(a1 + 104);
  v7 = v64;
  string = 0;
  v8 = WindowsCreateStringReference(a2, 0x26u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    goto LABEL_88;
  }
  v9 = string;
  v71 = string;
  if ( !*(_BYTE *)(v6 + 184) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  v10 = WindowsDuplicateString(v9, &newString);
  if ( v10 < 0 )
    goto LABEL_60;
  v58 = 0;
  v11 = 0;
  v12 = 0;
  if ( !v7 )
    goto LABEL_10;
  v59 = 0;
  if ( (**(int (__fastcall ***)(void *, GUID *, void **))v7)(v7, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, &v59) >= 0 )
  {
    v11 = v7;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
    v13 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    }
LABEL_10:
    v10 = 0;
    goto LABEL_11;
  }
  v50 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v52 = v50;
  if ( v50 )
  {
    *v50 = 1;
    v50[1] = 0;
    v10 = Windows::Internal::Details::Git::Acquire(v51);
    if ( v10 >= 0 )
      v10 = (*(__int64 (__fastcall **)(__int64, void *, GUID *, __int64))(*(_QWORD *)qword_180072C08 + 24LL))(
              qword_180072C08,
              v7,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              (__int64)v52 + 4);
    if ( v10 < 0 )
    {
      XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v52);
    }
    else
    {
      v11 = v52;
      v12 = 1;
    }
  }
  else
  {
    v10 = -2147024882;
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v59);
LABEL_11:
  v14 = 0;
  if ( v10 >= 0 )
    v14 = v11;
  v15 = 0;
  if ( v10 >= 0 )
    v15 = v12;
  v16 = 0;
  v59 = 0;
  v17 = 0;
  v56 = 0;
  if ( v10 < 0 )
    goto LABEL_52;
  v18 = (RTL_SRWLOCK *)(v6 + 160);
  v19 = (RTL_SRWLOCK *)(v6 + 168);
  if ( *(_DWORD *)(v6 + 160) == 1 )
  {
    if ( !LODWORD(v19->Ptr) )
      LODWORD(v19->Ptr) = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v6 + 168));
  }
  XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v57, *(unsigned __int8 *)(v6 + 186), v6 + 188);
  if ( **(int **)(v6 + 176) > 1 )
  {
    v53 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    v54 = v53;
    if ( v53 )
    {
      *v53 = 1;
      XWinRT::SecureVersionTag::Tag::Release(*(XWinRT::SecureVersionTag::Tag **)(v6 + 176));
      *(_QWORD *)(v6 + 176) = v54;
    }
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(newString, &length);
  v21 = 2166136261LL;
  v61 = -2128831035;
  v22 = -2128831035;
  for ( i = 0; i < 2 * (unsigned __int64)length; ++i )
  {
    v21 = v22 ^ *((unsigned __int8 *)StringRawBuffer + i);
    v22 = 16777619 * v21;
  }
  v24 = *(_QWORD *)(v6 + 80);
  if ( v24 )
  {
    for ( j = *(_QWORD *)(v24 + 8LL * (v22 % *(_DWORD *)(v6 + 96))); j; j = *(_QWORD *)(j + 24) )
    {
      if ( *(_DWORD *)(j + 32) == v22 )
      {
        v55 = 0;
        v26 = XWinRT::StringEquals::operator()(v21, *(_QWORD *)j, newString, &v55);
        if ( v26 < 0 )
        {
          j = 0;
          goto LABEL_26;
        }
        if ( v55 )
          goto LABEL_25;
      }
    }
  }
  j = 0;
LABEL_25:
  v26 = 0;
LABEL_26:
  v10 = v26;
  if ( v26 >= 0 )
    v10 = 0;
  v27 = 0;
  if ( v26 >= 0 )
    v27 = j;
  if ( v10 < 0 )
  {
LABEL_65:
    v16 = 0;
    goto LABEL_48;
  }
  if ( v27 )
  {
    v16 = *(void **)(v27 + 8);
    v59 = v16;
    v56 = *(_BYTE *)(v27 + 16);
    *(_QWORD *)(v27 + 8) = v14;
    *(_BYTE *)(v27 + 16) = v15;
    *(_DWORD *)(v27 + 17) = *(_DWORD *)&v66[1];
    *(_WORD *)(v27 + 21) = v67;
    *(_BYTE *)(v27 + 23) = v68;
    v14 = 0;
    v15 = 0;
    v58 = 1;
    goto LABEL_48;
  }
  if ( *(_QWORD *)(v6 + 88) == 0x7FFFFFFF )
  {
    v10 = -2147024882;
    goto LABEL_65;
  }
  v28 = v15;
  v55 = v15;
  v63 = v14;
  length = 0;
  v29 = WindowsGetStringRawBuffer(newString, &length);
  v30 = 0;
  if ( 2LL * length )
  {
    v31 = -2128831035;
    do
      v31 = 16777619 * (v31 ^ *((unsigned __int8 *)v29 + v30++));
    while ( v30 < 2 * (unsigned __int64)length );
    v61 = v31;
    v18 = (RTL_SRWLOCK *)(v6 + 160);
  }
  v32 = v61;
  v33 = v61 % *(_DWORD *)(v6 + 96);
  v70 = v33;
  v34 = *(_QWORD *)(v6 + 80);
  if ( !v34 )
  {
LABEL_41:
    if ( !*(_QWORD *)(v6 + 80) )
    {
      v42 = *(unsigned int *)(v6 + 96);
      v43 = 8 * v42;
      if ( !is_mul_ok(v42, 8u) )
        v43 = -1;
      v44 = operator new[](v43, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)(v6 + 80) = v44;
      if ( !v44 )
      {
        v10 = -2147024882;
        goto LABEL_77;
      }
      if ( (unsigned int)v42 > 0x1FFFFFFF )
      {
        v10 = -2147418113;
        goto LABEL_77;
      }
      memset_0(v44, 0, 8 * v42);
      *(_DWORD *)(v6 + 96) = v42;
      XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(v6 + 72);
      v28 = v55;
    }
    if ( *(_QWORD *)(v6 + 144) )
      goto LABEL_43;
    pExceptionObject = 0;
    v45 = 40LL * *(unsigned int *)(v6 + 132);
    if ( is_mul_ok(*(unsigned int *)(v6 + 132), 0x28u) && v45 + 8 >= v45 )
    {
      v46 = malloc(v45 + 8);
      if ( v46 )
      {
        v63 = v14;
        v55 = v28;
        *v46 = *(_QWORD *)(v6 + 136);
        *(_QWORD *)(v6 + 136) = v46;
        v47 = *(_DWORD *)(v6 + 132) - 1;
        v48 = &v46[4 * v47 + 1 + (unsigned int)v47];
        if ( v47 < 0 )
        {
          v63 = v14;
          v55 = v28;
        }
        else
        {
          do
          {
            v48[3] = *(_QWORD *)(v6 + 144);
            *(_QWORD *)(v6 + 144) = v48;
            v48 -= 5;
            --v47;
          }
          while ( v47 >= 0 );
        }
LABEL_43:
        v36 = *(_QWORD *)(v6 + 144);
        if ( v36 )
        {
          *(_QWORD *)(v6 + 144) = *(_QWORD *)(v36 + 24);
          *(_QWORD *)v36 = newString;
          *(_QWORD *)(v36 + 8) = 0;
          *(_BYTE *)(v36 + 16) = 0;
          *(_DWORD *)(v36 + 32) = v61;
          ++*(_QWORD *)(v6 + 88);
          v40 = v70;
          *(_QWORD *)(v36 + 24) = *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL * v70);
          *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8 * v40) = v36;
          v41 = *(_QWORD *)(v6 + 88);
          if ( v41 <= *(_QWORD *)(v6 + 112)
            || *(_DWORD *)(v6 + 128)
            || (v49 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(
                        v6 + 72,
                        v41,
                        v40),
                v10 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Rehash(
                        v6 + 72,
                        v49),
                v10 >= 0) )
          {
            *(_QWORD *)(v36 + 8) = v63;
            *(_BYTE *)(v36 + 16) = v55;
            *(_DWORD *)(v36 + 17) = *(_DWORD *)&v66[1];
            *(_WORD *)(v36 + 21) = v67;
            *(_BYTE *)(v36 + 23) = v68;
            goto LABEL_47;
          }
        }
        else
        {
          v10 = -2147418113;
        }
        goto LABEL_77;
      }
    }
    v10 = -2147024882;
LABEL_77:
    v19 = v18 + 1;
    v16 = v59;
    goto LABEL_48;
  }
  for ( k = *(_QWORD *)(v34 + 8 * v33); ; k = *(_QWORD *)(k + 24) )
  {
    if ( !k )
    {
      v28 = v15;
      v55 = v15;
      v63 = v14;
      goto LABEL_41;
    }
    if ( *(_DWORD *)(k + 32) == (_DWORD)v32 )
      break;
LABEL_69:
    ;
  }
  v57 = 0;
  v10 = XWinRT::StringEquals::operator()(v32, *(_QWORD *)k, newString, &v57);
  if ( v10 < 0 )
    goto LABEL_77;
  if ( !v57 )
  {
    v32 = v61;
    goto LABEL_69;
  }
  *(_QWORD *)(k + 8) = v14;
  *(_BYTE *)(k + 16) = v15;
  *(_DWORD *)(k + 17) = *(_DWORD *)&v66[1];
  *(_WORD *)(k + 21) = v67;
  *(_BYTE *)(k + 23) = v68;
LABEL_47:
  v10 = 0;
  newString = 0;
  v14 = 0;
  v15 = 0;
  v19 = v18 + 1;
  v16 = 0;
LABEL_48:
  if ( v18 )
  {
    if ( LODWORD(v18->Ptr) == 1 )
    {
      LODWORD(v19->Ptr) += 0x10000000;
    }
    else
    {
      ReleaseSRWLockExclusive(v19);
      v16 = v59;
    }
  }
  v17 = v56;
LABEL_52:
  if ( v17 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v16);
  }
  else if ( v16 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v15 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v14);
  }
  else if ( v14 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( v10 >= 0 )
  {
    v37 = v58 != 0;
    v58 = -v58;
    v10 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
            v57,
            *(unsigned __int8 *)(v6 + 185),
            v6,
            v37 ? 3 : 1,
            v71);
  }
LABEL_60:
  result = WindowsDeleteString(newString);
  if ( v10 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    *(_DWORD *)v66 = v10;
    v69 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v39 = v64;
  if ( v64 )
  {
    v64 = 0;
    return (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
  }
  return result;
}

```

## disassembly

```asm
0x18000d2f0  mov     [rsp-8+arg_18], rbx
0x18000d2f5  push    rbp
0x18000d2f6  push    rsi
0x18000d2f7  push    rdi
0x18000d2f8  push    r12
0x18000d2fa  push    r13
0x18000d2fc  push    r14
0x18000d2fe  push    r15
0x18000d300  lea     rbp, [rsp-27h]
0x18000d305  sub     rsp, 0C0h
0x18000d30c  mov     rax, cs:__security_cookie
0x18000d313  xor     rax, rsp
0x18000d316  mov     [rbp+57h+var_40], rax
0x18000d31a  mov     r9, r8
0x18000d31d  mov     rdi, rdx
0x18000d320  mov     rsi, rcx
0x18000d323  xor     r14d, r14d
0x18000d326  mov     [rbp+57h+var_98], r14
0x18000d32a  mov     rcx, [rcx+70h]
0x18000d32e  mov     rax, [rcx]
0x18000d331  lea     r8, [rbp+57h+var_98]
0x18000d335  mov     rdx, r9
0x18000d338  mov     rax, [rax+68h]
0x18000d33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d341  test    eax, eax
0x18000d343  js      loc_18000D898
0x18000d349  mov     rsi, [rsi+68h]
0x18000d34d  mov     rbx, [rbp+57h+var_98]
0x18000d351  mov     [rbp+57h+string], r14
0x18000d355  lea     r9, [rbp+57h+string]; string
0x18000d359  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000d35d  lea     edx, [r14+26h]; length
0x18000d361  mov     rcx, rdi; sourceString
0x18000d364  call    cs:__imp_WindowsCreateStringReference
0x18000d36a  test    eax, eax
0x18000d36c  js      loc_18000D885
0x18000d372  mov     rdi, [rbp+57h+string]
0x18000d376  mov     [rbp+57h+var_68], rdi
0x18000d37a  cmp     [rsi+0B8h], r14b
0x18000d381  jz      loc_18000D916
0x18000d387  mov     [rbp+57h+newString], r14
0x18000d38b  lea     rdx, [rbp+57h+newString]; newString
0x18000d38f  mov     rcx, rdi; string
0x18000d392  call    cs:__imp_WindowsDuplicateString
0x18000d398  mov     edi, eax
0x18000d39a  test    eax, eax
0x18000d39c  js      loc_18000D687
0x18000d3a2  xor     al, al
0x18000d3a4  mov     [rbp+57h+var_BD], al
0x18000d3a7  xor     r15d, r15d
0x18000d3aa  xor     r13b, r13b
0x18000d3ad  test    rbx, rbx
0x18000d3b0  jz      short loc_18000D408
0x18000d3b2  mov     [rbp+57h+var_B8], r15
0x18000d3b6  mov     rax, [rbx]
0x18000d3b9  lea     r8, [rbp+57h+var_B8]
0x18000d3bd  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x18000d3c4  mov     rcx, rbx
0x18000d3c7  mov     rax, [rax]
0x18000d3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3cf  test    eax, eax
0x18000d3d1  js      loc_18000D928
0x18000d3d7  mov     r15, rbx
0x18000d3da  mov     rax, [rbx]
0x18000d3dd  mov     rcx, rbx
0x18000d3e0  mov     rax, [rax+8]
0x18000d3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3e9  nop
0x18000d3ea  mov     rcx, [rbp+57h+var_B8]
0x18000d3ee  test    rcx, rcx
0x18000d3f1  jz      short loc_18000D408
0x18000d3f3  mov     [rbp+57h+var_B8], 0
0x18000d3fb  mov     rax, [rcx]
0x18000d3fe  mov     rax, [rax+10h]
0x18000d402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d407  nop
0x18000d408  xor     edi, edi
0x18000d40a  xor     r14d, r14d
0x18000d40d  test    edi, edi
0x18000d40f  cmovns  r14, r15
0x18000d413  xor     r12d, r12d
0x18000d416  movzx   eax, r13b
0x18000d41a  test    edi, edi
0x18000d41c  cmovns  r12d, eax
0x18000d420  xor     edx, edx
0x18000d422  mov     [rbp+57h+var_B8], rdx
0x18000d426  xor     al, al
0x18000d428  mov     [rbp+57h+var_BF], al
0x18000d42b  test    edi, edi
0x18000d42d  js      loc_18000D61D
0x18000d433  lea     rbx, [rsi+0A0h]
0x18000d43a  lea     r13, [rbx+8]
0x18000d43e  cmp     dword ptr [rbx], 1
0x18000d441  jz      loc_18000D9A5
0x18000d447  mov     rcx, r13; SRWLock
0x18000d44a  call    cs:__imp_AcquireSRWLockExclusive
0x18000d450  lea     r8, [rsi+0BCh]
0x18000d457  movzx   edx, byte ptr [rsi+0BAh]
0x18000d45e  lea     rcx, [rbp+57h+var_BE]
0x18000d462  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18000d467  mov     rax, [rsi+0B0h]
0x18000d46e  mov     ecx, [rax]
0x18000d470  cmp     ecx, 1
0x18000d473  jg      loc_18000D9BC
0x18000d479  mov     [rbp+57h+length], 0
0x18000d480  lea     rdx, [rbp+57h+length]; length
0x18000d484  mov     rcx, [rbp+57h+newString]; string
0x18000d488  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d48e  mov     ecx, 811C9DC5h
0x18000d493  mov     [rbp+57h+var_AC], ecx
0x18000d496  mov     edi, ecx
0x18000d498  mov     r8d, [rbp+57h+length]
0x18000d49c  add     r8, r8
0x18000d49f  mov     edx, 0
0x18000d4a4  jz      short loc_18000D4BA
0x18000d4a6  movzx   ecx, byte ptr [rdx+rax]
0x18000d4aa  xor     ecx, edi
0x18000d4ac  imul    edi, ecx, 1000193h
0x18000d4b2  inc     rdx
0x18000d4b5  cmp     rdx, r8
0x18000d4b8  jb      short loc_18000D4A6
0x18000d4ba  mov     r15, [rsi+50h]
0x18000d4be  test    r15, r15
0x18000d4c1  jz      short loc_18000D4D7
0x18000d4c3  xor     edx, edx
0x18000d4c5  mov     eax, edi
0x18000d4c7  div     dword ptr [rsi+60h]
0x18000d4ca  mov     r15, [r15+rdx*8]
0x18000d4ce  test    r15, r15
0x18000d4d1  jnz     loc_18000D6EB
0x18000d4d7  xor     r15d, r15d
0x18000d4da  xor     edx, edx
0x18000d4dc  mov     edi, edx
0x18000d4de  xor     eax, eax
0x18000d4e0  test    edx, edx
0x18000d4e2  cmovns  edi, eax
0x18000d4e5  xor     ecx, ecx
0x18000d4e7  test    edx, edx
0x18000d4e9  cmovns  rcx, r15
0x18000d4ed  test    edi, edi
0x18000d4ef  js      loc_18000D6E3
0x18000d4f5  test    rcx, rcx
0x18000d4f8  jnz     loc_18000DA28
0x18000d4fe  cmp     qword ptr [rsi+58h], 7FFFFFFFh
0x18000d506  jz      loc_18000D6DE
0x18000d50c  mov     dil, r12b
0x18000d50f  mov     [rbp+57h+var_C0], r12b
0x18000d513  mov     [rbp+57h+var_A0], r14
0x18000d517  mov     [rbp+57h+length], eax
0x18000d51a  lea     rdx, [rbp+57h+length]; length
0x18000d51e  mov     rcx, [rbp+57h+newString]; string
0x18000d522  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d528  mov     r8d, [rbp+57h+length]
0x18000d52c  add     r8, r8
0x18000d52f  mov     edx, 0
0x18000d534  jz      short loc_18000D559
0x18000d536  mov     ebx, 811C9DC5h
0x18000d53b  movzx   ecx, byte ptr [rdx+rax]
0x18000d53f  xor     ecx, ebx
0x18000d541  imul    ebx, ecx, 1000193h
0x18000d547  inc     rdx
0x18000d54a  cmp     rdx, r8
0x18000d54d  jb      short loc_18000D53B
0x18000d54f  mov     [rbp+57h+var_AC], ebx
0x18000d552  lea     rbx, [rsi+0A0h]
0x18000d559  xor     edx, edx
0x18000d55b  mov     ecx, [rbp+57h+var_AC]
0x18000d55e  mov     eax, ecx
0x18000d560  div     dword ptr [rsi+60h]
0x18000d563  mov     [rbp+57h+var_70], edx
0x18000d566  mov     r15, [rsi+50h]
0x18000d56a  test    r15, r15
0x18000d56d  jz      short loc_18000D587
0x18000d56f  mov     r15, [r15+rdx*8]
0x18000d573  test    r15, r15
0x18000d576  jnz     loc_18000D6FE
0x18000d57c  mov     dil, r12b
0x18000d57f  mov     [rbp+57h+var_C0], r12b
0x18000d583  mov     [rbp+57h+var_A0], r14
0x18000d587  mov     r15, r14
0x18000d58a  xor     r13d, r13d
0x18000d58d  cmp     [rsi+50h], r13
0x18000d591  jz      loc_18000D769
0x18000d597  cmp     qword ptr [rsi+90h], 0
0x18000d59f  jz      loc_18000D7C1
0x18000d5a5  mov     r15, [rsi+90h]
0x18000d5ac  test    r15, r15
0x18000d5af  jnz     loc_18000D711
0x18000d5b5  mov     edi, 8000FFFFh
0x18000d5ba  test    edi, edi
0x18000d5bc  js      loc_18000D7AC
0x18000d5c2  mov     rax, [rbp+57h+var_A0]
0x18000d5c6  mov     [r13+8], rax
0x18000d5ca  mov     al, [rbp+57h+var_C0]
0x18000d5cd  mov     [r13+10h], al
0x18000d5d1  mov     eax, [rbp+57h+var_87]
0x18000d5d4  mov     [r13+11h], eax
0x18000d5d8  movzx   eax, [rbp+57h+var_83]
0x18000d5dc  mov     [r13+15h], ax
0x18000d5e1  mov     al, [rbp+57h+var_81]
0x18000d5e4  mov     [r13+17h], al
0x18000d5e8  xor     edi, edi
0x18000d5ea  mov     [rbp+57h+newString], 0
0x18000d5f2  xor     r14d, r14d
0x18000d5f5  xor     r12b, r12b
0x18000d5f8  lea     r13, [rbx+8]
0x18000d5fc  mov     edx, r14d
0x18000d5ff  test    rbx, rbx
0x18000d602  jz      short loc_18000D61A
0x18000d604  cmp     dword ptr [rbx], 1
0x18000d607  jz      loc_18000DABE
0x18000d60d  mov     rcx, r13; SRWLock
0x18000d610  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d616  mov     rdx, [rbp+57h+var_B8]
0x18000d61a  mov     al, [rbp+57h+var_BF]
0x18000d61d  test    al, al
0x18000d61f  jnz     loc_18000DACB
0x18000d625  test    rdx, rdx
0x18000d628  jz      short loc_18000D63A
0x18000d62a  mov     rax, [rdx]
0x18000d62d  mov     rcx, rdx
0x18000d630  mov     rax, [rax+10h]
0x18000d634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d639  nop
0x18000d63a  test    r12b, r12b
0x18000d63d  jnz     loc_18000DAD8
0x18000d643  test    r14, r14
0x18000d646  jz      short loc_18000D658
0x18000d648  mov     rax, [r14]
0x18000d64b  mov     rcx, r14
0x18000d64e  mov     rax, [rax+10h]
0x18000d652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d657  nop
0x18000d658  test    edi, edi
0x18000d65a  js      short loc_18000D687
0x18000d65c  neg     [rbp+57h+var_BD]
0x18000d65f  sbb     r9d, r9d
0x18000d662  and     r9d, 2
0x18000d666  inc     r9d
0x18000d669  mov     rax, [rbp+57h+var_68]
0x18000d66d  mov     [rsp+0F0h+var_D0], rax
0x18000d672  mov     r8, rsi
0x18000d675  movzx   edx, byte ptr [rsi+0B9h]
0x18000d67c  movzx   ecx, [rbp+57h+var_BE]
0x18000d680  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18000d685  mov     edi, eax
0x18000d687  mov     rcx, [rbp+57h+newString]; string
0x18000d68b  call    cs:__imp_WindowsDeleteString
0x18000d691  test    edi, edi
0x18000d693  js      loc_18000D8BF
0x18000d699  mov     rcx, [rbp+57h+var_98]
0x18000d69d  test    rcx, rcx
0x18000d6a0  jz      short loc_18000D6B7
0x18000d6a2  mov     [rbp+57h+var_98], 0
0x18000d6aa  mov     rax, [rcx]
0x18000d6ad  mov     rax, [rax+10h]
0x18000d6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b6  nop
0x18000d6b7  mov     rcx, [rbp+57h+var_40]
0x18000d6bb  xor     rcx, rsp; StackCookie
0x18000d6be  call    __security_check_cookie
0x18000d6c3  mov     rbx, [rsp+0F0h+arg_18]
0x18000d6cb  add     rsp, 0C0h
0x18000d6d2  pop     r15
0x18000d6d4  pop     r14
0x18000d6d6  pop     r13
0x18000d6d8  pop     r12
0x18000d6da  pop     rdi
0x18000d6db  pop     rsi
0x18000d6dc  pop     rbp
0x18000d6dd  retn
0x18000d6de  mov     edi, 8007000Eh
0x18000d6e3  mov     rdx, rax
0x18000d6e6  jmp     loc_18000D5FF
0x18000d6eb  cmp     [r15+20h], edi
0x18000d6ef  jz      loc_18000D9F7
0x18000d6f5  mov     r15, [r15+18h]
0x18000d6f9  jmp     loc_18000D4CE
0x18000d6fe  cmp     [r15+20h], ecx
0x18000d702  jz      loc_18000DA61
0x18000d708  mov     r15, [r15+18h]
0x18000d70c  jmp     loc_18000D573
0x18000d711  mov     rax, [r15+18h]
0x18000d715  mov     [rsi+90h], rax
0x18000d71c  mov     rax, [rbp+57h+newString]
0x18000d720  mov     [r15], rax
0x18000d723  mov     qword ptr [r15+8], 0
0x18000d72b  mov     byte ptr [r15+10h], 0
0x18000d730  mov     eax, [rbp+57h+var_AC]
0x18000d733  mov     [r15+20h], eax
0x18000d737  inc     qword ptr [rsi+58h]
0x18000d73b  mov     r8d, [rbp+57h+var_70]
0x18000d73f  mov     rax, [rsi+50h]
0x18000d743  mov     rdx, [rax+r8*8]
0x18000d747  mov     [r15+18h], rdx
0x18000d74b  mov     rax, [rsi+50h]
0x18000d74f  mov     [rax+r8*8], r15
0x18000d753  mov     rdx, [rsi+58h]
0x18000d757  cmp     rdx, [rsi+70h]
0x18000d75b  ja      loc_18000D8E6
  ... truncated ...
```
