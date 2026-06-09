# CUninstallCbsClient::Finalize(bool *)

- ea: `0x18007c760`
- end: `0x18007c8f1`
- name: `?Finalize@CUninstallCbsClient@@QEAAJPEA_N@Z`
- size: `401`
- prototype: `__int64 __fastcall(CUninstallCbsClient *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007bdb0`

## callees

- `0x18001e51c`
- `0x1800293a0`
- `0x18003e810`
- `0x180044050`
- `0x18007c760`
- `0x1800a0020`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18007c7ef`
- `OLE32!CoTaskMemFree` at `0x18007c8a4`
- `OLE32!CoTaskMemFree` at `0x18007c7ef`
- `OLE32!CoTaskMemFree` at `0x18007c8a4`

## string_xrefs

- `0x18007c7d7`: `onecore\base\cbs\uninstall\cbsclient.cpp`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::Finalize(CUninstallCbsClient *this, bool *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 v12; // rax
  void *v13; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  int v17; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 1);
  v16 = 0;
  pv = 0;
  v17 = 0;
  v5 = **v2;
  InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v16);
  v7 = v5(v2, &GUID_f112757a_565b_4260_bd05_9fa34417349a, InitPointer);
  if ( v7 < 0 )
  {
    v8 = 157;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
      (const char *)(unsigned int)v7,
      v14);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return (unsigned int)v7;
  }
  v10 = v16;
  v11 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 88LL);
  v12 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&pv);
  v7 = v11(v10, v12);
  if ( v7 < 0 )
  {
    v8 = 159;
    goto LABEL_3;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1), &v17);
  if ( v7 < 0 )
  {
    v8 = 161;
    goto LABEL_3;
  }
  CBSWdsLog(0x4000000, 0, 0, "Session Finalized, ID: {}\n");
  v13 = pv;
  *a2 = v17 == 1;
  if ( v13 )
  {
    CoTaskMemFree(v13);
    pv = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return 0;
}

```

## disassembly

```asm
0x18007c760  mov     [rsp-18h+arg_10], rbx
0x18007c765  mov     [rsp-18h+arg_18], rsi
0x18007c76a  push    rbp
0x18007c76b  push    rdi
0x18007c76c  push    r14
0x18007c76e  mov     rbp, rsp
0x18007c771  sub     rsp, 50h
0x18007c775  mov     rax, cs:__security_cookie
0x18007c77c  xor     rax, rsp
0x18007c77f  mov     [rbp+var_8], rax
0x18007c783  mov     rdi, [rcx+8]
0x18007c787  mov     rsi, rcx
0x18007c78a  mov     [rbp+var_18], 0
0x18007c792  lea     rcx, [rbp+var_18]
0x18007c796  mov     [rbp+pv], 0
0x18007c79e  mov     r14, rdx
0x18007c7a1  mov     [rbp+var_10], 0
0x18007c7a8  mov     rax, [rdi]
0x18007c7ab  mov     rbx, [rax]
0x18007c7ae  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c7b3  mov     r8, rax
0x18007c7b6  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x18007c7bd  mov     rax, rbx
0x18007c7c0  mov     rcx, rdi
0x18007c7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c7c8  mov     ebx, eax
0x18007c7ca  test    eax, eax
0x18007c7cc  jns     short loc_18007C81F
0x18007c7ce  mov     edx, 9Dh; void *
0x18007c7d3  mov     rcx, [rbp+18h]; this
0x18007c7d7  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007c7de  mov     r9d, ebx; char *
0x18007c7e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c7e6  mov     rcx, [rbp+pv]; pv
0x18007c7ea  test    rcx, rcx
0x18007c7ed  jz      short loc_18007C803
0x18007c7ef  call    cs:__imp_CoTaskMemFree
0x18007c7f6  nop     dword ptr [rax+rax+00h]
0x18007c7fb  mov     [rbp+pv], 0
0x18007c803  mov     rcx, [rbp+var_18]
0x18007c807  test    rcx, rcx
0x18007c80a  jz      short loc_18007C818
0x18007c80c  mov     rax, [rcx]
0x18007c80f  mov     rax, [rax+10h]
0x18007c813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c818  mov     eax, ebx
0x18007c81a  jmp     loc_18007C8CF
0x18007c81f  mov     rdi, [rbp+var_18]
0x18007c823  lea     rcx, [rbp+pv]
0x18007c827  mov     rax, [rdi]
0x18007c82a  mov     rbx, [rax+58h]
0x18007c82e  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c833  mov     rdx, rax
0x18007c836  mov     rcx, rdi
0x18007c839  mov     rax, rbx
0x18007c83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c841  mov     ebx, eax
0x18007c843  test    eax, eax
0x18007c845  jns     short loc_18007C84E
0x18007c847  mov     edx, 9Fh
0x18007c84c  jmp     short loc_18007C7D3
0x18007c84e  mov     rcx, [rsi+8]
0x18007c852  lea     rdx, [rbp+var_10]
0x18007c856  mov     rax, [rcx]
0x18007c859  mov     rax, [rax+20h]
0x18007c85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c862  mov     ebx, eax
0x18007c864  test    eax, eax
0x18007c866  jns     short loc_18007C872
0x18007c868  mov     edx, 0A1h
0x18007c86d  jmp     loc_18007C7D3
0x18007c872  mov     rax, [rbp+pv]
0x18007c876  lea     r9, aSessionFinaliz; "Session Finalized, ID: {}\n"
0x18007c87d  xor     r8d, r8d
0x18007c880  mov     qword ptr [rsp+50h+var_30], rax
0x18007c885  xor     edx, edx
0x18007c887  mov     ecx, 4000000h
0x18007c88c  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c891  cmp     [rbp+var_10], 1
0x18007c895  mov     rcx, [rbp+pv]; pv
0x18007c899  setz    al
0x18007c89c  mov     [r14], al
0x18007c89f  test    rcx, rcx
0x18007c8a2  jz      short loc_18007C8B8
0x18007c8a4  call    cs:__imp_CoTaskMemFree
0x18007c8ab  nop     dword ptr [rax+rax+00h]
0x18007c8b0  mov     [rbp+pv], 0
0x18007c8b8  mov     rcx, [rbp+var_18]
0x18007c8bc  test    rcx, rcx
0x18007c8bf  jz      short loc_18007C8CD
0x18007c8c1  mov     rax, [rcx]
0x18007c8c4  mov     rax, [rax+10h]
0x18007c8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8cd  xor     eax, eax
0x18007c8cf  mov     rcx, [rbp+var_8]
0x18007c8d3  xor     rcx, rsp; StackCookie
0x18007c8d6  call    __security_check_cookie
0x18007c8db  lea     r11, [rsp+50h+var_s0]
0x18007c8e0  mov     rbx, [r11+30h]
0x18007c8e4  mov     rsi, [r11+38h]
0x18007c8e8  mov     rsp, r11
0x18007c8eb  pop     r14
0x18007c8ed  pop     rdi
0x18007c8ee  pop     rbp
0x18007c8ef  retn
```
