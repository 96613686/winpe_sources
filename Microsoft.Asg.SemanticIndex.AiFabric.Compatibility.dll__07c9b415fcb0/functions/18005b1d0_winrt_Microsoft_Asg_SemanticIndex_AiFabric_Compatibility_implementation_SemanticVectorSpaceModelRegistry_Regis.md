# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::RegisterTextEmbeddingsModelFactory(winrt::guid,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory)

- ea: `0x18005b1d0`
- end: `0x18005b790`
- name: `?RegisterTextEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AURegisterEmbeddingModelFactoryResult@345678@Uguid@8@UITextEmbeddingsModelFactory@345678@@Z`
- size: `1472`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005bde0`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180004bf0`
- `0x180004f00`
- `0x180007a00`
- `0x18000d230`
- `0x180010dd0`
- `0x18002bb20`
- `0x180057ba0`
- `0x18005a220`
- `0x18005b100`
- `0x18005b1d0`
- `0x180078d00`
- `0x180078d10`
- `0x18007c680`
- `0x180089ae0`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801f7110`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x180242120`

## string_xrefs

- `0x18005b2f2`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18005b6ff`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::RegisterTextEmbeddingsModelFactory(
        _QWORD *a1,
        _OWORD *a2,
        _QWORD *a3)
{
  const struct asg::SemanticRegistry::VectorSpaceRegistry *v6; // rax
  _QWORD *v7; // rax
  volatile signed __int32 *v8; // rbx
  __int64 (__fastcall ***v9)(_QWORD, __int64 *, LPVOID *); // rcx
  int v10; // eax
  void *v11; // rcx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, __int64 *, LPVOID *); // rcx
  int v14; // eax
  void *v15; // rcx
  int v16; // eax
  volatile signed __int32 *v17; // rbx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v20; // rsi
  __int64 (__fastcall ***v21)(_QWORD, __int64 *, LPVOID *); // rbx
  struct _Mtx_internal_imp_t *v22; // rax
  __int128 *v23; // rbx
  _QWORD *v24; // rax
  __int128 v25; // xmm1
  char *v26; // rcx
  __int128 *v27; // rbx
  LPVOID v29; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v30; // [rsp+28h] [rbp-D8h]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  char v32; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v34; // [rsp+58h] [rbp-A8h]
  char *v35; // [rsp+68h] [rbp-98h] BYREF
  const char *v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  _OWORD pExceptionObject[2]; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v41; // [rsp+C8h] [rbp-38h]
  __int128 v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+F0h] [rbp-10h]
  _BYTE v44[32]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v45; // [rsp+118h] [rbp+18h]

  v29 = a1;
  v30 = a3;
  if ( !*a3 )
  {
    LODWORD(v35) = 679;
    v36 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v37 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)&lpMem, L"factory");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)&lpMem,
      (const struct winrt::impl::slim_source_location *)&v35);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v6 = asg::SemanticRegistry::VectorSpaceRegistry::Instance();
  pExceptionObject[0] = *a2;
  asg::SemanticRegistry::VectorSpaceRegistry::TryGetVectorSpace(v6, &v33, pExceptionObject);
  if ( !v33 )
  {
    v7 = operator new(0x48u);
    v30 = v7;
    v7[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v7[1] = 1;
    *((_DWORD *)v7 + 6) = 101;
    *((_DWORD *)v7 + 7) = -2147467259;
    *((_OWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 3) = 0;
    *((_DWORD *)v7 + 16) = 0;
    *v7 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable';
    *a1 = v7 + 2;
    v8 = v34;
    if ( !v34 )
      goto LABEL_37;
    goto LABEL_34;
  }
  v29 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))*a3;
  if ( *a3 )
  {
    lpMem = 0;
    v10 = (**v9)(
            v9,
            winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>,
            &lpMem);
    v11 = lpMem;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  lpMem = v11;
  LODWORD(v35) = 510;
  v36 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v37 = 0;
  if ( v10 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v10, &v35);
  }
  LODWORD(v35) = 512;
  v36 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v37 = 0;
  v12 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v11 + 48LL))(v11, &v29);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, &v35);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&lpMem);
  v39 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::LookupSourceNameEnum(&v29);
  lpMem = 0;
  v13 = (__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))*a3;
  if ( *a3 )
  {
    v29 = 0;
    v14 = (**v13)(
            v13,
            winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>,
            &v29);
    v15 = v29;
  }
  else
  {
    v14 = 0;
    v15 = 0;
  }
  v29 = v15;
  LODWORD(v35) = 528;
  v36 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v37 = 0;
  if ( v14 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v14, &v35);
  }
  LODWORD(v35) = 530;
  v36 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v37 = 0;
  v16 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v15 + 56LL))(v15, &lpMem);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, &v35);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v29);
  v17 = (volatile signed __int32 *)lpMem;
  v29 = lpMem;
  if ( lpMem )
  {
    *(_QWORD *)&pExceptionObject[0] = *((_QWORD *)lpMem + 2);
    *((_QWORD *)&pExceptionObject[0] + 1) = *((unsigned int *)lpMem + 1);
  }
  else
  {
    *(_QWORD *)&pExceptionObject[0] = &String;
    *((_QWORD *)&pExceptionObject[0] + 1) = 0;
  }
  asg::wideToUtf8(v40, pExceptionObject);
  v41 = *(_OWORD *)(v33 + 8);
  if ( v17 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  v42 = *(_OWORD *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(
                     a3,
                     &v35);
  v43 = v39;
  std::string::string(v44, v40);
  v45 = v41;
  lpMem = qword_18033C3C0;
  v32 = 0;
  if ( Mtx_lock((_Mtx_t)qword_18033C3C0) )
    std::_Throw_Cpp_error(5);
  if ( dword_18033C40C == 0x7FFFFFFF )
  {
    dword_18033C40C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v32 = 1;
  v20 = (volatile signed __int32 *)operator new(0x20u);
  v29 = (LPVOID)v20;
  *(_OWORD *)v20 = 0;
  *((_DWORD *)v20 + 2) = 1;
  *((_DWORD *)v20 + 3) = 1;
  *(_QWORD *)v20 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextFactoryWrapper>::`vftable';
  v21 = (__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))*a3;
  if ( *a3 )
    ((void (__fastcall *)(_QWORD))(*v21)[1])(*a3);
  *((_QWORD *)v20 + 2) = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextFactoryWrapper::`vftable';
  *((_QWORD *)v20 + 3) = v21;
  v35 = (char *)(v20 + 4);
  v36 = (const char *)v20;
  v22 = asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance();
  pExceptionObject[0] = 0;
  _InterlockedIncrement(v20 + 2);
  *(_QWORD *)&pExceptionObject[0] = v20 + 4;
  *((_QWORD *)&pExceptionObject[0] + 1) = v20;
  if ( (unsigned __int8)asg::SemanticPipelines::ModelAccessorFactoryRegistry::RegisterModelAccessorFactory(v22) )
  {
    v27 = (__int128 *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(
                        a3,
                        pExceptionObject);
    v24 = operator new(0x48u);
    v30 = v24;
    v25 = *v27;
    v26 = (char *)(v24 + 2);
    v24[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v24[1] = 1;
    v24[3] = 0;
  }
  else
  {
    v23 = (__int128 *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(
                        a3,
                        pExceptionObject);
    v24 = operator new(0x48u);
    v30 = v24;
    v25 = *v23;
    v26 = (char *)(v24 + 2);
    v24[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v24[1] = 1;
    v24[3] = 1;
  }
  *((_DWORD *)v24 + 16) = 0;
  *((_OWORD *)v24 + 2) = *a2;
  *((_OWORD *)v24 + 3) = v25;
  *v24 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable';
  *a1 = v26;
  if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v20)((void *)v20);
    if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  }
  Mtx_unlock((_Mtx_t)qword_18033C3C0);
  std::basic_string<char8_t>::_Tidy_deallocate(v44);
  std::basic_string<char8_t>::_Tidy_deallocate(v40);
  v8 = v34;
  if ( v34 )
  {
LABEL_34:
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
LABEL_37:
  if ( *a3 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a3);
  return a1;
}

```

