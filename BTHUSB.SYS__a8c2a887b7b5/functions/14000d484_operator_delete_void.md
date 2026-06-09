# operator delete(void *)

- ea: `0x14000d484`
- end: `0x14000d49f`
- name: `??3@YAXPEAX@Z`
- size: `27`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140019764`
- `0x14001accc`

## callees

- `0x14000d484`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14000d48d`
- `ntoskrnl!ExFreePool` at `0x14000d48d`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePool(a1);
}

```

## disassembly

```asm
0x14000d484  sub     rsp, 28h
0x14000d488  test    rcx, rcx
0x14000d48b  jz      short loc_14000D499
0x14000d48d  call    cs:__imp_ExFreePool
0x14000d494  nop     dword ptr [rax+rax+00h]
0x14000d499  add     rsp, 28h
0x14000d49d  retn
```
