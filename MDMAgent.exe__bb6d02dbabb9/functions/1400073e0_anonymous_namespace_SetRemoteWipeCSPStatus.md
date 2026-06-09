# _anonymous_namespace_::SetRemoteWipeCSPStatus

- ea: `0x1400073e0`
- end: `0x1400074e4`
- name: `_anonymous_namespace_::SetRemoteWipeCSPStatus`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x140004b94`
- `0x140006c1c`
- `0x1400073e0`
- `0x140007e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007437`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007437`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007492`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007492`

## string_xrefs

- `0x14000744f`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x1400074aa`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 anonymous_namespace_::SetRemoteWipeCSPStatus()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  int Data[6]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  Data[0] = 1;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Provisioning\\Diagnostics\\RemoteWipe",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v0 )
  {
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x69,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
           (const char *)v0,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v1;
  }
  else
  {
    v3 = RegSetValueExW(hKey, L"Status", 0, 4u, (const BYTE *)Data, 4u);
    if ( v3 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x71,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
             (const char *)v3,
             dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v4;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1400073e0  mov     rax, rsp
0x1400073e3  mov     [rax+8], ecx
0x1400073e6  push    rbx
0x1400073e7  sub     rsp, 60h
0x1400073eb  mov     dword ptr [rax-18h], 1
0x1400073f2  xor     ebx, ebx
0x1400073f4  mov     [rax+10h], rbx
0x1400073f8  xor     edx, edx
0x1400073fa  lea     rcx, [rax+10h]
0x1400073fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140007403  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x140007408  lea     rax, [rsp+68h+hKey]
0x14000740d  mov     [rsp+68h+phkResult], rax; phkResult
0x140007412  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x140007417  mov     [rsp+68h+samDesired], 20006h; samDesired
0x14000741f  mov     [rsp+68h+dwOptions], ebx; unsigned int
0x140007423  xor     r9d, r9d; lpClass
0x140007426  xor     r8d, r8d; Reserved
0x140007429  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Diag"...
0x140007430  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007437  call    cs:__imp_RegCreateKeyExW
0x14000743e  nop     dword ptr [rax+rax+00h]
0x140007443  test    eax, eax
0x140007445  jz      short loc_14000746E
0x140007447  mov     rcx, [rsp+68h]; this
0x14000744c  mov     r9d, eax; char *
0x14000744f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140007456  lea     edx, [rbx+69h]; void *
0x140007459  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000745e  mov     ebx, eax
0x140007460  lea     rcx, [rsp+68h+hKey]
0x140007465  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000746a  mov     eax, ebx
0x14000746c  jmp     short loc_1400074DD
0x14000746e  mov     r9d, 4; dwType
0x140007474  mov     [rsp+68h+samDesired], r9d; cbData
0x140007479  lea     rax, [rsp+68h+Data]
0x14000747e  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x140007483  xor     r8d, r8d; Reserved
0x140007486  lea     rdx, aStatus; "Status"
0x14000748d  mov     rcx, [rsp+68h+hKey]; hKey
0x140007492  call    cs:__imp_RegSetValueExW
0x140007499  nop     dword ptr [rax+rax+00h]
0x14000749e  test    eax, eax
0x1400074a0  jz      short loc_1400074CB
0x1400074a2  mov     rcx, [rsp+68h]; this
0x1400074a7  mov     r9d, eax; char *
0x1400074aa  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400074b1  mov     edx, 71h ; 'q'; void *
0x1400074b6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400074bb  mov     ebx, eax
0x1400074bd  lea     rcx, [rsp+68h+hKey]
0x1400074c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400074c7  mov     eax, ebx
0x1400074c9  jmp     short loc_1400074DD
0x1400074cb  lea     rcx, [rsp+68h+hKey]
0x1400074d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400074d5  xor     eax, eax
0x1400074d7  jmp     short loc_1400074DD
0x1400074d9  mov     eax, [rsp+68h+arg_0]
0x1400074dd  add     rsp, 60h
0x1400074e1  pop     rbx
0x1400074e2  retn
```
