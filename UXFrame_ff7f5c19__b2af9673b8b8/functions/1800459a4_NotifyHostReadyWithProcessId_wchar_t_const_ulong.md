# NotifyHostReadyWithProcessId(wchar_t const *,ulong)

- ea: `0x1800459a4`
- end: `0x180045a21`
- name: `?NotifyHostReadyWithProcessId@@YA_NPEB_WK@Z`
- size: `125`
- prototype: `bool __fastcall(const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180045dd0`

## callees

- `0x180002b20`
- `0x18000e224`
- `0x1800438c4`
- `0x1800459a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800459f7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800459f7`

## string_xrefs

- `0x1800459eb`: `ProcessId`

## pseudocode

```c
bool __fastcall NotifyHostReadyWithProcessId(const wchar_t *a1, int a2)
{
  bool v2; // bl
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+38h] [rbp-20h] BYREF

  Data = a2;
  v2 = 0;
  hKey = 0;
  GetHostSessionSubKey(&hKey, a1);
  if ( hKey )
    v2 = RegSetKeyValueW(hKey, 0, L"ProcessId", 4u, &Data, 4u) == 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x1800459a4  push    rbx
0x1800459a6  sub     rsp, 50h
0x1800459aa  mov     rax, cs:__security_cookie
0x1800459b1  xor     rax, rsp
0x1800459b4  mov     [rsp+58h+var_18], rax
0x1800459b9  mov     [rsp+58h+Data], edx
0x1800459bd  xor     ebx, ebx
0x1800459bf  mov     rdx, rcx
0x1800459c2  mov     [rsp+58h+hKey], rbx
0x1800459c7  lea     rcx, [rsp+58h+hKey]
0x1800459cc  call    ?GetHostSessionSubKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WK@Z; GetHostSessionSubKey(wchar_t const *,ulong)
0x1800459d1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800459d6  test    rcx, rcx
0x1800459d9  jz      short loc_180045A02
0x1800459db  lea     r9d, [rbx+4]; dwType
0x1800459df  xor     edx, edx; lpSubKey
0x1800459e1  lea     rax, [rsp+58h+Data]
0x1800459e6  mov     [rsp+58h+cbData], r9d; cbData
0x1800459eb  lea     r8, aProcessid; "ProcessId"
0x1800459f2  mov     [rsp+58h+lpData], rax; lpData
0x1800459f7  call    cs:__imp_RegSetKeyValueW
0x1800459fd  test    eax, eax
0x1800459ff  setz    bl
0x180045a02  lea     rcx, [rsp+58h+hKey]
0x180045a07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180045a0c  mov     al, bl
0x180045a0e  mov     rcx, [rsp+58h+var_18]
0x180045a13  xor     rcx, rsp; StackCookie
0x180045a16  call    __security_check_cookie
0x180045a1b  add     rsp, 50h
0x180045a1f  pop     rbx
0x180045a20  retn
```
