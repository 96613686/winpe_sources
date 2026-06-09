# winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar::RegisterModelFactories(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IModelFactoryRegistry const &)

- ea: `0x180044eb0`
- end: `0x1800454ec`
- name: `?RegisterModelFactories@AiFabricModelFactoryRegistrar@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AU?$com_array@URegisterEmbeddingModelFactoryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@6@AEBUIModelFactoryRegistry@Compatibility@AiFabric@SemanticIndex@Asg@56@@Z`
- size: `1596`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045d00`

## callees

- `0x180001de0`
- `0x180002bb0`
- `0x180009580`
- `0x180044eb0`
- `0x18004c070`
- `0x18004c8cc`
- `0x18004c91c`
- `0x18004ecf0`
- `0x1800513c1`
- `0x18005e260`

## string_xrefs

- `0x180044f65`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180045256`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180045320`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar::RegisterModelFactories(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  _QWORD *v8; // rax
  char *v9; // r13
  __int64 v10; // rcx
  int v11; // eax
  _QWORD *v12; // rax
  char *v13; // r12
  __int64 v14; // rcx
  int v15; // eax
  _QWORD *v16; // rax
  char *v17; // r15
  __int64 v18; // rcx
  int v19; // eax
  _QWORD *v20; // rax
  char *v21; // r14
  __int64 v22; // rcx
  int v23; // eax
  _QWORD *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  _BYTE *v27; // rdi
  char *v28; // rbx
  signed __int64 v29; // rdi
  __int64 v30; // rcx
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v38; // [rsp+A0h] [rbp-60h] BYREF
  char *v39; // [rsp+A8h] [rbp-58h]
  char *v40; // [rsp+B0h] [rbp-50h]
  _QWORD v41[6]; // [rsp+B8h] [rbp-48h] BYREF
  char v42; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h] BYREF

  v44 = a2;
  v5 = operator new(0x40u);
  v40 = (char *)(v5 + 2);
  v5[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable';
  v5[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v5[1] = 1;
  *v5 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  *((_OWORD *)v5 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::TextModelId;
  *((_OWORD *)v5 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId;
  *v5 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  v38 = (char *)(v5 + 2);
  v45 = 0;
  LODWORD(v37[0]) = 377;
  v37[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = *a3;
  v32 = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int64 *))(*(_QWORD *)v6 + 56LL))(
         v6,
         &v32,
         v5 + 2,
         &v45);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v37);
  }
  v41[0] = v45;
  v8 = operator new(0x40u);
  v9 = (char *)(v8 + 2);
  v8[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable';
  v8[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v8[1] = 1;
  *v8 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  *((_OWORD *)v8 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::TextModelId;
  *((_OWORD *)v8 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::VectorSpaceId;
  *v8 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  v37[0] = v8 + 2;
  v45 = 0;
  LODWORD(v36[0]) = 377;
  v36[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v10 = *a3;
  v32 = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::VectorSpaceId;
  v11 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int64 *))(*(_QWORD *)v10 + 56LL))(
          v10,
          &v32,
          v8 + 2,
          &v45);
  if ( v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, v36);
  }
  v41[1] = v45;
  v12 = operator new(0x40u);
  v13 = (char *)(v12 + 2);
  v12[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable';
  v12[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v12[1] = 1;
  *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  *((_OWORD *)v12 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::TextModelId;
  *((_OWORD *)v12 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId;
  *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  v36[0] = v12 + 2;
  v45 = 0;
  LODWORD(v35[0]) = 377;
  v35[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *a3;
  v32 = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId;
  v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int64 *))(*(_QWORD *)v14 + 56LL))(
          v14,
          &v32,
          v12 + 2,
          &v45);
  if ( v15 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v15, v35);
  }
  v41[2] = v45;
  v16 = operator new(0x40u);
  v17 = (char *)(v16 + 2);
  v16[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable';
  v16[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v16[1] = 1;
  *v16 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  *((_OWORD *)v16 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::TextModelId;
  *((_OWORD *)v16 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId;
  *v16 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable';
  v35[0] = v16 + 2;
  v45 = 0;
  LODWORD(v34[0]) = 377;
  v34[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v18 = *a3;
  v32 = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId;
  v19 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int64 *))(*(_QWORD *)v18 + 56LL))(
          v18,
          &v32,
          v16 + 2,
          &v45);
  if ( v19 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v19, v34);
  }
  v41[3] = v45;
  v20 = operator new(0x40u);
  v21 = (char *)(v20 + 2);
  v20[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::`vftable';
  v20[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v20[1] = 1;
  *v20 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable';
  *((_OWORD *)v20 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::ImageModelId;
  *((_OWORD *)v20 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId;
  *v20 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable';
  v34[0] = v20 + 2;
  v45 = 0;
  LODWORD(v33[0]) = 371;
  v33[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v22 = *a3;
  v32 = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId;
  v23 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int64 *))(*(_QWORD *)v22 + 48LL))(
          v22,
          &v32,
          v20 + 2,
          &v45);
  if ( v23 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v23, v33);
  }
  v41[4] = v45;
  v24 = operator new(0x40u);
  v39 = (char *)(v24 + 2);
  v24[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::`vftable';
  v24[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v24[1] = 1;
  *v24 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable';
  *((_OWORD *)v24 + 2) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::ImageModelId;
  *((_OWORD *)v24 + 3) = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId;
  *v24 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable';
  v33[0] = v24 + 2;
  v45 = 0;
  LODWORD(v32) = 371;
  *((_QWORD *)&v32 + 1) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generate"
                          "d Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v25 = *a3;
  pExceptionObject[0] = winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId;
  v26 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD *, __int64 *))(*(_QWORD *)v25 + 48LL))(
          v25,
          pExceptionObject,
          v24 + 2,
          &v45);
  if ( v26 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v26, &v32);
  }
  v41[5] = v45;
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  v27 = WINRT_IMPL_CoTaskMemAlloc(0x30u);
  *(_QWORD *)a2 = v27;
  if ( !v27 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_DWORD *)(a2 + 8) = 6;
  v28 = (char *)v41;
  v29 = v27 - (_BYTE *)v41;
  do
  {
    v30 = *(_QWORD *)v28;
    *(_QWORD *)&v28[v29] = *(_QWORD *)v28;
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    v28 += 8;
  }
  while ( v28 != &v42 );
  `eh vector destructor iterator'(
    v41,
    8u,
    6u,
    winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>::~AsyncOperationCompletedHandler<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>);
  if ( v39 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v33);
  if ( v21 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v34);
  if ( v17 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v35);
  if ( v13 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v36);
  if ( v9 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v37);
  if ( v40 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
  return a2;
}

