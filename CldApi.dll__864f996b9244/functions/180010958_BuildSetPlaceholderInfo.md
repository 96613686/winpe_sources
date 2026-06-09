# BuildSetPlaceholderInfo

- ea: `0x180010958`
- end: `0x180010c96`
- name: `BuildSetPlaceholderInfo`
- size: `830`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa48`
- `0x18000d7b0`

## callees

- `0x180010958`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010abe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010afb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010abe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010afb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010acc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010acc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b09`

## pseudocode

```c
__int64 __fastcall BuildSetPlaceholderInfo(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v6; // r15d
  unsigned int v7; // r10d
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  signed int v10; // ebx
  unsigned __int64 v11; // rcx
  unsigned int v12; // edx
  int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // edx
  HANDLE ProcessHeap; // rax
  char *v18; // rdi
  HANDLE v19; // rax
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  __int64 v22; // rbx
  int v23; // r15d
  __int64 v24; // r14
  __int64 v25; // rax
  char *v26; // rsi
  unsigned __int16 v27; // cx
  int v28; // r12d
  int v29; // r12d
  int v30; // eax
  int v31; // eax
  unsigned int v33; // [rsp+20h] [rbp-48h]
  signed int v34; // [rsp+28h] [rbp-40h]
  unsigned int v35; // [rsp+78h] [rbp+10h]

  v33 = 0;
  v6 = 0;
  v7 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v8 = 88LL * v7;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*(_QWORD *)(v8 + a1) + 2 * v9) );
      v10 = 0;
      if ( !v9 )
        v10 = -2147024809;
      if ( v10 < 0 )
        break;
      v10 = v9 > 0x7FFF ? 0x57 : 0;
      if ( v9 > 0x7FFF )
        v10 = (v9 > 0x7FFF ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v11 = 2 * v9;
      v10 = v11 > 0xFFFFFFAF ? 0x57 : 0;
      if ( v11 > 0xFFFFFFAF )
        v10 = (v11 > 0xFFFFFFAF ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v12 = *(_DWORD *)(v8 + a1 + 64);
      v10 = v12 > 0x1000 ? 0x57 : 0;
      if ( v12 > 0x1000 )
        v10 = (v12 > 0x1000 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v13 = v11 + 80;
      v14 = ~(v11 + 80);
      v10 = v14 < v12 ? 0x57 : 0;
      if ( v12 > v14 )
        v10 = (v14 < v12 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v15 = v13 + v12;
      v10 = v15 > 0xFFFFFFF8 ? 0x57 : 0;
      if ( v15 > 0xFFFFFFF8 )
        v10 = (v15 > 0xFFFFFFF8 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v16 = (v15 + 7) & 0xFFFFFFF8;
      v10 = ~v6 < v16 ? 0x57 : 0;
      if ( v16 > ~v6 )
        v10 = (~v6 < v16 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v6 += v16;
      ++v7;
      v33 = v6;
      if ( v7 >= a2 )
        goto LABEL_26;
    }
  }
  else
  {
LABEL_26:
    ProcessHeap = GetProcessHeap();
    v18 = (char *)HeapAlloc(ProcessHeap, 0, v6);
    v10 = v18 == 0 ? 8 : 0;
    if ( !v18 )
      v10 |= 0x80070000;
    v34 = v10;
    if ( v10 > -1 )
    {
      v35 = 0;
      v20 = 0;
      if ( a2 )
      {
        v21 = a2 - 1;
        v22 = 0;
        v23 = 0;
        do
        {
          v24 = 88 * v22;
          v25 = -1;
          v26 = &v18[v23];
          do
            ++v25;
          while ( *(_WORD *)(*(_QWORD *)(88 * v22 + a1) + 2 * v25) );
          v27 = 2 * v25;
          v28 = *(_DWORD *)(v24 + a1 + 64) + 87;
          *((_DWORD *)v26 + 16) = -1;
          *((_DWORD *)v26 + 1) = 0;
          v29 = (2 * v25 + v28) & 0xFFFFFFF8;
          v30 = 0;
          if ( v20 != v21 )
            v30 = v29;
          *(_DWORD *)v26 = v30;
          if ( (*(_BYTE *)(v24 + a1 + 68) & 1) != 0 )
          {
            *((_DWORD *)v26 + 1) = 64;
            v31 = 64;
          }
          else
          {
            v31 = 0;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 2) != 0 )
          {
            v31 |= 1u;
            *((_DWORD *)v26 + 1) = v31;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 4) != 0 )
          {
            v31 |= 0x4000u;
            *((_DWORD *)v26 + 1) = v31;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 8) != 0 )
            *((_DWORD *)v26 + 1) = v31 | 0x400;
          *((_WORD *)v26 + 4) = 80;
          *((_WORD *)v26 + 5) = v27;
          *((_WORD *)v26 + 6) = v27 + 80;
          *((_WORD *)v26 + 7) = *(_WORD *)(v24 + a1 + 64);
          *(_OWORD *)&v18[v23 + 16] = *(_OWORD *)(v24 + a1 + 8);
          *(_OWORD *)&v18[v23 + 32] = *(_OWORD *)(v24 + a1 + 24);
          *(_QWORD *)&v18[v23 + 48] = *(_QWORD *)(v24 + a1 + 40);
          *((_QWORD *)v26 + 7) = *(_QWORD *)(v24 + a1 + 48);
          memcpy_0(&v18[v23 + 80], *(const void **)(v24 + a1), v27);
          memcpy_0(
            &v26[*((unsigned __int16 *)v26 + 6)],
            *(const void **)(v24 + a1 + 56),
            *((unsigned __int16 *)v26 + 7));
          v21 = a2 - 1;
          v23 += v29;
          v20 = v35 + 1;
          v35 = v20;
          ++v22;
        }
        while ( v20 < a2 );
        v10 = v34;
        v6 = v33;
      }
      *a3 = v18;
      *a4 = v6;
    }
    else if ( v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010958  mov     [rsp+arg_0], rbx
0x18001095d  mov     [rsp+arg_18], r9
0x180010962  mov     [rsp+arg_10], r8
0x180010967  push    rbp
0x180010968  push    rsi
0x180010969  push    rdi
0x18001096a  push    r12
0x18001096c  push    r13
0x18001096e  push    r14
0x180010970  push    r15
0x180010972  sub     rsp, 30h
0x180010976  xor     r12d, r12d
0x180010979  mov     r13d, edx
0x18001097c  mov     [rsp+68h+var_48], r12d
0x180010981  mov     rbp, rcx
0x180010984  mov     r15d, r12d
0x180010987  mov     r10d, r12d
0x18001098a  mov     esi, 80070000h
0x18001098f  test    edx, edx
0x180010991  jz      loc_180010ABE
0x180010997  mov     edi, 1000h
0x18001099c  lea     r9d, [r12+57h]
0x1800109a1  mov     r11d, 7FFFh
0x1800109a7  mov     r14d, 0FFFFFFAFh
0x1800109ad  mov     eax, r10d
0x1800109b0  imul    rdx, rax, 58h ; 'X'
0x1800109b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800109b8  mov     rax, [rdx+rbp]
0x1800109bc  inc     rcx
0x1800109bf  cmp     [rax+rcx*2], r12w
0x1800109c4  jnz     short loc_1800109BC
0x1800109c6  test    rcx, rcx
0x1800109c9  mov     ebx, r12d
0x1800109cc  cmovz   ebx, r9d
0x1800109d0  mov     eax, ebx
0x1800109d2  or      eax, esi
0x1800109d4  test    rcx, rcx
0x1800109d7  cmovz   ebx, eax
0x1800109da  test    ebx, ebx
0x1800109dc  jz      short loc_1800109E4
0x1800109de  js      loc_180010C7F
0x1800109e4  cmp     r11, rcx
0x1800109e7  sbb     ebx, ebx
0x1800109e9  and     ebx, r9d
0x1800109ec  mov     eax, ebx
0x1800109ee  or      eax, esi
0x1800109f0  cmp     rcx, r11
0x1800109f3  cmova   ebx, eax
0x1800109f6  test    ebx, ebx
0x1800109f8  jz      short loc_180010A00
0x1800109fa  js      loc_180010C7F
0x180010a00  add     rcx, rcx
0x180010a03  cmp     r14, rcx
0x180010a06  sbb     ebx, ebx
0x180010a08  and     ebx, r9d
0x180010a0b  mov     eax, ebx
0x180010a0d  or      eax, esi
0x180010a0f  cmp     rcx, r14
0x180010a12  cmova   ebx, eax
0x180010a15  test    ebx, ebx
0x180010a17  jz      short loc_180010A1F
0x180010a19  js      loc_180010C7F
0x180010a1f  mov     edx, [rdx+rbp+40h]
0x180010a23  cmp     edi, edx
0x180010a25  sbb     ebx, ebx
0x180010a27  and     ebx, r9d
0x180010a2a  mov     eax, ebx
0x180010a2c  or      eax, esi
0x180010a2e  cmp     edx, edi
0x180010a30  cmova   ebx, eax
0x180010a33  test    ebx, ebx
0x180010a35  jz      short loc_180010A3D
0x180010a37  js      loc_180010C7F
0x180010a3d  lea     r8d, [rcx+50h]
0x180010a41  mov     ecx, r8d
0x180010a44  not     ecx
0x180010a46  cmp     ecx, edx
0x180010a48  sbb     ebx, ebx
0x180010a4a  and     ebx, r9d
0x180010a4d  mov     eax, ebx
0x180010a4f  or      eax, esi
0x180010a51  cmp     edx, ecx
0x180010a53  cmova   ebx, eax
0x180010a56  test    ebx, ebx
0x180010a58  jz      short loc_180010A60
0x180010a5a  js      loc_180010C7F
0x180010a60  add     edx, r8d
0x180010a63  mov     r8d, 0FFFFFFF8h
0x180010a69  cmp     r8d, edx
0x180010a6c  sbb     ebx, ebx
0x180010a6e  and     ebx, r9d
0x180010a71  mov     eax, ebx
0x180010a73  or      eax, esi
0x180010a75  cmp     edx, r8d
0x180010a78  cmova   ebx, eax
0x180010a7b  test    ebx, ebx
0x180010a7d  jz      short loc_180010A85
0x180010a7f  js      loc_180010C7F
0x180010a85  add     edx, 7
0x180010a88  mov     ecx, r15d
0x180010a8b  and     edx, r8d
0x180010a8e  not     ecx
0x180010a90  cmp     ecx, edx
0x180010a92  sbb     ebx, ebx
0x180010a94  and     ebx, r9d
0x180010a97  mov     eax, ebx
0x180010a99  or      eax, esi
0x180010a9b  cmp     edx, ecx
0x180010a9d  cmova   ebx, eax
0x180010aa0  test    ebx, ebx
0x180010aa2  jz      short loc_180010AAA
0x180010aa4  js      loc_180010C7F
0x180010aaa  add     r15d, edx
0x180010aad  inc     r10d
0x180010ab0  mov     [rsp+68h+var_48], r15d
0x180010ab5  cmp     r10d, r13d
0x180010ab8  jb      loc_1800109AD
0x180010abe  call    cs:__imp_GetProcessHeap
0x180010ac4  mov     r8d, r15d; dwBytes
0x180010ac7  xor     edx, edx; dwFlags
0x180010ac9  mov     rcx, rax; hHeap
0x180010acc  call    cs:__imp_HeapAlloc
0x180010ad2  mov     rdi, rax
0x180010ad5  neg     rax
0x180010ad8  sbb     ebx, ebx
0x180010ada  not     ebx
0x180010adc  and     ebx, 8
0x180010adf  mov     eax, ebx
0x180010ae1  or      eax, esi
0x180010ae3  test    rdi, rdi
0x180010ae6  cmovz   ebx, eax
0x180010ae9  mov     [rsp+68h+var_40], ebx
0x180010aed  cmp     ebx, 0FFFFFFFFh
0x180010af0  jg      short loc_180010B14
0x180010af2  test    rdi, rdi
0x180010af5  jz      loc_180010C7F
0x180010afb  call    cs:__imp_GetProcessHeap
0x180010b01  mov     r8, rdi; lpMem
0x180010b04  xor     edx, edx; dwFlags
0x180010b06  mov     rcx, rax; hHeap
0x180010b09  call    cs:__imp_HeapFree
0x180010b0f  jmp     loc_180010C7F
0x180010b14  mov     [rsp+68h+arg_8], r12d
0x180010b19  mov     r8d, r12d
0x180010b1c  test    r13d, r13d
0x180010b1f  jz      loc_180010C69
0x180010b25  lea     r9d, [r13-1]
0x180010b29  mov     rbx, r12
0x180010b2c  mov     r10d, 50h ; 'P'
0x180010b32  mov     r15d, r12d
0x180010b35  imul    r14, rbx, 58h ; 'X'
0x180010b39  mov     edx, r15d
0x180010b3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010b40  mov     rcx, [r14+rbp]
0x180010b44  lea     rsi, [rdx+rdi]
0x180010b48  inc     rax
0x180010b4b  cmp     [rcx+rax*2], r12w
0x180010b50  jnz     short loc_180010B48
0x180010b52  mov     r12d, [r14+rbp+40h]
0x180010b57  lea     rcx, [rax+rax]
0x180010b5b  add     r12d, 57h ; 'W'
0x180010b5f  mov     dword ptr [rsi+40h], 0FFFFFFFFh
0x180010b66  add     r12d, ecx
0x180010b69  mov     dword ptr [rsi+4], 0
0x180010b70  and     r12d, 0FFFFFFF8h
0x180010b74  xor     eax, eax
0x180010b76  cmp     r8d, r9d
0x180010b79  cmovnz  eax, r12d
0x180010b7d  mov     [rsi], eax
0x180010b7f  test    byte ptr [r14+rbp+44h], 1
0x180010b85  jz      short loc_180010B95
0x180010b87  mov     dword ptr [rsi+4], 40h ; '@'
0x180010b8e  mov     eax, 40h ; '@'
0x180010b93  jmp     short loc_180010B97
0x180010b95  xor     eax, eax
0x180010b97  test    byte ptr [r14+rbp+44h], 2
0x180010b9d  jz      short loc_180010BA5
0x180010b9f  or      eax, 1
0x180010ba2  mov     [rsi+4], eax
0x180010ba5  test    byte ptr [r14+rbp+44h], 4
0x180010bab  jz      short loc_180010BB4
0x180010bad  bts     eax, 0Eh
0x180010bb1  mov     [rsi+4], eax
0x180010bb4  test    byte ptr [r14+rbp+44h], 8
0x180010bba  jz      short loc_180010BC3
0x180010bbc  bts     eax, 0Ah
0x180010bc0  mov     [rsi+4], eax
0x180010bc3  mov     [rsi+8], r10w
0x180010bc8  movzx   r8d, cx; Size
0x180010bcc  lea     rcx, [rdi+50h]
0x180010bd0  mov     [rsi+0Ah], r8w
0x180010bd5  add     rcx, rdx; void *
0x180010bd8  lea     eax, [r10+r8]
0x180010bdc  mov     [rsi+0Ch], ax
0x180010be0  movzx   eax, word ptr [r14+rbp+40h]
0x180010be6  mov     [rsi+0Eh], ax
0x180010bea  movups  xmm0, xmmword ptr [r14+rbp+8]
0x180010bf0  movups  xmmword ptr [rdx+rdi+10h], xmm0
0x180010bf5  movups  xmm1, xmmword ptr [r14+rbp+18h]
0x180010bfb  movups  xmmword ptr [rdx+rdi+20h], xmm1
0x180010c00  movsd   xmm0, qword ptr [r14+rbp+28h]
0x180010c07  movsd   qword ptr [rdx+rdi+30h], xmm0
0x180010c0d  mov     rax, [r14+rbp+30h]
0x180010c12  mov     [rsi+38h], rax
0x180010c16  mov     rdx, [r14+rbp]; Src
0x180010c1a  call    memcpy_0
0x180010c1f  movzx   ecx, word ptr [rsi+0Ch]
0x180010c23  movzx   r8d, word ptr [rsi+0Eh]; Size
0x180010c28  add     rcx, rsi; void *
0x180010c2b  mov     rdx, [r14+rbp+38h]; Src
0x180010c30  call    memcpy_0
0x180010c35  mov     r8d, [rsp+68h+arg_8]
0x180010c3a  lea     r9d, [r13-1]
0x180010c3e  add     r15d, r12d
0x180010c41  inc     r8d
0x180010c44  mov     r12d, 0
0x180010c4a  mov     [rsp+68h+arg_8], r8d
0x180010c4f  inc     rbx
0x180010c52  lea     r10d, [r12+50h]
0x180010c57  cmp     r8d, r13d
0x180010c5a  jb      loc_180010B35
0x180010c60  mov     ebx, [rsp+68h+var_40]
0x180010c64  mov     r15d, [rsp+68h+var_48]
0x180010c69  mov     rax, [rsp+68h+arg_10]
0x180010c71  mov     [rax], rdi
0x180010c74  mov     rax, [rsp+68h+arg_18]
0x180010c7c  mov     [rax], r15d
0x180010c7f  mov     eax, ebx
0x180010c81  mov     rbx, [rsp+68h+arg_0]
0x180010c86  add     rsp, 30h
0x180010c8a  pop     r15
0x180010c8c  pop     r14
0x180010c8e  pop     r13
0x180010c90  pop     r12
0x180010c92  pop     rdi
0x180010c93  pop     rsi
0x180010c94  pop     rbp
0x180010c95  retn
```
