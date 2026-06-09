# GetExtendedDeviceInfoImpl

- ea: `0x180022f38`
- end: `0x18002322a`
- name: `GetExtendedDeviceInfoImpl`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009745c`

## callees

- `0x18002085c`
- `0x1800208b0`
- `0x180020994`
- `0x1800209d4`
- `0x180020ad0`
- `0x180022da4`
- `0x180022f38`
- `0x180097804`
- `0x180098a2c`
- `0x18009c310`
- `0x18009cc78`
- `0x1800a98c0`
- `0x1800ee7dc`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022fc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180023135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180023166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180023135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180023166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002302e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800231e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800231f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002302e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800231e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800231f6`

## string_xrefs

- `0x180022fa1`: `Windows.Security.ExchangeActiveSyncProvisioning.EasClientDeviceInformation`
- `0x180022ff5`: `onecoreuap\drivers\mobilepc\location\product\common\wsprotocolslib\utils.cpp`
- `0x180023082`: `onecoreuap\drivers\mobilepc\location\product\common\wsprotocolslib\utils.cpp`
- `0x1800230ff`: `onecoreuap\drivers\mobilepc\location\product\common\wsprotocolslib\utils.cpp`
- `0x1800230ec`: `easClientDeviceInformation->get_SystemProductName(strProductName.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetExtendedDeviceInfoImpl(_BYTE *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  PCWSTR v12; // rax
  __int64 v13; // rcx
  wil::details *v15; // [rsp+28h] [rbp-11h]
  __int64 v16; // [rsp+30h] [rbp-9h] BYREF
  HSTRING string; // [rsp+38h] [rbp-1h] BYREF
  HSTRING v18; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp+Fh] BYREF
  HSTRING hstringHeader[4]; // [rsp+68h] [rbp+2Fh] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+5Fh]

  std::wstring::_Eos(a1, 0);
  std::wstring::wstring(v19);
  v18 = 0;
  string = 0;
  v16 = 0;
  memset(hstringHeader, 0, sizeof(hstringHeader));
  if ( WindowsCreateStringReference(
         L"Windows.Security.ExchangeActiveSyncProvisioning.EasClientDeviceInformation",
         0x4Au,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<ABI::Windows::Security::ExchangeActiveSyncProvisioning::IEasClientDeviceInformation>(
         hstringHeader[0],
         &v16);
  v3 = v2;
  if ( v2 < 0 )
  {
    LODWORD(v15) = v2;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\wsprotocolslib\\utils.cpp",
      "GetExtendedDeviceInfoImpl",
      "Windows::Foundation::ActivateInstance(strEasClientDeviceInformation.Get(), easClientDeviceInformation.GetAddressOf())",
      v15,
      v16);
    v4 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    if ( string )
      WindowsDeleteString(string);
    if ( v18 )
      WindowsDeleteString(v18);
    goto LABEL_31;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 72LL))(v16, &v18);
  v3 = v5;
  if ( v5 < 0 )
  {
    LODWORD(v15) = v5;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\wsprotocolslib\\utils.cpp",
      "GetExtendedDeviceInfoImpl",
      "easClientDeviceInformation->get_SystemManufacturer(strManufacturer.GetAddressOf())",
      v15,
      v16);
    v6 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
LABEL_13:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Windows::Internal::String::~String((Windows::Internal::String *)&v18);
    goto LABEL_31;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 80LL))(v16, &string);
  v3 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v15) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\wsprotocolslib\\utils.cpp",
      "GetExtendedDeviceInfoImpl",
      "easClientDeviceInformation->get_SystemProductName(strProductName.GetAddressOf())",
      v15,
      v16);
    v8 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_13;
  }
  if ( !WindowsIsStringEmpty(v18) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
    v10 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Append<unsigned short>(v19, v11, v10);
    if ( !WindowsIsStringEmpty(string) )
    {
      std::wstring::append(v19, L"/");
      v12 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::append(v19, v12);
    }
    LSUtility::RemoveInvalidXmlChars(v19);
  }
  if ( a1 != v19 )
  {
    std::wstring::_Tidy_deallocate(a1);
    std::wstring::_Take_contents(a1, v19);
  }
  v13 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v18 )
    WindowsDeleteString(v18);
  v3 = 0;
LABEL_31:
  std::wstring::_Tidy_deallocate(v19);
  return v3;
}

```

## disassembly

