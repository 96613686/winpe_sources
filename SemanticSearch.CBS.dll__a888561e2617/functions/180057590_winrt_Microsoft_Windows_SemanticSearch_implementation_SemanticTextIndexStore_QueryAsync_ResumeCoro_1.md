# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryAsync$_ResumeCoro$1

- ea: `0x180057590`
- end: `0x1800579d0`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryAsync$_ResumeCoro$1`
- size: `1088`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023ad0`
- `0x180057580`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001ee40`
- `0x180020f30`
- `0x180020fc0`
- `0x180021990`
- `0x18002ee40`
- `0x18002ff00`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x180057590`
- `0x18005e260`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18005761d`
- `KERNEL32!InitOnceExecuteOnce` at `0x18005761d`

## string_xrefs

- `0x18005767b`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::QueryAsync__ResumeCoro_1(
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
      v6 = (_QWORD *)winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticQueryOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions>(a1 + 152);
      v16 = (_QWORD *)winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryEmbeddings,winrt::Microsoft::Windows::SemanticSearch::QueryEmbeddings>(*((_QWORD *)a1 + 18));
      *((_QWORD *)a1 + 32) = 0;
      *((_DWORD *)a1 + 66) = 978;
      *((_QWORD *)a1 + 34) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      v7 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))(*((_QWORD *)a1 + 17) + 104LL);
      if ( v7 )
      {
        *((_QWORD *)a1 + 36) = 0;
        (**v7)(
          v7,
          winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>,
          a1 + 288);
        v8 = *((_QWORD *)a1 + 36);
        v19 = v8;
      }
      else
      {
        v8 = 0;
      }
      *((_QWORD *)a1 + 35) = v8;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)v8 + 48LL))(
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
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
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
0x180057590  mov     r11, rsp
0x180057593  mov     [r11+10h], rbx
0x180057597  mov     [r11+18h], rsi
0x18005759b  mov     [r11+8], rcx
0x18005759f  push    rdi
0x1800575a0  push    r12
0x1800575a2  push    r13
0x1800575a4  push    r14
0x1800575a6  push    r15
0x1800575a8  sub     rsp, 0E0h
0x1800575af  mov     rax, cs:__security_cookie
0x1800575b6  xor     rax, rsp
0x1800575b9  mov     [rsp+108h+var_38], rax
0x1800575c1  mov     rdi, rcx
0x1800575c4  mov     [rsp+108h+var_C8], rcx
0x1800575c9  lea     r15, [rdi+0A0h]
0x1800575d0  mov     [rsp+108h+var_B0], r15
0x1800575d5  movzx   eax, word ptr [r15]
0x1800575d9  mov     [rsp+108h+var_D6], ax
0x1800575de  inc     ax; switch 7 cases
0x1800575e1  cmp     ax, 6
0x1800575e5  ja      def_180057600; jumptable 0000000180057600 default case, case 0
0x1800575eb  movsx   rax, ax
0x1800575ef  lea     rdx, cs:180000000h
0x1800575f6  mov     ecx, ds:(jpt_180057600 - 180000000h)[rdx+rax*4]
0x1800575fd  add     rcx, rdx
0x180057600  jmp     rcx; switch jump
0x180057602  jmp     loc_180057950; jumptable 0000000180057600 case 3
0x180057607  xor     esi, esi; jumptable 0000000180057600 case 2
0x180057609  xor     r9d, r9d; Context
0x18005760c  xor     r8d, r8d; Parameter
0x18005760f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180057616  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x18005761d  call    cs:__imp_InitOnceExecuteOnce
0x180057623  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, sil; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x18005762a  jz      short loc_18005764A
0x18005762c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376> `wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl(void)'::`2'::impl
0x180057633  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(wil::ReportingKind)
0x180057638  mov     rcx, [rsp+108h]; this
0x180057640  test    al, al
0x180057642  jnz     short loc_18005764A
0x180057644  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005764a  lea     rcx, [rdi+98h]
0x180057651  call    ??$GetAsgImpl@USemanticQueryOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticQueryOptions@1234@@Z
0x180057656  mov     r13, rax
0x180057659  mov     rcx, [rdi+90h]
0x180057660  call    ??$GetAsgImpl@UQueryEmbeddings@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUQueryEmbeddings@1234@@Z
0x180057665  mov     [rsp+108h+var_C0], rax
0x18005766a  mov     [rdi+100h], rsi
0x180057671  mov     dword ptr [rdi+108h], 3D2h
0x18005767b  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180057682  mov     [rdi+110h], rax
0x180057689  mov     rcx, [rdi+88h]
0x180057690  mov     rcx, [rcx+68h]
0x180057694  test    rcx, rcx
0x180057697  jnz     short loc_18005769E
0x180057699  mov     rax, rsi
0x18005769c  jmp     short loc_1800576CE
0x18005769e  mov     [rdi+120h], rsi
0x1800576a5  mov     rax, [rcx]
0x1800576a8  lea     r8, [rdi+120h]
0x1800576af  lea     rdx, ??$guid_v@UISemanticIndex5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>
0x1800576b6  mov     rax, [rax]
0x1800576b9  call    cs:__guard_dispatch_icall_fptr
0x1800576bf  mov     rax, [rdi+120h]
0x1800576c6  mov     [rsp+108h+var_70], rax
0x1800576ce  mov     [rdi+118h], rax
0x1800576d5  mov     [rsp+108h+var_D0], rax
0x1800576da  mov     rcx, [rax]
0x1800576dd  mov     rax, [rcx+30h]
0x1800576e1  mov     rcx, [rdi+118h]
0x1800576e8  mov     [rsp+108h+var_D0], rcx
0x1800576ed  lea     r9, [rdi+100h]
0x1800576f4  mov     r8, [r13+0]
0x1800576f8  mov     rdx, [rsp+108h+var_C0]
0x1800576fd  mov     rdx, [rdx]
0x180057700  call    cs:__guard_dispatch_icall_fptr
0x180057706  test    eax, eax
0x180057708  jns     short loc_18005771C
0x18005770a  lfence
0x18005770d  lea     rdx, [rdi+108h]
0x180057714  mov     ecx, eax
0x180057716  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005771c  lea     rcx, [rdi+118h]
0x180057723  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057728  lea     rdx, [rdi+0A8h]
0x18005772f  mov     rax, [rdi+100h]
0x180057736  mov     [rsp+108h+var_68], rax
0x18005773e  mov     [rdx], rax
0x180057741  mov     eax, [rdi+70h]
0x180057744  cmp     eax, 2
0x180057747  jnz     short loc_18005777F
0x180057749  lea     rdx, [rdi+128h]; struct winrt::impl::slim_source_location *
0x180057750  mov     dword ptr [rdx], 0F8Ch
0x180057756  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005775d  mov     [rdi+130h], rax
0x180057764  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180057769  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005776e  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180057775  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18005777a  call    _CxxThrowException
0x18005777f  lea     rcx, [rdi+0B0h]
0x180057786  mov     [rcx], rsi
0x180057789  mov     [rdi+0B8h], rdx
0x180057790  mov     [rdi+0C0h], rsi
0x180057797  mov     byte ptr [rdi+0C8h], 1
0x18005779e  mov     eax, 4
0x1800577a3  mov     [r15], ax
0x1800577a7  mov     rdx, rdi
0x1800577aa  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>)
0x1800577af  test    al, al
0x1800577b1  jz      short loc_180057812
0x1800577b3  jmp     loc_180057985
0x1800577b8  cmp     qword ptr [rdi+0B0h], 0; jumptable 0000000180057600 case 5
0x1800577c0  jz      short loc_1800577F1
0x1800577c2  mov     rbx, [rdi+0B0h]
0x1800577c9  mov     [rsp+108h+var_90], rbx
0x1800577ce  xor     esi, esi
0x1800577d0  mov     eax, esi
0x1800577d2  xchg    rax, [rbx]
0x1800577d5  cmp     rax, 1
0x1800577d9  jnz     short loc_1800577F1
0x1800577db  nop     dword ptr [rax+rax+00h]
0x1800577e0  call    _Thrd_yield
0x1800577e5  mov     rax, rsi
0x1800577e8  xchg    rax, [rbx]
0x1800577eb  cmp     rax, 1
0x1800577ef  jz      short loc_1800577E0
0x1800577f1  lea     rcx, [rdi+0A8h]
0x1800577f8  mov     rax, [rcx]
0x1800577fb  mov     [rsp+108h+var_B8], rax
0x180057800  test    rax, rax
0x180057803  jz      short loc_18005780B
0x180057805  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005780a  nop
0x18005780b  jmp     loc_180057950; jumptable 0000000180057600 cases -1,1
0x180057810  xor     esi, esi; jumptable 0000000180057600 case 4
0x180057812  lea     rdx, [rdi+0D0h]
0x180057819  lea     rcx, [rdi+0B0h]
0x180057820  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x180057825  nop
0x180057826  cmp     qword ptr [rdi+0B0h], 0
0x18005782e  jz      short loc_180057859
0x180057830  mov     rbx, [rdi+0B0h]
0x180057837  mov     [rsp+108h+var_90], rbx
0x18005783c  mov     rcx, rsi
0x18005783f  xchg    rcx, [rbx]
0x180057842  cmp     rcx, 1
0x180057846  jnz     short loc_180057859
0x180057848  call    _Thrd_yield
0x18005784d  mov     rax, rsi
0x180057850  xchg    rax, [rbx]
0x180057853  cmp     rax, 1
0x180057857  jz      short loc_180057848
0x180057859  lea     rcx, [rdi+0A8h]
0x180057860  mov     rax, [rcx]
0x180057863  mov     [rsp+108h+var_B8], rax
0x180057868  test    rax, rax
0x18005786b  jz      short loc_180057872
0x18005786d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057872  mov     ecx, 20h ; ' '; Size
0x180057877  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005787c  mov     rcx, rax
0x18005787f  lea     rbx, [rax+10h]
0x180057883  lea     rax, ??_7?$produce@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIQueryResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable'
0x18005788a  mov     [rbx], rax
0x18005788d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180057894  mov     qword ptr [rcx+8], 1
0x18005789c  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x1800578a3  mov     [rcx], rax
0x1800578a6  mov     rax, [rdi+0D0h]
0x1800578ad  mov     [rdi+0D0h], rsi
0x1800578b4  mov     [rcx+18h], rax
0x1800578b8  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x1800578bf  mov     [rcx], rax
0x1800578c2  test    rcx, rcx
0x1800578c5  cmovz   rbx, rsi
0x1800578c9  lea     rcx, [rdi+0D8h]
0x1800578d0  mov     [rcx], rbx
0x1800578d3  lea     r14, [rdi+78h]
0x1800578d7  cmp     r14, rcx
0x1800578da  jz      short loc_1800578EF
0x1800578dc  cmp     qword ptr [r14], 0
0x1800578e0  jz      short loc_1800578EA
0x1800578e2  mov     rcx, r14
0x1800578e5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800578ea  mov     [r14], rbx
0x1800578ed  jmp     short loc_1800578FA
0x1800578ef  test    rbx, rbx
0x1800578f2  jz      short loc_1800578FA
0x1800578f4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800578f9  nop
0x1800578fa  mov     rax, [rdi+0D0h]
0x180057901  mov     [rsp+108h+var_60], rax
0x180057909  test    rax, rax
0x18005790c  jz      short loc_18005791B
0x18005790e  lea     rcx, [rdi+0D0h]
0x180057915  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005791a  nop
0x18005791b  jmp     short loc_180057929
0x18005791d  xor     esi, esi
0x18005791f  mov     rdi, [rsp+108h+var_C8]
0x180057924  mov     r15, [rsp+108h+var_B0]
0x180057929  lea     rax, [rdi+10h]
0x18005792d  lea     rcx, [rdi+0E0h]
0x180057934  mov     [rcx], rax
0x180057937  xor     eax, eax
0x180057939  mov     [r15], ax
0x18005793d  mov     [rdi], rsi
0x180057940  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180057945  test    al, al
0x180057947  jnz     short loc_180057985
0x180057949  nop     dword ptr [rax+00000000h]
0x180057950  lea     rcx, [rdi+10h]; jumptable 0000000180057600 cases -1,1
0x180057954  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180057959  lea     rcx, [rdi+98h]
0x180057960  cmp     qword ptr [rcx], 0
0x180057964  jz      short loc_18005796B
0x180057966  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005796b  cmp     word ptr [rdi+0A2h], 0
0x180057973  jz      short loc_180057985
0x180057975  mov     edx, 140h; unsigned __int64
0x18005797a  mov     rcx, rdi; void *
0x18005797d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180057982  jmp     short loc_180057985
0x180057984  int     3; Trap to Debugger
0x180057985  mov     rcx, [rsp+108h+var_38]
0x18005798d  xor     rcx, rsp; StackCookie
0x180057990  call    __security_check_cookie
0x180057995  lea     r11, [rsp+108h+var_28]
0x18005799d  mov     rbx, [r11+38h]
0x1800579a1  mov     rsi, [r11+40h]
0x1800579a5  mov     rsp, r11
0x1800579a8  pop     r15
0x1800579aa  pop     r14
0x1800579ac  pop     r13
0x1800579ae  pop     r12
0x1800579b0  pop     rdi
0x1800579b1  retn
```
