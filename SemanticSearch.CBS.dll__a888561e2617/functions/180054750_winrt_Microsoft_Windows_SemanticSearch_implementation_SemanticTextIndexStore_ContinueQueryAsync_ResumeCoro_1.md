# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::ContinueQueryAsync$_ResumeCoro$1

- ea: `0x180054750`
- end: `0x180054b60`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::ContinueQueryAsync$_ResumeCoro$1`
- size: `1040`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023980`
- `0x180054740`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001ee40`
- `0x180021050`
- `0x180021990`
- `0x18002ee40`
- `0x18002ff00`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x180054750`
- `0x18005e260`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1800547dd`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800547dd`

## string_xrefs

- `0x18005482a`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::ContinueQueryAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r15
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 *Continuation; // r13
  void (__fastcall ***v7)(_QWORD, __int64 *, char *); // rcx
  __int64 v8; // rax
  int v9; // eax
  volatile __int64 *v10; // rbx
  volatile __int64 *v11; // rbx
  _QWORD *v12; // rcx
  _QWORD *v13; // r14
  __int64 v14; // rax
  _QWORD *v15; // rbx
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-A8h] BYREF
  volatile __int64 *v17; // [rsp+68h] [rbp-90h]
  __int64 v18; // [rsp+88h] [rbp-70h]
  __int64 v19; // [rsp+90h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = a1 + 152;
  switch ( *((_WORD *)a1 + 76) )
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
      Continuation = winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryContinuationToken,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken>(*((_QWORD **)a1 + 18));
      *((_QWORD *)a1 + 28) = 0;
      *((_DWORD *)a1 + 64) = 984;
      *((_QWORD *)a1 + 33) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      v7 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))(*((_QWORD *)a1 + 17) + 104LL);
      if ( v7 )
      {
        *((_QWORD *)a1 + 35) = 0;
        (**v7)(
          v7,
          winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>,
          a1 + 280);
        v8 = *((_QWORD *)a1 + 35);
        v18 = v8;
      }
      else
      {
        v8 = 0;
      }
      *((_QWORD *)a1 + 34) = v8;
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)v8 + 56LL))(
             *((_QWORD *)a1 + 34),
             *Continuation,
             a1 + 224);
      if ( v9 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v9, a1 + 256);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 272);
      v19 = *((_QWORD *)a1 + 28);
      *((_QWORD *)a1 + 20) = v19;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 72) = 3980;
        *((_QWORD *)a1 + 37) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 288));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 21) = 0;
      *((_QWORD *)a1 + 22) = a1 + 160;
      *((_QWORD *)a1 + 23) = 0;
      a1[192] = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(
                              (_QWORD *)a1 + 21,
                              (__int64)a1) )
        return;
      goto LABEL_20;
    case 4:
