# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryImageAsync$_ResumeCoro$1

- ea: `0x1800579e0`
- end: `0x180057e00`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryImageAsync$_ResumeCoro$1`
- size: `1056`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023590`
- `0x1800579d0`

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
- `0x1800579e0`
- `0x18005e260`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x180057a6d`
- `KERNEL32!InitOnceExecuteOnce` at `0x180057a6d`

## string_xrefs

- `0x180057ac6`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryImageAsync__ResumeCoro_1(
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
  _QWORD *v16; // [rsp+48h] [rbp-C0h]
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
      v16 = (_QWORD *)*((_QWORD *)a1 + 18);
      *((_QWORD *)a1 + 32) = 0;
      *((_DWORD *)a1 + 66) = 586;
      *((_QWORD *)a1 + 34) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      v7 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))(*((_QWORD *)a1 + 17) + 104LL);
      if ( v7 )
      {
        *((_QWORD *)a1 + 36) = 0;
        (**v7)(
          v7,
          winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex5>,
          a1 + 288);
        v8 = *((_QWORD *)a1 + 36);
        v19 = v8;
      }
      else
      {
        v8 = 0;
      }
      *((_QWORD *)a1 + 35) = v8;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)v8 + 56LL))(
             *((_QWORD *)a1 + 35),
             *v16,
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
0x1800579e0  mov     r11, rsp
0x1800579e3  mov     [r11+10h], rbx
0x1800579e7  mov     [r11+18h], rsi
0x1800579eb  mov     [r11+8], rcx
0x1800579ef  push    rdi
0x1800579f0  push    r12
0x1800579f2  push    r13
0x1800579f4  push    r14
0x1800579f6  push    r15
0x1800579f8  sub     rsp, 0E0h
0x1800579ff  mov     rax, cs:__security_cookie
0x180057a06  xor     rax, rsp
0x180057a09  mov     [rsp+108h+var_38], rax
0x180057a11  mov     rdi, rcx
0x180057a14  mov     [rsp+108h+var_C8], rcx
0x180057a19  lea     r15, [rdi+0A0h]
0x180057a20  mov     [rsp+108h+var_B0], r15
0x180057a25  movzx   eax, word ptr [r15]
0x180057a29  mov     [rsp+108h+var_D6], ax
0x180057a2e  inc     ax; switch 7 cases
0x180057a31  cmp     ax, 6
0x180057a35  ja      def_180057A50; jumptable 0000000180057A50 default case, case 0
0x180057a3b  movsx   rax, ax
0x180057a3f  lea     rdx, cs:180000000h
0x180057a46  mov     ecx, ds:(jpt_180057A50 - 180000000h)[rdx+rax*4]
0x180057a4d  add     rcx, rdx
0x180057a50  jmp     rcx; switch jump
0x180057a52  jmp     loc_180057D91; jumptable 0000000180057A50 case 3
0x180057a57  xor     esi, esi; jumptable 0000000180057A50 case 2
0x180057a59  xor     r9d, r9d; Context
0x180057a5c  xor     r8d, r8d; Parameter
0x180057a5f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180057a66  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x180057a6d  call    cs:__imp_InitOnceExecuteOnce
0x180057a73  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, sil; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x180057a7a  jz      short loc_180057A9A
0x180057a7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376> `wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl(void)'::`2'::impl
0x180057a83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(wil::ReportingKind)
0x180057a88  mov     rcx, [rsp+108h]; this
0x180057a90  test    al, al
0x180057a92  jnz     short loc_180057A9A
0x180057a94  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180057a9a  mov     rcx, [rdi+98h]
0x180057aa1  call    ??$GetAsgImpl@USemanticQueryOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticQueryOptions@1234@@Z
0x180057aa6  mov     r13, rax
0x180057aa9  mov     rax, [rdi+90h]
0x180057ab0  mov     [rsp+108h+var_C0], rax
0x180057ab5  mov     [rdi+100h], rsi
0x180057abc  mov     dword ptr [rdi+108h], 24Ah
0x180057ac6  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180057acd  mov     [rdi+110h], rax
0x180057ad4  mov     rcx, [rdi+88h]
0x180057adb  mov     rcx, [rcx+68h]
0x180057adf  test    rcx, rcx
0x180057ae2  jnz     short loc_180057AE9
0x180057ae4  mov     rax, rsi
0x180057ae7  jmp     short loc_180057B19
0x180057ae9  mov     [rdi+120h], rsi
0x180057af0  mov     rax, [rcx]
0x180057af3  lea     r8, [rdi+120h]
0x180057afa  lea     rdx, ??$guid_v@UISemanticImageIndex5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex5>
0x180057b01  mov     rax, [rax]
0x180057b04  call    cs:__guard_dispatch_icall_fptr
0x180057b0a  mov     rax, [rdi+120h]
0x180057b11  mov     [rsp+108h+var_70], rax
0x180057b19  mov     [rdi+118h], rax
0x180057b20  mov     [rsp+108h+var_D0], rax
0x180057b25  mov     rcx, [rax]
0x180057b28  mov     rax, [rcx+38h]
0x180057b2c  mov     rcx, [rdi+118h]
0x180057b33  mov     [rsp+108h+var_D0], rcx
0x180057b38  lea     r9, [rdi+100h]
0x180057b3f  mov     r8, [r13+0]
0x180057b43  mov     rdx, [rsp+108h+var_C0]
0x180057b48  mov     rdx, [rdx]
0x180057b4b  call    cs:__guard_dispatch_icall_fptr
0x180057b51  test    eax, eax
0x180057b53  jns     short loc_180057B67
0x180057b55  lfence
0x180057b58  lea     rdx, [rdi+108h]
0x180057b5f  mov     ecx, eax
0x180057b61  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180057b67  lea     rcx, [rdi+118h]
0x180057b6e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057b73  lea     rdx, [rdi+0A8h]
0x180057b7a  mov     rax, [rdi+100h]
0x180057b81  mov     [rsp+108h+var_68], rax
0x180057b89  mov     [rdx], rax
0x180057b8c  mov     eax, [rdi+70h]
0x180057b8f  cmp     eax, 2
0x180057b92  jnz     short loc_180057BCA
0x180057b94  lea     rdx, [rdi+128h]; struct winrt::impl::slim_source_location *
0x180057b9b  mov     dword ptr [rdx], 0F8Ch
0x180057ba1  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180057ba8  mov     [rdi+130h], rax
0x180057baf  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180057bb4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180057bb9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180057bc0  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180057bc5  call    _CxxThrowException
0x180057bca  lea     rcx, [rdi+0B0h]
0x180057bd1  mov     [rcx], rsi
0x180057bd4  mov     [rdi+0B8h], rdx
0x180057bdb  mov     [rdi+0C0h], rsi
0x180057be2  mov     byte ptr [rdi+0C8h], 1
0x180057be9  mov     eax, 4
0x180057bee  mov     [r15], ax
0x180057bf2  mov     rdx, rdi
0x180057bf5  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>)
0x180057bfa  test    al, al
0x180057bfc  jz      short loc_180057C58
0x180057bfe  jmp     loc_180057DB4
0x180057c03  cmp     qword ptr [rdi+0B0h], 0; jumptable 0000000180057A50 case 5
0x180057c0b  jz      short loc_180057C37
0x180057c0d  mov     rbx, [rdi+0B0h]
0x180057c14  mov     [rsp+108h+var_90], rbx
0x180057c19  xor     esi, esi
0x180057c1b  mov     eax, esi
0x180057c1d  xchg    rax, [rbx]
0x180057c20  cmp     rax, 1
0x180057c24  jnz     short loc_180057C37
0x180057c26  call    _Thrd_yield
0x180057c2b  mov     rax, rsi
0x180057c2e  xchg    rax, [rbx]
0x180057c31  cmp     rax, 1
0x180057c35  jz      short loc_180057C26
0x180057c37  lea     rcx, [rdi+0A8h]
0x180057c3e  mov     rax, [rcx]
0x180057c41  mov     [rsp+108h+var_B8], rax
0x180057c46  test    rax, rax
0x180057c49  jz      short loc_180057C51
0x180057c4b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057c50  nop
0x180057c51  jmp     loc_180057D91; jumptable 0000000180057A50 cases -1,1
0x180057c56  xor     esi, esi; jumptable 0000000180057A50 case 4
0x180057c58  lea     rdx, [rdi+0D0h]
0x180057c5f  lea     rcx, [rdi+0B0h]
0x180057c66  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x180057c6b  nop
0x180057c6c  cmp     qword ptr [rdi+0B0h], 0
0x180057c74  jz      short loc_180057CA1
0x180057c76  mov     rbx, [rdi+0B0h]
0x180057c7d  mov     [rsp+108h+var_90], rbx
0x180057c82  mov     rcx, rsi
0x180057c85  xchg    rcx, [rbx]
0x180057c88  cmp     rcx, 1
0x180057c8c  jnz     short loc_180057CA1
0x180057c8e  xchg    ax, ax
0x180057c90  call    _Thrd_yield
0x180057c95  mov     rax, rsi
0x180057c98  xchg    rax, [rbx]
0x180057c9b  cmp     rax, 1
0x180057c9f  jz      short loc_180057C90
0x180057ca1  lea     rcx, [rdi+0A8h]
0x180057ca8  mov     rax, [rcx]
0x180057cab  mov     [rsp+108h+var_B8], rax
0x180057cb0  test    rax, rax
0x180057cb3  jz      short loc_180057CBA
0x180057cb5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057cba  mov     ecx, 20h ; ' '; Size
0x180057cbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057cc4  mov     rcx, rax
0x180057cc7  lea     rbx, [rax+10h]
0x180057ccb  lea     rax, ??_7?$produce@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIQueryResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable'
0x180057cd2  mov     [rbx], rax
0x180057cd5  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180057cdc  mov     qword ptr [rcx+8], 1
0x180057ce4  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x180057ceb  mov     [rcx], rax
0x180057cee  mov     rax, [rdi+0D0h]
0x180057cf5  mov     [rdi+0D0h], rsi
0x180057cfc  mov     [rcx+18h], rax
0x180057d00  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x180057d07  mov     [rcx], rax
0x180057d0a  test    rcx, rcx
0x180057d0d  cmovz   rbx, rsi
0x180057d11  lea     rcx, [rdi+0D8h]
0x180057d18  mov     [rcx], rbx
0x180057d1b  lea     r14, [rdi+78h]
0x180057d1f  cmp     r14, rcx
0x180057d22  jz      short loc_180057D37
0x180057d24  cmp     qword ptr [r14], 0
0x180057d28  jz      short loc_180057D32
0x180057d2a  mov     rcx, r14
0x180057d2d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057d32  mov     [r14], rbx
0x180057d35  jmp     short loc_180057D42
0x180057d37  test    rbx, rbx
0x180057d3a  jz      short loc_180057D42
0x180057d3c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057d41  nop
0x180057d42  mov     rax, [rdi+0D0h]
0x180057d49  mov     [rsp+108h+var_60], rax
0x180057d51  test    rax, rax
0x180057d54  jz      short loc_180057D63
0x180057d56  lea     rcx, [rdi+0D0h]
0x180057d5d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057d62  nop
0x180057d63  jmp     short loc_180057D71
0x180057d65  xor     esi, esi
0x180057d67  mov     rdi, [rsp+108h+var_C8]
0x180057d6c  mov     r15, [rsp+108h+var_B0]
0x180057d71  lea     rax, [rdi+10h]
0x180057d75  lea     rcx, [rdi+0E0h]
0x180057d7c  mov     [rcx], rax
0x180057d7f  xor     eax, eax
0x180057d81  mov     [r15], ax
0x180057d85  mov     [rdi], rsi
0x180057d88  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180057d8d  test    al, al
0x180057d8f  jnz     short loc_180057DB4
0x180057d91  lea     rcx, [rdi+10h]; jumptable 0000000180057A50 cases -1,1
0x180057d95  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180057d9a  cmp     word ptr [rdi+0A2h], 0
0x180057da2  jz      short loc_180057DB4
0x180057da4  mov     edx, 140h; unsigned __int64
0x180057da9  mov     rcx, rdi; void *
0x180057dac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180057db1  jmp     short loc_180057DB4
0x180057db3  int     3; Trap to Debugger
0x180057db4  mov     rcx, [rsp+108h+var_38]
0x180057dbc  xor     rcx, rsp; StackCookie
0x180057dbf  call    __security_check_cookie
0x180057dc4  lea     r11, [rsp+108h+var_28]
0x180057dcc  mov     rbx, [r11+38h]
0x180057dd0  mov     rsi, [r11+40h]
0x180057dd4  mov     rsp, r11
0x180057dd7  pop     r15
0x180057dd9  pop     r14
0x180057ddb  pop     r13
0x180057ddd  pop     r12
0x180057ddf  pop     rdi
0x180057de0  retn
```
