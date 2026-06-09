# avcodec_parameters_copy

- ea: `0x180006380`
- end: `0x18000646d`
- name: `avcodec_parameters_copy`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180005760`
- `0x180005cc0`

## callees

- `0x180006380`
- `0x180006848`
- `0x180006908`
- `0x180022716`
- `0x1800227be`
- `0x180024640`

## pseudocode

```c
__int64 __fastcall avcodec_parameters_copy(__int64 a1, __int64 a2)
{
  __m128i *v4; // rax
  __int64 result; // rax

  sub_180006908();
  sub_180024640((__m128i *)a1, (const __m128i *)a2, 0xB0u);
  *(_OWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    v4 = (__m128i *)av_mallocz(*(_DWORD *)(a2 + 24) + 64);
    *(_QWORD *)(a1 + 16) = v4;
    if ( !v4 )
      return 4294967284LL;
    sub_180024640(v4, *(const __m128i **)(a2 + 16), *(int *)(a2 + 24));
    *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 24);
  }
  result = sub_180006848(a1 + 32, a1 + 40, *(_QWORD *)(a2 + 32), *(unsigned int *)(a2 + 40));
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    result = av_channel_layout_copy();
    if ( (int)result >= 0 )
      return 0;
    else
      _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x180006380  mov     rax, rsp
0x180006383  mov     [rax+8], rbx
0x180006387  mov     [rax+10h], rsi
0x18000638b  mov     [rax+18h], rdi
0x18000638f  mov     [rax+20h], r14
0x180006393  push    r15
0x180006395  sub     rsp, 40h
0x180006399  mov     rbx, rdx
0x18000639c  mov     rdi, rcx
0x18000639f  call    sub_180006908
0x1800063a4  mov     r8d, 0B0h
0x1800063aa  mov     rdx, rbx
0x1800063ad  mov     rcx, rdi
0x1800063b0  call    sub_180024640
0x1800063b5  xor     eax, eax
0x1800063b7  lea     rsi, [rdi+80h]
0x1800063be  xorps   xmm0, xmm0
0x1800063c1  mov     [rsp+48h+var_18], rax
0x1800063c6  movups  xmmword ptr [rsi], xmm0
0x1800063c9  mov     [rdi+10h], rax
0x1800063cd  movsd   xmm0, [rsp+48h+var_18]
0x1800063d3  movsd   qword ptr [rsi+10h], xmm0
0x1800063d8  mov     [rdi+18h], eax
0x1800063db  mov     [rdi+20h], rax
0x1800063df  mov     [rdi+28h], eax
0x1800063e2  cmp     [rbx+10h], rax
0x1800063e6  jz      short loc_18000641C
0x1800063e8  mov     eax, [rbx+18h]
0x1800063eb  add     eax, 40h ; '@'
0x1800063ee  movsxd  rcx, eax
0x1800063f1  call    av_mallocz
0x1800063f6  mov     [rdi+10h], rax
0x1800063fa  test    rax, rax
0x1800063fd  jnz     short loc_180006406
0x1800063ff  mov     eax, 0FFFFFFF4h
0x180006404  jmp     short loc_180006452
0x180006406  movsxd  r8, dword ptr [rbx+18h]
0x18000640a  mov     rcx, rax
0x18000640d  mov     rdx, [rbx+10h]
0x180006411  call    sub_180024640
0x180006416  mov     eax, [rbx+18h]
0x180006419  mov     [rdi+18h], eax
0x18000641c  mov     r9d, [rbx+28h]
0x180006420  lea     rdx, [rdi+28h]
0x180006424  mov     r8, [rbx+20h]
0x180006428  lea     rcx, [rdi+20h]
0x18000642c  call    sub_180006848
0x180006431  lfence
0x180006434  test    eax, eax
0x180006436  js      short loc_180006452
0x180006438  lea     rdx, [rbx+80h]
0x18000643f  mov     rcx, rsi
0x180006442  call    av_channel_layout_copy
0x180006447  test    eax, eax
0x180006449  jns     short loc_180006450
0x18000644b  lfence
0x18000644e  jmp     short loc_180006452
0x180006450  xor     eax, eax
0x180006452  mov     rbx, [rsp+48h+arg_0]
0x180006457  mov     rsi, [rsp+48h+arg_8]
0x18000645c  mov     rdi, [rsp+48h+arg_10]
0x180006461  mov     r14, [rsp+48h+arg_18]
0x180006466  add     rsp, 40h
0x18000646a  pop     r15
0x18000646c  retn
```
