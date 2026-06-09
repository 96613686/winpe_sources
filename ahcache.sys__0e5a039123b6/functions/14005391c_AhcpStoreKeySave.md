# AhcpStoreKeySave

- ea: `0x14005391c`
- end: `0x140053c60`
- name: `AhcpStoreKeySave`
- size: `836`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005344c`

## callees

- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x14005391c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140053bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053c33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053c33`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053a90`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053b0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053b63`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053bd7`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053a90`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053b0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053b63`
- `ntoskrnl!KeGetCurrentIrql` at `0x140053bd7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053aad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053b2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053b80`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053bf5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053aad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053b2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053b80`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053bf5`

## string_xrefs

- `0x14005398b`: `Failed to write file name length [%x]`
- `0x1400539ac`: `Failed to write file name [%x]`

## pseudocode

```c
__int64 __fastcall AhcpStoreKeySave(unsigned __int16 *a1, _QWORD *a2)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 v4; // rax
  unsigned __int64 v6; // rdx
  POOL_TYPE v7; // r14d
  unsigned __int64 *v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned __int64 v12; // rax
  size_t v13; // r15
  size_t v14; // rcx
  const void *v15; // r13
  size_t v16; // rcx
  size_t v17; // rax
  __int64 v18; // rsi
  void *v19; // r15
  SIZE_T v20; // rsi
  KIRQL v21; // al
  POOL_TYPE v22; // ecx
  PVOID v23; // rax
  void *v24; // rbp
  __int64 v25; // rsi
  void *v26; // r12
  SIZE_T v27; // rsi
  PVOID v28; // rax
  void *v29; // rbp
  SIZE_T v30; // r13
  KIRQL CurrentIrql; // al
  POOL_TYPE v32; // ecx
  PVOID PoolWithTag; // rax
  size_t v34; // r8
  SIZE_T v35; // r13
  PVOID v36; // rax
  size_t v37; // r8
  const void *v38; // [rsp+88h] [rbp+10h]

  v2 = a2 + 4;
  v4 = a2[4];
  v6 = v4 + 2;
  if ( v4 + 2 < v4 )
  {
    v10 = -1073741811;
    goto LABEL_7;
  }
  v7 = 512;
  if ( v6 <= a2[2] )
  {
    v8 = v2;
    goto LABEL_4;
  }
  v18 = a2[3] - 1LL;
  if ( v18 + v6 < v6 )
    goto LABEL_6;
  v19 = (void *)a2[5];
  v20 = (v18 + v6) & ~v18;
  if ( v19 )
  {
    v30 = a2[1];
    CurrentIrql = KeGetCurrentIrql();
    v32 = 512;
    if ( CurrentIrql != 2 )
      v32 = PagedPool;
    PoolWithTag = ExAllocatePoolWithTag(v32, v20, 0x7274534Du);
    v24 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v20);
      v34 = v20;
      if ( v30 < v20 )
        v34 = v30;
      memmove(v24, v19, v34);
      ExFreePoolWithTag(v19, 0x7274534Du);
      goto LABEL_30;
    }
LABEL_50:
    v10 = -1073741801;
    goto LABEL_7;
  }
  v21 = KeGetCurrentIrql();
  v22 = 512;
  if ( v21 != 2 )
    v22 = PagedPool;
  v23 = ExAllocatePoolWithTag(v22, v20, 0x7274534Du);
  v24 = v23;
  if ( !v23 )
    goto LABEL_50;
  memset(v23, 0, v20);
LABEL_30:
  a2[5] = v24;
  v8 = a2 + 4;
  a2[2] = v20;
