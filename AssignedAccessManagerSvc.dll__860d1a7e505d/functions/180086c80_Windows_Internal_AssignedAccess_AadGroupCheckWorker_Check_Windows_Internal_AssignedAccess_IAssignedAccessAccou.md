# Windows::Internal::AssignedAccess::AadGroupCheckWorker::Check(Windows::Internal::AssignedAccess::IAssignedAccessAccount *,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,bool *)

- ea: `0x180086c80`
- end: `0x180086eed`
- name: `?Check@AadGroupCheckWorker@AssignedAccess@Internal@Windows@@UEAAJPEAUIAssignedAccessAccount@234@PEAUIAssignedAccessUserInfo@234@PEA_N@Z`
- size: `621`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AadGroupCheckWorker *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, bool *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x1800109e0`
- `0x180013eec`
- `0x180013fac`
- `0x18001f2b0`
- `0x1800271e4`
- `0x18002901c`
- `0x180086468`
- `0x1800864f0`
- `0x180086594`
- `0x180086c80`
- `0x180086f10`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086e83`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180086e05`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180086e05`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::AssignedAccess::AadGroupCheckWorker::Check(
        Windows::Internal::AssignedAccess::AadGroupCheckWorker *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *a2,
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *a3,
        bool *a4)
{
  int v6; // r14d
  __int64 (__fastcall *v7)(struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, HSTRING *); // rbx
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rbx
  int v17; // edi
  bool *v18; // rbx
  int v20[2]; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-B8h] BYREF
  bool *v25; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR v26; // [rsp+58h] [rbp-A8h] BYREF
  char v27; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v28[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = (int)this;
  v25 = a4;
  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "AADGroupCheckWorker_Check");
  v28[0] = &AssignedAccessTelemetry::AADGroupCheckWorker_Check::`vftable';
  AssignedAccessTelemetry::AADGroupCheckWorker_Check::StartActivity((AssignedAccessTelemetry::AADGroupCheckWorker_Check *)v28);
  v23 = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v23,
    0);
  v8 = v7(a2, &v23);
  v9 = v8;
  if ( v8 >= 0 )
  {
    string = 0;
    v10 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, HSTRING *))(*(_QWORD *)a3 + 48LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v11 = v10(a3, &string);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v22 = 0;
      v14 = _lambda_aea8160c3ad0287299557e903c448557_::_lambda_aea8160c3ad0287299557e903c448557_(
              (unsigned int)&v27,
              v6,
              (unsigned int)&v22,
              (unsigned int)&v23,
              (__int64)&string,
              (__int64)&v25);
      v15 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_19f6c0c811ebea76f38e14ac318d5e83_____lambda_19f6c0c811ebea76f38e14ac318d5e83___(
                         &StringRawBuffer,
                         v14);
      v16 = *v15;
      *v15 = 0;
      if ( StringRawBuffer )
      {
        StringRawBuffer = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release();
      }
      *(_QWORD *)v20 = v16;
      v17 = SHTaskPoolQueueTask(0, 32, 0);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadgroupcheckworker.cpp",
          (const char *)(unsigned int)v17,
          v16);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        v9 = v17;
        goto LABEL_15;
      }
      v9 = v22;
      if ( v22 >= 0 )
      {
        v18 = v25;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v26 = WindowsGetStringRawBuffer(v23, 0);
        AssignedAccessTelemetry::AADGroupCheckWorker_Check::IsUserMemberOfGroup<unsigned short const *,unsigned short const *,bool &>(
          v28,
          &v26,
          &StringRawBuffer,
          v18,
          *(_QWORD *)v20,
          0);
        wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v28);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        v9 = 0;
        goto LABEL_15;
      }
      v12 = (unsigned int)v22;
      v13 = 51;
    }
    else
    {
      v12 = (unsigned int)v11;
      v13 = 39;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadgroupcheckworker.cpp",
      (const char *)v12,
      v20[0]);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadgroupcheckworker.cpp",
      (const char *)(unsigned int)v8,
      v20[0]);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v23);
  AssignedAccessTelemetry::AADGroupCheckWorker_Check::~AADGroupCheckWorker_Check((AssignedAccessTelemetry::AADGroupCheckWorker_Check *)v28);
  return v9;
}

```

## disassembly

