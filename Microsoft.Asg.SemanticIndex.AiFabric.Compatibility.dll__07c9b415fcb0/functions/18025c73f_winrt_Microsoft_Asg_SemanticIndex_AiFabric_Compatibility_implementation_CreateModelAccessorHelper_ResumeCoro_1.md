# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper__::_1_::catch$83

- ea: `0x18025c73f`
- end: `0x18025c9d4`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper__::_1_::catch$83`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003db0`
- `0x180003eb0`
- `0x180004a80`
- `0x180007de0`
- `0x180008720`
- `0x1800087f0`
- `0x18005e2a0`
- `0x1801d1d70`
- `0x1801d1da0`
- `0x1801d1dd0`
- `0x1801d1e70`
- `0x180206a58`
- `0x18025c73f`

## string_xrefs

- `0x18025c770`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025c7ac`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025c77e`: `struct winrt::fire_and_forget __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,class std::shared_ptr<struct asg::SemanticPipelines::ITextModelAccessor>,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModel`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper__::_1_::catch_83(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  char v10; // al
  __int64 v11; // rax
  char v12; // al

  v3 = *(_QWORD *)(a2 + 496);
  v4 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(v3 + 272) = 360;
  *(_DWORD *)(v3 + 276) = 48;
  *(_QWORD *)(v3 + 280) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpac"
                          "eModelRegistry.cpp";
  *(_QWORD *)(v3 + 288) = "struct winrt::fire_and_forget __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib"
                          "ility::implementation::CreateModelAccessorHelper<struct winrt::Microsoft::Asg::SemanticIndex::"
                          "AiFabric::Compatibility::ITextEmbeddingsModelFactory,class std::shared_ptr<struct asg::Semanti"
                          "cPipelines::ITextModelAccessor>,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compati"
                          "bility::ITextEmbeddingsModel,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil"
                          "ity::implementation::TextModelWrapper>(struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::"
                          "Compatibility::ITextEmbeddingsModelFactory,const class std::optional<struct asg::SemanticRegis"
                          "try::EmbeddingQuantizationParameters> &,class std::promise<class std::shared_ptr<struct asg::S"
                          "emanticPipelines::ITextModelAccessor> > &&)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(v3 + 296, v4, v3 + 272);
  *(_DWORD *)(v3 + 376) = 361;
  *(_QWORD *)(v3 + 384) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpac"
                          "eModelRegistry.cpp";
  *(_QWORD *)(v3 + 392) = 0;
  v5 = *(_QWORD *)(v3 + 344);
  *(_QWORD *)(a2 + 192) = v5;
  if ( (_DWORD)v5 )
  {
    v6 = *(_QWORD *)(v3 + 336);
    *(_QWORD *)(a2 + 184) = v6;
    if ( *(_WORD *)(v6 + 2LL * (unsigned int)v5) )
      abort();
    *(_DWORD *)(v3 + 408) = 1;
    *(_DWORD *)(v3 + 412) = v5;
    v7 = *(_QWORD *)(v3 + 336);
    *(_QWORD *)(a2 + 184) = v7;
    *(_QWORD *)(v3 + 424) = v7;
    *(_QWORD *)(v3 + 400) = v3 + 408;
  }
  else
  {
    *(_QWORD *)(v3 + 400) = 0;
  }
  *(_QWORD *)(v3 + 352) = 0;
  *(_DWORD *)(v3 + 360) = -1430532899;
  *(_DWORD *)(v3 + 364) = v4;
  *(_QWORD *)(v3 + 368) = 0;
  v8 = *(_QWORD *)(v3 + 400);
  *(_QWORD *)(a2 + 248) = v8;
  winrt::hresult_error::originate(v3 + 352, v4, v8, v3 + 376);
  *(_QWORD *)(v3 + 432) = 0;
  *(_QWORD *)(v3 + 440) = 0;
  __ExceptionPtrCreate((void *)(v3 + 432));
  __ExceptionPtrCopyException((void *)(v3 + 432), (const void *)(v3 + 352), &TI1_AUhresult_error_winrt__);
  if ( (*(_DWORD *)(v3 + 480) & 8) != 0 )
    __ExceptionPtrDestroy((void *)(v3 + 432));
  winrt::hresult_out_of_bounds::~hresult_out_of_bounds((winrt::hresult_out_of_bounds *)(v3 + 352));
  *(_QWORD *)(v3 + 448) = 0;
  *(_QWORD *)(v3 + 456) = 0;
  __ExceptionPtrCopy((void *)(v3 + 448), (const void *)(v3 + 432));
  *(_QWORD *)(v3 + 496) = v3 + 448;
  v9 = *(_QWORD *)(v3 + 64);
  *(_QWORD *)(a2 + 64) = v9;
  if ( !v9
    || (v10 = *(_BYTE *)(v3 + 72), (*(_BYTE *)(a2 + 72) = v10) != 0)
    && (v11 = *(_QWORD *)(v3 + 64), *(_QWORD *)(a2 + 64) = v11, *(_BYTE *)(v11 + 200)) )
  {
    std::_Throw_future_error2(4);
  }
  *(_QWORD *)(v3 + 504) = 0;
  *(_QWORD *)(v3 + 512) = 0;
  __ExceptionPtrCopy((void *)(v3 + 504), (const void *)(v3 + 448));
  std::_State_manager<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::_Set_exception(v3 + 64, v3 + 504);
  __ExceptionPtrDestroy((void *)(v3 + 448));
  __ExceptionPtrDestroy((void *)(v3 + 432));
  v12 = *(_BYTE *)(v3 + 328);
  *(_BYTE *)(a2 + 176) = v12;
  if ( v12 )
    std::basic_string<char16_t>::_Tidy_deallocate(v3 + 296);
  return 0;
}

