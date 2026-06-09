# av_packet_side_data_add_0

- ea: `0x18000fcd4`
- end: `0x18000fd9e`
- name: `av_packet_side_data_add_0`
- size: `202`
- prototype: `_QWORD *__fastcall(__int64 *, int *, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000f480`
- `0x18000f760`

## callees

- `0x18000fcd4`
- `0x18002277c`
- `0x180022872`

## pseudocode

```c
_QWORD *__fastcall av_packet_side_data_add_0(__int64 *a1, int *a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rdi
  int v6; // r10d
  __int64 v7; // r11
  __int64 v12; // rbx
  __int64 v13; // r9
  _DWORD *v14; // rax
  __int64 v15; // rdx
  int v16; // edi
  __int64 v17; // rax
  _QWORD *result; // rax
  _QWORD *v19; // rbx

  v5 = *a2;
  v6 = 0;
  v7 = *a1;
  v12 = v5;
  if ( (int)v5 <= 0 )
  {
LABEL_5:
    if ( (_DWORD)v5 == 0x7FFFFFFF )
      return 0;
    v15 = v5 + 1;
    v16 = v5 + 1;
    v17 = av_realloc_array(*a1, v15, 24);
    if ( !v17 )
    {
      return 0;
    }
    else
    {
      *a1 = v17;
      result = (_QWORD *)(v17 + 24 * v12);
      result[1] = a5;
      *((_DWORD *)result + 4) = a3;
      *result = a4;
      *a2 = v16;
    }
  }
  else
  {
    v13 = 0;
    v14 = (_DWORD *)(v7 + 16);
    while ( *v14 != a3 )
    {
      ++v6;
      ++v13;
      v14 += 6;
      if ( v13 >= v5 )
        goto LABEL_5;
    }
    v19 = (_QWORD *)(v7 + 24LL * v6);
    av_free(*v19);
    result = v19;
    v19[1] = a5;
    *v19 = a4;
  }
  return result;
}

```

## disassembly

```asm
0x18000fcd4  mov     [rsp+arg_0], rbx
0x18000fcd9  mov     [rsp+arg_8], rbp
0x18000fcde  mov     [rsp+arg_10], rsi
0x18000fce3  push    rdi
0x18000fce4  push    r14
0x18000fce6  push    r15
0x18000fce8  sub     rsp, 20h
0x18000fcec  movsxd  rdi, dword ptr [rdx]
0x18000fcef  xor     r10d, r10d
0x18000fcf2  mov     r11, [rcx]
0x18000fcf5  mov     ebp, r8d
0x18000fcf8  mov     rsi, r9
0x18000fcfb  mov     r14, rdx
0x18000fcfe  mov     r15, rcx
0x18000fd01  mov     rbx, rdi
0x18000fd04  lea     r8d, [r10+18h]
0x18000fd08  test    edi, edi
0x18000fd0a  jle     short loc_18000FD25
0x18000fd0c  xor     r9d, r9d
0x18000fd0f  lea     rax, [r11+10h]
0x18000fd13  cmp     [rax], ebp
0x18000fd15  jz      short loc_18000FD5F
0x18000fd17  inc     r10d
0x18000fd1a  inc     r9
0x18000fd1d  add     rax, r8
0x18000fd20  cmp     r9, rbx
0x18000fd23  jl      short loc_18000FD13
0x18000fd25  cmp     edi, 7FFFFFFFh
0x18000fd2b  jz      short loc_18000FD83
0x18000fd2d  lea     rdx, [rbx+1]
0x18000fd31  mov     rcx, r11
0x18000fd34  inc     edi
0x18000fd36  call    av_realloc_array
0x18000fd3b  test    rax, rax
0x18000fd3e  jz      short loc_18000FD83
0x18000fd40  mov     [r15], rax
0x18000fd43  lea     rcx, [rbx+rbx*2]
0x18000fd47  lea     rax, [rax+rcx*8]
0x18000fd4b  mov     rcx, [rsp+38h+arg_20]
0x18000fd50  mov     [rax+8], rcx
0x18000fd54  mov     [rax+10h], ebp
0x18000fd57  mov     [rax], rsi
0x18000fd5a  mov     [r14], edi
0x18000fd5d  jmp     short loc_18000FD85
0x18000fd5f  movsxd  rax, r10d
0x18000fd62  lea     rcx, [rax+rax*2]
0x18000fd66  lea     rbx, [r11+rcx*8]
0x18000fd6a  mov     rcx, [rbx]
0x18000fd6d  call    av_free
0x18000fd72  mov     rcx, [rsp+38h+arg_20]
0x18000fd77  mov     rax, rbx
0x18000fd7a  mov     [rbx+8], rcx
0x18000fd7e  mov     [rbx], rsi
0x18000fd81  jmp     short loc_18000FD85
0x18000fd83  xor     eax, eax
0x18000fd85  mov     rbx, [rsp+38h+arg_0]
0x18000fd8a  mov     rbp, [rsp+38h+arg_8]
0x18000fd8f  mov     rsi, [rsp+38h+arg_10]
0x18000fd94  add     rsp, 20h
0x18000fd98  pop     r15
0x18000fd9a  pop     r14
0x18000fd9c  pop     rdi
0x18000fd9d  retn
```
