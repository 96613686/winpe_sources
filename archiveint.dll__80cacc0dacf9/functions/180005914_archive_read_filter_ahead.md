# __archive_read_filter_ahead

- ea: `0x180005914`
- end: `0x180005bf9`
- name: `__archive_read_filter_ahead`
- size: `741`
- prototype: ``
- caller_count: `134`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800035fc`
- `0x1800043a0`
- `0x180004690`
- `0x1800053a4`
- `0x180005608`
- `0x1800056c0`
- `0x1800057bc`
- `0x1800057f8`
- `0x1800075f4`
- `0x180008550`
- `0x18000c7a0`
- `0x18000ef1c`
- `0x18000fde0`
- `0x180012264`
- `0x1800bbec4`
- `0x1800c1cb0`
- `0x1800c1e90`
- `0x1800c1ff0`
- `0x1800c2280`
- `0x1800c25a0`
- `0x1800c267c`
- `0x1800c276c`
- `0x1800c29a0`
- `0x1800c2be0`
- `0x1800c2cd0`
- `0x1800c2ee0`
- `0x1800c3254`
- `0x1800c3540`
- `0x1800c36d0`
- `0x1800c37c0`
- `0x1800c3a8c`
- `0x1800c3cf0`
- `0x1800c4100`
- `0x1800c4960`
- `0x1800c49ac`
- `0x1800c4ae0`
- `0x1800c4ce0`
- `0x1800c4f20`
- `0x1800c4fd0`
- `0x1800c5310`
- `0x1800c5560`
- `0x1800c5ca0`
- `0x1800c6700`
- `0x1800c6a78`
- `0x1800c7670`
- `0x1800c94b4`
- `0x1800c95e4`
- `0x1800c9be8`
- `0x1800ca3e0`
- `0x1800ca480`

## callees

- `0x180005914`
- `0x180006c00`
- `0x1800aba54`
- `0x1800aba6c`
- `0x1800bc1c4`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005b8e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005b8e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005b68`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005b68`

## string_xrefs

- `0x180005bcc`: `Unable to allocate copy buffer`

## pseudocode

```c
const void *__fastcall _archive_read_filter_ahead(__int64 a1, size_t a2, size_t *a3)
{
  void **v6; // rax
  const void **v7; // r13
  void **v8; // r15
  size_t v9; // rcx
  __int64 v10; // r8
  size_t v11; // rdx
  void *v12; // rax
  char *v14; // r9
  char *v15; // r14
  size_t *v16; // r12
  _QWORD *v17; // rbx
  __int64 v18; // rax
  size_t v19; // rax
  size_t v20; // rbx
  __int64 v21; // r8
  size_t v22; // rdx
  size_t v23; // rcx
  size_t v24; // rbx
  const void **v25; // r9
  __int64 v26; // rax
  int v27; // edx
  char *v28; // rax
  size_t v29; // r8
  const void **v30; // [rsp+70h] [rbp+8h]

  if ( !*(_BYTE *)(a1 + 138) )
  {
    v6 = (void **)(a1 + 72);
    v30 = (const void **)(a1 + 88);
    v7 = (const void **)(a1 + 88);
    v8 = (void **)(a1 + 72);
    while ( 1 )
    {
      v9 = *(_QWORD *)(a1 + 96);
      if ( v9 >= a2 )
      {
        v8 = v6;
        if ( v9 )
        {
          if ( a3 )
          {
            v25 = v30;
            *a3 = v9;
          }
          else
          {
            v25 = v7;
          }
          return *v25;
        }
      }
      v10 = *(_QWORD *)(a1 + 128);
      v11 = v10 + v9;
      if ( *(_QWORD *)(a1 + 112) >= v10 + v9 && v11 >= a2 )
      {
        *(_QWORD *)(a1 + 120) -= v9;
        v12 = *v8;
        *(_QWORD *)(a1 + 128) = v11;
        *(_QWORD *)(a1 + 96) = 0;
        *(_QWORD *)(a1 + 88) = v12;
        if ( a3 )
          *a3 = v11;
        return *(const void **)(a1 + 120);
      }
      v8 = (void **)(a1 + 72);
      v14 = *(char **)(a1 + 72);
      v7 = (const void **)(a1 + 88);
      v15 = *(char **)(a1 + 88);
      v16 = (size_t *)(a1 + 80);
      if ( v15 > v14 && &v15[a2] > &v14[*v16] )
      {
        if ( v9 )
        {
          memmove_0(*(void **)(a1 + 72), *(const void **)(a1 + 88), *(_QWORD *)(a1 + 96));
          v10 = *(_QWORD *)(a1 + 128);
        }
        v15 = (char *)*v8;
        *v7 = *v8;
        v14 = v15;
      }
      if ( v10 )
      {
        v19 = *v16;
        v20 = *v16;
        if ( a2 > *v16 )
        {
          if ( !v19 )
            v20 = a2;
          while ( v20 < a2 )
          {
            v19 *= 2LL;
            if ( v19 <= v20 )
              goto LABEL_50;
            v20 = v19;
          }
          v28 = (char *)malloc(v20);
          v15 = v28;
          if ( !v28 )
          {
LABEL_50:
            archive_set_error(*(_QWORD *)(a1 + 24), 12, "Unable to allocate copy buffer", v14);
            goto LABEL_51;
          }
          v29 = *(_QWORD *)(a1 + 96);
          if ( v29 )
            memmove_0(v28, *v7, v29);
          free(*v8);
          v14 = v15;
          *v8 = v15;
          *v7 = v15;
          *v16 = v20;
        }
        v21 = *(_QWORD *)(a1 + 96);
        v22 = a2 - v21;
        v23 = &v14[-v21] - v15 + v20;
        v24 = *(_QWORD *)(a1 + 128);
        if ( v23 + v21 <= a2 )
          v22 = v23;
        if ( v22 <= v24 )
          v24 = v22;
        memcpy_0(&v15[v21], *(const void **)(a1 + 120), v24);
        *(_QWORD *)(a1 + 120) += v24;
        *(_QWORD *)(a1 + 128) -= v24;
        *(_QWORD *)(a1 + 96) += v24;
      }
      else
      {
        if ( *(_BYTE *)(a1 + 136) )
          goto LABEL_31;
        v17 = (_QWORD *)(a1 + 104);
        v18 = (**(__int64 (__fastcall ***)(__int64, __int64))(a1 + 32))(a1, a1 + 104);
        if ( v18 < 0 )
        {
          *(_QWORD *)(a1 + 128) = 0;
          *(_QWORD *)(a1 + 112) = 0;
          *v17 = 0;
          *(_QWORD *)(a1 + 120) = 0;
LABEL_51:
          *(_BYTE *)(a1 + 138) = 1;
          if ( a3 )
            *a3 = -30;
          return 0;
        }
        if ( v18 )
        {
          *(_QWORD *)(a1 + 112) = v18;
          *(_QWORD *)(a1 + 128) = v18;
          *(_QWORD *)(a1 + 120) = *v17;
        }
        else
        {
          v26 = *(_QWORD *)(a1 + 24);
          v27 = *(_DWORD *)(v26 + 228);
          if ( v27 == *(_DWORD *)(v26 + 224) - 1 || (unsigned int)client_switch_proxy(a1, (unsigned int)(v27 + 1)) )
          {
            *(_QWORD *)(a1 + 128) = 0;
            *(_QWORD *)(a1 + 112) = 0;
            *v17 = 0;
            *(_QWORD *)(a1 + 120) = 0;
            *(_BYTE *)(a1 + 136) = 1;
LABEL_31:
            if ( a3 )
              *a3 = *(_QWORD *)(a1 + 96);
            return 0;
          }
        }
      }
      v6 = (void **)(a1 + 72);
    }
  }
  if ( a3 )
    *a3 = -30;
  return 0;
}

