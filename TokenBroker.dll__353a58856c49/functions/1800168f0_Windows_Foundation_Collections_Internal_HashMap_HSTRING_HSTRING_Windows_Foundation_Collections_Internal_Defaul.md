# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x1800168f0`
- end: `0x180016e1b`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `1323`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18002a790`
- `0x1800eee30`

## callees

- `0x1800159bc`
- `0x1800168f0`
- `0x180016e24`
- `0x180016e40`
- `0x180016e5c`
- `0x1800174d0`
- `0x18003e0f8`
- `0x18003e214`
- `0x18008e710`
- `0x18008ebb0`
- `0x18008f1ec`
- `0x18008f234`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001697f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001697f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001694a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001694a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800169bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800169bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016d28`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016bc5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016bc5`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        _BYTE *a4)
{
  HRESULT v7; // r15d
  HSTRING v8; // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned int v10; // r14d
  unsigned int v11; // esi
  unsigned __int64 i; // rcx
  int v13; // edx
  __int64 v14; // r8
  _DWORD *v15; // r12
  __int64 *j; // rax
  PCWSTR v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r15
  HSTRING *k; // rsi
  __int64 v25; // rcx
  __int64 v26; // r12
  _BYTE *v27; // rsi
  __int64 v28; // r9
  unsigned int v30; // esi
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rsi
  unsigned __int64 v33; // rax
  void *v34; // rax
  _QWORD *v35; // rax
  int v36; // r8d
  HSTRING *v37; // rdx
  __int64 v38; // rdx
  _DWORD *v39; // rax
  _DWORD *v40; // rsi
  HSTRING v41; // rdx
  unsigned int v42; // eax
  UINT32 v43[2]; // [rsp+30h] [rbp-28h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-18h] BYREF
  __int64 v46; // [rsp+48h] [rbp-10h]
  __int64 length; // [rsp+90h] [rbp+38h] BYREF
  HSTRING v48; // [rsp+98h] [rbp+40h]
  _BYTE *v49; // [rsp+A8h] [rbp+50h]

  v49 = a4;
  v48 = a2;
  *a4 = 0;
  if ( !*(_BYTE *)(a1 + 184) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  v7 = WindowsDuplicateString(a2, &newString);
  if ( v7 < 0 )
    goto LABEL_36;
  v7 = WindowsDuplicateString(a3, &string);
  if ( v7 < 0 )
  {
    string = 0;
    WindowsDeleteString(0);
    WindowsDeleteString(string);
    goto LABEL_36;
  }
  v8 = 0;
  if ( *(_DWORD *)(a1 + 160) == 1 )
  {
    if ( !*(_DWORD *)(a1 + 168) )
      *(_DWORD *)(a1 + 168) = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
  }
  XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&length, *(unsigned __int8 *)(a1 + 186), a1 + 188);
  if ( **(int **)(a1 + 176) > 1 )
  {
    v39 = operator new(4u, (const struct std::nothrow_t *)std::nothrow);
    v40 = v39;
    if ( v39 )
    {
      *v39 = 1;
      XWinRT::SecureVersionTag::Tag::Release(*(XWinRT::SecureVersionTag::Tag **)(a1 + 176));
      *(_QWORD *)(a1 + 176) = v40;
    }
  }
  LODWORD(length) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(newString, (UINT32 *)&length);
  v10 = -2128831035;
  v11 = -2128831035;
  for ( i = 0; i < 2 * (unsigned __int64)(unsigned int)length; v11 = 16777619 * (v11 ^ v13) )
    v13 = *((unsigned __int8 *)StringRawBuffer + i++);
  v14 = *(_QWORD *)(a1 + 80);
  v15 = (_DWORD *)(a1 + 96);
  if ( v14 )
  {
    for ( j = *(__int64 **)(v14 + 8LL * (v11 % *v15)); ; j = (__int64 *)j[2] )
    {
      *(_QWORD *)v43 = j;
      if ( !j )
        break;
      if ( *((_DWORD *)j + 6) == v11 )
      {
        v38 = *j;
        LOBYTE(length) = 0;
        v7 = XWinRT::StringEquals::operator()(i, v38, newString, &length);
        if ( v7 < 0 )
          goto LABEL_28;
        if ( (_BYTE)length )
        {
          v8 = *(HSTRING *)(*(_QWORD *)v43 + 8LL);
          WindowsDeleteString(0);
          v7 = 0;
          *(_QWORD *)(*(_QWORD *)v43 + 8LL) = string;
          v27 = v49;
          string = 0;
          *v49 = 1;
          goto LABEL_29;
        }
        j = *(__int64 **)v43;
      }
    }
  }
  if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
  {
    v7 = -2147024882;
    goto LABEL_28;
  }
  v43[0] = 0;
  v17 = WindowsGetStringRawBuffer(newString, v43);
  v19 = 0;
  if ( 2LL * v43[0] )
  {
    do
    {
      v20 = *((unsigned __int8 *)v17 + v19++);
      v18 = v10 ^ v20;
      v10 = 16777619 * v18;
    }
    while ( v19 < 2 * (unsigned __int64)v43[0] );
    v15 = (_DWORD *)(a1 + 96);
  }
  v21 = *(_QWORD *)(a1 + 80);
  v22 = v10 % *v15;
  v23 = (unsigned int)v22;
  v46 = (unsigned int)v22;
  if ( v21 )
  {
    for ( k = *(HSTRING **)(v21 + 8 * v22); k; k = (HSTRING *)k[2] )
    {
      if ( *((_DWORD *)k + 6) == v10 )
      {
        v41 = *k;
        LOBYTE(length) = 0;
        v7 = XWinRT::StringEquals::operator()(v18, v41, newString, &length);
        if ( v7 < 0 )
          goto LABEL_28;
        if ( (_BYTE)length )
          goto LABEL_25;
      }
    }
    v23 = v46;
  }
  v25 = v23;
  if ( *(_QWORD *)(a1 + 80) )
  {
    v26 = a1 + 72;
  }
  else
  {
    v32 = (unsigned int)*v15;
    v33 = 8 * v32;
    if ( !is_mul_ok(v32, 8u) )
      v33 = -1;
    v34 = operator new[](v33, (const struct std::nothrow_t *)std::nothrow);
    *(_QWORD *)(a1 + 80) = v34;
    if ( !v34 )
      goto LABEL_41;
    if ( (unsigned int)v32 > 0x1FFFFFFF )
    {
LABEL_27:
      v7 = -2147418113;
      goto LABEL_28;
    }
    memset_0(v34, 0, 8 * v32);
    *v15 = v32;
    v26 = a1 + 72;
    XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::UpdateRehashThresholds(a1 + 72);
    v25 = v23;
  }
  k = *(HSTRING **)(a1 + 144);
  if ( k )
    goto LABEL_24;
  v30 = *(_DWORD *)(a1 + 132);
  v31 = 32LL * v30;
  length = 0;
  if ( !is_mul_ok(v30, 0x20u) || v31 + 8 < v31 || (v35 = o_malloc_0(v31 + 8)) == 0 )
  {
LABEL_41:
    v7 = -2147024882;
    goto LABEL_28;
  }
  v36 = v30 - 1;
  *v35 = *(_QWORD *)(a1 + 136);
  v37 = (HSTRING *)&v35[4 * v30 - 3];
  *(_QWORD *)(a1 + 136) = v35;
  if ( (int)(v30 - 1) < 0 )
    goto LABEL_27;
  do
  {
    k = v37;
    v37[2] = *(HSTRING *)(a1 + 144);
    *(_QWORD *)(a1 + 144) = v37;
    v37 -= 4;
    --v36;
  }
  while ( v36 >= 0 );
  v25 = (unsigned int)v23;
  if ( !k )
    goto LABEL_27;
LABEL_24:
  *(_QWORD *)(a1 + 144) = k[2];
  *k = newString;
  *((_DWORD *)k + 6) = v10;
  ++*(_QWORD *)(a1 + 88);
  k[2] = *(HSTRING *)(*(_QWORD *)(a1 + 80) + 8 * v25);
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8 * v25) = k;
  if ( *(_QWORD *)(a1 + 88) <= *(_QWORD *)(a1 + 112)
    || *(_DWORD *)(a1 + 128)
    || (v42 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::PickSize(v26),
        v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(
               v26,
               v42),
        v7 >= 0) )
  {
LABEL_25:
    k[1] = string;
    v7 = 0;
    newString = 0;
    string = 0;
  }
LABEL_28:
  v27 = v49;
LABEL_29:
  if ( a1 != -160 )
  {
    if ( *(_DWORD *)(a1 + 160) == 1 )
      *(_DWORD *)(a1 + 168) += 0x10000000;
    else
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
  }
  WindowsDeleteString(v8);
  WindowsDeleteString(string);
  if ( v7 >= 0 )
  {
    v28 = 3;
    if ( !*v27 )
      v28 = 1;
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v49,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           v28,
           v48);
  }
LABEL_36:
  WindowsDeleteString(newString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800168f0  mov     [rsp-30h+arg_18], r9
0x1800168f5  mov     [rsp-30h+arg_8], rdx
0x1800168fa  push    rbp
0x1800168fb  push    rbx
0x1800168fc  push    rdi
0x1800168fd  push    r12
0x1800168ff  push    r13
0x180016901  push    r15
0x180016903  mov     rbp, rsp
0x180016906  sub     rsp, 58h
0x18001690a  mov     byte ptr [r9], 0
0x18001690e  mov     rbx, r8
0x180016911  cmp     byte ptr [rcx+0B8h], 0
0x180016918  mov     rdi, rdx
0x18001691b  mov     r13, rcx
0x18001691e  jz      loc_180016BBE
0x180016924  xor     r12d, r12d
0x180016927  lea     rdx, [rbp+newString]; newString
0x18001692b  mov     rcx, rdi; string
0x18001692e  mov     [rbp+newString], r12
0x180016932  call    cs:__imp_WindowsDuplicateString
0x180016938  mov     r15d, eax
0x18001693b  test    eax, eax
0x18001693d  js      loc_180016B91
0x180016943  lea     rdx, [rbp+string]; newString
0x180016947  mov     rcx, rbx; string
0x18001694a  call    cs:__imp_WindowsDuplicateString
0x180016950  mov     r15d, eax
0x180016953  test    eax, eax
0x180016955  js      loc_180016C04
0x18001695b  lea     rdi, [r13+0A0h]
0x180016962  mov     [rsp+58h+arg_10], rsi
0x18001696a  cmp     dword ptr [rdi], 1
0x18001696d  mov     ebx, r12d
0x180016970  mov     [rsp+58h+var_8], r14
0x180016975  jz      loc_180016DB6
0x18001697b  lea     rcx, [rdi+8]; SRWLock
0x18001697f  call    cs:__imp_AcquireSRWLockExclusive
0x180016985  movzx   edx, byte ptr [r13+0BAh]
0x18001698d  lea     r8, [r13+0BCh]
0x180016994  lea     rcx, [rbp+length]
0x180016998  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001699d  mov     rax, [r13+0B0h]
0x1800169a4  mov     ecx, [rax]
0x1800169a6  cmp     ecx, 1
0x1800169a9  jg      loc_180016D4D
0x1800169af  mov     rcx, [rbp+newString]; string
0x1800169b3  lea     rdx, [rbp+length]; length
0x1800169b7  mov     dword ptr [rbp+length], r12d
0x1800169bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800169c1  mov     r8d, dword ptr [rbp+length]
0x1800169c5  mov     r14d, 811C9DC5h
0x1800169cb  mov     esi, r14d
0x1800169ce  mov     rcx, r12
0x1800169d1  add     r8, r8
0x1800169d4  jz      short loc_1800169F4
0x1800169d6  nop     word ptr [rax+rax+00000000h]
0x1800169e0  movzx   edx, byte ptr [rax+rcx]
0x1800169e4  inc     rcx
0x1800169e7  xor     edx, esi
0x1800169e9  imul    esi, edx, 1000193h
0x1800169ef  cmp     rcx, r8
0x1800169f2  jb      short loc_1800169E0
0x1800169f4  mov     r8, [r13+50h]
0x1800169f8  lea     r12, [r13+60h]
0x1800169fc  test    r8, r8
0x1800169ff  jz      short loc_180016A1A
0x180016a01  xor     edx, edx
0x180016a03  mov     eax, esi
0x180016a05  div     dword ptr [r12]
0x180016a09  mov     rax, [r8+rdx*8]
0x180016a0d  mov     qword ptr [rbp+var_28], rax
0x180016a11  test    rax, rax
0x180016a14  jnz     loc_180016BAC
0x180016a1a  cmp     qword ptr [r13+58h], 7FFFFFFFh
0x180016a22  jz      loc_180016E04
0x180016a28  mov     rcx, [rbp+newString]; string
0x180016a2c  lea     rdx, [rbp+var_28]; length
0x180016a30  mov     [rbp+var_28], 0
0x180016a37  call    cs:__imp_WindowsGetStringRawBuffer
0x180016a3d  mov     r8d, [rbp+var_28]
0x180016a41  mov     edx, 0
0x180016a46  add     r8, r8
0x180016a49  jz      short loc_180016A6A
0x180016a4b  nop     dword ptr [rax+rax+00h]
0x180016a50  movzx   ecx, byte ptr [rax+rdx]
0x180016a54  inc     rdx
0x180016a57  xor     ecx, r14d
0x180016a5a  imul    r14d, ecx, 1000193h
0x180016a61  cmp     rdx, r8
0x180016a64  jb      short loc_180016A50
0x180016a66  lea     r12, [r13+60h]
0x180016a6a  mov     rsi, [r13+50h]
0x180016a6e  xor     edx, edx
0x180016a70  mov     eax, r14d
0x180016a73  div     dword ptr [r12]
0x180016a77  mov     r15d, edx
0x180016a7a  mov     [rbp+var_10], r15
0x180016a7e  test    rsi, rsi
0x180016a81  jz      short loc_180016A94
0x180016a83  mov     rsi, [rsi+rdx*8]
0x180016a87  test    rsi, rsi
0x180016a8a  jnz     loc_180016C84
0x180016a90  mov     r15, [rbp+var_10]
0x180016a94  cmp     qword ptr [r13+50h], 0
0x180016a99  mov     rcx, r15
0x180016a9c  jz      loc_180016C1F
0x180016aa2  lea     r12, [r13+48h]
0x180016aa6  mov     rsi, [r13+90h]
0x180016aad  test    rsi, rsi
0x180016ab0  jz      loc_180016BD0
0x180016ab6  mov     rax, [rsi+10h]
0x180016aba  mov     [r13+90h], rax
0x180016ac1  mov     rax, [rbp+newString]
0x180016ac5  mov     [rsi], rax
0x180016ac8  mov     [rsi+18h], r14d
0x180016acc  inc     qword ptr [r13+58h]
0x180016ad0  mov     rax, [r13+50h]
0x180016ad4  mov     rdx, [rax+rcx*8]
0x180016ad8  mov     [rsi+10h], rdx
0x180016adc  mov     rax, [r13+50h]
0x180016ae0  mov     [rax+rcx*8], rsi
0x180016ae4  mov     rdx, [r13+58h]
0x180016ae8  cmp     rdx, [r13+70h]
0x180016aec  ja      loc_180016DCB
0x180016af2  mov     rax, [rbp+string]
0x180016af6  mov     [rsi+8], rax
0x180016afa  xor     eax, eax
0x180016afc  mov     r15d, eax
0x180016aff  jmp     short loc_180016B16
0x180016b01  mov     ecx, r15d
0x180016b04  test    rsi, rsi
0x180016b07  jnz     short loc_180016AB6
0x180016b09  mov     r15d, 8000FFFFh
0x180016b0f  test    r15d, r15d
0x180016b12  js      short loc_180016B1E
0x180016b14  xor     eax, eax
0x180016b16  mov     [rbp+newString], rax
0x180016b1a  mov     [rbp+string], rax
0x180016b1e  mov     rsi, [rbp+arg_18]
0x180016b22  mov     r14, [rsp+58h+var_8]
0x180016b27  test    rdi, rdi
0x180016b2a  jz      short loc_180016B3F
0x180016b2c  cmp     dword ptr [rdi], 1
0x180016b2f  jz      loc_180016E0F
0x180016b35  lea     rcx, [rdi+8]; SRWLock
0x180016b39  call    cs:__imp_ReleaseSRWLockExclusive
0x180016b3f  mov     rcx, rbx; string
0x180016b42  call    cs:__imp_WindowsDeleteString
0x180016b48  mov     rcx, [rbp+string]; string
0x180016b4c  call    cs:__imp_WindowsDeleteString
0x180016b52  test    r15d, r15d
0x180016b55  js      short loc_180016B89
0x180016b57  cmp     byte ptr [rsi], 0
0x180016b5a  mov     eax, 1
0x180016b5f  movzx   edx, byte ptr [r13+0B9h]
0x180016b67  mov     r9d, 3
0x180016b6d  movzx   ecx, byte ptr [rbp+arg_18]
0x180016b71  cmovz   r9d, eax
0x180016b75  mov     rax, [rbp+arg_8]
0x180016b79  mov     r8, r13
0x180016b7c  mov     [rsp+58h+var_38], rax
0x180016b81  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180016b86  mov     r15d, eax
0x180016b89  mov     rsi, [rsp+58h+arg_10]
0x180016b91  mov     rcx, [rbp+newString]; string
0x180016b95  call    cs:__imp_WindowsDeleteString
0x180016b9b  mov     eax, r15d
0x180016b9e  add     rsp, 58h
0x180016ba2  pop     r15
0x180016ba4  pop     r13
0x180016ba6  pop     r12
0x180016ba8  pop     rdi
0x180016ba9  pop     rbx
0x180016baa  pop     rbp
0x180016bab  retn
0x180016bac  cmp     [rax+18h], esi
0x180016baf  jz      loc_180016CF5
0x180016bb5  mov     rax, [rax+10h]
0x180016bb9  jmp     loc_180016A0D
0x180016bbe  xor     edx, edx
0x180016bc0  mov     ecx, 8000FFFFh
0x180016bc5  call    cs:__imp_RoOriginateError
0x180016bcb  jmp     loc_180016924
0x180016bd0  mov     esi, [r13+84h]
0x180016bd7  mov     eax, 20h ; ' '
0x180016bdc  mul     rsi
0x180016bdf  mov     [rbp+length], 0
0x180016be7  test    rdx, rdx
0x180016bea  jnz     short loc_180016BF9
0x180016bec  lea     rcx, [rax+8]; Size
0x180016bf0  cmp     rcx, rax
0x180016bf3  jnb     loc_180016C97
0x180016bf9  mov     r15d, 8007000Eh
0x180016bff  jmp     loc_180016B0F
0x180016c04  xor     ecx, ecx; string
0x180016c06  mov     [rbp+string], r12
0x180016c0a  call    cs:__imp_WindowsDeleteString
0x180016c10  mov     rcx, [rbp+string]; string
0x180016c14  call    cs:__imp_WindowsDeleteString
0x180016c1a  jmp     loc_180016B91
0x180016c1f  mov     esi, [r12]
0x180016c23  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016c2a  mov     eax, 8
0x180016c2f  mul     rsi
0x180016c32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016c39  cmovb   rax, rcx
0x180016c3d  mov     rcx, rax; unsigned __int64
0x180016c40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016c45  mov     [r13+50h], rax
0x180016c49  test    rax, rax
0x180016c4c  jz      short loc_180016BF9
0x180016c4e  cmp     esi, 1FFFFFFFh
0x180016c54  ja      loc_180016B09
0x180016c5a  lea     r8, ds:0[rsi*8]; Size
0x180016c62  xor     edx, edx; Val
0x180016c64  mov     rcx, rax; void *
0x180016c67  call    memset_0
0x180016c6c  mov     [r12], esi
0x180016c70  lea     r12, [r13+48h]
0x180016c74  mov     rcx, r12
0x180016c77  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::UpdateRehashThresholds(void)
0x180016c7c  mov     rcx, r15
0x180016c7f  jmp     loc_180016AA6
0x180016c84  cmp     [rsi+18h], r14d
0x180016c88  jz      loc_180016D88
0x180016c8e  mov     rsi, [rsi+10h]
0x180016c92  jmp     loc_180016A87
0x180016c97  call    _o_malloc_0
0x180016c9c  test    rax, rax
0x180016c9f  jz      loc_180016BF9
0x180016ca5  mov     rcx, [r13+88h]
0x180016cac  lea     r8d, [rsi-1]
0x180016cb0  mov     edx, r8d
0x180016cb3  shl     rdx, 5
0x180016cb7  add     rdx, 8
0x180016cbb  mov     [rax], rcx
0x180016cbe  add     rdx, rax
0x180016cc1  mov     [r13+88h], rax
0x180016cc8  test    r8d, r8d
0x180016ccb  js      loc_180016B09
0x180016cd1  mov     rax, [r13+90h]
0x180016cd8  mov     rsi, rdx
0x180016cdb  mov     [rdx+10h], rax
0x180016cdf  mov     [r13+90h], rdx
0x180016ce6  sub     rdx, 20h ; ' '
0x180016cea  sub     r8d, 1
0x180016cee  jns     short loc_180016CD1
0x180016cf0  jmp     loc_180016B01
0x180016cf5  mov     r8, [rbp+newString]
0x180016cf9  lea     r9, [rbp+length]
0x180016cfd  mov     rdx, [rax]
0x180016d00  mov     byte ptr [rbp+length], 0
0x180016d04  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x180016d09  mov     r15d, eax
0x180016d0c  test    eax, eax
0x180016d0e  js      loc_180016B1E
0x180016d14  cmp     byte ptr [rbp+length], 0
0x180016d18  jz      loc_180016DFB
0x180016d1e  mov     rsi, qword ptr [rbp+var_28]
0x180016d22  xor     ecx, ecx; string
0x180016d24  mov     rbx, [rsi+8]
0x180016d28  call    cs:__imp_WindowsDeleteString
0x180016d2e  mov     rax, [rbp+string]
0x180016d32  xor     r15d, r15d
0x180016d35  mov     [rsi+8], rax
0x180016d39  mov     rsi, [rbp+arg_18]
0x180016d3d  mov     [rbp+string], 0
0x180016d45  mov     byte ptr [rsi], 1
0x180016d48  jmp     loc_180016B22
0x180016d4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016d54  mov     ecx, 4; unsigned __int64
0x180016d59  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016d5e  mov     rsi, rax
0x180016d61  test    rax, rax
0x180016d64  jz      loc_1800169AF
0x180016d6a  mov     dword ptr [rax], 1
0x180016d70  mov     rcx, [r13+0B0h]; this
0x180016d77  call    ?Release@Tag@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::Tag::Release(void)
0x180016d7c  mov     [r13+0B0h], rsi
0x180016d83  jmp     loc_1800169AF
0x180016d88  mov     r8, [rbp+newString]
0x180016d8c  lea     r9, [rbp+length]
0x180016d90  mov     rdx, [rsi]
0x180016d93  mov     byte ptr [rbp+length], 0
0x180016d97  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x180016d9c  mov     r15d, eax
0x180016d9f  test    eax, eax
0x180016da1  js      loc_180016B1E
0x180016da7  cmp     byte ptr [rbp+length], 0
0x180016dab  jnz     loc_180016AF2
0x180016db1  jmp     loc_180016C8E
0x180016db6  cmp     [rdi+8], ebx
0x180016db9  jnz     loc_180016985
0x180016dbf  mov     dword ptr [rdi+8], 0F0000000h
0x180016dc6  jmp     loc_180016985
0x180016dcb  cmp     dword ptr [r13+80h], 0
0x180016dd3  jnz     loc_180016AF2
0x180016dd9  mov     rcx, r12
0x180016ddc  call    ?PickSize@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEBAI_K@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::PickSize(unsigned __int64)
  ... truncated ...
```
