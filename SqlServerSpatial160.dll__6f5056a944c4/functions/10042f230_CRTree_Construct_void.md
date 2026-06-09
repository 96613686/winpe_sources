# CRTree::Construct(void)

- ea: `0x10042f230`
- end: `0x10042f52a`
- name: `?Construct@CRTree@@QEAAJXZ`
- size: `762`
- prototype: `__int64 __fastcall(CRTree *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x100405920`

## callees

- `0x10042f230`
- `0x10042f530`
- `0x10042f940`
- `0x100468a54`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f2ad`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f2f8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f344`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f38a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f2ad`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f2f8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f344`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042f38a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f484`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f4d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f50a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f484`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f4d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10042f50a`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x10042f402`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x10042f41b`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x10042f402`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x10042f41b`

## string_xrefs

- `0x10042f298`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x10042f2e6`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x10042f329`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x10042f36f`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
__int64 __fastcall CRTree::Construct(CRTree *this)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  unsigned int v5; // edi
  size_t v6; // r10
  void *v7; // rax
  size_t v8; // rdx
  void *v9; // rax
  unsigned __int64 v10; // rcx
  size_t v11; // r10
  _DWORD *v12; // rax
  _DWORD *v13; // rsi
  size_t v14; // r10
  void *v15; // rax
  void *v16; // rdi
  unsigned int v17; // ecx
  unsigned int i; // edx
  __int64 v19; // rcx
  int v20; // ebp

  v2 = *(_DWORD *)(*((_QWORD *)this + 7) + 12LL);
  *((_DWORD *)this + 28) = v2;
  v3 = ((((v2 - 1) >> 1) | (v2 - 1)) >> 2) | ((v2 - 1) >> 1) | (v2 - 1);
  v4 = (((v3 >> 4) | v3) >> 8) | (v3 >> 4) | v3;
  v5 = (v4 | (v4 >> 16)) + 1;
  v6 = 16LL * v5;
  if ( !is_mul_ok(v5, 0x10u) )
    v6 = -1;
  if ( g_SOSHost )
    v7 = (void *)(*(__int64 (__fastcall **)(_QWORD, size_t, const char *, __int64))(*g_SOSMemObj + 120LL))(
                   g_SOSMemObj,
                   v6,
                   "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                   26);
  else
    v7 = malloc(v6);
  *((_QWORD *)this + 12) = v7;
  if ( v7 )
  {
    *((_DWORD *)this + 26) = v5;
    *((_DWORD *)this + 27) = 0;
    v8 = *((unsigned int *)this + 28);
    if ( g_SOSHost )
      v9 = (void *)(*(__int64 (__fastcall **)(_QWORD, size_t, const char *, __int64))(*g_SOSMemObj + 120LL))(
                     g_SOSMemObj,
                     v8,
                     "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                     26);
    else
      v9 = malloc(v8);
    v10 = *((unsigned int *)this + 28);
    *((_QWORD *)this + 15) = v9;
    v11 = 16 * v10;
    if ( !is_mul_ok(v10, 0x10u) )
      v11 = -1;
    if ( g_SOSHost )
      v12 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, size_t, const char *, __int64))(*g_SOSMemObj + 120LL))(
                        g_SOSMemObj,
                        v11,
                        "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                        26);
    else
      v12 = malloc(v11);
    v13 = v12;
    v14 = 16LL * *((unsigned int *)this + 28);
    if ( !is_mul_ok(*((unsigned int *)this + 28), 0x10u) )
      v14 = -1;
    if ( g_SOSHost )
      v15 = (void *)(*(__int64 (__fastcall **)(_QWORD, size_t, const char *, __int64))(*g_SOSMemObj + 120LL))(
                      g_SOSMemObj,
                      v14,
                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                      26);
    else
      v15 = malloc(v14);
    v16 = v15;
    if ( *((_QWORD *)this + 15) && v13 && v15 )
    {
      v17 = *((_DWORD *)this + 28);
      for ( i = 0; i < v17; v17 = *((_DWORD *)this + 28) )
      {
        *(_BYTE *)(i + *((_QWORD *)this + 15)) = 0;
        v19 = 2LL * i;
        *((_DWORD *)v15 + 2 * v19 + 2) = i;
        v13[2 * v19 + 2] = i++;
      }
      (*(void (__fastcall **)(CRTree *, _QWORD, _DWORD *, void *))(*(_QWORD *)this + 8LL))(this, v17, v13, v15);
      qsort(v13, *((unsigned int *)this + 28), 0x10u, CompareT<double>);
      qsort(v16, *((unsigned int *)this + 28), 0x10u, CompareT<double>);
      v20 = CRTree::ConstructSubTree(
              this,
              *((_DWORD *)this + 28),
              (const struct CRTree::Key *)v13,
              (const struct CRTree::Key *)v16,
              (struct Node *)this + 1);
      if ( v20 >= 0 )
      {
        _mm_lfence();
        v20 = CRTree::ComputeEnvelope(this, (struct Node *)this + 1);
      }
    }
    else
    {
      v20 = -2147024882;
    }
    if ( g_SOSHost )
    {
      if ( *((_QWORD *)this + 15) )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(*((void **)this + 15));
    }
    *((_QWORD *)this + 15) = 0;
    operator delete(*((void **)this + 12), 0x10u);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    if ( g_SOSHost )
    {
      if ( v13 )
        (*(void (__fastcall **)(_QWORD, _DWORD *))(*g_SOSMemObj + 128LL))(g_SOSMemObj, v13);
    }
    else
    {
      free(v13);
    }
    if ( g_SOSHost )
    {
      if ( v16 )
      {
        (*(void (__fastcall **)(_QWORD, void *))(*g_SOSMemObj + 128LL))(g_SOSMemObj, v16);
        return (unsigned int)v20;
      }
    }
    else
    {
      free(v16);
    }
    return (unsigned int)v20;
  }
  else
  {
    _mm_lfence();
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x10042f230  push    rbx
0x10042f232  push    rbp
0x10042f233  push    rdi
0x10042f234  sub     rsp, 30h
0x10042f238  mov     rax, [rcx+38h]
0x10042f23c  mov     rbx, rcx
0x10042f23f  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x10042f246  mov     edx, [rax+0Ch]
0x10042f249  mov     [rcx+70h], edx
0x10042f24c  dec     edx
0x10042f24e  mov     eax, edx
0x10042f250  sar     eax, 1
0x10042f252  or      edx, eax
0x10042f254  mov     eax, edx
0x10042f256  sar     eax, 2
0x10042f259  or      edx, eax
0x10042f25b  mov     eax, edx
0x10042f25d  sar     eax, 4
0x10042f260  or      edx, eax
0x10042f262  mov     eax, edx
0x10042f264  sar     eax, 8
0x10042f267  or      edx, eax
0x10042f269  mov     eax, 10h
0x10042f26e  mov     edi, edx
0x10042f270  sar     edi, 10h
0x10042f273  or      edi, edx
0x10042f275  inc     edi
0x10042f277  mov     ecx, edi
0x10042f279  mul     rcx
0x10042f27c  mov     r10, rax
0x10042f27f  cmovo   r10, rbp
0x10042f283  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10042f28b  jz      short loc_10042F2AA
0x10042f28d  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f294  lea     r9d, [rbp+1Bh]
0x10042f298  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10042f29f  mov     rdx, r10
0x10042f2a2  mov     rax, [rcx]
0x10042f2a5  call    qword ptr [rax+78h]
0x10042f2a8  jmp     short loc_10042F2B3
0x10042f2aa  mov     rcx, r10; Size
0x10042f2ad  call    cs:__imp_malloc
0x10042f2b3  mov     [rbx+60h], rax
0x10042f2b7  test    rax, rax
0x10042f2ba  jz      loc_10042F51A
0x10042f2c0  mov     [rbx+68h], edi
0x10042f2c3  mov     [rsp+48h+arg_10], r15
0x10042f2c8  xor     r15d, r15d
0x10042f2cb  mov     [rbx+6Ch], r15d
0x10042f2cf  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10042f2d6  mov     edx, [rbx+70h]
0x10042f2d9  jz      short loc_10042F2F5
0x10042f2db  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f2e2  lea     r9d, [r15+1Ah]
0x10042f2e6  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10042f2ed  mov     rax, [rcx]
0x10042f2f0  call    qword ptr [rax+78h]
0x10042f2f3  jmp     short loc_10042F2FE
0x10042f2f5  mov     rcx, rdx; Size
0x10042f2f8  call    cs:__imp_malloc
0x10042f2fe  mov     ecx, [rbx+70h]
0x10042f301  mov     [rbx+78h], rax
0x10042f305  mov     eax, 10h
0x10042f30a  mul     rcx
0x10042f30d  mov     [rsp+48h+arg_0], rsi
0x10042f312  mov     r10, rax
0x10042f315  cmovo   r10, rbp
0x10042f319  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10042f320  jz      short loc_10042F341
0x10042f322  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f329  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10042f330  mov     r9d, 1Ah
0x10042f336  mov     rdx, r10
0x10042f339  mov     rax, [rcx]
0x10042f33c  call    qword ptr [rax+78h]
0x10042f33f  jmp     short loc_10042F34A
0x10042f341  mov     rcx, r10; Size
0x10042f344  call    cs:__imp_malloc
0x10042f34a  mov     ecx, [rbx+70h]
0x10042f34d  mov     rsi, rax
0x10042f350  mov     eax, 10h
0x10042f355  mul     rcx
0x10042f358  mov     r10, rax
0x10042f35b  cmovo   r10, rbp
0x10042f35f  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10042f366  jz      short loc_10042F387
0x10042f368  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f36f  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10042f376  mov     r9d, 1Ah
0x10042f37c  mov     rdx, r10
0x10042f37f  mov     rax, [rcx]
0x10042f382  call    qword ptr [rax+78h]
0x10042f385  jmp     short loc_10042F390
0x10042f387  mov     rcx, r10; Size
0x10042f38a  call    cs:__imp_malloc
0x10042f390  mov     rdi, rax
0x10042f393  mov     [rsp+48h+arg_8], r14
0x10042f398  cmp     [rbx+78h], r15
0x10042f39c  jz      loc_10042F453
0x10042f3a2  test    rsi, rsi
0x10042f3a5  jz      loc_10042F453
0x10042f3ab  test    rax, rax
0x10042f3ae  jz      loc_10042F453
0x10042f3b4  mov     ecx, [rbx+70h]
0x10042f3b7  mov     edx, r15d
0x10042f3ba  test    ecx, ecx
0x10042f3bc  jz      short loc_10042F3DE
0x10042f3be  xchg    ax, ax
0x10042f3c0  mov     rax, [rbx+78h]
0x10042f3c4  mov     ecx, edx
0x10042f3c6  mov     [rcx+rax], r15b
0x10042f3ca  add     rcx, rcx
0x10042f3cd  mov     [rdi+rcx*8+8], edx
0x10042f3d1  mov     [rsi+rcx*8+8], edx
0x10042f3d5  inc     edx
0x10042f3d7  mov     ecx, [rbx+70h]
0x10042f3da  cmp     edx, ecx
0x10042f3dc  jb      short loc_10042F3C0
0x10042f3de  mov     rax, [rbx]
0x10042f3e1  mov     edx, ecx
0x10042f3e3  mov     r9, rdi
0x10042f3e6  mov     r8, rsi
0x10042f3e9  mov     rcx, rbx
0x10042f3ec  call    qword ptr [rax+8]
0x10042f3ef  mov     edx, [rbx+70h]; NumOfElements
0x10042f3f2  lea     r9, ??$CompareT@N@@YAHPEBX0@Z; CompareFunction
0x10042f3f9  mov     r8d, 10h; SizeOfElements
0x10042f3ff  mov     rcx, rsi; Base
0x10042f402  call    cs:__imp_qsort
0x10042f408  mov     edx, [rbx+70h]; NumOfElements
0x10042f40b  lea     r9, ??$CompareT@N@@YAHPEBX0@Z; CompareFunction
0x10042f412  mov     r8d, 10h; SizeOfElements
0x10042f418  mov     rcx, rdi; Base
0x10042f41b  call    cs:__imp_qsort
0x10042f421  mov     edx, [rbx+70h]; unsigned int
0x10042f424  lea     r14, [rbx+8]
0x10042f428  mov     r9, rdi; struct CRTree::Key *
0x10042f42b  mov     [rsp+48h+var_28], r14; struct Node *
0x10042f430  mov     r8, rsi; struct CRTree::Key *
0x10042f433  mov     rcx, rbx; this
0x10042f436  call    ?ConstructSubTree@CRTree@@IEAAJIPEBUKey@1@0AEAUNode@1@@Z; CRTree::ConstructSubTree(uint,CRTree::Key const *,CRTree::Key const *,CRTree::Node &)
0x10042f43b  mov     ebp, eax
0x10042f43d  test    eax, eax
0x10042f43f  js      short loc_10042F458
0x10042f441  lfence
0x10042f444  mov     rdx, r14; struct Node *
0x10042f447  mov     rcx, rbx; this
0x10042f44a  call    ?ComputeEnvelope@CRTree@@IEAAJAEAUNode@1@@Z; CRTree::ComputeEnvelope(CRTree::Node &)
0x10042f44f  mov     ebp, eax
0x10042f451  jmp     short loc_10042F458
0x10042f453  mov     ebp, 8007000Eh
0x10042f458  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10042f45f  mov     rdx, [rbx+78h]
0x10042f463  mov     r14, [rsp+48h+arg_8]
0x10042f468  jz      short loc_10042F481
0x10042f46a  test    rdx, rdx
0x10042f46d  jz      short loc_10042F48A
0x10042f46f  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f476  mov     rax, [rcx]
0x10042f479  call    qword ptr [rax+80h]
0x10042f47f  jmp     short loc_10042F48A
0x10042f481  mov     rcx, rdx; Block
0x10042f484  call    cs:__imp_free
0x10042f48a  mov     [rbx+78h], r15
0x10042f48e  mov     edx, 10h; unsigned __int64
0x10042f493  mov     rcx, [rbx+60h]; void *
0x10042f497  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10042f49c  mov     [rbx+60h], r15
0x10042f4a0  mov     [rbx+68h], r15
0x10042f4a4  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10042f4ac  mov     r15, [rsp+48h+arg_10]
0x10042f4b1  jz      short loc_10042F4CD
0x10042f4b3  test    rsi, rsi
0x10042f4b6  jz      short loc_10042F4D6
0x10042f4b8  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f4bf  mov     rdx, rsi
0x10042f4c2  mov     rax, [rcx]
0x10042f4c5  call    qword ptr [rax+80h]
0x10042f4cb  jmp     short loc_10042F4D6
0x10042f4cd  mov     rcx, rsi; Block
0x10042f4d0  call    cs:__imp_free
0x10042f4d6  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10042f4de  mov     rsi, [rsp+48h+arg_0]
0x10042f4e3  jz      short loc_10042F507
0x10042f4e5  test    rdi, rdi
0x10042f4e8  jz      short loc_10042F510
0x10042f4ea  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042f4f1  mov     rdx, rdi
0x10042f4f4  mov     rax, [rcx]
0x10042f4f7  call    qword ptr [rax+80h]
0x10042f4fd  mov     eax, ebp
0x10042f4ff  add     rsp, 30h
0x10042f503  pop     rdi
0x10042f504  pop     rbp
0x10042f505  pop     rbx
0x10042f506  retn
0x10042f507  mov     rcx, rdi; Block
0x10042f50a  call    cs:__imp_free
0x10042f510  mov     eax, ebp
0x10042f512  add     rsp, 30h
0x10042f516  pop     rdi
0x10042f517  pop     rbp
0x10042f518  pop     rbx
0x10042f519  retn
0x10042f51a  lfence
0x10042f51d  mov     eax, 8007000Eh
0x10042f522  add     rsp, 30h
0x10042f526  pop     rdi
0x10042f527  pop     rbp
0x10042f528  pop     rbx
0x10042f529  retn
```