LABEL_4:
  *(_WORD *)(a2[5] + *v8) = *a1;
  v9 = *v2 + 2;
  if ( v9 >= *v2 )
  {
    *v2 = v9;
    v12 = a2[1];
    if ( v12 <= v9 )
      v12 = v9;
    a2[1] = v12;
    v13 = *a1;
    if ( !*a1 )
      return 0;
    v14 = *v2 + v13;
    if ( v14 < *v2 )
    {
      v10 = -1073741811;
      goto LABEL_10;
    }
    v15 = (const void *)*((_QWORD *)a1 + 1);
    v38 = v15;
    if ( v14 <= a2[2] )
      goto LABEL_18;
    v25 = a2[3] - 1LL;
    if ( v25 + v14 < v14 )
    {
LABEL_9:
      v10 = -1073741675;
LABEL_10:
      AslLogCallPrintf(1, "AhcpStoreKeySave", 325, "Failed to write file name [%x]", v10);
      return v10;
    }
    v26 = (void *)a2[5];
    v27 = (v25 + v14) & ~v25;
    if ( v26 )
    {
      v35 = a2[1];
      if ( KeGetCurrentIrql() != 2 )
        v7 = PagedPool;
      v36 = ExAllocatePoolWithTag(v7, v27, 0x7274534Du);
      v29 = v36;
      if ( v36 )
      {
        memset(v36, 0, v27);
        v37 = v27;
        if ( v35 < v27 )
          v37 = v35;
        memmove(v29, v26, v37);
        ExFreePoolWithTag(v26, 0x7274534Du);
        v15 = v38;
        goto LABEL_37;
      }
    }
    else
    {
      if ( KeGetCurrentIrql() != 2 )
        v7 = PagedPool;
      v28 = ExAllocatePoolWithTag(v7, v27, 0x7274534Du);
      v29 = v28;
      if ( v28 )
      {
        memset(v28, 0, v27);
LABEL_37:
        a2[5] = v29;
        a2[2] = v27;
LABEL_18:
        memmove((void *)(*v2 + a2[5]), v15, v13);
        v16 = *v2 + v13;
        if ( v16 >= *v2 )
        {
          *v2 = v16;
          v17 = a2[1];
          if ( v17 <= v16 )
            v17 = v16;
          a2[1] = v17;
          return 0;
        }
        *v2 = -1;
        goto LABEL_9;
      }
    }
    v10 = -1073741801;
    goto LABEL_10;
  }
  *v2 = -1;
LABEL_6:
  v10 = -1073741675;
LABEL_7:
  AslLogCallPrintf(1, "AhcpStoreKeySave", 319, "Failed to write file name length [%x]", v10);
  return v10;
}

