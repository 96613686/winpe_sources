# BfUpdateFileSizesWorker

- ea: `0x140006360`
- end: `0x140006378`
- name: `BfUpdateFileSizesWorker`
- size: `24`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006380`

## pseudocode

```c
__int64 __fastcall BfUpdateFileSizesWorker(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        __int64 CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  BfUpdateFileSizes(CompletionContext, (__int64)FltObjects->FileObject);
  return 0;
}

```

## disassembly

```asm
0x140006360  sub     rsp, 28h
0x140006364  mov     rdx, [rdx+20h]
0x140006368  mov     rcx, r8
0x14000636b  call    BfUpdateFileSizes
0x140006370  xor     eax, eax
0x140006372  add     rsp, 28h
0x140006376  retn
```
