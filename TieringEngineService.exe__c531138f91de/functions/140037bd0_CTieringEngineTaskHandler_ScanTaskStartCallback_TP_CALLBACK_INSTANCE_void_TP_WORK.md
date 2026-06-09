# CTieringEngineTaskHandler::ScanTaskStartCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140037bd0`
- end: `0x140037c25`
- name: `?ScanTaskStartCallback@CTieringEngineTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `85`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, CTieringEngineTaskHandler *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x140037940`
- `0x140037bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140037bfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140037bfa`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x140037c0c`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x140037c0c`

## pseudocode

```c
void __fastcall CTieringEngineTaskHandler::ScanTaskStartCallback(
        PTP_CALLBACK_INSTANCE Instance,
        CTieringEngineTaskHandler *Context,
        PTP_WORK Work)
{
  HMODULE phModule; // [rsp+48h] [rbp+20h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(4u, (LPCWSTR)CTieringEngineTaskHandler::ScanTaskStartCallback, &phModule) )
    FreeLibraryWhenCallbackReturns(Instance, phModule);
  CTieringEngineTaskHandler::ScanTaskStart(Context);
}

```

## disassembly

```asm
0x140037bd0  mov     [rsp+arg_0], rbx
0x140037bd5  push    rdi
0x140037bd6  sub     rsp, 20h
0x140037bda  mov     rbx, rdx
0x140037bdd  mov     [rsp+28h+phModule], 0
0x140037be6  mov     rdi, rcx
0x140037be9  lea     rdx, ?ScanTaskStartCallback@CTieringEngineTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x140037bf0  mov     ecx, 4; dwFlags
0x140037bf5  lea     r8, [rsp+28h+phModule]; phModule
0x140037bfa  call    cs:__imp_GetModuleHandleExW
0x140037c00  test    eax, eax
0x140037c02  jz      short loc_140037C12
0x140037c04  mov     rdx, [rsp+28h+phModule]; mod
0x140037c09  mov     rcx, rdi; pci
0x140037c0c  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x140037c12  mov     rcx, rbx; this
0x140037c15  call    ?ScanTaskStart@CTieringEngineTaskHandler@@AEAAXXZ; CTieringEngineTaskHandler::ScanTaskStart(void)
0x140037c1a  mov     rbx, [rsp+28h+arg_0]
0x140037c1f  add     rsp, 20h
0x140037c23  pop     rdi
0x140037c24  retn
```