```

## disassembly

```asm
0x180044eb0  mov     [rsp-8+arg_0], rbx
0x180044eb5  push    rbp
0x180044eb6  push    rsi
0x180044eb7  push    rdi
0x180044eb8  push    r12
0x180044eba  push    r13
0x180044ebc  push    r14
0x180044ebe  push    r15
0x180044ec0  lea     rbp, [rsp-30h]
0x180044ec5  sub     rsp, 130h
0x180044ecc  mov     rax, cs:__security_cookie
0x180044ed3  xor     rax, rsp
0x180044ed6  mov     [rbp+60h+var_40], rax
0x180044eda  mov     rbx, r8
0x180044edd  mov     rsi, rdx
0x180044ee0  mov     [rbp+60h+var_50], rdx
0x180044ee4  xor     edi, edi
0x180044ee6  mov     [rsp+160h+var_130], edi
0x180044eea  mov     ecx, 40h ; '@'; Size
0x180044eef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044ef4  mov     [rbp+60h+var_C0], rax
0x180044ef8  lea     rdx, [rax+10h]
0x180044efc  mov     [rbp+60h+var_B0], rdx
0x180044f00  lea     r15, ??_7?$produce@USemanticTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable'
0x180044f07  mov     [rdx], r15
0x180044f0a  lea     r12, ??_7?$produce@USemanticTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable'
0x180044f11  mov     [rdx+8], r12
0x180044f15  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180044f1c  mov     qword ptr [rax+8], 1
0x180044f24  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x180044f2b  mov     [rax], rcx
0x180044f2e  movups  xmm0, cs:?TextModelId@SpaceV6@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::TextModelId
0x180044f35  movups  xmmword ptr [rax+20h], xmm0
0x180044f39  movups  xmm1, cs:?VectorSpaceId@SpaceV6@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId
0x180044f40  movups  xmmword ptr [rax+30h], xmm1
0x180044f44  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x180044f4b  mov     [rax], rcx
0x180044f4e  mov     [rbp+60h+var_C0], rdx
0x180044f52  mov     [rsp+160h+var_130], 2
0x180044f5a  mov     [rbp+60h+var_48], rdi
0x180044f5e  mov     dword ptr [rbp+60h+var_D0], 179h
0x180044f65  lea     r14, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180044f6c  mov     [rbp+60h+var_C8], r14
0x180044f70  mov     rcx, [rbx]
0x180044f73  movups  xmm0, cs:?VectorSpaceId@SpaceV6@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId
0x180044f7a  movaps  [rsp+160h+var_120], xmm0
0x180044f7f  mov     rax, [rcx]
0x180044f82  lea     r9, [rbp+60h+var_48]
0x180044f86  mov     r8, rdx
0x180044f89  lea     rdx, [rsp+160h+var_120]
0x180044f8e  mov     rax, [rax+38h]
0x180044f92  call    cs:__guard_dispatch_icall_fptr
0x180044f98  test    eax, eax
0x180044f9a  js      loc_18004548E
0x180044fa0  mov     rax, [rbp+60h+var_48]
0x180044fa4  mov     [rbp+60h+var_A8], rax
0x180044fa8  mov     [rsp+160h+var_130], 6
0x180044fb0  mov     ecx, 40h ; '@'; Size
0x180044fb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044fba  mov     [rbp+60h+var_D0], rax
0x180044fbe  lea     r13, [rax+10h]
0x180044fc2  mov     [r13+0], r15
0x180044fc6  mov     [r13+8], r12
0x180044fca  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180044fd1  mov     qword ptr [rax+8], 1
0x180044fd9  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x180044fe0  mov     [rax], rcx
0x180044fe3  movups  xmm0, cs:?TextModelId@SpaceV6Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::TextModelId
0x180044fea  movups  xmmword ptr [rax+20h], xmm0
0x180044fee  movups  xmm1, cs:?VectorSpaceId@SpaceV6Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::VectorSpaceId
0x180044ff5  movups  xmmword ptr [rax+30h], xmm1
0x180044ff9  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x180045000  mov     [rax], rcx
0x180045003  mov     [rbp+60h+var_D0], r13
0x180045007  mov     [rsp+160h+var_130], 0Eh
0x18004500f  mov     [rbp+60h+var_48], rdi
0x180045013  mov     dword ptr [rbp+60h+var_E0], 179h
0x18004501a  mov     [rbp+60h+var_D8], r14
0x18004501e  mov     rcx, [rbx]
0x180045021  movups  xmm0, cs:?VectorSpaceId@SpaceV6Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Alternative::VectorSpaceId
0x180045028  movaps  [rsp+160h+var_120], xmm0
0x18004502d  mov     rax, [rcx]
0x180045030  lea     r9, [rbp+60h+var_48]
0x180045034  mov     r8, r13
0x180045037  lea     rdx, [rsp+160h+var_120]
0x18004503c  mov     rax, [rax+38h]
0x180045040  call    cs:__guard_dispatch_icall_fptr
0x180045046  test    eax, eax
0x180045048  js      loc_18004549D
0x18004504e  mov     rax, [rbp+60h+var_48]
0x180045052  mov     [rbp+60h+var_A0], rax
0x180045056  mov     [rsp+160h+var_130], 1Eh
0x18004505e  mov     ecx, 40h ; '@'; Size
0x180045063  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045068  mov     [rbp+60h+var_E0], rax
0x18004506c  lea     r12, [rax+10h]
0x180045070  lea     rcx, ??_7?$produce@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable'
0x180045077  mov     [r12], rcx
0x18004507b  lea     rcx, ??_7?$produce@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable'
0x180045082  mov     [r12+8], rcx
0x180045087  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004508e  mov     qword ptr [rax+8], 1
0x180045096  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x18004509d  mov     [rax], rcx
0x1800450a0  movups  xmm0, cs:?TextModelId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::TextModelId
0x1800450a7  movups  xmmword ptr [rax+20h], xmm0
0x1800450ab  movups  xmm1, cs:?VectorSpaceId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId
0x1800450b2  movups  xmmword ptr [rax+30h], xmm1
0x1800450b6  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x1800450bd  mov     [rax], rcx
0x1800450c0  mov     [rbp+60h+var_E0], r12
0x1800450c4  mov     [rsp+160h+var_130], 3Eh ; '>'
0x1800450cc  mov     [rbp+60h+var_48], rdi
0x1800450d0  mov     dword ptr [rsp+160h+var_F0], 179h
0x1800450d8  mov     [rsp+160h+var_E8], r14
0x1800450dd  mov     rcx, [rbx]
0x1800450e0  movups  xmm0, cs:?VectorSpaceId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId
0x1800450e7  movaps  [rsp+160h+var_120], xmm0
0x1800450ec  mov     rax, [rcx]
0x1800450ef  lea     r9, [rbp+60h+var_48]
0x1800450f3  mov     r8, r12
0x1800450f6  lea     rdx, [rsp+160h+var_120]
0x1800450fb  mov     rax, [rax+38h]
0x1800450ff  call    cs:__guard_dispatch_icall_fptr
0x180045105  test    eax, eax
0x180045107  js      loc_1800454AC
0x18004510d  mov     rax, [rbp+60h+var_48]
0x180045111  mov     [rbp+60h+var_98], rax
0x180045115  mov     [rsp+160h+var_130], 7Eh ; '~'
0x18004511d  mov     ecx, 40h ; '@'; Size
0x180045122  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045127  mov     [rsp+160h+var_F0], rax
0x18004512c  lea     r15, [rax+10h]
0x180045130  lea     rcx, ??_7?$produce@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory>::`vftable'
0x180045137  mov     [r15], rcx
0x18004513a  lea     rcx, ??_7?$produce@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable'
0x180045141  mov     [r15+8], rcx
0x180045145  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004514c  mov     qword ptr [rax+8], 1
0x180045154  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x18004515b  mov     [rax], rcx
0x18004515e  movups  xmm0, cs:?TextModelId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::TextModelId
0x180045165  movups  xmmword ptr [rax+20h], xmm0
0x180045169  movups  xmm1, cs:?VectorSpaceId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId
0x180045170  movups  xmmword ptr [rax+30h], xmm1
0x180045174  lea     rcx, ??_7?$heap_implements@UImageEmbeddingTextModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory>::`vftable'
0x18004517b  mov     [rax], rcx
0x18004517e  mov     [rsp+160h+var_F0], r15
0x180045183  mov     [rsp+160h+var_130], 0FEh
0x18004518b  mov     [rbp+60h+var_48], rdi
0x18004518f  mov     dword ptr [rsp+160h+var_100], 179h
0x180045197  mov     [rsp+160h+var_F8], r14
0x18004519c  mov     rcx, [rbx]
0x18004519f  movups  xmm0, cs:?VectorSpaceId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId
0x1800451a6  movaps  [rsp+160h+var_120], xmm0
0x1800451ab  mov     rax, [rcx]
0x1800451ae  lea     r9, [rbp+60h+var_48]
0x1800451b2  mov     r8, r15
0x1800451b5  lea     rdx, [rsp+160h+var_120]
0x1800451ba  mov     rax, [rax+38h]
0x1800451be  call    cs:__guard_dispatch_icall_fptr
0x1800451c4  test    eax, eax
0x1800451c6  js      loc_1800454BC
0x1800451cc  mov     rax, [rbp+60h+var_48]
0x1800451d0  mov     [rbp+60h+var_90], rax
0x1800451d4  mov     [rsp+160h+var_130], 1FEh
0x1800451dc  mov     ecx, 40h ; '@'; Size
0x1800451e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800451e6  mov     [rsp+160h+var_100], rax
0x1800451eb  lea     r14, [rax+10h]
0x1800451ef  lea     rcx, ??_7?$produce@UImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::`vftable'
0x1800451f6  mov     [r14], rcx
0x1800451f9  lea     rcx, ??_7?$produce@UImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable'
0x180045200  mov     [r14+8], rcx
0x180045204  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004520b  mov     qword ptr [rax+8], 1
0x180045213  lea     rcx, ??_7ImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable'
0x18004521a  mov     [rax], rcx
0x18004521d  movups  xmm0, cs:?ImageModelId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::ImageModelId
0x180045224  movups  xmmword ptr [rax+20h], xmm0
0x180045228  movups  xmm1, cs:?VectorSpaceId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId
0x18004522f  movups  xmmword ptr [rax+30h], xmm1
0x180045233  lea     rcx, ??_7ImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable'
0x18004523a  mov     [rax], rcx
0x18004523d  mov     [rsp+160h+var_100], r14
0x180045242  mov     [rsp+160h+var_130], 3FEh
0x18004524a  mov     [rbp+60h+var_48], rdi
0x18004524e  mov     dword ptr [rsp+160h+var_110], 173h
0x180045256  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004525d  mov     [rsp+160h+var_108], rax
0x180045262  mov     rcx, [rbx]
0x180045265  movups  xmm0, cs:?VectorSpaceId@FlorenceD3Compliant@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Compliant::VectorSpaceId
0x18004526c  movaps  [rsp+160h+var_120], xmm0
0x180045271  mov     rax, [rcx]
0x180045274  lea     r9, [rbp+60h+var_48]
0x180045278  mov     r8, r14
0x18004527b  lea     rdx, [rsp+160h+var_120]
0x180045280  mov     rax, [rax+30h]
0x180045284  call    cs:__guard_dispatch_icall_fptr
0x18004528a  test    eax, eax
0x18004528c  js      loc_1800454CC
0x180045292  mov     rax, [rbp+60h+var_48]
0x180045296  mov     [rbp+60h+var_88], rax
0x18004529a  mov     [rsp+160h+var_130], 7FEh
0x1800452a2  mov     ecx, 40h ; '@'; Size
0x1800452a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800452ac  mov     [rsp+160h+var_110], rax
0x1800452b1  lea     rdx, [rax+10h]
0x1800452b5  mov     [rbp+60h+var_B8], rdx
0x1800452b9  lea     rcx, ??_7?$produce@UImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory>::`vftable'
0x1800452c0  mov     [rdx], rcx
0x1800452c3  lea     rcx, ??_7?$produce@UImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::`vftable'
0x1800452ca  mov     [rdx+8], rcx
0x1800452ce  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800452d5  mov     qword ptr [rax+8], 1
0x1800452dd  lea     rcx, ??_7ImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable'
0x1800452e4  mov     [rax], rcx
0x1800452e7  movups  xmm0, cs:?ImageModelId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::ImageModelId
0x1800452ee  movups  xmmword ptr [rax+20h], xmm0
0x1800452f2  movups  xmm1, cs:?VectorSpaceId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId
0x1800452f9  movups  xmmword ptr [rax+30h], xmm1
0x1800452fd  lea     rcx, ??_7ImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory::`vftable'
0x180045304  mov     [rax], rcx
0x180045307  mov     [rsp+160h+var_110], rdx
0x18004530c  mov     [rsp+160h+var_130], 0FFEh
0x180045314  mov     [rbp+60h+var_48], rdi
0x180045318  mov     dword ptr [rsp+160h+var_120], 173h
0x180045320  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180045327  mov     qword ptr [rsp+160h+var_120+8], rax
0x18004532c  mov     rcx, [rbx]
0x18004532f  movups  xmm0, cs:?VectorSpaceId@FlorenceD3Alternative@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::FlorenceD3Alternative::VectorSpaceId
0x180045336  movaps  [rbp+60h+pExceptionObject], xmm0
0x18004533a  mov     rax, [rcx]
0x18004533d  lea     r9, [rbp+60h+var_48]
0x180045341  mov     r8, rdx
0x180045344  lea     rdx, [rbp+60h+pExceptionObject]
0x180045348  mov     rax, [rax+30h]
0x18004534c  call    cs:__guard_dispatch_icall_fptr
0x180045352  test    eax, eax
0x180045354  js      loc_1800454DC
0x18004535a  mov     rax, [rbp+60h+var_48]
0x18004535e  mov     [rbp+60h+var_80], rax
0x180045362  mov     [rsp+160h+var_130], 1FFEh
0x18004536a  mov     [rsi], rdi
0x18004536d  mov     [rsi+8], edi
0x180045370  mov     ecx, 30h ; '0'; cb
0x180045375  call    WINRT_IMPL_CoTaskMemAlloc
0x18004537a  mov     rdi, rax
0x18004537d  mov     [rsi], rax
0x180045380  test    rax, rax
0x180045383  jz      loc_180045474
0x180045389  mov     dword ptr [rsi+8], 6
0x180045390  lea     rbx, [rbp+60h+var_A8]
0x180045394  lea     rax, [rbp+60h+var_A8]
0x180045398  sub     rdi, rax
0x18004539b  nop     dword ptr [rax+rax+00h]
0x1800453a0  mov     rcx, [rbx]
0x1800453a3  mov     [rdi+rbx], rcx
0x1800453a7  test    rcx, rcx
0x1800453aa  jz      short loc_1800453B9
0x1800453ac  mov     rax, [rcx]
0x1800453af  mov     rax, [rax+8]
0x1800453b3  call    cs:__guard_dispatch_icall_fptr
0x1800453b9  add     rbx, 8
0x1800453bd  lea     rax, [rbp+60h+var_78]
0x1800453c1  cmp     rbx, rax
0x1800453c4  jnz     short loc_1800453A0
0x1800453c6  mov     [rsp+160h+var_130], 1FFFh
0x1800453ce  lea     r9, ??1?$AsyncOperationCompletedHandler@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; void (*)(void *)
0x1800453d5  mov     edx, 8; unsigned __int64
0x1800453da  mov     r8d, 6; unsigned __int64
0x1800453e0  lea     rcx, [rbp+60h+var_A8]; void *
0x1800453e4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800453e9  nop
0x1800453ea  cmp     [rbp+60h+var_B8], 0
0x1800453ef  jz      short loc_1800453FC
0x1800453f1  lea     rcx, [rsp+160h+var_110]
0x1800453f6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800453fb  nop
0x1800453fc  test    r14, r14
0x1800453ff  jz      short loc_18004540C
0x180045401  lea     rcx, [rsp+160h+var_100]
0x180045406  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004540b  nop
0x18004540c  test    r15, r15
0x18004540f  jz      short loc_18004541C
0x180045411  lea     rcx, [rsp+160h+var_F0]
0x180045416  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004541b  nop
0x18004541c  test    r12, r12
0x18004541f  jz      short loc_18004542B
0x180045421  lea     rcx, [rbp+60h+var_E0]
0x180045425  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004542a  nop
0x18004542b  test    r13, r13
0x18004542e  jz      short loc_18004543A
0x180045430  lea     rcx, [rbp+60h+var_D0]
0x180045434  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180045439  nop
0x18004543a  cmp     [rbp+60h+var_B0], 0
  ... truncated ...
```
