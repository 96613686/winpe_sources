# av_encryption_init_info_add_side_data

- ea: `0x180036c70`
- end: `0x180036dc1`
- name: `av_encryption_init_info_add_side_data`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180036c70`
- `0x180044a20`
- `0x180078c32`
- `0x18007a960`

## pseudocode

```c
_DWORD *__fastcall av_encryption_init_info_add_side_data(__int64 a1, size_t *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // r9
  size_t i; // r8
  _DWORD *v6; // r14
  __m128i *v8; // rsi
  __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  unsigned int v11; // eax

  v2 = 0;
  v3 = a1;
  v4 = a1;
  for ( i = 4; v4; v4 = *(_QWORD *)(v4 + 48) )
  {
    i += *(unsigned int *)(v4 + 8) + *(unsigned int *)(v4 + 40) + 16LL;
    if ( v2 == -1 )
      return 0;
    if ( i > 0xFFFFFFFF )
      return 0;
    ++v2;
    if ( *(_DWORD *)(v4 + 24) )
    {
      i += *(unsigned int *)(v4 + 24) * (unsigned __int64)*(unsigned int *)(v4 + 28);
      if ( i > 0xFFFFFFFF )
        return 0;
    }
  }
  *a2 = i;
  v6 = av_malloc(i);
  if ( !v6 )
    return 0;
  *v6 = byteswap_ulong(v2);
  v8 = (__m128i *)(v6 + 1);
  while ( v3 )
  {
    v8->m128i_i32[0] = byteswap_ulong(*(_DWORD *)(v3 + 8));
    v8->m128i_i32[1] = byteswap_ulong(*(_DWORD *)(v3 + 24));
    v8->m128i_i32[2] = byteswap_ulong(*(_DWORD *)(v3 + 28));
    v8->m128i_i32[3] = byteswap_ulong(*(_DWORD *)(v3 + 40));
    sub_18007A960(v8 + 1, *(const __m128i **)v3, *(unsigned int *)(v3 + 8));
    v8 = (__m128i *)((char *)v8 + *(unsigned int *)(v3 + 8) + 16);
    v9 = 0;
    if ( *(_DWORD *)(v3 + 24) )
    {
      v10 = *(unsigned int *)(v3 + 28);
      do
      {
        sub_18007A960(v8, *(const __m128i **)(*(_QWORD *)(v3 + 16) + 8 * v9), v10);
        v10 = *(unsigned int *)(v3 + 28);
        v9 = (unsigned int)(v9 + 1);
        v8 = (__m128i *)((char *)v8 + v10);
      }
      while ( (unsigned int)v9 < *(_DWORD *)(v3 + 24) );
    }
    v11 = *(_DWORD *)(v3 + 40);
    if ( v11 )
    {
      _mm_lfence();
      sub_18007A960(v8, *(const __m128i **)(v3 + 32), v11);
      v8 = (__m128i *)((char *)v8 + *(unsigned int *)(v3 + 40));
    }
    v3 = *(_QWORD *)(v3 + 48);
  }
  return v6;
}

