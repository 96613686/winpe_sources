# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectOneTrace(HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18002af80`
- end: `0x18002b1ea`
- name: `?CollectOneTrace@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this, HSTRING, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000523c`
- `0x18000a2a4`
- `0x180017284`
- `0x18001736c`
- `0x180018f88`
- `0x180018ff0`
- `0x1800199f8`
- `0x180019b4c`
- `0x180019f1c`
- `0x18001c798`
- `0x18001ee88`
- `0x1800227dc`
- `0x18002aee0`
- `0x18002af80`
- `0x18003b0f8`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002b107`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002b107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b00b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectOneTrace(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        HSTRING a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  _DWORD *v6; // rax
  HRESULT v7; // eax
  unsigned int v8; // edi
  int v9; // eax
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
0x18002af80  push    rbp
0x18002af82  push    rbx
0x18002af83  push    rsi
0x18002af84  push    rdi
0x18002af85  lea     rbp, [rsp-3Fh]
0x18002af8a  sub     rsp, 98h
0x18002af91  mov     rsi, r8
0x18002af94  mov     rdi, rdx
0x18002af97  mov     rbx, rcx
0x18002af9a  xorps   xmm0, xmm0
0x18002af9d  movdqu  xmmword ptr [rbp+57h+newString], xmm0
0x18002afa2  xor     edx, edx
0x18002afa4  lea     rcx, [rbp+57h+newString]
0x18002afa8  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18002afad  cmp     [rbp+57h+newString], 0
0x18002afb2  jnz     short loc_18002B004
0x18002afb4  mov     ecx, 18h; Size
0x18002afb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002afbe  mov     dword ptr [rax+8], 1
0x18002afc5  mov     dword ptr [rax+0Ch], 1
0x18002afcc  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable'
0x18002afd3  mov     [rax], rcx
0x18002afd6  lea     rcx, [rax+10h]
0x18002afda  mov     qword ptr [rcx], 0
0x18002afe1  mov     [rbp+57h+var_60], rcx
0x18002afe5  mov     [rbp+57h+var_58], rax
0x18002afe9  lea     rdx, [rbp+57h+var_60]
0x18002afed  lea     rcx, [rbp+57h+newString]
0x18002aff1  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002aff6  mov     rcx, [rbp+57h+var_58]; this
0x18002affa  test    rcx, rcx
0x18002affd  jz      short loc_18002B004
0x18002afff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b004  mov     rdx, [rbp+57h+newString]; newString
0x18002b008  mov     rcx, rdi; string
0x18002b00b  call    cs:__imp_WindowsDuplicateString
0x18002b011  mov     edi, eax
0x18002b013  test    eax, eax
0x18002b015  jns     short loc_18002B034
0x18002b017  mov     rcx, [rbp+5Fh]; this
0x18002b01b  mov     r9d, eax; char *
0x18002b01e  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002b025  mov     edx, 839h; void *
0x18002b02a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b02f  jmp     loc_18002B1CE
0x18002b034  mov     [rbp+57h+arg_18], rbx
0x18002b038  lea     rcx, [rbp+57h+arg_18]
0x18002b03c  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002b041  call    ?CollectOneTrace@EnrollmentLogging@@SAXXZ; EnrollmentLogging::CollectOneTrace(void)
0x18002b046  mov     byte ptr [rbp+57h+var_60], 0
0x18002b04a  mov     byte ptr [rbp+57h+var_60+2], 0
0x18002b04e  lea     rcx, [rbp+57h+var_60]; this
0x18002b052  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18002b057  mov     edi, eax
0x18002b059  test    eax, eax
0x18002b05b  jns     short loc_18002B099
0x18002b05d  mov     rcx, [rbp+5Fh]; this
0x18002b061  mov     r9d, eax; char *
0x18002b064  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002b06b  mov     edx, 842h; void *
0x18002b070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b075  lea     rcx, [rbp+57h+var_60]; this
0x18002b079  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002b07e  nop
0x18002b07f  test    rbx, rbx
0x18002b082  jz      short loc_18002B094
0x18002b084  mov     rax, [rbx]
0x18002b087  mov     rcx, rbx
0x18002b08a  mov     rax, [rax+10h]
0x18002b08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b093  nop
0x18002b094  jmp     loc_18002B1CE
0x18002b099  xorps   xmm0, xmm0
0x18002b09c  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18002b0a1  xor     edx, edx
0x18002b0a3  lea     rcx, [rbp+57h+var_70]
0x18002b0a7  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002b0ac  cmp     [rbp+57h+var_70], 0
0x18002b0b1  jnz     short loc_18002B103
0x18002b0b3  mov     ecx, 18h; Size
0x18002b0b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b0bd  mov     dword ptr [rax+8], 1
0x18002b0c4  mov     dword ptr [rax+0Ch], 1
0x18002b0cb  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x18002b0d2  mov     [rax], rcx
0x18002b0d5  lea     rcx, [rax+10h]
0x18002b0d9  mov     qword ptr [rcx], 0
0x18002b0e0  mov     [rbp+57h+var_90], rcx
0x18002b0e4  mov     [rbp+57h+var_88], rax
0x18002b0e8  lea     rdx, [rbp+57h+var_90]
0x18002b0ec  lea     rcx, [rbp+57h+var_70]
0x18002b0f0  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002b0f5  mov     rcx, [rbp+57h+var_88]; this
0x18002b0f9  test    rcx, rcx
0x18002b0fc  jz      short loc_18002B103
0x18002b0fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b103  mov     rcx, [rbp+57h+var_70]
0x18002b107  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x18002b10d  mov     edi, eax
0x18002b10f  test    eax, eax
0x18002b111  jns     short loc_18002B15A
0x18002b113  mov     rcx, [rbp+5Fh]; this
0x18002b117  mov     r9d, eax; char *
0x18002b11a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002b121  mov     edx, 845h; void *
0x18002b126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b12b  mov     rcx, [rbp+57h+var_70+8]; this
0x18002b12f  test    rcx, rcx
0x18002b132  jz      short loc_18002B139
0x18002b134  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b139  lea     rcx, [rbp+57h+var_60]; this
0x18002b13d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002b142  nop
0x18002b143  test    rbx, rbx
0x18002b146  jz      short loc_18002B158
0x18002b148  mov     rax, [rbx]
0x18002b14b  mov     rcx, rbx
0x18002b14e  mov     rax, [rax+10h]
0x18002b152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b157  nop
0x18002b158  jmp     short loc_18002B1CE
0x18002b15a  lea     rcx, [rbp+57h+var_60]; this
0x18002b15e  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18002b163  lea     r9, [rbp+57h+var_70]
0x18002b167  lea     r8, [rbp+57h+arg_18]
0x18002b16b  lea     rdx, [rbp+57h+newString]
0x18002b16f  lea     rcx, [rbp+57h+var_50]
0x18002b173  call    _lambda_983e7096dbc2b690dc04e89e03f79965____lambda_983e7096dbc2b690dc04e89e03f79965_
0x18002b178  mov     dword ptr [rbp+57h+var_90], 3
0x18002b17f  mov     [rbp+57h+var_90+4], 80h
0x18002b187  mov     r9, rax
0x18002b18a  mov     rdx, rsi
0x18002b18d  lea     rcx, [rbp+57h+var_90]
0x18002b191  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_983e7096dbc2b690dc04e89e03f79965___
0x18002b196  mov     edi, eax
0x18002b198  lea     rcx, [rbp+57h+var_50]
0x18002b19c  call    _lambda_983e7096dbc2b690dc04e89e03f79965_____lambda_983e7096dbc2b690dc04e89e03f79965_
0x18002b1a1  mov     rcx, [rbp+57h+var_70+8]; this
0x18002b1a5  test    rcx, rcx
0x18002b1a8  jz      short loc_18002B1AF
0x18002b1aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b1af  lea     rcx, [rbp+57h+var_60]; this
0x18002b1b3  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002b1b8  nop
0x18002b1b9  test    rbx, rbx
0x18002b1bc  jz      short loc_18002B1CE
0x18002b1be  mov     rax, [rbx]
0x18002b1c1  mov     rcx, rbx
0x18002b1c4  mov     rax, [rax+10h]
0x18002b1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1cd  nop
0x18002b1ce  mov     rcx, [rbp+57h+newString+8]; this
0x18002b1d2  test    rcx, rcx
0x18002b1d5  jz      short loc_18002B1DC
0x18002b1d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b1dc  mov     eax, edi
0x18002b1de  add     rsp, 98h
0x18002b1e5  pop     rdi
0x18002b1e6  pop     rsi
0x18002b1e7  pop     rbx
0x18002b1e8  pop     rbp
0x18002b1e9  retn
```
