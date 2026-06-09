# ReleaseInterface(IUnknown *)

- ea: `0x1400055e0`
- end: `0x1400055fb`
- name: `?ReleaseInterface@@YAXPEAUIUnknown@@@Z`
- size: `27`
- prototype: `void __fastcall(struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000366c`
- `0x140003774`
- `0x1400044f0`
- `0x140004850`

## callees

- `0x1400055e0`
- `0x140006590`

## pseudocode

```c
void __fastcall ReleaseInterface(struct IUnknown *a1)
{
  if ( a1 )
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
}

```

## disassembly

```asm
0x1400055e0  sub     rsp, 28h
0x1400055e4  test    rcx, rcx
0x1400055e7  jz      short loc_1400055F6
0x1400055e9  mov     rax, [rcx]
0x1400055ec  mov     rax, [rax+10h]
0x1400055f0  call    cs:__guard_dispatch_icall_fptr
0x1400055f6  add     rsp, 28h
0x1400055fa  retn
```
