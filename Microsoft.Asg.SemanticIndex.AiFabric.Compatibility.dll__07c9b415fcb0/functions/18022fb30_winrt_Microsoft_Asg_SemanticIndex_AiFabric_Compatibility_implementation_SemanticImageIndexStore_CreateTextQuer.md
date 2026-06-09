# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorAsync$_ResumeCoro$1

- ea: `0x18022fb30`
- end: `0x18022ff90`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorAsync$_ResumeCoro$1`
- size: `1120`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001cfd0`
- `0x18022fb20`

## callees

- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000b2a0`
- `0x18000d230`
- `0x1800149d0`
- `0x18001b1f0`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020e60`
- `0x180047520`
- `0x1800611a0`
- `0x180062570`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x18022fb30`
- `0x180242ca0`

## string_xrefs

- `0x18022fc98`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022fd15`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`
- `0x18022fe3c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorAsync__ResumeCoro_1(
        __int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rdx
  _QWORD *v4; // rdx
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  volatile __int64 *v7; // rdi
  char v8; // r14
  volatile __int64 *v9; // rdi
  unsigned int *v10; // rax
  _QWORD *v11; // r14
  _QWORD *v12; // rdi
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE v15[24]; // [rsp+60h] [rbp-98h] BYREF
  __int64 v16; // [rsp+78h] [rbp-80h]

  switch ( *(_WORD *)(a1 + 152) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_43;
    case 2:
      *(_OWORD *)(a1 + 320) = *(_OWORD *)(a1 + 132);
      if ( memcmp(
             (const void *)(a1 + 320),
             &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId,
             0x10u) )
      {
        *(_DWORD *)(a1 + 280) = 221;
        *(_QWORD *)(a1 + 288) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
        *(_QWORD *)(a1 + 296) = 0;
        winrt::hresult_not_implemented::hresult_not_implemented(
          (winrt::hresult_not_implemented *)v14,
          (const struct winrt::impl::slim_source_location *)(a1 + 280));
        throw (winrt::hresult_not_implemented *)v14;
      }
      v2 = operator new(0x1B8u);
      *(_QWORD *)(a1 + 336) = v2;
      *(_OWORD *)(a1 + 352) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(v2);
      *v2 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable';
      v3 = v2 + 2;
      if ( !v2 )
        v3 = 0;
      *(_QWORD *)(a1 + 368) = v3;
      *(_QWORD *)(a1 + 160) = v3;
      if ( !*(_BYTE *)(a1 + 148) )
        goto LABEL_36;
      *(_QWORD *)(a1 + 168) = 0;
      if ( !v3 )
        goto LABEL_12;
      v4 = v3 - 2;
      if ( !v4 )
        goto LABEL_12;
      *(_QWORD *)(a1 + 168) = v4;
      v5 = v4[1];
      if ( v5 < 0 )
        goto LABEL_11;
      break;
    case 4:
      goto LABEL_27;
    case 5:
      v7 = *(volatile __int64 **)(a1 + 184);
      if ( v7 )
      {
        v16 = *(_QWORD *)(a1 + 184);
        while ( _InterlockedExchange64(v7, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 176) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
      if ( *(_QWORD *)(a1 + 168) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 168);
      if ( *(_QWORD *)(a1 + 368) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
      goto LABEL_43;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v6 = v5;
    v5 = _InterlockedCompareExchange64(v4 + 1, v5 + 1, v5);
    if ( v6 == v5 )
      break;
    if ( v5 < 0 )
    {
LABEL_11:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
      break;
    }
  }
LABEL_12:
  *(_BYTE *)(a1 + 408) = 0;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(
    *(_QWORD *)(a1 + 168),
    a1 + 176,
    a1 + 376);
  if ( *(_DWORD *)(a1 + 112) == 2 )
  {
    *(_DWORD *)(a1 + 416) = 5672;
    *(_QWORD *)(a1 + 424) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated F"
                            "iles\\winrt\\Windows.Foundation.h";
    *(_QWORD *)(a1 + 432) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)(a1 + 416));
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = a1 + 176;
  *(_QWORD *)(a1 + 200) = 0;
  *(_BYTE *)(a1 + 208) = 1;
  *(_WORD *)(a1 + 152) = 4;
  if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                           (_QWORD *)(a1 + 184),
                           a1) )
  {
LABEL_27:
    v8 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 184);
    v9 = *(volatile __int64 **)(a1 + 184);
    if ( v9 )
    {
      v16 = *(_QWORD *)(a1 + 184);
      while ( _InterlockedExchange64(v9, 0) == 1 )
        Thrd_yield();
    }
    if ( *(_QWORD *)(a1 + 176) )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
    if ( !v8 )
    {
      *(_DWORD *)(a1 + 216) = 212;
      *(_QWORD *)(a1 + 224) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
      *(_QWORD *)(a1 + 232) = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)(a1 + 240),
        L"Failed to load text query embedding model - migration of underlying index may be required");
      v10 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 272), -2081706723);
      winrt::hresult_error::hresult_error(v15, *v10, a1 + 240, a1 + 216);
      throw (winrt::hresult_error *)v15;
    }
    if ( *(_QWORD *)(a1 + 168) )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 168);
