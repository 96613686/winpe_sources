# IsWCOSUserModelSpecialAccount(SpecialAccountTypes,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023584`
- end: `0x1800236e3`
- name: `?IsWCOSUserModelSpecialAccount@@YA_NW4SpecialAccountTypes@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013040`
- `0x180015ee0`
- `0x180016eb8`

## callees

- `0x180003530`
- `0x18000ccd4`
- `0x18001238c`
- `0x180015490`
- `0x180015cb0`
- `0x180023200`
- `0x180023584`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800235f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800235f2`
- `ntdll!RtlIsMultiSessionSku` at `0x1800235aa`
- `ntdll!RtlIsMultiSessionSku` at `0x1800235aa`

## string_xrefs

- `0x180023603`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall IsWCOSUserModelSpecialAccount(int a1, __int64 a2)
{
  char v4; // bl
  int ActivationFactory; // eax
  HSTRING_HEADER *v6; // rbx
  __int64 v8[2]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v9[6]; // [rsp+30h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  __int64 v11; // [rsp+78h] [rbp+Fh]
  __int64 v12; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = 0;
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    v8[0] = 0;
    v11 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v11, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, v8);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5C,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v8[0]);
    v9[0] = 1;
    v9[1] = IsResourceAccount;
    v9[2] = 2;
    v9[3] = IsVisitorAccount;
    v9[4] = 4;
    v9[5] = IsDSMA;
    LODWORD(hstringHeader.Reserved.Reserved1) = a1;
    std::wstring::wstring(&hstringHeader.Reserved.Reserved2[8], a2);
    v12 = v8[0];
    if ( v8[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8[0] + 8LL))(v8[0]);
    v8[1] = (__int64)&hstringHeader;
    v6 = (HSTRING_HEADER *)v9;
    do
    {
      if ( ((__int64)v6->Reserved.Reserved1 & LODWORD(hstringHeader.Reserved.Reserved1)) != 0
        && (*(unsigned __int8 (__fastcall **)(__int64, char *))&v6->Reserved.Reserved2[8])(
             v12,
             &hstringHeader.Reserved.Reserved2[8]) )
      {
        break;
      }
      v6 = (HSTRING_HEADER *)((char *)v6 + 16);
    }
    while ( v6 != &hstringHeader );
    lambda_06041550e7ef66c0a8694d296676c2b0_::__lambda_06041550e7ef66c0a8694d296676c2b0_(&hstringHeader);
    wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(v8);
    return v6 != &hstringHeader;
  }
  return v4;
}

```

## disassembly

```asm
0x180023584  push    rbp
0x180023586  push    rbx
0x180023587  push    rsi
0x180023588  push    rdi
0x180023589  lea     rbp, [rsp-3Fh]
0x18002358e  sub     rsp, 0A8h
0x180023595  mov     rax, cs:__security_cookie
0x18002359c  xor     rax, rsp
0x18002359f  mov     [rbp+57h+var_30], rax
0x1800235a3  mov     rsi, rdx
0x1800235a6  mov     edi, ecx
0x1800235a8  xor     bl, bl
0x1800235aa  call    cs:__imp_RtlIsMultiSessionSku
0x1800235b0  test    al, al
0x1800235b2  jnz     loc_1800236C9
0x1800235b8  mov     [rbp+57h+var_A0], 0
0x1800235c0  mov     [rbp+57h+var_48], 0
0x1800235c8  mov     r9d, 23h ; '#'; unsigned int
0x1800235ce  lea     r8d, [r9+1]; unsigned int
0x1800235d2  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800235d9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800235dd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800235e2  nop
0x1800235e3  lea     r8, [rbp+57h+var_A0]
0x1800235e7  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x1800235ee  mov     rcx, [rbp+57h+var_48]
0x1800235f2  call    cs:__imp_RoGetActivationFactory
0x1800235f8  mov     rcx, [rbp+5Fh]; this
0x1800235fc  test    eax, eax
0x1800235fe  jns     short loc_180023615
0x180023600  mov     r9d, eax; char *
0x180023603  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002360a  mov     edx, 5Ch ; '\'; void *
0x18002360f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023615  mov     [rbp+57h+var_90], 1
0x18002361d  lea     rax, ?IsResourceAccount@@YA_NPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsResourceAccount(Windows::System::Internal::IUserManagerStatics *,std::wstring const &)
0x180023624  mov     [rbp+57h+var_88], rax
0x180023628  mov     [rbp+57h+var_80], 2
0x180023630  lea     rax, ?IsVisitorAccount@@YA_NPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsVisitorAccount(Windows::System::Internal::IUserManagerStatics *,std::wstring const &)
0x180023637  mov     [rbp+57h+var_78], rax
0x18002363b  mov     [rbp+57h+var_70], 4
0x180023643  lea     rax, ?IsDSMA@@YA_NPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsDSMA(Windows::System::Internal::IUserManagerStatics *,std::wstring const &)
0x18002364a  mov     [rbp+57h+var_68], rax
0x18002364e  mov     dword ptr [rbp+57h+hstringHeader.Reserved], edi
0x180023651  mov     rdx, rsi
0x180023654  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x180023658  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002365d  mov     rcx, [rbp+57h+var_A0]
0x180023661  mov     [rbp+57h+var_38], rcx
0x180023665  test    rcx, rcx
0x180023668  jz      short loc_180023677
0x18002366a  mov     rax, [rcx]
0x18002366d  mov     rax, [rax+8]
0x180023671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023676  nop
0x180023677  lea     rax, [rbp+57h+hstringHeader]
0x18002367b  mov     [rbp+57h+var_98], rax
0x18002367f  lea     rbx, [rbp+57h+var_90]
0x180023683  mov     eax, [rbx]
0x180023685  test    dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x180023688  jz      short loc_18002369F
0x18002368a  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]
0x18002368e  mov     rcx, [rbp+57h+var_38]
0x180023692  mov     rax, [rbx+8]
0x180023696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002369b  test    al, al
0x18002369d  jnz     short loc_1800236AC
0x18002369f  add     rbx, 10h
0x1800236a3  lea     rax, [rbp+57h+hstringHeader]
0x1800236a7  cmp     rbx, rax
0x1800236aa  jnz     short loc_180023683
0x1800236ac  lea     rcx, [rbp+57h+hstringHeader]
0x1800236b0  call    _lambda_06041550e7ef66c0a8694d296676c2b0_____lambda_06041550e7ef66c0a8694d296676c2b0_
0x1800236b5  nop
0x1800236b6  lea     rcx, [rbp+57h+var_A0]
0x1800236ba  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x1800236bf  lea     rax, [rbp+57h+hstringHeader]
0x1800236c3  cmp     rbx, rax
0x1800236c6  setnz   bl
0x1800236c9  mov     al, bl
0x1800236cb  mov     rcx, [rbp+57h+var_30]
0x1800236cf  xor     rcx, rsp; StackCookie
0x1800236d2  call    __security_check_cookie
0x1800236d7  add     rsp, 0A8h
0x1800236de  pop     rdi
0x1800236df  pop     rsi
0x1800236e0  pop     rbx
0x1800236e1  pop     rbp
0x1800236e2  retn
```