```

## disassembly

```asm
0x180005914  push    rbx
0x180005916  push    rbp
0x180005917  push    rsi
0x180005918  push    rdi
0x180005919  push    r12
0x18000591b  push    r13
0x18000591d  push    r14
0x18000591f  push    r15
0x180005921  sub     rsp, 28h
0x180005925  xor     r10d, r10d
0x180005928  mov     rsi, r8
0x18000592b  mov     rbp, rdx
0x18000592e  mov     rdi, rcx
0x180005931  cmp     [rcx+8Ah], r10b
0x180005938  jnz     short loc_1800059A3
0x18000593a  lea     r9, [rcx+58h]
0x18000593e  lea     rax, [rcx+48h]
0x180005942  mov     [rsp+68h+arg_0], r9
0x180005947  mov     r13, r9
0x18000594a  mov     r15, rax
0x18000594d  mov     rcx, [rdi+60h]
0x180005951  cmp     rcx, rbp
0x180005954  jnb     loc_180005A82
0x18000595a  mov     r8, [rdi+80h]
0x180005961  lea     rdx, [r8+rcx]
0x180005965  cmp     [rdi+70h], rdx
0x180005969  jb      short loc_1800059B0
0x18000596b  cmp     rdx, rbp
0x18000596e  jb      short loc_1800059B0
0x180005970  sub     [rdi+78h], rcx
0x180005974  mov     rax, [r15]
0x180005977  mov     [rdi+80h], rdx
0x18000597e  mov     [rdi+60h], r10
0x180005982  mov     [rdi+58h], rax
0x180005986  test    rsi, rsi
0x180005989  jz      short loc_18000598E
0x18000598b  mov     [rsi], rdx
0x18000598e  mov     rax, [rdi+78h]
0x180005992  add     rsp, 28h
0x180005996  pop     r15
0x180005998  pop     r14
0x18000599a  pop     r13
0x18000599c  pop     r12
0x18000599e  pop     rdi
0x18000599f  pop     rsi
0x1800059a0  pop     rbp
0x1800059a1  pop     rbx
0x1800059a2  retn
0x1800059a3  test    rsi, rsi
0x1800059a6  jnz     loc_180005AE6
0x1800059ac  xor     eax, eax
0x1800059ae  jmp     short loc_180005992
0x1800059b0  lea     r15, [rdi+48h]
0x1800059b4  mov     r9, [r15]
0x1800059b7  lea     r13, [rdi+58h]
0x1800059bb  mov     r14, [r13+0]
0x1800059bf  lea     r12, [rdi+50h]
0x1800059c3  cmp     r14, r9
0x1800059c6  ja      loc_180005AF2
0x1800059cc  test    r8, r8
0x1800059cf  jnz     short loc_180005A21
0x1800059d1  cmp     [rdi+88h], r10b
0x1800059d8  jnz     loc_180005AD1
0x1800059de  mov     rax, [rdi+20h]
0x1800059e2  lea     rbx, [rdi+68h]
0x1800059e6  mov     rdx, rbx
0x1800059e9  mov     rcx, rdi
0x1800059ec  mov     rax, [rax]
0x1800059ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f4  xor     r10d, r10d
0x1800059f7  test    rax, rax
0x1800059fa  js      loc_180005BB4
0x180005a00  jz      loc_180005AA2
0x180005a06  mov     [rdi+70h], rax
0x180005a0a  mov     [rdi+80h], rax
0x180005a11  mov     rax, [rbx]
0x180005a14  mov     [rdi+78h], rax
0x180005a18  lea     rax, [rdi+48h]
0x180005a1c  jmp     loc_18000594D
0x180005a21  mov     rax, [r12]
0x180005a25  mov     rbx, rax
0x180005a28  cmp     rbp, rax
0x180005a2b  ja      loc_180005B4C
0x180005a31  mov     r8, [rdi+60h]
0x180005a35  mov     rdx, rbp
0x180005a38  sub     rdx, r8
0x180005a3b  sub     r9, r8
0x180005a3e  sub     r9, r14
0x180005a41  lea     rcx, [r9+rbx]
0x180005a45  mov     rbx, [rdi+80h]
0x180005a4c  lea     rax, [rcx+r8]
0x180005a50  cmp     rax, rbp
0x180005a53  cmovbe  rdx, rcx
0x180005a57  lea     rcx, [r8+r14]; void *
0x180005a5b  cmp     rdx, rbx
0x180005a5e  cmovbe  rbx, rdx
0x180005a62  mov     rdx, [rdi+78h]; Src
0x180005a66  mov     r8, rbx; Size
0x180005a69  call    memcpy_0
0x180005a6e  add     [rdi+78h], rbx
0x180005a72  sub     [rdi+80h], rbx
0x180005a79  add     [rdi+60h], rbx
0x180005a7d  xor     r10d, r10d
0x180005a80  jmp     short loc_180005A18
0x180005a82  mov     r15, rax
0x180005a85  test    rcx, rcx
0x180005a88  jz      loc_18000595A
0x180005a8e  test    rsi, rsi
0x180005a91  jnz     loc_180005BA7
0x180005a97  mov     r9, r13
0x180005a9a  mov     rax, [r9]
0x180005a9d  jmp     loc_180005992
0x180005aa2  mov     rax, [rdi+18h]
0x180005aa6  mov     ecx, [rax+0E0h]
0x180005aac  mov     edx, [rax+0E4h]
0x180005ab2  dec     ecx
0x180005ab4  cmp     edx, ecx
0x180005ab6  jnz     short loc_180005B32
0x180005ab8  mov     [rdi+80h], r10
0x180005abf  mov     [rdi+70h], r10
0x180005ac3  mov     [rbx], r10
0x180005ac6  mov     [rdi+78h], r10
0x180005aca  mov     byte ptr [rdi+88h], 1
0x180005ad1  test    rsi, rsi
0x180005ad4  jz      loc_1800059AC
0x180005ada  mov     rax, [rdi+60h]
0x180005ade  mov     [rsi], rax
0x180005ae1  jmp     loc_1800059AC
0x180005ae6  mov     qword ptr [r8], 0FFFFFFFFFFFFFFE2h
0x180005aed  jmp     loc_1800059AC
0x180005af2  mov     rdx, [r12]
0x180005af6  lea     rax, [r14+rbp]
0x180005afa  add     rdx, r9
0x180005afd  cmp     rax, rdx
0x180005b00  jbe     loc_1800059CC
0x180005b06  test    rcx, rcx
0x180005b09  jz      short loc_180005B23
0x180005b0b  mov     r8, rcx; Size
0x180005b0e  mov     rdx, r14; Src
0x180005b11  mov     rcx, r9; void *
0x180005b14  call    memmove_0
0x180005b19  mov     r8, [rdi+80h]
0x180005b20  xor     r10d, r10d
0x180005b23  mov     r14, [r15]
0x180005b26  mov     [r13+0], r14
0x180005b2a  mov     r9, r14
0x180005b2d  jmp     loc_1800059CC
0x180005b32  inc     edx
0x180005b34  mov     rcx, rdi
0x180005b37  call    client_switch_proxy
0x180005b3c  xor     r10d, r10d
0x180005b3f  test    eax, eax
0x180005b41  jnz     loc_180005AB8
0x180005b47  jmp     loc_180005A18
0x180005b4c  test    rax, rax
0x180005b4f  cmovz   rbx, rbp
0x180005b53  cmp     rbx, rbp
0x180005b56  jnb     short loc_180005B65
0x180005b58  add     rax, rax
0x180005b5b  cmp     rax, rbx
0x180005b5e  jbe     short loc_180005BC8
0x180005b60  mov     rbx, rax
0x180005b63  jmp     short loc_180005B53
0x180005b65  mov     rcx, rbx; Size
0x180005b68  call    cs:__imp_malloc
0x180005b6e  mov     r14, rax
0x180005b71  test    rax, rax
0x180005b74  jz      short loc_180005BC8
0x180005b76  mov     r8, [rdi+60h]; Size
0x180005b7a  test    r8, r8
0x180005b7d  jz      short loc_180005B8B
0x180005b7f  mov     rdx, [r13+0]; Src
0x180005b83  mov     rcx, rax; void *
0x180005b86  call    memmove_0
0x180005b8b  mov     rcx, [r15]; Block
0x180005b8e  call    cs:__imp_free
0x180005b94  mov     r9, r14
0x180005b97  mov     [r15], r14
0x180005b9a  mov     [r13+0], r14
0x180005b9e  mov     [r12], rbx
0x180005ba2  jmp     loc_180005A31
0x180005ba7  mov     r9, [rsp+68h+arg_0]
0x180005bac  mov     [rsi], rcx
0x180005baf  jmp     loc_180005A9A
0x180005bb4  mov     [rdi+80h], r10
0x180005bbb  mov     [rdi+70h], r10
0x180005bbf  mov     [rbx], r10
0x180005bc2  mov     [rdi+78h], r10
0x180005bc6  jmp     short loc_180005BDD
0x180005bc8  mov     rcx, [rdi+18h]
0x180005bcc  lea     r8, aUnableToAlloca_0; "Unable to allocate copy buffer"
0x180005bd3  mov     edx, 0Ch
0x180005bd8  call    archive_set_error
0x180005bdd  mov     byte ptr [rdi+8Ah], 1
0x180005be4  test    rsi, rsi
0x180005be7  jz      loc_1800059AC
0x180005bed  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFE2h
0x180005bf4  jmp     loc_1800059AC
```
