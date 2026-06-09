# Windows::GetPolicyValue(tagEnterprisePolicy)

- ea: `0x14025d674`
- end: `0x14025d7dc`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@W4tagEnterprisePolicy@@@Z`
- size: `360`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14025d7f0`
- `0x14025dae0`
- `0x14025de10`

## callees

- `0x1400c695c`
- `0x14025d674`
- `0x14025e0cc`
- `0x14025eab8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d6dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d6dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14025d6e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14025d6e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14025d6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14025d6d1`
- `OLEAUT32!__imp_VariantClear` at `0x14025d755`
- `OLEAUT32!__imp_VariantClear` at `0x14025d755`

## string_xrefs

- `0x14025d726`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::GetPolicyValue(__int64 a1, unsigned int a2)
{
  int (__fastcall *v4)(__int64, _QWORD, LPVOID *); // r12
  int v5; // eax
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-49h]
  _QWORD v9[2]; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  __int64 v11; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  pv = 0;
  v11 = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v11);
  v4 = *(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v11 + 48LL);
  pv = 0;
  if ( v4(v11, a2, &pv) < 0 )
  {
LABEL_4:
    *(_BYTE *)(a1 + 32) = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, a2, v12);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x967,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      (const char *)(unsigned int)v5,
      v8);
    goto LABEL_4;
  }
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)pv + v7) );
  v9[0] = pv;
  v9[1] = v7;
  Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1>>(a1, v9, v12);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_6:
  VariantClear(&pvarg);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x14025d674  mov     [rsp-8+arg_10], rbx
0x14025d679  push    rbp
0x14025d67a  push    rsi
0x14025d67b  push    rdi
0x14025d67c  push    r12
0x14025d67e  push    r13
0x14025d680  push    r14
0x14025d682  push    r15
0x14025d684  lea     rbp, [rsp-27h]
0x14025d689  sub     rsp, 90h
0x14025d690  mov     rax, cs:__security_cookie
0x14025d697  xor     rax, rsp
0x14025d69a  mov     [rbp+57h+var_40], rax
0x14025d69e  mov     r15d, edx
0x14025d6a1  mov     rsi, rcx
0x14025d6a4  mov     [rbp+57h+var_78], rcx
0x14025d6a8  xor     r13d, r13d
0x14025d6ab  mov     [rbp+57h+pv], r13
0x14025d6af  mov     [rbp+57h+var_78], r13
0x14025d6b3  lea     rcx, [rbp+57h+var_78]
0x14025d6b7  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x14025d6bc  nop
0x14025d6bd  mov     rbx, [rbp+57h+var_78]
0x14025d6c1  mov     rax, [rbx]
0x14025d6c4  mov     r12, [rax+30h]
0x14025d6c8  mov     r14, [rbp+57h+pv]
0x14025d6cc  test    r14, r14
0x14025d6cf  jz      short loc_14025D6EA
0x14025d6d1  call    cs:__imp_GetLastError
0x14025d6d7  mov     edi, eax
0x14025d6d9  mov     rcx, r14; pv
0x14025d6dc  call    cs:__imp_CoTaskMemFree
0x14025d6e2  mov     ecx, edi; dwErrCode
0x14025d6e4  call    cs:__imp_SetLastError
0x14025d6ea  mov     [rbp+57h+pv], r13
0x14025d6ee  lea     r8, [rbp+57h+pv]
0x14025d6f2  mov     edx, r15d
0x14025d6f5  mov     rcx, rbx
0x14025d6f8  mov     rax, r12
0x14025d6fb  call    _guard_dispatch_icall
0x14025d700  test    eax, eax
0x14025d702  js      short loc_14025D737
0x14025d704  mov     rcx, [rbp+57h+var_78]
0x14025d708  mov     rax, [rcx]
0x14025d70b  lea     r8, [rbp+57h+var_70]
0x14025d70f  mov     edx, r15d
0x14025d712  mov     rax, [rax+20h]
0x14025d716  call    _guard_dispatch_icall
0x14025d71b  mov     rcx, [rbp+5Fh]; this
0x14025d71f  test    eax, eax
0x14025d721  jns     short loc_14025D795
0x14025d723  mov     r9d, eax; char *
0x14025d726  lea     r8, aCW1SSrcOrchest_58; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14025d72d  mov     edx, 967h; void *
0x14025d732  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14025d737  mov     [rsi+20h], r13b
0x14025d73b  mov     rcx, [rbp+57h+var_78]
0x14025d73f  test    rcx, rcx
0x14025d742  jz      short loc_14025D751
0x14025d744  mov     rax, [rcx]
0x14025d747  mov     rax, [rax+10h]
0x14025d74b  call    _guard_dispatch_icall
0x14025d750  nop
0x14025d751  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14025d755  call    cs:__imp_VariantClear
0x14025d75b  nop
0x14025d75c  mov     rcx, [rbp+57h+pv]; pv
0x14025d760  test    rcx, rcx
0x14025d763  jz      short loc_14025D76B
0x14025d765  call    cs:__imp_CoTaskMemFree
0x14025d76b  mov     rax, rsi
0x14025d76e  mov     rcx, [rbp+57h+var_40]
0x14025d772  xor     rcx, rsp; StackCookie
0x14025d775  call    __security_check_cookie
0x14025d77a  mov     rbx, [rsp+0C0h+arg_10]
0x14025d782  add     rsp, 90h
0x14025d789  pop     r15
0x14025d78b  pop     r14
0x14025d78d  pop     r13
0x14025d78f  pop     r12
0x14025d791  pop     rdi
0x14025d792  pop     rsi
0x14025d793  pop     rbp
0x14025d794  retn
0x14025d795  mov     rax, [rbp+57h+pv]
0x14025d799  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14025d79d  inc     rcx
0x14025d7a0  cmp     [rax+rcx*2], r13w
0x14025d7a5  jnz     short loc_14025D79D
0x14025d7a7  mov     [rbp+57h+var_90], rax
0x14025d7ab  mov     [rbp+57h+var_88], rcx
0x14025d7af  lea     r8, [rbp+57h+var_70]
0x14025d7b3  lea     rdx, [rbp+57h+var_90]
0x14025d7b7  mov     rcx, rsi
0x14025d7ba  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagEnterprisePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@AEBV?$WrappedPolicyValue@UtagEnterprisePolicyValue_V1@@@0@_N@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1>>(wil::basic_zstring_view<wchar_t>,Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1> const &,bool)
0x14025d7bf  nop
0x14025d7c0  mov     rcx, [rbp+57h+var_78]
0x14025d7c4  test    rcx, rcx
0x14025d7c7  jz      short loc_14025D7D6
0x14025d7c9  mov     rax, [rcx]
0x14025d7cc  mov     rax, [rax+10h]
0x14025d7d0  call    _guard_dispatch_icall
0x14025d7d5  nop
0x14025d7d6  jmp     loc_14025D751
```
