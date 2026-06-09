# SetOobeTimeoutOverrides

- ea: `0x180034284`
- end: `0x1800343dd`
- name: `SetOobeTimeoutOverrides`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026894`

## callees

- `0x180004eb0`
- `0x180016698`
- `0x180017118`
- `0x180034284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003436b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003436b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003439d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003439d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800342f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800342f6`

## string_xrefs

- `0x180034336`: `EventTimeoutShellReady`

## pseudocode

```c
__int64 SetOobeTimeoutOverrides()
{
  LPCWSTR *v0; // rbx
  HKEY hkey; // [rsp+50h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp+1Fh] BYREF
  _QWORD v4[4]; // [rsp+60h] [rbp+27h] BYREF
  __int64 v5; // [rsp+80h] [rbp+47h] BYREF

  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          0,
          0,
          0,
          3u,
          0,
          &hkey,
          0) )
  {
    *(_DWORD *)Data = 1800;
    v4[0] = L"EventTimeoutTimeoutEventInitial";
    v0 = (LPCWSTR *)v4;
    v4[1] = L"EventTimeoutUserSignIn";
    v4[2] = L"EventTimeoutLogonFrameworkStart";
    v4[3] = L"EventTimeoutShellReady";
    do
    {
      if ( RegGetValueW(hkey, 0, *v0, 0x18u, 0, 0, 0) == 2 )
        RegSetValueExW(hkey, *v0, 0, 4u, Data, 4u);
      ++v0;
    }
    while ( v0 != (LPCWSTR *)&v5 );
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
}

```

## disassembly

```asm
0x180034284  mov     [rsp-8+arg_0], rbx
0x180034289  push    rbp
0x18003428a  lea     rbp, [rsp-57h]
0x18003428f  sub     rsp, 90h
0x180034296  mov     rax, cs:__security_cookie
0x18003429d  xor     rax, rsp
0x1800342a0  mov     [rbp+57h+var_10], rax
0x1800342a4  xor     edx, edx
0x1800342a6  mov     [rbp+57h+hkey], 0
0x1800342ae  lea     rcx, [rbp+57h+hkey]
0x1800342b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800342b7  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800342c0  lea     rax, [rbp+57h+hkey]
0x1800342c4  mov     [rsp+90h+phkResult], rax; phkResult
0x1800342c9  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800342d0  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800342d9  xor     r9d, r9d; lpClass
0x1800342dc  mov     [rsp+90h+samDesired], 3; samDesired
0x1800342e4  xor     r8d, r8d; Reserved
0x1800342e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800342ee  mov     [rsp+90h+dwOptions], 0; dwOptions
0x1800342f6  call    cs:__imp_RegCreateKeyExW
0x1800342fd  nop     dword ptr [rax+rax+00h]
0x180034302  test    eax, eax
0x180034304  jnz     loc_1800343B6
0x18003430a  lea     rax, aEventtimeoutti; "EventTimeoutTimeoutEventInitial"
0x180034311  mov     dword ptr [rbp+57h+Data], 708h
0x180034318  mov     [rbp+57h+var_30], rax
0x18003431c  lea     rbx, [rbp+57h+var_30]
0x180034320  lea     rax, aEventtimeoutus; "EventTimeoutUserSignIn"
0x180034327  mov     [rbp+57h+var_28], rax
0x18003432b  lea     rax, aEventtimeoutlo; "EventTimeoutLogonFrameworkStart"
0x180034332  mov     [rbp+57h+var_20], rax
0x180034336  lea     rax, aEventtimeoutsh; "EventTimeoutShellReady"
0x18003433d  mov     [rbp+57h+var_18], rax
0x180034341  mov     r8, [rbx]; lpValue
0x180034344  mov     r9d, 18h; dwFlags
0x18003434a  mov     rcx, [rbp+57h+hkey]; hkey
0x18003434e  xor     edx, edx; lpSubKey
0x180034350  mov     [rsp+90h+lpSecurityAttributes], 0; pcbData
0x180034359  mov     qword ptr [rsp+90h+samDesired], 0; pvData
0x180034362  mov     qword ptr [rsp+90h+dwOptions], 0; pdwType
0x18003436b  call    cs:__imp_RegGetValueW
0x180034372  nop     dword ptr [rax+rax+00h]
0x180034377  cmp     eax, 2
0x18003437a  jnz     short loc_1800343A9
0x18003437c  mov     rdx, [rbx]; lpValueName
0x18003437f  lea     rax, [rbp+57h+Data]
0x180034383  mov     rcx, [rbp+57h+hkey]; hKey
0x180034387  mov     r9d, 4; dwType
0x18003438d  mov     [rsp+90h+samDesired], 4; cbData
0x180034395  xor     r8d, r8d; Reserved
0x180034398  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x18003439d  call    cs:__imp_RegSetValueExW
0x1800343a4  nop     dword ptr [rax+rax+00h]
0x1800343a9  add     rbx, 8
0x1800343ad  lea     rax, [rbp+57h+var_10]
0x1800343b1  cmp     rbx, rax
0x1800343b4  jnz     short loc_180034341
0x1800343b6  lea     rcx, [rbp+57h+hkey]
0x1800343ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800343bf  mov     rcx, [rbp+57h+var_10]
0x1800343c3  xor     rcx, rsp; StackCookie
0x1800343c6  call    __security_check_cookie
0x1800343cb  mov     rbx, [rsp+90h+arg_0]
0x1800343d3  add     rsp, 90h
0x1800343da  pop     rbp
0x1800343db  retn
```
