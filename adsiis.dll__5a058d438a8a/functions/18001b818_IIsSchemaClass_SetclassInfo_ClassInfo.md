# IIsSchemaClass::SetclassInfo(_ClassInfo *)

- ea: `0x18001b818`
- end: `0x18001b967`
- name: `?SetclassInfo@IIsSchemaClass@@QEAAJPEAU_ClassInfo@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(IIsSchemaClass *__hidden this, struct _ClassInfo *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001a578`
- `0x18001b62c`

## callees

- `0x18001b818`
- `0x18001d652`
- `0x18001d66a`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b89d`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b8ec`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b92b`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b89d`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b8ec`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001b92b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b83c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b84b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b85a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b83c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b84b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001b85a`

## pseudocode

```c
__int64 __fastcall IIsSchemaClass::SetclassInfo(IIsSchemaClass *this, struct _ClassInfo *a2)
{
  void *v3; // rcx
  unsigned int v5; // ebx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbp
  __int64 v10; // rax
  DWORD v11; // r14d
  void *v12; // rax
  void *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  DWORD v16; // r15d
  void *v17; // rax
  void *v18; // r14
  __int64 v19; // rax
  DWORD v20; // r14d
  void *v21; // rax
  void *v22; // rbp

  v3 = (void *)*((_QWORD *)this + 9);
  v5 = 0;
  if ( v3 )
    FreeADsMem(v3);
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
    FreeADsMem(v6);
  v7 = (void *)*((_QWORD *)this + 6);
  if ( v7 )
    FreeADsMem(v7);
  memset_0((char *)this + 8, 0, 0x60u);
  if ( a2 )
  {
    v8 = *((_QWORD *)a2 + 8);
    v9 = -1;
    if ( v8 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v8 + 2 * v10) );
      v11 = 2 * v10 + 2;
      v12 = AllocADsMem(v11);
      v13 = v12;
      if ( !v12 )
        return (unsigned int)-2147024882;
      memcpy_0(v12, *((const void **)a2 + 8), v11);
      *((_QWORD *)this + 9) = v13;
      v5 = 0;
    }
    v14 = *((_QWORD *)a2 + 5);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = 2 * v15 + 2;
      v17 = AllocADsMem(v16);
      v18 = v17;
      if ( !v17 )
        return (unsigned int)-2147024882;
      memcpy_0(v17, *((const void **)a2 + 5), v16);
      *((_QWORD *)this + 6) = v18;
    }
    v19 = *((_QWORD *)a2 + 6);
    if ( v19 )
    {
      do
        ++v9;
      while ( *(_WORD *)(v19 + 2 * v9) );
      v20 = 2 * v9 + 2;
      v21 = AllocADsMem(v20);
      v22 = v21;
      if ( !v21 )
        return (unsigned int)-2147024882;
      memcpy_0(v21, *((const void **)a2 + 6), v20);
      *((_QWORD *)this + 7) = v22;
    }
    *((_DWORD *)this + 20) = *((_DWORD *)a2 + 18);
  }
  return v5;
}

```

## disassembly

