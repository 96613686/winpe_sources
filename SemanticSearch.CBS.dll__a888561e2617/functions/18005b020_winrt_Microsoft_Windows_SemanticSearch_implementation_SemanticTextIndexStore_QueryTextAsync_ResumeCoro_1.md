# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryTextAsync$_ResumeCoro$1

- ea: `0x18005b020`
- end: `0x18005b440`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryTextAsync$_ResumeCoro$1`
- size: `1056`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003a6d0`
- `0x18005b010`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001ee40`
- `0x180020f30`
- `0x180021990`
- `0x18002ee40`
- `0x18002ff00`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x18005b020`
- `0x18005e260`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18005b0ad`
- `KERNEL32!InitOnceExecuteOnce` at `0x18005b0ad`

## string_xrefs

- `0x18005b109`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryTextAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r15
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  _QWORD *v6; // r13
  void (__fastcall ***v7)(_QWORD, __int64 *, char *); // rcx
  __int64 v8; // rax
  int v9; // eax
  volatile __int64 *v10; // rbx
  volatile __int64 *v11; // rbx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // [rsp+48h] [rbp-C0h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-A8h] BYREF
  volatile __int64 *v18; // [rsp+78h] [rbp-90h]
  __int64 v19; // [rsp+98h] [rbp-70h]
  __int64 v20; // [rsp+A0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = a1 + 160;
  switch ( *((_WORD *)a1 + 80) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_36;
    case 2:
      InitOnceExecuteOnce(
        &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
        `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
        0,
        0);
      if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
        && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(retaddr, v3, v4, v5);
      }
      v6 = (_QWORD *)winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticQueryOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions>(*((_QWORD *)a1 + 19));
      v16 = **((_QWORD **)a1 + 18);
      *((_QWORD *)a1 + 32) = 0;
      *((_DWORD *)a1 + 66) = 1068;
      *((_QWORD *)a1 + 34) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      v7 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))(*((_QWORD *)a1 + 17) + 104LL);
      if ( v7 )
      {
        *((_QWORD *)a1 + 36) = 0;
        (**v7)(
          v7,
          winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex5>,
          a1 + 288);
        v8 = *((_QWORD *)a1 + 36);
        v19 = v8;
      }
      else
      {
        v8 = 0;
      }
      *((_QWORD *)a1 + 35) = v8;
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(*(_QWORD *)v8 + 48LL))(
             *((_QWORD *)a1 + 35),
             v16,
             *v6,
             a1 + 256);
      if ( v9 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v9, a1 + 264);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 280);
      v20 = *((_QWORD *)a1 + 32);
      *((_QWORD *)a1 + 21) = v20;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 74) = 3980;
        *((_QWORD *)a1 + 38) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 296));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 22) = 0;
      *((_QWORD *)a1 + 23) = a1 + 168;
      *((_QWORD *)a1 + 24) = 0;
      a1[200] = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(
                              (_QWORD *)a1 + 22,
                              (__int64)a1) )
        return;
      goto LABEL_20;
    case 4:
