# RDXAppServiceConnection::SendSimpleMessageAndWaitForResponse(ushort const *,void *,_GUID const &,void * *)

- ea: `0x180033a10`
- end: `0x180033c54`
- name: `?SendSimpleMessageAndWaitForResponse@RDXAppServiceConnection@@UEAAJPEBGPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `580`
- prototype: `__int64 __usercall@<rax>(RDXAppServiceConnection *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, void *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x1800056d5`
- `0x18000e330`
- `0x18001094c`
- `0x18001bf68`
- `0x18002666c`
- `0x180027a38`
- `0x180032a28`
- `0x1800337c0`
- `0x180033a10`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033a86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033a6d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180033aa8`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180033aa8`

## string_xrefs

- `0x180033b16`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033b91`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033bf8`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033b5e`: `Command`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall RDXAppServiceConnection::SendSimpleMessageAndWaitForResponse(
        RDXAppServiceConnection *this,
        const unsigned __int16 *a2,
        void *a3,
        const struct _GUID *a4,
        void **a5)
{
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v12; // [rsp+20h] [rbp-98h]
  int v13; // [rsp+20h] [rbp-98h]
  struct Windows::Foundation::Collections::IPropertySet *v14; // [rsp+30h] [rbp-88h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v15; // [rsp+38h] [rbp-80h] BYREF
  const unsigned __int16 *v16; // [rsp+40h] [rbp-78h] BYREF
  HSTRING string; // [rsp+48h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v16 = a2;
  *a5 = 0;
  v14 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v14 = 0;
  v15 = 0;
  v8 = RoActivateInstance(string, &v15);
  if ( v8 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v14 = v15;
    }
    else
    {
      v8 = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))v15)(
             v15,
             &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
             &v14);
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
      (const char *)(unsigned int)v8,
      v12);
  Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
    (Windows::Internal::ShellHelpers::PropertySetHelper *)&v15,
    v14);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, &v16);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&string, L"Command", 8u, 7u);
  v9 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
         (Windows::Internal::ShellHelpers::PropertySetHelper *)&v15,
         *(HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
      (const char *)(unsigned int)v9,
      v12);
  v10 = RDXAppServiceConnection::SendMessageAndWaitForResponse(this, v14, a3, a4, a5);
  if ( v10 == -2147023673 )
  {
    if ( v15 )
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v15 + 16LL))(v15);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v14);
    return 2147943623LL;
  }
  else
  {
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
        (const char *)(unsigned int)v10,
        v13);
    if ( v15 )
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v15 + 16LL))(v15);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180033a10  push    rbx
0x180033a12  push    rsi
0x180033a13  push    rdi
0x180033a14  push    r14
0x180033a16  push    r15
0x180033a18  sub     rsp, 90h
0x180033a1f  mov     rax, cs:__security_cookie
0x180033a26  xor     rax, rsp
0x180033a29  mov     [rsp+0B8h+var_30], rax
0x180033a31  mov     r15, r9
0x180033a34  mov     r14, r8
0x180033a37  mov     rsi, rcx
0x180033a3a  mov     [rsp+0B8h+var_78], rdx
0x180033a3f  mov     rdi, [rsp+0B8h+arg_20]
0x180033a47  mov     qword ptr [rdi], 0
0x180033a4e  mov     [rsp+0B8h+var_88], 0
0x180033a57  lea     r9, [rsp+0B8h+string]; string
0x180033a5c  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x180033a61  mov     edx, 2Ah ; '*'; length
0x180033a66  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180033a6d  call    cs:__imp_WindowsCreateStringReference
0x180033a73  test    eax, eax
0x180033a75  jns     short loc_180033A8C
0x180033a77  xor     r9d, r9d; lpArguments
0x180033a7a  xor     r8d, r8d; nNumberOfArguments
0x180033a7d  lea     edx, [r9+1]; dwExceptionFlags
0x180033a81  mov     ecx, 0C000000Dh; dwExceptionCode
0x180033a86  call    cs:__imp_RaiseException
0x180033a8c  mov     [rsp+0B8h+var_88], 0
0x180033a95  mov     [rsp+0B8h+var_80], 0
0x180033a9e  lea     rdx, [rsp+0B8h+var_80]
0x180033aa3  mov     rcx, [rsp+0B8h+string]
0x180033aa8  call    cs:__imp_RoActivateInstance
0x180033aae  mov     ebx, eax
0x180033ab0  test    eax, eax
0x180033ab2  js      short loc_180033B07
0x180033ab4  mov     r8d, 10h; Size
0x180033aba  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180033ac1  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180033ac8  call    memcmp_0
0x180033acd  mov     rcx, [rsp+0B8h+var_80]
0x180033ad2  test    eax, eax
0x180033ad4  jnz     short loc_180033ADD
0x180033ad6  mov     [rsp+0B8h+var_88], rcx
0x180033adb  jmp     short loc_180033B07
0x180033add  mov     rax, [rcx]
0x180033ae0  lea     r8, [rsp+0B8h+var_88]
0x180033ae5  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180033aec  mov     rax, [rax]
0x180033aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af4  mov     ebx, eax
0x180033af6  mov     rcx, [rsp+0B8h+var_80]
0x180033afb  mov     rax, [rcx]
0x180033afe  mov     rax, [rax+10h]
0x180033b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b07  mov     rcx, [rsp+0B8h]; this
0x180033b0f  test    ebx, ebx
0x180033b11  jns     short loc_180033B27
0x180033b13  mov     r9d, ebx; char *
0x180033b16  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033b1d  mov     edx, 9Fh; void *
0x180033b22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033b27  mov     rdx, [rsp+0B8h+var_88]; struct Windows::Foundation::Collections::IPropertySet *
0x180033b2c  lea     rcx, [rsp+0B8h+var_80]; this
0x180033b31  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180033b36  nop
0x180033b37  lea     rdx, [rsp+0B8h+var_78]
0x180033b3c  lea     rcx, [rsp+0B8h+var_50]
0x180033b41  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033b46  nop
0x180033b47  mov     rbx, [rax+18h]
0x180033b4b  mov     qword ptr [rsp+0B8h+hstringHeader.Reserved+10h], 0
0x180033b54  mov     r9d, 7; unsigned int
0x180033b5a  lea     r8d, [r9+1]; unsigned int
0x180033b5e  lea     rdx, aCommand; "Command"
0x180033b65  lea     rcx, [rsp+0B8h+string]; hstringHeader
0x180033b6a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180033b6f  nop
0x180033b70  mov     r9, rbx
0x180033b73  mov     rdx, qword ptr [rsp+0B8h+hstringHeader.Reserved+10h]; HSTRING
0x180033b78  lea     rcx, [rsp+0B8h+var_80]; this
0x180033b7d  call    ??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)
0x180033b82  mov     rcx, [rsp+0B8h]; this
0x180033b8a  test    eax, eax
0x180033b8c  jns     short loc_180033BA3
0x180033b8e  mov     r9d, eax; char *
0x180033b91  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033b98  mov     edx, 0A1h; void *
0x180033b9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033ba3  mov     qword ptr [rsp+0B8h+var_98], rdi; int
0x180033ba8  mov     r9, r15; struct _GUID *
0x180033bab  mov     r8, r14; void *
0x180033bae  mov     rdx, [rsp+0B8h+var_88]; struct Windows::Foundation::Collections::IPropertySet *
0x180033bb3  mov     rcx, rsi; this
0x180033bb6  call    ?SendMessageAndWaitForResponse@RDXAppServiceConnection@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAXAEBU_GUID@@PEAPEAX@Z; RDXAppServiceConnection::SendMessageAndWaitForResponse(Windows::Foundation::Collections::IPropertySet *,void *,_GUID const &,void * *)
0x180033bbb  mov     ebx, 800704C7h
0x180033bc0  cmp     eax, ebx
0x180033bc2  jnz     short loc_180033BE9
0x180033bc4  mov     rcx, [rsp+0B8h+var_80]
0x180033bc9  test    rcx, rcx
0x180033bcc  jz      short loc_180033BDB
0x180033bce  mov     rdx, [rcx]
0x180033bd1  mov     rax, [rdx+10h]
0x180033bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bda  nop
0x180033bdb  lea     rcx, [rsp+0B8h+var_88]
0x180033be0  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180033be5  mov     eax, ebx
0x180033be7  jmp     short loc_180033C34
0x180033be9  mov     rcx, [rsp+0B8h]; this
0x180033bf1  test    eax, eax
0x180033bf3  jns     short loc_180033C0A
0x180033bf5  mov     r9d, eax; char *
0x180033bf8  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033bff  mov     edx, 0A5h; void *
0x180033c04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033c0a  mov     rcx, [rsp+0B8h+var_80]
0x180033c0f  test    rcx, rcx
0x180033c12  jz      short loc_180033C21
0x180033c14  mov     rax, [rcx]
0x180033c17  mov     rax, [rax+10h]
0x180033c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c20  nop
0x180033c21  lea     rcx, [rsp+0B8h+var_88]
0x180033c26  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180033c2b  nop
0x180033c2c  xor     eax, eax
0x180033c2e  jmp     short loc_180033C34
0x180033c30  mov     eax, dword ptr [rsp+0B8h+var_88]
0x180033c34  mov     rcx, [rsp+0B8h+var_30]
0x180033c3c  xor     rcx, rsp; StackCookie
0x180033c3f  call    __security_check_cookie
0x180033c44  add     rsp, 90h
0x180033c4b  pop     r15
0x180033c4d  pop     r14
0x180033c4f  pop     rdi
0x180033c50  pop     rsi
0x180033c51  pop     rbx
0x180033c52  retn
```
