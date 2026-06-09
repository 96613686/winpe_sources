# MmAllocate(unsigned __int64)

- ea: `0x18000e61c`
- end: `0x18000e666`
- name: `?MmAllocate@@YAPEAX_K@Z`
- size: `74`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180005528`
- `0x180006b94`
- `0x1800071c4`
- `0x18000b04c`
- `0x18000b0cc`
- `0x18000b11c`
- `0x18000b728`
- `0x18000b98c`
- `0x18000d3e0`
- `0x18000e610`
- `0x18000fd38`

## callees

- `0x18000e61c`
- `0x18000e66c`
- `0x18000e6a0`

## import_xrefs

- `msvcrt!malloc` at `0x18000e625`
- `msvcrt!malloc` at `0x18000e625`

## pseudocode

```c
void *__fastcall MmAllocate(size_t a1)
{
  void *result; // rax
  __int64 v3; // r8

  result = malloc(a1);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v3, a1);
    MmThrowBadAlloc();
  }
  return result;
}

```

## disassembly

```asm
0x18000e61c  push    rbx
0x18000e61e  sub     rsp, 20h
0x18000e622  mov     rbx, rcx
0x18000e625  call    cs:__imp_malloc
0x18000e62b  test    rax, rax
0x18000e62e  jz      short loc_18000E636
0x18000e630  add     rsp, 20h
0x18000e634  pop     rbx
0x18000e635  retn
0x18000e636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e63d  lea     rax, WPP_GLOBAL_Control
0x18000e644  cmp     rcx, rax
0x18000e647  jz      short loc_18000E660
0x18000e649  test    byte ptr [rcx+1Ch], 1
0x18000e64d  jz      short loc_18000E660
0x18000e64f  mov     rcx, [rcx+10h]
0x18000e653  mov     edx, 0Bh
0x18000e658  mov     r9, rbx
0x18000e65b  call    WPP_SF_P
0x18000e660  call    ?MmThrowBadAlloc@@YAXXZ; MmThrowBadAlloc(void)
```
