# DeclaredConfigurationStore_SetDriftControlDword(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800aacf8`
- end: `0x1800aaeda`
- name: `?DeclaredConfigurationStore_SetDriftControlDword@@YAJPEBG00K@Z`
- size: `482`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ab0d0`
- `0x1800ab7c0`
- `0x1800abb60`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x1800aacf8`
- `0x1800abdf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aae80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aae80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aae3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aae3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aadd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aadd6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800aad6f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800aad6f`

## string_xrefs

- `0x1800aad57`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800aad7c`: `OSData\Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`
- `0x1800aad75`: `Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeclaredConfigurationStore_SetDriftControlDword(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  signed int updated; // ebx
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v10; // r8
  int v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *(_DWORD *)Data = a4;
  hKey = 0;
  if ( !a1 )
  {
    updated = -2147024809;
    v7 = 149;
LABEL_5:
    v8 = (unsigned int)updated;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
      (const char *)v8,
      phkResult);
    goto LABEL_23;
  }
  if ( a2 )
  {
    updated = -2147024846;
    v7 = 153;
    goto LABEL_5;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v10 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
  if ( !IsStateSeparationEnabled )
    v10 = L"Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
  v11 = StringCchPrintfW(SubKey, 0x104u, v10, a1);
  updated = v11;
  if ( v11 < 0 )
  {
    v8 = (unsigned int)v11;
    v7 = 158;
    goto LABEL_6;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
  updated = v12;
  if ( v12 > 0 )
    updated = (unsigned __int16)v12 | 0x80070000;
  if ( updated == -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2011Fu, 0, &hKey, 0);
    updated = v13;
    if ( v13 > 0 )
      updated = (unsigned __int16)v13 | 0x80070000;
  }
  if ( updated < 0 )
  {
    v7 = 181;
    goto LABEL_5;
  }
  v14 = RegSetValueExW(hKey, a3, 0, 4u, Data, 4u);
  updated = v14;
  if ( v14 > 0 )
    updated = (unsigned __int16)v14 | 0x80070000;
  if ( updated >= 0 )
  {
    updated = DeclaredConfigurationStore_UpdateRefreshScheduleTask(a1);
    if ( updated == -2147024894 )
      updated = 0;
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800aacf8  mov     [rsp-8+arg_8], rbx
0x1800aacfd  push    rbp
0x1800aacfe  push    rsi
0x1800aacff  push    rdi
0x1800aad00  lea     rbp, [rsp-180h]
0x1800aad08  sub     rsp, 280h
0x1800aad0f  mov     rax, cs:__security_cookie
0x1800aad16  xor     rax, rsp
0x1800aad19  mov     [rbp+190h+var_20], rax
0x1800aad20  mov     rsi, r8
0x1800aad23  mov     rdi, rcx
0x1800aad26  mov     dword ptr [rsp+290h+Data], r9d
0x1800aad2b  mov     [rsp+290h+hKey], 0
0x1800aad34  test    rcx, rcx
0x1800aad37  jnz     short loc_1800AAD45
0x1800aad39  mov     ebx, 80070057h
0x1800aad3e  mov     edx, 95h
0x1800aad43  jmp     short loc_1800AAD54
0x1800aad45  test    rdx, rdx
0x1800aad48  jz      short loc_1800AAD6F
0x1800aad4a  mov     ebx, 80070032h
0x1800aad4f  mov     edx, 99h; void *
0x1800aad54  mov     r9d, ebx; char *
0x1800aad57  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aad5e  mov     rcx, [rbp+198h]; this
0x1800aad65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aad6a  jmp     loc_1800AAEAC
0x1800aad6f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800aad75  lea     rcx, aSoftwareMicros_70; "Software\\Microsoft\\DeclaredConfigurat"...
0x1800aad7c  lea     r8, aOsdataSoftware_58; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x1800aad83  test    al, al
0x1800aad85  cmovz   r8, rcx; unsigned __int16 *
0x1800aad89  mov     r9, rdi
0x1800aad8c  mov     edx, 104h; unsigned __int64
0x1800aad91  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1800aad96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aad9b  mov     ebx, eax
0x1800aad9d  test    eax, eax
0x1800aad9f  jns     short loc_1800AADAB
0x1800aada1  mov     r9d, eax
0x1800aada4  mov     edx, 9Eh
0x1800aada9  jmp     short loc_1800AAD57
0x1800aadab  xor     edx, edx
0x1800aadad  lea     rcx, [rsp+290h+hKey]
0x1800aadb2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800aadb7  lea     rax, [rsp+290h+hKey]
0x1800aadbc  mov     [rsp+290h+phkResult], rax; phkResult
0x1800aadc1  mov     r9d, 2011Fh; samDesired
0x1800aadc7  xor     r8d, r8d; ulOptions
0x1800aadca  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800aadcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aadd6  call    cs:__imp_RegOpenKeyExW
0x1800aaddc  mov     ebx, eax
0x1800aadde  test    eax, eax
0x1800aade0  jle     short loc_1800AADEB
0x1800aade2  movzx   ebx, ax
0x1800aade5  or      ebx, 80070000h
0x1800aadeb  cmp     ebx, 80070002h
0x1800aadf1  jnz     short loc_1800AAE52
0x1800aadf3  xor     edx, edx
0x1800aadf5  lea     rcx, [rsp+290h+hKey]
0x1800aadfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800aadff  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x1800aae08  lea     rax, [rsp+290h+hKey]
0x1800aae0d  mov     [rsp+290h+var_258], rax; phkResult
0x1800aae12  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800aae1b  mov     [rsp+290h+samDesired], 2011Fh; samDesired
0x1800aae23  mov     dword ptr [rsp+290h+phkResult], 0; dwOptions
0x1800aae2b  xor     r9d, r9d; lpClass
0x1800aae2e  xor     r8d, r8d; Reserved
0x1800aae31  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800aae36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aae3d  call    cs:__imp_RegCreateKeyExW
0x1800aae43  mov     ebx, eax
0x1800aae45  test    eax, eax
0x1800aae47  jle     short loc_1800AAE52
0x1800aae49  movzx   ebx, ax
0x1800aae4c  or      ebx, 80070000h
0x1800aae52  test    ebx, ebx
0x1800aae54  jns     short loc_1800AAE60
0x1800aae56  mov     edx, 0B5h
0x1800aae5b  jmp     loc_1800AAD54
0x1800aae60  mov     r9d, 4; dwType
0x1800aae66  mov     [rsp+290h+samDesired], r9d; cbData
0x1800aae6b  lea     rax, [rsp+290h+Data]
0x1800aae70  mov     [rsp+290h+phkResult], rax; lpData
0x1800aae75  xor     r8d, r8d; Reserved
0x1800aae78  mov     rdx, rsi; lpValueName
0x1800aae7b  mov     rcx, [rsp+290h+hKey]; hKey
0x1800aae80  call    cs:__imp_RegSetValueExW
0x1800aae86  mov     ebx, eax
0x1800aae88  test    eax, eax
0x1800aae8a  jle     short loc_1800AAE95
0x1800aae8c  movzx   ebx, ax
0x1800aae8f  or      ebx, 80070000h
0x1800aae95  test    ebx, ebx
0x1800aae97  js      short loc_1800AAEAC
0x1800aae99  mov     rcx, rdi; unsigned __int16 *
0x1800aae9c  call    ?DeclaredConfigurationStore_UpdateRefreshScheduleTask@@YAJPEBG@Z; DeclaredConfigurationStore_UpdateRefreshScheduleTask(ushort const *)
0x1800aaea1  mov     ebx, eax
0x1800aaea3  cmp     eax, 80070002h
0x1800aaea8  jnz     short loc_1800AAEAC
0x1800aaeaa  xor     ebx, ebx
0x1800aaeac  lea     rcx, [rsp+290h+hKey]
0x1800aaeb1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aaeb6  mov     eax, ebx
0x1800aaeb8  mov     rcx, [rbp+190h+var_20]
0x1800aaebf  xor     rcx, rsp; StackCookie
0x1800aaec2  call    __security_check_cookie
0x1800aaec7  mov     rbx, [rsp+290h+arg_8]
0x1800aaecf  add     rsp, 280h
0x1800aaed6  pop     rdi
0x1800aaed7  pop     rsi
0x1800aaed8  pop     rbp
0x1800aaed9  retn
```
