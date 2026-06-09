# NgcUtils::SetScenarioInProgressStatus

- ea: `0x18005c84c`
- end: `0x18005c9a4`
- name: `NgcUtils::SetScenarioInProgressStatus`
- size: `344`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050070`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x1800199d8`
- `0x180023278`
- `0x1800232a0`
- `0x18002b0dc`
- `0x18002c640`
- `0x18005c788`
- `0x18005c84c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c959`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c959`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c8fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c8fb`

## string_xrefs

- `0x18005c892`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`
- `0x18005c910`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 NgcUtils::SetScenarioInProgressStatus()
{
  unsigned __int16 *v0; // r8
  int v1; // eax
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  const WCHAR *v4; // rdx
  unsigned int Key; // eax
  __int64 v6; // rdx
  int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  HKEY hKey; // [rsp+50h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp+1Fh] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpSubKey);
  v1 = NgcUtils::BuildFullRegKeyPath_0(v0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v4 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v4 = lpSubKey[0];
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 0x20006u, 0, phkResult, 0);
    if ( Key )
    {
      v6 = 604;
    }
    else
    {
      *(_DWORD *)Data = 1;
      Key = RegSetValueExW(hKey, L"DestructiveResetInProgress", 0, 4u, Data, 4u);
      if ( !Key )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v2 = 0;
        goto LABEL_11;
      }
      v6 = 614;
    }
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
           (const char *)Key,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
      (const char *)(unsigned int)v1,
      dwOptions);
  }
LABEL_11:
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return v2;
}

```

## disassembly

```asm
0x18005c84c  mov     [rsp-8+arg_8], rbx
0x18005c851  push    rbp
0x18005c852  lea     rbp, [rsp-57h]
0x18005c857  sub     rsp, 90h
0x18005c85e  mov     rax, cs:__security_cookie
0x18005c865  xor     rax, rsp
0x18005c868  mov     [rbp+57h+var_10], rax
0x18005c86c  mov     r8, rcx
0x18005c86f  lea     rcx, [rbp+57h+lpSubKey]
0x18005c873  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18005c878  nop
0x18005c879  lea     rdx, [rbp+57h+lpSubKey]
0x18005c87d  mov     rcx, r8; unsigned __int16 *
0x18005c880  call    NgcUtils__BuildFullRegKeyPath_0
0x18005c885  mov     ebx, eax
0x18005c887  test    eax, eax
0x18005c889  jns     short loc_18005C8A8
0x18005c88b  mov     rcx, [rbp+5Fh]; this
0x18005c88f  mov     r9d, eax; char *
0x18005c892  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005c899  mov     edx, 250h; void *
0x18005c89e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c8a3  jmp     loc_18005C97B
0x18005c8a8  mov     [rbp+57h+hKey], 0
0x18005c8b0  lea     rcx, [rbp+57h+hKey]
0x18005c8b4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005c8b9  lea     rdx, [rbp+57h+lpSubKey]
0x18005c8bd  cmp     [rbp+57h+var_18], 7
0x18005c8c2  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18005c8c7  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x18005c8d0  mov     [rsp+90h+phkResult], rax; phkResult
0x18005c8d5  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005c8de  mov     [rsp+90h+samDesired], 20006h; samDesired
0x18005c8e6  mov     [rsp+90h+dwOptions], 0; unsigned int
0x18005c8ee  xor     r9d, r9d; lpClass
0x18005c8f1  xor     r8d, r8d; Reserved
0x18005c8f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c8fb  call    cs:__imp_RegCreateKeyExW
0x18005c902  nop     dword ptr [rax+rax+00h]
0x18005c907  test    eax, eax
0x18005c909  jz      short loc_18005C930
0x18005c90b  mov     edx, 25Ch; void *
0x18005c910  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005c917  mov     r9d, eax; char *
0x18005c91a  mov     rcx, [rbp+5Fh]; this
0x18005c91e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005c923  mov     ebx, eax
0x18005c925  lea     rcx, [rbp+57h+hKey]
0x18005c929  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005c92e  jmp     short loc_18005C97B
0x18005c930  mov     dword ptr [rbp+57h+Data], 1
0x18005c937  mov     r9d, 4; dwType
0x18005c93d  mov     [rsp+90h+samDesired], r9d; cbData
0x18005c942  lea     rax, [rbp+57h+Data]
0x18005c946  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x18005c94b  xor     r8d, r8d; Reserved
0x18005c94e  lea     rdx, aDestructiveres; "DestructiveResetInProgress"
0x18005c955  mov     rcx, [rbp+57h+hKey]; hKey
0x18005c959  call    cs:__imp_RegSetValueExW
0x18005c960  nop     dword ptr [rax+rax+00h]
0x18005c965  test    eax, eax
0x18005c967  jz      short loc_18005C970
0x18005c969  mov     edx, 266h
0x18005c96e  jmp     short loc_18005C910
0x18005c970  lea     rcx, [rbp+57h+hKey]
0x18005c974  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005c979  xor     ebx, ebx
0x18005c97b  lea     rcx, [rbp+57h+lpSubKey]
0x18005c97f  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005c984  mov     eax, ebx
0x18005c986  mov     rcx, [rbp+57h+var_10]
0x18005c98a  xor     rcx, rsp; StackCookie
0x18005c98d  call    __security_check_cookie
0x18005c992  mov     rbx, [rsp+90h+arg_8]
0x18005c99a  add     rsp, 90h
0x18005c9a1  pop     rbp
0x18005c9a2  retn
```
