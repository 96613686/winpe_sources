# winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::CreateAsync$_ResumeCoro$1

- ea: `0x18005b450`
- end: `0x18005b860`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::CreateAsync$_ResumeCoro$1`
- size: `1040`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e750`
- `0x18005b440`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001ee40`
- `0x180021610`
- `0x18003ea50`
- `0x1800454f0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x18005b450`
- `0x18005e260`

## string_xrefs

- `0x18005b52f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::CreateAsync__ResumeCoro_1(
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
      *((_QWORD *)a1 + 34) = &qword_180086988;
      _InterlockedIncrement64(&qword_180086988);
      v4 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics> )
      {
        *((_QWORD *)a1 + 35) = 0;
        *((_DWORD *)a1 + 72) = 1309;
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
        _InterlockedDecrement64(&qword_180086988);
      }
      else
      {
        _InterlockedDecrement64(&qword_180086988);
        ___call_AEAV_lambda_1___1__CreateAsync_TextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIndexVectorSpaceIds_456789__Z____factory_cache_entry_UTextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UITextEmbeddingsGeneratorStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_TextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIndexVectorSpaceIds_6789Microsoft_2__Z__Z(
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
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsGenerator>,winrt::guid>::promise_type>(
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
      v10[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::ITextEmbeddingsGenerator>::`vftable';
      v10[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::ITextEmbeddingsGenerator2>::`vftable';
      v10[4] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Windows::Foundation::IClosable>::`vftable';
      v10[5] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IVectorSpaceInfo>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v10[1] = 1;
      *v10 = &winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::`vftable';
      v12 = *((_QWORD *)a1 + 30);
      *((_QWORD *)a1 + 30) = 0;
      v10[6] = v12;
      *v10 = &winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::`vftable';
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
0x18005b450  mov     r11, rsp
0x18005b453  mov     [r11+10h], rbx
0x18005b457  mov     [r11+18h], rsi
0x18005b45b  mov     [r11+20h], rdi
0x18005b45f  mov     [r11+8], rcx
0x18005b463  push    r12
0x18005b465  push    r14
0x18005b467  push    r15
0x18005b469  sub     rsp, 0E0h
0x18005b470  mov     rax, cs:__security_cookie
0x18005b477  xor     rax, rsp
0x18005b47a  mov     [rsp+0F8h+var_28], rax
0x18005b482  mov     rbx, rcx
0x18005b485  mov     [rsp+0F8h+var_C8], rcx
0x18005b48a  lea     r14, [rbx+0A4h]
0x18005b491  mov     [rsp+0F8h+var_C0], r14
0x18005b496  movzx   eax, word ptr [r14]
0x18005b49a  mov     [rsp+0F8h+var_D8], ax
0x18005b49f  inc     ax; switch 7 cases
0x18005b4a2  cmp     ax, 6
0x18005b4a6  ja      def_18005B4C1; jumptable 000000018005B4C1 default case, case 0
0x18005b4ac  movsx   rax, ax
0x18005b4b0  lea     rdx, cs:180000000h
0x18005b4b7  mov     ecx, ds:(jpt_18005B4C1 - 180000000h)[rdx+rax*4]
0x18005b4be  add     rcx, rdx
0x18005b4c1  jmp     rcx; switch jump
0x18005b4c3  jmp     loc_18005B7F2; jumptable 000000018005B4C1 case 3
0x18005b4c8  xor     edi, edi; jumptable 000000018005B4C1 case 2
0x18005b4ca  call    ?EnsureRegistered@AiFabricModelFactories@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXXZ; winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered(void)
0x18005b4cf  lea     rcx, [rbx+0A8h]
0x18005b4d6  movups  xmm0, xmmword ptr [rbx+84h]
0x18005b4dd  movups  xmmword ptr [rcx], xmm0
0x18005b4e0  movups  xmm0, xmmword ptr [rbx+94h]
0x18005b4e7  movups  xmmword ptr [rbx+0B8h], xmm0
0x18005b4ee  lea     r8, [rbx+108h]
0x18005b4f5  mov     [r8], rcx
0x18005b4f8  lea     rax, qword_180086988
0x18005b4ff  mov     [rbx+110h], rax
0x18005b506  lock inc cs:qword_180086988
0x18005b50e  mov     r9, cs:??$factory_cache_entry_v@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>
0x18005b515  test    r9, r9
0x18005b518  jz      loc_18005B5AE
0x18005b51e  mov     [rbx+118h], rdi
0x18005b525  mov     dword ptr [rbx+120h], 51Dh
0x18005b52f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b536  mov     [rbx+128h], rax
0x18005b53d  mov     rax, [r9]
0x18005b540  lea     rdx, [rbx+130h]
0x18005b547  movups  xmm1, xmmword ptr [rcx]
0x18005b54a  movups  [rsp+0F8h+var_68], xmm1
0x18005b552  movups  xmm0, xmmword ptr [rcx+10h]
0x18005b556  movups  [rsp+0F8h+var_58], xmm0
0x18005b55e  movaps  xmmword ptr [rdx], xmm1
0x18005b561  movaps  xmmword ptr [rdx+10h], xmm0
0x18005b565  lea     r8, [rbx+118h]
0x18005b56c  mov     rcx, r9
0x18005b56f  mov     rax, [rax+30h]
0x18005b573  call    cs:__guard_dispatch_icall_fptr
0x18005b579  test    eax, eax
0x18005b57b  jns     short loc_18005B58E
0x18005b57d  lfence
0x18005b580  lea     rdx, [rbx+120h]
0x18005b587  mov     ecx, eax
0x18005b589  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005b58e  mov     rax, [rbx+118h]
0x18005b595  mov     [rsp+0F8h+var_78], rax
0x18005b59d  mov     [rbx+0C8h], rax
0x18005b5a4  lock dec cs:qword_180086988
0x18005b5ac  jmp     short loc_18005B5C3
0x18005b5ae  lock dec cs:qword_180086988
0x18005b5b6  lea     rdx, [rbx+0C8h]
0x18005b5bd  call    ??$call@AEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z
0x18005b5c2  nop
0x18005b5c3  mov     eax, [rbx+70h]
0x18005b5c6  cmp     eax, 2
0x18005b5c9  jnz     short loc_18005B601
0x18005b5cb  lea     rdx, [rbx+150h]; struct winrt::impl::slim_source_location *
0x18005b5d2  mov     dword ptr [rdx], 0F8Ch
0x18005b5d8  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b5df  mov     [rbx+158h], rax
0x18005b5e6  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18005b5eb  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005b5f0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005b5f7  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18005b5fc  call    _CxxThrowException
0x18005b601  lea     rcx, [rbx+0D0h]
0x18005b608  mov     [rcx], rdi
0x18005b60b  lea     rax, [rbx+0C8h]
0x18005b612  mov     [rbx+0D8h], rax
0x18005b619  mov     [rbx+0E0h], rdi
0x18005b620  mov     byte ptr [rbx+0E8h], 1
0x18005b627  mov     eax, 4
0x18005b62c  mov     [r14], ax
0x18005b630  mov     rdx, rbx
0x18005b633  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@@std@@@?$await_adapter@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsGenerator>,winrt::guid>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsGenerator>,winrt::guid>::promise_type>)
0x18005b638  test    al, al
0x18005b63a  jz      short loc_18005B696
0x18005b63c  jmp     loc_18005B815
0x18005b641  cmp     qword ptr [rbx+0D0h], 0; jumptable 000000018005B4C1 case 5
0x18005b649  jz      short loc_18005B675
0x18005b64b  mov     rsi, [rbx+0D0h]
0x18005b652  mov     [rsp+0F8h+var_98], rsi
0x18005b657  xor     edi, edi
0x18005b659  mov     eax, edi
0x18005b65b  xchg    rax, [rsi]
0x18005b65e  cmp     rax, 1
0x18005b662  jnz     short loc_18005B675
0x18005b664  call    _Thrd_yield
0x18005b669  mov     rax, rdi
0x18005b66c  xchg    rax, [rsi]
0x18005b66f  cmp     rax, 1
0x18005b673  jz      short loc_18005B664
0x18005b675  lea     rcx, [rbx+0C8h]
0x18005b67c  mov     rax, [rcx]
0x18005b67f  mov     [rsp+0F8h+var_D0], rax
0x18005b684  test    rax, rax
0x18005b687  jz      short loc_18005B68F
0x18005b689  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b68e  nop
0x18005b68f  jmp     loc_18005B7F2; jumptable 000000018005B4C1 cases -1,1
0x18005b694  xor     edi, edi; jumptable 000000018005B4C1 case 4
0x18005b696  lea     rdx, [rbx+0F0h]
0x18005b69d  lea     rcx, [rbx+0D0h]
0x18005b6a4  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x18005b6a9  nop
0x18005b6aa  cmp     qword ptr [rbx+0D0h], 0
0x18005b6b2  jz      short loc_18005B6E1
0x18005b6b4  mov     rsi, [rbx+0D0h]
0x18005b6bb  mov     [rsp+0F8h+var_98], rsi
0x18005b6c0  mov     rcx, rdi
0x18005b6c3  xchg    rcx, [rsi]
0x18005b6c6  cmp     rcx, 1
0x18005b6ca  jnz     short loc_18005B6E1
0x18005b6cc  nop     dword ptr [rax+00h]
0x18005b6d0  call    _Thrd_yield
0x18005b6d5  mov     rax, rdi
0x18005b6d8  xchg    rax, [rsi]
0x18005b6db  cmp     rax, 1
0x18005b6df  jz      short loc_18005B6D0
0x18005b6e1  lea     rcx, [rbx+0C8h]
0x18005b6e8  mov     rax, [rcx]
0x18005b6eb  mov     [rsp+0F8h+var_D0], rax
0x18005b6f0  test    rax, rax
0x18005b6f3  jz      short loc_18005B6FA
0x18005b6f5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b6fa  mov     ecx, 38h ; '8'; Size
0x18005b6ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b704  mov     rcx, rax
0x18005b707  lea     rsi, [rax+10h]
0x18005b70b  lea     rax, ??_7?$produce@UTextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextEmbeddingsGenerator@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::ITextEmbeddingsGenerator>::`vftable'
0x18005b712  mov     [rsi], rax
0x18005b715  lea     rax, ??_7?$produce@UTextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextEmbeddingsGenerator2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::ITextEmbeddingsGenerator2>::`vftable'
0x18005b71c  mov     [rsi+8], rax
0x18005b720  lea     rax, ??_7?$produce@UTextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIClosable@Foundation@46@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Windows::Foundation::IClosable>::`vftable'
0x18005b727  mov     [rsi+10h], rax
0x18005b72b  lea     rax, ??_7?$produce@UTextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIVectorSpaceInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Windows::SemanticSearch::IVectorSpaceInfo>::`vftable'
0x18005b732  mov     [rsi+18h], rax
0x18005b736  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b73d  mov     qword ptr [rcx+8], 1
0x18005b745  lea     rax, ??_7TextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::`vftable'
0x18005b74c  mov     [rcx], rax
0x18005b74f  mov     rax, [rbx+0F0h]
0x18005b756  mov     [rbx+0F0h], rdi
0x18005b75d  mov     [rcx+30h], rax
0x18005b761  lea     rax, ??_7TextEmbeddingsGenerator@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::TextEmbeddingsGenerator::`vftable'
0x18005b768  mov     [rcx], rax
0x18005b76b  test    rcx, rcx
0x18005b76e  cmovz   rsi, rdi
0x18005b772  lea     rcx, [rbx+0F8h]
0x18005b779  mov     [rcx], rsi
0x18005b77c  lea     r15, [rbx+78h]
0x18005b780  cmp     r15, rcx
0x18005b783  jz      short loc_18005B798
0x18005b785  cmp     qword ptr [r15], 0
0x18005b789  jz      short loc_18005B793
0x18005b78b  mov     rcx, r15
0x18005b78e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b793  mov     [r15], rsi
0x18005b796  jmp     short loc_18005B7A3
0x18005b798  test    rsi, rsi
0x18005b79b  jz      short loc_18005B7A3
0x18005b79d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b7a2  nop
0x18005b7a3  mov     rax, [rbx+0F0h]
0x18005b7aa  mov     [rsp+0F8h+var_70], rax
0x18005b7b2  test    rax, rax
0x18005b7b5  jz      short loc_18005B7C4
0x18005b7b7  lea     rcx, [rbx+0F0h]
0x18005b7be  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b7c3  nop
0x18005b7c4  jmp     short loc_18005B7D2
0x18005b7c6  xor     edi, edi
0x18005b7c8  mov     rbx, [rsp+0F8h+var_C8]
0x18005b7cd  mov     r14, [rsp+0F8h+var_C0]
0x18005b7d2  lea     rax, [rbx+10h]
0x18005b7d6  lea     rcx, [rbx+100h]
0x18005b7dd  mov     [rcx], rax
0x18005b7e0  xor     eax, eax
0x18005b7e2  mov     [r14], ax
0x18005b7e6  mov     [rbx], rdi
0x18005b7e9  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005b7ee  test    al, al
0x18005b7f0  jnz     short loc_18005B815
0x18005b7f2  lea     rcx, [rbx+10h]; jumptable 000000018005B4C1 cases -1,1
0x18005b7f6  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005b7fb  cmp     word ptr [rbx+0A6h], 0
0x18005b803  jz      short loc_18005B815
0x18005b805  mov     edx, 160h; unsigned __int64
0x18005b80a  mov     rcx, rbx; void *
0x18005b80d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b812  jmp     short loc_18005B815
0x18005b814  int     3; Trap to Debugger
0x18005b815  mov     rcx, [rsp+0F8h+var_28]
0x18005b81d  xor     rcx, rsp; StackCookie
0x18005b820  call    __security_check_cookie
0x18005b825  lea     r11, [rsp+0F8h+var_18]
0x18005b82d  mov     rbx, [r11+28h]
0x18005b831  mov     rsi, [r11+30h]
0x18005b835  mov     rdi, [r11+38h]
0x18005b839  mov     rsp, r11
0x18005b83c  pop     r15
0x18005b83e  pop     r14
0x18005b840  pop     r12
0x18005b842  retn
```
