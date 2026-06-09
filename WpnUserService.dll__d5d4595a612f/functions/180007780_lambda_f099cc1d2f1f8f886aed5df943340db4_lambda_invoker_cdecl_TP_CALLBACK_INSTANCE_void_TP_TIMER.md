# _lambda_f099cc1d2f1f8f886aed5df943340db4_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180007780`
- end: `0x1800077ba`
- name: `?_lambda_invoker_cdecl_@_lambda_f099cc1d2f1f8f886aed5df943340db4_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `58`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007793`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007789`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007789`
- `faultrep!ReportCoreHang` at `0x1800077ae`
- `faultrep!ReportCoreHang` at `0x1800077ae`

## pseudocode

```c
void __fastcall _lambda_f099cc1d2f1f8f886aed5df943340db4_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  unsigned int v3; // ebx
  DWORD CurrentProcessId; // [rsp+48h] [rbp+20h] BYREF

  v3 = (unsigned int)Context;
  if ( !IsDebuggerPresent() )
  {
    CurrentProcessId = GetCurrentProcessId();
    ReportCoreHang(&CurrentProcessId, 1, v3, 32);
  }
}

```

## disassembly

```asm
0x180007780  push    rbx
0x180007782  sub     rsp, 20h
0x180007786  mov     rbx, rdx
0x180007789  call    cs:__imp_IsDebuggerPresent
0x18000778f  test    eax, eax
0x180007791  jnz     short loc_1800077B4
0x180007793  call    cs:__imp_GetCurrentProcessId
0x180007799  mov     edx, 1
0x18000779e  lea     rcx, [rsp+28h+arg_18]
0x1800077a3  mov     r8d, ebx
0x1800077a6  mov     [rsp+28h+arg_18], eax
0x1800077aa  lea     r9d, [rdx+1Fh]
0x1800077ae  call    cs:__imp_ReportCoreHang
0x1800077b4  add     rsp, 20h
0x1800077b8  pop     rbx
0x1800077b9  retn
```
