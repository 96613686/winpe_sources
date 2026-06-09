# RPCFunctions::MesDecodeBufferHandleCreate(char *,ulong,void * *)

- ea: `0x180016880`
- end: `0x180016892`
- name: `?MesDecodeBufferHandleCreate@RPCFunctions@@UEAAJPEADKPEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(RPCFunctions *__hidden this, char *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001688b`

## pseudocode

```c
RPC_STATUS __fastcall RPCFunctions::MesDecodeBufferHandleCreate(
        RPCFunctions *this,
        char *a2,
        unsigned int a3,
        void **a4)
{
  return MesDecodeBufferHandleCreate(a2, a3, a4);
}

```

## disassembly

```asm
0x180016880  mov     eax, r8d
0x180016883  mov     rcx, rdx
0x180016886  mov     edx, eax
0x180016888  mov     r8, r9
0x18001688b  jmp     cs:__imp_MesDecodeBufferHandleCreate
```
