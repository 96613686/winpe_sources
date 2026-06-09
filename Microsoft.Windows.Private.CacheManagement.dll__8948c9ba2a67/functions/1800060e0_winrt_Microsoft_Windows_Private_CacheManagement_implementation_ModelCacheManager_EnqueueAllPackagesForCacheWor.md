# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(std::optional<winrt::hstring>,bool)

- ea: `0x1800060e0`
- end: `0x18000646a`
- name: `?EnqueueAllPackagesForCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXV?$optional@Uhstring@winrt@@@std@@_N@Z`
- size: `906`
- prototype: `int __fastcall(__int64, __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009410`
- `0x1800094d0`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180004c30`
- `0x1800060e0`
- `0x180006470`
- `0x1800127e0`
- `0x180016298`
- `0x18001629e`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000640d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006416`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000640d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006416`

## pseudocode

```c
int __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3)
{
  int v4; // eax
  void *v5; // rbx
  int v6; // edi
  int v7; // edi
  int v8; // eax
  __int64 v9; // r15
  int v10; // edi
  void *v11; // rbx
  unsigned int v12; // r14d
  int result; // eax
  int v14; // r13d
  int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  struct winrt::impl::hstring_header **v19; // rbx
  int v20; // edi
  int v21; // eax
  struct winrt::impl::hstring_header **v22; // rsi
  int v23; // edi
  int v24; // eax
  struct winrt::impl::hstring_header *v25; // rdx
  HANDLE ProcessHeap; // rax
  winrt::impl *v27; // rbx
  signed __int32 v28; // esi
  HANDLE v29; // rax
  struct winrt::impl::hstring_header **v31; // [rsp+28h] [rbp-51h] BYREF
  struct winrt::impl::hstring_header **v32; // [rsp+30h] [rbp-49h] BYREF
  __int64 v33; // [rsp+38h] [rbp-41h]
  struct winrt::impl::hstring_header *v34; // [rsp+40h] [rbp-39h] BYREF
  char v35; // [rsp+48h] [rbp-31h]
  struct winrt::impl::hstring_header **v36; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v37[2]; // [rsp+68h] [rbp-11h] BYREF
  void *v38; // [rsp+78h] [rbp-1h] BYREF
  int v39; // [rsp+80h] [rbp+7h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+Fh] BYREF
  __int64 *v41; // [rsp+90h] [rbp+17h] BYREF

  v33 = a1;
  v37[1] = a2;
  LODWORD(v36) = 0;
  v34 = (struct winrt::impl::hstring_header *)qword_18002E880;
  v37[0] = &v34;
  v41 = &qword_18002E748;
  _InterlockedIncrement64(&qword_18002E748);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> )
  {
    v37[0] = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, struct winrt::impl::hstring_header *, _QWORD *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
                                                                                            + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
           v34,
           v37);
    if ( v4 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v4);
    }
    v5 = (void *)v37[0];
    v38 = (void *)v37[0];
    v6 = 448;
    _InterlockedDecrement64(&qword_18002E748);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002E748);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::call<_lambda_cb41fde99ba74c6248b3ce76f09f9615_ &>(
      0,
      &v38,
      v37);
    v6 = 64;
    v5 = v38;
  }
  v7 = v6 | 0x20;
  v37[0] = 0;
  v8 = (*(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)v5 + 48LL))(v5, v37);
  if ( v8 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v8);
  }
  v9 = v37[0];
  v41 = (__int64 *)v37[0];
  v10 = v7 | 0x200;
  if ( v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  v11 = 0;
  v12 = 0;
  v39 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 56LL))(v9, &v39);
  if ( result < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)result);
  }
  v14 = v39;
  if ( v39 )
  {
    do
    {
      v38 = v11;
      v15 = v10 | 2;
      LODWORD(v36) = v15;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v9 + 48LL))(v9, v12, &v38);
      if ( v16 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v16);
      }
      v17 = v15 & 0xFFFFFFFC | 1;
      v36 = (struct winrt::impl::hstring_header **)v11;
      v18 = (*(__int64 (__fastcall **)(void *, struct winrt::impl::hstring_header ***))(*(_QWORD *)v38 + 72LL))(
              v38,
              &v36);
      if ( v18 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v18);
      }
      v19 = v36;
      v31 = v36;
      v20 = v17 | 4;
      v36 = 0;
      v21 = (*((__int64 (__fastcall **)(struct winrt::impl::hstring_header **, struct winrt::impl::hstring_header ***))*v31
             + 6))(
              v31,
              &v36);
      if ( v21 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v21);
      }
      v22 = v36;
      v32 = v36;
      v23 = v20 | 8;
      v36 = 0;
      v24 = (*((__int64 (__fastcall **)(struct winrt::impl::hstring_header **, struct winrt::impl::hstring_header ***))*v32
             + 12))(
              v32,
              &v36);
      if ( v24 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v24);
      }
      lpMem = v36;
      v10 = v23 | 0x10;
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
      if ( v19 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
      v31 = &v34;
      v35 = 0;
      if ( *(_BYTE *)(a2 + 8) )
      {
        v34 = winrt::impl::duplicate_hstring(*(winrt::impl **)a2, v25);
        v35 = 1;
      }
      result = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueuePackageForCacheWork(
                 v33,
                 &lpMem,
                 &v34,
                 a3);
      v11 = lpMem;
      if ( lpMem )
      {
        result = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( result )
        {
          if ( result < 0 )
            abort();
          v11 = 0;
          lpMem = 0;
          v9 = v37[0];
          v14 = v39;
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          result = WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
          v11 = 0;
          lpMem = 0;
          v9 = v37[0];
          v14 = v39;
        }
      }
      if ( v38 )
        result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
      ++v12;
    }
    while ( v12 != v14 );
  }
  if ( v9 )
    result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
  if ( *(_BYTE *)(a2 + 8) )
  {
    v27 = *(winrt::impl **)a2;
    if ( *(_QWORD *)a2 )
    {
      v28 = _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 6, 0xFFFFFFFF);
      result = v28 - 1;
      if ( v28 == 1 )
      {
        v29 = WINRT_IMPL_GetProcessHeap();
        result = WINRT_IMPL_HeapFree(v29, 0, v27);
      }
      else if ( result < 0 )
      {
        abort();
      }
      *(_QWORD *)a2 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800060e0  mov     [rsp-8+arg_18], rbx
0x1800060e5  push    rbp
0x1800060e6  push    rsi
0x1800060e7  push    rdi
0x1800060e8  push    r12
0x1800060ea  push    r13
0x1800060ec  push    r14
0x1800060ee  push    r15
0x1800060f0  lea     rbp, [rsp-27h]
0x1800060f5  sub     rsp, 0A0h
0x1800060fc  mov     rax, cs:__security_cookie
0x180006103  xor     rax, rsp
0x180006106  mov     [rbp+57h+var_38], rax
0x18000610a  mov     [rbp+57h+var_B0], r8b
0x18000610e  mov     r12, rdx
0x180006111  mov     [rbp+57h+var_98], rcx
0x180006115  mov     [rbp+57h+var_60], rdx
0x180006119  xor     esi, esi
0x18000611b  mov     dword ptr [rbp+57h+var_70], esi
0x18000611e  mov     rax, cs:qword_18002E880
0x180006125  mov     [rbp+57h+var_90], rax
0x180006129  lea     rax, [rbp+57h+var_90]
0x18000612d  mov     [rbp+57h+var_68], rax
0x180006131  lea     rax, qword_18002E748
0x180006138  mov     [rbp+57h+var_40], rax
0x18000613c  lock inc cs:qword_18002E748
0x180006144  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x18000614b  test    rcx, rcx
0x18000614e  jz      short loc_180006188
0x180006150  mov     [rbp+57h+var_68], rsi
0x180006154  mov     rax, [rcx]
0x180006157  lea     r8, [rbp+57h+var_68]
0x18000615b  mov     rdx, [rbp+57h+var_90]
0x18000615f  mov     rax, [rax+30h]
0x180006163  call    cs:__guard_dispatch_icall_fptr
0x180006169  test    eax, eax
0x18000616b  js      loc_180006428
0x180006171  mov     rbx, [rbp+57h+var_68]
0x180006175  mov     [rbp+57h+var_58], rbx
0x180006179  mov     edi, 1C0h
0x18000617e  lock dec cs:qword_18002E748
0x180006186  jmp     short loc_1800061A6
0x180006188  lock dec cs:qword_18002E748
0x180006190  lea     r8, [rbp+57h+var_68]
0x180006194  lea     rdx, [rbp+57h+var_58]
0x180006198  call    ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z
0x18000619d  mov     edi, 40h ; '@'
0x1800061a2  mov     rbx, [rbp+57h+var_58]
0x1800061a6  or      edi, 20h
0x1800061a9  mov     [rbp+57h+var_68], rsi
0x1800061ad  mov     rax, [rbx]
0x1800061b0  lea     rdx, [rbp+57h+var_68]
0x1800061b4  mov     rcx, rbx
0x1800061b7  mov     rax, [rax+30h]
0x1800061bb  call    cs:__guard_dispatch_icall_fptr
0x1800061c1  test    eax, eax
0x1800061c3  js      loc_180006433
0x1800061c9  mov     r15, [rbp+57h+var_68]
0x1800061cd  mov     [rbp+57h+var_40], r15
0x1800061d1  bts     edi, 9
0x1800061d5  test    rbx, rbx
0x1800061d8  jz      short loc_1800061E3
0x1800061da  lea     rcx, [rbp+57h+var_58]
0x1800061de  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800061e3  xor     ebx, ebx
0x1800061e5  mov     r14d, ebx
0x1800061e8  mov     [rbp+57h+var_50], ebx
0x1800061eb  mov     rax, [r15]
0x1800061ee  lea     rdx, [rbp+57h+var_50]
0x1800061f2  mov     rcx, r15
0x1800061f5  mov     rax, [rax+38h]
0x1800061f9  call    cs:__guard_dispatch_icall_fptr
0x1800061ff  test    eax, eax
0x180006201  js      loc_18000643E
0x180006207  mov     esi, 0FFFFFFFFh
0x18000620c  mov     r13d, [rbp+57h+var_50]
0x180006210  test    r13d, r13d
0x180006213  jz      loc_1800063A0
0x180006219  nop     dword ptr [rax+00000000h]
0x180006220  mov     [rbp+57h+var_58], rbx
0x180006224  or      edi, 2
0x180006227  mov     dword ptr [rbp+57h+var_70], edi
0x18000622a  mov     rax, [r15]
0x18000622d  lea     r8, [rbp+57h+var_58]
0x180006231  mov     edx, r14d
0x180006234  mov     rcx, r15
0x180006237  mov     rax, [rax+30h]
0x18000623b  call    cs:__guard_dispatch_icall_fptr
0x180006241  test    eax, eax
0x180006243  js      loc_18000641D
0x180006249  and     edi, 0FFFFFFFDh
0x18000624c  or      edi, 1
0x18000624f  mov     [rbp+57h+var_70], rbx
0x180006253  mov     rcx, [rbp+57h+var_58]
0x180006257  mov     rax, [rcx]
0x18000625a  lea     rdx, [rbp+57h+var_70]
0x18000625e  mov     rax, [rax+48h]
0x180006262  call    cs:__guard_dispatch_icall_fptr
0x180006268  test    eax, eax
0x18000626a  js      loc_18000645F
0x180006270  mov     rbx, [rbp+57h+var_70]
0x180006274  mov     [rbp+57h+var_A8], rbx
0x180006278  or      edi, 4
0x18000627b  mov     [rbp+57h+var_70], 0
0x180006283  mov     rax, [rbx]
0x180006286  lea     rdx, [rbp+57h+var_70]
0x18000628a  mov     rcx, rbx
0x18000628d  mov     rax, [rax+30h]
0x180006291  call    cs:__guard_dispatch_icall_fptr
0x180006297  test    eax, eax
0x180006299  js      loc_180006454
0x18000629f  mov     rsi, [rbp+57h+var_70]
0x1800062a3  mov     [rbp+57h+var_A0], rsi
0x1800062a7  or      edi, 8
0x1800062aa  mov     [rbp+57h+var_70], 0
0x1800062b2  mov     rax, [rsi]
0x1800062b5  lea     rdx, [rbp+57h+var_70]
0x1800062b9  mov     rcx, rsi
0x1800062bc  mov     rax, [rax+60h]
0x1800062c0  call    cs:__guard_dispatch_icall_fptr
0x1800062c6  test    eax, eax
0x1800062c8  js      loc_180006449
0x1800062ce  mov     rax, [rbp+57h+var_70]
0x1800062d2  mov     [rbp+57h+lpMem], rax
0x1800062d6  or      edi, 10h
0x1800062d9  test    rsi, rsi
0x1800062dc  jz      short loc_1800062E8
0x1800062de  lea     rcx, [rbp+57h+var_A0]
0x1800062e2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800062e7  nop
0x1800062e8  test    rbx, rbx
0x1800062eb  jz      short loc_1800062F6
0x1800062ed  lea     rcx, [rbp+57h+var_A8]
0x1800062f1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800062f6  lea     rax, [rbp+57h+var_90]
0x1800062fa  mov     [rbp+57h+var_A8], rax
0x1800062fe  mov     [rbp+57h+var_88], 0
0x180006302  cmp     byte ptr [r12+8], 0
0x180006308  jz      short loc_18000631B
0x18000630a  mov     rcx, [r12]; this
0x18000630e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180006313  mov     [rbp+57h+var_90], rax
0x180006317  mov     [rbp+57h+var_88], 1
0x18000631b  movzx   r9d, [rbp+57h+var_B0]
0x180006320  lea     r8, [rbp+57h+var_90]
0x180006324  lea     rdx, [rbp+57h+lpMem]
0x180006328  mov     rcx, [rbp+57h+var_98]
0x18000632c  call    ?EnqueuePackageForCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUhstring@7@V?$optional@Uhstring@winrt@@@std@@_N@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueuePackageForCacheWork(winrt::hstring const &,std::optional<winrt::hstring>,bool)
0x180006331  nop
0x180006332  mov     rbx, [rbp+57h+lpMem]
0x180006336  mov     esi, 0FFFFFFFFh
0x18000633b  test    rbx, rbx
0x18000633e  jz      short loc_180006384
0x180006340  mov     eax, esi
0x180006342  lock xadd [rbx+18h], eax
0x180006347  sub     eax, 1
0x18000634a  jnz     short loc_18000636E
0x18000634c  call    WINRT_IMPL_GetProcessHeap
0x180006351  mov     rcx, rax; hHeap
0x180006354  mov     r8, rbx; lpMem
0x180006357  xor     edx, edx; dwFlags
0x180006359  call    WINRT_IMPL_HeapFree
0x18000635e  xor     ebx, ebx
0x180006360  mov     [rbp+57h+lpMem], rbx
0x180006364  mov     r15, [rbp+57h+var_68]
0x180006368  mov     r13d, [rbp+57h+var_50]
0x18000636c  jmp     short loc_180006384
0x18000636e  test    eax, eax
0x180006370  js      loc_18000640D
0x180006376  xor     ebx, ebx
0x180006378  mov     [rbp+57h+lpMem], rbx
0x18000637c  mov     r15, [rbp+57h+var_68]
0x180006380  mov     r13d, [rbp+57h+var_50]
0x180006384  cmp     [rbp+57h+var_58], 0
0x180006389  jz      short loc_180006394
0x18000638b  lea     rcx, [rbp+57h+var_58]
0x18000638f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006394  inc     r14d
0x180006397  cmp     r14d, r13d
0x18000639a  jnz     loc_180006220
0x1800063a0  test    r15, r15
0x1800063a3  jz      short loc_1800063AF
0x1800063a5  lea     rcx, [rbp+57h+var_40]
0x1800063a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800063ae  nop
0x1800063af  cmp     byte ptr [r12+8], 0
0x1800063b5  jz      short loc_1800063E6
0x1800063b7  mov     rbx, [r12]
0x1800063bb  test    rbx, rbx
0x1800063be  jz      short loc_1800063E6
0x1800063c0  lock xadd [rbx+18h], esi
0x1800063c5  lea     eax, [rsi-1]
0x1800063c8  test    eax, eax
0x1800063ca  jnz     short loc_180006414
0x1800063cc  call    WINRT_IMPL_GetProcessHeap
0x1800063d1  mov     rcx, rax; hHeap
0x1800063d4  mov     r8, rbx; lpMem
0x1800063d7  xor     edx, edx; dwFlags
0x1800063d9  call    WINRT_IMPL_HeapFree
0x1800063de  mov     qword ptr [r12], 0
0x1800063e6  mov     rcx, [rbp+57h+var_38]
0x1800063ea  xor     rcx, rsp; StackCookie
0x1800063ed  call    __security_check_cookie
0x1800063f2  mov     rbx, [rsp+0D0h+arg_18]
0x1800063fa  add     rsp, 0A0h
0x180006401  pop     r15
0x180006403  pop     r14
0x180006405  pop     r13
0x180006407  pop     r12
0x180006409  pop     rdi
0x18000640a  pop     rsi
0x18000640b  pop     rbp
0x18000640c  retn
0x18000640d  call    cs:__imp_abort
0x180006414  jns     short loc_1800063DE
0x180006416  call    cs:__imp_abort
0x18000641d  lfence
0x180006420  mov     ecx, eax
0x180006422  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006428  lfence
0x18000642b  mov     ecx, eax
0x18000642d  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006433  lfence
0x180006436  mov     ecx, eax
0x180006438  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000643e  lfence
0x180006441  mov     ecx, eax
0x180006443  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006449  lfence
0x18000644c  mov     ecx, eax
0x18000644e  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006454  lfence
0x180006457  mov     ecx, eax
0x180006459  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000645f  lfence
0x180006462  mov     ecx, eax
0x180006464  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
