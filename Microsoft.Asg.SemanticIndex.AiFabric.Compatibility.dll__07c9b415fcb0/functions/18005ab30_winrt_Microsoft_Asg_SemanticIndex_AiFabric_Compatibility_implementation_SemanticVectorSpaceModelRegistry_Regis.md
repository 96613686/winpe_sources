# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::RegisterImageEmbeddingsModelFactory(winrt::guid,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory)

- ea: `0x18005ab30`
- end: `0x18005b0f2`
- name: `?RegisterImageEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AURegisterEmbeddingModelFactoryResult@345678@Uguid@8@UIImageEmbeddingsModelFactory@345678@@Z`
- size: `1474`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005be80`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180004bf0`
- `0x180004f00`
- `0x180007a00`
- `0x18000d230`
- `0x180010dd0`
- `0x18002bb20`
- `0x180057d60`
- `0x18005a220`
- `0x18005ab30`
- `0x18005b100`
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

- `0x18005ac52`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18005b061`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::RegisterImageEmbeddingsModelFactory(
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
    LODWORD(v35) = 629;
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
  *(_QWORD *)v20 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageFactoryWrapper>::`vftable';
  v21 = (__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))*a3;
  if ( *a3 )
    ((void (__fastcall *)(_QWORD))(*v21)[1])(*a3);
  *((_QWORD *)v20 + 2) = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageFactoryWrapper::`vftable';
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
  *((_OWORD *)v24 + 2) = *a2;
  *((_OWORD *)v24 + 3) = v25;
  *((_DWORD *)v24 + 16) = 1;
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
0x18005ab30  mov     [rsp-8+arg_18], rbx
0x18005ab35  push    rbp
0x18005ab36  push    rsi
0x18005ab37  push    rdi
0x18005ab38  push    r12
0x18005ab3a  push    r13
0x18005ab3c  push    r14
0x18005ab3e  push    r15
0x18005ab40  lea     rbp, [rsp-40h]
0x18005ab45  sub     rsp, 140h
0x18005ab4c  mov     rax, cs:__security_cookie
0x18005ab53  xor     rax, rsp
0x18005ab56  mov     [rbp+70h+var_40], rax
0x18005ab5a  mov     r14, r8
0x18005ab5d  mov     r13, rdx
0x18005ab60  mov     r15, rcx
0x18005ab63  mov     [rsp+170h+var_150], rcx
0x18005ab68  mov     [rsp+170h+var_148], r8
0x18005ab6d  xor     edi, edi
0x18005ab6f  cmp     [r8], rdi
0x18005ab72  jz      loc_18005B059
0x18005ab78  call    ?Instance@VectorSpaceRegistry@SemanticRegistry@asg@@SAAEBV123@XZ; asg::SemanticRegistry::VectorSpaceRegistry::Instance(void)
0x18005ab7d  movups  xmm0, xmmword ptr [r13+0]
0x18005ab82  movaps  [rbp+70h+pExceptionObject], xmm0
0x18005ab86  lea     r8, [rbp+70h+pExceptionObject]
0x18005ab8a  lea     rdx, [rsp+170h+var_120]
0x18005ab8f  mov     rcx, rax
0x18005ab92  call    ?TryGetVectorSpace@VectorSpaceRegistry@SemanticRegistry@asg@@QEBA?AV?$shared_ptr@$$CBVVectorSpaceDescriptor@SemanticRegistry@asg@@@std@@UGuid@3@@Z; asg::SemanticRegistry::VectorSpaceRegistry::TryGetVectorSpace(asg::Guid)
0x18005ab97  nop
0x18005ab98  cmp     [rsp+170h+var_120], rdi
0x18005ab9d  jnz     short loc_18005AC0F
0x18005ab9f  mov     ecx, 48h ; 'H'; Size
0x18005aba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005aba9  mov     [rsp+170h+var_148], rax
0x18005abae  xorps   xmm1, xmm1
0x18005abb1  xorps   xmm0, xmm0
0x18005abb4  lea     rcx, [rax+10h]
0x18005abb8  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005abbf  mov     [rcx], rdx
0x18005abc2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005abc9  mov     qword ptr [rax+8], 1
0x18005abd1  mov     dword ptr [rax+18h], 65h ; 'e'
0x18005abd8  mov     dword ptr [rax+1Ch], 80004005h
0x18005abdf  movups  xmmword ptr [rax+20h], xmm0
0x18005abe3  movups  xmmword ptr [rax+30h], xmm1
0x18005abe7  mov     [rax+40h], edi
0x18005abea  lea     rdx, ??_7?$heap_implements@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable'
0x18005abf1  mov     [rax], rdx
0x18005abf4  mov     [r15], rcx
0x18005abf7  mov     rbx, [rsp+170h+var_118]
0x18005abfc  test    rbx, rbx
0x18005abff  jz      loc_18005B008
0x18005ac05  mov     edi, 0FFFFFFFFh
0x18005ac0a  jmp     loc_18005AFD2
0x18005ac0f  mov     [rsp+170h+var_150], rdi
0x18005ac14  mov     rcx, [r14]
0x18005ac17  test    rcx, rcx
0x18005ac1a  jnz     short loc_18005AC23
0x18005ac1c  mov     eax, edi
0x18005ac1e  mov     rcx, rdi
0x18005ac21  jmp     short loc_18005AC45
0x18005ac23  mov     [rsp+170h+lpMem], rdi
0x18005ac28  mov     rax, [rcx]
0x18005ac2b  lea     r8, [rsp+170h+lpMem]
0x18005ac30  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18005ac37  mov     rax, [rax]
0x18005ac3a  call    cs:__guard_dispatch_icall_fptr
0x18005ac40  mov     rcx, [rsp+170h+lpMem]
0x18005ac45  mov     [rsp+170h+lpMem], rcx
0x18005ac4a  mov     dword ptr [rsp+170h+var_108], 1FEh
0x18005ac52  lea     rbx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18005ac59  mov     [rsp+170h+var_100], rbx
0x18005ac5e  mov     [rsp+170h+var_F8], rdi
0x18005ac63  test    eax, eax
0x18005ac65  js      loc_18005B0A7
0x18005ac6b  mov     dword ptr [rsp+170h+var_108], 200h
0x18005ac73  mov     [rsp+170h+var_100], rbx
0x18005ac78  mov     [rsp+170h+var_F8], rdi
0x18005ac7d  mov     rax, [rcx]
0x18005ac80  lea     rdx, [rsp+170h+var_150]
0x18005ac85  mov     rax, [rax+30h]
0x18005ac89  call    cs:__guard_dispatch_icall_fptr
0x18005ac8f  test    eax, eax
0x18005ac91  js      loc_18005B0B7
0x18005ac97  lea     rcx, [rsp+170h+lpMem]
0x18005ac9c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005aca1  mov     rax, [rsp+170h+var_150]
0x18005aca6  mov     [rsp+170h+var_150], rax
0x18005acab  lea     rcx, [rsp+170h+var_150]
0x18005acb0  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__LookupSourceNameEnum
0x18005acb5  mov     [rbp+70h+var_D0], eax
0x18005acb8  mov     [rsp+170h+lpMem], rdi
0x18005acbd  mov     rcx, [r14]
0x18005acc0  test    rcx, rcx
0x18005acc3  jnz     short loc_18005ACCC
0x18005acc5  mov     eax, edi
0x18005acc7  mov     rcx, rdi
0x18005acca  jmp     short loc_18005ACEE
0x18005accc  mov     [rsp+170h+var_150], rdi
0x18005acd1  mov     rax, [rcx]
0x18005acd4  lea     r8, [rsp+170h+var_150]
0x18005acd9  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18005ace0  mov     rax, [rax]
0x18005ace3  call    cs:__guard_dispatch_icall_fptr
0x18005ace9  mov     rcx, [rsp+170h+var_150]
0x18005acee  mov     [rsp+170h+var_150], rcx
0x18005acf3  mov     dword ptr [rsp+170h+var_108], 210h
0x18005acfb  mov     [rsp+170h+var_100], rbx
0x18005ad00  mov     [rsp+170h+var_F8], rdi
0x18005ad05  test    eax, eax
0x18005ad07  js      loc_18005B0C7
0x18005ad0d  mov     dword ptr [rsp+170h+var_108], 212h
0x18005ad15  mov     [rsp+170h+var_100], rbx
0x18005ad1a  mov     [rsp+170h+var_F8], rdi
0x18005ad1f  mov     rax, [rcx]
0x18005ad22  lea     rdx, [rsp+170h+lpMem]
0x18005ad27  mov     rax, [rax+38h]
0x18005ad2b  call    cs:__guard_dispatch_icall_fptr
0x18005ad31  test    eax, eax
0x18005ad33  js      loc_18005B0D7
0x18005ad39  lea     rcx, [rsp+170h+var_150]
0x18005ad3e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005ad43  mov     rbx, [rsp+170h+lpMem]
0x18005ad48  mov     [rsp+170h+var_150], rbx
0x18005ad4d  test    rbx, rbx
0x18005ad50  jz      short loc_18005AD63
0x18005ad52  mov     rax, [rbx+10h]
0x18005ad56  mov     qword ptr [rbp+70h+pExceptionObject], rax
0x18005ad5a  mov     eax, [rbx+4]
0x18005ad5d  mov     qword ptr [rbp+70h+pExceptionObject+8], rax
0x18005ad61  jmp     short loc_18005AD72
0x18005ad63  lea     rax, String
0x18005ad6a  mov     qword ptr [rbp+70h+pExceptionObject], rax
0x18005ad6e  mov     qword ptr [rbp+70h+pExceptionObject+8], rdi
0x18005ad72  movaps  xmm0, [rbp+70h+pExceptionObject]
0x18005ad76  movdqa  [rbp+70h+pExceptionObject], xmm0
0x18005ad7b  lea     rdx, [rbp+70h+pExceptionObject]
0x18005ad7f  lea     rcx, [rbp+70h+var_C8]
0x18005ad83  call    ?wideToUtf8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::wideToUtf8(std::wstring_view)
0x18005ad88  mov     rax, [rsp+170h+var_120]
0x18005ad8d  movups  xmm0, xmmword ptr [rax+8]
0x18005ad91  movups  [rbp+70h+var_A8], xmm0
0x18005ad95  mov     edi, 0FFFFFFFFh
0x18005ad9a  test    rbx, rbx
0x18005ad9d  jz      short loc_18005ADC3
0x18005ad9f  mov     eax, edi
0x18005ada1  lock xadd [rbx+18h], eax
0x18005ada6  sub     eax, 1
0x18005ada9  jnz     loc_18005AF04
0x18005adaf  call    WINRT_IMPL_GetProcessHeap
0x18005adb4  mov     rcx, rax; hHeap
0x18005adb7  mov     r8, [rsp+170h+lpMem]; lpMem
0x18005adbc  xor     edx, edx; dwFlags
0x18005adbe  call    WINRT_IMPL_HeapFree
0x18005adc3  lea     rdx, [rsp+170h+var_108]
0x18005adc8  mov     rcx, r14
0x18005adcb  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005add0  movups  xmm0, xmmword ptr [rax]
0x18005add3  movaps  [rbp+70h+var_90], xmm0
0x18005add7  mov     eax, [rbp+70h+var_D0]
0x18005adda  mov     [rbp+70h+var_80], eax
0x18005addd  lea     rdx, [rbp+70h+var_C8]
0x18005ade1  lea     rcx, [rbp+70h+var_78]
0x18005ade5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18005adea  movups  xmm0, [rbp+70h+var_A8]
0x18005adee  movups  [rbp+70h+var_58], xmm0
0x18005adf2  lea     rax, qword_18033C3C0
0x18005adf9  mov     [rsp+170h+lpMem], rax
0x18005adfe  mov     [rsp+170h+var_138], 0
0x18005ae03  mov     rcx, rax; _Mtx_t
0x18005ae06  call    _Mtx_lock
0x18005ae0b  test    eax, eax
0x18005ae0d  jnz     loc_18005B0E7
0x18005ae13  mov     eax, cs:dword_18033C40C
0x18005ae19  cmp     eax, 7FFFFFFFh
0x18005ae1e  jz      loc_18005B040
0x18005ae24  mov     [rsp+170h+var_138], 1
0x18005ae29  mov     ecx, 20h ; ' '; Size
0x18005ae2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ae33  mov     rsi, rax
0x18005ae36  mov     [rsp+170h+var_150], rax
0x18005ae3b  xorps   xmm0, xmm0
0x18005ae3e  movups  xmmword ptr [rax], xmm0
0x18005ae41  mov     dword ptr [rax+8], 1
0x18005ae48  mov     dword ptr [rax+0Ch], 1
0x18005ae4f  lea     rax, ??_7?$_Ref_count_obj2@UImageFactoryWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageFactoryWrapper>::`vftable'
0x18005ae56  mov     [rsi], rax
0x18005ae59  lea     r12, [rsi+10h]
0x18005ae5d  mov     rbx, [r14]
0x18005ae60  test    rbx, rbx
0x18005ae63  jz      short loc_18005AE75
0x18005ae65  mov     rax, [rbx]
0x18005ae68  mov     rcx, rbx
0x18005ae6b  mov     rax, [rax+8]
0x18005ae6f  call    cs:__guard_dispatch_icall_fptr
0x18005ae75  lea     rax, ??_7ImageFactoryWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageFactoryWrapper::`vftable'
0x18005ae7c  mov     [r12], rax
0x18005ae80  mov     [r12+8], rbx
0x18005ae85  mov     [rsp+170h+var_108], r12
0x18005ae8a  mov     [rsp+170h+var_100], rsi
0x18005ae8f  call    ?Instance@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@SAAEAU123@XZ; asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance(void)
0x18005ae94  xorps   xmm0, xmm0
0x18005ae97  movdqu  [rbp+70h+pExceptionObject], xmm0
0x18005ae9c  lock inc dword ptr [rsi+8]
0x18005aea0  mov     qword ptr [rbp+70h+pExceptionObject], r12
0x18005aea4  mov     qword ptr [rbp+70h+pExceptionObject+8], rsi
0x18005aea8  lea     r8, [rbp+70h+pExceptionObject]
0x18005aeac  lea     rdx, [rbp+70h+var_90]
0x18005aeb0  mov     rcx, rax; _Mtx_t
0x18005aeb3  call    ?RegisterModelAccessorFactory@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@QEAA_NAEBUModelVersionKey@23@V?$shared_ptr@UIImageModelAccessorFactory@SemanticPipelines@asg@@@std@@_N@Z; asg::SemanticPipelines::ModelAccessorFactoryRegistry::RegisterModelAccessorFactory(asg::SemanticPipelines::ModelVersionKey const &,std::shared_ptr<asg::SemanticPipelines::IImageModelAccessorFactory>,bool)
0x18005aeb8  lea     rdx, [rbp+70h+pExceptionObject]
0x18005aebc  mov     rcx, r14
0x18005aebf  test    al, al
0x18005aec1  jnz     short loc_18005AF11
0x18005aec3  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005aec8  mov     rbx, rax
0x18005aecb  mov     ecx, 48h ; 'H'; Size
0x18005aed0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005aed5  mov     [rsp+170h+var_148], rax
0x18005aeda  movups  xmm1, xmmword ptr [rbx]
0x18005aedd  lea     rcx, [rax+10h]
0x18005aee1  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005aee8  mov     [rcx], rdx
0x18005aeeb  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005aef2  mov     qword ptr [rax+8], 1
0x18005aefa  mov     qword ptr [rax+18h], 1
0x18005af02  jmp     short loc_18005AF4E
0x18005af04  test    eax, eax
0x18005af06  js      loc_18005B053
0x18005af0c  jmp     loc_18005ADC3
0x18005af11  call    ?ModelId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_IEmbeddingsModelFactory<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::ModelId(void)
0x18005af16  mov     rbx, rax
0x18005af19  mov     ecx, 48h ; 'H'; Size
0x18005af1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005af23  mov     [rsp+170h+var_148], rax
0x18005af28  movups  xmm1, xmmword ptr [rbx]
0x18005af2b  lea     rcx, [rax+10h]
0x18005af2f  lea     rdx, ??_7?$produce@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIRegisterEmbeddingModelFactoryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IRegisterEmbeddingModelFactoryResult>::`vftable'
0x18005af36  mov     [rcx], rdx
0x18005af39  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005af40  mov     qword ptr [rax+8], 1
0x18005af48  xor     edx, edx
0x18005af4a  mov     [rax+18h], rdx
0x18005af4e  movups  xmm0, xmmword ptr [r13+0]
0x18005af53  lea     rdx, ??_7?$heap_implements@VRegisterEmbeddingModelFactoryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::RegisterEmbeddingModelFactoryResult>::`vftable'
0x18005af5a  movups  xmmword ptr [rax+20h], xmm0
0x18005af5e  movups  xmmword ptr [rax+30h], xmm1
0x18005af62  mov     dword ptr [rax+40h], 1
0x18005af69  mov     [rax], rdx
0x18005af6c  mov     [r15], rcx
0x18005af6f  mov     eax, edi
0x18005af71  lock xadd [rsi+8], eax
0x18005af76  cmp     eax, 1
0x18005af79  jnz     short loc_18005AFA7
0x18005af7b  mov     rax, [rsi]
0x18005af7e  mov     rcx, rsi
0x18005af81  mov     rax, [rax]
0x18005af84  call    cs:__guard_dispatch_icall_fptr
0x18005af8a  mov     eax, edi
0x18005af8c  lock xadd [rsi+0Ch], eax
0x18005af91  cmp     eax, 1
0x18005af94  jnz     short loc_18005AFA7
0x18005af96  mov     rax, [rsi]
0x18005af99  mov     rcx, rsi
0x18005af9c  mov     rax, [rax+8]
0x18005afa0  call    cs:__guard_dispatch_icall_fptr
0x18005afa6  nop
0x18005afa7  lea     rcx, qword_18033C3C0; _Mtx_t
0x18005afae  call    _Mtx_unlock
0x18005afb3  nop
0x18005afb4  lea     rcx, [rbp+70h+var_78]; void *
0x18005afb8  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
0x18005afbd  nop
0x18005afbe  lea     rcx, [rbp+70h+var_C8]; void *
0x18005afc2  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
0x18005afc7  nop
0x18005afc8  mov     rbx, [rsp+170h+var_118]
0x18005afcd  test    rbx, rbx
0x18005afd0  jz      short loc_18005B008
0x18005afd2  mov     eax, edi
0x18005afd4  lock xadd [rbx+8], eax
0x18005afd9  cmp     eax, 1
0x18005afdc  jnz     short loc_18005B008
0x18005afde  mov     rax, [rbx]
0x18005afe1  mov     rcx, rbx
0x18005afe4  mov     rax, [rax]
0x18005afe7  call    cs:__guard_dispatch_icall_fptr
0x18005afed  lock xadd [rbx+0Ch], edi
0x18005aff2  cmp     edi, 1
0x18005aff5  jnz     short loc_18005B008
0x18005aff7  mov     rax, [rbx]
0x18005affa  mov     rcx, rbx
0x18005affd  mov     rax, [rax+8]
0x18005b001  call    cs:__guard_dispatch_icall_fptr
0x18005b007  nop
0x18005b008  cmp     qword ptr [r14], 0
0x18005b00c  jz      short loc_18005B016
0x18005b00e  mov     rcx, r14
0x18005b011  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b016  mov     rax, r15
  ... truncated ...
```