## disassembly

```asm
0x18005b1d0  mov     [rsp-8+arg_18], rbx
0x18005b1d5  push    rbp
0x18005b1d6  push    rsi
0x18005b1d7  push    rdi
0x18005b1d8  push    r12
0x18005b1da  push    r13
0x18005b1dc  push    r14
0x18005b1de  push    r15
0x18005b1e0  lea     rbp, [rsp-40h]
0x18005b1e5  sub     rsp, 140h
0x18005b1ec  mov     rax, cs:__security_cookie
0x18005b1f3  xor     rax, rsp
0x18005b1f6  mov     [rbp+70h+var_40], rax
0x18005b1fa  mov     r14, r8
0x18005b1fd  mov     r13, rdx
0x18005b200  mov     r15, rcx
0x18005b203  mov     [rsp+170h+var_150], rcx
0x18005b208  mov     [rsp+170h+var_148], r8
0x18005b20d  xor     edi, edi
0x18005b20f  cmp     [r8], rdi
0x18005b212  jz      loc_18005B6F7
0x18005b218  call    ?Instance@VectorSpaceRegistry@SemanticRegistry@asg@@SAAEBV123@XZ; asg::SemanticRegistry::VectorSpaceRegistry::Instance(void)
0x18005b21d  movups  xmm0, xmmword ptr [r13+0]
0x18005b222  movaps  [rbp+70h+pExceptionObject], xmm0
0x18005b226  lea     r8, [rbp+70h+pExceptionObject]
0x18005b22a  lea     rdx, [rsp+170h+var_120]
0x18005b22f  mov     rcx, rax
0x18005b232  call    ?TryGetVectorSpace@VectorSpaceRegistry@SemanticRegistry@asg@@QEBA?AV?$shared_ptr@$$CBVVectorSpaceDescriptor@SemanticRegistry@asg@@@std@@UGuid@3@@Z; asg::SemanticRegistry::VectorSpaceRegistry::TryGetVectorSpace(asg::Guid)
0x18005b237  nop
0x18005b238  cmp     [rsp+170h+var_120], rdi
0x18005b23d  jnz     short loc_18005B2AF
0x18005b23f  mov     ecx, 48h ; 'H'; Size
0x18005b244  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b249  mov     [rsp+170h+var_148], rax
0x18005b24e  xorps   xmm1, xmm1
0x18005b251  xorps   xmm0, xmm0
0x18005b254  lea     rcx, [rax+10h]
0x18005b258  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005b25f  mov     [rcx], rdx
0x18005b262  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b269  mov     qword ptr [rax+8], 1
0x18005b271  mov     dword ptr [rax+18h], 65h ; 'e'
0x18005b278  mov     dword ptr [rax+1Ch], 80004005h
0x18005b27f  movups  xmmword ptr [rax+20h], xmm0
0x18005b283  movups  xmmword ptr [rax+30h], xmm1
0x18005b287  mov     [rax+40h], edi
0x18005b28a  lea     rdx, ??_7?$heap_implements@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable'
0x18005b291  mov     [rax], rdx
0x18005b294  mov     [r15], rcx
0x18005b297  mov     rbx, [rsp+170h+var_118]
0x18005b29c  test    rbx, rbx
0x18005b29f  jz      loc_18005B6A6
0x18005b2a5  mov     edi, 0FFFFFFFFh
0x18005b2aa  jmp     loc_18005B670
0x18005b2af  mov     [rsp+170h+var_150], rdi
0x18005b2b4  mov     rcx, [r14]
0x18005b2b7  test    rcx, rcx
0x18005b2ba  jnz     short loc_18005B2C3
0x18005b2bc  mov     eax, edi
0x18005b2be  mov     rcx, rdi
0x18005b2c1  jmp     short loc_18005B2E5
0x18005b2c3  mov     [rsp+170h+lpMem], rdi
0x18005b2c8  mov     rax, [rcx]
0x18005b2cb  lea     r8, [rsp+170h+lpMem]
0x18005b2d0  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18005b2d7  mov     rax, [rax]
0x18005b2da  call    cs:__guard_dispatch_icall_fptr
0x18005b2e0  mov     rcx, [rsp+170h+lpMem]
0x18005b2e5  mov     [rsp+170h+lpMem], rcx
0x18005b2ea  mov     dword ptr [rsp+170h+var_108], 1FEh
0x18005b2f2  lea     rbx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18005b2f9  mov     [rsp+170h+var_100], rbx
0x18005b2fe  mov     [rsp+170h+var_F8], rdi
0x18005b303  test    eax, eax
0x18005b305  js      loc_18005B745
0x18005b30b  mov     dword ptr [rsp+170h+var_108], 200h
0x18005b313  mov     [rsp+170h+var_100], rbx
0x18005b318  mov     [rsp+170h+var_F8], rdi
0x18005b31d  mov     rax, [rcx]
0x18005b320  lea     rdx, [rsp+170h+var_150]
0x18005b325  mov     rax, [rax+30h]
0x18005b329  call    cs:__guard_dispatch_icall_fptr
0x18005b32f  test    eax, eax
0x18005b331  js      loc_18005B755
0x18005b337  lea     rcx, [rsp+170h+lpMem]
0x18005b33c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b341  mov     rax, [rsp+170h+var_150]
0x18005b346  mov     [rsp+170h+var_150], rax
0x18005b34b  lea     rcx, [rsp+170h+var_150]
0x18005b350  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__LookupSourceNameEnum
0x18005b355  mov     [rbp+70h+var_D0], eax
0x18005b358  mov     [rsp+170h+lpMem], rdi
0x18005b35d  mov     rcx, [r14]
0x18005b360  test    rcx, rcx
0x18005b363  jnz     short loc_18005B36C
0x18005b365  mov     eax, edi
0x18005b367  mov     rcx, rdi
0x18005b36a  jmp     short loc_18005B38E
0x18005b36c  mov     [rsp+170h+var_150], rdi
0x18005b371  mov     rax, [rcx]
0x18005b374  lea     r8, [rsp+170h+var_150]
0x18005b379  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18005b380  mov     rax, [rax]
0x18005b383  call    cs:__guard_dispatch_icall_fptr
0x18005b389  mov     rcx, [rsp+170h+var_150]
0x18005b38e  mov     [rsp+170h+var_150], rcx
0x18005b393  mov     dword ptr [rsp+170h+var_108], 210h
0x18005b39b  mov     [rsp+170h+var_100], rbx
0x18005b3a0  mov     [rsp+170h+var_F8], rdi
0x18005b3a5  test    eax, eax
0x18005b3a7  js      loc_18005B765
0x18005b3ad  mov     dword ptr [rsp+170h+var_108], 212h
0x18005b3b5  mov     [rsp+170h+var_100], rbx
0x18005b3ba  mov     [rsp+170h+var_F8], rdi
0x18005b3bf  mov     rax, [rcx]
0x18005b3c2  lea     rdx, [rsp+170h+lpMem]
0x18005b3c7  mov     rax, [rax+38h]
0x18005b3cb  call    cs:__guard_dispatch_icall_fptr
0x18005b3d1  test    eax, eax
0x18005b3d3  js      loc_18005B775
0x18005b3d9  lea     rcx, [rsp+170h+var_150]
0x18005b3de  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b3e3  mov     rbx, [rsp+170h+lpMem]
0x18005b3e8  mov     [rsp+170h+var_150], rbx
0x18005b3ed  test    rbx, rbx
0x18005b3f0  jz      short loc_18005B403
0x18005b3f2  mov     rax, [rbx+10h]
0x18005b3f6  mov     qword ptr [rbp+70h+pExceptionObject], rax
0x18005b3fa  mov     eax, [rbx+4]
0x18005b3fd  mov     qword ptr [rbp+70h+pExceptionObject+8], rax
0x18005b401  jmp     short loc_18005B412
0x18005b403  lea     rax, String
0x18005b40a  mov     qword ptr [rbp+70h+pExceptionObject], rax
0x18005b40e  mov     qword ptr [rbp+70h+pExceptionObject+8], rdi
0x18005b412  movaps  xmm0, [rbp+70h+pExceptionObject]
0x18005b416  movdqa  [rbp+70h+pExceptionObject], xmm0
0x18005b41b  lea     rdx, [rbp+70h+pExceptionObject]
0x18005b41f  lea     rcx, [rbp+70h+var_C8]
0x18005b423  call    ?wideToUtf8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::wideToUtf8(std::wstring_view)
0x18005b428  mov     rax, [rsp+170h+var_120]
0x18005b42d  movups  xmm0, xmmword ptr [rax+8]
0x18005b431  movups  [rbp+70h+var_A8], xmm0
0x18005b435  mov     edi, 0FFFFFFFFh
0x18005b43a  test    rbx, rbx
0x18005b43d  jz      short loc_18005B463
0x18005b43f  mov     eax, edi
0x18005b441  lock xadd [rbx+18h], eax
0x18005b446  sub     eax, 1
0x18005b449  jnz     loc_18005B5A6
0x18005b44f  call    WINRT_IMPL_GetProcessHeap
0x18005b454  mov     rcx, rax; hHeap
0x18005b457  mov     r8, [rsp+170h+lpMem]; lpMem
0x18005b45c  xor     edx, edx; dwFlags
0x18005b45e  call    WINRT_IMPL_HeapFree
0x18005b463  lea     rdx, [rsp+170h+var_108]
0x18005b468  mov     rcx, r14
0x18005b46b  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005b470  movups  xmm0, xmmword ptr [rax]
0x18005b473  movaps  [rbp+70h+var_90], xmm0
0x18005b477  mov     eax, [rbp+70h+var_D0]
0x18005b47a  mov     [rbp+70h+var_80], eax
0x18005b47d  lea     rdx, [rbp+70h+var_C8]
0x18005b481  lea     rcx, [rbp+70h+var_78]
0x18005b485  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18005b48a  movups  xmm0, [rbp+70h+var_A8]
0x18005b48e  movups  [rbp+70h+var_58], xmm0
0x18005b492  lea     rax, qword_18033C3C0
0x18005b499  mov     [rsp+170h+lpMem], rax
0x18005b49e  mov     [rsp+170h+var_138], 0
0x18005b4a3  mov     rcx, rax; _Mtx_t
0x18005b4a6  call    _Mtx_lock
0x18005b4ab  test    eax, eax
0x18005b4ad  jnz     loc_18005B785
0x18005b4b3  mov     eax, cs:dword_18033C40C
0x18005b4b9  cmp     eax, 7FFFFFFFh
0x18005b4be  jz      loc_18005B6DE
0x18005b4c4  mov     [rsp+170h+var_138], 1
0x18005b4c9  mov     ecx, 20h ; ' '; Size
0x18005b4ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b4d3  mov     rsi, rax
0x18005b4d6  mov     [rsp+170h+var_150], rax
0x18005b4db  xorps   xmm0, xmm0
0x18005b4de  movups  xmmword ptr [rax], xmm0
0x18005b4e1  mov     dword ptr [rax+8], 1
0x18005b4e8  mov     dword ptr [rax+0Ch], 1
0x18005b4ef  lea     rax, ??_7?$_Ref_count_obj2@UTextFactoryWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextFactoryWrapper>::`vftable'
0x18005b4f6  mov     [rsi], rax
0x18005b4f9  lea     r12, [rsi+10h]
0x18005b4fd  mov     rbx, [r14]
0x18005b500  test    rbx, rbx
0x18005b503  jz      short loc_18005B515
0x18005b505  mov     rax, [rbx]
0x18005b508  mov     rcx, rbx
0x18005b50b  mov     rax, [rax+8]
0x18005b50f  call    cs:__guard_dispatch_icall_fptr
0x18005b515  lea     rax, ??_7TextFactoryWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextFactoryWrapper::`vftable'
0x18005b51c  mov     [r12], rax
0x18005b520  mov     [r12+8], rbx
0x18005b525  mov     [rsp+170h+var_108], r12
0x18005b52a  mov     [rsp+170h+var_100], rsi
0x18005b52f  call    ?Instance@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@SAAEAU123@XZ; asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance(void)
0x18005b534  xorps   xmm0, xmm0
0x18005b537  movdqu  [rbp+70h+pExceptionObject], xmm0
0x18005b53c  lock inc dword ptr [rsi+8]
0x18005b540  mov     qword ptr [rbp+70h+pExceptionObject], r12
0x18005b544  mov     qword ptr [rbp+70h+pExceptionObject+8], rsi
0x18005b548  lea     r8, [rbp+70h+pExceptionObject]
0x18005b54c  lea     rdx, [rbp+70h+var_90]
0x18005b550  mov     rcx, rax; _Mtx_t
0x18005b553  call    ?RegisterModelAccessorFactory@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@QEAA_NAEBUModelVersionKey@23@V?$shared_ptr@UITextModelAccessorFactory@SemanticPipelines@asg@@@std@@_N@Z; asg::SemanticPipelines::ModelAccessorFactoryRegistry::RegisterModelAccessorFactory(asg::SemanticPipelines::ModelVersionKey const &,std::shared_ptr<asg::SemanticPipelines::ITextModelAccessorFactory>,bool)
0x18005b558  lea     rdx, [rbp+70h+pExceptionObject]
0x18005b55c  mov     rcx, r14
0x18005b55f  test    al, al
0x18005b561  jnz     short loc_18005B5B3
0x18005b563  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005b568  mov     rbx, rax
0x18005b56b  mov     ecx, 48h ; 'H'; Size
0x18005b570  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b575  mov     [rsp+170h+var_148], rax
0x18005b57a  movups  xmm1, xmmword ptr [rbx]
0x18005b57d  lea     rcx, [rax+10h]
0x18005b581  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005b588  mov     [rcx], rdx
0x18005b58b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b592  mov     qword ptr [rax+8], 1
0x18005b59a  mov     qword ptr [rax+18h], 1
0x18005b5a2  xor     edx, edx
0x18005b5a4  jmp     short loc_18005B5F0
0x18005b5a6  test    eax, eax
0x18005b5a8  js      loc_18005B6F1
0x18005b5ae  jmp     loc_18005B463
0x18005b5b3  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005b5b8  mov     rbx, rax
0x18005b5bb  mov     ecx, 48h ; 'H'; Size
0x18005b5c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b5c5  mov     [rsp+170h+var_148], rax
0x18005b5ca  movups  xmm1, xmmword ptr [rbx]
0x18005b5cd  lea     rcx, [rax+10h]
0x18005b5d1  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005b5d8  mov     [rcx], rdx
0x18005b5db  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b5e2  mov     qword ptr [rax+8], 1
0x18005b5ea  xor     edx, edx
0x18005b5ec  mov     [rax+18h], rdx
0x18005b5f0  mov     [rax+40h], edx
0x18005b5f3  movups  xmm0, xmmword ptr [r13+0]
0x18005b5f8  lea     rdx, ??_7?$heap_implements@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable'
0x18005b5ff  movups  xmmword ptr [rax+20h], xmm0
0x18005b603  movups  xmmword ptr [rax+30h], xmm1
0x18005b607  mov     [rax], rdx
0x18005b60a  mov     [r15], rcx
0x18005b60d  mov     eax, edi
0x18005b60f  lock xadd [rsi+8], eax
0x18005b614  cmp     eax, 1
0x18005b617  jnz     short loc_18005B645
0x18005b619  mov     rax, [rsi]
0x18005b61c  mov     rcx, rsi
0x18005b61f  mov     rax, [rax]
0x18005b622  call    cs:__guard_dispatch_icall_fptr
0x18005b628  mov     eax, edi
0x18005b62a  lock xadd [rsi+0Ch], eax
0x18005b62f  cmp     eax, 1
0x18005b632  jnz     short loc_18005B645
0x18005b634  mov     rax, [rsi]
0x18005b637  mov     rcx, rsi
0x18005b63a  mov     rax, [rax+8]
0x18005b63e  call    cs:__guard_dispatch_icall_fptr
0x18005b644  nop
0x18005b645  lea     rcx, qword_18033C3C0; _Mtx_t
0x18005b64c  call    _Mtx_unlock
0x18005b651  nop
0x18005b652  lea     rcx, [rbp+70h+var_78]; void *
0x18005b656  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
0x18005b65b  nop
0x18005b65c  lea     rcx, [rbp+70h+var_C8]; void *
0x18005b660  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
0x18005b665  nop
0x18005b666  mov     rbx, [rsp+170h+var_118]
0x18005b66b  test    rbx, rbx
0x18005b66e  jz      short loc_18005B6A6
0x18005b670  mov     eax, edi
0x18005b672  lock xadd [rbx+8], eax
0x18005b677  cmp     eax, 1
0x18005b67a  jnz     short loc_18005B6A6
0x18005b67c  mov     rax, [rbx]
0x18005b67f  mov     rcx, rbx
0x18005b682  mov     rax, [rax]
0x18005b685  call    cs:__guard_dispatch_icall_fptr
0x18005b68b  lock xadd [rbx+0Ch], edi
0x18005b690  cmp     edi, 1
0x18005b693  jnz     short loc_18005B6A6
0x18005b695  mov     rax, [rbx]
0x18005b698  mov     rcx, rbx
0x18005b69b  mov     rax, [rax+8]
0x18005b69f  call    cs:__guard_dispatch_icall_fptr
0x18005b6a5  nop
0x18005b6a6  cmp     qword ptr [r14], 0
0x18005b6aa  jz      short loc_18005B6B4
0x18005b6ac  mov     rcx, r14
0x18005b6af  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
  ... truncated ...
```