```

## disassembly

```asm
0x180036c70  mov     [rsp+arg_0], rbx
0x180036c75  mov     [rsp+arg_8], rsi
0x180036c7a  mov     [rsp+arg_10], rdi
0x180036c7f  push    r14
0x180036c81  sub     rsp, 20h
0x180036c85  xor     ebx, ebx
0x180036c87  mov     r10, rdx
0x180036c8a  mov     rdi, rcx
0x180036c8d  mov     r9, rcx
0x180036c90  lea     r8d, [rbx+4]
0x180036c94  test    rcx, rcx
0x180036c97  jz      short loc_180036CE1
0x180036c99  mov     r11d, 0FFFFFFFFh
0x180036c9f  mov     ecx, [r9+28h]
0x180036ca3  mov     eax, [r9+8]
0x180036ca7  add     rax, r8
0x180036caa  lea     r8, [rcx+10h]
0x180036cae  add     r8, rax
0x180036cb1  cmp     ebx, r11d
0x180036cb4  jz      short loc_180036CF4
0x180036cb6  cmp     r8, r11
0x180036cb9  ja      short loc_180036CF4
0x180036cbb  inc     ebx
0x180036cbd  cmp     dword ptr [r9+18h], 0
0x180036cc2  jz      short loc_180036CD8
0x180036cc4  mov     edx, [r9+1Ch]
0x180036cc8  mov     eax, [r9+18h]
0x180036ccc  imul    rdx, rax
0x180036cd0  add     r8, rdx
0x180036cd3  cmp     r8, r11
0x180036cd6  ja      short loc_180036CF4
0x180036cd8  mov     r9, [r9+30h]
0x180036cdc  test    r9, r9
0x180036cdf  jnz     short loc_180036C9F
0x180036ce1  mov     rcx, r8
0x180036ce4  mov     [r10], r8
0x180036ce7  call    av_malloc
0x180036cec  mov     r14, rax
0x180036cef  test    rax, rax
0x180036cf2  jnz     short loc_180036CFB
0x180036cf4  xor     eax, eax
0x180036cf6  jmp     loc_180036DAB
0x180036cfb  mov     ecx, ebx; Number
0x180036cfd  call    _byteswap_ulong
0x180036d02  mov     [r14], eax
0x180036d05  lea     rsi, [r14+4]
0x180036d09  jmp     loc_180036D9F
0x180036d0e  mov     ecx, [rdi+8]; Number
0x180036d11  call    _byteswap_ulong
0x180036d16  mov     [rsi], eax
0x180036d18  mov     ecx, [rdi+18h]; Number
0x180036d1b  call    _byteswap_ulong
0x180036d20  mov     [rsi+4], eax
0x180036d23  mov     ecx, [rdi+1Ch]; Number
0x180036d26  call    _byteswap_ulong
0x180036d2b  mov     [rsi+8], eax
0x180036d2e  mov     ecx, [rdi+28h]; Number
0x180036d31  call    _byteswap_ulong
0x180036d36  mov     [rsi+0Ch], eax
0x180036d39  lea     rbx, [rsi+10h]
0x180036d3d  mov     r8d, [rdi+8]
0x180036d41  mov     rcx, rbx
0x180036d44  mov     rdx, [rdi]
0x180036d47  call    sub_18007A960
0x180036d4c  mov     esi, [rdi+8]
0x180036d4f  add     rsi, rbx
0x180036d52  xor     ebx, ebx
0x180036d54  cmp     [rdi+18h], ebx
0x180036d57  jbe     short loc_180036D7C
0x180036d59  mov     ecx, [rdi+1Ch]
0x180036d5c  mov     rdx, [rdi+10h]
0x180036d60  mov     r8, rcx
0x180036d63  mov     rcx, rsi
0x180036d66  mov     rdx, [rdx+rbx*8]
0x180036d6a  call    sub_18007A960
0x180036d6f  mov     ecx, [rdi+1Ch]
0x180036d72  inc     ebx
0x180036d74  add     rsi, rcx
0x180036d77  cmp     ebx, [rdi+18h]
0x180036d7a  jb      short loc_180036D5C
0x180036d7c  mov     eax, [rdi+28h]
0x180036d7f  test    eax, eax
0x180036d81  jz      short loc_180036D9B
0x180036d83  lfence
0x180036d86  mov     rdx, [rdi+20h]
0x180036d8a  mov     r8d, eax
0x180036d8d  mov     rcx, rsi
0x180036d90  call    sub_18007A960
0x180036d95  mov     eax, [rdi+28h]
0x180036d98  add     rsi, rax
0x180036d9b  mov     rdi, [rdi+30h]
0x180036d9f  test    rdi, rdi
0x180036da2  jnz     loc_180036D0E
0x180036da8  mov     rax, r14
0x180036dab  mov     rbx, [rsp+28h+arg_0]
0x180036db0  mov     rsi, [rsp+28h+arg_8]
0x180036db5  mov     rdi, [rsp+28h+arg_10]
0x180036dba  add     rsp, 20h
0x180036dbe  pop     r14
0x180036dc0  retn
```