LABEL_36:
    v11 = (_QWORD *)(a1 + 120);
    v12 = (_QWORD *)(a1 + 160);
    if ( a1 + 120 != a1 + 160 )
    {
      if ( *v11 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
      *v12 = 0;
      *v11 = *(_QWORD *)(a1 + 368);
    }
    if ( *v12 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
    *(_QWORD *)(a1 + 304) = a1 + 16;
    *(_WORD *)(a1 + 152) = 0;
    *(_QWORD *)a1 = 0;
    if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 304) )
    {
LABEL_43:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 16);
      if ( *(_WORD *)(a1 + 154) )
        operator delete((void *)a1);
    }
  }
}

```

## disassembly

```asm
0x18022fb30  mov     [rsp+Block], rcx
0x18022fb35  push    rbx
0x18022fb36  push    rsi
0x18022fb37  push    rdi
0x18022fb38  push    r14
0x18022fb3a  push    r15
0x18022fb3c  sub     rsp, 0D0h
0x18022fb43  mov     rsi, [rsp+0F8h+Block]
0x18022fb4b  mov     [rsp+0F8h+arg_18], rsi
0x18022fb53  movzx   eax, word ptr [rsi+98h]
0x18022fb5a  mov     [rsp+0F8h+var_D8], ax
0x18022fb5f  inc     ax; switch 7 cases
0x18022fb62  cmp     ax, 6
0x18022fb66  ja      def_18022FB81; jumptable 000000018022FB81 default case, case 0
0x18022fb6c  movsx   rax, ax
0x18022fb70  lea     rdx, cs:180000000h
0x18022fb77  mov     ecx, ds:(jpt_18022FB81 - 180000000h)[rdx+rax*4]
0x18022fb7e  add     rcx, rdx
0x18022fb81  jmp     rcx; switch jump
0x18022fb83  jmp     loc_18022FF40; jumptable 000000018022FB81 case 3
0x18022fb88  xor     ebx, ebx; jumptable 000000018022FB81 case 2
0x18022fb8a  lea     rcx, [rsi+140h]; Buf1
0x18022fb91  movups  xmm0, xmmword ptr [rsi+84h]
0x18022fb98  movaps  xmmword ptr [rcx], xmm0
0x18022fb9b  mov     r15d, 10h
0x18022fba1  mov     r8d, r15d; Size
0x18022fba4  lea     rdx, ?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; Buf2
0x18022fbab  call    memcmp
0x18022fbb0  test    eax, eax
0x18022fbb2  jnz     loc_18022FD08
0x18022fbb8  mov     ecx, 1B8h; Size
0x18022fbbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022fbc2  mov     rdi, rax
0x18022fbc5  mov     [rsi+150h], rax
0x18022fbcc  lea     rdx, [rsi+160h]
0x18022fbd3  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x18022fbda  movaps  xmmword ptr [rdx], xmm0
0x18022fbdd  mov     rcx, rax
0x18022fbe0  call    ??0TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@UGuid@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(asg::Guid)
0x18022fbe5  lea     rax, ??_7?$heap_implements@UTextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable'
0x18022fbec  mov     [rdi], rax
0x18022fbef  lea     rdx, [rdi+10h]
0x18022fbf3  test    rdi, rdi
0x18022fbf6  cmovz   rdx, rbx
0x18022fbfa  mov     [rsi+170h], rdx
0x18022fc01  mov     [rsi+0A0h], rdx
0x18022fc08  cmp     [rsi+94h], bl
0x18022fc0e  jz      loc_18022FEBD
0x18022fc14  mov     [rsi+0A8h], rbx
0x18022fc1b  test    rdx, rdx
0x18022fc1e  jz      short loc_18022FC56
0x18022fc20  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18022fc24  jz      short loc_18022FC56
0x18022fc26  mov     [rsi+0A8h], rdx
0x18022fc2d  mov     rax, [rdx+8]
0x18022fc31  test    rax, rax
0x18022fc34  js      short loc_18022FC51
0x18022fc36  nop     word ptr [rax+rax+00000000h]
0x18022fc40  lea     rcx, [rax+1]
0x18022fc44  lock cmpxchg [rdx+8], rcx
0x18022fc4a  jz      short loc_18022FC56
0x18022fc4c  test    rax, rax
0x18022fc4f  jns     short loc_18022FC40
0x18022fc51  lock inc dword ptr [rax+rax+18h]
0x18022fc56  lea     r8, [rsi+178h]
0x18022fc5d  mov     byte ptr [rsi+198h], 0
0x18022fc64  lea     rdi, [rsi+0B0h]
0x18022fc6b  mov     rcx, [rsi+0A8h]
0x18022fc72  mov     [rsp+0F8h+arg_8], rcx
0x18022fc7a  mov     rdx, rdi
0x18022fc7d  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x18022fc82  nop
0x18022fc83  mov     eax, [rsi+70h]
0x18022fc86  cmp     eax, 2
0x18022fc89  jnz     short loc_18022FCC8
0x18022fc8b  lea     rdx, [rsi+1A0h]; struct winrt::impl::slim_source_location *
0x18022fc92  mov     dword ptr [rdx], 1628h
0x18022fc98  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022fc9f  mov     [rsi+1A8h], rax
0x18022fca6  mov     [rsi+1B0h], rbx
0x18022fcad  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18022fcb2  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022fcb7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022fcbe  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18022fcc3  call    _CxxThrowException
0x18022fcc8  lea     rcx, [rsi+0B8h]
0x18022fccf  mov     [rcx], rbx
0x18022fcd2  mov     [rsi+0C0h], rdi
0x18022fcd9  mov     [rsi+0C8h], rbx
0x18022fce0  mov     byte ptr [rsi+0D0h], 1
0x18022fce7  mov     eax, 4
0x18022fcec  mov     [rsi+98h], ax
0x18022fcf3  mov     rdx, rsi
0x18022fcf6  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18022fcfb  test    al, al
0x18022fcfd  jz      loc_18022FDD3
0x18022fd03  jmp     loc_18022FF63
0x18022fd08  lea     rdx, [rsi+118h]; struct winrt::impl::slim_source_location *
0x18022fd0f  mov     dword ptr [rdx], 0DDh
0x18022fd15  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022fd1c  mov     [rsi+120h], rax
0x18022fd23  mov     [rsi+128h], rbx
0x18022fd2a  lea     rcx, [rsp+0F8h+var_B0]; this
0x18022fd2f  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18022fd34  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18022fd3b  lea     rcx, [rsp+0F8h+var_B0]; pExceptionObject
0x18022fd40  call    _CxxThrowException
0x18022fd46  mov     rdi, [rsi+0B8h]; jumptable 000000018022FB81 case 5
0x18022fd4d  test    rdi, rdi
0x18022fd50  jz      short loc_18022FD75
0x18022fd52  mov     [rsp+0F8h+var_80], rdi
0x18022fd57  xor     ebx, ebx
0x18022fd59  mov     eax, ebx
0x18022fd5b  xchg    rax, [rdi]
0x18022fd5e  cmp     rax, 1
0x18022fd62  jnz     short loc_18022FD75
0x18022fd64  call    _Thrd_yield
0x18022fd69  mov     rax, rbx
0x18022fd6c  xchg    rax, [rdi]
0x18022fd6f  cmp     rax, 1
0x18022fd73  jz      short loc_18022FD64
0x18022fd75  lea     rcx, [rsi+0B0h]
0x18022fd7c  mov     rax, [rcx]
0x18022fd7f  mov     [rsp+0F8h+arg_10], rax
0x18022fd87  test    rax, rax
0x18022fd8a  jz      short loc_18022FD92
0x18022fd8c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022fd91  nop
0x18022fd92  lea     rcx, [rsi+0A8h]
0x18022fd99  mov     rax, [rcx]
0x18022fd9c  mov     [rsp+0F8h+arg_8], rax
0x18022fda4  test    rax, rax
0x18022fda7  jz      short loc_18022FDAF
0x18022fda9  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022fdae  nop
0x18022fdaf  cmp     qword ptr [rsi+170h], 0
0x18022fdb7  jz      short loc_18022FDC6
0x18022fdb9  lea     rcx, [rsi+0A0h]
0x18022fdc0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022fdc5  nop
0x18022fdc6  jmp     loc_18022FF40; jumptable 000000018022FB81 cases -1,1
0x18022fdcb  xor     ebx, ebx; jumptable 000000018022FB81 case 4
0x18022fdcd  mov     r15d, 10h
0x18022fdd3  lea     rcx, [rsi+0B8h]
0x18022fdda  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18022fddf  movzx   r14d, al
0x18022fde3  mov     rdi, [rsi+0B8h]
0x18022fdea  test    rdi, rdi
0x18022fded  jz      short loc_18022FE11
0x18022fdef  mov     [rsp+0F8h+var_80], rdi
0x18022fdf4  mov     rcx, rbx
0x18022fdf7  xchg    rcx, [rdi]
0x18022fdfa  cmp     rcx, 1
0x18022fdfe  jnz     short loc_18022FE11
0x18022fe00  call    _Thrd_yield
0x18022fe05  mov     rax, rbx
0x18022fe08  xchg    rax, [rdi]
0x18022fe0b  cmp     rax, 1
0x18022fe0f  jz      short loc_18022FE00
0x18022fe11  lea     rcx, [rsi+0B0h]
0x18022fe18  mov     rax, [rcx]
0x18022fe1b  mov     [rsp+0F8h+arg_10], rax
0x18022fe23  test    rax, rax
0x18022fe26  jz      short loc_18022FE2D
0x18022fe28  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022fe2d  test    r14b, r14b
0x18022fe30  jnz     short loc_18022FEA1
0x18022fe32  mov     dword ptr [rsi+0D8h], 0D4h
0x18022fe3c  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022fe43  mov     [rsi+0E0h], rax
0x18022fe4a  mov     [rsi+0E8h], rbx
0x18022fe51  lea     rdx, aFailedToLoadTe_1; "Failed to load text query embedding mod"...
0x18022fe58  lea     rcx, [rsi+0F0h]; this
0x18022fe5f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022fe64  lea     rcx, [rsi+110h]; this
0x18022fe6b  mov     edx, 83EBAD1Dh; int
0x18022fe70  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18022fe75  lea     r9, [rsi+0D8h]
0x18022fe7c  lea     r8, [rsi+0F0h]
0x18022fe83  mov     edx, [rax]
0x18022fe85  lea     rcx, [rsp+0F8h+var_98]
0x18022fe8a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022fe8f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18022fe96  lea     rcx, [rsp+0F8h+var_98]; pExceptionObject
0x18022fe9b  call    _CxxThrowException
0x18022fea1  lea     rcx, [rsi+0A8h]
0x18022fea8  mov     rax, [rcx]
0x18022feab  mov     [rsp+0F8h+arg_8], rax
0x18022feb3  test    rax, rax
0x18022feb6  jz      short loc_18022FEBD
0x18022feb8  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022febd  lea     r14, [rsi+78h]
0x18022fec1  lea     rdi, [rsi+0A0h]
0x18022fec8  cmp     r14, rdi
0x18022fecb  jz      short loc_18022FEE8
0x18022fecd  cmp     qword ptr [r14], 0
0x18022fed1  jz      short loc_18022FEDB
0x18022fed3  mov     rcx, r14
0x18022fed6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022fedb  mov     [rdi], rbx
0x18022fede  mov     rax, [rsi+170h]
0x18022fee5  mov     [r14], rax
0x18022fee8  mov     rax, rsi
0x18022feeb  lea     r14, [rax+r15]
0x18022feef  mov     rax, [rdi]
0x18022fef2  mov     [rsp+0F8h+var_D0], rax
0x18022fef7  test    rax, rax
0x18022fefa  jz      short loc_18022FF05
0x18022fefc  mov     rcx, rdi
0x18022feff  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022ff04  nop
0x18022ff05  jmp     short loc_18022FF1D
0x18022ff07  mov     r14, [rsp+0F8h+arg_18]
0x18022ff0f  add     r14, 10h
0x18022ff13  xor     ebx, ebx
0x18022ff15  mov     rsi, [rsp+0F8h+Block]
0x18022ff1d  lea     rcx, [rsi+130h]
0x18022ff24  mov     [rcx], r14
0x18022ff27  xor     eax, eax
0x18022ff29  mov     [rsi+98h], ax
0x18022ff30  mov     [rsi], rbx
0x18022ff33  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022ff38  test    al, al
0x18022ff3a  jnz     short loc_18022FF63
0x18022ff3c  nop     dword ptr [rax+00h]
0x18022ff40  lea     rcx, [rsi+10h]; jumptable 000000018022FB81 cases -1,1
0x18022ff44  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(void)
0x18022ff49  cmp     word ptr [rsi+9Ah], 0
0x18022ff51  jz      short loc_18022FF63
0x18022ff53  mov     edx, 1C0h
0x18022ff58  mov     rcx, rsi; Block
0x18022ff5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022ff60  jmp     short loc_18022FF63
0x18022ff62  int     3; Trap to Debugger
0x18022ff63  add     rsp, 0D0h
0x18022ff6a  pop     r15
0x18022ff6c  pop     r14
0x18022ff6e  pop     rdi
0x18022ff6f  pop     rsi
0x18022ff70  pop     rbx
0x18022ff71  retn
```
