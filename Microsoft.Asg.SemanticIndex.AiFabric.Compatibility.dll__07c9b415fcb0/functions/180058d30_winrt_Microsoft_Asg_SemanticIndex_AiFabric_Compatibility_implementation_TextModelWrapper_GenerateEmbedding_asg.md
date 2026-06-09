# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper::GenerateEmbedding(asg::SemanticRegistry::TextEmbeddingTokens,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::ExecutionPriorityHint)

- ea: `0x180058d30`
- end: `0x180059490`
- name: `?GenerateEmbedding@TextModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UEAA?AV?$shared_ptr@UIVectorData@SemanticRegistry@asg@@@std@@UTextEmbeddingTokens@SemanticRegistry@asg@@W4EmbeddingElementType@SemanticRegistry@asg@@W4ExecutionPriorityHint@SemanticRegistry@asg@@@Z`
- size: `1888`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180004280`
- `0x180007ba0`
- `0x18000cc40`
- `0x18000d230`
- `0x180010dd0`
- `0x18001fc60`
- `0x180057f20`
- `0x180058670`
- `0x180058d30`
- `0x18005ee40`
- `0x18005fd00`
- `0x18005fdd0`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`
- `0x18020c450`
- `0x18022ae90`
- `0x18022aeae`
- `0x180242120`
- `0x1802421a0`
- `0x180242860`

## string_xrefs

