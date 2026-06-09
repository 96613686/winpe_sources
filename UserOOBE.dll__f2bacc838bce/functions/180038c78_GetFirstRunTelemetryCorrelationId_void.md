# GetFirstRunTelemetryCorrelationId(void)

- ea: `0x180038c78`
- end: `0x180038d61`
- name: `?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ`
- size: `233`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038f8c`

## callees

- `0x1800032b0`
- `0x180018c98`
- `0x18001f168`
- `0x180038c78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038d12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038d12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038cd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038cd6`

## pseudocode

```c
struct _GUID *__fastcall GetFirstRunTelemetryCorrelationId(struct _GUID *__return_ptr retstr)
{
  struct _GUID v2; // xmm6
  LSTATUS v3; // eax
  bool v4; // sf
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-38h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-34h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-30h] BYREF

  hKey = 0;
  v2 = 0;
  *(_OWORD *)Data = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TelemetryCorrelation",
         0,
         0x20019u,
         &hKey) < 0 )
    goto LABEL_6;
  Type = 3;
  cbData = 16;
  v3 = RegQueryValueExW(hKey, L"FirstRunCorrelationID", 0, &Type, Data, &cbData);
  v4 = v3 < 0;
  if ( v3 > 0 )
    v4 = 1;
  if ( v4 )
    *(_OWORD *)Data = 0;
  else
LABEL_6:
    v2 = *(struct _GUID *)Data;
  *retstr = v2;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return retstr;
}

```

## disassembly

```asm
0x180038c78  mov     [rsp-8+arg_0], rbx
0x180038c7d  push    rbp
0x180038c7e  mov     rbp, rsp
0x180038c81  sub     rsp, 70h
0x180038c85  movaps  [rsp+70h+var_10], xmm6
0x180038c8a  mov     rax, cs:__security_cookie
0x180038c91  xor     rax, rsp
0x180038c94  mov     [rbp+var_20], rax
0x180038c98  mov     rbx, rcx
0x180038c9b  mov     [rbp+hKey], 0
0x180038ca3  xorps   xmm6, xmm6
0x180038ca6  lea     rcx, [rbp+hKey]
0x180038caa  xor     edx, edx
0x180038cac  movdqa  xmmword ptr [rbp+Data], xmm6
0x180038cb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038cb6  lea     rax, [rbp+hKey]
0x180038cba  mov     r9d, 20019h; samDesired
0x180038cc0  xor     r8d, r8d; ulOptions
0x180038cc3  mov     [rsp+70h+phkResult], rax; phkResult
0x180038cc8  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180038ccf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038cd6  call    cs:__imp_RegOpenKeyExW
0x180038cdc  test    eax, eax
0x180038cde  js      short loc_180038D2E
0x180038ce0  mov     rcx, [rbp+hKey]; hKey
0x180038ce4  lea     rax, [rbp+cbData]
0x180038ce8  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180038ced  lea     r9, [rbp+Type]; lpType
0x180038cf1  lea     rax, [rbp+Data]
0x180038cf5  mov     [rbp+Type], 3
0x180038cfc  xor     r8d, r8d; lpReserved
0x180038cff  mov     [rsp+70h+phkResult], rax; lpData
0x180038d04  lea     rdx, aFirstruncorrel; "FirstRunCorrelationID"
0x180038d0b  mov     [rbp+cbData], 10h
0x180038d12  call    cs:__imp_RegQueryValueExW
0x180038d18  test    eax, eax
0x180038d1a  jle     short loc_180038D26
0x180038d1c  movzx   eax, ax
0x180038d1f  or      eax, 80070000h
0x180038d24  test    eax, eax
0x180038d26  jns     short loc_180038D2E
0x180038d28  movaps  xmmword ptr [rbp+Data], xmm6
0x180038d2c  jmp     short loc_180038D32
0x180038d2e  movaps  xmm6, xmmword ptr [rbp+Data]
0x180038d32  lea     rcx, [rbp+hKey]
0x180038d36  movdqu  xmmword ptr [rbx], xmm6
0x180038d3a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038d3f  mov     rax, rbx
0x180038d42  mov     rcx, [rbp+var_20]
0x180038d46  xor     rcx, rsp; StackCookie
0x180038d49  call    __security_check_cookie
0x180038d4e  mov     rbx, [rsp+70h+arg_0]
0x180038d56  movaps  xmm6, [rsp+70h+var_10]
0x180038d5b  add     rsp, 70h
0x180038d5f  pop     rbp
0x180038d60  retn
```
