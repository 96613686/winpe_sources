# av_encryption_info_add_side_data

- ea: `0x1800368a0`
- end: `0x1800369e0`
- name: `av_encryption_info_add_side_data`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800368a0`
- `0x180044a20`
- `0x180078c32`
- `0x18007a960`

## pseudocode

```c
char *__fastcall av_encryption_info_add_side_data(__int64 a1, size_t *a2)
{
  unsigned int v3; // ecx
  unsigned int v5; // r8d
  unsigned int v6; // edx
  size_t v7; // rcx
  unsigned int v8; // esi
  char *v9; // r14
  __m128i *v10; // rbx
  unsigned int *v11; // r15

  v3 = *(_DWORD *)(a1 + 24);
  if ( v3 > 0xFFFFFFE7 )
    return 0;
  v5 = *(_DWORD *)(a1 + 40);
  if ( -25 - v3 < v5 )
    return 0;
  v6 = *(_DWORD *)(a1 + 56);
  if ( (-25 - v3 - v5) >> 3 < v6 )
    return 0;
  _mm_lfence();
  v7 = v5 + 24 + v3 + 8 * v6;
  *a2 = v7;
  v8 = 0;
  v9 = (char *)av_malloc(v7);
  if ( !v9 )
    return 0;
  _mm_lfence();
  *(_DWORD *)v9 = byteswap_ulong(*(_DWORD *)a1);
  *((_DWORD *)v9 + 1) = byteswap_ulong(*(_DWORD *)(a1 + 4));
  *((_DWORD *)v9 + 2) = byteswap_ulong(*(_DWORD *)(a1 + 8));
  *((_DWORD *)v9 + 3) = byteswap_ulong(*(_DWORD *)(a1 + 24));
  *((_DWORD *)v9 + 4) = byteswap_ulong(*(_DWORD *)(a1 + 40));
  *((_DWORD *)v9 + 5) = byteswap_ulong(*(_DWORD *)(a1 + 56));
  sub_18007A960((__m128i *)(v9 + 24), *(const __m128i **)(a1 + 16), *(unsigned int *)(a1 + 24));
  v10 = (__m128i *)&v9[*(unsigned int *)(a1 + 24) + 24];
  sub_18007A960(v10, *(const __m128i **)(a1 + 32), *(unsigned int *)(a1 + 40));
  v11 = (unsigned __int32 *)((char *)v10->m128i_u32 + *(unsigned int *)(a1 + 40));
  if ( *(_DWORD *)(a1 + 56) )
  {
    do
    {
      *v11 = byteswap_ulong(*(_DWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v8));
      v11[1] = byteswap_ulong(*(_DWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v8 + 4));
      v11 += 2;
      ++v8;
    }
    while ( v8 < *(_DWORD *)(a1 + 56) );
  }
  return v9;
}

```

## disassembly

```asm
0x1800368a0  mov     rax, rsp
0x1800368a3  mov     [rax+8], rbx
0x1800368a7  mov     [rax+10h], rsi
0x1800368ab  mov     [rax+18h], rdi
0x1800368af  mov     [rax+20h], r14
0x1800368b3  push    r15
0x1800368b5  sub     rsp, 20h
0x1800368b9  mov     rdi, rcx
0x1800368bc  mov     eax, 0FFFFFFE7h
0x1800368c1  mov     ecx, [rcx+18h]
0x1800368c4  mov     r9, rdx
0x1800368c7  cmp     ecx, eax
0x1800368c9  ja      loc_1800369C3
0x1800368cf  mov     r8d, [rdi+28h]
0x1800368d3  sub     eax, ecx
0x1800368d5  cmp     eax, r8d
0x1800368d8  jb      loc_1800369C3
0x1800368de  mov     edx, [rdi+38h]
0x1800368e1  sub     eax, r8d
0x1800368e4  shr     eax, 3
0x1800368e7  cmp     eax, edx
0x1800368e9  jb      loc_1800369C3
0x1800368ef  lfence
0x1800368f2  lea     ecx, [rcx+rdx*8]
0x1800368f5  add     r8d, 18h
0x1800368f9  add     ecx, r8d
0x1800368fc  mov     [r9], rcx
0x1800368ff  call    av_malloc
0x180036904  xor     esi, esi
0x180036906  mov     r14, rax
0x180036909  test    rax, rax
0x18003690c  jz      loc_1800369C3
0x180036912  lfence
0x180036915  mov     ecx, [rdi]; Number
0x180036917  call    _byteswap_ulong
0x18003691c  mov     [r14], eax
0x18003691f  mov     ecx, [rdi+4]; Number
0x180036922  call    _byteswap_ulong
0x180036927  mov     [r14+4], eax
0x18003692b  mov     ecx, [rdi+8]; Number
0x18003692e  call    _byteswap_ulong
0x180036933  mov     [r14+8], eax
0x180036937  mov     ecx, [rdi+18h]; Number
0x18003693a  call    _byteswap_ulong
0x18003693f  mov     [r14+0Ch], eax
0x180036943  mov     ecx, [rdi+28h]; Number
0x180036946  call    _byteswap_ulong
0x18003694b  mov     [r14+10h], eax
0x18003694f  mov     ecx, [rdi+38h]; Number
0x180036952  call    _byteswap_ulong
0x180036957  mov     [r14+14h], eax
0x18003695b  lea     rbx, [r14+18h]
0x18003695f  mov     r8d, [rdi+18h]
0x180036963  mov     rcx, rbx
0x180036966  mov     rdx, [rdi+10h]
0x18003696a  call    sub_18007A960
0x18003696f  mov     eax, [rdi+18h]
0x180036972  mov     r8d, [rdi+28h]
0x180036976  add     rbx, rax
0x180036979  mov     rdx, [rdi+20h]
0x18003697d  mov     rcx, rbx
0x180036980  call    sub_18007A960
0x180036985  mov     r15d, [rdi+28h]
0x180036989  add     r15, rbx
0x18003698c  cmp     [rdi+38h], esi
0x18003698f  jbe     short loc_1800369BE
0x180036991  mov     rcx, [rdi+30h]
0x180036995  mov     ebx, esi
0x180036997  mov     ecx, [rcx+rbx*8]; Number
0x18003699a  call    _byteswap_ulong
0x18003699f  mov     [r15], eax
0x1800369a2  mov     rcx, [rdi+30h]
0x1800369a6  mov     ecx, [rcx+rbx*8+4]; Number
0x1800369aa  call    _byteswap_ulong
0x1800369af  mov     [r15+4], eax
0x1800369b3  lea     r15, [r15+8]
0x1800369b7  inc     esi
0x1800369b9  cmp     esi, [rdi+38h]
0x1800369bc  jb      short loc_180036991
0x1800369be  mov     rax, r14
0x1800369c1  jmp     short loc_1800369C5
0x1800369c3  xor     eax, eax
0x1800369c5  mov     rbx, [rsp+28h+arg_0]
0x1800369ca  mov     rsi, [rsp+28h+arg_8]
0x1800369cf  mov     rdi, [rsp+28h+arg_10]
0x1800369d4  mov     r14, [rsp+28h+arg_18]
0x1800369d9  add     rsp, 20h
0x1800369dd  pop     r15
0x1800369df  retn
```
