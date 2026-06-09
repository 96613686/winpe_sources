# dxg::svc::CreateServiceParameterKey(ushort const *,ulong)

- ea: `0x180026354`
- end: `0x18002648c`
- name: `?CreateServiceParameterKey@svc@dxg@@YAPEAUHKEY__@@PEBGK@Z`
- size: `312`
- prototype: `HKEY __fastcall(dxg::svc *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026494`

## callees

- `0x18000e77c`
- `0x18001c068`
- `0x180026330`
- `0x180026354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026444`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026444`

## string_xrefs

- `0x180026392`: `SYSTEM\CurrentControlSet\Services\`
- `0x1800263b1`: `onecoreuap\windows\directx\dxg\common\servicehelpers\parameters.cpp`
- `0x180026408`: `onecoreuap\windows\directx\dxg\common\servicehelpers\parameters.cpp`
- `0x180026455`: `onecoreuap\windows\directx\dxg\common\servicehelpers\parameters.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY __fastcall dxg::svc::CreateServiceParameterKey(dxg::svc *this, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  HKEY v5; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int phkResultb; // [rsp+20h] [rbp-30h]
  HKEY *p_hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY v11; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY v14; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HKEY v16; // [rsp+78h] [rbp+28h] BYREF

  hKey = 0;
  v14 = 0;
  p_hKey = &hKey;
  v11 = 0;
  v12 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\", 0, 0x20019u, &v11);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\parameters.cpp",
      (const char *)v2,
      phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  p_hKey = &v14;
  v11 = 0;
  v12 = 1;
  v3 = RegOpenKeyExW(hKey, L"GraphicsPerfSvc", 0, 0x20019u, &v11);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\parameters.cpp",
      (const char *)v3,
      phkResulta);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v16 = 0;
  v4 = RegOpenKeyExW(v14, L"Parameters", 0, 0x20019u, &v16);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\parameters.cpp",
      (const char *)v4,
      phkResultb);
  v5 = v16;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180026354  mov     [rsp-8+arg_8], rbx
0x180026359  mov     [rsp-8+arg_0], rcx
0x18002635e  push    rbp
0x18002635f  mov     rbp, rsp
0x180026362  sub     rsp, 50h
0x180026366  xor     ebx, ebx
0x180026368  mov     [rbp+hKey], rbx
0x18002636c  mov     [rbp+arg_0], rbx
0x180026370  lea     rax, [rbp+hKey]
0x180026374  mov     [rbp+var_20], rax
0x180026378  mov     [rbp+var_18], rbx
0x18002637c  mov     [rbp+var_10], 1
0x180026380  lea     rax, [rbp+var_18]
0x180026384  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180026389  mov     r9d, 20019h; samDesired
0x18002638f  xor     r8d, r8d; ulOptions
0x180026392  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\"
0x180026399  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800263a0  call    cs:__imp_RegOpenKeyExW
0x1800263a6  mov     rcx, [rbp+8]; this
0x1800263aa  test    eax, eax
0x1800263ac  jz      short loc_1800263C1
0x1800263ae  mov     r9d, eax; char *
0x1800263b1  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800263b8  lea     edx, [rbx+18h]; void *
0x1800263bb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800263c1  lea     rcx, [rbp+var_20]
0x1800263c5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800263ca  lea     rax, [rbp+arg_0]
0x1800263ce  mov     [rbp+var_20], rax
0x1800263d2  mov     [rbp+var_18], rbx
0x1800263d6  mov     [rbp+var_10], 1
0x1800263da  lea     rax, [rbp+var_18]
0x1800263de  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x1800263e3  mov     r9d, 20019h; samDesired
0x1800263e9  xor     r8d, r8d; ulOptions
0x1800263ec  lea     rdx, ServiceName; "GraphicsPerfSvc"
0x1800263f3  mov     rcx, [rbp+hKey]; hKey
0x1800263f7  call    cs:__imp_RegOpenKeyExW
0x1800263fd  mov     rcx, [rbp+8]; this
0x180026401  test    eax, eax
0x180026403  jz      short loc_18002641A
0x180026405  mov     r9d, eax; char *
0x180026408  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18002640f  mov     edx, 19h; void *
0x180026414  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002641a  lea     rcx, [rbp+var_20]
0x18002641e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180026423  mov     [rbp+arg_18], rbx
0x180026427  lea     rax, [rbp+arg_18]
0x18002642b  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180026430  mov     r9d, 20019h; samDesired
0x180026436  xor     r8d, r8d; ulOptions
0x180026439  lea     rdx, aParameters; "Parameters"
0x180026440  mov     rcx, [rbp+arg_0]; hKey
0x180026444  call    cs:__imp_RegOpenKeyExW
0x18002644a  mov     rcx, [rbp+8]; this
0x18002644e  test    eax, eax
0x180026450  jz      short loc_180026467
0x180026452  mov     r9d, eax; char *
0x180026455  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18002645c  mov     edx, 1Ch; void *
0x180026461  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180026467  mov     rbx, [rbp+arg_18]
0x18002646b  lea     rcx, [rbp+arg_0]
0x18002646f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026474  nop
0x180026475  lea     rcx, [rbp+hKey]
0x180026479  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002647e  mov     rax, rbx
0x180026481  mov     rbx, [rsp+50h+arg_8]
0x180026486  add     rsp, 50h
0x18002648a  pop     rbp
0x18002648b  retn
```
