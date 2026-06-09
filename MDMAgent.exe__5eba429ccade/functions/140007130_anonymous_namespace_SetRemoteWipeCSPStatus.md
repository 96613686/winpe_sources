# _anonymous_namespace_::SetRemoteWipeCSPStatus

- ea: `0x140007130`
- end: `0x140007228`
- name: `_anonymous_namespace_::SetRemoteWipeCSPStatus`
- size: `248`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140004b0c`
- `0x1400069a8`
- `0x140007130`
- `0x140007b34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007187`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007187`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400071dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400071dc`

## string_xrefs

- `0x140007199`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x1400071ee`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

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
0x140007130  mov     rax, rsp
0x140007133  mov     [rax+8], ecx
0x140007136  push    rbx
0x140007137  sub     rsp, 60h
0x14000713b  mov     dword ptr [rax-18h], 1
0x140007142  xor     ebx, ebx
0x140007144  mov     [rax+10h], rbx
0x140007148  xor     edx, edx
0x14000714a  lea     rcx, [rax+10h]
0x14000714e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140007153  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x140007158  lea     rax, [rsp+68h+hKey]
0x14000715d  mov     [rsp+68h+phkResult], rax; phkResult
0x140007162  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x140007167  mov     [rsp+68h+samDesired], 20006h; samDesired
0x14000716f  mov     [rsp+68h+dwOptions], ebx; unsigned int
0x140007173  xor     r9d, r9d; lpClass
0x140007176  xor     r8d, r8d; Reserved
0x140007179  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Diag"...
0x140007180  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007187  call    cs:__imp_RegCreateKeyExW
0x14000718d  test    eax, eax
0x14000718f  jz      short loc_1400071B8
0x140007191  mov     rcx, [rsp+68h]; this
0x140007196  mov     r9d, eax; char *
0x140007199  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400071a0  lea     edx, [rbx+69h]; void *
0x1400071a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400071a8  mov     ebx, eax
0x1400071aa  lea     rcx, [rsp+68h+hKey]
0x1400071af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400071b4  mov     eax, ebx
0x1400071b6  jmp     short loc_140007221
0x1400071b8  mov     r9d, 4; dwType
0x1400071be  mov     [rsp+68h+samDesired], r9d; cbData
0x1400071c3  lea     rax, [rsp+68h+Data]
0x1400071c8  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x1400071cd  xor     r8d, r8d; Reserved
0x1400071d0  lea     rdx, aStatus; "Status"
0x1400071d7  mov     rcx, [rsp+68h+hKey]; hKey
0x1400071dc  call    cs:__imp_RegSetValueExW
0x1400071e2  test    eax, eax
0x1400071e4  jz      short loc_14000720F
0x1400071e6  mov     rcx, [rsp+68h]; this
0x1400071eb  mov     r9d, eax; char *
0x1400071ee  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400071f5  mov     edx, 71h ; 'q'; void *
0x1400071fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400071ff  mov     ebx, eax
0x140007201  lea     rcx, [rsp+68h+hKey]
0x140007206  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000720b  mov     eax, ebx
0x14000720d  jmp     short loc_140007221
0x14000720f  lea     rcx, [rsp+68h+hKey]
0x140007214  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140007219  xor     eax, eax
0x14000721b  jmp     short loc_140007221
0x14000721d  mov     eax, [rsp+68h+arg_0]
0x140007221  add     rsp, 60h
0x140007225  pop     rbx
0x140007226  retn
```
