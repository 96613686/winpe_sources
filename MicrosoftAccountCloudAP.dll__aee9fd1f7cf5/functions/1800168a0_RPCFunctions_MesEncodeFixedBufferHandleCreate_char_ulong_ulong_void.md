# RPCFunctions::MesEncodeFixedBufferHandleCreate(char *,ulong,ulong *,void * *)

- ea: `0x1800168a0`
- end: `0x1800168bb`
- name: `?MesEncodeFixedBufferHandleCreate@RPCFunctions@@UEAAJPEADKPEAKPEAPEAX@Z`
- size: `27`
- prototype: `__int64 __fastcall(RPCFunctions *__hidden this, char *, unsigned int, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x1800168b4`

## pseudocode

```c
RPC_STATUS __fastcall RPCFunctions::MesEncodeFixedBufferHandleCreate(
        RPCFunctions *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4,
        void **a5)
{
  return MesEncodeFixedBufferHandleCreate(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800168a0  mov     rax, r9
0x1800168a3  mov     r10d, r8d
0x1800168a6  mov     r9, [rsp+arg_20]
0x1800168ab  mov     rcx, rdx
0x1800168ae  mov     r8, rax
0x1800168b1  mov     edx, r10d
0x1800168b4  jmp     cs:__imp_MesEncodeFixedBufferHandleCreate
```