```

## disassembly

```asm
0x14005391c  push    rbx
0x14005391e  push    rbp
0x14005391f  push    rsi
0x140053920  push    rdi
0x140053921  push    r12
0x140053923  push    r13
0x140053925  push    r14
0x140053927  push    r15
0x140053929  sub     rsp, 38h
0x14005392d  lea     rdi, [rdx+20h]
0x140053931  mov     rbx, rdx
0x140053934  mov     rax, [rdi]
0x140053937  mov     r12, rcx
0x14005393a  mov     ebp, 1
0x14005393f  lea     rdx, [rax+2]
0x140053943  cmp     rdx, rax
0x140053946  jb      loc_1400539DE
0x14005394c  mov     r14d, 200h
0x140053952  cmp     rdx, [rbx+10h]
0x140053956  ja      loc_140053A69
0x14005395c  mov     rcx, rdi
0x14005395f  mov     rcx, [rcx]
0x140053962  movzx   eax, word ptr [r12]
0x140053967  mov     rdx, [rbx+28h]
0x14005396b  mov     [rdx+rcx], ax
0x14005396f  mov     rax, [rdi]
0x140053972  lea     rcx, [rax+2]
0x140053976  cmp     rcx, rax
0x140053979  jnb     short loc_1400539E5
0x14005397b  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140053982  mov     ebx, 0C0000095h
0x140053987  mov     [rsp+78h+var_58], ebx
0x14005398b  lea     r9, aFailedToWriteF_3; "Failed to write file name length [%x]"
0x140053992  mov     r8d, 13Fh
0x140053998  jmp     short loc_1400539B9
0x14005399a  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1400539a1  mov     ebx, 0C0000095h
0x1400539a6  mov     eax, ebx
0x1400539a8  mov     [rsp+78h+var_58], ebx
0x1400539ac  lea     r9, aFailedToWriteF; "Failed to write file name [%x]"
0x1400539b3  mov     r8d, 145h
0x1400539b9  lea     rdx, aAhcpstorekeysa; "AhcpStoreKeySave"
0x1400539c0  mov     ecx, 1
0x1400539c5  call    AslLogCallPrintf
0x1400539ca  mov     eax, ebx
0x1400539cc  add     rsp, 38h
0x1400539d0  pop     r15
0x1400539d2  pop     r14
0x1400539d4  pop     r13
0x1400539d6  pop     r12
0x1400539d8  pop     rdi
0x1400539d9  pop     rsi
0x1400539da  pop     rbp
0x1400539db  pop     rbx
0x1400539dc  retn
0x1400539de  mov     ebx, 0C000000Dh
0x1400539e3  jmp     short loc_140053987
0x1400539e5  mov     [rdi], rcx
0x1400539e8  mov     rax, [rbx+8]
0x1400539ec  cmp     rax, rcx
0x1400539ef  cmovbe  rax, rcx
0x1400539f3  mov     [rbx+8], rax
0x1400539f7  movzx   r15d, word ptr [r12]
0x1400539fc  test    r15, r15
0x1400539ff  jz      short loc_140053A58
0x140053a01  mov     rax, [rdi]
0x140053a04  lea     rcx, [rax+r15]
0x140053a08  cmp     rcx, rax
0x140053a0b  jb      short loc_140053A5F
0x140053a0d  mov     r13, [r12+8]
0x140053a12  mov     [rsp+78h+arg_8], r13
0x140053a1a  cmp     rcx, [rbx+10h]
0x140053a1e  ja      loc_140053AE8
0x140053a24  mov     rcx, [rbx+28h]
0x140053a28  mov     r8, r15; Size
0x140053a2b  add     rcx, [rdi]; void *
0x140053a2e  mov     rdx, r13; Src
0x140053a31  call    memmove
0x140053a36  mov     rax, [rdi]
0x140053a39  lea     rcx, [rax+r15]
0x140053a3d  cmp     rcx, rax
0x140053a40  jb      loc_14005399A
0x140053a46  mov     [rdi], rcx
0x140053a49  mov     rax, [rbx+8]
0x140053a4d  cmp     rax, rcx
0x140053a50  cmovbe  rax, rcx
0x140053a54  mov     [rbx+8], rax
0x140053a58  xor     ebx, ebx
0x140053a5a  jmp     loc_1400539CA
0x140053a5f  mov     ebx, 0C000000Dh
0x140053a64  jmp     loc_1400539A6
0x140053a69  mov     rsi, [rbx+18h]
0x140053a6d  dec     rsi
0x140053a70  lea     rax, [rsi+rdx]
0x140053a74  cmp     rax, rdx
0x140053a77  jb      loc_140053982
0x140053a7d  mov     r15, [rbx+28h]
0x140053a81  not     rsi
0x140053a84  and     rsi, rax
0x140053a87  test    r15, r15
0x140053a8a  jnz     loc_140053B5F
0x140053a90  call    cs:__imp_KeGetCurrentIrql
0x140053a97  nop     dword ptr [rax+rax+00h]
0x140053a9c  mov     ecx, r14d
0x140053a9f  mov     r8d, 7274534Dh; Tag
0x140053aa5  cmp     al, 2
0x140053aa7  mov     rdx, rsi; NumberOfBytes
0x140053aaa  cmovnz  ecx, ebp; PoolType
0x140053aad  call    cs:__imp_ExAllocatePoolWithTag
0x140053ab4  nop     dword ptr [rax+rax+00h]
0x140053ab9  mov     rbp, rax
0x140053abc  test    rax, rax
0x140053abf  jz      loc_140053C4C
0x140053ac5  mov     r8, rsi; Size
0x140053ac8  xor     edx, edx; Val
0x140053aca  mov     rcx, rax; void *
0x140053acd  call    memset
0x140053ad2  mov     [rbx+28h], rbp
0x140053ad6  lea     rcx, [rbx+20h]
0x140053ada  mov     ebp, 1
0x140053adf  mov     [rbx+10h], rsi
0x140053ae3  jmp     loc_14005395F
0x140053ae8  mov     rsi, [rbx+18h]
0x140053aec  dec     rsi
0x140053aef  lea     rax, [rsi+rcx]
0x140053af3  cmp     rax, rcx
0x140053af6  jb      loc_1400539A1
0x140053afc  mov     r12, [rbx+28h]
0x140053b00  not     rsi
0x140053b03  and     rsi, rax
0x140053b06  test    r12, r12
0x140053b09  jnz     loc_140053BD3
0x140053b0f  call    cs:__imp_KeGetCurrentIrql
0x140053b16  nop     dword ptr [rax+rax+00h]
0x140053b1b  mov     r8d, 7274534Dh; Tag
0x140053b21  mov     rdx, rsi; NumberOfBytes
0x140053b24  cmp     al, 2
0x140053b26  cmovnz  r14d, ebp
0x140053b2a  mov     ecx, r14d; PoolType
0x140053b2d  call    cs:__imp_ExAllocatePoolWithTag
0x140053b34  nop     dword ptr [rax+rax+00h]
0x140053b39  mov     rbp, rax
0x140053b3c  test    rax, rax
0x140053b3f  jz      loc_140053C56
0x140053b45  mov     r8, rsi; Size
0x140053b48  xor     edx, edx; Val
0x140053b4a  mov     rcx, rax; void *
0x140053b4d  call    memset
0x140053b52  mov     [rbx+28h], rbp
0x140053b56  mov     [rbx+10h], rsi
0x140053b5a  jmp     loc_140053A24
0x140053b5f  mov     r13, [rbx+8]
0x140053b63  call    cs:__imp_KeGetCurrentIrql
0x140053b6a  nop     dword ptr [rax+rax+00h]
0x140053b6f  mov     ecx, r14d
0x140053b72  mov     r8d, 7274534Dh; Tag
0x140053b78  cmp     al, 2
0x140053b7a  mov     rdx, rsi; NumberOfBytes
0x140053b7d  cmovnz  ecx, ebp; PoolType
0x140053b80  call    cs:__imp_ExAllocatePoolWithTag
0x140053b87  nop     dword ptr [rax+rax+00h]
0x140053b8c  mov     rbp, rax
0x140053b8f  test    rax, rax
0x140053b92  jz      loc_140053C4C
0x140053b98  mov     r8, rsi; Size
0x140053b9b  xor     edx, edx; Val
0x140053b9d  mov     rcx, rax; void *
0x140053ba0  call    memset
0x140053ba5  cmp     r13, rsi
0x140053ba8  mov     r8, rsi
0x140053bab  mov     rdx, r15; Src
0x140053bae  mov     rcx, rbp; void *
0x140053bb1  cmovb   r8, r13; Size
0x140053bb5  call    memmove
0x140053bba  mov     edx, 7274534Dh; Tag
0x140053bbf  mov     rcx, r15; P
0x140053bc2  call    cs:__imp_ExFreePoolWithTag
0x140053bc9  nop     dword ptr [rax+rax+00h]
0x140053bce  jmp     loc_140053AD2
0x140053bd3  mov     r13, [rbx+8]
0x140053bd7  call    cs:__imp_KeGetCurrentIrql
0x140053bde  nop     dword ptr [rax+rax+00h]
0x140053be3  mov     r8d, 7274534Dh; Tag
0x140053be9  mov     rdx, rsi; NumberOfBytes
0x140053bec  cmp     al, 2
0x140053bee  cmovnz  r14d, ebp
0x140053bf2  mov     ecx, r14d; PoolType
0x140053bf5  call    cs:__imp_ExAllocatePoolWithTag
0x140053bfc  nop     dword ptr [rax+rax+00h]
0x140053c01  mov     rbp, rax
0x140053c04  test    rax, rax
0x140053c07  jz      short loc_140053C56
0x140053c09  mov     r8, rsi; Size
0x140053c0c  xor     edx, edx; Val
0x140053c0e  mov     rcx, rax; void *
0x140053c11  call    memset
0x140053c16  cmp     r13, rsi
0x140053c19  mov     r8, rsi
0x140053c1c  mov     rdx, r12; Src
0x140053c1f  mov     rcx, rbp; void *
0x140053c22  cmovb   r8, r13; Size
0x140053c26  call    memmove
0x140053c2b  mov     edx, 7274534Dh; Tag
0x140053c30  mov     rcx, r12; P
0x140053c33  call    cs:__imp_ExFreePoolWithTag
0x140053c3a  nop     dword ptr [rax+rax+00h]
0x140053c3f  mov     r13, [rsp+78h+arg_8]
0x140053c47  jmp     loc_140053B52
0x140053c4c  mov     ebx, 0C0000017h
0x140053c51  jmp     loc_140053987
0x140053c56  mov     ebx, 0C0000017h
0x140053c5b  jmp     loc_1400539A6
```