LABEL_20:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(
        (__int64)(a1 + 176),
        (_QWORD *)a1 + 26);
      if ( *((_QWORD *)a1 + 22) )
      {
        v11 = (volatile __int64 *)*((_QWORD *)a1 + 22);
        v18 = v11;
        while ( _InterlockedExchange64(v11, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 21) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
      v12 = operator new(0x20u);
      v13 = v12 + 2;
      v12[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v12[1] = 1;
      *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable';
      v14 = *((_QWORD *)a1 + 26);
      *((_QWORD *)a1 + 26) = 0;
      v12[3] = v14;
      *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable';
      if ( !v12 )
        v13 = 0;
      *((_QWORD *)a1 + 27) = v13;
      v15 = a1 + 120;
      if ( a1 + 120 == a1 + 216 )
      {
        if ( v13 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 216);
      }
      else
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        *v15 = v13;
      }
      if ( *((_QWORD *)a1 + 26) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
      *((_QWORD *)a1 + 28) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 28) )
        goto LABEL_36;
      return;
    case 5:
      if ( *((_QWORD *)a1 + 22) )
      {
        v10 = (volatile __int64 *)*((_QWORD *)a1 + 22);
        v18 = v10;
        while ( _InterlockedExchange64(v10, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 21) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
LABEL_36:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 81) )
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
0x18005b020  mov     r11, rsp
0x18005b023  mov     [r11+10h], rbx
0x18005b027  mov     [r11+18h], rsi
0x18005b02b  mov     [r11+8], rcx
0x18005b02f  push    rdi
0x18005b030  push    r12
0x18005b032  push    r13
0x18005b034  push    r14
0x18005b036  push    r15
0x18005b038  sub     rsp, 0E0h
0x18005b03f  mov     rax, cs:__security_cookie
0x18005b046  xor     rax, rsp
0x18005b049  mov     [rsp+108h+var_38], rax
0x18005b051  mov     rdi, rcx
0x18005b054  mov     [rsp+108h+var_C8], rcx
0x18005b059  lea     r15, [rdi+0A0h]
0x18005b060  mov     [rsp+108h+var_B0], r15
0x18005b065  movzx   eax, word ptr [r15]
0x18005b069  mov     [rsp+108h+var_D6], ax
0x18005b06e  inc     ax; switch 7 cases
0x18005b071  cmp     ax, 6
0x18005b075  ja      def_18005B090; jumptable 000000018005B090 default case, case 0
0x18005b07b  movsx   rax, ax
0x18005b07f  lea     rdx, cs:180000000h
0x18005b086  mov     ecx, ds:(jpt_18005B090 - 180000000h)[rdx+rax*4]
0x18005b08d  add     rcx, rdx
0x18005b090  jmp     rcx; switch jump
0x18005b092  jmp     loc_18005B3D1; jumptable 000000018005B090 case 3
0x18005b097  xor     esi, esi; jumptable 000000018005B090 case 2
0x18005b099  xor     r9d, r9d; Context
0x18005b09c  xor     r8d, r8d; Parameter
0x18005b09f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005b0a6  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x18005b0ad  call    cs:__imp_InitOnceExecuteOnce
0x18005b0b3  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, sil; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x18005b0ba  jz      short loc_18005B0DA
0x18005b0bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376> `wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl(void)'::`2'::impl
0x18005b0c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(wil::ReportingKind)
0x18005b0c8  mov     rcx, [rsp+108h]; this
0x18005b0d0  test    al, al
0x18005b0d2  jnz     short loc_18005B0DA
0x18005b0d4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005b0da  mov     rcx, [rdi+98h]
0x18005b0e1  call    ??$GetAsgImpl@USemanticQueryOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticQueryOptions@1234@@Z
0x18005b0e6  mov     r13, rax
0x18005b0e9  mov     rcx, [rdi+90h]
0x18005b0f0  mov     rax, [rcx]
0x18005b0f3  mov     [rsp+108h+var_C0], rax
0x18005b0f8  mov     [rdi+100h], rsi
0x18005b0ff  mov     dword ptr [rdi+108h], 42Ch
0x18005b109  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b110  mov     [rdi+110h], rax
0x18005b117  mov     rcx, [rdi+88h]
0x18005b11e  mov     rcx, [rcx+68h]
0x18005b122  test    rcx, rcx
0x18005b125  jnz     short loc_18005B12C
0x18005b127  mov     rax, rsi
0x18005b12a  jmp     short loc_18005B15C
0x18005b12c  mov     [rdi+120h], rsi
0x18005b133  mov     rax, [rcx]
0x18005b136  lea     r8, [rdi+120h]
0x18005b13d  lea     rdx, ??$guid_v@UISemanticTextIndex5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex5>
0x18005b144  mov     rax, [rax]
0x18005b147  call    cs:__guard_dispatch_icall_fptr
0x18005b14d  mov     rax, [rdi+120h]
0x18005b154  mov     [rsp+108h+var_70], rax
0x18005b15c  mov     [rdi+118h], rax
0x18005b163  mov     [rsp+108h+var_D0], rax
0x18005b168  mov     rcx, [rax]
0x18005b16b  mov     rax, [rcx+30h]
0x18005b16f  mov     rcx, [rdi+118h]
0x18005b176  mov     [rsp+108h+var_D0], rcx
0x18005b17b  lea     r9, [rdi+100h]
0x18005b182  mov     r8, [r13+0]
0x18005b186  mov     rdx, [rsp+108h+var_C0]
0x18005b18b  call    cs:__guard_dispatch_icall_fptr
0x18005b191  test    eax, eax
0x18005b193  jns     short loc_18005B1A7
0x18005b195  lfence
0x18005b198  lea     rdx, [rdi+108h]
0x18005b19f  mov     ecx, eax
0x18005b1a1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005b1a7  lea     rcx, [rdi+118h]
0x18005b1ae  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b1b3  lea     rdx, [rdi+0A8h]
0x18005b1ba  mov     rax, [rdi+100h]
0x18005b1c1  mov     [rsp+108h+var_68], rax
0x18005b1c9  mov     [rdx], rax
0x18005b1cc  mov     eax, [rdi+70h]
0x18005b1cf  cmp     eax, 2
0x18005b1d2  jnz     short loc_18005B20A
0x18005b1d4  lea     rdx, [rdi+128h]; struct winrt::impl::slim_source_location *
0x18005b1db  mov     dword ptr [rdx], 0F8Ch
0x18005b1e1  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005b1e8  mov     [rdi+130h], rax
0x18005b1ef  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18005b1f4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005b1f9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005b200  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18005b205  call    _CxxThrowException
0x18005b20a  lea     rcx, [rdi+0B0h]
0x18005b211  mov     [rcx], rsi
0x18005b214  mov     [rdi+0B8h], rdx
0x18005b21b  mov     [rdi+0C0h], rsi
0x18005b222  mov     byte ptr [rdi+0C8h], 1
0x18005b229  mov     eax, 4
0x18005b22e  mov     [r15], ax
0x18005b232  mov     rdx, rdi
0x18005b235  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>)
0x18005b23a  test    al, al
0x18005b23c  jz      short loc_18005B298
0x18005b23e  jmp     loc_18005B3F4
0x18005b243  cmp     qword ptr [rdi+0B0h], 0; jumptable 000000018005B090 case 5
0x18005b24b  jz      short loc_18005B277
0x18005b24d  mov     rbx, [rdi+0B0h]
0x18005b254  mov     [rsp+108h+var_90], rbx
0x18005b259  xor     esi, esi
0x18005b25b  mov     eax, esi
0x18005b25d  xchg    rax, [rbx]
0x18005b260  cmp     rax, 1
0x18005b264  jnz     short loc_18005B277
0x18005b266  call    _Thrd_yield
0x18005b26b  mov     rax, rsi
0x18005b26e  xchg    rax, [rbx]
0x18005b271  cmp     rax, 1
0x18005b275  jz      short loc_18005B266
0x18005b277  lea     rcx, [rdi+0A8h]
0x18005b27e  mov     rax, [rcx]
0x18005b281  mov     [rsp+108h+var_B8], rax
0x18005b286  test    rax, rax
0x18005b289  jz      short loc_18005B291
0x18005b28b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b290  nop
0x18005b291  jmp     loc_18005B3D1; jumptable 000000018005B090 cases -1,1
0x18005b296  xor     esi, esi; jumptable 000000018005B090 case 4
0x18005b298  lea     rdx, [rdi+0D0h]
0x18005b29f  lea     rcx, [rdi+0B0h]
0x18005b2a6  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x18005b2ab  nop
0x18005b2ac  cmp     qword ptr [rdi+0B0h], 0
0x18005b2b4  jz      short loc_18005B2E1
0x18005b2b6  mov     rbx, [rdi+0B0h]
0x18005b2bd  mov     [rsp+108h+var_90], rbx
0x18005b2c2  mov     rcx, rsi
0x18005b2c5  xchg    rcx, [rbx]
0x18005b2c8  cmp     rcx, 1
0x18005b2cc  jnz     short loc_18005B2E1
0x18005b2ce  xchg    ax, ax
0x18005b2d0  call    _Thrd_yield
0x18005b2d5  mov     rax, rsi
0x18005b2d8  xchg    rax, [rbx]
0x18005b2db  cmp     rax, 1
0x18005b2df  jz      short loc_18005B2D0
0x18005b2e1  lea     rcx, [rdi+0A8h]
0x18005b2e8  mov     rax, [rcx]
0x18005b2eb  mov     [rsp+108h+var_B8], rax
0x18005b2f0  test    rax, rax
0x18005b2f3  jz      short loc_18005B2FA
0x18005b2f5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b2fa  mov     ecx, 20h ; ' '; Size
0x18005b2ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b304  mov     rcx, rax
0x18005b307  lea     rbx, [rax+10h]
0x18005b30b  lea     rax, ??_7?$produce@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIQueryResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable'
0x18005b312  mov     [rbx], rax
0x18005b315  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b31c  mov     qword ptr [rcx+8], 1
0x18005b324  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x18005b32b  mov     [rcx], rax
0x18005b32e  mov     rax, [rdi+0D0h]
0x18005b335  mov     [rdi+0D0h], rsi
0x18005b33c  mov     [rcx+18h], rax
0x18005b340  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x18005b347  mov     [rcx], rax
0x18005b34a  test    rcx, rcx
0x18005b34d  cmovz   rbx, rsi
0x18005b351  lea     rcx, [rdi+0D8h]
0x18005b358  mov     [rcx], rbx
0x18005b35b  lea     r14, [rdi+78h]
0x18005b35f  cmp     r14, rcx
0x18005b362  jz      short loc_18005B377
0x18005b364  cmp     qword ptr [r14], 0
0x18005b368  jz      short loc_18005B372
0x18005b36a  mov     rcx, r14
0x18005b36d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b372  mov     [r14], rbx
0x18005b375  jmp     short loc_18005B382
0x18005b377  test    rbx, rbx
0x18005b37a  jz      short loc_18005B382
0x18005b37c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b381  nop
0x18005b382  mov     rax, [rdi+0D0h]
0x18005b389  mov     [rsp+108h+var_60], rax
0x18005b391  test    rax, rax
0x18005b394  jz      short loc_18005B3A3
0x18005b396  lea     rcx, [rdi+0D0h]
0x18005b39d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005b3a2  nop
0x18005b3a3  jmp     short loc_18005B3B1
0x18005b3a5  xor     esi, esi
0x18005b3a7  mov     r15, [rsp+108h+var_B0]
0x18005b3ac  mov     rdi, [rsp+108h+var_C8]
0x18005b3b1  lea     rax, [rdi+10h]
0x18005b3b5  lea     rcx, [rdi+0E0h]
0x18005b3bc  mov     [rcx], rax
0x18005b3bf  xor     eax, eax
0x18005b3c1  mov     [r15], ax
0x18005b3c5  mov     [rdi], rsi
0x18005b3c8  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005b3cd  test    al, al
0x18005b3cf  jnz     short loc_18005B3F4
0x18005b3d1  lea     rcx, [rdi+10h]; jumptable 000000018005B090 cases -1,1
0x18005b3d5  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005b3da  cmp     word ptr [rdi+0A2h], 0
0x18005b3e2  jz      short loc_18005B3F4
0x18005b3e4  mov     edx, 140h; unsigned __int64
0x18005b3e9  mov     rcx, rdi; void *
0x18005b3ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b3f1  jmp     short loc_18005B3F4
0x18005b3f3  int     3; Trap to Debugger
0x18005b3f4  mov     rcx, [rsp+108h+var_38]
0x18005b3fc  xor     rcx, rsp; StackCookie
0x18005b3ff  call    __security_check_cookie
0x18005b404  lea     r11, [rsp+108h+var_28]
0x18005b40c  mov     rbx, [r11+38h]
0x18005b410  mov     rsi, [r11+40h]
0x18005b414  mov     rsp, r11
0x18005b417  pop     r15
0x18005b419  pop     r14
0x18005b41b  pop     r13
0x18005b41d  pop     r12
0x18005b41f  pop     rdi
0x18005b420  retn
```