```asm
0x180022f38  mov     [rsp-8+arg_8], rbx
0x180022f3d  mov     [rsp-8+arg_10], rdi
0x180022f42  push    rbp
0x180022f43  lea     rbp, [rsp-57h]
0x180022f48  sub     rsp, 90h
0x180022f4f  mov     rax, cs:__security_cookie
0x180022f56  xor     rax, rsp
0x180022f59  mov     [rbp+57h+var_8], rax
0x180022f5d  mov     rdi, rcx
0x180022f60  xor     edx, edx
0x180022f62  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180022f67  lea     rcx, [rbp+57h+var_48]
0x180022f6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022f70  nop
0x180022f71  mov     [rbp+57h+var_50], 0
0x180022f79  mov     [rbp+57h+string], 0
0x180022f81  mov     [rbp+57h+var_60], 0
0x180022f89  xorps   xmm0, xmm0
0x180022f8c  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180022f90  movups  xmmword ptr [rbp+57h+hstringHeader+10h], xmm0
0x180022f94  lea     r9, [rbp+57h+hstringHeader]; string
0x180022f98  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180022f9c  mov     edx, 4Ah ; 'J'; length
0x180022fa1  lea     rcx, ?RuntimeClass_Windows_Security_ExchangeActiveSyncProvisioning_EasClientDeviceInformation@@3QBGB; "Windows.Security.ExchangeActiveSyncProv"...
0x180022fa8  call    cs:__imp_WindowsCreateStringReference
0x180022fae  test    eax, eax
0x180022fb0  jns     short loc_180022FC7
0x180022fb2  xor     r9d, r9d; lpArguments
0x180022fb5  xor     r8d, r8d; nNumberOfArguments
0x180022fb8  lea     edx, [r9+1]; dwExceptionFlags
0x180022fbc  mov     ecx, 0C000000Dh; dwExceptionCode
0x180022fc1  call    cs:__imp_RaiseException
0x180022fc7  lea     rdx, [rbp+57h+var_60]
0x180022fcb  mov     rcx, qword ptr [rbp+57h+hstringHeader]
0x180022fcf  call    ??$ActivateInstance@UIEasClientDeviceInformation@ExchangeActiveSyncProvisioning@Security@Windows@ABI@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEasClientDeviceInformation@ExchangeActiveSyncProvisioning@Security@1ABI@@@Z; Windows::Foundation::ActivateInstance<ABI::Windows::Security::ExchangeActiveSyncProvisioning::IEasClientDeviceInformation>(HSTRING__ *,ABI::Windows::Security::ExchangeActiveSyncProvisioning::IEasClientDeviceInformation * *)
0x180022fd4  mov     ebx, eax
0x180022fd6  test    eax, eax
0x180022fd8  jns     short loc_18002304D
0x180022fda  mov     rcx, [rbp+5Fh]; this
0x180022fde  mov     dword ptr [rsp+90h+var_68], eax; wil::details *
0x180022fe2  lea     rax, aWindowsFoundat; "Windows::Foundation::ActivateInstance(s"...
0x180022fe9  mov     [rsp+90h+var_70], rax; char *
0x180022fee  lea     r9, aGetextendeddev_0; "GetExtendedDeviceInfoImpl"
0x180022ff5  lea     r8, aOnecoreuapDriv_36; "onecoreuap\\drivers\\mobilepc\\location"...
0x180022ffc  mov     edx, 29Ch; void *
0x180023001  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180023006  nop
0x180023007  mov     rcx, [rbp+57h+var_60]
0x18002300b  test    rcx, rcx
0x18002300e  jz      short loc_180023025
0x180023010  mov     [rbp+57h+var_60], 0
0x180023018  mov     rax, [rcx]
0x18002301b  mov     rax, [rax+10h]
0x18002301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023024  nop
0x180023025  mov     rcx, [rbp+57h+string]; string
0x180023029  test    rcx, rcx
0x18002302c  jz      short loc_180023035
0x18002302e  call    cs:__imp_WindowsDeleteString
0x180023034  nop
0x180023035  mov     rcx, [rbp+57h+var_50]; string
0x180023039  test    rcx, rcx
0x18002303c  jz      loc_1800231FE
0x180023042  call    cs:__imp_WindowsDeleteString
0x180023048  jmp     loc_1800231FE
0x18002304d  mov     rcx, [rbp+57h+var_60]
0x180023051  mov     rax, [rcx]
0x180023054  lea     rdx, [rbp+57h+var_50]
0x180023058  mov     rax, [rax+48h]
0x18002305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023061  mov     ebx, eax
0x180023063  test    eax, eax
0x180023065  jns     short loc_1800230CA
0x180023067  mov     rcx, [rbp+5Fh]; this
0x18002306b  mov     dword ptr [rsp+90h+var_68], eax; wil::details *
0x18002306f  lea     rax, aEasclientdevic_0; "easClientDeviceInformation->get_SystemM"...
0x180023076  mov     [rsp+90h+var_70], rax; char *
0x18002307b  lea     r9, aGetextendeddev_0; "GetExtendedDeviceInfoImpl"
0x180023082  lea     r8, aOnecoreuapDriv_36; "onecoreuap\\drivers\\mobilepc\\location"...
0x180023089  mov     edx, 29Eh; void *
0x18002308e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180023093  nop
0x180023094  mov     rcx, [rbp+57h+var_60]
0x180023098  test    rcx, rcx
0x18002309b  jz      short loc_1800230B2
0x18002309d  mov     [rbp+57h+var_60], 0
0x1800230a5  mov     rax, [rcx]
0x1800230a8  mov     rax, [rax+10h]
0x1800230ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230b1  nop
0x1800230b2  lea     rcx, [rbp+57h+string]; this
0x1800230b6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800230bb  nop
0x1800230bc  lea     rcx, [rbp+57h+var_50]; this
0x1800230c0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800230c5  jmp     loc_1800231FE
0x1800230ca  mov     rcx, [rbp+57h+var_60]
0x1800230ce  mov     rax, [rcx]
0x1800230d1  lea     rdx, [rbp+57h+string]
0x1800230d5  mov     rax, [rax+50h]
0x1800230d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230de  mov     ebx, eax
0x1800230e0  test    eax, eax
0x1800230e2  jns     short loc_180023131
0x1800230e4  mov     rcx, [rbp+5Fh]; this
0x1800230e8  mov     dword ptr [rsp+90h+var_68], eax; wil::details *
0x1800230ec  lea     rax, aEasclientdevic; "easClientDeviceInformation->get_SystemP"...
0x1800230f3  mov     [rsp+90h+var_70], rax; char *
0x1800230f8  lea     r9, aGetextendeddev_0; "GetExtendedDeviceInfoImpl"
0x1800230ff  lea     r8, aOnecoreuapDriv_36; "onecoreuap\\drivers\\mobilepc\\location"...
0x180023106  mov     edx, 29Fh; void *
0x18002310b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180023110  nop
0x180023111  mov     rcx, [rbp+57h+var_60]
0x180023115  test    rcx, rcx
0x180023118  jz      short loc_18002312F
0x18002311a  mov     [rbp+57h+var_60], 0
0x180023122  mov     rax, [rcx]
0x180023125  mov     rax, [rax+10h]
0x180023129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002312e  nop
0x18002312f  jmp     short loc_1800230B2
0x180023131  mov     rcx, [rbp+57h+var_50]; string
0x180023135  call    cs:__imp_WindowsIsStringEmpty
0x18002313b  test    eax, eax
0x18002313d  jnz     short loc_1800231A1
0x18002313f  xor     edx, edx; length
0x180023141  mov     rcx, [rbp+57h+var_50]; string
0x180023145  call    cs:__imp_WindowsGetStringRawBuffer
0x18002314b  mov     rcx, rax
0x18002314e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180023153  mov     r8, rax
0x180023156  mov     rdx, rcx
0x180023159  lea     rcx, [rbp+57h+var_48]
0x18002315d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180023162  mov     rcx, [rbp+57h+string]; string
0x180023166  call    cs:__imp_WindowsIsStringEmpty
0x18002316c  test    eax, eax
0x18002316e  jnz     short loc_180023198
0x180023170  lea     rdx, asc_180195200; "/"
0x180023177  lea     rcx, [rbp+57h+var_48]
0x18002317b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023180  xor     edx, edx; length
0x180023182  mov     rcx, [rbp+57h+string]; string
0x180023186  call    cs:__imp_WindowsGetStringRawBuffer
0x18002318c  mov     rdx, rax
0x18002318f  lea     rcx, [rbp+57h+var_48]
0x180023193  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023198  lea     rcx, [rbp+57h+var_48]
0x18002319c  call    ?RemoveInvalidXmlChars@LSUtility@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LSUtility::RemoveInvalidXmlChars(std::wstring &)
0x1800231a1  lea     rax, [rbp+57h+var_48]
0x1800231a5  cmp     rdi, rax
0x1800231a8  jz      short loc_1800231BF
0x1800231aa  mov     rcx, rdi
0x1800231ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800231b2  lea     rdx, [rbp+57h+var_48]
0x1800231b6  mov     rcx, rdi
0x1800231b9  call    ?_Take_contents@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x1800231be  nop
0x1800231bf  mov     rcx, [rbp+57h+var_60]
0x1800231c3  test    rcx, rcx
0x1800231c6  jz      short loc_1800231DD
0x1800231c8  mov     [rbp+57h+var_60], 0
0x1800231d0  mov     rax, [rcx]
0x1800231d3  mov     rax, [rax+10h]
0x1800231d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231dc  nop
0x1800231dd  mov     rcx, [rbp+57h+string]; string
0x1800231e1  test    rcx, rcx
0x1800231e4  jz      short loc_1800231ED
0x1800231e6  call    cs:__imp_WindowsDeleteString
0x1800231ec  nop
0x1800231ed  mov     rcx, [rbp+57h+var_50]; string
0x1800231f1  test    rcx, rcx
0x1800231f4  jz      short loc_1800231FC
0x1800231f6  call    cs:__imp_WindowsDeleteString
0x1800231fc  xor     ebx, ebx
0x1800231fe  lea     rcx, [rbp+57h+var_48]
0x180023202  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023207  mov     eax, ebx
0x180023209  mov     rcx, [rbp+57h+var_8]
0x18002320d  xor     rcx, rsp; StackCookie
0x180023210  call    __security_check_cookie
0x180023215  lea     r11, [rsp+90h+var_s0]
0x18002321d  mov     rbx, [r11+18h]
0x180023221  mov     rdi, [r11+20h]
0x180023225  mov     rsp, r11
0x180023228  pop     rbp
0x180023229  retn
```
