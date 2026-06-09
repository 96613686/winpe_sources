# MIDL_user_allocate

- ea: `0x1400066f0`
- end: `0x14000670c`
- name: `MIDL_user_allocate`
- size: `28`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `22`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140003af0`
- `0x140003e58`
- `0x1400044d0`
- `0x140006380`
- `0x1400180d0`
- `0x140018340`
- `0x140018540`
- `0x140018880`
- `0x140019210`
- `0x14001a69c`
- `0x14001a778`
- `0x14001a828`
- `0x14001b834`
- `0x14001bad8`
- `0x14001c4a8`
- `0x14001c788`
- `0x14001ced8`
- `0x14001d584`
- `0x14001e3c8`
- `0x1400353e0`
- `0x140036570`
- `0x140036cbc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140006705`

## pseudocode

```c
void *__stdcall MIDL_user_allocate(size_t size)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, size);
}

```

## disassembly

```asm
0x1400066f0  mov     rax, gs:60h
0x1400066f9  mov     r8, rcx
0x1400066fc  mov     edx, 8
0x140006701  mov     rcx, [rax+30h]
0x140006705  jmp     cs:__imp_RtlAllocateHeap
```
