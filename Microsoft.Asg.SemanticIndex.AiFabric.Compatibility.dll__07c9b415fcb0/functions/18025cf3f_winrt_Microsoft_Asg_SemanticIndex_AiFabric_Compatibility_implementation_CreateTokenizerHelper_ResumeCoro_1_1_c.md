# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper$_ResumeCoro$1_::_1_::catch$83

- ea: `0x18025cf3f`
- end: `0x18025d1d4`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper$_ResumeCoro$1_::_1_::catch$83`
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
- `0x18025cf3f`

## string_xrefs

- `0x18025cf70`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025cfac`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x18025cf7e`: `struct winrt::fire_and_forget __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper(struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,class std::promise<class std::shared_ptr<class asg::SemanticRegistry::ITokenizer> > &&)`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper__ResumeCoro_1_::_1_::catch_83(
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
  *(_DWORD *)(v3 + 264) = 405;
  *(_DWORD *)(v3 + 268) = 48;
  *(_QWORD *)(v3 + 272) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpac"
                          "eModelRegistry.cpp";
  *(_QWORD *)(v3 + 280) = "struct winrt::fire_and_forget __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib"
                          "ility::implementation::CreateTokenizerHelper(struct winrt::Microsoft::Asg::SemanticIndex::AiFa"
                          "bric::Compatibility::ITextEmbeddingsModelFactory,class std::promise<class std::shared_ptr<clas"
                          "s asg::SemanticRegistry::ITokenizer> > &&)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(v3 + 288, v4, v3 + 264);
  *(_DWORD *)(v3 + 368) = 406;
  *(_QWORD *)(v3 + 376) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpac"
                          "eModelRegistry.cpp";
  *(_QWORD *)(v3 + 384) = 0;
  v5 = *(_QWORD *)(v3 + 336);
  *(_QWORD *)(a2 + 192) = v5;
  if ( (_DWORD)v5 )
  {
    v6 = *(_QWORD *)(v3 + 328);
    *(_QWORD *)(a2 + 184) = v6;
    if ( *(_WORD *)(v6 + 2LL * (unsigned int)v5) )
      abort();
    *(_DWORD *)(v3 + 400) = 1;
    *(_DWORD *)(v3 + 404) = v5;
    v7 = *(_QWORD *)(v3 + 328);
    *(_QWORD *)(a2 + 184) = v7;
    *(_QWORD *)(v3 + 416) = v7;
    *(_QWORD *)(v3 + 392) = v3 + 400;
  }
  else
  {
    *(_QWORD *)(v3 + 392) = 0;
  }
  *(_QWORD *)(v3 + 344) = 0;
  *(_DWORD *)(v3 + 352) = -1430532899;
  *(_DWORD *)(v3 + 356) = v4;
  *(_QWORD *)(v3 + 360) = 0;
  v8 = *(_QWORD *)(v3 + 392);
  *(_QWORD *)(a2 + 248) = v8;
  winrt::hresult_error::originate(v3 + 344, v4, v8, v3 + 368);
  *(_QWORD *)(v3 + 424) = 0;
  *(_QWORD *)(v3 + 432) = 0;
  __ExceptionPtrCreate((void *)(v3 + 424));
  __ExceptionPtrCopyException((void *)(v3 + 424), (const void *)(v3 + 344), &TI1_AUhresult_error_winrt__);
  if ( (*(_DWORD *)(v3 + 472) & 8) != 0 )
    __ExceptionPtrDestroy((void *)(v3 + 424));
  winrt::hresult_out_of_bounds::~hresult_out_of_bounds((winrt::hresult_out_of_bounds *)(v3 + 344));
  *(_QWORD *)(v3 + 440) = 0;
  *(_QWORD *)(v3 + 448) = 0;
  __ExceptionPtrCopy((void *)(v3 + 440), (const void *)(v3 + 424));
  *(_QWORD *)(v3 + 488) = v3 + 440;
  v9 = *(_QWORD *)(v3 + 56);
  *(_QWORD *)(a2 + 64) = v9;
  if ( !v9
    || (v10 = *(_BYTE *)(v3 + 64), (*(_BYTE *)(a2 + 72) = v10) != 0)
    && (v11 = *(_QWORD *)(v3 + 56), *(_QWORD *)(a2 + 64) = v11, *(_BYTE *)(v11 + 200)) )
  {
    std::_Throw_future_error2(4);
  }
  *(_QWORD *)(v3 + 496) = 0;
  *(_QWORD *)(v3 + 504) = 0;
  __ExceptionPtrCopy((void *)(v3 + 496), (const void *)(v3 + 440));
  std::_State_manager<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::_Set_exception(v3 + 56, v3 + 496);
  __ExceptionPtrDestroy((void *)(v3 + 440));
  __ExceptionPtrDestroy((void *)(v3 + 424));
  v12 = *(_BYTE *)(v3 + 320);
  *(_BYTE *)(a2 + 176) = v12;
  if ( v12 )
    std::basic_string<char16_t>::_Tidy_deallocate(v3 + 288);
  return 0;
}

```

## disassembly

