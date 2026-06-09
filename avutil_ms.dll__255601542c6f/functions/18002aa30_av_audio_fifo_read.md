# av_audio_fifo_read

- ea: `0x18002aa30`
- end: `0x18002aacb`
- name: `av_audio_fifo_read`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002aa30`
- `0x180039d60`

## pseudocode

```c
__int64 __fastcall av_audio_fifo_read(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  int v7; // ebp
  __int64 v8; // r14
  __int64 v9; // rsi

  v3 = a3;
  if ( a3 < 0 )
    return 4294967274LL;
  _mm_lfence();
  if ( a3 > *(_DWORD *)(a1 + 12) )
    v3 = *(_DWORD *)(a1 + 12);
  if ( !v3 )
    return 0;
  v7 = 0;
  if ( *(int *)(a1 + 8) <= 0 )
  {
LABEL_11:
    _mm_lfence();
    *(_DWORD *)(a1 + 12) -= v3;
    return v3;
  }
  else
  {
    v8 = (int)(*(_DWORD *)(a1 + 28) * v3);
    v9 = 0;
    while ( (int)av_fifo_read(*(_QWORD *)(*(_QWORD *)a1 + v9), *(_QWORD *)(v9 + a2), v8) >= 0 )
    {
      ++v7;
      v9 += 8;
      if ( v7 >= *(_DWORD *)(a1 + 8) )
        goto LABEL_11;
    }
    return 3736644286LL;
  }
}

```

## disassembly

```asm
0x18002aa30  mov     [rsp+arg_0], rbx
0x18002aa35  mov     [rsp+arg_8], rbp
0x18002aa3a  mov     [rsp+arg_10], rsi
0x18002aa3f  push    rdi
0x18002aa40  push    r14
0x18002aa42  push    r15
0x18002aa44  sub     rsp, 20h
0x18002aa48  mov     ebx, r8d
0x18002aa4b  mov     r15, rdx
0x18002aa4e  mov     rdi, rcx
0x18002aa51  test    r8d, r8d
0x18002aa54  jns     short loc_18002AA5D
0x18002aa56  mov     eax, 0FFFFFFEAh
0x18002aa5b  jmp     short loc_18002AAAB
0x18002aa5d  lfence
0x18002aa60  cmp     ebx, [rcx+0Ch]
0x18002aa63  cmovg   ebx, [rcx+0Ch]
0x18002aa67  test    ebx, ebx
0x18002aa69  jnz     short loc_18002AA6F
0x18002aa6b  xor     eax, eax
0x18002aa6d  jmp     short loc_18002AAAB
0x18002aa6f  mov     eax, ebx
0x18002aa71  xor     ebp, ebp
0x18002aa73  imul    eax, [rcx+1Ch]
0x18002aa77  cmp     [rcx+8], ebp
0x18002aa7a  jle     short loc_18002AAA3
0x18002aa7c  movsxd  r14, eax
0x18002aa7f  xor     esi, esi
0x18002aa81  mov     rcx, [rdi]
0x18002aa84  mov     r8, r14
0x18002aa87  mov     rdx, [rsi+r15]
0x18002aa8b  mov     rcx, [rcx+rsi]
0x18002aa8f  call    av_fifo_read
0x18002aa94  test    eax, eax
0x18002aa96  js      short loc_18002AAC4
0x18002aa98  inc     ebp
0x18002aa9a  add     rsi, 8
0x18002aa9e  cmp     ebp, [rdi+8]
0x18002aaa1  jl      short loc_18002AA81
0x18002aaa3  lfence
0x18002aaa6  sub     [rdi+0Ch], ebx
0x18002aaa9  mov     eax, ebx
0x18002aaab  mov     rbx, [rsp+38h+arg_0]
0x18002aab0  mov     rbp, [rsp+38h+arg_8]
0x18002aab5  mov     rsi, [rsp+38h+arg_10]
0x18002aaba  add     rsp, 20h
0x18002aabe  pop     r15
0x18002aac0  pop     r14
0x18002aac2  pop     rdi
0x18002aac3  retn
0x18002aac4  mov     eax, 0DEB8AABEh
0x18002aac9  jmp     short loc_18002AAAB
```
