# av_encryption_info_get_side_data

- ea: `0x180036b40`
- end: `0x180036c70`
- name: `av_encryption_info_get_side_data`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800369e0`
- `0x180036b40`
- `0x180078c32`
- `0x18007a960`

## pseudocode

```c
__int64 __fastcall av_encryption_info_get_side_data(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbx
  __int64 v5; // r14
  __int64 v6; // r15
  unsigned int v7; // eax
  unsigned __int64 v8; // rbp
  __int64 v9; // rsi
  unsigned int v10; // eax
  __m128i *v11; // rcx
  unsigned int *v12; // rdi
  unsigned int v13; // eax

  v2 = 0;
  if ( !a1 )
    return 0;
  if ( a2 < 0x18 )
    return 0;
  v5 = byteswap_ulong(*(_DWORD *)(a1 + 12));
  v6 = byteswap_ulong(*(_DWORD *)(a1 + 16));
  v7 = byteswap_ulong(*(_DWORD *)(a1 + 20));
  v8 = v7;
  if ( a2 < v5 + v6 + 8 * (unsigned __int64)v7 + 24 )
    return 0;
  _mm_lfence();
  v9 = av_encryption_info_alloc(v7, (unsigned int)v5, (unsigned int)v6);
  if ( !v9 )
    return 0;
  _mm_lfence();
  *(_DWORD *)v9 = byteswap_ulong(*(_DWORD *)a1);
  *(_DWORD *)(v9 + 4) = byteswap_ulong(*(_DWORD *)(a1 + 4));
  v10 = byteswap_ulong(*(_DWORD *)(a1 + 8));
  v11 = *(__m128i **)(v9 + 16);
  *(_DWORD *)(v9 + 8) = v10;
  sub_18007A960(v11, (const __m128i *)(a1 + 24), (unsigned int)v5);
  sub_18007A960(*(__m128i **)(v9 + 32), (const __m128i *)(v5 + a1 + 24), (unsigned int)v6);
  v12 = (unsigned int *)(v5 + v6 + a1 + 24);
  if ( v8 )
  {
    _mm_lfence();
    do
    {
      *(_DWORD *)(*(_QWORD *)(v9 + 48) + 8 * v2) = byteswap_ulong(*v12);
      v13 = byteswap_ulong(v12[1]);
      v12 += 2;
      *(_DWORD *)(*(_QWORD *)(v9 + 48) + 8 * v2++ + 4) = v13;
    }
    while ( v2 < v8 );
  }
  return v9;
}

```

## disassembly

```asm
0x180036b40  mov     [rsp+arg_0], rbx
0x180036b45  mov     [rsp+arg_8], rbp
0x180036b4a  mov     [rsp+arg_10], rsi
0x180036b4f  push    rdi
0x180036b50  push    r12
0x180036b52  push    r13
0x180036b54  push    r14
0x180036b56  push    r15
0x180036b58  sub     rsp, 20h
0x180036b5c  xor     ebx, ebx
0x180036b5e  mov     rsi, rdx
0x180036b61  mov     rdi, rcx
0x180036b64  test    rcx, rcx
0x180036b67  jz      loc_180036C51
0x180036b6d  cmp     rdx, 18h
0x180036b71  jb      loc_180036C51
0x180036b77  mov     ecx, [rcx+0Ch]; Number
0x180036b7a  call    _byteswap_ulong
0x180036b7f  mov     ecx, [rdi+10h]; Number
0x180036b82  mov     r14d, eax
0x180036b85  call    _byteswap_ulong
0x180036b8a  mov     ecx, [rdi+14h]; Number
0x180036b8d  mov     r15d, eax
0x180036b90  call    _byteswap_ulong
0x180036b95  mov     ebp, eax
0x180036b97  lea     rcx, ds:18h[rbp*8]
0x180036b9f  add     rcx, r15
0x180036ba2  add     rcx, r14
0x180036ba5  cmp     rsi, rcx
0x180036ba8  jb      loc_180036C51
0x180036bae  lfence
0x180036bb1  mov     r8d, r15d
0x180036bb4  mov     edx, r14d
0x180036bb7  mov     ecx, ebp
0x180036bb9  call    av_encryption_info_alloc
0x180036bbe  mov     rsi, rax
0x180036bc1  test    rax, rax
0x180036bc4  jz      loc_180036C51
0x180036bca  lfence
0x180036bcd  mov     ecx, [rdi]; Number
0x180036bcf  call    _byteswap_ulong
0x180036bd4  mov     [rsi], eax
0x180036bd6  mov     ecx, [rdi+4]; Number
0x180036bd9  call    _byteswap_ulong
0x180036bde  mov     [rsi+4], eax
0x180036be1  mov     ecx, [rdi+8]; Number
0x180036be4  call    _byteswap_ulong
0x180036be9  mov     rcx, [rsi+10h]
0x180036bed  lea     rdx, [rdi+18h]
0x180036bf1  mov     r8d, r14d
0x180036bf4  mov     [rsi+8], eax
0x180036bf7  call    sub_18007A960
0x180036bfc  mov     rcx, [rsi+20h]
0x180036c00  lea     rdx, [rdi+18h]
0x180036c04  add     rdx, r14
0x180036c07  mov     r8d, r15d
0x180036c0a  call    sub_18007A960
0x180036c0f  add     rdi, 18h
0x180036c13  lea     rax, [r14+r15]
0x180036c17  add     rdi, rax
0x180036c1a  test    rbp, rbp
0x180036c1d  jz      short loc_180036C4C
0x180036c1f  lfence
0x180036c22  mov     ecx, [rdi]; Number
0x180036c24  call    _byteswap_ulong
0x180036c29  mov     rcx, [rsi+30h]
0x180036c2d  mov     [rcx+rbx*8], eax
0x180036c30  mov     ecx, [rdi+4]; Number
0x180036c33  call    _byteswap_ulong
0x180036c38  mov     rcx, [rsi+30h]
0x180036c3c  lea     rdi, [rdi+8]
0x180036c40  mov     [rcx+rbx*8+4], eax
0x180036c44  inc     rbx
0x180036c47  cmp     rbx, rbp
0x180036c4a  jb      short loc_180036C22
0x180036c4c  mov     rax, rsi
0x180036c4f  jmp     short loc_180036C53
0x180036c51  xor     eax, eax
0x180036c53  mov     rbx, [rsp+48h+arg_0]
0x180036c58  mov     rbp, [rsp+48h+arg_8]
0x180036c5d  mov     rsi, [rsp+48h+arg_10]
0x180036c62  add     rsp, 20h
0x180036c66  pop     r15
0x180036c68  pop     r14
0x180036c6a  pop     r13
0x180036c6c  pop     r12
0x180036c6e  pop     rdi
0x180036c6f  retn
```
