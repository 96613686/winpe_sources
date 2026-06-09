# StorageWriter::ReadFeatureUsageSubscription(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,uint,ushort const *)

- ea: `0x18004f548`
- end: `0x18004f6d1`
- name: `?ReadFeatureUsageSubscription@StorageWriter@@CA?AU_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@IPEBG@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004f6d8`

## callees

- `0x18000a6e0`
- `0x180019f10`
- `0x180024550`
- `0x18004f548`
- `0x18004fc08`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18004f58d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18004f58d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f5de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f660`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f5de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f660`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall StorageWriter::ReadFeatureUsageSubscription(_OWORD *a1, HKEY *a2, int a3, const WCHAR *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // r8d
  unsigned int ValueW; // eax
  unsigned int v11; // r8d
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int pdwType; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-50h]
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  __int128 pvData; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v8 = RegOpenKeyW(*a2, a4, &phkResult);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x188, v9, (const char *)v8, pdwType);
  pvData = 0;
  LODWORD(pvData) = a3;
  pcbData = 4;
  ValueW = RegGetValueW(phkResult, 0, L"ReportingKind", 0x10u, 0, (char *)&pvData + 4, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x18E, v11, (const char *)ValueW, pdwTypea);
  pcbData = 4;
  v12 = RegGetValueW(phkResult, 0, L"ReportingOptions", 0x10u, 0, (char *)&pvData + 6, &pcbData);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x191, v13, (const char *)v12, pdwTypeb);
  pcbData = 8;
  v14 = RegGetValueW(phkResult, 0, L"ReportingTarget", 8u, 0, (char *)&pvData + 8, &pcbData);
  if ( v14 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x194, v15, (const char *)v14, pdwTypec);
  *a1 = pvData;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return a1;
}

```

## disassembly

```asm
0x18004f548  push    rbp
0x18004f54a  push    rbx
0x18004f54b  push    rsi
0x18004f54c  push    rdi
0x18004f54d  push    r14
0x18004f54f  mov     rbp, rsp
0x18004f552  sub     rsp, 70h
0x18004f556  mov     rax, cs:__security_cookie
0x18004f55d  xor     rax, rsp
0x18004f560  mov     [rbp+var_10], rax
0x18004f564  mov     rdi, r9
0x18004f567  mov     r14d, r8d
0x18004f56a  mov     rbx, rdx
0x18004f56d  mov     rsi, rcx
0x18004f570  mov     [rbp+phkResult], 0
0x18004f578  xor     edx, edx
0x18004f57a  lea     rcx, [rbp+phkResult]
0x18004f57e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004f583  lea     r8, [rbp+phkResult]; phkResult
0x18004f587  mov     rdx, rdi; lpSubKey
0x18004f58a  mov     rcx, [rbx]; hKey
0x18004f58d  call    cs:__imp_RegOpenKeyW
0x18004f593  mov     rcx, [rbp+28h]; this
0x18004f597  test    eax, eax
0x18004f599  jnz     loc_18004F6A7
0x18004f59f  xorps   xmm0, xmm0
0x18004f5a2  movups  [rbp+var_20], xmm0
0x18004f5a6  mov     dword ptr [rbp+var_20], r14d
0x18004f5aa  lea     ebx, [rax+4]
0x18004f5ad  mov     [rbp+var_30], ebx
0x18004f5b0  lea     rax, [rbp+var_30]
0x18004f5b4  mov     [rsp+70h+pcbData], rax; pcbData
0x18004f5b9  lea     rax, [rbp+var_20+4]
0x18004f5bd  mov     [rsp+70h+pvData], rax; pvData
0x18004f5c2  mov     [rsp+70h+pdwType], 0; unsigned int
0x18004f5cb  lea     edi, [rbx+0Ch]
0x18004f5ce  mov     r9d, edi; dwFlags
0x18004f5d1  lea     r8, aReportingkind; "ReportingKind"
0x18004f5d8  xor     edx, edx; lpSubKey
0x18004f5da  mov     rcx, [rbp+phkResult]; hkey
0x18004f5de  call    cs:__imp_RegGetValueW
0x18004f5e4  mov     rcx, [rbp+28h]; this
0x18004f5e8  test    eax, eax
0x18004f5ea  jnz     loc_18004F6B5
0x18004f5f0  mov     [rbp+var_30], ebx
0x18004f5f3  lea     rax, [rbp+var_30]
0x18004f5f7  mov     [rsp+70h+pcbData], rax; pcbData
0x18004f5fc  lea     rax, [rbp+var_20+6]
0x18004f600  mov     [rsp+70h+pvData], rax; pvData
0x18004f605  mov     [rsp+70h+pdwType], 0; unsigned int
0x18004f60e  mov     r9d, edi; dwFlags
0x18004f611  lea     r8, aReportingoptio; "ReportingOptions"
0x18004f618  xor     edx, edx; lpSubKey
0x18004f61a  mov     rcx, [rbp+phkResult]; hkey
0x18004f61e  call    cs:__imp_RegGetValueW
0x18004f624  mov     rcx, [rbp+28h]; this
0x18004f628  test    eax, eax
0x18004f62a  jnz     loc_18004F6C3
0x18004f630  lea     r9d, [rbx+4]; dwFlags
0x18004f634  mov     [rbp+var_30], r9d
0x18004f638  lea     rax, [rbp+var_30]
0x18004f63c  mov     [rsp+70h+pcbData], rax; pcbData
0x18004f641  lea     rax, [rbp+var_20+8]
0x18004f645  mov     [rsp+70h+pvData], rax; pvData
0x18004f64a  mov     [rsp+70h+pdwType], 0; unsigned int
0x18004f653  lea     r8, aReportingtarge; "ReportingTarget"
0x18004f65a  xor     edx, edx; lpSubKey
0x18004f65c  mov     rcx, [rbp+phkResult]; hkey
0x18004f660  call    cs:__imp_RegGetValueW
0x18004f666  mov     rcx, [rbp+28h]; this
0x18004f66a  test    eax, eax
0x18004f66c  jnz     short loc_18004F699
0x18004f66e  movups  xmm0, [rbp+var_20]
0x18004f672  movdqu  xmmword ptr [rsi], xmm0
0x18004f676  lea     rcx, [rbp+phkResult]
0x18004f67a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004f67f  mov     rax, rsi
0x18004f682  mov     rcx, [rbp+var_10]
0x18004f686  xor     rcx, rsp; StackCookie
0x18004f689  call    __security_check_cookie
0x18004f68e  add     rsp, 70h
0x18004f692  pop     r14
0x18004f694  pop     rdi
0x18004f695  pop     rsi
0x18004f696  pop     rbx
0x18004f697  pop     rbp
0x18004f698  retn
0x18004f699  mov     r9d, eax; char *
0x18004f69c  mov     edx, 194h; void *
0x18004f6a1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004f6a7  mov     r9d, eax; char *
0x18004f6aa  mov     edx, 188h; void *
0x18004f6af  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004f6b5  mov     r9d, eax; char *
0x18004f6b8  mov     edx, 18Eh; void *
0x18004f6bd  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004f6c3  mov     r9d, eax; char *
0x18004f6c6  mov     edx, 191h; void *
0x18004f6cb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
