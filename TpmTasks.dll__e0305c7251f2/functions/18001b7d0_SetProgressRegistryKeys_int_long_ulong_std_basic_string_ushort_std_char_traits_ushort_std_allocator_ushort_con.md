# SetProgressRegistryKeys(int,long,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,ulong,ulong)

- ea: `0x18001b7d0`
- end: `0x18001ba0a`
- name: `?SetProgressRegistryKeys@@YAXHJKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KKKK@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x18000e48c`
- `0x180015580`
- `0x18001b7d0`
- `0x180023634`
- `0x1800243e8`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b9da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b9eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b9da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b9eb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b859`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b89c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b8ca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b944`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b96b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b991`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b9c9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b859`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b89c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b8ca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b944`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b96b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b991`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001b9c9`

## string_xrefs

- `0x18001b8bd`: `ConfidenceUpdateType`
- `0x18001b8d4`: `All required keys are updated`
- `0x18001b8e8`: `Updated`
- `0x18001b914`: `Key Rolling updates are in progress, setting UEFICA2023Error to %x UEFICA2023ErrorEvent to %x`
- `0x18001b999`: `Updates NotStarted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall SetProgressRegistryKeys(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9)
{
  int v12; // edi
  _WORD *lpData; // rdx
  __int64 v14; // rbx
  DWORD cbData; // eax
  __int64 v16; // rax
  _WORD *v17; // rax
  DWORD v18; // ebx
  unsigned int Data; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF

  v12 = a1;
  hKey = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(
              a1,
              L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
              &hKey,
              1) >= 0 )
  {
    lpData = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    v14 = -1;
    if ( lpData )
    {
      v16 = -1;
      do
        ++v16;
      while ( lpData[v16] );
      cbData = 2 * v16 + 2;
    }
    else
    {
      cbData = 0;
    }
    RegSetKeyValueW(hKey, 0, L"BucketHash", 1u, lpData, cbData);
    v17 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    if ( v17 )
    {
      do
        ++v14;
      while ( v17[v14] );
      v18 = 2 * v14 + 2;
    }
    else
    {
      v18 = 0;
    }
    RegSetKeyValueW(hKey, 0, L"ConfidenceLevel", 1u, v17, v18);
    Data = a6;
    RegSetKeyValueW(hKey, 0, L"ConfidenceUpdateType", 4u, &Data, 4u);
    if ( v12 )
    {
      SBServicingLogMessage((wchar_t *)L"All required keys are updated");
      RegSetKeyValueW(hKey, 0, L"UEFICA2023Status", 1u, L"Updated", 0x10u);
LABEL_16:
      RegDeleteValueW(hKey, L"UEFICA2023Error");
      RegDeleteValueW(hKey, L"UEFICA2023ErrorEvent");
      return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    if ( !(unsigned int)IsKeyRollUpdatesInProgress(a7, a8, a9) )
    {
      SBServicingLogMessage((wchar_t *)L"Updates NotStarted");
      RegSetKeyValueW(hKey, 0, L"UEFICA2023Status", 1u, L"NotStarted", 0x16u);
      goto LABEL_16;
    }
    SBServicingLogMessage(
      (wchar_t *)L"Key Rolling updates are in progress, setting UEFICA2023Error to %x UEFICA2023ErrorEvent to %x",
      a2,
      a3);
    RegSetKeyValueW(hKey, 0, L"UEFICA2023Status", 1u, L"InProgress", 0x16u);
    Data = a2;
    RegSetKeyValueW(hKey, 0, L"UEFICA2023Error", 4u, &Data, 4u);
    Data = a3;
    RegSetKeyValueW(hKey, 0, L"UEFICA2023ErrorEvent", 4u, &Data, 4u);
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18001b7d0  push    rbp
0x18001b7d2  push    rbx
0x18001b7d3  push    rsi
0x18001b7d4  push    rdi
0x18001b7d5  push    r12
0x18001b7d7  push    r14
0x18001b7d9  push    r15
0x18001b7db  mov     rbp, rsp
0x18001b7de  sub     rsp, 40h
0x18001b7e2  mov     rbx, r9
0x18001b7e5  mov     esi, r8d
0x18001b7e8  mov     r14d, edx
0x18001b7eb  mov     edi, ecx
0x18001b7ed  xor     r15d, r15d
0x18001b7f0  mov     [rbp+hKey], r15
0x18001b7f4  lea     r12d, [r15+1]
0x18001b7f8  mov     r9d, r12d
0x18001b7fb  lea     r8, [rbp+hKey]
0x18001b7ff  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18001b806  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001b80b  test    eax, eax
0x18001b80d  js      loc_18001B9F2
0x18001b813  mov     rcx, rbx
0x18001b816  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b81b  mov     rdx, rax
0x18001b81e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b822  test    rax, rax
0x18001b825  jnz     short loc_18001B82C
0x18001b827  mov     eax, r15d
0x18001b82a  jmp     short loc_18001B840
0x18001b82c  mov     rax, rbx
0x18001b82f  inc     rax
0x18001b832  cmp     [rdx+rax*2], r15w
0x18001b837  jnz     short loc_18001B82F
0x18001b839  lea     eax, ds:2[rax*2]
0x18001b840  mov     [rsp+40h+cbData], eax; cbData
0x18001b844  mov     [rsp+40h+lpData], rdx; lpData
0x18001b849  mov     r9d, r12d; dwType
0x18001b84c  lea     r8, aBuckethash; "BucketHash"
0x18001b853  xor     edx, edx; lpSubKey
0x18001b855  mov     rcx, [rbp+hKey]; hKey
0x18001b859  call    cs:__imp_RegSetKeyValueW
0x18001b85f  mov     rcx, [rbp+arg_20]
0x18001b863  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b868  test    rax, rax
0x18001b86b  jnz     short loc_18001B872
0x18001b86d  mov     ebx, r15d
0x18001b870  jmp     short loc_18001B883
0x18001b872  inc     rbx
0x18001b875  cmp     [rax+rbx*2], r15w
0x18001b87a  jnz     short loc_18001B872
0x18001b87c  lea     ebx, ds:2[rbx*2]
0x18001b883  mov     [rsp+40h+cbData], ebx; cbData
0x18001b887  mov     [rsp+40h+lpData], rax; lpData
0x18001b88c  mov     r9d, r12d; dwType
0x18001b88f  lea     r8, aConfidenceleve; "ConfidenceLevel"
0x18001b896  xor     edx, edx; lpSubKey
0x18001b898  mov     rcx, [rbp+hKey]; hKey
0x18001b89c  call    cs:__imp_RegSetKeyValueW
0x18001b8a2  mov     eax, [rbp+arg_28]
0x18001b8a5  mov     [rbp+Data], eax
0x18001b8a8  mov     ebx, 4
0x18001b8ad  mov     [rsp+40h+cbData], ebx; cbData
0x18001b8b1  lea     rax, [rbp+Data]
0x18001b8b5  mov     [rsp+40h+lpData], rax; lpData
0x18001b8ba  mov     r9d, ebx; dwType
0x18001b8bd  lea     r8, aConfidenceupda; "ConfidenceUpdateType"
0x18001b8c4  xor     edx, edx; lpSubKey
0x18001b8c6  mov     rcx, [rbp+hKey]; hKey
0x18001b8ca  call    cs:__imp_RegSetKeyValueW
0x18001b8d0  test    edi, edi
0x18001b8d2  jz      short loc_18001B8F4
0x18001b8d4  lea     rcx, aAllRequiredKey; "All required keys are updated"
0x18001b8db  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18001b8e0  mov     [rsp+40h+cbData], 10h
0x18001b8e8  lea     rax, aUpdated; "Updated"
0x18001b8ef  jmp     loc_18001B9B4
0x18001b8f4  mov     r8d, [rbp+arg_40]; unsigned int
0x18001b8fb  mov     edx, [rbp+arg_38]; unsigned int
0x18001b8fe  mov     ecx, [rbp+arg_30]; unsigned int
0x18001b901  call    ?IsKeyRollUpdatesInProgress@@YAHKKK@Z; IsKeyRollUpdatesInProgress(ulong,ulong,ulong)
0x18001b906  test    eax, eax
0x18001b908  jz      loc_18001B999
0x18001b90e  mov     r8d, esi
0x18001b911  mov     edx, r14d
0x18001b914  lea     rcx, aKeyRollingUpda; "Key Rolling updates are in progress, se"...
0x18001b91b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18001b920  mov     [rsp+40h+cbData], 16h; cbData
0x18001b928  lea     rax, aInprogress; "InProgress"
0x18001b92f  mov     [rsp+40h+lpData], rax; lpData
0x18001b934  mov     r9d, r12d; dwType
0x18001b937  lea     r8, aUefica2023stat; "UEFICA2023Status"
0x18001b93e  xor     edx, edx; lpSubKey
0x18001b940  mov     rcx, [rbp+hKey]; hKey
0x18001b944  call    cs:__imp_RegSetKeyValueW
0x18001b94a  mov     [rbp+Data], r14d
0x18001b94e  mov     [rsp+40h+cbData], ebx; cbData
0x18001b952  lea     rax, [rbp+Data]
0x18001b956  mov     [rsp+40h+lpData], rax; lpData
0x18001b95b  mov     r9d, ebx; dwType
0x18001b95e  lea     r8, aUefica2023erro; "UEFICA2023Error"
0x18001b965  xor     edx, edx; lpSubKey
0x18001b967  mov     rcx, [rbp+hKey]; hKey
0x18001b96b  call    cs:__imp_RegSetKeyValueW
0x18001b971  mov     [rbp+Data], esi
0x18001b974  mov     [rsp+40h+cbData], ebx; cbData
0x18001b978  lea     rax, [rbp+Data]
0x18001b97c  mov     [rsp+40h+lpData], rax; lpData
0x18001b981  mov     r9d, ebx; dwType
0x18001b984  lea     r8, aUefica2023erro_0; "UEFICA2023ErrorEvent"
0x18001b98b  xor     edx, edx; lpSubKey
0x18001b98d  mov     rcx, [rbp+hKey]; hKey
0x18001b991  call    cs:__imp_RegSetKeyValueW
0x18001b997  jmp     short loc_18001B9F2
0x18001b999  lea     rcx, aUpdatesNotstar; "Updates NotStarted"
0x18001b9a0  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18001b9a5  mov     [rsp+40h+cbData], 16h; cbData
0x18001b9ad  lea     rax, aNotstarted; "NotStarted"
0x18001b9b4  mov     [rsp+40h+lpData], rax; lpData
0x18001b9b9  mov     r9d, r12d; dwType
0x18001b9bc  lea     r8, aUefica2023stat; "UEFICA2023Status"
0x18001b9c3  xor     edx, edx; lpSubKey
0x18001b9c5  mov     rcx, [rbp+hKey]; hKey
0x18001b9c9  call    cs:__imp_RegSetKeyValueW
0x18001b9cf  lea     rdx, aUefica2023erro; "UEFICA2023Error"
0x18001b9d6  mov     rcx, [rbp+hKey]; hKey
0x18001b9da  call    cs:__imp_RegDeleteValueW
0x18001b9e0  lea     rdx, aUefica2023erro_0; "UEFICA2023ErrorEvent"
0x18001b9e7  mov     rcx, [rbp+hKey]; hKey
0x18001b9eb  call    cs:__imp_RegDeleteValueW
0x18001b9f1  nop
0x18001b9f2  lea     rcx, [rbp+hKey]
0x18001b9f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001b9fb  add     rsp, 40h
0x18001b9ff  pop     r15
0x18001ba01  pop     r14
0x18001ba03  pop     r12
0x18001ba05  pop     rdi
0x18001ba06  pop     rsi
0x18001ba07  pop     rbx
0x18001ba08  pop     rbp
0x18001ba09  retn
```
