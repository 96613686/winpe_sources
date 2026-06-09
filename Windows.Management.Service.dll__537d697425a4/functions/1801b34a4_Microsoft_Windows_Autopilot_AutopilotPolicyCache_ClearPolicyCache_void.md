# Microsoft::Windows::Autopilot::AutopilotPolicyCache::ClearPolicyCache(void)

- ea: `0x1801b34a4`
- end: `0x1801b35d7`
- name: `?ClearPolicyCache@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `307`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801958a0`

## callees

- `0x180067e54`
- `0x180080984`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1801b34a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801b3571`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801b3571`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801b3515`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801b3515`

## string_xrefs

- `0x1801b352a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1801b35a7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1801b34da`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x1801b34d1`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x1801b3542`: `PolicyJsonCache`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::AutopilotPolicyCache::ClearPolicyCache(void)
{
  bool v0; // al
  const WCHAR *v1; // rdx
  unsigned int v2; // eax
  unsigned int v3; // ebx
  LPCWSTR *v4; // rdi
  LSTATUS v5; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  _QWORD v8[2]; // [rsp+50h] [rbp-18h] BYREF
  char v9; // [rsp+60h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = ZTPIsStateSeparationEnabled();
  v1 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  if ( !v0 )
    v1 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4E,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
           (const char *)v2,
           dwOptions);
  }
  else
  {
    v8[0] = L"PolicyJsonCache";
    v4 = (LPCWSTR *)v8;
    v8[1] = L"ProfileAvailable";
    while ( 1 )
    {
      if ( v4 == (LPCWSTR *)&v9 )
      {
        v3 = 0;
        goto LABEL_15;
      }
      v5 = RegDeleteValueW(hKey, *v4);
      v3 = v5;
      if ( (v5 & 0xFFFFFFFC) != 0 || v5 == 1 )
        break;
      ++v4;
    }
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v3,
        dwOptions);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x1801b34a4  mov     [rsp+arg_8], rbx
0x1801b34a9  push    rdi
0x1801b34aa  sub     rsp, 60h
0x1801b34ae  xor     edx, edx
0x1801b34b0  mov     [rsp+68h+hKey], 0
0x1801b34b9  lea     rcx, [rsp+68h+hKey]
0x1801b34be  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801b34c3  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801b34c8  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1801b34d1  lea     rcx, aSoftwareMicros_17; "Software\\Microsoft\\Provisioning\\Auto"...
0x1801b34d8  test    al, al
0x1801b34da  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x1801b34e1  lea     rax, [rsp+68h+hKey]
0x1801b34e6  mov     [rsp+68h+phkResult], rax; phkResult
0x1801b34eb  cmovz   rdx, rcx; lpSubKey
0x1801b34ef  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801b34f8  xor     r9d, r9d; lpClass
0x1801b34fb  mov     [rsp+68h+samDesired], 2; samDesired
0x1801b3503  xor     r8d, r8d; Reserved
0x1801b3506  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801b350d  mov     [rsp+68h+dwOptions], 0; int
0x1801b3515  call    cs:__imp_RegCreateKeyExW
0x1801b351c  nop     dword ptr [rax+rax+00h]
0x1801b3521  test    eax, eax
0x1801b3523  jz      short loc_1801B3542
0x1801b3525  mov     rcx, [rsp+68h]; this
0x1801b352a  lea     r8, aOnecoreuapAdmi_51; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b3531  mov     r9d, eax; char *
0x1801b3534  mov     edx, 4Eh ; 'N'; void *
0x1801b3539  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801b353e  mov     ebx, eax
0x1801b3540  jmp     short loc_1801B35BF
0x1801b3542  lea     rax, aPolicyjsoncach; "PolicyJsonCache"
0x1801b3549  mov     [rsp+68h+var_18], rax
0x1801b354e  lea     rdi, [rsp+68h+var_18]
0x1801b3553  lea     rax, aProfileavailab; "ProfileAvailable"
0x1801b355a  mov     [rsp+68h+var_10], rax
0x1801b355f  lea     rax, [rsp+68h+var_8]
0x1801b3564  cmp     rdi, rax
0x1801b3567  jz      short loc_1801B35BD
0x1801b3569  mov     rdx, [rdi]; lpValueName
0x1801b356c  mov     rcx, [rsp+68h+hKey]; hKey
0x1801b3571  call    cs:__imp_RegDeleteValueW
0x1801b3578  nop     dword ptr [rax+rax+00h]
0x1801b357d  mov     ebx, eax
0x1801b357f  test    eax, 0FFFFFFFCh
0x1801b3584  jnz     short loc_1801B3591
0x1801b3586  cmp     eax, 1
0x1801b3589  jz      short loc_1801B3591
0x1801b358b  add     rdi, 8
0x1801b358f  jmp     short loc_1801B355F
0x1801b3591  test    eax, eax
0x1801b3593  jle     short loc_1801B359E
0x1801b3595  movzx   ebx, ax
0x1801b3598  or      ebx, 80070000h
0x1801b359e  test    ebx, ebx
0x1801b35a0  jns     short loc_1801B35BF
0x1801b35a2  mov     rcx, [rsp+68h]; this
0x1801b35a7  lea     r8, aOnecoreuapAdmi_51; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b35ae  mov     r9d, ebx; char *
0x1801b35b1  mov     edx, 5Bh ; '['; void *
0x1801b35b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b35bb  jmp     short loc_1801B35BF
0x1801b35bd  xor     ebx, ebx
0x1801b35bf  lea     rcx, [rsp+68h+hKey]
0x1801b35c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801b35c9  mov     eax, ebx
0x1801b35cb  mov     rbx, [rsp+68h+arg_8]
0x1801b35d0  add     rsp, 60h
0x1801b35d4  pop     rdi
0x1801b35d5  retn
```
