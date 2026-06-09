# MapiIdleThreadMain(void *)

- ea: `0x18002ee50`
- end: `0x18002ee7c`
- name: `?MapiIdleThreadMain@@YAKPEAX@Z`
- size: `44`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002f9cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ee59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ee59`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18002ee69`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18002ee69`

## string_xrefs

- `0x18002ee62`: `MapiIdleThreadMain`

## pseudocode

```c
ULONG __fastcall MapiIdleThreadMain(CMapiManager *Parameter)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"MapiIdleThreadMain");
  return CMapiManager::RunMapiIdleThread(Parameter);
}

```

## disassembly

```asm
0x18002ee50  push    rbx
0x18002ee52  sub     rsp, 20h
0x18002ee56  mov     rbx, rcx
0x18002ee59  call    cs:__imp_GetCurrentThread
0x18002ee5f  mov     rcx, rax; hThread
0x18002ee62  lea     rdx, ThreadDescription; "MapiIdleThreadMain"
0x18002ee69  call    cs:__imp_SetThreadDescription
0x18002ee6f  mov     rcx, rbx; this
0x18002ee72  add     rsp, 20h
0x18002ee76  pop     rbx
0x18002ee77  jmp     ?RunMapiIdleThread@CMapiManager@@QEAAKXZ; CMapiManager::RunMapiIdleThread(void)
```
