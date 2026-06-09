# av_realloc

- ea: `0x180044d10`
- end: `0x180044d48`
- name: `av_realloc`
- size: `56`
- prototype: `void *__fastcall(void *, unsigned __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d2b0`
- `0x18002e3c0`
- `0x18002e790`
- `0x18002f030`
- `0x180036210`
- `0x1800446a0`
- `0x180044770`
- `0x180044840`
- `0x180044920`
- `0x180044d50`
- `0x180044d90`
- `0x180044df0`
- `0x180044f00`
- `0x180044f60`

## callees

- `0x180044d10`
- `0x180078dc0`

## pseudocode

```c
void *__fastcall av_realloc(void *a1, unsigned __int64 a2)
{
  __int64 v3; // rdx
  signed __int32 v5[10]; // [rsp+0h] [rbp-28h] BYREF

  v3 = 0;
  _InterlockedOr(v5, 0);
  if ( a2 > qword_1800A9028 )
    return 0;
  _mm_lfence();
  LOBYTE(v3) = a2 == 0;
  return aligned_realloc(a1, a2 + v3, 0x40u);
}

```

## disassembly

```asm
0x180044d10  sub     rsp, 28h
0x180044d14  mov     rax, rdx
0x180044d17  xor     edx, edx
0x180044d19  lock or [rsp+28h+var_28], edx
0x180044d1d  cmp     rax, cs:qword_1800A9028
0x180044d24  jbe     short loc_180044D2D
0x180044d26  xor     eax, eax
0x180044d28  add     rsp, 28h
0x180044d2c  retn
0x180044d2d  lfence
0x180044d30  test    rax, rax
0x180044d33  mov     r8d, 40h ; '@'; Alignment
0x180044d39  setz    dl
0x180044d3c  add     rdx, rax; Size
0x180044d3f  add     rsp, 28h
0x180044d43  jmp     _aligned_realloc
```
