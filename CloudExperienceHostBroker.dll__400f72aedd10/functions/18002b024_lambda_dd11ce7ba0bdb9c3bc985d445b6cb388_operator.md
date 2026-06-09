# _lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_::operator()

- ea: `0x18002b024`
- end: `0x18002b2f9`
- name: `_lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_::operator()`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e9f0`

## callees

- `0x180004760`
- `0x1800059e0`
- `0x180005b30`
- `0x180006140`
- `0x1800065e4`
- `0x180007608`
- `0x180007df0`
- `0x180009f30`
- `0x18000c8a4`
- `0x18000cb20`
- `0x1800163c0`
- `0x180018be8`
- `0x18001fa54`
- `0x18002b024`
- `0x180038010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002b0a1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002b0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1de`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1de`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18002b148`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18002b148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b27d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b27d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b07c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b0d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b0d5`

## string_xrefs

- `0x18002b0ea`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002b15d`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002b199`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_::operator()(const struct _GUID *a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // r8d
  PCWSTR StringRawBuffer; // rax
  HRESULT v7; // eax
  __int64 v8; // rax
  int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  HRESULT v12; // eax
  void *v13; // rdi
  __int64 (__fastcall *v14)(void *, wchar_t *, BSTR *); // rsi
  OLECHAR *v15; // rbx
  int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  const WCHAR *v19; // rdi
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  HSTRING v22; // rdi
  HSTRING *v23; // rbx
  unsigned int v24; // r8d
  const char *v25; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-78h]
  IUnknown *pUnk; // [rsp+30h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-60h] BYREF
  LPVOID v30; // [rsp+40h] [rbp-58h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-50h] BYREF
  void *v32; // [rsp+50h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-40h] BYREF
  HSTRING string; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v32 = 0;
    v4 = CloudExperienceHostCreateOOBEUserObjectForceBroker(a1, &GUID_426317b8_c7d2_4647_ad76_2554806561b6, &v32);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x7B, v5, (const char *)(unsigned int)v4, ppv);
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&a1->Data1, 0);
    wil::make_bstr(&Str, StringRawBuffer);
    bstrString = 0;
    if ( !wcsstr(Str, L"\"function\":\"launchsharedialog\"") )
      goto LABEL_15;
    v30 = 0;
    v7 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v30);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
        (const char *)(unsigned int)v7,
        ppv);
LABEL_14:
      wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v30);
LABEL_15:
      v13 = v32;
      v14 = *(__int64 (__fastcall **)(void *, wchar_t *, BSTR *))(*(_QWORD *)v32 + 112LL);
      v15 = bstrString;
      if ( bstrString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v30);
        SysFreeString(v15);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v30);
      }
      bstrString = 0;
      v16 = v14(v13, Str, &bstrString);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x94, v18, (const char *)(unsigned int)v16, ppv);
      string = 0;
      v19 = bstrString;
      v20 = -1;
      do
        ++v20;
      while ( bstrString[v20] );
      if ( v20 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v17, v18);
        JUMPOUT(0x18002B2F7LL);
      }
      v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v19, v21, v20);
      v22 = string;
      v23 = (HSTRING *)(a2 + 16);
      if ( !string || string != *v23 )
      {
        WindowsDeleteString(*v23);
        *v23 = 0;
        WindowsDuplicateString(v22, (HSTRING *)(a2 + 16));
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v32);
      return 0;
    }
    pUnk = 0;
    v8 = *(_QWORD *)v30;
    pUnk = 0;
    v9 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, IUnknown **))(v8 + 24))(
           v30,
           &IID_IImmersiveApplicationManager,
           &GUID_bf63999f_7411_40da_861c_df72c0ffee84,
           &pUnk);
    v10 = retaddr;
    if ( v9 >= 0 )
    {
      v12 = CoAllowSetForegroundWindow(pUnk, 0);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
          (const char *)(unsigned int)v12,
          ppv);
      v9 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64))pUnk->lpVtbl[4].QueryInterface)(pUnk, 0, 32);
      v10 = retaddr;
      if ( v9 >= 0 )
        goto LABEL_13;
      v11 = 143;
    }
    else
    {
      v11 = 139;
    }
    wil::details::in1diag3::_Log_Hr(
      v10,
      (void *)v11,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_13:
    wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&pUnk);
    goto LABEL_14;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x97, v24, v25);
  }
  return result;
}

