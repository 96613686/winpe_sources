# udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent

- ea: `0x14001f544`
- end: `0x14001f5ed`
- name: `udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f138`
- `0x14001f5f4`
- `0x1400205cc`

## callees

- `0x14000c864`
- `0x14000f2b0`
- `0x14001f544`
- `0x140037698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f582`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f582`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent()
{
  HKEY *v0; // rax
  LSTATUS v1; // eax
  int v2; // r8d
  int v3; // r9d
  bool v4; // sf
  signed int v5; // eax
  bool result; // al
  bool v7; // bl
  const char *v8; // r9
  wil::reg::reg_view_details *phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v11; // [rsp+50h] [rbp+8h] BYREF
  char v12; // [rsp+54h] [rbp+Ch]
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\HCF\\Status",
         0,
         0x20019u,
         v0);
  v4 = v1 < 0;
  if ( v1 > 0 )
  {
    v5 = (unsigned __int16)v1 | 0x80070000;
    v4 = v5 < 0;
  }
  if ( v4 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  else
  {
    v14 = v13;
    LODWORD(phkResult) = 16;
    try
    {
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
        (int)&v14,
        (int)&v11,
        v2,
        v3,
        phkResult);
      v7 = (v12 != 0 ? v11 : 0) != 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
      result = v7;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
        v8);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001f544  push    rbx
0x14001f546  sub     rsp, 40h
0x14001f54a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x14001f553  mov     [rsp+48h+arg_8], 0
0x14001f55c  lea     rcx, [rsp+48h+arg_8]
0x14001f561  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14001f566  mov     [rsp+48h+phkResult], rax; phkResult
0x14001f56b  mov     r9d, 20019h; samDesired
0x14001f571  xor     r8d, r8d; ulOptions
0x14001f574  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001f57b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001f582  call    cs:__imp_RegOpenKeyExW
0x14001f588  test    eax, eax
0x14001f58a  jle     short loc_14001F596
0x14001f58c  movzx   eax, ax
0x14001f58f  or      eax, 80070000h
0x14001f594  test    eax, eax
0x14001f596  jns     short loc_14001F5A6
0x14001f598  lea     rcx, [rsp+48h+arg_8]
0x14001f59d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001f5a2  xor     al, al
0x14001f5a4  jmp     short loc_14001F5E6
0x14001f5a6  mov     rax, [rsp+48h+arg_8]
0x14001f5ab  mov     [rsp+48h+arg_10], rax
0x14001f5b0  mov     dword ptr [rsp+48h+phkResult], 10h; wil::reg::reg_view_details *
0x14001f5b8  lea     rdx, [rsp+48h+arg_0]; int
0x14001f5bd  lea     rcx, [rsp+48h+arg_10]; int
0x14001f5c2  call    ??$try_get_value@I@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@I@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<uint>(wchar_t const *,wchar_t const *,ulong)
0x14001f5c7  mov     al, [rsp+48h+arg_4]
0x14001f5cb  neg     al
0x14001f5cd  sbb     ecx, ecx
0x14001f5cf  and     ecx, [rsp+48h+arg_0]
0x14001f5d3  setnz   bl
0x14001f5d6  lea     rcx, [rsp+48h+arg_8]
0x14001f5db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001f5e0  mov     al, bl
0x14001f5e2  jmp     short loc_14001F5E6
0x14001f5e4  xor     al, al
0x14001f5e6  add     rsp, 40h
0x14001f5ea  pop     rbx
0x14001f5eb  retn
```
