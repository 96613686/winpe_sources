# NetSetupService::OpenStateSeparationHives(void)

- ea: `0x18000b2c0`
- end: `0x18000b4ad`
- name: `?OpenStateSeparationHives@NetSetupService@@AEAAXXZ`
- size: `493`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800088d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x180008e3c`
- `0x18000953c`
- `0x18000b2c0`
- `0x180026958`
- `0x180027560`
- `0x1800285cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b35a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b3fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b35a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b3fe`

## string_xrefs

- `0x18000b31a`: `StateSeparatedRegistryLayout`

## pseudocode

```c
void __fastcall NetSetupService::OpenStateSeparationHives(HKEY *this)
{
  unsigned int v2; // eax
  signed int v3; // ebx
  unsigned int v4; // eax
  signed int v5; // ebx
  HKEY v6; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp+8h] BYREF
  HKEY v9; // [rsp+110h] [rbp+10h] BYREF

  RegistryKey::TryOpenSubKey(this + 35, &v9, L"Control\\NetworkSetup2\\Parameters", 1, 0);
  if ( v9 && RegistryKey::GetValueBoolean((__int64)&v9, (__int64)L"StateSeparatedRegistryLayout") )
  {
    phkResult = 0;
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"DEVICES", 0, 4u, &phkResult);
    v3 = v2;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v2);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v3);
      throw (Win32Exception *)pExceptionObject;
    }
    RegistryKey::RegistryKey((RegistryKey *)&v6, phkResult);
    RegistryKey::operator=(this + 36, &v6);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"OSDATA", 0, 4u, &phkResult);
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v4);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
      throw (Win32Exception *)pExceptionObject;
    }
    RegistryKey::RegistryKey((RegistryKey *)&v6, phkResult);
    RegistryKey::operator=(this + 37, &v6);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x18000b2c0  mov     [rsp-8+arg_8], rbx
0x18000b2c5  mov     [rsp-8+arg_10], rdi
0x18000b2ca  push    rbp
0x18000b2cb  lea     rbp, [rsp-20h]
0x18000b2d0  sub     rsp, 120h
0x18000b2d7  mov     rax, cs:__security_cookie
0x18000b2de  xor     rax, rsp
0x18000b2e1  mov     [rbp+20h+var_8], rax
0x18000b2e5  mov     rdi, rcx
0x18000b2e8  add     rcx, 118h
0x18000b2ef  mov     [rsp+120h+phkResult], 0
0x18000b2f8  mov     r9d, 1
0x18000b2fe  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\Parameters"
0x18000b305  lea     rdx, [rbp+20h+var_10]
0x18000b309  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000b30e  nop
0x18000b30f  cmp     [rbp+20h+var_10], 0
0x18000b314  jz      loc_18000B483
0x18000b31a  lea     rdx, aStateseparated; "StateSeparatedRegistryLayout"
0x18000b321  lea     rcx, [rbp+20h+var_10]
0x18000b325  call    ?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18000b32a  test    al, al
0x18000b32c  jz      loc_18000B483
0x18000b332  mov     [rbp+20h+var_18], 0
0x18000b33a  lea     rax, [rbp+20h+var_18]
0x18000b33e  mov     [rsp+120h+phkResult], rax; phkResult
0x18000b343  mov     r9d, 4; samDesired
0x18000b349  xor     r8d, r8d; ulOptions
0x18000b34c  lea     rdx, aDevices; "DEVICES"
0x18000b353  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b35a  call    cs:__imp_RegOpenKeyExW
0x18000b360  mov     ebx, eax
0x18000b362  test    eax, eax
0x18000b364  jz      short loc_18000B3B5
0x18000b366  lea     rdx, WPP_GLOBAL_Control
0x18000b36d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b374  cmp     rcx, rdx
0x18000b377  jz      short loc_18000B397
0x18000b379  cmp     byte ptr [rcx+19h], 2
0x18000b37d  jb      short loc_18000B397
0x18000b37f  mov     edx, 15h
0x18000b384  mov     r9d, eax
0x18000b387  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000b38e  mov     rcx, [rcx+10h]
0x18000b392  call    WPP_SF_d
0x18000b397  mov     edx, ebx; int
0x18000b399  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18000b39e  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000b3a3  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000b3aa  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18000b3af  call    _CxxThrowException_0
0x18000b3b5  mov     rdx, [rbp+20h+var_18]; HKEY
0x18000b3b9  lea     rcx, [rsp+120h+var_F0]; this
0x18000b3be  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000b3c3  lea     rcx, [rdi+120h]
0x18000b3ca  lea     rdx, [rsp+120h+var_F0]
0x18000b3cf  call    ??4RegistryKey@@QEAAAEAV0@$$QEAV0@@Z; RegistryKey::operator=(RegistryKey &&)
0x18000b3d4  lea     rcx, [rsp+120h+var_F0]
0x18000b3d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b3de  lea     rax, [rbp+20h+var_18]
0x18000b3e2  mov     [rsp+120h+phkResult], rax; phkResult
0x18000b3e7  mov     r9d, 4; samDesired
0x18000b3ed  xor     r8d, r8d; ulOptions
0x18000b3f0  lea     rdx, aOsdata; "OSDATA"
0x18000b3f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b3fe  call    cs:__imp_RegOpenKeyExW
0x18000b404  mov     ebx, eax
0x18000b406  test    eax, eax
0x18000b408  jz      short loc_18000B459
0x18000b40a  lea     rdx, WPP_GLOBAL_Control
0x18000b411  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b418  cmp     rcx, rdx
0x18000b41b  jz      short loc_18000B43B
0x18000b41d  cmp     byte ptr [rcx+19h], 2
0x18000b421  jb      short loc_18000B43B
0x18000b423  mov     edx, 16h
0x18000b428  mov     r9d, eax
0x18000b42b  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000b432  mov     rcx, [rcx+10h]
0x18000b436  call    WPP_SF_d
0x18000b43b  mov     edx, ebx; int
0x18000b43d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18000b442  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000b447  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000b44e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18000b453  call    _CxxThrowException_0
0x18000b459  mov     rdx, [rbp+20h+var_18]; HKEY
0x18000b45d  lea     rcx, [rsp+120h+var_F0]; this
0x18000b462  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000b467  lea     rcx, [rdi+128h]
0x18000b46e  lea     rdx, [rsp+120h+var_F0]
0x18000b473  call    ??4RegistryKey@@QEAAAEAV0@$$QEAV0@@Z; RegistryKey::operator=(RegistryKey &&)
0x18000b478  lea     rcx, [rsp+120h+var_F0]
0x18000b47d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b482  nop
0x18000b483  lea     rcx, [rbp+20h+var_10]
0x18000b487  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b48c  mov     rcx, [rbp+20h+var_8]
0x18000b490  xor     rcx, rsp; StackCookie
0x18000b493  call    __security_check_cookie
0x18000b498  lea     r11, [rsp+120h+var_s0]
0x18000b4a0  mov     rbx, [r11+18h]
0x18000b4a4  mov     rdi, [r11+20h]
0x18000b4a8  mov     rsp, r11
0x18000b4ab  pop     rbp
0x18000b4ac  retn
```
