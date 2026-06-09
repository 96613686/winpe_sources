# av_packet_add_side_data

- ea: `0x18000ecb0`
- end: `0x18000ed6f`
- name: `av_packet_add_side_data`
- size: `191`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000f190`

## callees

- `0x18000ecb0`
- `0x18002277c`
- `0x180022892`

## pseudocode

```c
__int64 __fastcall av_packet_add_side_data(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  __int64 *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v13; // rbx
  __int64 v14; // rax

  v6 = *(int *)(a1 + 56);
  v9 = (__int64 *)(a1 + 48);
  if ( (int)v6 <= 0 )
  {
LABEL_5:
    if ( (unsigned int)(v6 + 1) > 0x28 )
      return 4294967262LL;
    _mm_lfence();
    v13 = 3 * v6;
    v14 = av_realloc(*v9, 24 * v6 + 24);
    if ( !v14 )
      return 4294967284LL;
    *v9 = v14;
    *(_QWORD *)(v14 + 8 * v13) = a3;
    *(_QWORD *)(*v9 + 8 * v13 + 8) = a4;
    *(_DWORD *)(*v9 + 8 * v13 + 16) = a2;
    ++*(_DWORD *)(a1 + 56);
  }
  else
  {
    v10 = *v9;
    v11 = 0;
    while ( *(_DWORD *)(v10 + 16) != a2 )
    {
      ++v11;
      v10 += 24;
      if ( v11 >= v6 )
        goto LABEL_5;
    }
    av_free(*(_QWORD *)v10);
    *(_QWORD *)v10 = a3;
    *(_QWORD *)(v10 + 8) = a4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ecb0  mov     [rsp+arg_0], rbx
0x18000ecb5  mov     [rsp+arg_8], rbp
0x18000ecba  mov     [rsp+arg_10], rsi
0x18000ecbf  push    rdi
0x18000ecc0  push    r14
0x18000ecc2  push    r15
0x18000ecc4  sub     rsp, 20h
0x18000ecc8  mov     rsi, rcx
0x18000eccb  mov     rbp, r9
0x18000ecce  movsxd  rcx, dword ptr [rcx+38h]
0x18000ecd2  mov     r14, r8
0x18000ecd5  mov     r15d, edx
0x18000ecd8  lea     rdi, [rsi+30h]
0x18000ecdc  test    ecx, ecx
0x18000ecde  jle     short loc_18000ECF7
0x18000ece0  mov     rbx, [rdi]
0x18000ece3  xor     eax, eax
0x18000ece5  cmp     [rbx+10h], r15d
0x18000ece9  jz      short loc_18000ED06
0x18000eceb  inc     rax
0x18000ecee  add     rbx, 18h
0x18000ecf2  cmp     rax, rcx
0x18000ecf5  jl      short loc_18000ECE5
0x18000ecf7  lea     eax, [rcx+1]
0x18000ecfa  cmp     eax, 28h ; '('
0x18000ecfd  jbe     short loc_18000ED17
0x18000ecff  mov     eax, 0FFFFFFDEh
0x18000ed04  jmp     short loc_18000ED56
0x18000ed06  mov     rcx, [rbx]
0x18000ed09  call    av_free
0x18000ed0e  mov     [rbx], r14
0x18000ed11  mov     [rbx+8], rbp
0x18000ed15  jmp     short loc_18000ED54
0x18000ed17  lfence
0x18000ed1a  lea     rbx, [rcx+rcx*2]
0x18000ed1e  mov     rcx, [rdi]
0x18000ed21  lea     rdx, ds:18h[rbx*8]
0x18000ed29  call    av_realloc
0x18000ed2e  test    rax, rax
0x18000ed31  jnz     short loc_18000ED3A
0x18000ed33  mov     eax, 0FFFFFFF4h
0x18000ed38  jmp     short loc_18000ED56
0x18000ed3a  mov     [rdi], rax
0x18000ed3d  mov     [rax+rbx*8], r14
0x18000ed41  mov     rax, [rdi]
0x18000ed44  mov     [rax+rbx*8+8], rbp
0x18000ed49  mov     rax, [rdi]
0x18000ed4c  mov     [rax+rbx*8+10h], r15d
0x18000ed51  inc     dword ptr [rsi+38h]
0x18000ed54  xor     eax, eax
0x18000ed56  mov     rbx, [rsp+38h+arg_0]
0x18000ed5b  mov     rbp, [rsp+38h+arg_8]
0x18000ed60  mov     rsi, [rsp+38h+arg_10]
0x18000ed65  add     rsp, 20h
0x18000ed69  pop     r15
0x18000ed6b  pop     r14
0x18000ed6d  pop     rdi
0x18000ed6e  retn
```
