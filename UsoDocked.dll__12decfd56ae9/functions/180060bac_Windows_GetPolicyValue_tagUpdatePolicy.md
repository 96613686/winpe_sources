# Windows::GetPolicyValue(tagUpdatePolicy)

- ea: `0x180060bac`
- end: `0x180060cd5`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@W4tagUpdatePolicy@@@Z`
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
- `0x180060bac`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060c04`
- `OLEAUT32!__imp_VariantClear` at `0x180060c79`
- `OLEAUT32!__imp_VariantClear` at `0x180060c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060c89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060c89`

## string_xrefs

- `0x180060c4a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`

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
  int v10; // [rsp+20h] [rbp-30h]
  _BYTE v11[16]; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v15; // [rsp+98h] [rbp+48h] BYREF

  pv = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v15);
  v4 = v15;
  v5 = *(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v15 + 40LL);
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
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v15 + 24LL))(v15, a2, v11);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43D,
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
0x180060bac  mov     [rsp-28h+arg_0], rbx
0x180060bb1  mov     [rsp-28h+arg_8], rsi
0x180060bb6  push    rbp
0x180060bb7  push    rdi
0x180060bb8  push    r12
0x180060bba  push    r14
0x180060bbc  push    r15
0x180060bbe  mov     rbp, rsp
0x180060bc1  sub     rsp, 50h
0x180060bc5  mov     r15d, edx
0x180060bc8  mov     rdi, rcx
0x180060bcb  mov     [rbp+pv], 0
0x180060bd3  lea     rcx, [rbp+arg_18]
0x180060bd7  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x180060bdc  nop
0x180060bdd  mov     r14, [rbp+arg_18]
0x180060be1  mov     rax, [r14]
0x180060be4  mov     r12, [rax+28h]
0x180060be8  mov     rsi, [rbp+pv]
0x180060bec  test    rsi, rsi
0x180060bef  jz      short loc_180060C0A
0x180060bf1  call    cs:__imp_GetLastError
0x180060bf7  mov     ebx, eax
0x180060bf9  mov     rcx, rsi; pv
0x180060bfc  call    cs:__imp_CoTaskMemFree
0x180060c02  mov     ecx, ebx; dwErrCode
0x180060c04  call    cs:__imp_SetLastError
0x180060c0a  mov     [rbp+pv], 0
0x180060c12  lea     r8, [rbp+pv]
0x180060c16  mov     edx, r15d
0x180060c19  mov     rcx, r14
0x180060c1c  mov     rax, r12
0x180060c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c24  test    eax, eax
0x180060c26  js      short loc_180060C5B
0x180060c28  mov     rcx, [rbp+arg_18]
0x180060c2c  mov     rax, [rcx]
0x180060c2f  lea     r8, [rbp+var_28]
0x180060c33  mov     edx, r15d
0x180060c36  mov     rax, [rax+18h]
0x180060c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c3f  mov     rcx, [rbp+28h]; this
0x180060c43  test    eax, eax
0x180060c45  jns     short loc_180060CAB
0x180060c47  mov     r9d, eax; char *
0x180060c4a  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180060c51  mov     edx, 43Dh; void *
0x180060c56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060c5b  mov     byte ptr [rdi+20h], 0
0x180060c5f  mov     rcx, [rbp+arg_18]
0x180060c63  test    rcx, rcx
0x180060c66  jz      short loc_180060C75
0x180060c68  mov     rax, [rcx]
0x180060c6b  mov     rax, [rax+10h]
0x180060c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c74  nop
0x180060c75  lea     rcx, [rbp+pvarg]; pvarg
0x180060c79  call    cs:__imp_VariantClear
0x180060c7f  nop
0x180060c80  mov     rcx, [rbp+pv]; pv
0x180060c84  test    rcx, rcx
0x180060c87  jz      short loc_180060C8F
0x180060c89  call    cs:__imp_CoTaskMemFree
0x180060c8f  mov     rax, rdi
0x180060c92  lea     r11, [rsp+50h+var_s0]
0x180060c97  mov     rbx, [r11+30h]
0x180060c9b  mov     rsi, [r11+38h]
0x180060c9f  mov     rsp, r11
0x180060ca2  pop     r15
0x180060ca4  pop     r14
0x180060ca6  pop     r12
0x180060ca8  pop     rdi
0x180060ca9  pop     rbp
0x180060caa  retn
0x180060cab  lea     r8, [rbp+var_28]
0x180060caf  mov     rdx, [rbp+pv]
0x180060cb3  mov     rcx, rdi
0x180060cb6  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEBGAEBV?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@0@@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(ushort const *,Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1> const &)
0x180060cbb  nop
0x180060cbc  mov     rcx, [rbp+arg_18]
0x180060cc0  test    rcx, rcx
0x180060cc3  jz      short loc_180060CD2
0x180060cc5  mov     rax, [rcx]
0x180060cc8  mov     rax, [rax+10h]
0x180060ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cd1  nop
0x180060cd2  jmp     short loc_180060C75
```
