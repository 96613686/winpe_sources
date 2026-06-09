# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x180034680`
- end: `0x180034b6f`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `1263`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180031f2c`
- `0x180031fac`
- `0x180032d40`
- `0x180034680`
- `0x18003518c`
- `0x1800351a8`
- `0x1800351c4`
- `0x180061508`
- `0x1800f073c`
- `0x1800f10e4`
- `0x1800fc0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034894`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034894`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034967`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034967`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034716`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800346d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800346ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800346d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800346ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800347dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800347dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003497e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003498c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003497e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003498c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034aea`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180034779`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1800347fc`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180034779`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1800347fc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800346c1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800346c1`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        _BYTE *a4)
{
  _BYTE *v4; // r14
  HSTRING v6; // r15
  HRESULT v8; // edi
  HRESULT v9; // eax
  HSTRING v10; // rbx
  RTL_SRWLOCK *v11; // r12
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdi
  PCWSTR v15; // r13
  unsigned int i; // r14d
  WCHAR v17; // ax
  __int64 v18; // rdi
  __int64 j; // rdi
  PCWSTR v20; // rax
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rdi
  PCWSTR v23; // r15
  int v24; // r12d
  WCHAR v25; // ax
  unsigned int v26; // ecx
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 k; // rdi
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // kr00_8
  _QWORD *v32; // rax
  __int64 v33; // rcx
  int v34; // r8d
  _QWORD *m; // rdx
  __int64 v36; // r14
  __int64 v37; // r8
  unsigned __int64 v39; // rdi
  unsigned __int64 v40; // rax
  void *v41; // rax
  _DWORD *v42; // rax
  _DWORD *v43; // rdi
  unsigned int v44; // eax
  UINT32 length; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v46; // [rsp+34h] [rbp-1Ch]
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v49; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v50; // [rsp+98h] [rbp+48h]
  _BYTE *v51; // [rsp+A8h] [rbp+58h]

  v51 = a4;
  v50 = a2;
  *a4 = 0;
  v4 = a4;
  v6 = a2;
  if ( !*(_BYTE *)(a1 + 152) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  v8 = WindowsDuplicateString(v6, &newString);
  if ( v8 >= 0 )
  {
    v9 = WindowsDuplicateString(a3, string);
    v10 = 0;
    v8 = v9;
    if ( v9 < 0 )
    {
      string[0] = 0;
LABEL_37:
      WindowsDeleteString(v10);
      WindowsDeleteString(string[0]);
      if ( v8 >= 0 )
        v8 = Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(
               (unsigned __int8)v51,
               *(unsigned __int8 *)(a1 + 153),
               a1,
               *v4 != 0 ? 3 : 1,
               v6);
      goto LABEL_39;
    }
    v11 = (RTL_SRWLOCK *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !LODWORD(v11->Ptr) )
        LODWORD(v11->Ptr) = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v49, *(unsigned __int8 *)(a1 + 154), a1 + 156);
    if ( **(int **)(a1 + 144) > 1 )
    {
      v42 = operator new(4u, (const struct std::nothrow_t *)std::nothrow);
      v43 = v42;
      if ( v42 )
      {
        *v42 = 1;
        XWinRT::SecureVersionTag::Tag::Release(*(XWinRT::SecureVersionTag::Tag **)(a1 + 144));
        *(_QWORD *)(a1 + 144) = v43;
      }
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(newString, &length);
    v13 = length;
    v14 = 0;
    v15 = StringRawBuffer;
    v49 = -2128831035;
    for ( i = -2128831035; v14 < v13; i = 16777619 * (HIBYTE(v17) ^ (16777619 * (i ^ (unsigned __int8)v17))) )
      v17 = RtlUpcaseUnicodeChar(v15[v14++]);
    v18 = *(_QWORD *)(a1 + 48);
    if ( v18 )
    {
      for ( j = *(_QWORD *)(v18 + 8LL * (i % *(_DWORD *)(a1 + 64))); j; j = *(_QWORD *)(j + 16) )
      {
        if ( *(_DWORD *)(j + 24) == i && RegistryNamesAreEqual(*(HSTRING *)j, newString) )
        {
          v10 = *(HSTRING *)(j + 8);
          WindowsDeleteString(0);
          v4 = v51;
          *(HSTRING *)(j + 8) = string[0];
          v8 = 0;
          string[0] = 0;
          *v4 = 1;
          goto LABEL_34;
        }
      }
    }
    if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
    {
      v8 = -2147024882;
      goto LABEL_33;
    }
    length = 0;
    v20 = WindowsGetStringRawBuffer(newString, &length);
    v21 = length;
    v22 = 0;
    v23 = v20;
    if ( length )
    {
      v24 = -2128831035;
      do
      {
        v25 = RtlUpcaseUnicodeChar(v23[v22++]);
        v24 = 16777619 * (HIBYTE(v25) ^ (16777619 * (v24 ^ (unsigned __int8)v25)));
      }
      while ( v22 < v21 );
      v49 = v24;
      v11 = (RTL_SRWLOCK *)(a1 + 136);
    }
    v26 = v49;
    v27 = *(_QWORD *)(a1 + 48);
    v28 = v49 % *(_DWORD *)(a1 + 64);
    v46 = v28;
    if ( v27 )
    {
      for ( k = *(_QWORD *)(v27 + 8 * v28); k; k = *(_QWORD *)(k + 16) )
      {
        if ( *(_DWORD *)(k + 24) == v26 )
        {
          if ( RegistryNamesAreEqual(*(HSTRING *)k, newString) )
          {
            *(HSTRING *)(k + 8) = string[0];
            goto LABEL_31;
          }
          v26 = v49;
        }
      }
    }
    if ( !*(_QWORD *)(a1 + 48) )
    {
      v39 = *(unsigned int *)(a1 + 64);
      v40 = 8 * v39;
      if ( !is_mul_ok(v39, 8u) )
        v40 = -1;
      v41 = operator new[](v40, (const struct std::nothrow_t *)std::nothrow);
      *(_QWORD *)(a1 + 48) = v41;
      if ( !v41 )
      {
        v8 = -2147024882;
        goto LABEL_33;
      }
      if ( (unsigned int)v39 > 0x1FFFFFFF )
      {
        v8 = -2147418113;
        goto LABEL_33;
      }
      memset_0(v41, 0, 8 * v39);
      *(_DWORD *)(a1 + 64) = v39;
      XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds(a1 + 40);
    }
    if ( !*(_QWORD *)(a1 + 112) )
    {
      v31 = *(unsigned int *)(a1 + 100);
      v30 = 32 * v31;
      string[1] = 0;
      if ( !is_mul_ok(v31, 0x20u) || v30 + 8 < v30 || (v32 = malloc(v30 + 8)) == 0 )
      {
        v8 = -2147024882;
        goto LABEL_33;
      }
      v33 = *(_QWORD *)(a1 + 104);
      *(_QWORD *)(a1 + 104) = v32;
      v34 = *(_DWORD *)(a1 + 100) - 1;
      *v32 = v33;
      for ( m = &v32[4 * (unsigned int)v34 + 1]; v34 >= 0; --v34 )
      {
        m[2] = *(_QWORD *)(a1 + 112);
        *(_QWORD *)(a1 + 112) = m;
        m -= 4;
      }
    }
    v36 = *(_QWORD *)(a1 + 112);
    if ( v36 )
    {
      v37 = v46;
      *(_QWORD *)(a1 + 112) = *(_QWORD *)(v36 + 16);
      *(_QWORD *)v36 = newString;
      *(_DWORD *)(v36 + 24) = v49;
      ++*(_QWORD *)(a1 + 56);
      *(_QWORD *)(v36 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v37);
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v37) = v36;
      if ( *(_QWORD *)(a1 + 56) <= *(_QWORD *)(a1 + 80)
        || *(_DWORD *)(a1 + 96)
        || (v44 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(a1 + 40),
            v8 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(
                   a1 + 40,
                   v44),
            v8 >= 0) )
      {
        *(HSTRING *)(v36 + 8) = string[0];
LABEL_31:
        v8 = 0;
        newString = 0;
        string[0] = 0;
      }
    }
    else
    {
      v8 = -2147418113;
    }
LABEL_33:
    v4 = v51;
LABEL_34:
    if ( *(_DWORD *)(a1 + 128) == 1 )
      LODWORD(v11->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v11);
    v6 = v50;
    goto LABEL_37;
  }
LABEL_39:
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180034680  mov     [rsp-38h+arg_10], rbx
0x180034685  mov     [rsp-38h+arg_18], r9
0x18003468a  mov     [rsp-38h+arg_8], rdx
0x18003468f  push    rbp
0x180034690  push    rsi
0x180034691  push    rdi
0x180034692  push    r12
0x180034694  push    r13
0x180034696  push    r14
0x180034698  push    r15
0x18003469a  mov     rbp, rsp
0x18003469d  sub     rsp, 50h
0x1800346a1  mov     byte ptr [r9], 0
0x1800346a5  mov     r14, r9
0x1800346a8  cmp     byte ptr [rcx+98h], 0
0x1800346af  mov     rbx, r8
0x1800346b2  mov     r15, rdx
0x1800346b5  mov     rsi, rcx
0x1800346b8  jnz     short loc_1800346C7
0x1800346ba  xor     edx, edx
0x1800346bc  mov     ecx, 8000FFFFh
0x1800346c1  call    cs:__imp_RoOriginateError
0x1800346c7  lea     rdx, [rbp+newString]; newString
0x1800346cb  mov     [rbp+newString], 0
0x1800346d3  mov     rcx, r15; string
0x1800346d6  call    cs:__imp_WindowsDuplicateString
0x1800346dc  mov     edi, eax
0x1800346de  test    eax, eax
0x1800346e0  js      loc_180034988
0x1800346e6  lea     rdx, [rbp+string]; newString
0x1800346ea  mov     rcx, rbx; string
0x1800346ed  call    cs:__imp_WindowsDuplicateString
0x1800346f3  xor     ebx, ebx
0x1800346f5  mov     edi, eax
0x1800346f7  test    eax, eax
0x1800346f9  js      loc_180034B58
0x1800346ff  cmp     dword ptr [rsi+80h], 1
0x180034706  lea     r12, [rsi+88h]
0x18003470d  jz      loc_180034B41
0x180034713  mov     rcx, r12; SRWLock
0x180034716  call    cs:__imp_AcquireSRWLockExclusive
0x18003471c  movzx   edx, byte ptr [rsi+9Ah]
0x180034723  lea     r8, [rsi+9Ch]
0x18003472a  lea     rcx, [rbp+arg_0]
0x18003472e  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180034733  mov     rax, [rsi+90h]
0x18003473a  mov     ecx, [rax]
0x18003473c  cmp     ecx, 1
0x18003473f  jg      loc_180034A25
0x180034745  mov     rcx, [rbp+newString]; string
0x180034749  lea     rdx, [rbp+length]; length
0x18003474d  mov     [rbp+length], 0
0x180034754  call    cs:__imp_WindowsGetStringRawBuffer
0x18003475a  mov     r15d, [rbp+length]
0x18003475e  xor     edi, edi
0x180034760  mov     r13, rax
0x180034763  mov     eax, 811C9DC5h
0x180034768  mov     [rbp+arg_0], eax
0x18003476b  mov     r14d, eax
0x18003476e  test    r15, r15
0x180034771  jz      short loc_1800347A2
0x180034773  movzx   ecx, word ptr [r13+rdi*2+0]; Source
0x180034779  call    cs:__imp_RtlUpcaseUnicodeChar
0x18003477f  movzx   edx, ax
0x180034782  inc     rdi
0x180034785  movzx   eax, dl
0x180034788  xor     eax, r14d
0x18003478b  shr     edx, 8
0x18003478e  imul    ecx, eax, 1000193h
0x180034794  xor     ecx, edx
0x180034796  imul    r14d, ecx, 1000193h
0x18003479d  cmp     rdi, r15
0x1800347a0  jb      short loc_180034773
0x1800347a2  mov     rdi, [rsi+30h]
0x1800347a6  test    rdi, rdi
0x1800347a9  jz      short loc_1800347C0
0x1800347ab  xor     edx, edx
0x1800347ad  mov     eax, r14d
0x1800347b0  div     dword ptr [rsi+40h]
0x1800347b3  mov     rdi, [rdi+rdx*8]
0x1800347b7  test    rdi, rdi
0x1800347ba  jnz     loc_180034A8C
0x1800347c0  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x1800347c8  jz      loc_180034A82
0x1800347ce  mov     rcx, [rbp+newString]; string
0x1800347d2  lea     rdx, [rbp+length]; length
0x1800347d6  mov     [rbp+length], 0
0x1800347dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800347e3  mov     r14d, [rbp+length]
0x1800347e7  xor     edi, edi
0x1800347e9  mov     r15, rax
0x1800347ec  test    r14, r14
0x1800347ef  jz      short loc_180034830
0x1800347f1  mov     r12d, 811C9DC5h
0x1800347f7  movzx   ecx, word ptr [r15+rdi*2]; Source
0x1800347fc  call    cs:__imp_RtlUpcaseUnicodeChar
0x180034802  movzx   edx, ax
0x180034805  inc     rdi
0x180034808  movzx   ecx, dl
0x18003480b  xor     ecx, r12d
0x18003480e  shr     edx, 8
0x180034811  imul    eax, ecx, 1000193h
0x180034817  xor     eax, edx
0x180034819  imul    r12d, eax, 1000193h
0x180034820  cmp     rdi, r14
0x180034823  jb      short loc_1800347F7
0x180034825  mov     [rbp+arg_0], r12d
0x180034829  lea     r12, [rsi+88h]
0x180034830  mov     ecx, [rbp+arg_0]
0x180034833  xor     edx, edx
0x180034835  mov     rdi, [rsi+30h]
0x180034839  mov     eax, ecx
0x18003483b  div     dword ptr [rsi+40h]
0x18003483e  mov     [rbp+var_1C], edx
0x180034841  test    rdi, rdi
0x180034844  jz      short loc_180034853
0x180034846  mov     rdi, [rdi+rdx*8]
0x18003484a  test    rdi, rdi
0x18003484d  jnz     loc_180034A9B
0x180034853  xor     r15d, r15d
0x180034856  lea     r13, [rsi+28h]
0x18003485a  cmp     [rsi+30h], r15
0x18003485e  jz      loc_1800349D7
0x180034864  cmp     qword ptr [rsi+70h], 0
0x180034869  jnz     short loc_1800348DE
0x18003486b  mov     ecx, [rsi+64h]
0x18003486e  mov     eax, 20h ; ' '
0x180034873  mul     rcx
0x180034876  mov     [rbp+var_8], 0
0x18003487e  test    rdx, rdx
0x180034881  jnz     loc_180034A1B
0x180034887  lea     rcx, [rax+8]; Size
0x18003488b  cmp     rcx, rax
0x18003488e  jb      loc_180034A1B
0x180034894  call    cs:__imp_malloc
0x18003489a  test    rax, rax
0x18003489d  jz      loc_180034A1B
0x1800348a3  mov     rcx, [rsi+68h]
0x1800348a7  mov     [rsi+68h], rax
0x1800348ab  mov     r8d, [rsi+64h]
0x1800348af  dec     r8d
0x1800348b2  mov     [rax], rcx
0x1800348b5  mov     edx, r8d
0x1800348b8  shl     rdx, 5
0x1800348bc  add     rdx, 8
0x1800348c0  add     rdx, rax
0x1800348c3  test    r8d, r8d
0x1800348c6  js      short loc_1800348DE
0x1800348c8  mov     rax, [rsi+70h]
0x1800348cc  mov     [rdx+10h], rax
0x1800348d0  mov     [rsi+70h], rdx
0x1800348d4  sub     rdx, 20h ; ' '
0x1800348d8  sub     r8d, 1
0x1800348dc  jns     short loc_1800348C8
0x1800348de  mov     r14, [rsi+70h]
0x1800348e2  test    r14, r14
0x1800348e5  jz      short loc_180034936
0x1800348e7  mov     rax, [r14+10h]
0x1800348eb  mov     r8d, [rbp+var_1C]
0x1800348ef  mov     [rsi+70h], rax
0x1800348f3  mov     rax, [rbp+newString]
0x1800348f7  mov     [r14], rax
0x1800348fa  mov     eax, [rbp+arg_0]
0x1800348fd  mov     [r14+18h], eax
0x180034901  inc     qword ptr [rsi+38h]
0x180034905  mov     rax, [rsi+30h]
0x180034909  mov     rdx, [rax+r8*8]
0x18003490d  mov     [r14+10h], rdx
0x180034911  mov     rax, [rsi+30h]
0x180034915  mov     [rax+r8*8], r14
0x180034919  mov     rdx, [rsi+38h]
0x18003491d  cmp     rdx, [rsi+50h]
0x180034921  ja      loc_180034AA9
0x180034927  mov     r15, r14
0x18003492a  mov     rax, [rbp+string]
0x18003492e  mov     [r15+8], rax
0x180034932  xor     edi, edi
0x180034934  jmp     short loc_180034943
0x180034936  mov     edi, 8000FFFFh
0x18003493b  test    edi, edi
0x18003493d  jns     short loc_18003492A
0x18003493f  test    edi, edi
0x180034941  js      short loc_180034953
0x180034943  mov     [rbp+newString], 0
0x18003494b  mov     [rbp+string], 0
0x180034953  mov     r14, [rbp+arg_18]
0x180034957  cmp     dword ptr [rsi+80h], 1
0x18003495e  jz      loc_180034B2C
0x180034964  mov     rcx, r12; SRWLock
0x180034967  call    cs:__imp_ReleaseSRWLockExclusive
0x18003496d  mov     r15, [rbp+arg_8]
0x180034971  mov     rcx, rbx; string
0x180034974  call    cs:__imp_WindowsDeleteString
0x18003497a  mov     rcx, [rbp+string]; string
0x18003497e  call    cs:__imp_WindowsDeleteString
0x180034984  test    edi, edi
0x180034986  jns     short loc_1800349AC
0x180034988  mov     rcx, [rbp+newString]; string
0x18003498c  call    cs:__imp_WindowsDeleteString
0x180034992  mov     rbx, [rsp+50h+arg_10]
0x18003499a  mov     eax, edi
0x18003499c  add     rsp, 50h
0x1800349a0  pop     r15
0x1800349a2  pop     r14
0x1800349a4  pop     r13
0x1800349a6  pop     r12
0x1800349a8  pop     rdi
0x1800349a9  pop     rsi
0x1800349aa  pop     rbp
0x1800349ab  retn
0x1800349ac  mov     al, [r14]
0x1800349af  mov     r8, rsi
0x1800349b2  movzx   edx, byte ptr [rsi+99h]
0x1800349b9  neg     al
0x1800349bb  movzx   ecx, byte ptr [rbp+arg_18]
0x1800349bf  sbb     r9d, r9d
0x1800349c2  mov     [rsp+50h+var_30], r15
0x1800349c7  and     r9d, 2
0x1800349cb  inc     r9d
0x1800349ce  call    ?RaiseEvent@?$HashMapOptions@U_GUID@@PEAVComProxyStubRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(...)
0x1800349d3  mov     edi, eax
0x1800349d5  jmp     short loc_180034988
0x1800349d7  mov     edi, [rsi+40h]
0x1800349da  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800349e1  mov     eax, 8
0x1800349e6  mul     rdi
0x1800349e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800349f0  cmovb   rax, rcx
0x1800349f4  mov     rcx, rax; unsigned __int64
0x1800349f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800349fc  mov     [rsi+30h], rax
0x180034a00  test    rax, rax
0x180034a03  jz      loc_180034B65
0x180034a09  cmp     edi, 1FFFFFFFh
0x180034a0f  jbe     short loc_180034A60
0x180034a11  mov     edi, 8000FFFFh
0x180034a16  jmp     loc_18003493F
0x180034a1b  mov     edi, 8007000Eh
0x180034a20  jmp     loc_18003493B
0x180034a25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034a2c  mov     ecx, 4; unsigned __int64
0x180034a31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034a36  mov     rdi, rax
0x180034a39  test    rax, rax
0x180034a3c  jz      loc_180034745
0x180034a42  mov     dword ptr [rax], 1
0x180034a48  mov     rcx, [rsi+90h]; this
0x180034a4f  call    ?Release@Tag@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::Tag::Release(void)
0x180034a54  mov     [rsi+90h], rdi
0x180034a5b  jmp     loc_180034745
0x180034a60  lea     r8, ds:0[rdi*8]; Size
0x180034a68  xor     edx, edx; Val
0x180034a6a  mov     rcx, rax; void *
0x180034a6d  call    memset_0
0x180034a72  mov     rcx, r13
0x180034a75  mov     [rsi+40h], edi
0x180034a78  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAUIComTypeLibRegistration@DEH@OSIntegration@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVComTypeLibRegistration@DEH@OSIntegration@@@9Collections@Foundation@Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@9Collections@Foundation@Windows@@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIComTypeLibRegistration@DEH@OSIntegration@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds(void)
0x180034a7d  jmp     loc_180034864
0x180034a82  mov     edi, 8007000Eh
0x180034a87  jmp     loc_180034953
0x180034a8c  cmp     [rdi+18h], r14d
0x180034a90  jz      short loc_180034AD4
0x180034a92  mov     rdi, [rdi+10h]
0x180034a96  jmp     loc_1800347B7
0x180034a9b  cmp     [rdi+18h], ecx
0x180034a9e  jz      short loc_180034B0F
0x180034aa0  mov     rdi, [rdi+10h]
0x180034aa4  jmp     loc_18003484A
0x180034aa9  cmp     dword ptr [rsi+60h], 0
0x180034aad  jnz     loc_180034927
0x180034ab3  mov     rcx, r13
0x180034ab6  call    ?PickSize@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEBAI_K@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(unsigned __int64)
0x180034abb  mov     edx, eax
0x180034abd  mov     rcx, r13
0x180034ac0  call    ?Rehash@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJI@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(uint)
0x180034ac5  mov     edi, eax
0x180034ac7  test    eax, eax
0x180034ac9  js      loc_18003493B
0x180034acf  jmp     loc_180034927
0x180034ad4  mov     rdx, [rbp+newString]; HSTRING
0x180034ad8  mov     rcx, [rdi]; HSTRING
0x180034adb  call    ?RegistryNamesAreEqual@@YA_NPEAUHSTRING__@@0@Z; RegistryNamesAreEqual(HSTRING__ *,HSTRING__ *)
0x180034ae0  test    al, al
0x180034ae2  jz      short loc_180034A92
0x180034ae4  mov     rbx, [rdi+8]
0x180034ae8  xor     ecx, ecx; string
0x180034aea  call    cs:__imp_WindowsDeleteString
0x180034af0  mov     rax, [rbp+string]
0x180034af4  mov     r14, [rbp+arg_18]
0x180034af8  mov     [rdi+8], rax
0x180034afc  xor     edi, edi
0x180034afe  mov     [rbp+string], 0
0x180034b06  mov     byte ptr [r14], 1
0x180034b0a  jmp     loc_180034957
0x180034b0f  mov     rdx, [rbp+newString]; HSTRING
0x180034b13  mov     rcx, [rdi]; HSTRING
0x180034b16  call    ?RegistryNamesAreEqual@@YA_NPEAUHSTRING__@@0@Z; RegistryNamesAreEqual(HSTRING__ *,HSTRING__ *)
0x180034b1b  test    al, al
0x180034b1d  jz      short loc_180034B39
0x180034b1f  mov     rax, [rbp+string]
  ... truncated ...
```
