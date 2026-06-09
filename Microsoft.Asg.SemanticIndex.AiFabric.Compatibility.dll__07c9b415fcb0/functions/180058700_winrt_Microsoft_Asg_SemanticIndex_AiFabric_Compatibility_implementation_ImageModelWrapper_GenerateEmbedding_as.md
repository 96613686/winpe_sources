# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper::GenerateEmbedding(asg::SemanticRegistry::Bgra8ImageView const &,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::ExecutionPriorityHint)

- ea: `0x180058700`
- end: `0x180058cdd`
- name: `?GenerateEmbedding@ImageModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UEAA?AV?$shared_ptr@UIVectorData@SemanticRegistry@asg@@@std@@AEBUBgra8ImageView@SemanticRegistry@asg@@W4EmbeddingElementType@SemanticRegistry@asg@@W4ExecutionPriorityHint@SemanticRegistry@asg@@@Z`
- size: `1501`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180004280`
- `0x18000cc40`
- `0x18000d230`
- `0x180010dd0`
- `0x18001fc60`
- `0x180057f20`
- `0x180058670`
- `0x180058700`
- `0x18005fd00`
- `0x18005fdd0`
- `0x1801f7190`
- `0x1801f97e0`
- `0x18020c450`
- `0x18022ae90`
- `0x18022aeae`
- `0x180242120`
- `0x180242860`

## string_xrefs

- `0x18005891b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800588a2`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180058b8d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180058bdb`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180058c29`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180058c97`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper::GenerateEmbedding(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v8; // ebx
  unsigned __int64 v9; // rcx
  float *v10; // rdi
  _QWORD *v11; // rsi
  _DWORD *v12; // rdi
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  SIZE_T v17; // r12
  float *v18; // r13
  _DWORD *v19; // rdi
  float *v21; // rsi
  unsigned int v22; // r15d
  float *v23; // rax
  unsigned int i; // edi
  float v25; // xmm6_4
  SIZE_T *p_cb; // rax
  _DWORD *v27; // rdi
  _QWORD *v28; // rsi
  SIZE_T v29; // [rsp+48h] [rbp-C0h] BYREF
  SIZE_T *v30; // [rsp+50h] [rbp-B8h] BYREF
  const char *v31; // [rsp+58h] [rbp-B0h]
  __int64 v32; // [rsp+60h] [rbp-A8h]
  __int64 pExceptionObject; // [rsp+68h] [rbp-A0h] BYREF
  const char *v34; // [rsp+70h] [rbp-98h]
  __int64 v35; // [rsp+78h] [rbp-90h]
  float *v36; // [rsp+88h] [rbp-80h] BYREF
  int v37; // [rsp+90h] [rbp-78h]
  int v38; // [rsp+94h] [rbp-74h]
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v40; // [rsp+B0h] [rbp-58h] BYREF
  float *v41; // [rsp+B8h] [rbp-50h] BYREF
  int v42; // [rsp+C0h] [rbp-48h]
  _OWORD v43[6]; // [rsp+C8h] [rbp-40h] BYREF
  SIZE_T cb; // [rsp+168h] [rbp+60h] BYREF
  _QWORD *v45; // [rsp+170h] [rbp+68h]
  unsigned int v46; // [rsp+180h] [rbp+78h]

  v46 = a4;
  v45 = a2;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 8LL))(a1, a4) )
  {
    LODWORD(v30) = 115;
    v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v32 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v43, L"Unsupported embedding element type");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v43,
      (const struct winrt::impl::slim_source_location *)&v30);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v8 = *(_DWORD *)a3 * *(_DWORD *)(a3 + 4);
  v9 = 4LL * v8;
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(v30) = 121;
    v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v32 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v43, L"image has too many pixels to embed");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v43,
      (const struct winrt::impl::slim_source_location *)&v30);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  if ( v9 > 4LL * *(_QWORD *)(a3 + 16) )
  {
    LODWORD(v30) = 126;
    v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v32 = 0;
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v43,
      L"image pixel buffer is too small for the image dimensions");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v43,
      (const struct winrt::impl::slim_source_location *)&v30);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v43[0] = 0u;
  cb = 0;
  v10 = *(float **)(a3 + 8);
  v11 = operator new(0x40u);
  v40 = v11;
  v36 = v10;
  v37 = 4 * v8;
  v38 = HIDWORD(v31);
  v11[1] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable';
  v11[2] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable';
  *v11 = &winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v11[4] = 1;
  *v11 = &CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v11[3] = &CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v12 = operator new(0x38u);
  pv = v12;
  *(_OWORD *)v12 = 0;
  v12[2] = 1;
  v12[3] = 1;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<MemoryLifetime>::`vftable';
  MemoryLifetime::MemoryLifetime(v12 + 4, &v36, &cb);
  v11[5] = 0;
  v11[6] = v12 + 4;
  v11[7] = v12;
  *v11 = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v11[3] = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v40 = v11 + 1;
  if ( cb )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&cb);
  cb = 0;
  LODWORD(v30) = 507;
  v31 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v32 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD *, SIZE_T *))(v11[1] + 48LL))(v11 + 1, &cb);
  if ( v13 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v13, &v30);
  }
  v29 = cb;
  v30 = &v29;
  LOBYTE(v31) = 1;
  LODWORD(v41) = 0;
  HIDWORD(v41) = *(_DWORD *)a3;
  v42 = *(_DWORD *)(a3 + 4);
  v14 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::FromAsg(a5);
  LODWORD(cb) = 0;
  pv = 0;
  v15 = *(_QWORD *)(a1 + 8);
  LODWORD(pExceptionObject) = 787;
  v34 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v35 = 0;
  v36 = v41;
  v37 = v42;
  v16 = (*(__int64 (__fastcall **)(__int64, float **, SIZE_T, _QWORD, SIZE_T *, LPVOID *))(*(_QWORD *)v15 + 48LL))(
          v15,
          &v36,
          v29,
          v14,
          &cb,
          &pv);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, &pExceptionObject);
  }
  v17 = (unsigned int)cb;
  v18 = (float *)pv;
  *(_QWORD *)&v43[0] = pv;
  DWORD2(v43[0]) = cb;
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(&v29);
  if ( v29 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v29);
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v40);
  if ( v46 == 1 )
  {
    v19 = operator new(0x28u);
    cb = (SIZE_T)v19;
    *(_OWORD *)v19 = 0;
    v19[2] = 1;
    v19[3] = 1;
    *(_QWORD *)v19 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>>::`vftable';
    v36 = v18;
    v37 = v17;
    *(_QWORD *)&v43[0] = 0;
    DWORD2(v43[0]) = 0;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>::VectorDataWrapper<float>(
      v19 + 4,
      &v36);
    *a2 = v19 + 4;
    a2[1] = v19;
    return a2;
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 24) )
    {
      LODWORD(pExceptionObject) = 157;
      v34 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
      v35 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)&v36,
        L"Cannot produce quantized embedding without quantization parameters");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&v30,
        (const struct winrt::param::hstring *)&v36,
        (const struct winrt::impl::slim_source_location *)&pExceptionObject);
      throw (winrt::hresult_invalid_argument *)&v30;
    }
    v21 = 0;
    v36 = 0;
    v22 = 0;
    v37 = 0;
    if ( (_DWORD)v17 )
    {
      v23 = (float *)WINRT_IMPL_CoTaskMemAlloc(v17);
      v21 = v23;
      v36 = v23;
      if ( !v23 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
        throw (std::bad_alloc *)&pExceptionObject;
      }
      v22 = v17;
      v37 = v17;
      memset(v23, 0, v17);
    }
    for ( i = 0; i < v22; ++i )
    {
      if ( !*(_BYTE *)(a1 + 24) )
        std::_Throw_bad_optional_access();
      v25 = *(float *)(a1 + 20);
      *(float *)&cb = v25 + nearbyintf(v18[i] / *(float *)(a1 + 16));
      LODWORD(v29) = 1132396544;
      p_cb = &cb;
      if ( *(float *)&cb >= 255.0 )
        p_cb = &v29;
      *((_BYTE *)v21 + i) = (int)fmaxf(*(float *)p_cb, 0.0);
    }
    v27 = operator new(0x28u);
    cb = (SIZE_T)v27;
    *(_OWORD *)v27 = 0;
    v27[2] = 1;
    v27[3] = 1;
    *(_QWORD *)v27 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<unsigned char>>::`vftable';
    v41 = v21;
    v42 = v22;
    v36 = 0;
    v37 = 0;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<unsigned char>::VectorDataWrapper<unsigned char>(
      v27 + 4,
      &v41);
    v28 = v45;
    *v45 = v27 + 4;
    v28[1] = v27;
    if ( v18 )
      CoTaskMemFree_0(v18);
    return v28;
  }
}

```

