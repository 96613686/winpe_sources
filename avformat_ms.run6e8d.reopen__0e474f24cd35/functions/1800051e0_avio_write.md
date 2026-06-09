# avio_write

- ea: `0x1800051e0`
- end: `0x180005290`
- name: `avio_write`
- size: `176`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004450`
- `0x1800044d0`
- `0x180004e10`

## callees

- `0x180003fb0`
- `0x1800051e0`
- `0x180005c3c`
- `0x180005f80`
- `0x18001d740`

## pseudocode

```c
unsigned __int64 __fastcall avio_write(__int64 a1, const __m128i *a2, int a3)
{
  int v3; // edi
  unsigned __int64 result; // rax
  __m128i *v7; // rcx
  int v8; // ebp

  if ( a3 > 0 )
  {
    v3 = a3;
    if ( !*(_DWORD *)(a1 + 140) || *(_QWORD *)(a1 + 112) )
    {
      do
      {
        v7 = *(__m128i **)(a1 + 24);
        v8 = v3;
        if ( *(_QWORD *)(a1 + 32) - (_QWORD)v7 <= (__int64)(unsigned int)v3 )
          v8 = *(_DWORD *)(a1 + 32) - (_DWORD)v7;
        sub_18001D740(v7, a2, v8);
        *(_QWORD *)(a1 + 24) += v8;
        result = *(_QWORD *)(a1 + 24);
        if ( result >= *(_QWORD *)(a1 + 32) )
          result = sub_180005C3C(a1);
        a2 = (const __m128i *)((char *)a2 + v8);
        v3 -= v8;
      }
      while ( v3 > 0 );
    }
    else
    {
      _mm_lfence();
      avio_flush(a1);
      return sub_180005F80(a1, a2, (unsigned int)v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800051e0  test    r8d, r8d
0x1800051e3  jle     locret_18000528F
0x1800051e9  mov     rax, rsp
0x1800051ec  mov     [rax+8], rbx
0x1800051f0  mov     [rax+10h], rbp
0x1800051f4  mov     [rax+18h], rsi
0x1800051f8  mov     [rax+20h], rdi
0x1800051fc  push    r14
0x1800051fe  sub     rsp, 20h
0x180005202  cmp     dword ptr [rcx+8Ch], 0
0x180005209  mov     edi, r8d
0x18000520c  mov     rsi, rdx
0x18000520f  mov     rbx, rcx
0x180005212  jz      short loc_180005233
0x180005214  cmp     qword ptr [rcx+70h], 0
0x180005219  jnz     short loc_180005233
0x18000521b  lfence
0x18000521e  call    avio_flush
0x180005223  mov     r8d, edi
0x180005226  mov     rdx, rsi
0x180005229  mov     rcx, rbx
0x18000522c  call    sub_180005F80
0x180005231  jmp     short loc_180005275
0x180005233  mov     rcx, [rbx+18h]
0x180005237  mov     ebp, edi
0x180005239  mov     rdx, [rbx+20h]
0x18000523d  sub     rdx, rcx
0x180005240  mov     eax, edi
0x180005242  cmp     rdx, rax
0x180005245  cmovle  ebp, edx
0x180005248  mov     rdx, rsi
0x18000524b  movsxd  r14, ebp
0x18000524e  mov     r8, r14
0x180005251  call    sub_18001D740
0x180005256  add     [rbx+18h], r14
0x18000525a  mov     rax, [rbx+18h]
0x18000525e  cmp     rax, [rbx+20h]
0x180005262  jb      short loc_18000526C
0x180005264  mov     rcx, rbx
0x180005267  call    sub_180005C3C
0x18000526c  add     rsi, r14
0x18000526f  sub     edi, ebp
0x180005271  test    edi, edi
0x180005273  jg      short loc_180005233
0x180005275  mov     rbx, [rsp+28h+arg_0]
0x18000527a  mov     rbp, [rsp+28h+arg_8]
0x18000527f  mov     rsi, [rsp+28h+arg_10]
0x180005284  mov     rdi, [rsp+28h+arg_18]
0x180005289  add     rsp, 20h
0x18000528d  pop     r14
0x18000528f  retn
```
