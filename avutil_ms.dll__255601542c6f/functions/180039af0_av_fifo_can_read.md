# av_fifo_can_read

- ea: `0x180039af0`
- end: `0x180039b18`
- name: `av_fifo_can_read`
- size: `40`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18002aad0`
- `0x180033780`
- `0x180033790`
- `0x180039b20`
- `0x180039b40`
- `0x180039e70`
- `0x180039f88`
- `0x180051aa0`
- `0x180051bf0`
- `0x180051c30`

## callees

- `0x180039af0`

## pseudocode

```c
unsigned __int64 __fastcall av_fifo_can_read(__int64 a1)
{
  unsigned __int64 v1; // r8
  unsigned __int64 v2; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 > v1 || *(_DWORD *)(a1 + 40) )
    return v2 - v1;
  _mm_lfence();
  return v2 + *(_QWORD *)(a1 + 16) - v1;
}

```

## disassembly

```asm
0x180039af0  mov     r8, [rcx+18h]
0x180039af4  mov     rdx, [rcx+20h]
0x180039af8  cmp     rdx, r8
0x180039afb  ja      short loc_180039B11
0x180039afd  cmp     dword ptr [rcx+28h], 0
0x180039b01  jnz     short loc_180039B11
0x180039b03  lfence
0x180039b06  mov     rax, [rcx+10h]
0x180039b0a  sub     rax, r8
0x180039b0d  add     rax, rdx
0x180039b10  retn
0x180039b11  sub     rdx, r8
0x180039b14  mov     rax, rdx
0x180039b17  retn
```