LABEL_20:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(
        (__int64)(a1 + 168),
        (_QWORD *)a1 + 25);
      if ( *((_QWORD *)a1 + 21) )
      {
        v11 = (volatile __int64 *)*((_QWORD *)a1 + 21);
        v17 = v11;
        while ( _InterlockedExchange64(v11, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 20) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
      v12 = operator new(0x20u);
      v13 = v12 + 2;
      v12[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v12[1] = 1;
      *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable';
      v14 = *((_QWORD *)a1 + 25);
      *((_QWORD *)a1 + 25) = 0;
      v12[3] = v14;
      *v12 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable';
      if ( !v12 )
        v13 = 0;
      *((_QWORD *)a1 + 26) = v13;
      v15 = a1 + 120;
      if ( a1 + 120 == a1 + 208 )
      {
        if ( v13 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
      }
      else
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        *v15 = v13;
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      *((_QWORD *)a1 + 27) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 27) )
        goto LABEL_36;
      return;
    case 5:
      if ( *((_QWORD *)a1 + 21) )
      {
        v10 = (volatile __int64 *)*((_QWORD *)a1 + 21);
        v17 = v10;
        while ( _InterlockedExchange64(v10, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 20) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
LABEL_36:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 77) )
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
0x180054750  mov     r11, rsp
0x180054753  mov     [r11+10h], rbx
0x180054757  mov     [r11+18h], rsi
0x18005475b  mov     [r11+8], rcx
0x18005475f  push    rdi
0x180054760  push    r12
0x180054762  push    r13
0x180054764  push    r14
0x180054766  push    r15
0x180054768  sub     rsp, 0D0h
0x18005476f  mov     rax, cs:__security_cookie
0x180054776  xor     rax, rsp
0x180054779  mov     [rsp+0F8h+var_38], rax
0x180054781  mov     rdi, rcx
0x180054784  mov     [rsp+0F8h+var_C8], rcx
0x180054789  lea     r15, [rdi+98h]
0x180054790  mov     [rsp+0F8h+var_B8], r15
0x180054795  movzx   eax, word ptr [r15]
0x180054799  mov     [rsp+0F8h+var_D6], ax
0x18005479e  inc     ax; switch 7 cases
0x1800547a1  cmp     ax, 6
0x1800547a5  ja      def_1800547C0; jumptable 00000001800547C0 default case, case 0
0x1800547ab  movsx   rax, ax
0x1800547af  lea     rdx, cs:180000000h
0x1800547b6  mov     ecx, ds:(jpt_1800547C0 - 180000000h)[rdx+rax*4]
0x1800547bd  add     rcx, rdx
0x1800547c0  jmp     rcx; switch jump
0x1800547c2  jmp     loc_180054AF1; jumptable 00000001800547C0 case 3
0x1800547c7  xor     esi, esi; jumptable 00000001800547C0 case 2
0x1800547c9  xor     r9d, r9d; Context
0x1800547cc  xor     r8d, r8d; Parameter
0x1800547cf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800547d6  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x1800547dd  call    cs:__imp_InitOnceExecuteOnce
0x1800547e3  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, sil; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x1800547ea  jz      short loc_18005480A
0x1800547ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376> `wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl(void)'::`2'::impl
0x1800547f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(wil::ReportingKind)
0x1800547f8  mov     rcx, [rsp+0F8h]; this
0x180054800  test    al, al
0x180054802  jnz     short loc_18005480A
0x180054804  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005480a  mov     rcx, [rdi+90h]
0x180054811  call    ??$GetAsgImpl@UQueryContinuationToken@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUQueryContinuationToken@1234@@Z
0x180054816  mov     r13, rax
0x180054819  mov     [rdi+0E0h], rsi
0x180054820  mov     dword ptr [rdi+100h], 3D8h
0x18005482a  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180054831  mov     [rdi+108h], rax
0x180054838  mov     rcx, [rdi+88h]
0x18005483f  mov     rcx, [rcx+68h]
0x180054843  test    rcx, rcx
0x180054846  jnz     short loc_18005484D
0x180054848  mov     rax, rsi
0x18005484b  jmp     short loc_18005487D
0x18005484d  mov     [rdi+118h], rsi
0x180054854  mov     rax, [rcx]
0x180054857  lea     r8, [rdi+118h]
0x18005485e  lea     rdx, ??$guid_v@UISemanticIndex5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>
0x180054865  mov     rax, [rax]
0x180054868  call    cs:__guard_dispatch_icall_fptr
0x18005486e  mov     rax, [rdi+118h]
0x180054875  mov     [rsp+0F8h+var_70], rax
0x18005487d  mov     [rdi+110h], rax
0x180054884  mov     [rsp+0F8h+var_D0], rax
0x180054889  mov     rcx, [rax]
0x18005488c  mov     rax, [rcx+38h]
0x180054890  mov     rcx, [rdi+110h]
0x180054897  mov     [rsp+0F8h+var_D0], rcx
0x18005489c  lea     r8, [rdi+0E0h]
0x1800548a3  mov     rdx, [r13+0]
0x1800548a7  call    cs:__guard_dispatch_icall_fptr
0x1800548ad  test    eax, eax
0x1800548af  jns     short loc_1800548C3
0x1800548b1  lfence
0x1800548b4  lea     rdx, [rdi+100h]
0x1800548bb  mov     ecx, eax
0x1800548bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800548c3  lea     rcx, [rdi+110h]
0x1800548ca  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800548cf  lea     rdx, [rdi+0A0h]
0x1800548d6  mov     rax, [rdi+0E0h]
0x1800548dd  mov     [rsp+0F8h+var_68], rax
0x1800548e5  mov     [rdx], rax
0x1800548e8  mov     eax, [rdi+70h]
0x1800548eb  cmp     eax, 2
0x1800548ee  jnz     short loc_180054926
0x1800548f0  lea     rdx, [rdi+120h]; struct winrt::impl::slim_source_location *
0x1800548f7  mov     dword ptr [rdx], 0F8Ch
0x1800548fd  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180054904  mov     [rdi+128h], rax
0x18005490b  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180054910  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180054915  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005491c  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180054921  call    _CxxThrowException
0x180054926  lea     rcx, [rdi+0A8h]
0x18005492d  mov     [rcx], rsi
0x180054930  mov     [rdi+0B0h], rdx
0x180054937  mov     [rdi+0B8h], rsi
0x18005493e  mov     byte ptr [rdi+0C0h], 1
0x180054945  mov     eax, 4
0x18005494a  mov     [r15], ax
0x18005494e  mov     rdx, rdi
0x180054951  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>)
0x180054956  test    al, al
0x180054958  jz      short loc_1800549B4
0x18005495a  jmp     loc_180054B14
0x18005495f  cmp     qword ptr [rdi+0A8h], 0; jumptable 00000001800547C0 case 5
0x180054967  jz      short loc_180054993
0x180054969  mov     rbx, [rdi+0A8h]
0x180054970  mov     [rsp+0F8h+var_90], rbx
0x180054975  xor     esi, esi
0x180054977  mov     eax, esi
0x180054979  xchg    rax, [rbx]
0x18005497c  cmp     rax, 1
0x180054980  jnz     short loc_180054993
0x180054982  call    _Thrd_yield
0x180054987  mov     rax, rsi
0x18005498a  xchg    rax, [rbx]
0x18005498d  cmp     rax, 1
0x180054991  jz      short loc_180054982
0x180054993  lea     rcx, [rdi+0A0h]
0x18005499a  mov     rax, [rcx]
0x18005499d  mov     [rsp+0F8h+var_C0], rax
0x1800549a2  test    rax, rax
0x1800549a5  jz      short loc_1800549AD
0x1800549a7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800549ac  nop
0x1800549ad  jmp     loc_180054AF1; jumptable 00000001800547C0 cases -1,1
0x1800549b2  xor     esi, esi; jumptable 00000001800547C0 case 4
0x1800549b4  lea     rdx, [rdi+0C8h]
0x1800549bb  lea     rcx, [rdi+0A8h]
0x1800549c2  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x1800549c7  nop
0x1800549c8  cmp     qword ptr [rdi+0A8h], 0
0x1800549d0  jz      short loc_180054A01
0x1800549d2  mov     rbx, [rdi+0A8h]
0x1800549d9  mov     [rsp+0F8h+var_90], rbx
0x1800549de  mov     rcx, rsi
0x1800549e1  xchg    rcx, [rbx]
0x1800549e4  cmp     rcx, 1
0x1800549e8  jnz     short loc_180054A01
0x1800549ea  nop     word ptr [rax+rax+00h]
0x1800549f0  call    _Thrd_yield
0x1800549f5  mov     rax, rsi
0x1800549f8  xchg    rax, [rbx]
0x1800549fb  cmp     rax, 1
0x1800549ff  jz      short loc_1800549F0
0x180054a01  lea     rcx, [rdi+0A0h]
0x180054a08  mov     rax, [rcx]
0x180054a0b  mov     [rsp+0F8h+var_C0], rax
0x180054a10  test    rax, rax
0x180054a13  jz      short loc_180054A1A
0x180054a15  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054a1a  mov     ecx, 20h ; ' '; Size
0x180054a1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054a24  mov     rcx, rax
0x180054a27  lea     r14, [rax+10h]
0x180054a2b  lea     rax, ??_7?$produce@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIQueryResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable'
0x180054a32  mov     [r14], rax
0x180054a35  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180054a3c  mov     qword ptr [rcx+8], 1
0x180054a44  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x180054a4b  mov     [rcx], rax
0x180054a4e  mov     rax, [rdi+0C8h]
0x180054a55  mov     [rdi+0C8h], rsi
0x180054a5c  mov     [rcx+18h], rax
0x180054a60  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x180054a67  mov     [rcx], rax
0x180054a6a  test    rcx, rcx
0x180054a6d  cmovz   r14, rsi
0x180054a71  lea     rcx, [rdi+0D0h]
0x180054a78  mov     [rcx], r14
0x180054a7b  lea     rbx, [rdi+78h]
0x180054a7f  cmp     rbx, rcx
0x180054a82  jz      short loc_180054A97
0x180054a84  cmp     qword ptr [rbx], 0
0x180054a88  jz      short loc_180054A92
0x180054a8a  mov     rcx, rbx
0x180054a8d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054a92  mov     [rbx], r14
0x180054a95  jmp     short loc_180054AA2
0x180054a97  test    r14, r14
0x180054a9a  jz      short loc_180054AA2
0x180054a9c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054aa1  nop
0x180054aa2  mov     rax, [rdi+0C8h]
0x180054aa9  mov     [rsp+0F8h+var_60], rax
0x180054ab1  test    rax, rax
0x180054ab4  jz      short loc_180054AC3
0x180054ab6  lea     rcx, [rdi+0C8h]
0x180054abd  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054ac2  nop
0x180054ac3  jmp     short loc_180054AD1
0x180054ac5  xor     esi, esi
0x180054ac7  mov     rdi, [rsp+0F8h+var_C8]
0x180054acc  mov     r15, [rsp+0F8h+var_B8]
0x180054ad1  lea     rax, [rdi+10h]
0x180054ad5  lea     rcx, [rdi+0D8h]
0x180054adc  mov     [rcx], rax
0x180054adf  xor     eax, eax
0x180054ae1  mov     [r15], ax
0x180054ae5  mov     [rdi], rsi
0x180054ae8  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180054aed  test    al, al
0x180054aef  jnz     short loc_180054B14
0x180054af1  lea     rcx, [rdi+10h]; jumptable 00000001800547C0 cases -1,1
0x180054af5  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180054afa  cmp     word ptr [rdi+9Ah], 0
0x180054b02  jz      short loc_180054B14
0x180054b04  mov     edx, 130h; unsigned __int64
0x180054b09  mov     rcx, rdi; void *
0x180054b0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054b11  jmp     short loc_180054B14
0x180054b13  int     3; Trap to Debugger
0x180054b14  mov     rcx, [rsp+0F8h+var_38]
0x180054b1c  xor     rcx, rsp; StackCookie
0x180054b1f  call    __security_check_cookie
0x180054b24  lea     r11, [rsp+0F8h+var_28]
0x180054b2c  mov     rbx, [r11+38h]
0x180054b30  mov     rsi, [r11+40h]
0x180054b34  mov     rsp, r11
0x180054b37  pop     r15
0x180054b39  pop     r14
0x180054b3b  pop     r13
0x180054b3d  pop     r12
0x180054b3f  pop     rdi
0x180054b40  retn
```