```

## disassembly

```asm
0x18002b024  mov     r11, rsp
0x18002b027  mov     [r11+18h], rbx
0x18002b02b  mov     [r11+20h], rsi
0x18002b02f  push    rdi
0x18002b030  push    r14
0x18002b032  push    r15
0x18002b034  sub     rsp, 80h
0x18002b03b  mov     rax, cs:__security_cookie
0x18002b042  xor     rax, rsp
0x18002b045  mov     [rsp+98h+var_20], rax
0x18002b04a  mov     r14, rdx
0x18002b04d  mov     rbx, rcx
0x18002b050  xor     r15d, r15d
0x18002b053  mov     [r11-48h], r15
0x18002b057  lea     r8, [r11-48h]; void **
0x18002b05b  lea     rdx, _GUID_426317b8_c7d2_4647_ad76_2554806561b6; struct _GUID *
0x18002b062  call    ?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18002b067  mov     rcx, [rsp+98h]; this
0x18002b06f  test    eax, eax
0x18002b071  js      loc_18002B2D3
0x18002b077  xor     edx, edx; length
0x18002b079  mov     rcx, [rbx]; string
0x18002b07c  call    cs:__imp_WindowsGetStringRawBuffer
0x18002b082  mov     rdx, rax
0x18002b085  lea     rcx, [rsp+98h+Str]
0x18002b08a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002b08f  nop
0x18002b090  mov     [rsp+98h+bstrString], r15
0x18002b095  lea     rdx, aFunctionLaunch; "\"function\":\"launchsharedialog\""
0x18002b09c  mov     rcx, [rsp+98h+Str]; Str
0x18002b0a1  call    cs:__imp_wcsstr
0x18002b0a7  test    rax, rax
0x18002b0aa  jz      loc_18002B1BB
0x18002b0b0  mov     [rsp+98h+var_58], r15
0x18002b0b5  lea     rax, [rsp+98h+var_58]
0x18002b0ba  mov     qword ptr [rsp+98h+ppv], rax; int
0x18002b0bf  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18002b0c6  xor     edx, edx; pUnkOuter
0x18002b0c8  mov     r8d, 404h; dwClsContext
0x18002b0ce  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18002b0d5  call    cs:__imp_CoCreateInstance
0x18002b0db  mov     rcx, [rsp+98h]; this
0x18002b0e3  test    eax, eax
0x18002b0e5  jns     short loc_18002B100
0x18002b0e7  mov     r9d, eax; char *
0x18002b0ea  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002b0f1  mov     edx, 88h; void *
0x18002b0f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b0fb  jmp     loc_18002B1B1
0x18002b100  mov     [rsp+98h+pUnk], r15
0x18002b105  mov     rcx, [rsp+98h+var_58]
0x18002b10a  mov     rax, [rcx]
0x18002b10d  mov     [rsp+98h+pUnk], r15
0x18002b112  lea     r9, [rsp+98h+pUnk]
0x18002b117  lea     r8, _GUID_bf63999f_7411_40da_861c_df72c0ffee84
0x18002b11e  lea     rdx, IID_IImmersiveApplicationManager
0x18002b125  mov     rax, [rax+18h]
0x18002b129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b12e  mov     rcx, [rsp+98h]
0x18002b136  test    eax, eax
0x18002b138  jns     short loc_18002B141
0x18002b13a  mov     edx, 8Bh
0x18002b13f  jmp     short loc_18002B196
0x18002b141  xor     edx, edx; lpvReserved
0x18002b143  mov     rcx, [rsp+98h+pUnk]; pUnk
0x18002b148  call    cs:__imp_CoAllowSetForegroundWindow
0x18002b14e  mov     rcx, [rsp+98h]; this
0x18002b156  test    eax, eax
0x18002b158  jns     short loc_18002B16E
0x18002b15a  mov     r9d, eax; char *
0x18002b15d  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002b164  mov     edx, 8Eh; void *
0x18002b169  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b16e  mov     rcx, [rsp+98h+pUnk]
0x18002b173  mov     rax, [rcx]
0x18002b176  xor     edx, edx
0x18002b178  lea     r8d, [rdx+20h]
0x18002b17c  mov     rax, [rax+60h]
0x18002b180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b185  mov     rcx, [rsp+98h]; this
0x18002b18d  test    eax, eax
0x18002b18f  jns     short loc_18002B1A6
0x18002b191  mov     edx, 8Fh; void *
0x18002b196  mov     r9d, eax; char *
0x18002b199  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002b1a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b1a5  nop
0x18002b1a6  lea     rcx, [rsp+98h+pUnk]
0x18002b1ab  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002b1b0  nop
0x18002b1b1  lea     rcx, [rsp+98h+var_58]
0x18002b1b6  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002b1bb  mov     rdi, [rsp+98h+var_48]
0x18002b1c0  mov     rax, [rdi]
0x18002b1c3  mov     rsi, [rax+70h]
0x18002b1c7  mov     rbx, [rsp+98h+bstrString]
0x18002b1cc  test    rbx, rbx
0x18002b1cf  jz      short loc_18002B1EE
0x18002b1d1  lea     rcx, [rsp+98h+var_58]; this
0x18002b1d6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b1db  mov     rcx, rbx; bstrString
0x18002b1de  call    cs:__imp_SysFreeString
0x18002b1e4  lea     rcx, [rsp+98h+var_58]; this
0x18002b1e9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b1ee  mov     [rsp+98h+bstrString], r15
0x18002b1f3  lea     r8, [rsp+98h+bstrString]
0x18002b1f8  mov     rdx, [rsp+98h+Str]
0x18002b1fd  mov     rcx, rdi
0x18002b200  mov     rax, rsi
0x18002b203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b208  mov     rcx, [rsp+98h]; this
0x18002b210  test    eax, eax
0x18002b212  js      loc_18002B2E0
0x18002b218  mov     [rsp+98h+string], r15
0x18002b21d  mov     rdi, [rsp+98h+bstrString]
0x18002b222  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b226  inc     rbx
0x18002b229  cmp     [rdi+rbx*2], r15w
0x18002b22e  jnz     short loc_18002B226
0x18002b230  mov     eax, 0FFFFFFFFh
0x18002b235  cmp     rbx, rax
0x18002b238  ja      loc_18002B2ED
0x18002b23e  mov     ecx, ebx; unsigned int
0x18002b240  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002b245  mov     r9d, ebx; unsigned int
0x18002b248  mov     r8d, eax; unsigned int
0x18002b24b  mov     rdx, rdi; sourceString
0x18002b24e  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x18002b253  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b258  mov     rdi, [rsp+98h+string]
0x18002b25d  lea     rbx, [r14+10h]
0x18002b261  test    rdi, rdi
0x18002b264  jz      short loc_18002B26B
0x18002b266  cmp     rdi, [rbx]
0x18002b269  jz      short loc_18002B284
0x18002b26b  mov     rcx, [rbx]; string
0x18002b26e  call    cs:__imp_WindowsDeleteString
0x18002b274  mov     [rbx], r15
0x18002b277  mov     rdx, rbx; newString
0x18002b27a  mov     rcx, rdi; string
0x18002b27d  call    cs:__imp_WindowsDuplicateString
0x18002b283  nop
0x18002b284  lea     rcx, [rsp+98h+bstrString]
0x18002b289  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b28e  nop
0x18002b28f  lea     rcx, [rsp+98h+Str]
0x18002b294  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b299  nop
0x18002b29a  lea     rcx, [rsp+98h+var_48]
0x18002b29f  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002b2a4  nop
0x18002b2a5  xor     eax, eax
0x18002b2a7  jmp     short loc_18002B2AD
0x18002b2a9  mov     eax, dword ptr [rsp+98h+pUnk]
0x18002b2ad  mov     rcx, [rsp+98h+var_20]
0x18002b2b2  xor     rcx, rsp; StackCookie
0x18002b2b5  call    __security_check_cookie
0x18002b2ba  lea     r11, [rsp+98h+var_18]
0x18002b2c2  mov     rbx, [r11+30h]
0x18002b2c6  mov     rsi, [r11+38h]
0x18002b2ca  mov     rsp, r11
0x18002b2cd  pop     r15
0x18002b2cf  pop     r14
0x18002b2d1  pop     rdi
0x18002b2d2  retn
0x18002b2d3  mov     r9d, eax; char *
0x18002b2d6  lea     edx, [r15+7Bh]; void *
0x18002b2da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b2e0  mov     r9d, eax; char *
0x18002b2e3  mov     edx, 94h; void *
0x18002b2e8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b2ed  mov     ecx, 80070216h; this
0x18002b2f2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
