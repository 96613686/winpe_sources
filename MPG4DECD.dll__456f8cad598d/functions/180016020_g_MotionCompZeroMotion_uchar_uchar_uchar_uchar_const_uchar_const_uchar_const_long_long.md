# g_MotionCompZeroMotion(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long)

- ea: `0x180016020`
- end: `0x180016080`
- name: `?g_MotionCompZeroMotion@@YAXPEAE00PEBE11JJ@Z`
- size: `96`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x180016020`

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
0x180016020  push    rbx
0x180016022  push    rbp
0x180016023  push    rsi
0x180016024  push    rdi
0x180016025  movsxd  rbp, [rsp+20h+arg_30]
0x18001602a  mov     ebx, 8
0x18001602f  movsxd  r10, [rsp+20h+arg_38]
0x180016034  mov     rdi, [rsp+20h+arg_28]
0x180016039  mov     rsi, [rsp+20h+arg_20]
0x18001603e  mov     r11d, 2
0x180016044  mov     rax, [r9]
0x180016047  mov     [rcx], rax
0x18001604a  mov     rax, [r9+8]
0x18001604e  add     r9, rbp
0x180016051  mov     [rcx+8], rax
0x180016055  add     rcx, rbp
0x180016058  sub     r11d, 1
0x18001605c  jnz     short loc_180016044
0x18001605e  mov     rax, [rsi]
0x180016061  add     rsi, r10
0x180016064  mov     [rdx], rax
0x180016067  add     rdx, r10
0x18001606a  mov     rax, [rdi]
0x18001606d  add     rdi, r10
0x180016070  mov     [r8], rax
0x180016073  add     r8, r10
0x180016076  sub     ebx, 1
0x180016079  jnz     short loc_18001603E
0x18001607b  pop     rdi
0x18001607c  pop     rsi
0x18001607d  pop     rbp
0x18001607e  pop     rbx
0x18001607f  retn
```
