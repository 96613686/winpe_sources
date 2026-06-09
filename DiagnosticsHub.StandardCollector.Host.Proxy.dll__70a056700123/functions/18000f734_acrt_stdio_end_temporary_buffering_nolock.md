# __acrt_stdio_end_temporary_buffering_nolock

- ea: `0x18000f734`
- end: `0x18000f771`
- name: `__acrt_stdio_end_temporary_buffering_nolock`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800418d8`
- `0x180041928`
- `0x180041a4c`
- `0x180041b78`
- `0x180041cb4`
- `0x180041df0`
- `0x180041f50`

## callees

- `0x18000f1a0`
- `0x18000f734`

## pseudocode

```c
__int64 __fastcall _acrt_stdio_end_temporary_buffering_nolock(char a1, __int64 a2)
{
  __int64 result; // rax

  if ( a1 )
  {
    result = *(_DWORD *)(a2 + 20) >> 9;
    if ( (*(_DWORD *)(a2 + 20) & 0x200) != 0 )
    {
      result = _acrt_stdio_flush_nolock((FILE *)a2);
      _InterlockedAnd((volatile signed __int32 *)(a2 + 20), 0xFFFFFD7F);
      *(_DWORD *)(a2 + 32) = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)a2 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f734  test    cl, cl
0x18000f736  jz      short locret_18000F770
0x18000f738  push    rbx
0x18000f739  sub     rsp, 20h
0x18000f73d  mov     eax, [rdx+14h]
0x18000f740  mov     rbx, rdx
0x18000f743  shr     eax, 9
0x18000f746  nop
0x18000f747  test    al, 1
0x18000f749  jz      short loc_18000F76B
0x18000f74b  mov     rdx, r8
0x18000f74e  mov     rcx, rbx; Stream
0x18000f751  call    __acrt_stdio_flush_nolock
0x18000f756  lock and dword ptr [rbx+14h], 0FFFFFD7Fh
0x18000f75e  and     dword ptr [rbx+20h], 0
0x18000f762  and     qword ptr [rbx+8], 0
0x18000f767  and     qword ptr [rbx], 0
0x18000f76b  add     rsp, 20h
0x18000f76f  pop     rbx
0x18000f770  retn
```
