# VfsUpdateFileSizesWorker

- ea: `0x14000b1d0`
- end: `0x14000b1e8`
- name: `VfsUpdateFileSizesWorker`
- size: `24`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000f5b4`

## pseudocode

```c
__int64 __fastcall VfsUpdateFileSizesWorker(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        __int64 CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  VfsUpdateFileSizes(CompletionContext, (__int64)FltObjects->FileObject);
  return 0;
}

```

## disassembly

```asm
0x14000b1d0  sub     rsp, 28h
0x14000b1d4  mov     rdx, [rdx+20h]
0x14000b1d8  mov     rcx, r8
0x14000b1db  call    VfsUpdateFileSizes
0x14000b1e0  xor     eax, eax
0x14000b1e2  add     rsp, 28h
0x14000b1e6  retn
```
