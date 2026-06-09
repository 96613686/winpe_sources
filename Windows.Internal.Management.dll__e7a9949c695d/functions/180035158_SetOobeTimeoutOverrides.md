# SetOobeTimeoutOverrides

- ea: `0x180035158`
- end: `0x18003529e`
- name: `SetOobeTimeoutOverrides`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028068`

## callees

- `0x180004d50`
- `0x180015f70`
- `0x1800169b8`
- `0x180035158`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035239`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035239`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035265`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035265`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351ca`

## string_xrefs

- `0x180035204`: `EventTimeoutShellReady`

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
0x180035158  mov     [rsp-8+arg_0], rbx
0x18003515d  push    rbp
0x18003515e  lea     rbp, [rsp-57h]
0x180035163  sub     rsp, 90h
0x18003516a  mov     rax, cs:__security_cookie
0x180035171  xor     rax, rsp
0x180035174  mov     [rbp+57h+var_10], rax
0x180035178  xor     edx, edx
0x18003517a  mov     [rbp+57h+hkey], 0
0x180035182  lea     rcx, [rbp+57h+hkey]
0x180035186  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003518b  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x180035194  lea     rax, [rbp+57h+hkey]
0x180035198  mov     [rsp+90h+phkResult], rax; phkResult
0x18003519d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800351a4  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800351ad  xor     r9d, r9d; lpClass
0x1800351b0  mov     [rsp+90h+samDesired], 3; samDesired
0x1800351b8  xor     r8d, r8d; Reserved
0x1800351bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800351c2  mov     [rsp+90h+dwOptions], 0; dwOptions
0x1800351ca  call    cs:__imp_RegCreateKeyExW
0x1800351d0  test    eax, eax
0x1800351d2  jnz     loc_180035278
0x1800351d8  lea     rax, aEventtimeoutti; "EventTimeoutTimeoutEventInitial"
0x1800351df  mov     dword ptr [rbp+57h+Data], 708h
0x1800351e6  mov     [rbp+57h+var_30], rax
0x1800351ea  lea     rbx, [rbp+57h+var_30]
0x1800351ee  lea     rax, aEventtimeoutus; "EventTimeoutUserSignIn"
0x1800351f5  mov     [rbp+57h+var_28], rax
0x1800351f9  lea     rax, aEventtimeoutlo; "EventTimeoutLogonFrameworkStart"
0x180035200  mov     [rbp+57h+var_20], rax
0x180035204  lea     rax, aEventtimeoutsh; "EventTimeoutShellReady"
0x18003520b  mov     [rbp+57h+var_18], rax
0x18003520f  mov     r8, [rbx]; lpValue
0x180035212  mov     r9d, 18h; dwFlags
0x180035218  mov     rcx, [rbp+57h+hkey]; hkey
0x18003521c  xor     edx, edx; lpSubKey
0x18003521e  mov     [rsp+90h+lpSecurityAttributes], 0; pcbData
0x180035227  mov     qword ptr [rsp+90h+samDesired], 0; pvData
0x180035230  mov     qword ptr [rsp+90h+dwOptions], 0; pdwType
0x180035239  call    cs:__imp_RegGetValueW
0x18003523f  cmp     eax, 2
0x180035242  jnz     short loc_18003526B
0x180035244  mov     rdx, [rbx]; lpValueName
0x180035247  lea     rax, [rbp+57h+Data]
0x18003524b  mov     rcx, [rbp+57h+hkey]; hKey
0x18003524f  mov     r9d, 4; dwType
0x180035255  mov     [rsp+90h+samDesired], 4; cbData
0x18003525d  xor     r8d, r8d; Reserved
0x180035260  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x180035265  call    cs:__imp_RegSetValueExW
0x18003526b  add     rbx, 8
0x18003526f  lea     rax, [rbp+57h+var_10]
0x180035273  cmp     rbx, rax
0x180035276  jnz     short loc_18003520F
0x180035278  lea     rcx, [rbp+57h+hkey]
0x18003527c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180035281  mov     rcx, [rbp+57h+var_10]
0x180035285  xor     rcx, rsp; StackCookie
0x180035288  call    __security_check_cookie
0x18003528d  mov     rbx, [rsp+90h+arg_0]
0x180035295  add     rsp, 90h
0x18003529c  pop     rbp
0x18003529d  retn
```
