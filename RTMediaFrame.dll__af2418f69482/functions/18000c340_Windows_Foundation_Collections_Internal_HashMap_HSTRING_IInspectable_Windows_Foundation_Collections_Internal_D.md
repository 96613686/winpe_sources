# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18000c340`
- end: `0x18000ca42`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `1794`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004704`
- `0x18000b090`
- `0x18000e178`
- `0x18001cadc`
- `0x18001ce90`

## callees

- `0x1800019c0`
- `0x18000a930`
- `0x18000c340`
- `0x18000ca48`
- `0x18000ca64`
- `0x1800174dc`
- `0x180019420`
- `0x180022528`
- `0x180026e0c`
- `0x180027490`
- `0x180027a20`
- `0x180032a9c`
- `0x18003a818`
- `0x18003d210`
- `0x180052010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c7a0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c7a0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c84e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c84e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c430`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c430`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c63c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000c38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000c38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c501`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        void *a3,
        _BYTE *a4)
{
  _QWORD *v6; // r12
  unsigned __int128 v7; // rax
  unsigned __int64 StringRawBuffer; // r8
  HRESULT v9; // r14d
  void *v10; // r13
  char v11; // r15
  void *v12; // rcx
  _QWORD *v13; // rbx
  unsigned int v14; // esi
  unsigned int v15; // edi
  unsigned __int64 v16; // rcx
  __int64 v17; // r15
  _DWORD *v18; // r12
  __int64 i; // r15
  PCWSTR v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // r15
  __int64 v24; // rdi
  __int64 j; // rdi
  __int64 v26; // r14
  _QWORD *v27; // r13
  void *v28; // rdi
  char v29; // si
  _BYTE *v30; // r15
  void *v31; // rcx
  char v32; // al
  __int64 v33; // r9
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // eax
  _DWORD *v39; // rax
  Windows::Internal::Details::Git *v40; // rcx
  void *v41; // rdi
  _DWORD *v42; // rax
  _DWORD *v43; // rdi
  char v44; // [rsp+30h] [rbp-30h]
  char v45; // [rsp+31h] [rbp-2Fh]
  _BYTE v46[2]; // [rsp+32h] [rbp-2Eh] BYREF
  UINT32 length; // [rsp+34h] [rbp-2Ch] BYREF
  void *v48; // [rsp+38h] [rbp-28h]
  HSTRING newString; // [rsp+40h] [rbp-20h] BYREF
  void *v50; // [rsp+48h] [rbp-18h] BYREF
  int v51; // [rsp+51h] [rbp-Fh]
  __int16 v52; // [rsp+55h] [rbp-Bh]
  char v53; // [rsp+57h] [rbp-9h]
  _QWORD *v54; // [rsp+A0h] [rbp+40h]

  v54 = (_QWORD *)a1;
  v6 = (_QWORD *)a1;
  *a4 = 0;
  if ( !*(_BYTE *)(a1 + 184) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  v9 = WindowsDuplicateString(a2, &newString);
  if ( v9 >= 0 )
  {
    v10 = 0;
    v48 = 0;
    v11 = 0;
    v44 = 0;
    if ( a3 )
    {
      v50 = 0;
      if ( (**(int (__fastcall ***)(void *, GUID *, void **))a3)(a3, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, &v50) < 0 )
      {
        v39 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
        v41 = v39;
        if ( v39 )
        {
          *v39 = 1;
          v39[1] = 0;
          v9 = Windows::Internal::Details::Git::Acquire(v40);
          if ( v9 >= 0 )
            v9 = (*(__int64 (__fastcall **)(__int64, void *, GUID *, __int64))(*(_QWORD *)qword_180072C08 + 24LL))(
                   qword_180072C08,
                   a3,
                   &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                   (__int64)v41 + 4);
          if ( v9 < 0 )
          {
            XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v41);
          }
          else
          {
            v10 = v41;
            v48 = v41;
            v11 = 1;
            v44 = 1;
          }
        }
        else
        {
          v9 = -2147024882;
        }
        Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v50);
      }
      else
      {
        v44 = 0;
        v10 = a3;
        v48 = a3;
        (*(void (__fastcall **)(void *))(*(_QWORD *)a3 + 8LL))(a3);
        v12 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        v9 = 0;
      }
    }
    else
    {
      v9 = 0;
    }
    if ( v9 < 0 )
    {
      v28 = 0;
      v29 = 0;
      v31 = 0;
      v50 = 0;
      v32 = 0;
      v30 = a4;
LABEL_39:
      if ( v32 )
      {
        XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v31);
      }
      else if ( v50 )
      {
        (*(void (__fastcall **)(void *, _QWORD, unsigned __int64))(*(_QWORD *)v50 + 16LL))(
          v50,
          *((_QWORD *)&v7 + 1),
          StringRawBuffer);
      }
      if ( v29 )
      {
        XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v28);
      }
      else if ( v28 )
      {
        (*(void (__fastcall **)(void *, _QWORD, unsigned __int64))(*(_QWORD *)v28 + 16LL))(
          v28,
          *((_QWORD *)&v7 + 1),
          StringRawBuffer);
      }
      if ( v9 >= 0 )
      {
        v33 = 3;
        if ( !*v30 )
          v33 = 1;
        v9 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
               (unsigned __int8)v54,
               *((unsigned __int8 *)v6 + 185),
               v6,
               v33,
               a2);
      }
      goto LABEL_49;
    }
    v13 = v6 + 20;
    if ( *((_DWORD *)v6 + 40) == 1 )
    {
      if ( !*((_DWORD *)v6 + 42) )
        *((_DWORD *)v6 + 42) = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)v6 + 21);
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(v46, *((unsigned __int8 *)v6 + 186), (char *)v6 + 188);
    if ( *(int *)v6[22] > 1 )
    {
      v42 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
      v43 = v42;
      if ( v42 )
      {
        *v42 = 1;
        XWinRT::SecureVersionTag::Tag::Release((XWinRT::SecureVersionTag::Tag *)v6[22]);
        v6[22] = v43;
      }
    }
    length = 0;
    StringRawBuffer = (unsigned __int64)WindowsGetStringRawBuffer(newString, &length);
    v14 = -2128831035;
    v15 = -2128831035;
    *((_QWORD *)&v7 + 1) = 2LL * length;
    v16 = 0;
    if ( *((_QWORD *)&v7 + 1) )
    {
      do
        v15 = 16777619 * (v15 ^ *(unsigned __int8 *)(StringRawBuffer + v16++));
      while ( v16 < *((_QWORD *)&v7 + 1) );
      v45 = 0;
    }
    else
    {
      v45 = 0;
      v44 = v11;
      v48 = v10;
    }
    v50 = 0;
    v17 = v6[10];
    v18 = v6 + 12;
    if ( v17 )
    {
      *((_QWORD *)&v7 + 1) = v15 % *v18;
      for ( i = *(_QWORD *)(v17 + 8LL * *((_QWORD *)&v7 + 1)); i; i = *(_QWORD *)(i + 24) )
      {
        if ( *(_DWORD *)(i + 32) == v15 )
        {
          v46[0] = 0;
          v9 = XWinRT::StringEquals::operator()(v16, *(_QWORD *)i, newString, v46);
          if ( v9 < 0 )
            goto LABEL_88;
          if ( v46[0] )
          {
            v50 = *(void **)(i + 8);
            v45 = *(_BYTE *)(i + 16);
            *(_QWORD *)(i + 8) = v10;
            *(_BYTE *)(i + 16) = v44;
            *(_DWORD *)(i + 17) = v51;
            *(_WORD *)(i + 21) = v52;
            *(_BYTE *)(i + 23) = v53;
            v28 = 0;
            v29 = 0;
            v30 = a4;
            *a4 = 1;
            v9 = 0;
            v6 = v54;
            goto LABEL_35;
          }
        }
      }
    }
    if ( v54[11] == 0x7FFFFFFF )
    {
      v9 = -2147024882;
LABEL_88:
      v6 = v54;
      goto LABEL_89;
    }
    length = 0;
    v20 = WindowsGetStringRawBuffer(newString, &length);
    StringRawBuffer = 2LL * length;
    v22 = 0;
    if ( StringRawBuffer )
    {
      do
      {
        v21 = v14 ^ *((unsigned __int8 *)v20 + v22);
        v14 = 16777619 * v21;
        ++v22;
      }
      while ( v22 < StringRawBuffer );
      v18 = v54 + 12;
    }
    *((_QWORD *)&v7 + 1) = v14 % *v18;
    v23 = DWORD2(v7);
    v24 = v54[10];
    if ( v24 )
    {
      for ( j = *(_QWORD *)(v24 + 8LL * *((_QWORD *)&v7 + 1)); j; j = *(_QWORD *)(j + 24) )
      {
        if ( *(_DWORD *)(j + 32) == v14 )
        {
          v46[0] = 0;
          v9 = XWinRT::StringEquals::operator()(v21, *(_QWORD *)j, newString, v46);
          if ( v9 < 0 )
            goto LABEL_88;
          if ( v46[0] )
          {
            v6 = v54;
            goto LABEL_30;
          }
        }
      }
    }
    v26 = v23;
    v27 = v54 + 9;
    if ( !v54[10] )
    {
      v35 = (unsigned int)*v18;
      v36 = 8 * v35;
      if ( !is_mul_ok(v35, 8u) )
        v36 = -1;
      *(_QWORD *)&v7 = operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
      v54[10] = v7;
      if ( !(_QWORD)v7 )
      {
        v9 = -2147024882;
        v6 = v54;
        goto LABEL_89;
      }
      if ( (unsigned int)v35 > 0x1FFFFFFF )
      {
        v6 = v54;
        goto LABEL_32;
      }
      memset_0((void *)v7, 0, 8 * v35);
      *v18 = v35;
      XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(v27);
    }
    v6 = v54;
    if ( !v54[18] )
    {
      LOBYTE(v54) = 0;
      v7 = *((unsigned int *)v6 + 33) * (unsigned __int128)0x28uLL;
      if ( !is_mul_ok(*((unsigned int *)v6 + 33), 0x28u)
        || (__int64)v7 + 8 < (unsigned __int64)v7
        || (*(_QWORD *)&v7 = malloc(40LL * *((unsigned int *)v6 + 33) + 8), !(_QWORD)v7) )
      {
        v9 = -2147024882;
        goto LABEL_89;
      }
      *(_QWORD *)v7 = v6[17];
      v6[17] = v7;
      StringRawBuffer = (unsigned int)(*((_DWORD *)v6 + 33) - 1);
      v37 = v7 + 8 * (4LL * (unsigned int)StringRawBuffer + 1 + (unsigned int)StringRawBuffer);
      if ( (StringRawBuffer & 0x80000000) == 0LL )
      {
        do
        {
          *(_QWORD *)(v37 + 24) = v6[18];
          v6[18] = v37;
          v37 -= 40;
          StringRawBuffer = (unsigned int)(StringRawBuffer - 1);
        }
        while ( (StringRawBuffer & 0x80000000) == 0LL );
        v26 = v23;
      }
    }
    j = v6[18];
    if ( j )
    {
      v6[18] = *(_QWORD *)(j + 24);
      *(_QWORD *)j = newString;
      *(_QWORD *)(j + 8) = 0;
      *(_BYTE *)(j + 16) = 0;
      *(_DWORD *)(j + 32) = v14;
      ++v6[11];
      *(_QWORD *)(j + 24) = *(_QWORD *)(v6[10] + 8 * v26);
      *(_QWORD *)(v6[10] + 8 * v26) = j;
      *((_QWORD *)&v7 + 1) = v6[11];
      if ( *((_QWORD *)&v7 + 1) <= v6[14]
        || *((_DWORD *)v6 + 32)
        || (v38 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(
                    v27,
                    *((_QWORD *)&v7 + 1),
                    StringRawBuffer),
            v9 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Rehash(
                   v27,
                   v38),
            v9 >= 0) )
      {
LABEL_30:
        *(_QWORD *)(j + 8) = v48;
        *(_BYTE *)(j + 16) = v44;
        *(_DWORD *)(j + 17) = v51;
        *(_WORD *)(j + 21) = v52;
        *(_BYTE *)(j + 23) = v53;
        v9 = 0;
        newString = 0;
        v28 = 0;
        v29 = 0;
        goto LABEL_34;
      }
LABEL_89:
      v29 = v44;
      v28 = v48;
LABEL_34:
      v30 = a4;
LABEL_35:
      if ( v13 )
      {
        if ( *(_DWORD *)v13 == 1 )
          *((_DWORD *)v13 + 2) += 0x10000000;
        else
          ReleaseSRWLockExclusive((PSRWLOCK)v13 + 1);
      }
      v31 = v50;
      v32 = v45;
      goto LABEL_39;
    }
LABEL_32:
    v9 = -2147418113;
    goto LABEL_89;
  }
LABEL_49:
  WindowsDeleteString(newString);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c340  mov     [rsp-38h+arg_10], rbx
0x18000c345  mov     [rsp-38h+arg_18], r9
0x18000c34a  mov     [rsp-38h+arg_8], rdx
0x18000c34f  mov     [rsp-38h+arg_0], rcx
0x18000c354  push    rbp
0x18000c355  push    rsi
0x18000c356  push    rdi
0x18000c357  push    r12
0x18000c359  push    r13
0x18000c35b  push    r14
0x18000c35d  push    r15
0x18000c35f  mov     rbp, rsp
0x18000c362  sub     rsp, 60h
0x18000c366  mov     rbx, r8
0x18000c369  mov     rdi, rdx
0x18000c36c  mov     r12, rcx
0x18000c36f  mov     byte ptr [r9], 0
0x18000c373  cmp     byte ptr [rcx+0B8h], 0
0x18000c37a  jz      loc_18000C847
0x18000c380  xor     esi, esi
0x18000c382  mov     [rbp+newString], rsi
0x18000c386  lea     rdx, [rbp+newString]; newString
0x18000c38a  mov     rcx, rdi; string
0x18000c38d  call    cs:__imp_WindowsDuplicateString
0x18000c393  mov     r14d, eax
0x18000c396  test    eax, eax
0x18000c398  js      loc_18000C6BF
0x18000c39e  mov     r13d, esi
0x18000c3a1  mov     [rbp+var_28], rsi
0x18000c3a5  xor     r15b, r15b
0x18000c3a8  mov     [rbp+var_30], r15b
0x18000c3ac  test    rbx, rbx
0x18000c3af  jz      loc_18000C859
0x18000c3b5  mov     [rbp+var_18], rsi
0x18000c3b9  mov     rax, [rbx]
0x18000c3bc  lea     r8, [rbp+var_18]
0x18000c3c0  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x18000c3c7  mov     rcx, rbx
0x18000c3ca  mov     rax, [rax]
0x18000c3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d2  test    eax, eax
0x18000c3d4  js      loc_18000C861
0x18000c3da  mov     [rbp+var_30], r15b
0x18000c3de  mov     r13, rbx
0x18000c3e1  mov     [rbp+var_28], rbx
0x18000c3e5  mov     rax, [rbx]
0x18000c3e8  mov     rcx, rbx
0x18000c3eb  mov     rax, [rax+8]
0x18000c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f4  nop
0x18000c3f5  mov     rcx, [rbp+var_18]
0x18000c3f9  test    rcx, rcx
0x18000c3fc  jz      short loc_18000C40F
0x18000c3fe  mov     [rbp+var_18], rsi
0x18000c402  mov     rax, [rcx]
0x18000c405  mov     rax, [rax+10h]
0x18000c409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c40e  nop
0x18000c40f  mov     r14d, esi
0x18000c412  test    r14d, r14d
0x18000c415  js      loc_18000C8EE
0x18000c41b  lea     rbx, [r12+0A0h]
0x18000c423  cmp     dword ptr [rbx], 1
0x18000c426  jz      loc_18000C905
0x18000c42c  lea     rcx, [rbx+8]; SRWLock
0x18000c430  call    cs:__imp_AcquireSRWLockExclusive
0x18000c436  lea     r8, [r12+0BCh]
0x18000c43e  movzx   edx, byte ptr [r12+0BAh]
0x18000c447  lea     rcx, [rbp+var_2E]
0x18000c44b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18000c450  mov     rax, [r12+0B0h]
0x18000c458  mov     ecx, [rax]
0x18000c45a  cmp     ecx, 1
0x18000c45d  jg      loc_18000C91B
0x18000c463  mov     [rbp+length], esi
0x18000c466  lea     rdx, [rbp+length]; length
0x18000c46a  mov     rcx, [rbp+newString]; string
0x18000c46e  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c474  mov     r8, rax
0x18000c477  mov     esi, 811C9DC5h
0x18000c47c  mov     edi, esi
0x18000c47e  mov     edx, [rbp+length]
0x18000c481  add     rdx, rdx
0x18000c484  mov     r14d, 0
0x18000c48a  mov     ecx, r14d
0x18000c48d  jz      loc_18000C806
0x18000c493  nop     dword ptr [rax+00h]
0x18000c497  nop     word ptr [rax+rax+00000000h]
0x18000c4a0  movzx   eax, byte ptr [r8+rcx]
0x18000c4a5  xor     eax, edi
0x18000c4a7  imul    edi, eax, 1000193h
0x18000c4ad  inc     rcx
0x18000c4b0  cmp     rcx, rdx
0x18000c4b3  jb      short loc_18000C4A0
0x18000c4b5  mov     [rbp+var_2F], r14b
0x18000c4b9  mov     [rbp+var_18], r14
0x18000c4bd  mov     r15, [r12+50h]
0x18000c4c2  add     r12, 60h ; '`'
0x18000c4c6  test    r15, r15
0x18000c4c9  jz      short loc_18000C4E3
0x18000c4cb  xor     edx, edx
0x18000c4cd  mov     eax, edi
0x18000c4cf  div     dword ptr [r12]
0x18000c4d3  mov     r15, [r15+rdx*8]
0x18000c4d7  test    r15, r15
0x18000c4da  jnz     loc_18000C6F6
0x18000c4e0  xor     r14d, r14d
0x18000c4e3  mov     r13, [rbp+arg_0]
0x18000c4e7  cmp     qword ptr [r13+58h], 7FFFFFFFh
0x18000c4ef  jz      loc_18000C9CA
0x18000c4f5  mov     [rbp+length], r14d
0x18000c4f9  lea     rdx, [rbp+length]; length
0x18000c4fd  mov     rcx, [rbp+newString]; string
0x18000c501  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c507  mov     r8d, [rbp+length]
0x18000c50b  add     r8, r8
0x18000c50e  mov     rdx, r14
0x18000c511  jz      short loc_18000C538
0x18000c513  nop     dword ptr [rax+00h]
0x18000c517  nop     word ptr [rax+rax+00000000h]
0x18000c520  movzx   ecx, byte ptr [rax+rdx]
0x18000c524  xor     ecx, esi
0x18000c526  imul    esi, ecx, 1000193h
0x18000c52c  inc     rdx
0x18000c52f  cmp     rdx, r8
0x18000c532  jb      short loc_18000C520
0x18000c534  lea     r12, [r13+60h]
0x18000c538  xor     edx, edx
0x18000c53a  mov     eax, esi
0x18000c53c  div     dword ptr [r12]
0x18000c540  mov     r15d, edx
0x18000c543  mov     rdi, [r13+50h]
0x18000c547  test    rdi, rdi
0x18000c54a  jz      short loc_18000C559
0x18000c54c  mov     rdi, [rdi+rdx*8]
0x18000c550  test    rdi, rdi
0x18000c553  jnz     loc_18000C6E4
0x18000c559  mov     r14, r15
0x18000c55c  add     r13, 48h ; 'H'
0x18000c560  mov     rax, [rbp+arg_0]
0x18000c564  cmp     qword ptr [rax+50h], 0
0x18000c569  jz      loc_18000C709
0x18000c56f  mov     r12, [rbp+arg_0]
0x18000c573  cmp     qword ptr [r12+90h], 0
0x18000c57c  jz      loc_18000C76F
0x18000c582  mov     rdi, [r12+90h]
0x18000c58a  test    rdi, rdi
0x18000c58d  jz      short loc_18000C60B
0x18000c58f  mov     rax, [rdi+18h]
0x18000c593  mov     [r12+90h], rax
0x18000c59b  mov     rax, [rbp+newString]
0x18000c59f  mov     [rdi], rax
0x18000c5a2  mov     qword ptr [rdi+8], 0
0x18000c5aa  mov     byte ptr [rdi+10h], 0
0x18000c5ae  mov     [rdi+20h], esi
0x18000c5b1  inc     qword ptr [r12+58h]
0x18000c5b6  mov     rax, [r12+50h]
0x18000c5bb  mov     rdx, [rax+r14*8]
0x18000c5bf  mov     [rdi+18h], rdx
0x18000c5c3  mov     rax, [r12+50h]
0x18000c5c8  mov     [rax+r14*8], rdi
0x18000c5cc  mov     rdx, [r12+58h]
0x18000c5d1  cmp     rdx, [r12+70h]
0x18000c5d6  ja      loc_18000C816
0x18000c5dc  mov     rax, [rbp+var_28]
0x18000c5e0  mov     [rdi+8], rax
0x18000c5e4  movzx   eax, [rbp+var_30]
0x18000c5e8  mov     [rdi+10h], al
0x18000c5eb  mov     eax, [rbp+var_F]
0x18000c5ee  mov     [rdi+11h], eax
0x18000c5f1  movzx   eax, [rbp+var_B]
0x18000c5f5  mov     [rdi+15h], ax
0x18000c5f9  movzx   eax, [rbp+var_9]
0x18000c5fd  mov     [rdi+17h], al
0x18000c600  xor     eax, eax
0x18000c602  mov     r14d, eax
0x18000c605  jmp     short loc_18000C61C
0x18000c607  mov     r12, [rbp+arg_0]
0x18000c60b  mov     r14d, 8000FFFFh
0x18000c611  test    r14d, r14d
0x18000c614  js      loc_18000C9D4
0x18000c61a  xor     eax, eax
0x18000c61c  mov     [rbp+newString], rax
0x18000c620  mov     rdi, rax
0x18000c623  xor     sil, sil
0x18000c626  mov     r15, [rbp+arg_18]
0x18000c62a  test    rbx, rbx
0x18000c62d  jz      short loc_18000C642
0x18000c62f  cmp     dword ptr [rbx], 1
0x18000c632  jz      loc_18000CA1E
0x18000c638  lea     rcx, [rbx+8]; SRWLock
0x18000c63c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c642  mov     rcx, [rbp+var_18]; void *
0x18000c646  movzx   eax, [rbp+var_2F]
0x18000c64a  test    al, al
0x18000c64c  jnz     loc_18000CA2A
0x18000c652  mov     rcx, [rbp+var_18]
0x18000c656  test    rcx, rcx
0x18000c659  jz      short loc_18000C668
0x18000c65b  mov     rax, [rcx]
0x18000c65e  mov     rax, [rax+10h]
0x18000c662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c667  nop
0x18000c668  test    sil, sil
0x18000c66b  jnz     loc_18000CA34
0x18000c671  test    rdi, rdi
0x18000c674  jz      short loc_18000C686
0x18000c676  mov     rax, [rdi]
0x18000c679  mov     rcx, rdi
0x18000c67c  mov     rax, [rax+10h]
0x18000c680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c685  nop
0x18000c686  test    r14d, r14d
0x18000c689  js      short loc_18000C6BF
0x18000c68b  mov     r9d, 3
0x18000c691  cmp     byte ptr [r15], 0
0x18000c695  mov     eax, 1
0x18000c69a  cmovz   r9d, eax
0x18000c69e  mov     rax, [rbp+arg_8]
0x18000c6a2  mov     [rsp+60h+var_40], rax
0x18000c6a7  mov     r8, r12
0x18000c6aa  movzx   edx, byte ptr [r12+0B9h]
0x18000c6b3  movzx   ecx, byte ptr [rbp+arg_0]
0x18000c6b7  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18000c6bc  mov     r14d, eax
0x18000c6bf  mov     rcx, [rbp+newString]; string
0x18000c6c3  call    cs:__imp_WindowsDeleteString
0x18000c6c9  mov     eax, r14d
0x18000c6cc  mov     rbx, [rsp+60h+arg_10]
0x18000c6d4  add     rsp, 60h
0x18000c6d8  pop     r15
0x18000c6da  pop     r14
0x18000c6dc  pop     r13
0x18000c6de  pop     r12
0x18000c6e0  pop     rdi
0x18000c6e1  pop     rsi
0x18000c6e2  pop     rbp
0x18000c6e3  retn
0x18000c6e4  cmp     [rdi+20h], esi
0x18000c6e7  jz      loc_18000C9E1
0x18000c6ed  mov     rdi, [rdi+18h]
0x18000c6f1  jmp     loc_18000C550
0x18000c6f6  cmp     [r15+20h], edi
0x18000c6fa  jz      loc_18000C958
0x18000c700  mov     r15, [r15+18h]
0x18000c704  jmp     loc_18000C4D7
0x18000c709  mov     edi, [r12]
0x18000c70d  mov     eax, 8
0x18000c712  mul     rdi
0x18000c715  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c71c  cmovb   rax, rcx
0x18000c720  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c727  mov     rcx, rax; unsigned __int64
0x18000c72a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c72f  mov     rcx, [rbp+arg_0]
0x18000c733  mov     [rcx+50h], rax
0x18000c737  test    rax, rax
0x18000c73a  jz      loc_18000CA0F
0x18000c740  cmp     edi, 1FFFFFFFh
0x18000c746  ja      loc_18000C607
0x18000c74c  lea     r8, ds:0[rdi*8]; Size
0x18000c754  xor     edx, edx; Val
0x18000c756  mov     rcx, rax; void *
0x18000c759  call    memset_0
0x18000c75e  mov     [r12], edi
0x18000c762  mov     rcx, r13
0x18000c765  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(void)
0x18000c76a  jmp     loc_18000C56F
0x18000c76f  mov     [rbp+arg_0], 0
0x18000c777  mov     ecx, [r12+84h]
0x18000c77f  mov     eax, 28h ; '('
0x18000c784  mul     rcx
0x18000c787  test    rdx, rdx
0x18000c78a  jz      short loc_18000C797
0x18000c78c  mov     r14d, 8007000Eh
0x18000c792  jmp     loc_18000C611
0x18000c797  lea     rcx, [rax+8]; Size
0x18000c79b  cmp     rcx, rax
0x18000c79e  jb      short loc_18000C78C
0x18000c7a0  call    cs:__imp_malloc
0x18000c7a6  test    rax, rax
0x18000c7a9  jz      short loc_18000C78C
0x18000c7ab  mov     rcx, [r12+88h]
0x18000c7b3  mov     [rax], rcx
0x18000c7b6  mov     [r12+88h], rax
0x18000c7be  mov     r8d, [r12+84h]
0x18000c7c6  sub     r8d, 1
0x18000c7ca  lea     rcx, ds:1[r8*4]
0x18000c7d2  lea     rcx, [rcx+r8]
0x18000c7d6  lea     rcx, [rax+rcx*8]
0x18000c7da  js      loc_18000C582
0x18000c7e0  mov     rax, [r12+90h]
0x18000c7e8  mov     [rcx+18h], rax
0x18000c7ec  mov     [r12+90h], rcx
0x18000c7f4  sub     rcx, 28h ; '('
0x18000c7f8  sub     r8d, 1
0x18000c7fc  jns     short loc_18000C7E0
0x18000c7fe  mov     r14, r15
0x18000c801  jmp     loc_18000C582
0x18000c806  mov     [rbp+var_2F], cl
  ... truncated ...
```
