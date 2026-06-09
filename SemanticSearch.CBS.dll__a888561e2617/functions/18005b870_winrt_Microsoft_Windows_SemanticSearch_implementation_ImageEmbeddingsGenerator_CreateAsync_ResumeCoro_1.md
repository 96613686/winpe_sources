# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::CreateAsync$_ResumeCoro$1

- ea: `0x18005b870`
- end: `0x18005bc80`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::CreateAsync$_ResumeCoro$1`
- size: `1040`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003ec70`
- `0x18005b860`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001ee40`
- `0x1800215e0`
- `0x18003ef70`
- `0x1800454f0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x18005b870`
- `0x18005e260`

## string_xrefs

- `0x18005b94f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::CreateAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r14
  __int128 *v3; // rcx
  __int64 *v4; // r9
  __int64 v5; // rax
  __int128 v6; // xmm0
  int v7; // eax
  volatile __int64 *v8; // rsi
  volatile __int64 *v9; // rsi
  _QWORD *v10; // rcx
  _QWORD *v11; // rsi
  __int64 v12; // rax
  _QWORD *v13; // r15
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-B0h] BYREF
  volatile __int64 *v15; // [rsp+60h] [rbp-98h]
  __int64 v16; // [rsp+80h] [rbp-78h]
  __int128 v18; // [rsp+90h] [rbp-68h]
  __int128 v19; // [rsp+A0h] [rbp-58h]

  v2 = a1 + 164;
  switch ( *((_WORD *)a1 + 82) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_33;
    case 2:
      winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered();
      v3 = (__int128 *)(a1 + 168);
      *(_OWORD *)(a1 + 168) = *(_OWORD *)(a1 + 132);
      *(_OWORD *)(a1 + 184) = *(_OWORD *)(a1 + 148);
      *((_QWORD *)a1 + 33) = a1 + 168;
      *((_QWORD *)a1 + 34) = &qword_1800869A8;
      _InterlockedIncrement64(&qword_1800869A8);
      v4 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics> )
      {
        *((_QWORD *)a1 + 35) = 0;
        *((_DWORD *)a1 + 72) = 265;
        *((_QWORD *)a1 + 37) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        v5 = *v4;
        v18 = *v3;
        v19 = *(_OWORD *)(a1 + 184);
        v6 = v19;
        *((_OWORD *)a1 + 19) = v18;
        *((_OWORD *)a1 + 20) = v6;
        v7 = (*(__int64 (__fastcall **)(__int64 *, char *, char *))(v5 + 48))(v4, a1 + 304, a1 + 280);
        if ( v7 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v7, a1 + 288);
        }
        v16 = *((_QWORD *)a1 + 35);
        *((_QWORD *)a1 + 25) = v16;
        _InterlockedDecrement64(&qword_1800869A8);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800869A8);
        ___call_AEAV_lambda_1___1__CreateAsync_ImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIndexVectorSpaceIds_456789__Z____factory_cache_entry_UImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UIImageEmbeddingsGeneratorStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_ImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIndexVectorSpaceIds_6789Microsoft_2__Z__Z(
          (__int64)v3,
          (_QWORD *)a1 + 25,
          (__int128 **)a1 + 33);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 84) = 3980;
        *((_QWORD *)a1 + 43) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 336));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 26) = 0;
      *((_QWORD *)a1 + 27) = a1 + 200;
      *((_QWORD *)a1 + 28) = 0;
      a1[232] = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::ImageEmbeddingsGenerator>,winrt::Microsoft::Windows::SemanticSearch::IndexVectorSpaceIds>::promise_type>(
                              (_QWORD *)a1 + 26,
                              (__int64)a1) )
        return;
      goto LABEL_17;
    case 4:
