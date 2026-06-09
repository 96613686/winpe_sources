# g_MotionCompZeroMotion(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long)

- ea: `0x180015f60`
- end: `0x180015fc0`
- name: `?g_MotionCompZeroMotion@@YAXPEAE00PEBE11JJ@Z`
- size: `96`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x180015f60`

## pseudocode

```c
void __fastcall g_MotionCompZeroMotion(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const unsigned __int8 *a6,
        int a7,
        int a8)
{
  int v8; // ebx
  int v11; // r11d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax

  v8 = 8;
  do
  {
    v11 = 2;
    do
    {
      *(_QWORD *)a1 = *(_QWORD *)a4;
      v12 = *((_QWORD *)a4 + 1);
      a4 += a7;
      *((_QWORD *)a1 + 1) = v12;
      a1 += a7;
      --v11;
    }
    while ( v11 );
    v13 = *(_QWORD *)a5;
    a5 += a8;
    *(_QWORD *)a2 = v13;
    a2 += a8;
    v14 = *(_QWORD *)a6;
    a6 += a8;
    *(_QWORD *)a3 = v14;
    a3 += a8;
    --v8;
  }
  while ( v8 );
}

```

## disassembly

```asm
0x180015f60  push    rbx
0x180015f62  push    rbp
0x180015f63  push    rsi
0x180015f64  push    rdi
0x180015f65  movsxd  rbp, [rsp+20h+arg_30]
0x180015f6a  mov     ebx, 8
0x180015f6f  movsxd  r10, [rsp+20h+arg_38]
0x180015f74  mov     rdi, [rsp+20h+arg_28]
0x180015f79  mov     rsi, [rsp+20h+arg_20]
0x180015f7e  mov     r11d, 2
0x180015f84  mov     rax, [r9]
0x180015f87  mov     [rcx], rax
0x180015f8a  mov     rax, [r9+8]
0x180015f8e  add     r9, rbp
0x180015f91  mov     [rcx+8], rax
0x180015f95  add     rcx, rbp
0x180015f98  sub     r11d, 1
0x180015f9c  jnz     short loc_180015F84
0x180015f9e  mov     rax, [rsi]
0x180015fa1  add     rsi, r10
0x180015fa4  mov     [rdx], rax
0x180015fa7  add     rdx, r10
0x180015faa  mov     rax, [rdi]
0x180015fad  add     rdi, r10
0x180015fb0  mov     [r8], rax
0x180015fb3  add     r8, r10
0x180015fb6  sub     ebx, 1
0x180015fb9  jnz     short loc_180015F7E
0x180015fbb  pop     rdi
0x180015fbc  pop     rsi
0x180015fbd  pop     rbp
0x180015fbe  pop     rbx
0x180015fbf  retn
```