```asm
0x180086c80  push    rbp
0x180086c82  push    rbx
0x180086c83  push    rsi
0x180086c84  push    rdi
0x180086c85  push    r14
0x180086c87  lea     rbp, [rsp-0F0h]
0x180086c8f  sub     rsp, 1F0h
0x180086c96  mov     rax, cs:__security_cookie
0x180086c9d  xor     rax, rsp
0x180086ca0  mov     [rbp+110h+var_30], rax
0x180086ca7  mov     rsi, r8
0x180086caa  mov     rdi, rdx
0x180086cad  mov     r14, rcx
0x180086cb0  mov     [rsp+210h+var_1C0], r9
0x180086cb5  lea     rdx, aAadgroupcheckw_0; "AADGroupCheckWorker_Check"
0x180086cbc  lea     rcx, [rbp+110h+var_180]
0x180086cc0  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180086cc5  lea     rax, ??_7AADGroupCheckWorker_Check@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AADGroupCheckWorker_Check::`vftable'
0x180086ccc  mov     [rbp+110h+var_180], rax
0x180086cd0  lea     rcx, [rbp+110h+var_180]; this
0x180086cd4  call    ?StartActivity@AADGroupCheckWorker_Check@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::AADGroupCheckWorker_Check::StartActivity(void)
0x180086cd9  nop
0x180086cda  mov     [rsp+210h+var_1D0], 0
0x180086ce3  mov     rax, [rdi]
0x180086ce6  mov     rbx, [rax+30h]
0x180086cea  xor     edx, edx
0x180086cec  lea     rcx, [rsp+210h+var_1D0]
0x180086cf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180086cf6  lea     rdx, [rsp+210h+var_1D0]
0x180086cfb  mov     rcx, rdi
0x180086cfe  mov     rax, rbx
0x180086d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d06  mov     ebx, eax
0x180086d08  test    eax, eax
0x180086d0a  jns     short loc_180086D2C
0x180086d0c  mov     rcx, [rbp+118h]; this
0x180086d13  mov     r9d, eax; char *
0x180086d16  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180086d1d  mov     edx, 25h ; '%'; void *
0x180086d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086d27  jmp     loc_180086EBA
0x180086d2c  mov     [rsp+210h+string], 0
0x180086d35  mov     rax, [rsi]
0x180086d38  mov     rbx, [rax+30h]
0x180086d3c  xor     edx, edx
0x180086d3e  lea     rcx, [rsp+210h+string]
0x180086d43  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180086d48  lea     rdx, [rsp+210h+string]
0x180086d4d  mov     rcx, rsi
0x180086d50  mov     rax, rbx
0x180086d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d58  mov     ebx, eax
0x180086d5a  test    eax, eax
0x180086d5c  jns     short loc_180086D89
0x180086d5e  mov     r9d, eax; char *
0x180086d61  mov     edx, 27h ; '''; void *
0x180086d66  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180086d6d  mov     rcx, [rbp+118h]; this
0x180086d74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086d79  nop
0x180086d7a  lea     rcx, [rsp+210h+string]
0x180086d7f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180086d84  jmp     loc_180086EBA
0x180086d89  mov     [rsp+210h+var_1D8], 0
0x180086d91  lea     rax, [rsp+210h+var_1C0]
0x180086d96  mov     [rsp+210h+var_1E8], rax
0x180086d9b  lea     rax, [rsp+210h+string]
0x180086da0  mov     qword ptr [rsp+210h+var_1F0], rax
0x180086da5  lea     r9, [rsp+210h+var_1D0]
0x180086daa  lea     r8, [rsp+210h+var_1D8]
0x180086daf  mov     rdx, r14
0x180086db2  lea     rcx, [rsp+210h+var_1B0]
0x180086db7  call    ??0_lambda_aea8160c3ad0287299557e903c448557_@@QEAA@PEAV?$SimpleVectorIterator@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@V?$Vector@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3674@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAPEAUIAssignedAccessProfile@AssignedAccess@25@AEAPEAIAEAV_lambda_5f721b843dc364e73b248e28e561c680_@@@Z; _lambda_aea8160c3ad0287299557e903c448557_::_lambda_aea8160c3ad0287299557e903c448557_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,XWinRT::IntVersionTag,1> *,uint &,Windows::Internal::AssignedAccess::IAssignedAccessProfile * * &,uint * &,_lambda_5f721b843dc364e73b248e28e561c680_ &)
0x180086dbc  mov     rdx, rax
0x180086dbf  lea     rcx, [rsp+210h+var_1C8]
0x180086dc4  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_19f6c0c811ebea76f38e14ac318d5e83_____lambda_19f6c0c811ebea76f38e14ac318d5e83___
0x180086dc9  mov     rbx, [rax]
0x180086dcc  mov     qword ptr [rax], 0
0x180086dd3  mov     rcx, [rsp+210h+var_1C8]
0x180086dd8  test    rcx, rcx
0x180086ddb  jz      short loc_180086DEB
0x180086ddd  mov     [rsp+210h+var_1C8], 0
0x180086de6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release(void)
0x180086deb  mov     [rsp+210h+var_1E8], 0
0x180086df4  mov     qword ptr [rsp+210h+var_1F0], rbx; int
0x180086df9  xor     r9d, r9d
0x180086dfc  xor     r8d, r8d
0x180086dff  lea     edx, [r9+20h]
0x180086e03  xor     ecx, ecx
0x180086e05  call    cs:__imp_SHTaskPoolQueueTask
0x180086e0b  mov     edi, eax
0x180086e0d  test    rbx, rbx
0x180086e10  jz      short loc_180086E22
0x180086e12  mov     rdx, [rbx]
0x180086e15  mov     rcx, rbx
0x180086e18  mov     rax, [rdx+10h]
0x180086e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e21  nop
0x180086e22  test    edi, edi
0x180086e24  jns     short loc_180086E50
0x180086e26  mov     rcx, [rbp+118h]; this
0x180086e2d  mov     r9d, edi; char *
0x180086e30  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180086e37  mov     edx, 32h ; '2'; void *
0x180086e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086e41  nop
0x180086e42  lea     rcx, [rsp+210h+string]
0x180086e47  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180086e4c  mov     ebx, edi
0x180086e4e  jmp     short loc_180086EBA
0x180086e50  mov     ebx, [rsp+210h+var_1D8]
0x180086e54  test    ebx, ebx
0x180086e56  jns     short loc_180086E65
0x180086e58  mov     r9d, ebx
0x180086e5b  mov     edx, 33h ; '3'
0x180086e60  jmp     loc_180086D66
0x180086e65  mov     rbx, [rsp+210h+var_1C0]
0x180086e6a  xor     edx, edx; length
0x180086e6c  mov     rcx, [rsp+210h+string]; string
0x180086e71  call    cs:__imp_WindowsGetStringRawBuffer
0x180086e77  mov     [rsp+210h+var_1C8], rax
0x180086e7c  xor     edx, edx; length
0x180086e7e  mov     rcx, [rsp+210h+var_1D0]; string
0x180086e83  call    cs:__imp_WindowsGetStringRawBuffer
0x180086e89  mov     [rsp+210h+var_1B8], rax
0x180086e8e  mov     r9, rbx
0x180086e91  lea     r8, [rsp+210h+var_1C8]
0x180086e96  lea     rdx, [rsp+210h+var_1B8]
0x180086e9b  lea     rcx, [rbp+110h+var_180]
0x180086e9f  call    ??$IsUserMemberOfGroup@PEBGPEBGAEA_N@AADGroupCheckWorker_Check@AssignedAccessTelemetry@@QEAAX$$QEAPEBG0AEA_N@Z; AssignedAccessTelemetry::AADGroupCheckWorker_Check::IsUserMemberOfGroup<ushort const *,ushort const *,bool &>(ushort const * &&,ushort const * &&,bool &)
0x180086ea4  lea     rcx, [rbp+110h+var_180]
0x180086ea8  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180086ead  nop
0x180086eae  lea     rcx, [rsp+210h+string]
0x180086eb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180086eb8  xor     ebx, ebx
0x180086eba  lea     rcx, [rsp+210h+var_1D0]
0x180086ebf  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180086ec4  nop
0x180086ec5  lea     rcx, [rbp+110h+var_180]; this
0x180086ec9  call    ??1AADGroupCheckWorker_Check@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AADGroupCheckWorker_Check::~AADGroupCheckWorker_Check(void)
0x180086ece  mov     eax, ebx
0x180086ed0  mov     rcx, [rbp+110h+var_30]
0x180086ed7  xor     rcx, rsp; StackCookie
0x180086eda  call    __security_check_cookie
0x180086edf  add     rsp, 1F0h
0x180086ee6  pop     r14
0x180086ee8  pop     rdi
0x180086ee9  pop     rsi
0x180086eea  pop     rbx
0x180086eeb  pop     rbp
0x180086eec  retn
```
