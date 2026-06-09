# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectOneTrace(HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180029910`
- end: `0x180029b87`
- name: `?CollectOneTrace@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `631`
- prototype: `int(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, HSTRING, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000539c`
- `0x18000a5c4`
- `0x180017a88`
- `0x180017b70`
- `0x1800181cc`
- `0x18001823c`
- `0x1800183bc`
- `0x180018508`
- `0x180018738`
- `0x18001ac60`
- `0x18001d3c0`
- `0x180020e30`
- `0x180029874`
- `0x180029910`
- `0x18003a488`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x180029a9d`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x180029a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002999b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002999b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectOneTrace(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        HSTRING a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  _DWORD *v6; // rax
  HRESULT v7; // eax
  unsigned int v8; // edi
  HRESULT v9; // eax
  _DWORD *v10; // rax
  int CurrentUserToken; // eax
  __int64 v12; // rax
  __int64 v13; // r8
  __int128 v15; // [rsp+20h] [rbp-39h] BYREF
  HSTRING *newString[2]; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v17[2]; // [rsp+40h] [rbp-19h] BYREF
  char *v18; // [rsp+50h] [rbp-9h] BYREF
  std::_Ref_count_base *v19; // [rsp+58h] [rbp-1h]
  _BYTE v20[80]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_OWORD *)newString = 0;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
    newString,
    0);
  if ( !newString[0] )
  {
    v6 = operator new(0x18u);
    v6[2] = 1;
    v6[3] = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable';
    *((_QWORD *)v6 + 2) = 0;
    v18 = (char *)(v6 + 4);
    v19 = (std::_Ref_count_base *)v6;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
      newString,
      &v18);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  v7 = WindowsDuplicateString(a2, newString[0]);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v22 = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v22);
    EnrollmentLogging::CollectOneTrace();
    LOBYTE(v18) = 0;
    BYTE2(v18) = 0;
    v9 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)&v18);
    v8 = v9;
    if ( v9 >= 0 )
    {
      *(_OWORD *)v17 = 0;
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        v17,
        0);
      if ( !v17[0] )
      {
        v10 = operator new(0x18u);
        v10[2] = 1;
        v10[3] = 1;
        *(_QWORD *)v10 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
        *((_QWORD *)v10 + 2) = 0;
        *(_QWORD *)&v15 = v10 + 4;
        *((_QWORD *)&v15 + 1) = v10;
        std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
          v17,
          &v15);
        if ( *((_QWORD *)&v15 + 1) )
          std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v15 + 1));
      }
      CurrentUserToken = DmGetCurrentUserToken((void **)v17[0]);
      v8 = CurrentUserToken;
      if ( CurrentUserToken >= 0 )
      {
        AutoImpersonate::RevertToSelf((AutoImpersonate *)&v18);
        v12 = lambda_983e7096dbc2b690dc04e89e03f79965_::_lambda_983e7096dbc2b690dc04e89e03f79965_(
                v20,
                newString,
                &v22,
                v17);
        LODWORD(v15) = 3;
        *(_QWORD *)((char *)&v15 + 4) = 128;
        v8 = ((__int64 (__fastcall *)(__int128 *, struct Windows::Foundation::IAsyncAction **, __int64, __int64))Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_983e7096dbc2b690dc04e89e03f79965___)(
               &v15,
               a3,
               v13,
               v12);
        lambda_983e7096dbc2b690dc04e89e03f79965_::__lambda_983e7096dbc2b690dc04e89e03f79965_(v20);
        if ( v17[1] )
          std::_Ref_count_base::_Decref(v17[1]);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v18);
        if ( this )
          (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x845,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)CurrentUserToken,
          v15);
        if ( v17[1] )
          std::_Ref_count_base::_Decref(v17[1]);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v18);
        if ( this )
          (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x842,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v9,
        v15);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v18);
      if ( this )
        (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x839,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v7,
      v15);
  }
  if ( newString[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)newString[1]);
  return v8;
}