LABEL_17:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(
        (__int64)(a1 + 208),
        (_QWORD *)a1 + 30);
      if ( *((_QWORD *)a1 + 26) )
      {
        v9 = (volatile __int64 *)*((_QWORD *)a1 + 26);
        v15 = v9;
        while ( _InterlockedExchange64(v9, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      v10 = operator new(0x38u);
      v11 = v10 + 2;
      v10[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::`vftable';
      v10[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator2>::`vftable';
      v10[4] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Windows::Foundation::IClosable>::`vftable';
      v10[5] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IVectorSpaceInfo>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v10[1] = 1;
      *v10 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::`vftable';
      v12 = *((_QWORD *)a1 + 30);
      *((_QWORD *)a1 + 30) = 0;
      v10[6] = v12;
      *v10 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::`vftable';
      if ( !v10 )
        v11 = 0;
      *((_QWORD *)a1 + 31) = v11;
      v13 = a1 + 120;
      if ( a1 + 120 == a1 + 248 )
      {
        if ( v11 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 248);
      }
      else
      {
        if ( *v13 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        *v13 = v11;
      }
      if ( *((_QWORD *)a1 + 30) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 240);
      *((_QWORD *)a1 + 32) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 32) )
        goto LABEL_33;
      return;
    case 5:
      if ( *((_QWORD *)a1 + 26) )
      {
        v8 = (volatile __int64 *)*((_QWORD *)a1 + 26);
        v15 = v8;
        while ( _InterlockedExchange64(v8, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
LABEL_33:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 83) )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18005b870  mov     r11, rsp
0x18005b873  mov     [r11+10h], rbx
0x18005b877  mov     [r11+18h], rsi
0x18005b87b  mov     [r11+20h], rdi
0x18005b87f  mov     [r11+8], rcx
0x18005b883  push    r12
0x18005b885  push    r14
0x18005b887  push    r15
0x18005b889  sub     rsp, 0E0h
0x18005b890  mov     rax, cs:__security_cookie
0x18005b897  xor     rax, rsp
0x18005b89a  mov     [rsp+0F8h+var_28], rax
0x18005b8a2  mov     rbx, rcx
0x18005b8a5  mov     [rsp+0F8h+var_C8], rcx
0x18005b8aa  lea     r14, [rbx+0A4h]
0x18005b8b1  mov     [rsp+0F8h+var_C0], r14
0x18005b8b6  movzx   eax, word ptr [r14]
0x18005b8ba  mov     [rsp+0F8h+var_D8], ax
0x18005b8bf  inc     ax; switch 7 cases
0x18005b8c2  cmp     ax, 6
0x18005b8c6  ja      def_18005B8E1; jumptable 000000018005B8E1 default case, case 0
0x18005b8cc  movsx   rax, ax
0x18005b8d0  lea     rdx, cs:180000000h
0x18005b8d7  mov     ecx, ds:(jpt_18005B8E1 - 180000000h)[rdx+rax*4]
0x18005b8de  add     rcx, rdx
0x18005b8e1  jmp     rcx; switch jump
0x18005b8e3  jmp     loc_18005BC12; jumptable 000000018005B8E1 case 3
0x18005b8e8  xor     edi, edi; jumptable 000000018005B8E1 case 2
0x18005b8ea  call    ?EnsureRegistered@AiFabricModelFactories@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXXZ; winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered(void)
0x18005b8ef  lea     rcx, [rbx+0A8h]
0x18005b8f6  movups  xmm0, xmmword ptr [rbx+84h]
0x18005b8fd  movups  xmmword ptr [rcx], xmm0
0x18005b900  movups  xmm0, xmmword ptr [rbx+94h]
0x18005b907  movups  xmmword ptr [rbx+0B8h], xmm0
0x18005b90e  lea     r8, [rbx+108h]
0x18005b915  mov     [r8], rcx
0x18005b918  lea     rax, qword_1800869A8
0x18005b91f  mov     [rbx+110h], rax
0x18005b926  lock inc cs:qword_1800869A8
0x18005b92e  mov     r9, cs:??$factory_cache_entry_v@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>
0x18005b935  test    r9, r9
0x18005b938  jz      loc_18005B9CE
0x18005b93e  mov     [rbx+118h], rdi
0x18005b945  mov     dword ptr [rbx+120h], 109h
0x18005b94f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b956  mov     [rbx+128h], rax
0x18005b95d  mov     rax, [r9]
0x18005b960  lea     rdx, [rbx+130h]
0x18005b967  movups  xmm1, xmmword ptr [rcx]
0x18005b96a  movups  [rsp+0F8h+var_68], xmm1
0x18005b972  movups  xmm0, xmmword ptr [rcx+10h]
0x18005b976  movups  [rsp+0F8h+var_58], xmm0
0x18005b97e  movaps  xmmword ptr [rdx], xmm1
0x18005b981  movaps  xmmword ptr [rdx+10h], xmm0
0x18005b985  lea     r8, [rbx+118h]
0x18005b98c  mov     rcx, r9
0x18005b98f  mov     rax, [rax+30h]
0x18005b993  call    cs:__guard_dispatch_icall_fptr
0x18005b999  test    eax, eax
0x18005b99b  jns     short loc_18005B9AE
0x18005b99d  lfence
0x18005b9a0  lea     rdx, [rbx+120h]
0x18005b9a7  mov     ecx, eax
0x18005b9a9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005b9ae  mov     rax, [rbx+118h]
0x18005b9b5  mov     [rsp+0F8h+var_78], rax
0x18005b9bd  mov     [rbx+0C8h], rax
0x18005b9c4  lock dec cs:qword_1800869A8
0x18005b9cc  jmp     short loc_18005B9E3
0x18005b9ce  lock dec cs:qword_1800869A8
0x18005b9d6  lea     rdx, [rbx+0C8h]
0x18005b9dd  call    ??$call@AEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z
0x18005b9e2  nop
0x18005b9e3  mov     eax, [rbx+70h]
0x18005b9e6  cmp     eax, 2
0x18005b9e9  jnz     short loc_18005BA21
0x18005b9eb  lea     rdx, [rbx+150h]; struct winrt::impl::slim_source_location *
0x18005b9f2  mov     dword ptr [rdx], 0F8Ch
0x18005b9f8  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b9ff  mov     [rbx+158h], rax
0x18005ba06  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18005ba0b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005ba10  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005ba17  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18005ba1c  call    _CxxThrowException
0x18005ba21  lea     rcx, [rbx+0D0h]
0x18005ba28  mov     [rcx], rdi
0x18005ba2b  lea     rax, [rbx+0C8h]
0x18005ba32  mov     [rbx+0D8h], rax
0x18005ba39  mov     [rbx+0E0h], rdi
0x18005ba40  mov     byte ptr [rbx+0E8h], 1
0x18005ba47  mov     eax, 4
0x18005ba4c  mov     [r14], ax
0x18005ba50  mov     rdx, rbx
0x18005ba53  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UIndexVectorSpaceIds@SemanticSearch@3Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperation@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UIndexVectorSpaceIds@SemanticSearch@3Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::ImageEmbeddingsGenerator>,winrt::Microsoft::Windows::SemanticSearch::IndexVectorSpaceIds>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::ImageEmbeddingsGenerator>,winrt::Microsoft::Windows::SemanticSearch::IndexVectorSpaceIds>::promise_type>)
0x18005ba58  test    al, al
0x18005ba5a  jz      short loc_18005BAB6
0x18005ba5c  jmp     loc_18005BC35
0x18005ba61  cmp     qword ptr [rbx+0D0h], 0; jumptable 000000018005B8E1 case 5
0x18005ba69  jz      short loc_18005BA95
0x18005ba6b  mov     rsi, [rbx+0D0h]
0x18005ba72  mov     [rsp+0F8h+var_98], rsi
0x18005ba77  xor     edi, edi
0x18005ba79  mov     eax, edi
0x18005ba7b  xchg    rax, [rsi]
0x18005ba7e  cmp     rax, 1
0x18005ba82  jnz     short loc_18005BA95
0x18005ba84  call    _Thrd_yield
0x18005ba89  mov     rax, rdi
0x18005ba8c  xchg    rax, [rsi]
0x18005ba8f  cmp     rax, 1
0x18005ba93  jz      short loc_18005BA84
0x18005ba95  lea     rcx, [rbx+0C8h]
0x18005ba9c  mov     rax, [rcx]
0x18005ba9f  mov     [rsp+0F8h+var_D0], rax
0x18005baa4  test    rax, rax
0x18005baa7  jz      short loc_18005BAAF
0x18005baa9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005baae  nop
0x18005baaf  jmp     loc_18005BC12; jumptable 000000018005B8E1 cases -1,1
0x18005bab4  xor     edi, edi; jumptable 000000018005B8E1 case 4
0x18005bab6  lea     rdx, [rbx+0F0h]
0x18005babd  lea     rcx, [rbx+0D0h]
0x18005bac4  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x18005bac9  nop
0x18005baca  cmp     qword ptr [rbx+0D0h], 0
0x18005bad2  jz      short loc_18005BB01
0x18005bad4  mov     rsi, [rbx+0D0h]
0x18005badb  mov     [rsp+0F8h+var_98], rsi
0x18005bae0  mov     rcx, rdi
0x18005bae3  xchg    rcx, [rsi]
0x18005bae6  cmp     rcx, 1
0x18005baea  jnz     short loc_18005BB01
0x18005baec  nop     dword ptr [rax+00h]
0x18005baf0  call    _Thrd_yield
0x18005baf5  mov     rax, rdi
0x18005baf8  xchg    rax, [rsi]
0x18005bafb  cmp     rax, 1
0x18005baff  jz      short loc_18005BAF0
0x18005bb01  lea     rcx, [rbx+0C8h]
0x18005bb08  mov     rax, [rcx]
0x18005bb0b  mov     [rsp+0F8h+var_D0], rax
0x18005bb10  test    rax, rax
0x18005bb13  jz      short loc_18005BB1A
0x18005bb15  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005bb1a  mov     ecx, 38h ; '8'; Size
0x18005bb1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bb24  mov     rcx, rax
0x18005bb27  lea     rsi, [rax+10h]
0x18005bb2b  lea     rax, ??_7?$produce@UImageEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsGenerator@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::`vftable'
0x18005bb32  mov     [rsi], rax
0x18005bb35  lea     rax, ??_7?$produce@UImageEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsGenerator2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator2>::`vftable'
0x18005bb3c  mov     [rsi+8], rax
0x18005bb40  lea     rax, ??_7?$produce@UImageEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIClosable@Foundation@46@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator,winrt::Windows::Foundation::IClosable>::`vftable'
0x18005bb47  mov     [rsi+10h], rax
0x18005bb4b  lea     rax, ??_7?$produce@UTextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIVectorSpaceInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IVectorSpaceInfo>::`vftable'
0x18005bb52  mov     [rsi+18h], rax
0x18005bb56  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005bb5d  mov     qword ptr [rcx+8], 1
0x18005bb65  lea     rax, ??_7ImageEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::`vftable'
0x18005bb6c  mov     [rcx], rax
0x18005bb6f  mov     rax, [rbx+0F0h]
0x18005bb76  mov     [rbx+0F0h], rdi
0x18005bb7d  mov     [rcx+30h], rax
0x18005bb81  lea     rax, ??_7ImageEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingsGenerator::`vftable'
0x18005bb88  mov     [rcx], rax
0x18005bb8b  test    rcx, rcx
0x18005bb8e  cmovz   rsi, rdi
0x18005bb92  lea     rcx, [rbx+0F8h]
0x18005bb99  mov     [rcx], rsi
0x18005bb9c  lea     r15, [rbx+78h]
0x18005bba0  cmp     r15, rcx
0x18005bba3  jz      short loc_18005BBB8
0x18005bba5  cmp     qword ptr [r15], 0
0x18005bba9  jz      short loc_18005BBB3
0x18005bbab  mov     rcx, r15
0x18005bbae  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005bbb3  mov     [r15], rsi
0x18005bbb6  jmp     short loc_18005BBC3
0x18005bbb8  test    rsi, rsi
0x18005bbbb  jz      short loc_18005BBC3
0x18005bbbd  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005bbc2  nop
0x18005bbc3  mov     rax, [rbx+0F0h]
0x18005bbca  mov     [rsp+0F8h+var_70], rax
0x18005bbd2  test    rax, rax
0x18005bbd5  jz      short loc_18005BBE4
0x18005bbd7  lea     rcx, [rbx+0F0h]
0x18005bbde  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005bbe3  nop
0x18005bbe4  jmp     short loc_18005BBF2
0x18005bbe6  xor     edi, edi
0x18005bbe8  mov     rbx, [rsp+0F8h+var_C8]
0x18005bbed  mov     r14, [rsp+0F8h+var_C0]
0x18005bbf2  lea     rax, [rbx+10h]
0x18005bbf6  lea     rcx, [rbx+100h]
0x18005bbfd  mov     [rcx], rax
0x18005bc00  xor     eax, eax
0x18005bc02  mov     [r14], ax
0x18005bc06  mov     [rbx], rdi
0x18005bc09  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005bc0e  test    al, al
0x18005bc10  jnz     short loc_18005BC35
0x18005bc12  lea     rcx, [rbx+10h]; jumptable 000000018005B8E1 cases -1,1
0x18005bc16  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005bc1b  cmp     word ptr [rbx+0A6h], 0
0x18005bc23  jz      short loc_18005BC35
0x18005bc25  mov     edx, 160h; unsigned __int64
0x18005bc2a  mov     rcx, rbx; void *
0x18005bc2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005bc32  jmp     short loc_18005BC35
0x18005bc34  int     3; Trap to Debugger
0x18005bc35  mov     rcx, [rsp+0F8h+var_28]
0x18005bc3d  xor     rcx, rsp; StackCookie
0x18005bc40  call    __security_check_cookie
0x18005bc45  lea     r11, [rsp+0F8h+var_18]
0x18005bc4d  mov     rbx, [r11+28h]
0x18005bc51  mov     rsi, [r11+30h]
0x18005bc55  mov     rdi, [r11+38h]
0x18005bc59  mov     rsp, r11
0x18005bc5c  pop     r15
0x18005bc5e  pop     r14
0x18005bc60  pop     r12
0x18005bc62  retn
```