- `0x180059027`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180058fc1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18005932e`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18005937a`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180059449`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18005938b`: `tokens.TokenText has too many tokens to embed`
- `0x1800593df`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\common_includes\ComHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper::GenerateEmbedding(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        unsigned int a4,
        unsigned int a5)
{
  _QWORD *v6; // r12
  unsigned __int64 v8; // rsi
  char *v9; // rcx
  __int64 v10; // r13
  _QWORD *v11; // r15
  void *v12; // rcx
  char *v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rsi
  _QWORD *v16; // r8
  unsigned __int64 v17; // rbx
  _QWORD *v18; // rsi
  _DWORD *v19; // rdi
  int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  SIZE_T v24; // r15
  float *v25; // r13
  _DWORD *v26; // rdi
  void *v27; // rcx
  _BYTE *v29; // rsi
  unsigned int v30; // r12d
  _BYTE *v31; // rax
  unsigned int i; // edi
  float v33; // xmm6_4
  SIZE_T *p_cb; // rax
  _DWORD *v35; // rdi
  __int128 v36; // [rsp+40h] [rbp-C8h] BYREF
  const char *v37; // [rsp+50h] [rbp-B8h]
  __int64 v38; // [rsp+58h] [rbp-B0h]
  SIZE_T Src; // [rsp+68h] [rbp-A0h] BYREF
  void *Src_8[2]; // [rsp+70h] [rbp-98h] BYREF
  char *v41; // [rsp+80h] [rbp-88h]
  int pExceptionObject; // [rsp+88h] [rbp-80h] BYREF
  const char *v43; // [rsp+90h] [rbp-78h]
  __int64 v44; // [rsp+98h] [rbp-70h]
  _QWORD *v45; // [rsp+A0h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  int v47; // [rsp+B0h] [rbp-58h]
  _OWORD v48[6]; // [rsp+C8h] [rbp-40h] BYREF
  SIZE_T cb; // [rsp+168h] [rbp+60h] BYREF
  _QWORD *v50; // [rsp+170h] [rbp+68h]
  unsigned int v51; // [rsp+180h] [rbp+78h]

  v51 = a4;
  v50 = a2;
  v6 = a2;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 8LL))(a1, a4) )
  {
    DWORD2(v36) = 194;
    v37 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v38 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v48, L"Unsupported embedding element type");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v48,
      (const struct winrt::impl::slim_source_location *)((char *)&v36 + 8));
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v8 = a3[1];
  if ( v8 > 0xFFFFFFFF )
  {
    DWORD2(v36) = 199;
    v37 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
    v38 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v48, L"tokens.TokenText has too many tokens to embed");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v48,
      (const struct winrt::impl::slim_source_location *)((char *)&v36 + 8));
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  *(_OWORD *)Src_8 = 0;
  v9 = 0;
  v41 = 0;
  if ( v8 )
  {
    _mm_lfence();
    v10 = v8;
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v8);
    memmove(v11, Src_8[0], (char *)Src_8[1] - (char *)Src_8[0]);
    v12 = Src_8[0];
    if ( Src_8[0] )
    {
      if ( ((v41 - (char *)Src_8[0]) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
      {
        v12 = (void *)*((_QWORD *)Src_8[0] - 1);
        if ( (unsigned __int64)((char *)Src_8[0] - (char *)v12 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v12);
    }
    Src_8[0] = v11;
    v13 = (char *)v11;
    Src_8[1] = v11;
    v9 = (char *)&v11[v10];
    v41 = (char *)&v11[v10];
  }
  else
  {
    v13 = (char *)Src_8[1];
    v11 = Src_8[0];
  }
  v14 = *a3;
  v15 = v14 + 24 * v8;
  if ( v14 != v15 )
  {
    while ( 1 )
    {
      v16 = (_QWORD *)(v14 + 8);
      if ( v13 == v9 )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(Src_8, v13, v16);
        v13 = (char *)Src_8[1];
      }
      else
      {
        *(_QWORD *)v13 = *v16;
        v13 = (char *)Src_8[1] + 8;
        Src_8[1] = (char *)Src_8[1] + 8;
      }
      v14 += 24;
      if ( v14 == v15 )
        break;
      v9 = v41;
    }
    v11 = Src_8[0];
  }
  v48[0] = 0u;
  cb = 0;
  v17 = (v13 - (char *)v11) >> 3;
  if ( v17 > 0xFFFFFFFF )
  {
    DWORD2(v36) = 217;
    v37 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\common_includes\\ComHelpers.h";
    v38 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)&pv, L"span is too large to represent using IMemoryBuffer");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)&pv,
      (const struct winrt::impl::slim_source_location *)((char *)&v36 + 8));
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v18 = operator new(0x40u);
  v45 = v18;
  *((_QWORD *)&v36 + 1) = v11;
  LODWORD(v37) = 8 * v17;
  v18[1] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable';
  v18[2] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable';
  *v18 = &winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v18[4] = 1;
  *v18 = &CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v18[3] = &CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v19 = operator new(0x38u);
  pv = v19;
  *(_OWORD *)v19 = 0;
  v19[2] = 1;
  v19[3] = 1;
  *(_QWORD *)v19 = &std::_Ref_count_obj2<MemoryLifetime>::`vftable';
  MemoryLifetime::MemoryLifetime(v19 + 4, (char *)&v36 + 8, &cb);
  v18[5] = 0;
  v18[6] = v19 + 4;
  v18[7] = v19;
  *v18 = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v18[3] = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v45 = v18 + 1;
  if ( cb )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&cb);
  cb = 0;
  DWORD2(v36) = 507;
  v37 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v38 = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD *, SIZE_T *))(v18[1] + 48LL))(v18 + 1, &cb);
  if ( v20 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v20, (char *)&v36 + 8);
  }
  Src = cb;
  *((_QWORD *)&v36 + 1) = &Src;
  LOBYTE(v37) = 1;
  v21 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::FromAsg(a5);
  LODWORD(cb) = 0;
  pv = 0;
  v22 = *(_QWORD *)(a1 + 8);
  pExceptionObject = 4015;
  v43 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v44 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, signed __int64, SIZE_T, _QWORD, SIZE_T *, LPVOID *))(*(_QWORD *)v22 + 48LL))(
          v22,
          ((char *)Src_8[1] - (char *)Src_8[0]) >> 3,
          Src,
          v21,
          &cb,
          &pv);
  if ( v23 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v23, &pExceptionObject);
  }
  v24 = (unsigned int)cb;
  v25 = (float *)pv;
  *(_QWORD *)&v48[0] = pv;
  DWORD2(v48[0]) = cb;
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(&Src);
  if ( Src )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&Src);
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v45);
  if ( v51 == 1 )
  {
    v26 = operator new(0x28u);
    cb = (SIZE_T)v26;
    *(_OWORD *)v26 = 0;
    v26[2] = 1;
    v26[3] = 1;
    *(_QWORD *)v26 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>>::`vftable';
    *((_QWORD *)&v36 + 1) = v25;
    LODWORD(v37) = v24;
    *(_QWORD *)&v48[0] = 0;
    DWORD2(v48[0]) = 0;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>::VectorDataWrapper<float>(
      v26 + 4,
      (char *)&v36 + 8);
    *v6 = v26 + 4;
    v6[1] = v26;
    v27 = Src_8[0];
    if ( Src_8[0] )
    {
      if ( ((v41 - (char *)Src_8[0]) & 0xFFFFFFFFFFFFFFF8uLL) < 0x1000
        || (v27 = (void *)*((_QWORD *)Src_8[0] - 1), (unsigned __int64)((char *)Src_8[0] - (char *)v27 - 8) <= 0x1F) )
      {
LABEL_28:
        operator delete(v27);
        return v6;
      }
LABEL_46:
      invoke_watson(0, 0, 0, 0, 0);
    }
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 24) )
    {
      pExceptionObject = 231;
      v43 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
      v44 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)&pv,
        L"Cannot produce quantized embedding without quantization parameters");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)((char *)&v36 + 8),
        (const struct winrt::param::hstring *)&pv,
        (const struct winrt::impl::slim_source_location *)&pExceptionObject);
      throw (winrt::hresult_invalid_argument *)((char *)&v36 + 8);
    }
    v29 = 0;
    pv = 0;
    v30 = 0;
    v47 = 0;
    if ( (_DWORD)v24 )
    {
      v31 = WINRT_IMPL_CoTaskMemAlloc(v24);
      v29 = v31;
      pv = v31;
      if ( !v31 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
        throw (std::bad_alloc *)&pExceptionObject;
      }
      v30 = v24;
      v47 = v24;
      memset(v31, 0, v24);
    }
    for ( i = 0; i < v30; ++i )
    {
      if ( !*(_BYTE *)(a1 + 24) )
        std::_Throw_bad_optional_access();
      v33 = *(float *)(a1 + 20);
      *(float *)&cb = v33 + nearbyintf(v25[i] / *(float *)(a1 + 16));
      LODWORD(Src) = 1132396544;
      p_cb = &cb;
      if ( *(float *)&cb >= 255.0 )
        p_cb = &Src;
      v29[i] = (int)fmaxf(*(float *)p_cb, 0.0);
    }
    v35 = operator new(0x28u);
    cb = (SIZE_T)v35;
    *(_OWORD *)v35 = 0;
    v35[2] = 1;
    v35[3] = 1;
    *(_QWORD *)v35 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<unsigned char>>::`vftable';
    *((_QWORD *)&v36 + 1) = v29;
    LODWORD(v37) = v30;
    pv = 0;
    v47 = 0;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<unsigned char>::VectorDataWrapper<unsigned char>(
      v35 + 4,
      (char *)&v36 + 8);
    v6 = v50;
    *v50 = v35 + 4;
    v6[1] = v35;
    if ( v25 )
      CoTaskMemFree_0(v25);
    v27 = Src_8[0];
    if ( Src_8[0] )
    {
      if ( ((v41 - (char *)Src_8[0]) & 0xFFFFFFFFFFFFFFF8uLL) < 0x1000 )
        goto LABEL_28;
      v27 = (void *)*((_QWORD *)Src_8[0] - 1);
      if ( (unsigned __int64)((char *)Src_8[0] - (char *)v27 - 8) <= 0x1F )
        goto LABEL_28;
      goto LABEL_46;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180058d30  mov     rax, rsp
0x180058d33  mov     [rax+18h], rbx
0x180058d37  mov     [rax+20h], r9d
0x180058d3b  mov     [rax+10h], rdx
0x180058d3f  push    rbp
0x180058d40  push    rsi
0x180058d41  push    rdi
0x180058d42  push    r12
0x180058d44  push    r13
0x180058d46  push    r14
0x180058d48  push    r15
0x180058d4a  lea     rbp, [rax-58h]
0x180058d4e  sub     rsp, 120h
0x180058d55  movaps  xmmword ptr [rax-48h], xmm6
0x180058d59  movaps  xmmword ptr [rax-58h], xmm7
0x180058d5d  movaps  xmmword ptr [rax-68h], xmm8
0x180058d62  mov     rdi, r8
0x180058d65  mov     r12, rdx
0x180058d68  mov     r14, rcx
0x180058d6b  xor     r13d, r13d
0x180058d6e  mov     rax, [rcx]
0x180058d71  mov     edx, r9d
0x180058d74  mov     rax, [rax+8]
0x180058d78  call    cs:__guard_dispatch_icall_fptr
0x180058d7e  test    al, al
0x180058d80  jz      loc_180059326
0x180058d86  mov     rsi, [rdi+8]
0x180058d8a  mov     eax, 0FFFFFFFFh
0x180058d8f  cmp     rsi, rax
0x180058d92  ja      loc_180059372
0x180058d98  xorps   xmm0, xmm0
0x180058d9b  movdqu  xmmword ptr [rsp+150h+Src+8], xmm0
0x180058da1  mov     ecx, r13d
0x180058da4  mov     [rsp+150h+var_D8], rcx
0x180058da9  test    rsi, rsi
0x180058dac  jz      loc_180058E38
0x180058db2  lfence
0x180058db5  lea     r13, ds:0[rsi*8]
0x180058dbd  mov     rcx, r13
0x180058dc0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180058dc5  mov     r15, rax
0x180058dc8  mov     r8, [rsp+150h+var_E0]
0x180058dcd  mov     rdx, [rsp+150h+Src+8]; Src
0x180058dd2  sub     r8, rdx; Size
0x180058dd5  mov     rcx, rax; void *
0x180058dd8  call    memmove
0x180058ddd  mov     rcx, [rsp+150h+Src+8]
0x180058de2  test    rcx, rcx
0x180058de5  jz      short loc_180058E1D
0x180058de7  mov     rdx, [rsp+150h+var_D8]
0x180058dec  sub     rdx, rcx
0x180058def  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180058df3  mov     rax, rcx
0x180058df6  cmp     rdx, 1000h
0x180058dfd  jb      short loc_180058E18
0x180058dff  add     rdx, 27h ; '''
0x180058e03  mov     rcx, [rcx-8]; Block
0x180058e07  sub     rax, rcx
0x180058e0a  sub     rax, 8
0x180058e0e  cmp     rax, 1Fh
0x180058e12  ja      loc_1800593BE
0x180058e18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180058e1d  mov     [rsp+150h+Src+8], r15
0x180058e22  mov     rbx, r15
0x180058e25  mov     [rsp+150h+var_E0], rbx
0x180058e2a  lea     rcx, [r15+r13]
0x180058e2e  mov     [rsp+150h+var_D8], rcx
0x180058e33  xor     r13d, r13d
0x180058e36  jmp     short loc_180058E42
0x180058e38  mov     rbx, [rsp+150h+var_E0]
0x180058e3d  mov     r15, [rsp+150h+Src+8]
0x180058e42  mov     rdi, [rdi]
0x180058e45  lea     rax, [rsi+rsi*2]
0x180058e49  lea     rsi, [rdi+rax*8]
0x180058e4d  cmp     rdi, rsi
0x180058e50  jz      short loc_180058E98
0x180058e52  lea     r8, [rdi+8]
0x180058e56  cmp     rbx, rcx
0x180058e59  jz      short loc_180058E71
0x180058e5b  mov     rax, [r8]
0x180058e5e  mov     [rbx], rax
0x180058e61  mov     rbx, [rsp+150h+var_E0]
0x180058e66  add     rbx, 8
0x180058e6a  mov     [rsp+150h+var_E0], rbx
0x180058e6f  jmp     short loc_180058E83
0x180058e71  mov     rdx, rbx
0x180058e74  lea     rcx, [rsp+150h+Src+8]
0x180058e79  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x180058e7e  mov     rbx, [rsp+150h+var_E0]
0x180058e83  add     rdi, 18h
0x180058e87  cmp     rdi, rsi
0x180058e8a  jz      short loc_180058E93
0x180058e8c  mov     rcx, [rsp+150h+var_D8]
0x180058e91  jmp     short loc_180058E52
0x180058e93  mov     r15, [rsp+150h+Src+8]
0x180058e98  xorps   xmm0, xmm0
0x180058e9b  movups  [rbp+50h+var_90], xmm0
0x180058e9f  mov     qword ptr [rbp+50h+var_90], r13
0x180058ea3  mov     dword ptr [rbp+50h+var_90+8], r13d
0x180058ea7  mov     [rbp+50h+cb], r13
0x180058eab  sub     rbx, r15
0x180058eae  sar     rbx, 3
0x180058eb2  mov     eax, 0FFFFFFFFh
0x180058eb7  cmp     rbx, rax
0x180058eba  ja      loc_1800593D7
0x180058ec0  lea     ebx, ds:0[rbx*8]
0x180058ec7  mov     ecx, 40h ; '@'; Size
0x180058ecc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058ed1  mov     rsi, rax
0x180058ed4  mov     [rbp+50h+var_B8], rax
0x180058ed8  mov     qword ptr [rsp+150h+var_118+8], r15
0x180058edd  mov     dword ptr [rsp+150h+var_108], ebx
0x180058ee1  mov     ecx, dword ptr [rsp+150h+var_108+4]
0x180058ee5  mov     dword ptr [rsp+150h+var_108+4], ecx
0x180058ee9  lea     r15, [rax+8]
0x180058eed  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable'
0x180058ef4  mov     [r15], rax
0x180058ef7  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIClosable@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable'
0x180058efe  mov     [rsi+10h], rax
0x180058f02  lea     rax, ??_7?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable'
0x180058f09  mov     [rsi], rax
0x180058f0c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180058f13  mov     qword ptr [rsi+20h], 1
0x180058f1b  lea     rax, ??_7CustomMemoryBuffer@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x180058f22  mov     [rsi], rax
0x180058f25  lea     rax, ??_7CustomMemoryBuffer@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x180058f2c  mov     [rsi+18h], rax
0x180058f30  mov     ecx, 38h ; '8'; Size
0x180058f35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058f3a  mov     rdi, rax
0x180058f3d  mov     [rbp+50h+pv], rax
0x180058f41  xorps   xmm0, xmm0
0x180058f44  movups  xmmword ptr [rax], xmm0
0x180058f47  mov     dword ptr [rax+8], 1
0x180058f4e  mov     dword ptr [rax+0Ch], 1
0x180058f55  lea     rax, ??_7?$_Ref_count_obj2@UMemoryLifetime@@@std@@6B@; const std::_Ref_count_obj2<MemoryLifetime>::`vftable'
0x180058f5c  mov     [rdi], rax
0x180058f5f  lea     rbx, [rdi+10h]
0x180058f63  movaps  xmm0, [rsp+150h+var_118+8]
0x180058f68  movdqa  [rsp+150h+var_118+8], xmm0
0x180058f6e  lea     r8, [rbp+50h+cb]
0x180058f72  lea     rdx, [rsp+150h+var_118+8]
0x180058f77  mov     rcx, rbx
0x180058f7a  call    ??0MemoryLifetime@@QEAA@U?$array_view@E@winrt@@AEBUDeferralCompletedHandler@Foundation@Windows@2@@Z; MemoryLifetime::MemoryLifetime(winrt::array_view<uchar>,winrt::Windows::Foundation::DeferralCompletedHandler const &)
0x180058f7f  nop
0x180058f80  mov     [rsi+28h], r13
0x180058f84  mov     [rsi+30h], rbx
0x180058f88  mov     [rsi+38h], rdi
0x180058f8c  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x180058f93  mov     [rsi], rax
0x180058f96  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x180058f9d  mov     [rsi+18h], rax
0x180058fa1  mov     [rbp+50h+var_B8], r15
0x180058fa5  cmp     [rbp+50h+cb], 0
0x180058faa  jz      short loc_180058FB5
0x180058fac  lea     rcx, [rbp+50h+cb]
0x180058fb0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058fb5  mov     [rbp+50h+cb], r13
0x180058fb9  mov     dword ptr [rsp+150h+var_118+8], 1FBh
0x180058fc1  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180058fc8  mov     [rsp+150h+var_108], rax
0x180058fcd  mov     [rsp+150h+var_100], r13
0x180058fd2  mov     rax, [r15]
0x180058fd5  lea     rdx, [rbp+50h+cb]
0x180058fd9  mov     rcx, r15
0x180058fdc  mov     rax, [rax+30h]
0x180058fe0  call    cs:__guard_dispatch_icall_fptr
0x180058fe6  test    eax, eax
0x180058fe8  js      loc_180059423
0x180058fee  mov     rax, [rbp+50h+cb]
0x180058ff2  mov     [rsp+150h+Src], rax
0x180058ff7  lea     rax, [rsp+150h+Src]
0x180058ffc  mov     qword ptr [rsp+150h+var_118+8], rax
0x180059001  mov     byte ptr [rsp+150h+var_108], 1
0x180059006  mov     ecx, [rbp+50h+arg_20]
0x18005900c  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__FromAsg
0x180059011  mov     r9d, eax
0x180059014  mov     dword ptr [rbp+50h+cb], r13d
0x180059018  mov     [rbp+50h+pv], r13
0x18005901c  mov     rcx, [r14+8]
0x180059020  mov     [rbp+50h+pExceptionObject], 0FAFh
0x180059027  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18005902e  mov     [rbp+50h+var_C8], rax
0x180059032  mov     [rbp+50h+var_C0], r13
0x180059036  mov     rdx, [rsp+150h+var_E0]
0x18005903b  sub     rdx, [rsp+150h+Src+8]
0x180059040  sar     rdx, 3
0x180059044  mov     r8, [rcx]
0x180059047  mov     rax, [r8+30h]
0x18005904b  lea     r8, [rbp+50h+pv]
0x18005904f  mov     [rsp+150h+var_128], r8
0x180059054  lea     r8, [rbp+50h+cb]
0x180059058  mov     [rsp+150h+Reserved], r8
0x18005905d  mov     r8, [rsp+150h+Src]
0x180059062  call    cs:__guard_dispatch_icall_fptr
0x180059068  test    eax, eax
0x18005906a  js      loc_180059433
0x180059070  mov     r15d, dword ptr [rbp+50h+cb]
0x180059074  mov     r13, [rbp+50h+pv]
0x180059078  mov     qword ptr [rbp+50h+var_90], r13
0x18005907c  mov     dword ptr [rbp+50h+var_90+8], r15d
0x180059080  lea     rcx, [rsp+150h+Src]
0x180059085  call    ?Close@?$consume_Windows_Foundation_IClosable@UIBitmapBuffer@Imaging@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(void)
0x18005908a  nop
0x18005908b  cmp     [rsp+150h+Src], 0
0x180059091  jz      short loc_18005909E
0x180059093  lea     rcx, [rsp+150h+Src]
0x180059098  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005909d  nop
0x18005909e  lea     rcx, [rbp+50h+var_B8]
0x1800590a2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800590a7  cmp     [rbp+50h+arg_18], 1
0x1800590ab  jnz     loc_18005917D
0x1800590b1  mov     ecx, 28h ; '('; Size
0x1800590b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800590bb  mov     rdi, rax
0x1800590be  mov     [rbp+50h+cb], rax
0x1800590c2  xorps   xmm0, xmm0
0x1800590c5  movups  xmmword ptr [rax], xmm0
0x1800590c8  mov     dword ptr [rax+8], 1
0x1800590cf  mov     dword ptr [rax+0Ch], 1
0x1800590d6  lea     rax, ??_7?$_Ref_count_obj2@U?$VectorDataWrapper@M@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>>::`vftable'
0x1800590dd  mov     [rdi], rax
0x1800590e0  lea     rbx, [rdi+10h]
0x1800590e4  mov     qword ptr [rsp+150h+var_118+8], r13
0x1800590e9  mov     dword ptr [rsp+150h+var_108], r15d
0x1800590ee  xor     r15d, r15d
0x1800590f1  mov     qword ptr [rbp+50h+var_90], r15
0x1800590f5  mov     dword ptr [rbp+50h+var_90+8], r15d
0x1800590f9  lea     rdx, [rsp+150h+var_118+8]
0x1800590fe  mov     rcx, rbx
0x180059101  call    ??0?$VectorDataWrapper@M@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@U?$com_array@M@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorDataWrapper<float>::VectorDataWrapper<float>(winrt::com_array<float>)
0x180059106  nop
0x180059107  mov     [r12], rbx
0x18005910b  mov     [r12+8], rdi
0x180059110  mov     rcx, [rsp+150h+Src+8]
0x180059115  test    rcx, rcx
0x180059118  jz      short loc_180059150
0x18005911a  mov     rdx, [rsp+150h+var_D8]
0x18005911f  sub     rdx, rcx
0x180059122  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180059126  mov     rax, rcx
0x180059129  cmp     rdx, 1000h
0x180059130  jb      short loc_18005914B
0x180059132  add     rdx, 27h ; '''
0x180059136  mov     rcx, [rcx-8]; Block
0x18005913a  sub     rax, rcx
0x18005913d  sub     rax, 8
0x180059141  cmp     rax, 1Fh
0x180059145  ja      loc_18005930B
0x18005914b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180059150  mov     rax, r12
0x180059153  lea     r11, [rsp+150h+var_30]
0x18005915b  mov     rbx, [r11+50h]
0x18005915f  movaps  xmm6, xmmword ptr [r11-10h]
0x180059164  movaps  xmm7, xmmword ptr [r11-20h]
0x180059169  movaps  xmm8, xmmword ptr [r11-30h]
0x18005916e  mov     rsp, r11
0x180059171  pop     r15
0x180059173  pop     r14
0x180059175  pop     r13
0x180059177  pop     r12
0x180059179  pop     rdi
0x18005917a  pop     rsi
0x18005917b  pop     rbp
0x18005917c  retn
0x18005917d  cmp     byte ptr [r14+18h], 0
0x180059182  jz      loc_180059442
0x180059188  xor     esi, esi
0x18005918a  mov     [rbp+50h+pv], rsi
0x18005918e  xor     r12d, r12d
0x180059191  mov     [rbp+50h+var_A8], r12d
0x180059195  test    r15d, r15d
0x180059198  jz      short loc_1800591CC
0x18005919a  mov     rcx, r15; cb
0x18005919d  call    WINRT_IMPL_CoTaskMemAlloc
0x1800591a2  mov     rsi, rax
0x1800591a5  mov     [rbp+50h+pv], rax
0x1800591a9  test    rax, rax
0x1800591ac  jz      loc_1800592F1
0x1800591b2  mov     r12d, r15d
0x1800591b5  mov     [rbp+50h+var_A8], r15d
0x1800591b9  test    r15d, r15d
0x1800591bc  jz      short loc_1800591CC
0x1800591be  mov     r8, r15; Size
0x1800591c1  xor     edx, edx; Val
0x1800591c3  mov     rcx, rax; void *
0x1800591c6  call    memset
0x1800591cb  nop
0x1800591cc  xor     r15d, r15d
0x1800591cf  mov     edi, r15d
0x1800591d2  test    r12d, r12d
0x1800591d5  jz      short loc_18005923F
0x1800591d7  movss   xmm7, cs:__real@437f0000
0x1800591df  xorps   xmm8, xmm8
0x1800591e3  cmp     [r14+18h], r15b
0x1800591e7  jz      loc_180059320
0x1800591ed  mov     ebx, edi
0x1800591ef  movss   xmm6, dword ptr [r14+14h]
0x1800591f5  movss   xmm0, dword ptr [r13+rbx*4+0]
  ... truncated ...
```