## disassembly

```asm
0x180058700  mov     rax, rsp
0x180058703  mov     [rax+18h], rbx
0x180058707  mov     [rax+20h], r9d
0x18005870b  mov     [rax+10h], rdx
0x18005870f  push    rbp
0x180058710  push    rsi
0x180058711  push    rdi
0x180058712  push    r12
0x180058714  push    r13
0x180058716  push    r14
0x180058718  push    r15
0x18005871a  lea     rbp, [rax-58h]
0x18005871e  sub     rsp, 120h
0x180058725  movaps  xmmword ptr [rax-48h], xmm6
0x180058729  movaps  xmmword ptr [rax-58h], xmm7
0x18005872d  movaps  xmmword ptr [rax-68h], xmm8
0x180058732  mov     r12, r8
0x180058735  mov     r15, rdx
0x180058738  mov     r14, rcx
0x18005873b  xor     edi, edi
0x18005873d  mov     rax, [rcx]
0x180058740  mov     edx, r9d
0x180058743  mov     rax, [rax+8]
0x180058747  call    cs:__guard_dispatch_icall_fptr
0x18005874d  test    al, al
0x18005874f  jz      loc_180058B85
0x180058755  mov     eax, [r12+4]
0x18005875a  imul    eax, [r12]
0x18005875f  mov     ebx, eax
0x180058761  mov     ecx, eax
0x180058763  shl     rcx, 2
0x180058767  mov     eax, 0FFFFFFFFh
0x18005876c  cmp     rcx, rax
0x18005876f  ja      loc_180058BD3
0x180058775  mov     rax, [r12+10h]
0x18005877a  lea     rax, ds:0[rax*4]
0x180058782  cmp     rcx, rax
0x180058785  ja      loc_180058C21
0x18005878b  xorps   xmm0, xmm0
0x18005878e  movups  [rbp+50h+var_90], xmm0
0x180058792  mov     qword ptr [rbp+50h+var_90], rdi
0x180058796  mov     dword ptr [rbp+50h+var_90+8], edi
0x180058799  mov     [rbp+50h+cb], rdi
0x18005879d  mov     rdi, [r12+8]
0x1800587a2  lea     ebx, ds:0[rbx*4]
0x1800587a9  mov     ecx, 40h ; '@'; Size
0x1800587ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800587b3  mov     rsi, rax
0x1800587b6  mov     [rbp+50h+var_A8], rax
0x1800587ba  mov     qword ptr [rbp+50h+var_D0], rdi
0x1800587be  mov     dword ptr [rbp+50h+var_D0+8], ebx
0x1800587c1  mov     ecx, dword ptr [rsp+150h+var_100+4]
0x1800587c5  mov     dword ptr [rbp+50h+var_D0+0Ch], ecx
0x1800587c8  lea     r13, [rax+8]
0x1800587cc  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable'
0x1800587d3  mov     [r13+0], rax
0x1800587d7  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIClosable@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable'
0x1800587de  mov     [rsi+10h], rax
0x1800587e2  lea     rax, ??_7?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable'
0x1800587e9  mov     [rsi], rax
0x1800587ec  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800587f3  mov     qword ptr [rsi+20h], 1
0x1800587fb  lea     rax, ??_7CustomMemoryBuffer@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x180058802  mov     [rsi], rax
0x180058805  lea     rax, ??_7CustomMemoryBuffer@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x18005880c  mov     [rsi+18h], rax
0x180058810  mov     ecx, 38h ; '8'; Size
0x180058815  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005881a  mov     rdi, rax
0x18005881d  mov     [rbp+50h+pv], rax
0x180058821  xorps   xmm0, xmm0
0x180058824  movups  xmmword ptr [rax], xmm0
0x180058827  mov     dword ptr [rax+8], 1
0x18005882e  mov     dword ptr [rax+0Ch], 1
0x180058835  lea     rax, ??_7?$_Ref_count_obj2@UMemoryLifetime@@@std@@6B@; const std::_Ref_count_obj2<MemoryLifetime>::`vftable'
0x18005883c  mov     [rdi], rax
0x18005883f  lea     rbx, [rdi+10h]
0x180058843  movaps  xmm0, [rbp+50h+var_D0]
0x180058847  movdqa  [rbp+50h+var_D0], xmm0
0x18005884c  lea     r8, [rbp+50h+cb]
0x180058850  lea     rdx, [rbp+50h+var_D0]
0x180058854  mov     rcx, rbx
0x180058857  call    ??0MemoryLifetime@@QEAA@U?$array_view@E@winrt@@AEBUDeferralCompletedHandler@Foundation@Windows@2@@Z; MemoryLifetime::MemoryLifetime(winrt::array_view<uchar>,winrt::Windows::Foundation::DeferralCompletedHandler const &)
0x18005885c  nop
0x18005885d  xor     eax, eax
0x18005885f  mov     [rsi+28h], rax
0x180058863  mov     [rsi+30h], rbx
0x180058867  mov     [rsi+38h], rdi
0x18005886b  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x180058872  mov     [rsi], rax
0x180058875  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x18005887c  mov     [rsi+18h], rax
0x180058880  mov     [rbp+50h+var_A8], r13
0x180058884  cmp     [rbp+50h+cb], 0
0x180058889  jz      short loc_180058894
0x18005888b  lea     rcx, [rbp+50h+cb]
0x18005888f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058894  xor     ebx, ebx
0x180058896  mov     [rbp+50h+cb], rbx
0x18005889a  mov     dword ptr [rsp+150h+var_108], 1FBh
0x1800588a2  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1800588a9  mov     [rsp+150h+var_100], rax
0x1800588ae  mov     [rsp+150h+var_F8], rbx
0x1800588b3  mov     rax, [r13+0]
0x1800588b7  lea     rdx, [rbp+50h+cb]
0x1800588bb  mov     rcx, r13
0x1800588be  mov     rax, [rax+30h]
0x1800588c2  call    cs:__guard_dispatch_icall_fptr
0x1800588c8  test    eax, eax
0x1800588ca  js      loc_180058C6F
0x1800588d0  mov     rax, [rbp+50h+cb]
0x1800588d4  mov     [rsp+150h+var_110], rax
0x1800588d9  lea     rax, [rsp+150h+var_110]
0x1800588de  mov     [rsp+150h+var_108], rax
0x1800588e3  mov     byte ptr [rsp+150h+var_100], 1
0x1800588e8  mov     dword ptr [rbp+50h+var_A0], ebx
0x1800588eb  mov     eax, [r12]
0x1800588ef  mov     dword ptr [rbp+50h+var_A0+4], eax
0x1800588f2  mov     eax, [r12+4]
0x1800588f7  mov     [rbp+50h+var_98], eax
0x1800588fa  mov     ecx, [rbp+50h+arg_20]
0x180058900  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__FromAsg
0x180058905  mov     r9d, eax
0x180058908  mov     dword ptr [rbp+50h+cb], ebx
0x18005890b  mov     [rbp+50h+pv], rbx
0x18005890f  mov     rcx, [r14+8]
0x180058913  mov     dword ptr [rsp+150h+pExceptionObject], 313h
0x18005891b  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180058922  mov     [rsp+150h+var_E8], rax
0x180058927  mov     [rsp+150h+var_E0], rbx
0x18005892c  movsd   xmm0, [rbp+50h+var_A0]
0x180058931  movsd   qword ptr [rbp+50h+var_D0], xmm0
0x180058936  mov     edx, [rbp+50h+var_98]
0x180058939  mov     dword ptr [rbp+50h+var_D0+8], edx
0x18005893c  mov     rdx, [rcx]
0x18005893f  mov     rax, [rdx+30h]
0x180058943  lea     rdx, [rbp+50h+pv]
0x180058947  mov     [rsp+150h+var_128], rdx
0x18005894c  lea     rdx, [rbp+50h+cb]
0x180058950  mov     [rsp+150h+var_130], rdx
0x180058955  mov     r8, [rsp+150h+var_110]
0x18005895a  lea     rdx, [rbp+50h+var_D0]
0x18005895e  call    cs:__guard_dispatch_icall_fptr
0x180058964  test    eax, eax
0x180058966  js      loc_180058C7F
0x18005896c  mov     r12d, dword ptr [rbp+50h+cb]
0x180058970  mov     r13, [rbp+50h+pv]
0x180058974  mov     qword ptr [rbp+50h+var_90], r13
0x180058978  mov     dword ptr [rbp+50h+var_90+8], r12d
0x18005897c  lea     rcx, [rsp+150h+var_110]
0x180058981  call    ?Close@?$consume_Windows_Foundation_IClosable@UIBitmapBuffer@Imaging@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(void)
0x180058986  nop
0x180058987  cmp     [rsp+150h+var_110], rbx
0x18005898c  jz      short loc_180058999
0x18005898e  lea     rcx, [rsp+150h+var_110]
0x180058993  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058998  nop
0x180058999  lea     rcx, [rbp+50h+var_A8]
0x18005899d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800589a2  cmp     [rbp+50h+arg_18], 1
0x1800589a6  jnz     short loc_180058A08
0x1800589a8  mov     ecx, 28h ; '('; Size
0x1800589ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800589b2  mov     rdi, rax
0x1800589b5  mov     [rbp+50h+cb], rax
0x1800589b9  xorps   xmm0, xmm0
0x1800589bc  movups  xmmword ptr [rax], xmm0
0x1800589bf  mov     dword ptr [rax+8], 1
0x1800589c6  mov     dword ptr [rax+0Ch], 1
0x1800589cd  lea     rax, ??_7?$_Ref_count_obj2@U?$VectorDataWrapper@M@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>>::`vftable'
0x1800589d4  mov     [rdi], rax
0x1800589d7  lea     rbx, [rdi+10h]
0x1800589db  mov     qword ptr [rbp+50h+var_D0], r13
0x1800589df  mov     dword ptr [rbp+50h+var_D0+8], r12d
0x1800589e3  xor     eax, eax
0x1800589e5  mov     qword ptr [rbp+50h+var_90], rax
0x1800589e9  mov     dword ptr [rbp+50h+var_90+8], eax
0x1800589ec  lea     rdx, [rbp+50h+var_D0]
0x1800589f0  mov     rcx, rbx
0x1800589f3  call    ??0?$VectorDataWrapper@M@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@U?$com_array@M@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>::VectorDataWrapper<float>(winrt::com_array<float>)
0x1800589f8  nop
0x1800589f9  mov     [r15], rbx
0x1800589fc  mov     [r15+8], rdi
0x180058a00  mov     rax, r15
0x180058a03  jmp     loc_180058B39
0x180058a08  cmp     byte ptr [r14+18h], 0
0x180058a0d  jz      loc_180058C8F
0x180058a13  mov     rsi, rbx
0x180058a16  mov     qword ptr [rbp+50h+var_D0], rbx
0x180058a1a  mov     r15d, ebx
0x180058a1d  mov     dword ptr [rbp+50h+var_D0+8], ebx
0x180058a20  test    r12d, r12d
0x180058a23  jz      short loc_180058A57
0x180058a25  mov     rcx, r12; cb
0x180058a28  call    WINRT_IMPL_CoTaskMemAlloc
0x180058a2d  mov     rsi, rax
0x180058a30  mov     qword ptr [rbp+50h+var_D0], rax
0x180058a34  test    rax, rax
0x180058a37  jz      loc_180058B63
0x180058a3d  mov     r15d, r12d
0x180058a40  mov     dword ptr [rbp+50h+var_D0+8], r12d
0x180058a44  test    r12d, r12d
0x180058a47  jz      short loc_180058A57
0x180058a49  mov     r8, r12; Size
0x180058a4c  xor     edx, edx; Val
0x180058a4e  mov     rcx, rax; void *
0x180058a51  call    memset
0x180058a56  nop
0x180058a57  mov     edi, ebx
0x180058a59  test    r15d, r15d
0x180058a5c  jz      short loc_180058ACD
0x180058a5e  movss   xmm7, cs:__real@437f0000
0x180058a66  xorps   xmm8, xmm8
0x180058a6a  nop     word ptr [rax+rax+00h]
0x180058a70  cmp     byte ptr [r14+18h], 0
0x180058a75  jz      loc_180058B7F
0x180058a7b  mov     ebx, edi
0x180058a7d  movss   xmm6, dword ptr [r14+14h]
0x180058a83  movss   xmm0, dword ptr [r13+rbx*4+0]
0x180058a8a  divss   xmm0, dword ptr [r14+10h]; X
0x180058a90  call    nearbyintf
0x180058a95  addss   xmm6, xmm0
0x180058a99  movss   dword ptr [rbp+50h+cb], xmm6
0x180058a9e  mov     dword ptr [rsp+150h+var_110], 437F0000h
0x180058aa6  lea     rax, [rbp+50h+cb]
0x180058aaa  lea     rcx, [rsp+150h+var_110]
0x180058aaf  comiss  xmm7, xmm6
0x180058ab2  cmovbe  rax, rcx
0x180058ab6  movss   xmm0, dword ptr [rax]
0x180058aba  maxss   xmm0, xmm8
0x180058abf  cvttss2si eax, xmm0
0x180058ac3  mov     [rbx+rsi], al
0x180058ac6  inc     edi
0x180058ac8  cmp     edi, r15d
0x180058acb  jb      short loc_180058A70
0x180058acd  mov     ecx, 28h ; '('; Size
0x180058ad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058ad7  mov     rdi, rax
0x180058ada  mov     [rbp+50h+cb], rax
0x180058ade  xorps   xmm0, xmm0
0x180058ae1  movups  xmmword ptr [rax], xmm0
0x180058ae4  mov     dword ptr [rax+8], 1
0x180058aeb  mov     dword ptr [rax+0Ch], 1
0x180058af2  lea     rax, ??_7?$_Ref_count_obj2@U?$VectorDataWrapper@E@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<uchar>>::`vftable'
0x180058af9  mov     [rdi], rax
0x180058afc  lea     rbx, [rdi+10h]
0x180058b00  mov     [rbp+50h+var_A0], rsi
0x180058b04  mov     [rbp+50h+var_98], r15d
0x180058b08  xor     eax, eax
0x180058b0a  mov     qword ptr [rbp+50h+var_D0], rax
0x180058b0e  mov     dword ptr [rbp+50h+var_D0+8], eax
0x180058b11  lea     rdx, [rbp+50h+var_A0]
0x180058b15  mov     rcx, rbx
0x180058b18  call    ??0?$VectorDataWrapper@E@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@U?$com_array@E@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<uchar>::VectorDataWrapper<uchar>(winrt::com_array<uchar>)
0x180058b1d  nop
0x180058b1e  mov     rsi, [rbp+50h+arg_8]
0x180058b22  mov     [rsi], rbx
0x180058b25  mov     [rsi+8], rdi
0x180058b29  test    r13, r13
0x180058b2c  jz      short loc_180058B36
0x180058b2e  mov     rcx, r13; pv
0x180058b31  call    CoTaskMemFree_0
0x180058b36  mov     rax, rsi
0x180058b39  lea     r11, [rsp+150h+var_30]
0x180058b41  mov     rbx, [r11+50h]
0x180058b45  movaps  xmm6, xmmword ptr [r11-10h]
0x180058b4a  movaps  xmm7, xmmword ptr [r11-20h]
0x180058b4f  movaps  xmm8, xmmword ptr [r11-30h]
0x180058b54  mov     rsp, r11
0x180058b57  pop     r15
0x180058b59  pop     r14
0x180058b5b  pop     r13
0x180058b5d  pop     r12
0x180058b5f  pop     rdi
0x180058b60  pop     rsi
0x180058b61  pop     rbp
0x180058b62  retn
0x180058b63  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180058b68  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180058b6d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180058b74  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180058b79  call    _CxxThrowException
0x180058b7f  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180058b85  mov     dword ptr [rsp+150h+var_108], 73h ; 's'
0x180058b8d  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180058b94  mov     [rsp+150h+var_100], rax
0x180058b99  mov     [rsp+150h+var_F8], rdi
0x180058b9e  lea     rdx, aUnsupportedEmb; "Unsupported embedding element type"
0x180058ba5  lea     rcx, [rbp+50h+var_90]; this
0x180058ba9  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180058bae  lea     r8, [rsp+150h+var_108]; struct winrt::impl::slim_source_location *
0x180058bb3  lea     rdx, [rbp+50h+var_90]; struct winrt::param::hstring *
0x180058bb7  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180058bbc  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180058bc1  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180058bc8  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180058bcd  call    _CxxThrowException
0x180058bd3  mov     dword ptr [rsp+150h+var_108], 79h ; 'y'
0x180058bdb  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180058be2  mov     [rsp+150h+var_100], rax
  ... truncated ...
```
