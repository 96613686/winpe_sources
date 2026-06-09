# CoTaskMemAllocWithInit(unsigned __int64,void * *)

- ea: `0x180007d90`
- end: `0x180007dcf`
- name: `?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z`
- size: `63`
- prototype: `__int64 __fastcall(size_t Size, void **)`
- caller_count: `23`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005d8c`
- `0x1800078cc`
- `0x180007c94`
- `0x1800084a0`
- `0x18000b684`
- `0x18001150c`
- `0x1800119a0`
- `0x180011f44`
- `0x1800130bc`
- `0x18001329c`
- `0x1800138a0`
- `0x1800139ec`
- `0x180017340`
- `0x18001742c`
- `0x180017490`
- `0x18001e6a8`
- `0x18001e8e4`
- `0x18001eaec`
- `0x18001ec58`
- `0x18001ed94`
- `0x18001ef18`
- `0x18001f108`
- `0x18001f724`

## callees

- `0x180007d90`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007da0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007da0`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocWithInit(size_t Size, void **a2)
{
  void *v4; // rax

  v4 = CoTaskMemAlloc(Size);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0(v4, 0, Size);
  return 0;
}

```

## disassembly

```asm
0x180007d90  mov     [rsp+arg_0], rbx
0x180007d95  push    rdi
0x180007d96  sub     rsp, 20h
0x180007d9a  mov     rbx, rdx
0x180007d9d  mov     rdi, rcx
0x180007da0  call    cs:__imp_CoTaskMemAlloc
0x180007da6  mov     [rbx], rax
0x180007da9  test    rax, rax
0x180007dac  jz      short loc_180007DC8
0x180007dae  mov     r8, rdi; Size
0x180007db1  xor     edx, edx; Val
0x180007db3  mov     rcx, rax; void *
0x180007db6  call    memset_0
0x180007dbb  xor     eax, eax
0x180007dbd  mov     rbx, [rsp+28h+arg_0]
0x180007dc2  add     rsp, 20h
0x180007dc6  pop     rdi
0x180007dc7  retn
0x180007dc8  mov     eax, 8007000Eh
0x180007dcd  jmp     short loc_180007DBD
```
