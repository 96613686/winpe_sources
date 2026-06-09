# ATL::CRegistryVirtualMachine::AddReplacement(wchar_t const *,wchar_t const *)

- ea: `0x18000d2b0`
- end: `0x18000d48f`
- name: `?AddReplacement@CRegistryVirtualMachine@ATL@@UEAAJPEB_W0@Z`
- size: `479`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800129f0`

## callees

- `0x180002b9c`
- `0x18000b410`
- `0x18000d2b0`
- `0x18000d70c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d3d4`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d3f2`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d3d4`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d3f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d32f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d392`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d32f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d392`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::AddReplacement(
        ATL::CRegistryVirtualMachine *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  unsigned int v6; // r14d
  __int64 v7; // rbp
  __int64 v8; // rax
  unsigned int v9; // edi
  __int64 v10; // rdx
  void *v11; // rdi
  int v12; // eax
  void *v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  void *Block; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    v6 = -2147024882;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    Block = 0;
    v9 = v8 + 1;
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<wchar_t>::Allocate(&Block, (unsigned int)(v8 + 1)) )
    {
      v11 = Block;
      goto LABEL_28;
    }
    v10 = v9;
    v11 = Block;
    v12 = _o_wcscpy_s(Block, v10, a2);
    if ( v12 )
    {
      if ( v12 == 12 )
        goto LABEL_30;
      if ( v12 == 22 || v12 == 34 )
        goto LABEL_32;
      if ( v12 != 80 )
        goto LABEL_31;
    }
    do
      ++v7;
    while ( a3[v7] );
    Block = 0;
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<wchar_t>::Allocate(&Block, (unsigned int)(v7 + 1)) )
    {
      v13 = Block;
LABEL_26:
      operator delete(v13);
LABEL_28:
      operator delete(v11);
      return v6;
    }
    v13 = Block;
    v14 = _o_wcscpy_s(Block, (unsigned int)(v7 + 1), a3);
    if ( !v14 )
    {
LABEL_18:
      v15 = _o__recalloc(*((_QWORD *)this + 1), *((_DWORD *)this + 6) + 1, 8);
      if ( v15 )
      {
        *((_QWORD *)this + 1) = v15;
        v16 = _o__recalloc(*((_QWORD *)this + 2), *((_DWORD *)this + 6) + 1, 8);
        if ( v16 )
        {
          *((_QWORD *)this + 2) = v16;
          v17 = *((int *)this + 6);
          v18 = (_QWORD *)(*((_QWORD *)this + 1) + 8 * v17);
          if ( v18 )
            *v18 = v11;
          v19 = (_QWORD *)(*((_QWORD *)this + 2) + 8 * v17);
          if ( v19 )
            *v19 = v13;
          ++*((_DWORD *)this + 6);
          v6 = 0;
          v11 = 0;
          v13 = 0;
        }
      }
      goto LABEL_26;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_18;
LABEL_31:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_32:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_30:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d2b0  push    rsi
0x18000d2b2  push    rdi
0x18000d2b3  push    r12
0x18000d2b5  push    r14
0x18000d2b7  push    r15
0x18000d2b9  sub     rsp, 30h
0x18000d2bd  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000d2c6  mov     [rsp+58h+arg_0], rbx
0x18000d2cb  mov     [rsp+58h+arg_10], rbp
0x18000d2d0  mov     r15, r8
0x18000d2d3  mov     rbx, rdx
0x18000d2d6  mov     rsi, rcx
0x18000d2d9  xor     r12d, r12d
0x18000d2dc  test    rdx, rdx
0x18000d2df  jz      loc_18000D454
0x18000d2e5  test    r8, r8
0x18000d2e8  jz      loc_18000D454
0x18000d2ee  mov     r14d, 8007000Eh
0x18000d2f4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000d2f8  mov     rax, rbp
0x18000d2fb  inc     rax
0x18000d2fe  cmp     [rdx+rax*2], r12w
0x18000d303  jnz     short loc_18000D2FB
0x18000d305  mov     [rsp+58h+Block], r12
0x18000d30a  inc     eax
0x18000d30c  mov     edi, eax
0x18000d30e  mov     edx, eax
0x18000d310  lea     rcx, [rsp+58h+Block]
0x18000d315  call    ?Allocate@?$CAutoVectorPtr@_W@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<wchar_t>::Allocate(unsigned __int64)
0x18000d31a  test    al, al
0x18000d31c  jz      loc_18000D442
0x18000d322  mov     r8, rbx
0x18000d325  mov     edx, edi
0x18000d327  mov     rdi, [rsp+58h+Block]
0x18000d32c  mov     rcx, rdi
0x18000d32f  call    cs:__imp__o_wcscpy_s
0x18000d335  test    eax, eax
0x18000d337  jz      short loc_18000D35D
0x18000d339  cmp     eax, 0Ch
0x18000d33c  jz      loc_18000D470
0x18000d342  cmp     eax, 16h
0x18000d345  jz      loc_18000D484
0x18000d34b  cmp     eax, 22h ; '"'
0x18000d34e  jz      loc_18000D484
0x18000d354  cmp     eax, 50h ; 'P'
0x18000d357  jnz     loc_18000D479
0x18000d35d  inc     rbp
0x18000d360  cmp     [r15+rbp*2], r12w
0x18000d365  jnz     short loc_18000D35D
0x18000d367  mov     [rsp+58h+Block], r12
0x18000d36c  lea     eax, [rbp+1]
0x18000d36f  mov     ebx, eax
0x18000d371  mov     edx, eax
0x18000d373  lea     rcx, [rsp+58h+Block]
0x18000d378  call    ?Allocate@?$CAutoVectorPtr@_W@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<wchar_t>::Allocate(unsigned __int64)
0x18000d37d  test    al, al
0x18000d37f  jz      loc_18000D433
0x18000d385  mov     r8, r15
0x18000d388  mov     edx, ebx
0x18000d38a  mov     rbx, [rsp+58h+Block]
0x18000d38f  mov     rcx, rbx
0x18000d392  call    cs:__imp__o_wcscpy_s
0x18000d398  test    eax, eax
0x18000d39a  jz      short loc_18000D3C0
0x18000d39c  cmp     eax, 0Ch
0x18000d39f  jz      loc_18000D470
0x18000d3a5  cmp     eax, 16h
0x18000d3a8  jz      loc_18000D484
0x18000d3ae  cmp     eax, 22h ; '"'
0x18000d3b1  jz      loc_18000D484
0x18000d3b7  cmp     eax, 50h ; 'P'
0x18000d3ba  jnz     loc_18000D479
0x18000d3c0  mov     eax, [rsi+18h]
0x18000d3c3  inc     eax
0x18000d3c5  movsxd  rdx, eax
0x18000d3c8  mov     ebp, 8
0x18000d3cd  mov     r8d, ebp
0x18000d3d0  mov     rcx, [rsi+8]
0x18000d3d4  call    cs:__imp__o__recalloc
0x18000d3da  test    rax, rax
0x18000d3dd  jz      short loc_18000D438
0x18000d3df  mov     [rsi+8], rax
0x18000d3e3  mov     eax, [rsi+18h]
0x18000d3e6  inc     eax
0x18000d3e8  movsxd  rdx, eax
0x18000d3eb  mov     r8d, ebp
0x18000d3ee  mov     rcx, [rsi+10h]
0x18000d3f2  call    cs:__imp__o__recalloc
0x18000d3f8  test    rax, rax
0x18000d3fb  jz      short loc_18000D438
0x18000d3fd  mov     [rsi+10h], rax
0x18000d401  movsxd  rdx, dword ptr [rsi+18h]
0x18000d405  mov     rax, [rsi+8]
0x18000d409  lea     rcx, [rax+rdx*8]
0x18000d40d  test    rcx, rcx
0x18000d410  jz      short loc_18000D415
0x18000d412  mov     [rcx], rdi
0x18000d415  mov     rax, [rsi+10h]
0x18000d419  lea     rcx, [rax+rdx*8]
0x18000d41d  test    rcx, rcx
0x18000d420  jz      short loc_18000D425
0x18000d422  mov     [rcx], rbx
0x18000d425  inc     dword ptr [rsi+18h]
0x18000d428  mov     r14d, r12d
0x18000d42b  mov     rdi, r12
0x18000d42e  mov     rbx, r12
0x18000d431  jmp     short loc_18000D438
0x18000d433  mov     rbx, [rsp+58h+Block]
0x18000d438  mov     rcx, rbx; Block
0x18000d43b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d440  jmp     short loc_18000D447
0x18000d442  mov     rdi, [rsp+58h+Block]
0x18000d447  mov     rcx, rdi; Block
0x18000d44a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d44f  mov     eax, r14d
0x18000d452  jmp     short loc_18000D459
0x18000d454  mov     eax, 80070057h
0x18000d459  mov     rbx, [rsp+58h+arg_0]
0x18000d45e  mov     rbp, [rsp+58h+arg_10]
0x18000d463  add     rsp, 30h
0x18000d467  pop     r15
0x18000d469  pop     r14
0x18000d46b  pop     r12
0x18000d46d  pop     rdi
0x18000d46e  pop     rsi
0x18000d46f  retn
0x18000d470  mov     ecx, r14d; int
0x18000d473  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d479  mov     ecx, 80004005h; int
0x18000d47e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d484  mov     ecx, 80070057h; int
0x18000d489  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
