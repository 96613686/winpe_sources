# McpManagementService::GetShutdownDelay(void)

- ea: `0x1800098d8`
- end: `0x1800099d2`
- name: `?GetShutdownDelay@McpManagementService@@QEAAKXZ`
- size: `250`
- prototype: `__int64 __fastcall(McpManagementService *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180007980`

## callees

- `0x180003a60`
- `0x180004d4c`
- `0x180007468`
- `0x180009264`
- `0x1800098d8`
- `0x18000af7c`
- `0x18000e208`
- `0x18000e790`
- `0x180015f60`

## pseudocode

```c
__int64 __fastcall McpManagementService::GetShutdownDelay(McpManagementService *this)
{
  __int64 MpsRegKeyPath; // rax
  __int64 v2; // rax
  HKEY v3; // rax
  unsigned int DwordValue; // ebx
  bool v6; // [rsp+20h] [rbp-29h] BYREF
  HKEY v7; // [rsp+28h] [rbp-21h] BYREF
  HKEY v8; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v11[32]; // [rsp+78h] [rbp+2Fh] BYREF

  v7 = 0;
  v6 = 0;
  MpsRegKeyPath = CloudPrint::CloudPrintHelper::GetMpsRegKeyPath((__int64)v11);
  v2 = std::operator+<unsigned short>(v10, MpsRegKeyPath, L"\\");
  std::operator+<unsigned short>(v9, v2, L"ShutdownDelay");
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v11);
  v8 = HKEY_LOCAL_MACHINE;
  v3 = PrintCore::RegHelpers::OpenKey(&v8, (__int64)v9, 0x20019u);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v7,
    v3);
  if ( !v7 || (v8 = v7, DwordValue = PrintCore::RegHelpers::GetDwordValue(&v8, 0, L"Delay", &v6), !v6) )
    DwordValue = 30000;
  std::wstring::_Tidy_deallocate((__int64)v9);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v7);
  return DwordValue;
}

```

## disassembly

```asm
0x1800098d8  mov     [rsp-8+arg_0], rbx
0x1800098dd  push    rbp
0x1800098de  lea     rbp, [rsp-57h]
0x1800098e3  sub     rsp, 0A0h
0x1800098ea  mov     rax, cs:__security_cookie
0x1800098f1  xor     rax, rsp
0x1800098f4  mov     [rbp+57h+var_8], rax
0x1800098f8  mov     [rbp+57h+var_78], 0
0x180009900  mov     [rbp+57h+var_80], 0
0x180009904  lea     rcx, [rbp+57h+var_28]
0x180009908  call    ?GetMpsRegKeyPath@CloudPrintHelper@CloudPrint@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CloudPrint::CloudPrintHelper::GetMpsRegKeyPath(void)
0x18000990d  nop
0x18000990e  lea     r8, asc_18002DEF8; "\\"
0x180009915  mov     rdx, rax
0x180009918  lea     rcx, [rbp+57h+var_48]
0x18000991c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180009921  nop
0x180009922  lea     r8, aShutdowndelay; "ShutdownDelay"
0x180009929  mov     rdx, rax
0x18000992c  lea     rcx, [rbp+57h+var_68]
0x180009930  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180009935  nop
0x180009936  lea     rcx, [rbp+57h+var_48]
0x18000993a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000993f  nop
0x180009940  lea     rcx, [rbp+57h+var_28]
0x180009944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009949  mov     [rbp+57h+var_70], 0FFFFFFFF80000002h
0x180009951  mov     r8d, 20019h
0x180009957  lea     rdx, [rbp+57h+var_68]
0x18000995b  lea     rcx, [rbp+57h+var_70]
0x18000995f  call    ?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x180009964  mov     rdx, rax
0x180009967  lea     rcx, [rbp+57h+var_78]
0x18000996b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009970  mov     rax, [rbp+57h+var_78]
0x180009974  test    rax, rax
0x180009977  jz      short loc_18000999B
0x180009979  mov     [rbp+57h+var_70], rax
0x18000997d  lea     r9, [rbp+57h+var_80]; bool *
0x180009981  lea     r8, aDelay; "Delay"
0x180009988  xor     edx, edx; unsigned __int16 *
0x18000998a  lea     rcx, [rbp+57h+var_70]; HKEY *
0x18000998e  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180009993  mov     ebx, eax
0x180009995  cmp     [rbp+57h+var_80], 0
0x180009999  jnz     short loc_1800099A0
0x18000999b  mov     ebx, 7530h
0x1800099a0  lea     rcx, [rbp+57h+var_68]
0x1800099a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800099a9  nop
0x1800099aa  lea     rcx, [rbp+57h+var_78]
0x1800099ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800099b3  mov     eax, ebx
0x1800099b5  mov     rcx, [rbp+57h+var_8]
0x1800099b9  xor     rcx, rsp; StackCookie
0x1800099bc  call    __security_check_cookie
0x1800099c1  mov     rbx, [rsp+0A0h+arg_0]
0x1800099c9  add     rsp, 0A0h
0x1800099d0  pop     rbp
0x1800099d1  retn
```
