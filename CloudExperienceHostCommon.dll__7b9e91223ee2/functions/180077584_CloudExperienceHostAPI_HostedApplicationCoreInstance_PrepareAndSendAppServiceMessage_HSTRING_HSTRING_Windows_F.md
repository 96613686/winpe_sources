# CloudExperienceHostAPI::HostedApplicationCoreInstance::PrepareAndSendAppServiceMessage(HSTRING__ *,HSTRING__ *,Windows::Foundation::Rect)

- ea: `0x180077584`
- end: `0x18007782f`
- name: `?PrepareAndSendAppServiceMessage@HostedApplicationCoreInstance@CloudExperienceHostAPI@@AEAAXPEAUHSTRING__@@0URect@Foundation@Windows@@@Z`
- size: `683`
- prototype: `void __high(HSTRING, HSTRING, struct Windows::Foundation::Rect)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180079bd0`

## callees

- `0x180005174`
- `0x180010500`
- `0x180010810`
- `0x180010c8c`
- `0x1800169cc`
- `0x18001a540`
- `0x18005f960`
- `0x18007387c`
- `0x1800739b8`
- `0x180077584`
- `0x180079194`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180077656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180077656`

## string_xrefs

- `0x18007774a`: `AppServiceResponseStatus: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CloudExperienceHostAPI::HostedApplicationCoreInstance::PrepareAndSendAppServiceMessage(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        __int128 *a4)
{
  char v8; // r8
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  char v11; // r8
  HSTRING_HEADER *v12; // rax
  int v13; // eax
  char v14; // r8
  wchar_t **v15; // rdx
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-79h]
  char *v26; // [rsp+30h] [rbp-69h]
  INT32 result; // [rsp+40h] [rbp-59h] BYREF
  _DWORD v28[3]; // [rsp+44h] [rbp-55h] BYREF
  __int64 v29; // [rsp+50h] [rbp-49h] BYREF
  __int64 v30; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v32; // [rsp+70h] [rbp-29h]
  HSTRING string2[4]; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER v34; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  wil::ActivateInstance<Windows::Foundation::Collections::IPropertySet>((__int64)v31, (__int64)a2, a3);
  v29 = v31[0];
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 8LL))(v31[0]);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         (HSTRING_HEADER *)string2,
         (const WCHAR **)off_1800F5140,
         v8);
  v10 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v29,
          (HSTRING)v9[1].Reserved.Reserved1);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v10,
      v25);
  if ( a3 )
  {
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            (HSTRING_HEADER *)string2,
            (const WCHAR **)off_1800F5130,
            v11);
    v13 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v29,
            (HSTRING)v12[1].Reserved.Reserved1);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
        (const char *)(unsigned int)v13,
        v25);
  }
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)string2,
    L"UpdatePosition");
  result = 0;
  WindowsCompareStringOrdinal(a2, string2[0], &result);
  v15 = off_1800F5128;
  if ( result )
    v15 = off_1800F5138;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, (const WCHAR **)v15, v14);
  v32 = *a4;
  v17 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<Windows::Foundation::Rect>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v29,
          (HSTRING)v16[1].Reserved.Reserved1);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v17,
      v25);
  *(_QWORD *)&v28[1] = 0;
  v18 = *(__int64 **)(a1 + 128);
  v19 = *v18;
  *(_QWORD *)&v28[1] = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _DWORD *))(v19 + 88))(v18, v31[0], &v28[1]);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v20,
      v25);
  v30 = 0;
  v21 = *(_QWORD *)&v28[1];
  v22 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(*(_QWORD *)&v28[1]);
  if ( v22 >= 0 )
    v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, &v30);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v22,
      v25);
  v28[0] = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v30 + 56LL))(v30, v28);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v23,
      v25);
  LODWORD(v26) = v28[0];
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
    (const char *)0x8007065BLL,
    v28[0] == 0,
    (bool)"AppServiceResponseStatus: %d",
    v26);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v30);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v28[1]);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(v31);
}

