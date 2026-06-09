# IsServicingInProgress(void)

- ea: `0x18000a95c`
- end: `0x18000aa83`
- name: `?IsServicingInProgress@@YA_NXZ`
- size: `295`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a6d4`
- `0x18000f4b0`

## callees

- `0x1800027c0`
- `0x1800078f8`
- `0x180008e3c`
- `0x18000a95c`
- `0x18000de84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a9a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a9a8`

## string_xrefs

- `0x18000a98d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`

## pseudocode

```c
bool IsServicingInProgress(void)
{
  bool v0; // bl
  unsigned int v1; // eax
  unsigned int v2; // eax
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  v0 = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  Type = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
         0,
         1u,
         &hKey);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v1);
  }
  else
  {
    v2 = RegQueryValueExW(hKey, L"ServicingInProgress", 0, &Type, Data, &cbData);
    if ( v2 || Type != 4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v2, Type);
    }
    else
    {
      v0 = *(_DWORD *)Data != 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x18000a95c  mov     [rsp-8+arg_0], rbx
0x18000a961  push    rbp
0x18000a962  mov     rbp, rsp
0x18000a965  sub     rsp, 50h
0x18000a969  mov     rax, cs:__security_cookie
0x18000a970  xor     rax, rsp
0x18000a973  mov     [rbp+var_8], rax
0x18000a977  xor     ebx, ebx
0x18000a979  mov     [rbp+cbData], 4
0x18000a980  lea     rax, [rbp+hKey]
0x18000a984  mov     dword ptr [rbp+Data], ebx
0x18000a987  xor     r8d, r8d; ulOptions
0x18000a98a  mov     [rbp+Type], ebx
0x18000a98d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000a994  mov     [rbp+hKey], rbx
0x18000a998  lea     r9d, [rbx+1]; samDesired
0x18000a99c  mov     [rsp+50h+phkResult], rax; phkResult
0x18000a9a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a9a8  call    cs:__imp_RegOpenKeyExW
0x18000a9ae  test    eax, eax
0x18000a9b0  jz      short loc_18000A9EB
0x18000a9b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9b9  lea     rdx, WPP_GLOBAL_Control
0x18000a9c0  cmp     rcx, rdx
0x18000a9c3  jz      loc_18000AA61
0x18000a9c9  cmp     byte ptr [rcx+19h], 4
0x18000a9cd  jb      loc_18000AA61
0x18000a9d3  mov     rcx, [rcx+10h]
0x18000a9d7  lea     edx, [rbx+0Ah]
0x18000a9da  mov     r9d, eax
0x18000a9dd  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000a9e4  call    WPP_SF_d
0x18000a9e9  jmp     short loc_18000AA61
0x18000a9eb  mov     rcx, [rbp+hKey]; hKey
0x18000a9ef  lea     rax, [rbp+cbData]
0x18000a9f3  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000a9f8  lea     r9, [rbp+Type]; lpType
0x18000a9fc  lea     rax, [rbp+Data]
0x18000aa00  xor     r8d, r8d; lpReserved
0x18000aa03  lea     rdx, ValueName; "ServicingInProgress"
0x18000aa0a  mov     [rsp+50h+phkResult], rax; lpData
0x18000aa0f  call    cs:__imp_RegQueryValueExW
0x18000aa15  mov     r8d, [rbp+Type]
0x18000aa19  test    eax, eax
0x18000aa1b  jnz     short loc_18000AA2B
0x18000aa1d  cmp     r8d, 4
0x18000aa21  jnz     short loc_18000AA2B
0x18000aa23  cmp     dword ptr [rbp+Data], ebx
0x18000aa26  setnbe  bl
0x18000aa29  jmp     short loc_18000AA61
0x18000aa2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa32  lea     rdx, WPP_GLOBAL_Control
0x18000aa39  cmp     rcx, rdx
0x18000aa3c  jz      short loc_18000AA61
0x18000aa3e  cmp     byte ptr [rcx+19h], 4
0x18000aa42  jb      short loc_18000AA61
0x18000aa44  mov     rcx, [rcx+10h]
0x18000aa48  mov     edx, 0Bh
0x18000aa4d  mov     dword ptr [rsp+50h+phkResult], r8d
0x18000aa52  mov     r9d, eax
0x18000aa55  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000aa5c  call    WPP_SF_DD
0x18000aa61  lea     rcx, [rbp+hKey]
0x18000aa65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000aa6a  mov     al, bl
0x18000aa6c  mov     rcx, [rbp+var_8]
0x18000aa70  xor     rcx, rsp; StackCookie
0x18000aa73  call    __security_check_cookie
0x18000aa78  mov     rbx, [rsp+50h+arg_0]
0x18000aa7d  add     rsp, 50h
0x18000aa81  pop     rbp
0x18000aa82  retn
```
