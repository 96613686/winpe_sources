# Windows::GetPolicyValue(tagUpdatePolicy)

- ea: `0x14025d4f8`
- end: `0x14025d66b`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@W4tagUpdatePolicy@@@Z`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14025d7f0`
- `0x14025dae0`

## callees

- `0x1400c695c`
- `0x14025d4f8`
- `0x14025e0cc`
- `0x14025e840`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14025d5e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14025d565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14025d565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14025d552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14025d552`
- `OLEAUT32!__imp_VariantClear` at `0x14025d5d4`
- `OLEAUT32!__imp_VariantClear` at `0x14025d5d4`

## string_xrefs

- `0x14025d5a5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::GetPolicyValue(__int64 a1, unsigned int a2)
{
  int (__fastcall *v4)(__int64, _QWORD, LPVOID *); // r12
  int v5; // eax
  __int64 v6; // r9
  __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-60h]
  _QWORD v10[2]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v12; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v13[16]; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  pv = 0;
  v12 = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v12);
  v4 = *(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 40LL);
  pv = 0;
  if ( v4(v12, a2, &pv) < 0 )
  {
LABEL_4:
    *(_BYTE *)(a1 + 32) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v12 + 24LL))(v12, a2, v13);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x95A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      (const char *)(unsigned int)v5,
      v9);
    goto LABEL_4;
  }
  if ( a2 == 12 || (LOBYTE(v6) = 0, a2 == 26) )
    LOBYTE(v6) = 1;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)pv + v8) );
  v10[0] = pv;
  v10[1] = v8;
  Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(a1, v10, v13, v6);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_6:
  VariantClear(&pvarg);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x14025d4f8  mov     [rsp-38h+arg_10], rbx
0x14025d4fd  push    rbp
0x14025d4fe  push    rsi
0x14025d4ff  push    rdi
0x14025d500  push    r12
0x14025d502  push    r13
0x14025d504  push    r14
0x14025d506  push    r15
0x14025d508  mov     rbp, rsp
0x14025d50b  sub     rsp, 80h
0x14025d512  mov     rax, cs:__security_cookie
0x14025d519  xor     rax, rsp
0x14025d51c  mov     [rbp+var_8], rax
0x14025d520  mov     esi, edx
0x14025d522  mov     r14, rcx
0x14025d525  mov     [rbp+var_38], rcx
0x14025d529  xor     r13d, r13d
0x14025d52c  mov     [rbp+pv], r13
0x14025d530  mov     [rbp+var_38], r13
0x14025d534  lea     rcx, [rbp+var_38]
0x14025d538  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x14025d53d  nop
0x14025d53e  mov     rbx, [rbp+var_38]
0x14025d542  mov     rax, [rbx]
0x14025d545  mov     r12, [rax+28h]
0x14025d549  mov     r15, [rbp+pv]
0x14025d54d  test    r15, r15
0x14025d550  jz      short loc_14025D56B
0x14025d552  call    cs:__imp_GetLastError
0x14025d558  mov     edi, eax
0x14025d55a  mov     rcx, r15; pv
0x14025d55d  call    cs:__imp_CoTaskMemFree
0x14025d563  mov     ecx, edi; dwErrCode
0x14025d565  call    cs:__imp_SetLastError
0x14025d56b  mov     [rbp+pv], r13
0x14025d56f  lea     r8, [rbp+pv]
0x14025d573  mov     edx, esi
0x14025d575  mov     rcx, rbx
0x14025d578  mov     rax, r12
0x14025d57b  call    _guard_dispatch_icall
0x14025d580  test    eax, eax
0x14025d582  js      short loc_14025D5B6
0x14025d584  mov     rcx, [rbp+var_38]
0x14025d588  mov     rax, [rcx]
0x14025d58b  lea     r8, [rbp+var_30]
0x14025d58f  mov     edx, esi
0x14025d591  mov     rax, [rax+18h]
0x14025d595  call    _guard_dispatch_icall
0x14025d59a  mov     rcx, [rbp+38h]; this
0x14025d59e  test    eax, eax
0x14025d5a0  jns     short loc_14025D614
0x14025d5a2  mov     r9d, eax; char *
0x14025d5a5  lea     r8, aCW1SSrcOrchest_58; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14025d5ac  mov     edx, 95Ah; void *
0x14025d5b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14025d5b6  mov     [r14+20h], r13b
0x14025d5ba  mov     rcx, [rbp+var_38]
0x14025d5be  test    rcx, rcx
0x14025d5c1  jz      short loc_14025D5D0
0x14025d5c3  mov     rax, [rcx]
0x14025d5c6  mov     rax, [rax+10h]
0x14025d5ca  call    _guard_dispatch_icall
0x14025d5cf  nop
0x14025d5d0  lea     rcx, [rbp+pvarg]; pvarg
0x14025d5d4  call    cs:__imp_VariantClear
0x14025d5da  nop
0x14025d5db  mov     rcx, [rbp+pv]; pv
0x14025d5df  test    rcx, rcx
0x14025d5e2  jz      short loc_14025D5EA
0x14025d5e4  call    cs:__imp_CoTaskMemFree
0x14025d5ea  mov     rax, r14
0x14025d5ed  mov     rcx, [rbp+var_8]
0x14025d5f1  xor     rcx, rsp; StackCookie
0x14025d5f4  call    __security_check_cookie
0x14025d5f9  mov     rbx, [rsp+80h+arg_10]
0x14025d601  add     rsp, 80h
0x14025d608  pop     r15
0x14025d60a  pop     r14
0x14025d60c  pop     r13
0x14025d60e  pop     r12
0x14025d610  pop     rdi
0x14025d611  pop     rsi
0x14025d612  pop     rbp
0x14025d613  retn
0x14025d614  cmp     esi, 0Ch
0x14025d617  jz      short loc_14025D621
0x14025d619  cmp     esi, 1Ah
0x14025d61c  mov     r9b, r13b
0x14025d61f  jnz     short loc_14025D624
0x14025d621  mov     r9b, 1
0x14025d624  mov     rax, [rbp+pv]
0x14025d628  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14025d62c  inc     rcx
0x14025d62f  cmp     [rax+rcx*2], r13w
0x14025d634  jnz     short loc_14025D62C
0x14025d636  mov     [rbp+var_50], rax
0x14025d63a  mov     [rbp+var_48], rcx
0x14025d63e  lea     r8, [rbp+var_30]
0x14025d642  lea     rdx, [rbp+var_50]
0x14025d646  mov     rcx, r14
0x14025d649  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@AEBV?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@0@_N@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(wil::basic_zstring_view<wchar_t>,Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1> const &,bool)
0x14025d64e  nop
0x14025d64f  mov     rcx, [rbp+var_38]
0x14025d653  test    rcx, rcx
0x14025d656  jz      short loc_14025D665
0x14025d658  mov     rax, [rcx]
0x14025d65b  mov     rax, [rax+10h]
0x14025d65f  call    _guard_dispatch_icall
0x14025d664  nop
0x14025d665  jmp     loc_14025D5D0
```
