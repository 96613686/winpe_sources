# USBDevice::DeleteRecyclableFlag(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180030038`
- end: `0x180030106`
- name: `?DeleteRecyclableFlag@USBDevice@@SA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `206`
- prototype: `char __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800098c0`

## callees

- `0x180002d40`
- `0x18000f760`
- `0x18000f8a8`
- `0x18001d0e4`
- `0x180027060`
- `0x180030038`
- `0x1800307ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030084`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030084`

## string_xrefs

- `0x18003009e`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x1800300ca`: `USBDevice::DeleteRecyclableFlag`
- `0x180030092`: `RegDeleteValue for recyclable flag failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall USBDevice::DeleteRecyclableFlag(HKEY a1)
{
  HKEY v2; // rdx
  unsigned int v3; // eax
  char v4; // di
  HKEY v5; // r8
  const char *v7; // [rsp+28h] [rbp-30h]
  HKEY hKey[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  hKey[1] = a1;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v2 = a1;
  else
    v2 = *(HKEY *)a1;
  USBDevice::_OpenDeviceInterfaceKey(hKey, v2);
  if ( hKey[0] )
  {
    v3 = RegDeleteValueW(hKey[0], L"recyclable");
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
      (const char *)v3,
      (unsigned int)"RegDeleteValue for recyclable flag failed!",
      v7);
    v4 = 1;
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v5 = a1;
    else
      v5 = *(HKEY *)a1;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo("USBDevice::DeleteRecyclableFlag", L"Device not present: %ws", v5);
    v4 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  std::wstring::_Tidy_deallocate(a1);
  return v4;
}

```

## disassembly

```asm
0x180030038  mov     [rsp+arg_8], rbx
0x18003003d  push    rdi
0x18003003e  sub     rsp, 50h
0x180030042  mov     rax, cs:__security_cookie
0x180030049  xor     rax, rsp
0x18003004c  mov     [rsp+58h+var_18], rax
0x180030051  mov     rbx, rcx
0x180030054  mov     [rsp+58h+var_20], rcx
0x180030059  cmp     qword ptr [rcx+18h], 7
0x18003005e  jbe     short loc_180030065
0x180030060  mov     rdx, [rcx]
0x180030063  jmp     short loc_180030068
0x180030065  mov     rdx, rbx
0x180030068  lea     rcx, [rsp+58h+hKey]
0x18003006d  call    ?_OpenDeviceInterfaceKey@USBDevice@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; USBDevice::_OpenDeviceInterfaceKey(ushort const *)
0x180030072  nop
0x180030073  mov     rcx, [rsp+58h+hKey]; hKey
0x180030078  test    rcx, rcx
0x18003007b  jz      short loc_1800300B4
0x18003007d  lea     rdx, ValueName; "recyclable"
0x180030084  call    cs:__imp_RegDeleteValueW
0x18003008a  mov     r9d, eax; char *
0x18003008d  mov     rcx, [rsp+58h]; this
0x180030092  lea     rax, aRegdeletevalue; "RegDeleteValue for recyclable flag fail"...
0x180030099  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18003009e  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x1800300a5  mov     edx, 43h ; 'C'; void *
0x1800300aa  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800300af  mov     dil, 1
0x1800300b2  jmp     short loc_1800300D8
0x1800300b4  cmp     qword ptr [rbx+18h], 7
0x1800300b9  jbe     short loc_1800300C0
0x1800300bb  mov     r8, [rbx]
0x1800300be  jmp     short loc_1800300C3
0x1800300c0  mov     r8, rbx
0x1800300c3  lea     rdx, aDeviceNotPrese; "Device not present: %ws"
0x1800300ca  lea     rcx, aUsbdeviceDelet; "USBDevice::DeleteRecyclableFlag"
0x1800300d1  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800300d6  xor     edi, edi
0x1800300d8  lea     rcx, [rsp+58h+hKey]
0x1800300dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800300e2  nop
0x1800300e3  mov     rcx, rbx
0x1800300e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800300eb  mov     al, dil
0x1800300ee  mov     rcx, [rsp+58h+var_18]
0x1800300f3  xor     rcx, rsp; StackCookie
0x1800300f6  call    __security_check_cookie
0x1800300fb  mov     rbx, [rsp+58h+arg_8]
0x180030100  add     rsp, 50h
0x180030104  pop     rdi
0x180030105  retn
```
