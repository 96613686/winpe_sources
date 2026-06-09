# VfsScbGetMapping

- ea: `0x14000d9cc`
- end: `0x14000da25`
- name: `VfsScbGetMapping`
- size: `89`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400061b4`
- `0x140007c7c`
- `0x14000a3c0`
- `0x14000aefc`
- `0x14000b4ec`
- `0x14000c574`
- `0x14000c6fc`
- `0x14000ca28`
- `0x14000cfd8`

## callees

- `0x14000d9cc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000da0a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000da0a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9eb`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9eb`

## pseudocode

```c
volatile signed __int32 *__fastcall VfsScbGetMapping(__int64 a1)
{
  volatile signed __int32 *v3; // rbx

  if ( !*(_QWORD *)(a1 + 144) )
    return 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 120));
  v3 = *(volatile signed __int32 **)(a1 + 144);
  if ( v3 )
    _InterlockedIncrement(v3);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 120));
  return v3;
}

```

## disassembly

```asm
0x14000d9cc  mov     [rsp+arg_0], rbx
0x14000d9d1  push    rdi
0x14000d9d2  sub     rsp, 20h
0x14000d9d6  cmp     qword ptr [rcx+90h], 0
0x14000d9de  mov     rdi, rcx
0x14000d9e1  jnz     short loc_14000D9E7
0x14000d9e3  xor     eax, eax
0x14000d9e5  jmp     short loc_14000DA19
0x14000d9e7  mov     rcx, [rcx+78h]; FastMutex
0x14000d9eb  call    cs:__imp_ExAcquireFastMutex
0x14000d9f2  nop     dword ptr [rax+rax+00h]
0x14000d9f7  mov     rbx, [rdi+90h]
0x14000d9fe  test    rbx, rbx
0x14000da01  jz      short loc_14000DA06
0x14000da03  lock inc dword ptr [rbx]
0x14000da06  mov     rcx, [rdi+78h]; FastMutex
0x14000da0a  call    cs:__imp_ExReleaseFastMutex
0x14000da11  nop     dword ptr [rax+rax+00h]
0x14000da16  mov     rax, rbx
0x14000da19  mov     rbx, [rsp+28h+arg_0]
0x14000da1e  add     rsp, 20h
0x14000da22  pop     rdi
0x14000da23  retn
```
