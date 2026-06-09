# messages::write<wchar_t const *>(uchar * &,uchar const *,ulong &,wchar_t const * const,unsigned __int64)

- ea: `0x140010130`
- end: `0x140010182`
- name: `??$write@PEB_W@messages@@YAXAEAPEAEPEBEAEAKQEB_W_K@Z`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ff30`
- `0x140010f38`
- `0x140011478`
- `0x140014dcc`

## callees

- `0x140010130`
- `0x140015c00`

## pseudocode

```c
char *__fastcall messages::write<wchar_t const *>(void **a1, int a2, _DWORD *a3, const void *a4, size_t Size)
{
  char *v8; // rbx
  char *result; // rax
  int v10; // ecx

  if ( a4 && Size )
  {
    v8 = (char *)*a1;
    memmove(*a1, a4, Size);
    result = &v8[Size];
    v10 = *(_DWORD *)a1 - a2;
    *a1 = &v8[Size];
  }
  else
  {
    v10 = 0;
  }
  *a3 = v10;
  return result;
}

```

## disassembly

```asm
0x140010130  push    rbx
0x140010132  push    rbp
0x140010133  push    rsi
0x140010134  push    rdi
0x140010135  push    r14
0x140010137  sub     rsp, 20h
0x14001013b  mov     rsi, r8
0x14001013e  mov     rbp, rdx
0x140010141  mov     r14, rcx
0x140010144  test    r9, r9
0x140010147  jz      short loc_140010172
0x140010149  mov     rdi, [rsp+48h+Size]
0x14001014e  test    rdi, rdi
0x140010151  jz      short loc_140010172
0x140010153  mov     rbx, [rcx]
0x140010156  mov     r8, rdi; Size
0x140010159  mov     rcx, rbx; void *
0x14001015c  mov     rdx, r9; Src
0x14001015f  call    memmove
0x140010164  mov     ecx, [r14]
0x140010167  lea     rax, [rbx+rdi]
0x14001016b  sub     ecx, ebp
0x14001016d  mov     [r14], rax
0x140010170  jmp     short loc_140010174
0x140010172  xor     ecx, ecx
0x140010174  mov     [rsi], ecx
0x140010176  add     rsp, 20h
0x14001017a  pop     r14
0x14001017c  pop     rdi
0x14001017d  pop     rsi
0x14001017e  pop     rbp
0x14001017f  pop     rbx
0x140010180  retn
```