```asm
0x18025cf3f  mov     [rsp+arg_8], rdx
0x18025cf44  push    rbx
0x18025cf45  push    rbp
0x18025cf46  push    rdi
0x18025cf47  sub     rsp, 20h
0x18025cf4b  mov     rbp, rdx
0x18025cf4e  mov     rbx, [rbp+1F0h]
0x18025cf55  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18025cf5a  mov     edi, eax
0x18025cf5c  mov     dword ptr [rbx+108h], 195h
0x18025cf66  mov     dword ptr [rbx+10Ch], 30h ; '0'
0x18025cf70  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025cf77  mov     [rbx+110h], rax
0x18025cf7e  lea     rax, aStructWinrtFir_0; "struct winrt::fire_and_forget __cdecl w"...
0x18025cf85  mov     [rbx+118h], rax
0x18025cf8c  lea     r8, [rbx+108h]
0x18025cf93  lea     rcx, [rbx+120h]
0x18025cf9a  mov     edx, edi
0x18025cf9c  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18025cfa1  nop
0x18025cfa2  mov     dword ptr [rbx+170h], 196h
0x18025cfac  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18025cfb3  mov     [rbx+178h], rax
0x18025cfba  mov     qword ptr [rbx+180h], 0
0x18025cfc5  mov     rdx, [rbx+150h]
0x18025cfcc  mov     [rbp+0C0h], rdx
0x18025cfd3  test    edx, edx
0x18025cfd5  jnz     short loc_18025CFE4
0x18025cfd7  mov     qword ptr [rbx+188h], 0
0x18025cfe2  jmp     short loc_18025D034
0x18025cfe4  mov     rcx, [rbx+148h]
0x18025cfeb  mov     [rbp+0B8h], rcx
0x18025cff2  mov     eax, edx
0x18025cff4  cmp     word ptr [rcx+rax*2], 0
0x18025cff9  jz      short loc_18025D001
0x18025cffb  call    abort
0x18025d001  mov     dword ptr [rbx+190h], 1
0x18025d00b  mov     [rbx+194h], edx
0x18025d011  mov     rax, [rbx+148h]
0x18025d018  mov     [rbp+0B8h], rax
0x18025d01f  mov     [rbx+1A0h], rax
0x18025d026  lea     rax, [rbx+190h]
0x18025d02d  mov     [rbx+188h], rax
0x18025d034  mov     qword ptr [rbx+158h], 0
0x18025d03f  mov     dword ptr [rbx+160h], 0AABBCCDDh
0x18025d049  mov     [rbx+164h], edi
0x18025d04f  mov     qword ptr [rbx+168h], 0
0x18025d05a  mov     r8, [rbx+188h]
0x18025d061  mov     [rbp+0F8h], r8
0x18025d068  lea     r9, [rbx+170h]
0x18025d06f  lea     rcx, [rbx+158h]
0x18025d076  mov     edx, edi
0x18025d078  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18025d07d  mov     qword ptr [rbx+1A8h], 0
0x18025d088  mov     qword ptr [rbx+1B0h], 0
0x18025d093  lea     rcx, [rbx+1A8h]; void *
0x18025d09a  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18025d09f  lea     rdx, [rbx+158h]; void *
0x18025d0a6  lea     rcx, [rbx+1A8h]; void *
0x18025d0ad  lea     r8, _TI1?AUhresult_error@winrt@@; void *
0x18025d0b4  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18025d0b9  test    dword ptr [rbx+1D8h], 8
0x18025d0c3  jz      short loc_18025D0D1
0x18025d0c5  lea     rcx, [rbx+1A8h]; void *
0x18025d0cc  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025d0d1  lea     rcx, [rbx+158h]; this
0x18025d0d8  call    ??1hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::~hresult_out_of_bounds(void)
0x18025d0dd  nop
0x18025d0de  mov     qword ptr [rbx+1B8h], 0
0x18025d0e9  mov     qword ptr [rbx+1C0h], 0
0x18025d0f4  lea     rdx, [rbx+1A8h]; void *
0x18025d0fb  lea     rcx, [rbx+1B8h]; void *
0x18025d102  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025d107  lea     rax, [rbx+1B8h]
0x18025d10e  mov     [rbx+1E8h], rax
0x18025d115  mov     rax, [rbx+38h]
0x18025d119  mov     [rbp+40h], rax
0x18025d11d  test    rax, rax
0x18025d120  jz      loc_18025D1C0
0x18025d126  movzx   eax, byte ptr [rbx+40h]
0x18025d12a  mov     [rbp+48h], al
0x18025d12d  test    al, al
0x18025d12f  jz      short loc_18025D142
0x18025d131  mov     rax, [rbx+38h]
0x18025d135  mov     [rbp+40h], rax
0x18025d139  cmp     byte ptr [rax+0C8h], 0
0x18025d140  jnz     short loc_18025D1C0
0x18025d142  mov     qword ptr [rbx+1F0h], 0
0x18025d14d  mov     qword ptr [rbx+1F8h], 0
0x18025d158  lea     rdx, [rbx+1B8h]; void *
0x18025d15f  lea     rcx, [rbx+1F0h]; void *
0x18025d166  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18025d16b  lea     rdx, [rbx+1F0h]
0x18025d172  lea     rcx, [rbx+38h]
0x18025d176  call    ?_Set_exception@?$_State_manager@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_State_manager<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::_Set_exception(std::exception_ptr,bool)
0x18025d17b  nop
0x18025d17c  lea     rcx, [rbx+1B8h]; void *
0x18025d183  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025d188  nop
0x18025d189  lea     rcx, [rbx+1A8h]; void *
0x18025d190  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18025d195  nop
0x18025d196  movzx   eax, byte ptr [rbx+140h]
0x18025d19d  mov     [rbp+0B0h], al
0x18025d1a3  test    al, al
0x18025d1a5  jz      short loc_18025D1B4
0x18025d1a7  lea     rcx, [rbx+120h]
0x18025d1ae  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18025d1b3  nop
0x18025d1b4  mov     rax, 0
0x18025d1be  jmp     short loc_18025D1CB
0x18025d1c0  mov     ecx, 4
0x18025d1c5  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18025d1cb  add     rsp, 20h
0x18025d1cf  pop     rdi
0x18025d1d0  pop     rbp
0x18025d1d1  pop     rbx
0x18025d1d2  retn
```
