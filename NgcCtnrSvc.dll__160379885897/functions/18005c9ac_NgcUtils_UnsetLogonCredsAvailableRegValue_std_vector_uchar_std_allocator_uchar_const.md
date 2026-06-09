# NgcUtils::UnsetLogonCredsAvailableRegValue(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18005c9ac`
- end: `0x18005cb2c`
- name: `?UnsetLogonCredsAvailableRegValue@NgcUtils@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180051aa0`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x180018194`
- `0x1800199d8`
- `0x18002b0dc`
- `0x18002c640`
- `0x18005c6cc`
- `0x18005c9ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cacc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cacc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ca47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ca47`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 NgcUtils::UnsetLogonCredsAvailableRegValue()
{
  __int64 v0; // r8
  int v1; // edi
  HKEY *phkResult; // rax
  const WCHAR *v3; // rdx
  int Key; // ebx
  unsigned __int8 *v5; // rdx
  int v7; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp+27h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+68h] [rbp+2Fh] BYREF

  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpSubKey);
  v1 = NgcUtils::BuildFullRegKeyPath(v0, lpSubKey);
  if ( v1 < 0 )
    goto LABEL_15;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v3 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v3 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x20006u, 0, phkResult, 0);
  if ( !Key )
  {
    *(_DWORD *)Data = 2;
    Key = RegSetValueExW(hKey, L"LogonCredsAvailable", 0, 4u, Data, 4u);
    if ( !Key )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_15;
    }
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_8;
    v5 = (unsigned __int8 *)&word_1800AE59E;
    goto LABEL_7;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v5 = (unsigned __int8 *)byte_1800AE561;
LABEL_7:
    v7 = Key;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      v5,
      0,
      0,
      (__int64)&v7);
  }
LABEL_8:
  if ( Key > 0 )
    Key = (unsigned __int16)Key | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v1 = Key;
LABEL_15:
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18005c9ac  mov     [rsp-8+arg_8], rbx
0x18005c9b1  mov     [rsp-8+arg_10], rdi
0x18005c9b6  push    rbp
0x18005c9b7  lea     rbp, [rsp-57h]
0x18005c9bc  sub     rsp, 90h
0x18005c9c3  mov     rax, cs:__security_cookie
0x18005c9ca  xor     rax, rsp
0x18005c9cd  mov     [rbp+57h+var_8], rax
0x18005c9d1  mov     r8, rcx
0x18005c9d4  lea     rcx, [rbp+57h+lpSubKey]
0x18005c9d8  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18005c9dd  nop
0x18005c9de  lea     rdx, [rbp+57h+lpSubKey]
0x18005c9e2  mov     rcx, r8
0x18005c9e5  call    NgcUtils__BuildFullRegKeyPath
0x18005c9ea  mov     edi, eax
0x18005c9ec  test    eax, eax
0x18005c9ee  js      loc_18005CAFF
0x18005c9f4  mov     [rbp+57h+hKey], 0
0x18005c9fc  lea     rcx, [rbp+57h+hKey]
0x18005ca00  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005ca05  lea     rdx, [rbp+57h+lpSubKey]
0x18005ca09  cmp     [rbp+57h+var_10], 7
0x18005ca0e  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18005ca13  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x18005ca1c  mov     [rsp+90h+phkResult], rax; phkResult
0x18005ca21  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005ca2a  mov     [rsp+90h+samDesired], 20006h; samDesired
0x18005ca32  mov     [rsp+90h+dwOptions], 0; dwOptions
0x18005ca3a  xor     r9d, r9d; lpClass
0x18005ca3d  xor     r8d, r8d; Reserved
0x18005ca40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ca47  call    cs:__imp_RegCreateKeyExW
0x18005ca4e  nop     dword ptr [rax+rax+00h]
0x18005ca53  mov     ebx, eax
0x18005ca55  test    eax, eax
0x18005ca57  jz      short loc_18005CAA3
0x18005ca59  mov     ecx, cs:dword_1800BE0B8
0x18005ca5f  cmp     ecx, 2
0x18005ca62  jbe     short loc_18005CA89
0x18005ca64  lea     rdx, byte_1800AE561
0x18005ca6b  lea     rax, [rbp+57h+var_40]
0x18005ca6f  mov     qword ptr [rsp+90h+dwOptions], rax
0x18005ca74  mov     [rbp+57h+var_40], ebx
0x18005ca77  xor     r9d, r9d
0x18005ca7a  xor     r8d, r8d
0x18005ca7d  lea     rcx, dword_1800BE0B8
0x18005ca84  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005ca89  test    ebx, ebx
0x18005ca8b  jle     short loc_18005CA96
0x18005ca8d  movzx   ebx, bx
0x18005ca90  or      ebx, 80070000h
0x18005ca96  lea     rcx, [rbp+57h+hKey]
0x18005ca9a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005ca9f  mov     edi, ebx
0x18005caa1  jmp     short loc_18005CAFF
0x18005caa3  mov     dword ptr [rbp+57h+Data], 2
0x18005caaa  mov     r9d, 4; dwType
0x18005cab0  mov     [rsp+90h+samDesired], r9d; cbData
0x18005cab5  lea     rax, [rbp+57h+Data]
0x18005cab9  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x18005cabe  xor     r8d, r8d; Reserved
0x18005cac1  lea     rdx, aLogoncredsavai; "LogonCredsAvailable"
0x18005cac8  mov     rcx, [rbp+57h+hKey]; hKey
0x18005cacc  call    cs:__imp_RegSetValueExW
0x18005cad3  nop     dword ptr [rax+rax+00h]
0x18005cad8  mov     ebx, eax
0x18005cada  test    eax, eax
0x18005cadc  jz      short loc_18005CAF5
0x18005cade  mov     ecx, cs:dword_1800BE0B8
0x18005cae4  cmp     ecx, 2
0x18005cae7  jbe     short loc_18005CA89
0x18005cae9  lea     rdx, word_1800AE59E
0x18005caf0  jmp     loc_18005CA6B
0x18005caf5  lea     rcx, [rbp+57h+hKey]
0x18005caf9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005cafe  nop
0x18005caff  lea     rcx, [rbp+57h+lpSubKey]
0x18005cb03  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005cb08  mov     eax, edi
0x18005cb0a  mov     rcx, [rbp+57h+var_8]
0x18005cb0e  xor     rcx, rsp; StackCookie
0x18005cb11  call    __security_check_cookie
0x18005cb16  lea     r11, [rsp+90h+var_s0]
0x18005cb1e  mov     rbx, [r11+18h]
0x18005cb22  mov     rdi, [r11+20h]
0x18005cb26  mov     rsp, r11
0x18005cb29  pop     rbp
0x18005cb2a  retn
```