```asm
0x18001b818  push    rbx
0x18001b81a  push    rbp
0x18001b81b  push    rsi
0x18001b81c  push    rdi
0x18001b81d  push    r12
0x18001b81f  push    r14
0x18001b821  push    r15
0x18001b823  sub     rsp, 20h
0x18001b827  xor     r12d, r12d
0x18001b82a  mov     rsi, rcx
0x18001b82d  mov     rcx, [rcx+48h]; pMem
0x18001b831  mov     rdi, rdx
0x18001b834  mov     ebx, r12d
0x18001b837  test    rcx, rcx
0x18001b83a  jz      short loc_18001B842
0x18001b83c  call    cs:__imp_FreeADsMem
0x18001b842  mov     rcx, [rsi+38h]; pMem
0x18001b846  test    rcx, rcx
0x18001b849  jz      short loc_18001B851
0x18001b84b  call    cs:__imp_FreeADsMem
0x18001b851  mov     rcx, [rsi+30h]; pMem
0x18001b855  test    rcx, rcx
0x18001b858  jz      short loc_18001B860
0x18001b85a  call    cs:__imp_FreeADsMem
0x18001b860  xor     edx, edx; Val
0x18001b862  lea     rcx, [rsi+8]; void *
0x18001b866  lea     r8d, [rdx+60h]; Size
0x18001b86a  call    memset_0
0x18001b86f  test    rdi, rdi
0x18001b872  jz      loc_18001B956
0x18001b878  mov     rcx, [rdi+40h]
0x18001b87c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001b880  test    rcx, rcx
0x18001b883  jz      short loc_18001B8CB
0x18001b885  mov     rax, rbp
0x18001b888  inc     rax
0x18001b88b  cmp     [rcx+rax*2], r12w
0x18001b890  jnz     short loc_18001B888
0x18001b892  lea     r14d, ds:2[rax*2]
0x18001b89a  mov     ecx, r14d; cb
0x18001b89d  call    cs:__imp_AllocADsMem
0x18001b8a3  mov     rbx, rax
0x18001b8a6  test    rax, rax
0x18001b8a9  jnz     short loc_18001B8B5
0x18001b8ab  mov     ebx, 8007000Eh
0x18001b8b0  jmp     loc_18001B956
0x18001b8b5  mov     rdx, [rdi+40h]; Src
0x18001b8b9  mov     rcx, rbx; void *
0x18001b8bc  mov     r8d, r14d; Size
0x18001b8bf  call    memcpy_0
0x18001b8c4  mov     [rsi+48h], rbx
0x18001b8c8  mov     ebx, r12d
0x18001b8cb  mov     rcx, [rdi+28h]
0x18001b8cf  test    rcx, rcx
0x18001b8d2  jz      short loc_18001B90D
0x18001b8d4  mov     rax, rbp
0x18001b8d7  inc     rax
0x18001b8da  cmp     [rcx+rax*2], r12w
0x18001b8df  jnz     short loc_18001B8D7
0x18001b8e1  lea     r15d, ds:2[rax*2]
0x18001b8e9  mov     ecx, r15d; cb
0x18001b8ec  call    cs:__imp_AllocADsMem
0x18001b8f2  mov     r14, rax
0x18001b8f5  test    rax, rax
0x18001b8f8  jz      short loc_18001B8AB
0x18001b8fa  mov     rdx, [rdi+28h]; Src
0x18001b8fe  mov     rcx, rax; void *
0x18001b901  mov     r8d, r15d; Size
0x18001b904  call    memcpy_0
0x18001b909  mov     [rsi+30h], r14
0x18001b90d  mov     rax, [rdi+30h]
0x18001b911  test    rax, rax
0x18001b914  jz      short loc_18001B950
0x18001b916  inc     rbp
0x18001b919  cmp     [rax+rbp*2], r12w
0x18001b91e  jnz     short loc_18001B916
0x18001b920  lea     r14d, ds:2[rbp*2]
0x18001b928  mov     ecx, r14d; cb
0x18001b92b  call    cs:__imp_AllocADsMem
0x18001b931  mov     rbp, rax
0x18001b934  test    rax, rax
0x18001b937  jz      loc_18001B8AB
0x18001b93d  mov     rdx, [rdi+30h]; Src
0x18001b941  mov     rcx, rax; void *
0x18001b944  mov     r8d, r14d; Size
0x18001b947  call    memcpy_0
0x18001b94c  mov     [rsi+38h], rbp
0x18001b950  mov     ecx, [rdi+48h]
0x18001b953  mov     [rsi+50h], ecx
0x18001b956  mov     eax, ebx
0x18001b958  add     rsp, 20h
0x18001b95c  pop     r15
0x18001b95e  pop     r14
0x18001b960  pop     r12
0x18001b962  pop     rdi
0x18001b963  pop     rsi
0x18001b964  pop     rbp
0x18001b965  pop     rbx
0x18001b966  retn
```