```

## disassembly

```asm
0x180029910  push    rbp
0x180029912  push    rbx
0x180029913  push    rsi
0x180029914  push    rdi
0x180029915  lea     rbp, [rsp-3Fh]
0x18002991a  sub     rsp, 98h
0x180029921  mov     rsi, r8
0x180029924  mov     rdi, rdx
0x180029927  mov     rbx, rcx
0x18002992a  xorps   xmm0, xmm0
0x18002992d  movdqu  xmmword ptr [rbp+57h+newString], xmm0
0x180029932  xor     edx, edx
0x180029934  lea     rcx, [rbp+57h+newString]
0x180029938  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18002993d  cmp     [rbp+57h+newString], 0
0x180029942  jnz     short loc_180029994
0x180029944  mov     ecx, 18h; Size
0x180029949  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002994e  mov     dword ptr [rax+8], 1
0x180029955  mov     dword ptr [rax+0Ch], 1
0x18002995c  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable'
0x180029963  mov     [rax], rcx
0x180029966  lea     rcx, [rax+10h]
0x18002996a  mov     qword ptr [rcx], 0
0x180029971  mov     [rbp+57h+var_60], rcx
0x180029975  mov     [rbp+57h+var_58], rax
0x180029979  lea     rdx, [rbp+57h+var_60]
0x18002997d  lea     rcx, [rbp+57h+newString]
0x180029981  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180029986  mov     rcx, [rbp+57h+var_58]; this
0x18002998a  test    rcx, rcx
0x18002998d  jz      short loc_180029994
0x18002998f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029994  mov     rdx, [rbp+57h+newString]; newString
0x180029998  mov     rcx, rdi; string
0x18002999b  call    cs:__imp_WindowsDuplicateString
0x1800299a2  nop     dword ptr [rax+rax+00h]
0x1800299a7  mov     edi, eax
0x1800299a9  test    eax, eax
0x1800299ab  jns     short loc_1800299CA
0x1800299ad  mov     rcx, [rbp+5Fh]; this
0x1800299b1  mov     r9d, eax; char *
0x1800299b4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800299bb  mov     edx, 839h; void *
0x1800299c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299c5  jmp     loc_180029B6A
0x1800299ca  mov     [rbp+57h+arg_18], rbx
0x1800299ce  lea     rcx, [rbp+57h+arg_18]
0x1800299d2  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800299d7  call    ?CollectOneTrace@EnrollmentLogging@@SAXXZ; EnrollmentLogging::CollectOneTrace(void)
0x1800299dc  mov     byte ptr [rbp+57h+var_60], 0
0x1800299e0  mov     byte ptr [rbp+57h+var_60+2], 0
0x1800299e4  lea     rcx, [rbp+57h+var_60]; this
0x1800299e8  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x1800299ed  mov     edi, eax
0x1800299ef  test    eax, eax
0x1800299f1  jns     short loc_180029A2F
0x1800299f3  mov     rcx, [rbp+5Fh]; this
0x1800299f7  mov     r9d, eax; char *
0x1800299fa  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029a01  mov     edx, 842h; void *
0x180029a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a0b  lea     rcx, [rbp+57h+var_60]; this
0x180029a0f  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180029a14  nop
0x180029a15  test    rbx, rbx
0x180029a18  jz      short loc_180029A2A
0x180029a1a  mov     rax, [rbx]
0x180029a1d  mov     rcx, rbx
0x180029a20  mov     rax, [rax+10h]
0x180029a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a29  nop
0x180029a2a  jmp     loc_180029B6A
0x180029a2f  xorps   xmm0, xmm0
0x180029a32  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180029a37  xor     edx, edx
0x180029a39  lea     rcx, [rbp+57h+var_70]
0x180029a3d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x180029a42  cmp     [rbp+57h+var_70], 0
0x180029a47  jnz     short loc_180029A99
0x180029a49  mov     ecx, 18h; Size
0x180029a4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029a53  mov     dword ptr [rax+8], 1
0x180029a5a  mov     dword ptr [rax+0Ch], 1
0x180029a61  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x180029a68  mov     [rax], rcx
0x180029a6b  lea     rcx, [rax+10h]
0x180029a6f  mov     qword ptr [rcx], 0
0x180029a76  mov     [rbp+57h+var_90], rcx
0x180029a7a  mov     [rbp+57h+var_88], rax
0x180029a7e  lea     rdx, [rbp+57h+var_90]
0x180029a82  lea     rcx, [rbp+57h+var_70]
0x180029a86  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180029a8b  mov     rcx, [rbp+57h+var_88]; this
0x180029a8f  test    rcx, rcx
0x180029a92  jz      short loc_180029A99
0x180029a94  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029a99  mov     rcx, [rbp+57h+var_70]
0x180029a9d  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x180029aa4  nop     dword ptr [rax+rax+00h]
0x180029aa9  mov     edi, eax
0x180029aab  test    eax, eax
0x180029aad  jns     short loc_180029AF6
0x180029aaf  mov     rcx, [rbp+5Fh]; this
0x180029ab3  mov     r9d, eax; char *
0x180029ab6  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029abd  mov     edx, 845h; void *
0x180029ac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ac7  mov     rcx, [rbp+57h+var_70+8]; this
0x180029acb  test    rcx, rcx
0x180029ace  jz      short loc_180029AD5
0x180029ad0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029ad5  lea     rcx, [rbp+57h+var_60]; this
0x180029ad9  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180029ade  nop
0x180029adf  test    rbx, rbx
0x180029ae2  jz      short loc_180029AF4
0x180029ae4  mov     rax, [rbx]
0x180029ae7  mov     rcx, rbx
0x180029aea  mov     rax, [rax+10h]
0x180029aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af3  nop
0x180029af4  jmp     short loc_180029B6A
0x180029af6  lea     rcx, [rbp+57h+var_60]; this
0x180029afa  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x180029aff  lea     r9, [rbp+57h+var_70]
0x180029b03  lea     r8, [rbp+57h+arg_18]
0x180029b07  lea     rdx, [rbp+57h+newString]
0x180029b0b  lea     rcx, [rbp+57h+var_50]
0x180029b0f  call    _lambda_983e7096dbc2b690dc04e89e03f79965____lambda_983e7096dbc2b690dc04e89e03f79965_
0x180029b14  mov     dword ptr [rbp+57h+var_90], 3
0x180029b1b  mov     [rbp+57h+var_90+4], 80h
0x180029b23  mov     r9, rax
0x180029b26  mov     rdx, rsi
0x180029b29  lea     rcx, [rbp+57h+var_90]
0x180029b2d  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_983e7096dbc2b690dc04e89e03f79965___
0x180029b32  mov     edi, eax
0x180029b34  lea     rcx, [rbp+57h+var_50]
0x180029b38  call    _lambda_983e7096dbc2b690dc04e89e03f79965_____lambda_983e7096dbc2b690dc04e89e03f79965_
0x180029b3d  mov     rcx, [rbp+57h+var_70+8]; this
0x180029b41  test    rcx, rcx
0x180029b44  jz      short loc_180029B4B
0x180029b46  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029b4b  lea     rcx, [rbp+57h+var_60]; this
0x180029b4f  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180029b54  nop
0x180029b55  test    rbx, rbx
0x180029b58  jz      short loc_180029B6A
0x180029b5a  mov     rax, [rbx]
0x180029b5d  mov     rcx, rbx
0x180029b60  mov     rax, [rax+10h]
0x180029b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b69  nop
0x180029b6a  mov     rcx, [rbp+57h+newString+8]; this
0x180029b6e  test    rcx, rcx
0x180029b71  jz      short loc_180029B78
0x180029b73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029b78  mov     eax, edi
0x180029b7a  add     rsp, 98h
0x180029b81  pop     rdi
0x180029b82  pop     rsi
0x180029b83  pop     rbx
0x180029b84  pop     rbp
0x180029b85  retn
```
