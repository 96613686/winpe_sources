# LocalAccountController::GetNextUserName(void)

- ea: `0x180016924`
- end: `0x180016aac`
- name: `?GetNextUserName@LocalAccountController@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015b40`

## callees

- `0x180003530`
- `0x1800057ac`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x180016924`
- `0x180016ab4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016a0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016a0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169ca`

## string_xrefs

- `0x180016957`: `CreatedLocalAccounts`
- `0x180016a1f`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180016a5c`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LocalAccountController::GetNextUserName(__int64 a1, __int64 a2)
{
  HKEY SharedPCKey; // rbx
  bool v4; // zf
  __int64 v5; // rax
  unsigned int v6; // eax
  int v7; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v14[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  std::wstring::wstring((__int64)v13, (__int64)L"CreatedLocalAccounts");
  SharedPCKey = GetSharedPCKey((__int64)v13, 0xF003Fu);
  v12 = SharedPCKey;
  std::wstring::_Tidy_deallocate((__int64)v13);
  *(_QWORD *)Data = 0;
  pcbData = 8;
  v4 = RegGetValueW(SharedPCKey, 0, L"NextAccountSuffix", 0x40u, 0, Data, &pcbData) == 0;
  v5 = 12648430;
  if ( v4 )
    v5 = *(_QWORD *)Data;
  *(_QWORD *)Data = v5 + 1;
  v6 = RegSetValueExW(SharedPCKey, L"NextAccountSuffix", 0, 0xBu, Data, 8u);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDB,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v6,
      pdwType);
  v7 = StringCchPrintfW(v14, 0x101u, L"shpcta%x", *(_QWORD *)Data - 1LL);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xDF,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v7,
      pdwType);
  std::wstring::wstring(a2, (__int64)v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
  return a2;
}

```

## disassembly

```asm
0x180016924  mov     [rsp-8+arg_0], rbx
0x180016929  mov     [rsp-8+arg_10], rdi
0x18001692e  push    rbp
0x18001692f  lea     rbp, [rsp-1A0h]
0x180016937  sub     rsp, 2A0h
0x18001693e  mov     rax, cs:__security_cookie
0x180016945  xor     rax, rsp
0x180016948  mov     [rbp+1A0h+var_10], rax
0x18001694f  mov     rdi, rdx
0x180016952  mov     [rsp+2A0h+var_250], rdx
0x180016957  lea     rdx, aCreatedlocalac; "CreatedLocalAccounts"
0x18001695e  lea     rcx, [rsp+2A0h+var_240]
0x180016963  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016968  nop
0x180016969  mov     edx, 0F003Fh
0x18001696e  lea     rcx, [rsp+2A0h+var_240]
0x180016973  call    ?GetSharedPCKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCKey(std::wstring const &,ulong)
0x180016978  mov     rbx, rax
0x18001697b  mov     [rsp+2A0h+var_250], rax
0x180016980  lea     rcx, [rsp+2A0h+var_240]
0x180016985  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001698a  mov     qword ptr [rsp+2A0h+Data], 0
0x180016993  mov     [rsp+2A0h+var_258], 8
0x18001699b  lea     rax, [rsp+2A0h+var_258]
0x1800169a0  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800169a5  lea     rax, [rsp+2A0h+Data]
0x1800169aa  mov     [rsp+2A0h+pvData], rax; pvData
0x1800169af  mov     [rsp+2A0h+pdwType], 0; pdwType
0x1800169b8  mov     r9d, 40h ; '@'; dwFlags
0x1800169be  lea     r8, ValueName; "NextAccountSuffix"
0x1800169c5  xor     edx, edx; lpSubKey
0x1800169c7  mov     rcx, rbx; hkey
0x1800169ca  call    cs:__imp_RegGetValueW
0x1800169d0  test    eax, eax
0x1800169d2  mov     eax, 0C0FFEEh
0x1800169d7  jnz     short loc_1800169DE
0x1800169d9  mov     rax, qword ptr [rsp+2A0h+Data]
0x1800169de  inc     rax
0x1800169e1  mov     qword ptr [rsp+2A0h+Data], rax
0x1800169e6  mov     dword ptr [rsp+2A0h+pvData], 8; cbData
0x1800169ee  lea     rax, [rsp+2A0h+Data]
0x1800169f3  mov     [rsp+2A0h+pdwType], rax; int
0x1800169f8  mov     r9d, 0Bh; dwType
0x1800169fe  xor     r8d, r8d; Reserved
0x180016a01  lea     rdx, ValueName; "NextAccountSuffix"
0x180016a08  mov     rcx, rbx; hKey
0x180016a0b  call    cs:__imp_RegSetValueExW
0x180016a11  mov     rcx, [rbp+1A8h]; this
0x180016a18  test    eax, eax
0x180016a1a  jz      short loc_180016A31
0x180016a1c  mov     r9d, eax; char *
0x180016a1f  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016a26  mov     edx, 0DBh; void *
0x180016a2b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016a31  mov     r9, qword ptr [rsp+2A0h+Data]
0x180016a36  dec     r9
0x180016a39  lea     r8, aShpctaX; "shpcta%x"
0x180016a40  mov     edx, 101h; unsigned __int64
0x180016a45  lea     rcx, [rbp+1A0h+var_220]; unsigned __int16 *
0x180016a49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016a4e  mov     rcx, [rbp+1A8h]; this
0x180016a55  test    eax, eax
0x180016a57  jns     short loc_180016A6E
0x180016a59  mov     r9d, eax; char *
0x180016a5c  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016a63  mov     edx, 0DFh; void *
0x180016a68  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016a6e  lea     rdx, [rbp+1A0h+var_220]
0x180016a72  mov     rcx, rdi
0x180016a75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016a7a  nop
0x180016a7b  lea     rcx, [rsp+2A0h+var_250]
0x180016a80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016a85  mov     rax, rdi
0x180016a88  mov     rcx, [rbp+1A0h+var_10]
0x180016a8f  xor     rcx, rsp; StackCookie
0x180016a92  call    __security_check_cookie
0x180016a97  lea     r11, [rsp+2A0h+var_s0]
0x180016a9f  mov     rbx, [r11+10h]
0x180016aa3  mov     rdi, [r11+20h]
0x180016aa7  mov     rsp, r11
0x180016aaa  pop     rbp
0x180016aab  retn
```
