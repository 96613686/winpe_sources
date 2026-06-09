# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryTextAsync$_ResumeCoro$1

- ea: `0x180057e10`
- end: `0x180058230`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryTextAsync$_ResumeCoro$1`
- size: `1056`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800236f0`
- `0x180057e00`

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
- `0x180057e10`
- `0x18005e260`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x180057e9d`
- `KERNEL32!InitOnceExecuteOnce` at `0x180057e9d`

## string_xrefs

- `0x180057ef9`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::QueryTextAsync__ResumeCoro_1(
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
      *((_DWORD *)a1 + 66) = 580;
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
0x180057e10  mov     r11, rsp
0x180057e13  mov     [r11+10h], rbx
0x180057e17  mov     [r11+18h], rsi
0x180057e1b  mov     [r11+8], rcx
0x180057e1f  push    rdi
0x180057e20  push    r12
0x180057e22  push    r13
0x180057e24  push    r14
0x180057e26  push    r15
0x180057e28  sub     rsp, 0E0h
0x180057e2f  mov     rax, cs:__security_cookie
0x180057e36  xor     rax, rsp
0x180057e39  mov     [rsp+108h+var_38], rax
0x180057e41  mov     rdi, rcx
0x180057e44  mov     [rsp+108h+var_C8], rcx
0x180057e49  lea     r15, [rdi+0A0h]
0x180057e50  mov     [rsp+108h+var_B0], r15
0x180057e55  movzx   eax, word ptr [r15]
0x180057e59  mov     [rsp+108h+var_D6], ax
0x180057e5e  inc     ax; switch 7 cases
0x180057e61  cmp     ax, 6
0x180057e65  ja      def_180057E80; jumptable 0000000180057E80 default case, case 0
0x180057e6b  movsx   rax, ax
0x180057e6f  lea     rdx, cs:180000000h
0x180057e76  mov     ecx, ds:(jpt_180057E80 - 180000000h)[rdx+rax*4]
0x180057e7d  add     rcx, rdx
0x180057e80  jmp     rcx; switch jump
0x180057e82  jmp     loc_1800581C1; jumptable 0000000180057E80 case 3
0x180057e87  xor     esi, esi; jumptable 0000000180057E80 case 2
0x180057e89  xor     r9d, r9d; Context
0x180057e8c  xor     r8d, r8d; Parameter
0x180057e8f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180057e96  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x180057e9d  call    cs:__imp_InitOnceExecuteOnce
0x180057ea3  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, sil; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x180057eaa  jz      short loc_180057ECA
0x180057eac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376> `wil::Feature<__WilFeatureTraits_Feature_58375376>::GetImpl(void)'::`2'::impl
0x180057eb3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58375376@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58375376>::__private_IsEnabled(wil::ReportingKind)
0x180057eb8  mov     rcx, [rsp+108h]; this
0x180057ec0  test    al, al
0x180057ec2  jnz     short loc_180057ECA
0x180057ec4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180057eca  mov     rcx, [rdi+98h]
0x180057ed1  call    ??$GetAsgImpl@USemanticQueryOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticQueryOptions@1234@@Z
0x180057ed6  mov     r13, rax
0x180057ed9  mov     rcx, [rdi+90h]
0x180057ee0  mov     rax, [rcx]
0x180057ee3  mov     [rsp+108h+var_C0], rax
0x180057ee8  mov     [rdi+100h], rsi
0x180057eef  mov     dword ptr [rdi+108h], 244h
0x180057ef9  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180057f00  mov     [rdi+110h], rax
0x180057f07  mov     rcx, [rdi+88h]
0x180057f0e  mov     rcx, [rcx+68h]
0x180057f12  test    rcx, rcx
0x180057f15  jnz     short loc_180057F1C
0x180057f17  mov     rax, rsi
0x180057f1a  jmp     short loc_180057F4C
0x180057f1c  mov     [rdi+120h], rsi
0x180057f23  mov     rax, [rcx]
0x180057f26  lea     r8, [rdi+120h]
0x180057f2d  lea     rdx, ??$guid_v@UISemanticImageIndex5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex5>
0x180057f34  mov     rax, [rax]
0x180057f37  call    cs:__guard_dispatch_icall_fptr
0x180057f3d  mov     rax, [rdi+120h]
0x180057f44  mov     [rsp+108h+var_70], rax
0x180057f4c  mov     [rdi+118h], rax
0x180057f53  mov     [rsp+108h+var_D0], rax
0x180057f58  mov     rcx, [rax]
0x180057f5b  mov     rax, [rcx+30h]
0x180057f5f  mov     rcx, [rdi+118h]
0x180057f66  mov     [rsp+108h+var_D0], rcx
0x180057f6b  lea     r9, [rdi+100h]
0x180057f72  mov     r8, [r13+0]
0x180057f76  mov     rdx, [rsp+108h+var_C0]
0x180057f7b  call    cs:__guard_dispatch_icall_fptr
0x180057f81  test    eax, eax
0x180057f83  jns     short loc_180057F97
0x180057f85  lfence
0x180057f88  lea     rdx, [rdi+108h]
0x180057f8f  mov     ecx, eax
0x180057f91  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180057f97  lea     rcx, [rdi+118h]
0x180057f9e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180057fa3  lea     rdx, [rdi+0A8h]
0x180057faa  mov     rax, [rdi+100h]
0x180057fb1  mov     [rsp+108h+var_68], rax
0x180057fb9  mov     [rdx], rax
0x180057fbc  mov     eax, [rdi+70h]
0x180057fbf  cmp     eax, 2
0x180057fc2  jnz     short loc_180057FFA
0x180057fc4  lea     rdx, [rdi+128h]; struct winrt::impl::slim_source_location *
0x180057fcb  mov     dword ptr [rdx], 0F8Ch
0x180057fd1  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180057fd8  mov     [rdi+130h], rax
0x180057fdf  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180057fe4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180057fe9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180057ff0  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180057ff5  call    _CxxThrowException
0x180057ffa  lea     rcx, [rdi+0B0h]
0x180058001  mov     [rcx], rsi
0x180058004  mov     [rdi+0B8h], rdx
0x18005800b  mov     [rdi+0C0h], rsi
0x180058012  mov     byte ptr [rdi+0C8h], 1
0x180058019  mov     eax, 4
0x18005801e  mov     [r15], ax
0x180058022  mov     rdx, rdi
0x180058025  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@SemanticSearch@3Microsoft@4@AEBUQueryContinuationToken@7384@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore &,winrt::Microsoft::Windows::SemanticSearch::QueryContinuationToken const &>::promise_type>)
0x18005802a  test    al, al
0x18005802c  jz      short loc_180058088
0x18005802e  jmp     loc_1800581E4
0x180058033  cmp     qword ptr [rdi+0B0h], 0; jumptable 0000000180057E80 case 5
0x18005803b  jz      short loc_180058067
0x18005803d  mov     rbx, [rdi+0B0h]
0x180058044  mov     [rsp+108h+var_90], rbx
0x180058049  xor     esi, esi
0x18005804b  mov     eax, esi
0x18005804d  xchg    rax, [rbx]
0x180058050  cmp     rax, 1
0x180058054  jnz     short loc_180058067
0x180058056  call    _Thrd_yield
0x18005805b  mov     rax, rsi
0x18005805e  xchg    rax, [rbx]
0x180058061  cmp     rax, 1
0x180058065  jz      short loc_180058056
0x180058067  lea     rcx, [rdi+0A8h]
0x18005806e  mov     rax, [rcx]
0x180058071  mov     [rsp+108h+var_B8], rax
0x180058076  test    rax, rax
0x180058079  jz      short loc_180058081
0x18005807b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058080  nop
0x180058081  jmp     loc_1800581C1; jumptable 0000000180057E80 cases -1,1
0x180058086  xor     esi, esi; jumptable 0000000180057E80 case 4
0x180058088  lea     rdx, [rdi+0D0h]
0x18005808f  lea     rcx, [rdi+0B0h]
0x180058096  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x18005809b  nop
0x18005809c  cmp     qword ptr [rdi+0B0h], 0
0x1800580a4  jz      short loc_1800580D1
0x1800580a6  mov     rbx, [rdi+0B0h]
0x1800580ad  mov     [rsp+108h+var_90], rbx
0x1800580b2  mov     rcx, rsi
0x1800580b5  xchg    rcx, [rbx]
0x1800580b8  cmp     rcx, 1
0x1800580bc  jnz     short loc_1800580D1
0x1800580be  xchg    ax, ax
0x1800580c0  call    _Thrd_yield
0x1800580c5  mov     rax, rsi
0x1800580c8  xchg    rax, [rbx]
0x1800580cb  cmp     rax, 1
0x1800580cf  jz      short loc_1800580C0
0x1800580d1  lea     rcx, [rdi+0A8h]
0x1800580d8  mov     rax, [rcx]
0x1800580db  mov     [rsp+108h+var_B8], rax
0x1800580e0  test    rax, rax
0x1800580e3  jz      short loc_1800580EA
0x1800580e5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800580ea  mov     ecx, 20h ; ' '; Size
0x1800580ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800580f4  mov     rcx, rax
0x1800580f7  lea     rbx, [rax+10h]
0x1800580fb  lea     rax, ??_7?$produce@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIQueryResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult,winrt::Microsoft::Windows::SemanticSearch::IQueryResult>::`vftable'
0x180058102  mov     [rbx], rax
0x180058105  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005810c  mov     qword ptr [rcx+8], 1
0x180058114  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x18005811b  mov     [rcx], rax
0x18005811e  mov     rax, [rdi+0D0h]
0x180058125  mov     [rdi+0D0h], rsi
0x18005812c  mov     [rcx+18h], rax
0x180058130  lea     rax, ??_7?$heap_implements@UQueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult>::`vftable'
0x180058137  mov     [rcx], rax
0x18005813a  test    rcx, rcx
0x18005813d  cmovz   rbx, rsi
0x180058141  lea     rcx, [rdi+0D8h]
0x180058148  mov     [rcx], rbx
0x18005814b  lea     r14, [rdi+78h]
0x18005814f  cmp     r14, rcx
0x180058152  jz      short loc_180058167
0x180058154  cmp     qword ptr [r14], 0
0x180058158  jz      short loc_180058162
0x18005815a  mov     rcx, r14
0x18005815d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058162  mov     [r14], rbx
0x180058165  jmp     short loc_180058172
0x180058167  test    rbx, rbx
0x18005816a  jz      short loc_180058172
0x18005816c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058171  nop
0x180058172  mov     rax, [rdi+0D0h]
0x180058179  mov     [rsp+108h+var_60], rax
0x180058181  test    rax, rax
0x180058184  jz      short loc_180058193
0x180058186  lea     rcx, [rdi+0D0h]
0x18005818d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180058192  nop
0x180058193  jmp     short loc_1800581A1
0x180058195  xor     esi, esi
0x180058197  mov     r15, [rsp+108h+var_B0]
0x18005819c  mov     rdi, [rsp+108h+var_C8]
0x1800581a1  lea     rax, [rdi+10h]
0x1800581a5  lea     rcx, [rdi+0E0h]
0x1800581ac  mov     [rcx], rax
0x1800581af  xor     eax, eax
0x1800581b1  mov     [r15], ax
0x1800581b5  mov     [rdi], rsi
0x1800581b8  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x1800581bd  test    al, al
0x1800581bf  jnz     short loc_1800581E4
0x1800581c1  lea     rcx, [rdi+10h]; jumptable 0000000180057E80 cases -1,1
0x1800581c5  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x1800581ca  cmp     word ptr [rdi+0A2h], 0
0x1800581d2  jz      short loc_1800581E4
0x1800581d4  mov     edx, 140h; unsigned __int64
0x1800581d9  mov     rcx, rdi; void *
0x1800581dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800581e1  jmp     short loc_1800581E4
0x1800581e3  int     3; Trap to Debugger
0x1800581e4  mov     rcx, [rsp+108h+var_38]
0x1800581ec  xor     rcx, rsp; StackCookie
0x1800581ef  call    __security_check_cookie
0x1800581f4  lea     r11, [rsp+108h+var_28]
0x1800581fc  mov     rbx, [r11+38h]
0x180058200  mov     rsi, [r11+40h]
0x180058204  mov     rsp, r11
0x180058207  pop     r15
0x180058209  pop     r14
0x18005820b  pop     r13
0x18005820d  pop     r12
0x18005820f  pop     rdi
0x180058210  retn
```
