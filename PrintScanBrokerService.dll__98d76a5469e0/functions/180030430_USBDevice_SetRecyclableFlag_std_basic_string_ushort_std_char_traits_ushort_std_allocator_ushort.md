# USBDevice::SetRecyclableFlag(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180030430`
- end: `0x18003050c`
- name: `?SetRecyclableFlag@USBDevice@@SA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `220`
- prototype: `char __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e410`

## callees

- `0x180002d40`
- `0x18000f760`
- `0x18000f8a8`
- `0x18001d0e4`
- `0x180027060`
- `0x180030430`
- `0x1800307ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003048d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003048d`

## string_xrefs

- `0x1800304a7`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x18003049b`: `RegSetValueEx for recyclable flag failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char __fastcall USBDevice::SetRecyclableFlag(HKEY a1)
{
  HKEY v2; // rdx
  char v3; // di
  unsigned int v4; // eax
  HKEY v5; // r8
  const char *cbData; // [rsp+28h] [rbp-30h]
  HKEY hKey[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  hKey[1] = a1;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v2 = a1;
  else
    v2 = *(HKEY *)a1;
  USBDevice::_OpenDeviceInterfaceKey(hKey, v2);
  v3 = 0;
  if ( hKey[0] )
  {
    v4 = RegSetValueExW(hKey[0], L"recyclable", 0, 0, 0, 0);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
      (const char *)v4,
      (unsigned int)"RegSetValueEx for recyclable flag failed!",
      cbData);
    v3 = 1;
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v5 = a1;
    else
      v5 = *(HKEY *)a1;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo("USBDevice::SetRecyclableFlag", L"Device not present: %ws", v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  std::wstring::_Tidy_deallocate(a1);
  return v3;
}

```

## disassembly

```asm
0x180030430  mov     [rsp+arg_8], rbx
0x180030435  push    rdi
0x180030436  sub     rsp, 50h
0x18003043a  mov     rax, cs:__security_cookie
0x180030441  xor     rax, rsp
0x180030444  mov     [rsp+58h+var_18], rax
0x180030449  mov     rbx, rcx
0x18003044c  mov     [rsp+58h+var_20], rcx
0x180030451  cmp     qword ptr [rcx+18h], 7
0x180030456  jbe     short loc_18003045D
0x180030458  mov     rdx, [rcx]
0x18003045b  jmp     short loc_180030460
0x18003045d  mov     rdx, rbx
0x180030460  lea     rcx, [rsp+58h+hKey]
0x180030465  call    ?_OpenDeviceInterfaceKey@USBDevice@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; USBDevice::_OpenDeviceInterfaceKey(ushort const *)
0x18003046a  nop
0x18003046b  mov     rcx, [rsp+58h+hKey]; hKey
0x180030470  xor     edi, edi
0x180030472  test    rcx, rcx
0x180030475  jz      short loc_1800304BB
0x180030477  mov     dword ptr [rsp+58h+cbData], edi; char *
0x18003047b  mov     [rsp+58h+lpData], rdi; lpData
0x180030480  xor     r9d, r9d; dwType
0x180030483  xor     r8d, r8d; Reserved
0x180030486  lea     rdx, ValueName; "recyclable"
0x18003048d  call    cs:__imp_RegSetValueExW
0x180030493  mov     r9d, eax; char *
0x180030496  mov     rcx, [rsp+58h]; this
0x18003049b  lea     rax, aRegsetvalueexF; "RegSetValueEx for recyclable flag faile"...
0x1800304a2  mov     [rsp+58h+lpData], rax; unsigned int
0x1800304a7  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x1800304ae  lea     edx, [rdi+33h]; void *
0x1800304b1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800304b6  mov     dil, 1
0x1800304b9  jmp     short loc_1800304DE
0x1800304bb  cmp     qword ptr [rbx+18h], 7
0x1800304c0  jbe     short loc_1800304C7
0x1800304c2  mov     r8, [rbx]
0x1800304c5  jmp     short loc_1800304CA
0x1800304c7  mov     r8, rbx
0x1800304ca  lea     rdx, aDeviceNotPrese; "Device not present: %ws"
0x1800304d1  lea     rcx, aUsbdeviceSetre; "USBDevice::SetRecyclableFlag"
0x1800304d8  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800304dd  nop
0x1800304de  lea     rcx, [rsp+58h+hKey]
0x1800304e3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800304e8  nop
0x1800304e9  mov     rcx, rbx
0x1800304ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800304f1  mov     al, dil
0x1800304f4  mov     rcx, [rsp+58h+var_18]
0x1800304f9  xor     rcx, rsp; StackCookie
0x1800304fc  call    __security_check_cookie
0x180030501  mov     rbx, [rsp+58h+arg_8]
0x180030506  add     rsp, 50h
0x18003050a  pop     rdi
0x18003050b  retn
```
