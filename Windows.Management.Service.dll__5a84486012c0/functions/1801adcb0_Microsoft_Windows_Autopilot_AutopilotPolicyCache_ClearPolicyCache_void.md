# Microsoft::Windows::Autopilot::AutopilotPolicyCache::ClearPolicyCache(void)

- ea: `0x1801adcb0`
- end: `0x1801addd6`
- name: `?ClearPolicyCache@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801908d4`

## callees

- `0x180067a54`
- `0x18007ff90`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1801adcb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801add77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801add77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801add21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801add21`

## string_xrefs

- `0x1801adce6`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x1801adcdd`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x1801add48`: `PolicyJsonCache`
- `0x1801add30`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1801adda7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

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
0x1801adcb0  mov     [rsp+arg_8], rbx
0x1801adcb5  push    rdi
0x1801adcb6  sub     rsp, 60h
0x1801adcba  xor     edx, edx
0x1801adcbc  mov     [rsp+68h+hKey], 0
0x1801adcc5  lea     rcx, [rsp+68h+hKey]
0x1801adcca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801adccf  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801adcd4  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1801adcdd  lea     rcx, aSoftwareMicros_17; "Software\\Microsoft\\Provisioning\\Auto"...
0x1801adce4  test    al, al
0x1801adce6  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x1801adced  lea     rax, [rsp+68h+hKey]
0x1801adcf2  mov     [rsp+68h+phkResult], rax; phkResult
0x1801adcf7  cmovz   rdx, rcx; lpSubKey
0x1801adcfb  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801add04  xor     r9d, r9d; lpClass
0x1801add07  mov     [rsp+68h+samDesired], 2; samDesired
0x1801add0f  xor     r8d, r8d; Reserved
0x1801add12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801add19  mov     [rsp+68h+dwOptions], 0; int
0x1801add21  call    cs:__imp_RegCreateKeyExW
0x1801add27  test    eax, eax
0x1801add29  jz      short loc_1801ADD48
0x1801add2b  mov     rcx, [rsp+68h]; this
0x1801add30  lea     r8, aOnecoreuapAdmi_51; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801add37  mov     r9d, eax; char *
0x1801add3a  mov     edx, 4Eh ; 'N'; void *
0x1801add3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801add44  mov     ebx, eax
0x1801add46  jmp     short loc_1801ADDBF
0x1801add48  lea     rax, aPolicyjsoncach; "PolicyJsonCache"
0x1801add4f  mov     [rsp+68h+var_18], rax
0x1801add54  lea     rdi, [rsp+68h+var_18]
0x1801add59  lea     rax, aProfileavailab; "ProfileAvailable"
0x1801add60  mov     [rsp+68h+var_10], rax
0x1801add65  lea     rax, [rsp+68h+var_8]
0x1801add6a  cmp     rdi, rax
0x1801add6d  jz      short loc_1801ADDBD
0x1801add6f  mov     rdx, [rdi]; lpValueName
0x1801add72  mov     rcx, [rsp+68h+hKey]; hKey
0x1801add77  call    cs:__imp_RegDeleteValueW
0x1801add7d  mov     ebx, eax
0x1801add7f  test    eax, 0FFFFFFFCh
0x1801add84  jnz     short loc_1801ADD91
0x1801add86  cmp     eax, 1
0x1801add89  jz      short loc_1801ADD91
0x1801add8b  add     rdi, 8
0x1801add8f  jmp     short loc_1801ADD65
0x1801add91  test    eax, eax
0x1801add93  jle     short loc_1801ADD9E
0x1801add95  movzx   ebx, ax
0x1801add98  or      ebx, 80070000h
0x1801add9e  test    ebx, ebx
0x1801adda0  jns     short loc_1801ADDBF
0x1801adda2  mov     rcx, [rsp+68h]; this
0x1801adda7  lea     r8, aOnecoreuapAdmi_51; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801addae  mov     r9d, ebx; char *
0x1801addb1  mov     edx, 5Bh ; '['; void *
0x1801addb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801addbb  jmp     short loc_1801ADDBF
0x1801addbd  xor     ebx, ebx
0x1801addbf  lea     rcx, [rsp+68h+hKey]
0x1801addc4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801addc9  mov     eax, ebx
0x1801addcb  mov     rbx, [rsp+68h+arg_8]
0x1801addd0  add     rsp, 60h
0x1801addd4  pop     rdi
0x1801addd5  retn
```
