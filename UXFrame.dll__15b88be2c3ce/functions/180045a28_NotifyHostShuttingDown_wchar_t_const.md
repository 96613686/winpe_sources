# NotifyHostShuttingDown(wchar_t const *)

- ea: `0x180045a28`
- end: `0x180045aa9`
- name: `?NotifyHostShuttingDown@@YA_NPEB_W@Z`
- size: `129`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004c970`
- `0x18004d0b8`

## callees

- `0x180002b20`
- `0x18000e224`
- `0x1800438c4`
- `0x180045a28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045a7f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045a7f`

## pseudocode

```c
bool __fastcall NotifyHostShuttingDown(const wchar_t *a1)
{
  bool v1; // bl
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+38h] [rbp-20h] BYREF

  Data = 1;
  v1 = 0;
  hKey = 0;
  GetHostSessionSubKey(&hKey, a1);
  if ( hKey )
    v1 = RegSetKeyValueW(hKey, 0, L"IsShuttingDown", 4u, &Data, 4u) == 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x180045a28  push    rbx
0x180045a2a  sub     rsp, 50h
0x180045a2e  mov     rax, cs:__security_cookie
0x180045a35  xor     rax, rsp
0x180045a38  mov     [rsp+58h+var_18], rax
0x180045a3d  mov     rdx, rcx
0x180045a40  mov     [rsp+58h+Data], 1
0x180045a48  xor     ebx, ebx
0x180045a4a  lea     rcx, [rsp+58h+hKey]
0x180045a4f  mov     [rsp+58h+hKey], rbx
0x180045a54  call    ?GetHostSessionSubKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WK@Z; GetHostSessionSubKey(wchar_t const *,ulong)
0x180045a59  mov     rcx, [rsp+58h+hKey]; hKey
0x180045a5e  test    rcx, rcx
0x180045a61  jz      short loc_180045A8A
0x180045a63  lea     r9d, [rbx+4]; dwType
0x180045a67  xor     edx, edx; lpSubKey
0x180045a69  lea     rax, [rsp+58h+Data]
0x180045a6e  mov     [rsp+58h+cbData], r9d; cbData
0x180045a73  lea     r8, aIsshuttingdown; "IsShuttingDown"
0x180045a7a  mov     [rsp+58h+lpData], rax; lpData
0x180045a7f  call    cs:__imp_RegSetKeyValueW
0x180045a85  test    eax, eax
0x180045a87  setz    bl
0x180045a8a  lea     rcx, [rsp+58h+hKey]
0x180045a8f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180045a94  mov     al, bl
0x180045a96  mov     rcx, [rsp+58h+var_18]
0x180045a9b  xor     rcx, rsp; StackCookie
0x180045a9e  call    __security_check_cookie
0x180045aa3  add     rsp, 50h
0x180045aa7  pop     rbx
0x180045aa8  retn
```