```

## disassembly

```asm
0x18025c73f  mov     [rsp+arg_8], rdx
0x18025c744  push    rbx
0x18025c745  push    rbp
0x18025c746  push    rdi
0x18025c747  sub     rsp, 20h
0x18025c74b  mov     rbp, rdx
0x18025c74e  mov     rbx, [rbp+1F0h]
0x18025c755  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18025c75a  mov     edi, eax
0x18025c75c  mov     dword ptr [rbx+110h], 168h
0x18025c766  mov     dword ptr [rbx+114h], 30h ; '0'
0x18025c770  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025c777  mov     [rbx+118h], rax
0x18025c77e  lea     rax, aStructWinrtFir; "struct winrt::fire_and_forget __cdecl w"...
0x18025c785  mov     [rbx+120h], rax
0x18025c78c  lea     r8, [rbx+110h]
0x18025c793  lea     rcx, [rbx+128h]
0x18025c79a  mov     edx, edi
0x18025c79c  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18025c7a1  nop
0x18025c7a2  mov     dword ptr [rbx+178h], 169h
0x18025c7ac  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025c7b3  mov     [rbx+180h], rax
0x18025c7ba  mov     qword ptr [rbx+188h], 0
0x18025c7c5  mov     rdx, [rbx+158h]
0x18025c7cc  mov     [rbp+0C0h], rdx
0x18025c7d3  test    edx, edx
0x18025c7d5  jnz     short loc_18025C7E4
0x18025c7d7  mov     qword ptr [rbx+190h], 0
0x18025c7e2  jmp     short loc_18025C834
0x18025c7e4  mov     rcx, [rbx+150h]
0x18025c7eb  mov     [rbp+0B8h], rcx
0x18025c7f2  mov     eax, edx
0x18025c7f4  cmp     word ptr [rcx+rax*2], 0
0x18025c7f9  jz      short loc_18025C801
0x18025c7fb  call    abort
0x18025c801  mov     dword ptr [rbx+198h], 1
0x18025c80b  mov     [rbx+19Ch], edx
0x18025c811  mov     rax, [rbx+150h]
0x18025c818  mov     [rbp+0B8h], rax
0x18025c81f  mov     [rbx+1A8h], rax
0x18025c826  lea     rax, [rbx+198h]
0x18025c82d  mov     [rbx+190h], rax
0x18025c834  mov     qword ptr [rbx+160h], 0
0x18025c83f  mov     dword ptr [rbx+168h], 0AABBCCDDh
0x18025c849  mov     [rbx+16Ch], edi
0x18025c84f  mov     qword ptr [rbx+170h], 0
0x18025c85a  mov     r8, [rbx+190h]
0x18025c861  mov     [rbp+0F8h], r8
0x18025c868  lea     r9, [rbx+178h]
0x18025c86f  lea     rcx, [rbx+160h]
0x18025c876  mov     edx, edi
0x18025c878  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18025c87d  mov     qword ptr [rbx+1B0h], 0
0x18025c888  mov     qword ptr [rbx+1B8h], 0
0x18025c893  lea     rcx, [rbx+1B0h]; void *
0x18025c89a  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18025c89f  lea     rdx, [rbx+160h]; void *
0x18025c8a6  lea     rcx, [rbx+1B0h]; void *
0x18025c8ad  lea     r8, _TI1?AUhresult_error@winrt@@; void *
0x18025c8b4  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18025c8b9  test    dword ptr [rbx+1E0h], 8
0x18025c8c3  jz      short loc_18025C8D1
0x18025c8c5  lea     rcx, [rbx+1B0h]; void *
0x18025c8cc  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c8d1  lea     rcx, [rbx+160h]; this
0x18025c8d8  call    ??1hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::~hresult_out_of_bounds(void)
0x18025c8dd  nop
0x18025c8de  mov     qword ptr [rbx+1C0h], 0
0x18025c8e9  mov     qword ptr [rbx+1C8h], 0
0x18025c8f4  lea     rdx, [rbx+1B0h]; void *
0x18025c8fb  lea     rcx, [rbx+1C0h]; void *
0x18025c902  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025c907  lea     rax, [rbx+1C0h]
0x18025c90e  mov     [rbx+1F0h], rax
0x18025c915  mov     rax, [rbx+40h]
0x18025c919  mov     [rbp+40h], rax
0x18025c91d  test    rax, rax
0x18025c920  jz      loc_18025C9C0
0x18025c926  movzx   eax, byte ptr [rbx+48h]
0x18025c92a  mov     [rbp+48h], al
0x18025c92d  test    al, al
0x18025c92f  jz      short loc_18025C942
0x18025c931  mov     rax, [rbx+40h]
0x18025c935  mov     [rbp+40h], rax
0x18025c939  cmp     byte ptr [rax+0C8h], 0
0x18025c940  jnz     short loc_18025C9C0
0x18025c942  mov     qword ptr [rbx+1F8h], 0
0x18025c94d  mov     qword ptr [rbx+200h], 0
0x18025c958  lea     rdx, [rbx+1C0h]; void *
0x18025c95f  lea     rcx, [rbx+1F8h]; void *
0x18025c966  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025c96b  lea     rdx, [rbx+1F8h]
0x18025c972  lea     rcx, [rbx+40h]
0x18025c976  call    ?_Set_exception@?$_State_manager@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_State_manager<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::_Set_exception(std::exception_ptr,bool)
0x18025c97b  nop
0x18025c97c  lea     rcx, [rbx+1C0h]; void *
0x18025c983  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c988  nop
0x18025c989  lea     rcx, [rbx+1B0h]; void *
0x18025c990  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c995  nop
0x18025c996  movzx   eax, byte ptr [rbx+148h]
0x18025c99d  mov     [rbp+0B0h], al
0x18025c9a3  test    al, al
0x18025c9a5  jz      short loc_18025C9B4
0x18025c9a7  lea     rcx, [rbx+128h]
0x18025c9ae  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18025c9b3  nop
0x18025c9b4  mov     rax, 0
0x18025c9be  jmp     short loc_18025C9CB
0x18025c9c0  mov     ecx, 4
0x18025c9c5  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18025c9cb  add     rsp, 20h
0x18025c9cf  pop     rdi
0x18025c9d0  pop     rbp
0x18025c9d1  pop     rbx
0x18025c9d2  retn
```
