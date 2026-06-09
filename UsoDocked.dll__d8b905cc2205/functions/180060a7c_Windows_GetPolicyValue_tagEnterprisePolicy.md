# Windows::GetPolicyValue(tagEnterprisePolicy)

- ea: `0x180060a7c`
- end: `0x180060ba5`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@W4tagEnterprisePolicy@@@Z`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180060ce0`
- `0x1800615d0`

## callees

- `0x1800239c4`
- `0x18005edc4`
- `0x18005ee34`
- `0x180060a7c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ac1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ad4`
- `OLEAUT32!__imp_VariantClear` at `0x180060b49`
- `OLEAUT32!__imp_VariantClear` at `0x180060b49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b59`

## string_xrefs

- `0x180060b1a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::GetPolicyValue(__int64 a1, unsigned int a2)
{
  __int64 v4; // r14
  int (__fastcall *v5)(__int64, _QWORD, LPVOID *); // r12
  void *v6; // rsi
  DWORD LastError; // ebx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-40h]
  _BYTE v11[16]; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+48h] BYREF

  pv = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v15);
  v4 = v15;
  v5 = *(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v15 + 48LL);
  v6 = pv;
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(v6);
    SetLastError(LastError);
  }
  pv = 0;
  if ( v5(v4, a2, &pv) < 0 )
    goto LABEL_6;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, a2, v11);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x44A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
      (const char *)(unsigned int)v8,
      v10);
LABEL_6:
    *(_BYTE *)(a1 + 32) = 0;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_8;
  }
  Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(a1, pv, v11);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_8:
  VariantClear(&pvarg);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x180060a7c  mov     [rsp-28h+arg_0], rbx
0x180060a81  mov     [rsp-28h+arg_8], rsi
0x180060a86  push    rbp
0x180060a87  push    rdi
0x180060a88  push    r12
0x180060a8a  push    r14
0x180060a8c  push    r15
0x180060a8e  mov     rbp, rsp
0x180060a91  sub     rsp, 60h
0x180060a95  mov     r15d, edx
0x180060a98  mov     rdi, rcx
0x180060a9b  mov     [rbp+pv], 0
0x180060aa3  lea     rcx, [rbp+arg_18]
0x180060aa7  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x180060aac  nop
0x180060aad  mov     r14, [rbp+arg_18]
0x180060ab1  mov     rax, [r14]
0x180060ab4  mov     r12, [rax+30h]
0x180060ab8  mov     rsi, [rbp+pv]
0x180060abc  test    rsi, rsi
0x180060abf  jz      short loc_180060ADA
0x180060ac1  call    cs:__imp_GetLastError
0x180060ac7  mov     ebx, eax
0x180060ac9  mov     rcx, rsi; pv
0x180060acc  call    cs:__imp_CoTaskMemFree
0x180060ad2  mov     ecx, ebx; dwErrCode
0x180060ad4  call    cs:__imp_SetLastError
0x180060ada  mov     [rbp+pv], 0
0x180060ae2  lea     r8, [rbp+pv]
0x180060ae6  mov     edx, r15d
0x180060ae9  mov     rcx, r14
0x180060aec  mov     rax, r12
0x180060aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060af4  test    eax, eax
0x180060af6  js      short loc_180060B2B
0x180060af8  mov     rcx, [rbp+arg_18]
0x180060afc  mov     rax, [rcx]
0x180060aff  lea     r8, [rbp+var_38]
0x180060b03  mov     edx, r15d
0x180060b06  mov     rax, [rax+20h]
0x180060b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b0f  mov     rcx, [rbp+28h]; this
0x180060b13  test    eax, eax
0x180060b15  jns     short loc_180060B7B
0x180060b17  mov     r9d, eax; char *
0x180060b1a  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180060b21  mov     edx, 44Ah; void *
0x180060b26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060b2b  mov     byte ptr [rdi+20h], 0
0x180060b2f  mov     rcx, [rbp+arg_18]
0x180060b33  test    rcx, rcx
0x180060b36  jz      short loc_180060B45
0x180060b38  mov     rax, [rcx]
0x180060b3b  mov     rax, [rax+10h]
0x180060b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b44  nop
0x180060b45  lea     rcx, [rbp+pvarg]; pvarg
0x180060b49  call    cs:__imp_VariantClear
0x180060b4f  nop
0x180060b50  mov     rcx, [rbp+pv]; pv
0x180060b54  test    rcx, rcx
0x180060b57  jz      short loc_180060B5F
0x180060b59  call    cs:__imp_CoTaskMemFree
0x180060b5f  mov     rax, rdi
0x180060b62  lea     r11, [rsp+60h+var_s0]
0x180060b67  mov     rbx, [r11+30h]
0x180060b6b  mov     rsi, [r11+38h]
0x180060b6f  mov     rsp, r11
0x180060b72  pop     r15
0x180060b74  pop     r14
0x180060b76  pop     r12
0x180060b78  pop     rdi
0x180060b79  pop     rbp
0x180060b7a  retn
0x180060b7b  lea     r8, [rbp+var_38]
0x180060b7f  mov     rdx, [rbp+pv]
0x180060b83  mov     rcx, rdi
0x180060b86  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEBGAEBV?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@0@@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(ushort const *,Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1> const &)
0x180060b8b  nop
0x180060b8c  mov     rcx, [rbp+arg_18]
0x180060b90  test    rcx, rcx
0x180060b93  jz      short loc_180060BA2
0x180060b95  mov     rax, [rcx]
0x180060b98  mov     rax, [rax+10h]
0x180060b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ba1  nop
0x180060ba2  jmp     short loc_180060B45
```
