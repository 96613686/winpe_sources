# CUninstallCbsClient::Finalize(bool *)

- ea: `0x18007bf48`
- end: `0x18007c0a4`
- name: `?Finalize@CUninstallCbsClient@@QEAAJPEA_N@Z`
- size: `348`
- prototype: `__int64 __fastcall(CUninstallCbsClient *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ba20`

## callees

- `0x180024c80`
- `0x18002d2b0`
- `0x180042bac`
- `0x18007bf48`
- `0x18009e020`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18007c057`
- `OLE32!CoTaskMemFree` at `0x18007c057`

## string_xrefs

- `0x18007c021`: `Failed uninstall`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::Finalize(CUninstallCbsClient *this, bool *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 v12; // rax
  int v13; // eax
  int v15; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF

  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 1);
  v17 = 0;
  pv = 0;
  v15 = 0;
  v5 = **v2;
  InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v17);
  v7 = v5(v2, &GUID_f112757a_565b_4260_bd05_9fa34417349a, InitPointer);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "Failed querying ICbsSession10 interface.";
LABEL_3:
    CBSWdsLog(0x4000000, (unsigned int)v7, 1, v9);
    goto LABEL_10;
  }
  v10 = v17;
  v11 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 88LL);
  v12 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&pv);
  v7 = v11(v10, v12);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "Failed to get session id.";
    goto LABEL_3;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1), &v15);
  v8 = v13;
  if ( v13 >= 0 )
  {
    CBSWdsLog(0x4000000, 0, 0, "Session Finalized, ID: %ws\n", pv);
    *a2 = v15 == 1;
  }
  else
  {
    CBSWdsLog(0x4000000, (unsigned int)v13, 1, "Failed uninstall");
  }
LABEL_10:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return v8;
}

```

## disassembly

```asm
0x18007bf48  mov     [rsp-18h+arg_10], rbx
0x18007bf4d  mov     [rsp-18h+arg_18], rsi
0x18007bf52  push    rbp
0x18007bf53  push    rdi
0x18007bf54  push    r14
0x18007bf56  mov     rbp, rsp
0x18007bf59  sub     rsp, 50h
0x18007bf5d  mov     rax, cs:__security_cookie
0x18007bf64  xor     rax, rsp
0x18007bf67  mov     [rbp+var_8], rax
0x18007bf6b  mov     rdi, [rcx+8]
0x18007bf6f  mov     rsi, rcx
0x18007bf72  mov     [rbp+var_10], 0
0x18007bf7a  lea     rcx, [rbp+var_10]
0x18007bf7e  mov     [rbp+pv], 0
0x18007bf86  mov     r14, rdx
0x18007bf89  mov     [rbp+var_20], 0
0x18007bf90  mov     rax, [rdi]
0x18007bf93  mov     rbx, [rax]
0x18007bf96  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007bf9b  mov     r8, rax
0x18007bf9e  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x18007bfa5  mov     rax, rbx
0x18007bfa8  mov     rcx, rdi
0x18007bfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfb0  mov     ebx, eax
0x18007bfb2  test    eax, eax
0x18007bfb4  jns     short loc_18007BFD1
0x18007bfb6  lea     r9, aFailedQuerying; "Failed querying ICbsSession10 interface"...
0x18007bfbd  mov     ecx, 4000000h
0x18007bfc2  mov     edx, eax
0x18007bfc4  mov     r8d, 1
0x18007bfca  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007bfcf  jmp     short loc_18007C04E
0x18007bfd1  mov     rdi, [rbp+var_10]
0x18007bfd5  lea     rcx, [rbp+pv]
0x18007bfd9  mov     rax, [rdi]
0x18007bfdc  mov     rbx, [rax+58h]
0x18007bfe0  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007bfe5  mov     rdx, rax
0x18007bfe8  mov     rcx, rdi
0x18007bfeb  mov     rax, rbx
0x18007bfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bff3  mov     ebx, eax
0x18007bff5  test    eax, eax
0x18007bff7  jns     short loc_18007C002
0x18007bff9  lea     r9, aFailedToGetSes; "Failed to get session id."
0x18007c000  jmp     short loc_18007BFBD
0x18007c002  mov     rcx, [rsi+8]
0x18007c006  lea     rdx, [rbp+var_20]
0x18007c00a  mov     rax, [rcx]
0x18007c00d  mov     rax, [rax+20h]
0x18007c011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c016  mov     ebx, eax
0x18007c018  mov     ecx, 4000000h
0x18007c01d  test    eax, eax
0x18007c01f  jns     short loc_18007C02A
0x18007c021  lea     r9, aFailedUninstal; "Failed uninstall"
0x18007c028  jmp     short loc_18007BFC2
0x18007c02a  mov     rax, [rbp+pv]
0x18007c02e  lea     r9, aSessionFinaliz; "Session Finalized, ID: %ws\n"
0x18007c035  xor     r8d, r8d
0x18007c038  mov     [rsp+50h+var_30], rax
0x18007c03d  xor     edx, edx
0x18007c03f  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c044  cmp     [rbp+var_20], 1
0x18007c048  setz    al
0x18007c04b  mov     [r14], al
0x18007c04e  mov     rcx, [rbp+pv]; pv
0x18007c052  test    rcx, rcx
0x18007c055  jz      short loc_18007C06B
0x18007c057  call    cs:__imp_CoTaskMemFree
0x18007c05e  nop     dword ptr [rax+rax+00h]
0x18007c063  mov     [rbp+pv], 0
0x18007c06b  mov     rcx, [rbp+var_10]
0x18007c06f  test    rcx, rcx
0x18007c072  jz      short loc_18007C080
0x18007c074  mov     rax, [rcx]
0x18007c077  mov     rax, [rax+10h]
0x18007c07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c080  mov     eax, ebx
0x18007c082  mov     rcx, [rbp+var_8]
0x18007c086  xor     rcx, rsp; StackCookie
0x18007c089  call    __security_check_cookie
0x18007c08e  lea     r11, [rsp+50h+var_s0]
0x18007c093  mov     rbx, [r11+30h]
0x18007c097  mov     rsi, [r11+38h]
0x18007c09b  mov     rsp, r11
0x18007c09e  pop     r14
0x18007c0a0  pop     rdi
0x18007c0a1  pop     rbp
0x18007c0a2  retn
```