```

## disassembly

```asm
0x180077584  push    rbp
0x180077586  push    rbx
0x180077587  push    rsi
0x180077588  push    rdi
0x180077589  push    r14
0x18007758b  lea     rbp, [rsp-37h]
0x180077590  sub     rsp, 0D0h
0x180077597  mov     rax, cs:__security_cookie
0x18007759e  xor     rax, rsp
0x1800775a1  mov     [rbp+57h+var_30], rax
0x1800775a5  mov     r14, r9
0x1800775a8  mov     rbx, r8
0x1800775ab  mov     rdi, rdx
0x1800775ae  mov     rsi, rcx
0x1800775b1  lea     rcx, [rbp+57h+var_90]
0x1800775b5  call    ??$ActivateInstance@UIPropertySet@Collections@Foundation@Windows@@@wil@@YA?AV?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Foundation::Collections::IPropertySet>(ushort const *)
0x1800775ba  nop
0x1800775bb  mov     rcx, [rbp+57h+var_90]
0x1800775bf  mov     [rbp+57h+var_A0], rcx
0x1800775c3  test    rcx, rcx
0x1800775c6  jz      short loc_1800775D5
0x1800775c8  mov     rax, [rcx]
0x1800775cb  mov     rax, [rax+8]
0x1800775cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775d4  nop
0x1800775d5  lea     rdx, off_1800F5140; "MessageType"
0x1800775dc  lea     rcx, [rbp+57h+string2]
0x1800775e0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800775e5  nop
0x1800775e6  mov     r9, rdi
0x1800775e9  mov     rdx, [rax+18h]; HSTRING
0x1800775ed  lea     rcx, [rbp+57h+var_A0]; this
0x1800775f1  call    ??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)
0x1800775f6  mov     rcx, [rbp+5Fh]; this
0x1800775fa  test    eax, eax
0x1800775fc  js      loc_1800777C6
0x180077602  test    rbx, rbx
0x180077605  jz      short loc_180077634
0x180077607  lea     rdx, off_1800F5130; "aumid"
0x18007760e  lea     rcx, [rbp+57h+string2]
0x180077612  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180077617  nop
0x180077618  mov     r9, rbx
0x18007761b  mov     rdx, [rax+18h]; HSTRING
0x18007761f  lea     rcx, [rbp+57h+var_A0]; this
0x180077623  call    ??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)
0x180077628  mov     rcx, [rbp+5Fh]; this
0x18007762c  test    eax, eax
0x18007762e  js      loc_1800777DB
0x180077634  mov     rdx, cs:off_1800F5158; unsigned __int16 *
0x18007763b  lea     rcx, [rbp+57h+string2]; this
0x18007763f  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180077644  mov     [rbp+57h+result], 0
0x18007764b  lea     r8, [rbp+57h+result]; result
0x18007764f  mov     rdx, [rbp+57h+string2]; string2
0x180077653  mov     rcx, rdi; string1
0x180077656  call    cs:__imp_WindowsCompareStringOrdinal
0x18007765c  lea     rdx, off_1800F5128; "appRect"
0x180077663  lea     rax, off_1800F5138; "modalRect"
0x18007766a  cmp     [rbp+57h+result], 0
0x18007766e  cmovnz  rdx, rax
0x180077672  lea     rcx, [rbp+57h+var_50]
0x180077676  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007767b  nop
0x18007767c  movaps  xmm0, xmmword ptr [r14]
0x180077680  movdqu  [rbp+57h+var_80], xmm0
0x180077685  lea     r9, [rbp+57h+var_80]
0x180077689  mov     rdx, [rax+18h]; HSTRING
0x18007768d  lea     rcx, [rbp+57h+var_A0]; this
0x180077691  call    ??$SetValue@URect@Foundation@Windows@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJURect@63@PEAPEAUIInspectable@@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<Windows::Foundation::Rect>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(Windows::Foundation::Rect,IInspectable * *),Windows::Foundation::Rect)
0x180077696  mov     rcx, [rbp+5Fh]; this
0x18007769a  test    eax, eax
0x18007769c  js      loc_1800777F0
0x1800776a2  mov     qword ptr [rbp+57h+var_AC+4], 0
0x1800776aa  mov     rcx, [rsi+80h]
0x1800776b1  mov     rax, [rcx]
0x1800776b4  mov     qword ptr [rbp+57h+var_AC+4], 0
0x1800776bc  lea     r8, [rbp+57h+var_AC+4]
0x1800776c0  mov     rdx, [rbp+57h+var_90]
0x1800776c4  mov     rax, [rax+58h]
0x1800776c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776cd  mov     rcx, [rbp+5Fh]; this
0x1800776d1  test    eax, eax
0x1800776d3  js      loc_180077805
0x1800776d9  mov     [rbp+57h+var_98], 0
0x1800776e1  mov     rbx, qword ptr [rbp+57h+var_AC+4]
0x1800776e5  mov     rcx, rbx
0x1800776e8  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)
0x1800776ed  test    eax, eax
0x1800776ef  js      short loc_180077704
0x1800776f1  mov     rax, [rbx]
0x1800776f4  lea     rdx, [rbp+57h+var_98]
0x1800776f8  mov     rcx, rbx
0x1800776fb  mov     rax, [rax+40h]
0x1800776ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077704  mov     rcx, [rbp+5Fh]; this
0x180077708  test    eax, eax
0x18007770a  js      loc_18007781A
0x180077710  mov     dword ptr [rbp+57h+var_AC], 0
0x180077717  mov     rcx, [rbp+57h+var_98]
0x18007771b  mov     rax, [rcx]
0x18007771e  lea     rdx, [rbp+57h+var_AC]
0x180077722  mov     rax, [rax+38h]
0x180077726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007772b  mov     rcx, [rbp+5Fh]; this
0x18007772f  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180077736  test    eax, eax
0x180077738  js      short loc_1800777B8
0x18007773a  mov     eax, dword ptr [rbp+57h+var_AC]
0x18007773d  test    eax, eax
0x18007773f  setz    dl
0x180077742  mov     rcx, [rbp+5Fh]; this
0x180077746  mov     dword ptr [rsp+0F0h+var_C0], eax; char *
0x18007774a  lea     rax, aAppserviceresp; "AppServiceResponseStatus: %d"
0x180077751  mov     qword ptr [rsp+0F0h+var_C8], rax; bool
0x180077756  mov     [rsp+0F0h+var_D0], dl; char
0x18007775a  mov     r9d, 8007065Bh; char *
0x180077760  mov     edx, 9Dh; void *
0x180077765  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18007776a  nop
0x18007776b  lea     rcx, [rbp+57h+var_98]
0x18007776f  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180077774  nop
0x180077775  lea     rcx, [rbp+57h+var_AC+4]
0x180077779  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18007777e  nop
0x18007777f  mov     rcx, [rbp+57h+var_A0]
0x180077783  test    rcx, rcx
0x180077786  jz      short loc_180077795
0x180077788  mov     rax, [rcx]
0x18007778b  mov     rax, [rax+10h]
0x18007778f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077794  nop
0x180077795  lea     rcx, [rbp+57h+var_90]
0x180077799  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18007779e  mov     rcx, [rbp+57h+var_30]
0x1800777a2  xor     rcx, rsp; StackCookie
0x1800777a5  call    __security_check_cookie
0x1800777aa  add     rsp, 0D0h
0x1800777b1  pop     r14
0x1800777b3  pop     rdi
0x1800777b4  pop     rsi
0x1800777b5  pop     rbx
0x1800777b6  pop     rbp
0x1800777b7  retn
0x1800777b8  mov     r9d, eax; char *
0x1800777bb  mov     edx, 9Bh; void *
0x1800777c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800777c6  mov     r9d, eax; char *
0x1800777c9  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800777d0  mov     edx, 8Dh; void *
0x1800777d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800777db  mov     r9d, eax; char *
0x1800777de  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800777e5  mov     edx, 90h; void *
0x1800777ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800777f0  mov     r9d, eax; char *
0x1800777f3  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800777fa  mov     edx, 94h; void *
0x1800777ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180077805  mov     r9d, eax; char *
0x180077808  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x18007780f  mov     edx, 97h; void *
0x180077814  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007781a  mov     r9d, eax; char *
0x18007781d  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180077824  mov     edx, 99h; void *
0x180077829  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
