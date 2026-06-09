# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper__::_1_::catch$83

- ea: `0x18025bfdf`
- end: `0x18025c274`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper__::_1_::catch$83`
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
- `0x18025bfdf`

## string_xrefs

- `0x18025c010`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025c04c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025c01e`: `struct winrt::fire_and_forget __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,class std::shared_ptr<struct asg::SemanticPipelines::IImageModelAccessor>,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageM`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper__::_1_::catch_83(
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
                          "AiFabric::Compatibility::IImageEmbeddingsModelFactory,class std::shared_ptr<struct asg::Semant"
                          "icPipelines::IImageModelAccessor>,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compa"
                          "tibility::IImageEmbeddingsModel,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compati"
                          "bility::implementation::ImageModelWrapper>(struct winrt::Microsoft::Asg::SemanticIndex::AiFabr"
                          "ic::Compatibility::IImageEmbeddingsModelFactory,const class std::optional<struct asg::Semantic"
                          "Registry::EmbeddingQuantizationParameters> &,class std::promise<class std::shared_ptr<struct a"
                          "sg::SemanticPipelines::IImageModelAccessor> > &&)";
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
0x18025bfdf  mov     [rsp+arg_8], rdx
0x18025bfe4  push    rbx
0x18025bfe5  push    rbp
0x18025bfe6  push    rdi
0x18025bfe7  sub     rsp, 20h
0x18025bfeb  mov     rbp, rdx
0x18025bfee  mov     rbx, [rbp+1F0h]
0x18025bff5  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18025bffa  mov     edi, eax
0x18025bffc  mov     dword ptr [rbx+110h], 168h
0x18025c006  mov     dword ptr [rbx+114h], 30h ; '0'
0x18025c010  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025c017  mov     [rbx+118h], rax
0x18025c01e  lea     rax, aStructWinrtFir_1; "struct winrt::fire_and_forget __cdecl w"...
0x18025c025  mov     [rbx+120h], rax
0x18025c02c  lea     r8, [rbx+110h]
0x18025c033  lea     rcx, [rbx+128h]
0x18025c03a  mov     edx, edi
0x18025c03c  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18025c041  nop
0x18025c042  mov     dword ptr [rbx+178h], 169h
0x18025c04c  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025c053  mov     [rbx+180h], rax
0x18025c05a  mov     qword ptr [rbx+188h], 0
0x18025c065  mov     rdx, [rbx+158h]
0x18025c06c  mov     [rbp+0C0h], rdx
0x18025c073  test    edx, edx
0x18025c075  jnz     short loc_18025C084
0x18025c077  mov     qword ptr [rbx+190h], 0
0x18025c082  jmp     short loc_18025C0D4
0x18025c084  mov     rcx, [rbx+150h]
0x18025c08b  mov     [rbp+0B8h], rcx
0x18025c092  mov     eax, edx
0x18025c094  cmp     word ptr [rcx+rax*2], 0
0x18025c099  jz      short loc_18025C0A1
0x18025c09b  call    abort
0x18025c0a1  mov     dword ptr [rbx+198h], 1
0x18025c0ab  mov     [rbx+19Ch], edx
0x18025c0b1  mov     rax, [rbx+150h]
0x18025c0b8  mov     [rbp+0B8h], rax
0x18025c0bf  mov     [rbx+1A8h], rax
0x18025c0c6  lea     rax, [rbx+198h]
0x18025c0cd  mov     [rbx+190h], rax
0x18025c0d4  mov     qword ptr [rbx+160h], 0
0x18025c0df  mov     dword ptr [rbx+168h], 0AABBCCDDh
0x18025c0e9  mov     [rbx+16Ch], edi
0x18025c0ef  mov     qword ptr [rbx+170h], 0
0x18025c0fa  mov     r8, [rbx+190h]
0x18025c101  mov     [rbp+0F8h], r8
0x18025c108  lea     r9, [rbx+178h]
0x18025c10f  lea     rcx, [rbx+160h]
0x18025c116  mov     edx, edi
0x18025c118  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18025c11d  mov     qword ptr [rbx+1B0h], 0
0x18025c128  mov     qword ptr [rbx+1B8h], 0
0x18025c133  lea     rcx, [rbx+1B0h]; void *
0x18025c13a  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18025c13f  lea     rdx, [rbx+160h]; void *
0x18025c146  lea     rcx, [rbx+1B0h]; void *
0x18025c14d  lea     r8, _TI1?AUhresult_error@winrt@@; void *
0x18025c154  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18025c159  test    dword ptr [rbx+1E0h], 8
0x18025c163  jz      short loc_18025C171
0x18025c165  lea     rcx, [rbx+1B0h]; void *
0x18025c16c  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c171  lea     rcx, [rbx+160h]; this
0x18025c178  call    ??1hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::~hresult_out_of_bounds(void)
0x18025c17d  nop
0x18025c17e  mov     qword ptr [rbx+1C0h], 0
0x18025c189  mov     qword ptr [rbx+1C8h], 0
0x18025c194  lea     rdx, [rbx+1B0h]; void *
0x18025c19b  lea     rcx, [rbx+1C0h]; void *
0x18025c1a2  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025c1a7  lea     rax, [rbx+1C0h]
0x18025c1ae  mov     [rbx+1F0h], rax
0x18025c1b5  mov     rax, [rbx+40h]
0x18025c1b9  mov     [rbp+40h], rax
0x18025c1bd  test    rax, rax
0x18025c1c0  jz      loc_18025C260
0x18025c1c6  movzx   eax, byte ptr [rbx+48h]
0x18025c1ca  mov     [rbp+48h], al
0x18025c1cd  test    al, al
0x18025c1cf  jz      short loc_18025C1E2
0x18025c1d1  mov     rax, [rbx+40h]
0x18025c1d5  mov     [rbp+40h], rax
0x18025c1d9  cmp     byte ptr [rax+0C8h], 0
0x18025c1e0  jnz     short loc_18025C260
0x18025c1e2  mov     qword ptr [rbx+1F8h], 0
0x18025c1ed  mov     qword ptr [rbx+200h], 0
0x18025c1f8  lea     rdx, [rbx+1C0h]; void *
0x18025c1ff  lea     rcx, [rbx+1F8h]; void *
0x18025c206  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025c20b  lea     rdx, [rbx+1F8h]
0x18025c212  lea     rcx, [rbx+40h]
0x18025c216  call    ?_Set_exception@?$_State_manager@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_State_manager<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::_Set_exception(std::exception_ptr,bool)
0x18025c21b  nop
0x18025c21c  lea     rcx, [rbx+1C0h]; void *
0x18025c223  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c228  nop
0x18025c229  lea     rcx, [rbx+1B0h]; void *
0x18025c230  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025c235  nop
0x18025c236  movzx   eax, byte ptr [rbx+148h]
0x18025c23d  mov     [rbp+0B0h], al
0x18025c243  test    al, al
0x18025c245  jz      short loc_18025C254
0x18025c247  lea     rcx, [rbx+128h]
0x18025c24e  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18025c253  nop
0x18025c254  mov     rax, 0
0x18025c25e  jmp     short loc_18025C26B
0x18025c260  mov     ecx, 4
0x18025c265  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18025c26b  add     rsp, 20h
0x18025c26f  pop     rdi
0x18025c270  pop     rbp
0x18025c271  pop     rbx
0x18025c272  retn
```
