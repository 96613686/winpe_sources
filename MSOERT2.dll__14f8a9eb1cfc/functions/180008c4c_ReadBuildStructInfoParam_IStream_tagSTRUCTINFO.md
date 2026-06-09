# ReadBuildStructInfoParam(IStream *,tagSTRUCTINFO *)

- ea: `0x180008c4c`
- end: `0x180008eea`
- name: `?ReadBuildStructInfoParam@@YAJPEAUIStream@@PEAUtagSTRUCTINFO@@@Z`
- size: `670`
- prototype: `int(struct IStream *, struct tagSTRUCTINFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800090b0`

## callees

- `0x180008c4c`
- `0x180012f82`
- `0x180012f8e`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ReadBuildStructInfoParam(struct IStream *a1, struct tagSTRUCTINFO *a2)
{
  int v4; // ebx
  unsigned int *v5; // r14
  unsigned int *v6; // r15
  __int64 *v7; // r12
  __int64 v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int i; // ebp
  char *v13; // r13
  _DWORD *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbp
  __int64 v19; // rcx
  __int64 j; // rsi

  memset_0(a2, 0, 0x108u);
  v4 = ((__int64 (__fastcall *)(struct IStream *, struct tagSTRUCTINFO *, __int64))a1->lpVtbl->Read)(a1, a2, 4);
  if ( v4 >= 0 )
  {
    v5 = (unsigned int *)((char *)a2 + 4);
    v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, _QWORD))a1->lpVtbl->Read)(a1, (char *)a2 + 4, 4, 0);
    if ( v4 >= 0 )
    {
      v6 = (unsigned int *)((char *)a2 + 16);
      v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, _QWORD))a1->lpVtbl->Read)(
             a1,
             (char *)a2 + 16,
             4,
             0);
      if ( v4 >= 0 )
      {
        v7 = (__int64 *)((char *)a2 + 8);
        if ( !*v6 )
        {
          if ( (*(_BYTE *)a2 & 2) != 0 )
          {
            v8 = ((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, *v5);
            *v7 = v8;
            v9 = (char *)v8;
            if ( !v8 )
              return (unsigned int)-2147024882;
            v10 = *v5;
          }
          else
          {
            v10 = 8;
            v9 = (char *)a2 + 8;
          }
          return ((unsigned int (__fastcall *)(struct IStream *, char *, __int64, _QWORD))a1->lpVtbl->Read)(
                   a1,
                   v9,
                   v10,
                   0);
        }
        v11 = ((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, *v5);
        *v7 = v11;
        if ( !v11 )
          return (unsigned int)-2147024882;
        for ( i = 0; i < *v6; ++i )
        {
          v13 = (char *)a2 + 24 * i + 24;
          v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64))a1->lpVtbl->Read)(a1, v13, 4);
          if ( v4 < 0 )
            return (unsigned int)v4;
          v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, _QWORD))a1->lpVtbl->Read)(a1, v13 + 4, 4, 0);
          if ( v4 < 0 )
            return (unsigned int)v4;
          v14 = v13 + 8;
          v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64))a1->lpVtbl->Read)(a1, v13 + 8, 4);
          if ( v4 < 0 )
            return (unsigned int)v4;
          if ( *v14 )
          {
            v15 = *((unsigned int *)v13 + 1);
            if ( (unsigned int)v15 <= *v14 )
              v15 = (unsigned int)*v14;
            v16 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, v15);
            *((_QWORD *)v13 + 2) = v16;
            if ( !v16 )
              return (unsigned int)-2147024882;
            v4 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a1->lpVtbl->Read)(
                   a1,
                   v16,
                   (unsigned int)*v14,
                   0);
            if ( v4 < 0 )
              return (unsigned int)v4;
          }
        }
        v17 = 0;
        v18 = 0;
        if ( *v6 )
        {
          do
          {
            v19 = *v7;
            if ( (*((_BYTE *)a2 + 24 * v18 + 24) & 1) != 0 )
              *(_QWORD *)(v17 + v19) = *((_QWORD *)a2 + 3 * v18 + 5);
            else
              memcpy_0(
                (void *)((unsigned int)v17 + v19),
                *((const void **)a2 + 3 * v18 + 5),
                *((unsigned int *)a2 + 6 * v18 + 8));
            v17 = (unsigned int)(*((_DWORD *)a2 + 6 * v18 + 7) + v17);
            v18 = (unsigned int)(v18 + 1);
          }
          while ( (unsigned int)v18 < *v6 );
          for ( j = 0; (unsigned int)j < *v6; j = (unsigned int)(j + 1) )
          {
            if ( (*((_BYTE *)a2 + 24 * j + 24) & 1) == 0 && *((_QWORD *)a2 + 3 * j + 5) )
            {
              ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
              *((_QWORD *)a2 + 3 * j + 5) = 0;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008c4c  push    rbx
0x180008c4e  push    rbp
0x180008c4f  push    rsi
0x180008c50  push    rdi
0x180008c51  push    r12
0x180008c53  push    r13
0x180008c55  push    r14
0x180008c57  push    r15
0x180008c59  sub     rsp, 38h
0x180008c5d  mov     rdi, rdx
0x180008c60  mov     rsi, rcx
0x180008c63  mov     rcx, rdi; void *
0x180008c66  xor     edx, edx; Val
0x180008c68  mov     r8d, 108h; Size
0x180008c6e  call    memset_0
0x180008c73  mov     rax, [rsi]
0x180008c76  xor     r9d, r9d
0x180008c79  mov     rdx, rdi
0x180008c7c  mov     rcx, rsi
0x180008c7f  mov     rax, [rax+18h]
0x180008c83  lea     ebp, [r9+4]
0x180008c87  mov     r8d, ebp
0x180008c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8f  mov     ebx, eax
0x180008c91  test    eax, eax
0x180008c93  js      loc_180008ED7
0x180008c99  mov     rax, [rsi]
0x180008c9c  lea     r14, [rdi+4]
0x180008ca0  xor     r9d, r9d
0x180008ca3  mov     r8d, ebp
0x180008ca6  mov     rdx, r14
0x180008ca9  mov     rcx, rsi
0x180008cac  mov     rax, [rax+18h]
0x180008cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb5  mov     ebx, eax
0x180008cb7  test    eax, eax
0x180008cb9  js      loc_180008ED7
0x180008cbf  mov     rax, [rsi]
0x180008cc2  lea     r15, [rdi+10h]
0x180008cc6  xor     r9d, r9d
0x180008cc9  mov     r8d, ebp
0x180008ccc  mov     rdx, r15
0x180008ccf  mov     rcx, rsi
0x180008cd2  mov     rax, [rax+18h]
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  mov     ebx, eax
0x180008cdd  test    eax, eax
0x180008cdf  js      loc_180008ED7
0x180008ce5  cmp     dword ptr [r15], 0
0x180008ce9  lea     r12, [rdi+8]
0x180008ced  jnz     short loc_180008D47
0x180008cef  test    byte ptr [rdi], 2
0x180008cf2  jz      short loc_180008D25
0x180008cf4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008cfb  mov     edx, [r14]
0x180008cfe  mov     rax, [rcx]
0x180008d01  mov     rax, [rax+18h]
0x180008d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d0a  mov     [r12], rax
0x180008d0e  mov     rdx, rax
0x180008d11  test    rax, rax
0x180008d14  jnz     short loc_180008D20
0x180008d16  mov     ebx, 8007000Eh
0x180008d1b  jmp     loc_180008ED7
0x180008d20  mov     r8d, [r14]
0x180008d23  jmp     short loc_180008D2E
0x180008d25  mov     r8d, 8
0x180008d2b  mov     rdx, r12
0x180008d2e  mov     rax, [rsi]
0x180008d31  xor     r9d, r9d
0x180008d34  mov     rcx, rsi
0x180008d37  mov     rax, [rax+18h]
0x180008d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d40  mov     ebx, eax
0x180008d42  jmp     loc_180008ED7
0x180008d47  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008d4e  mov     edx, [r14]
0x180008d51  mov     rax, [rcx]
0x180008d54  mov     rax, [rax+18h]
0x180008d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d5d  mov     [r12], rax
0x180008d61  test    rax, rax
0x180008d64  jz      short loc_180008D16
0x180008d66  xor     ebp, ebp
0x180008d68  cmp     ebp, [r15]
0x180008d6b  jnb     loc_180008E48
0x180008d71  xor     r9d, r9d
0x180008d74  mov     eax, ebp
0x180008d76  inc     rax
0x180008d79  mov     rcx, rsi
0x180008d7c  lea     r14d, [r9+4]
0x180008d80  lea     rax, [rax+rax*2]
0x180008d84  mov     r8d, r14d
0x180008d87  lea     r13, [rdi+rax*8]
0x180008d8b  mov     rax, [rsi]
0x180008d8e  mov     rdx, r13
0x180008d91  mov     rax, [rax+18h]
0x180008d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d9a  mov     ebx, eax
0x180008d9c  test    eax, eax
0x180008d9e  js      loc_180008ED7
0x180008da4  mov     rax, [rsi]
0x180008da7  lea     rdx, [r13+4]
0x180008dab  xor     r9d, r9d
0x180008dae  mov     r8d, r14d
0x180008db1  mov     rcx, rsi
0x180008db4  mov     rax, [rax+18h]
0x180008db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbd  mov     ebx, eax
0x180008dbf  test    eax, eax
0x180008dc1  js      loc_180008ED7
0x180008dc7  mov     rax, [rsi]
0x180008dca  lea     r14, [r13+8]
0x180008dce  xor     r9d, r9d
0x180008dd1  mov     rdx, r14
0x180008dd4  mov     rcx, rsi
0x180008dd7  mov     rax, [rax+18h]
0x180008ddb  lea     r8d, [r9+4]
0x180008ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de4  mov     ebx, eax
0x180008de6  test    eax, eax
0x180008de8  js      loc_180008ED7
0x180008dee  cmp     dword ptr [r14], 0
0x180008df2  jz      short loc_180008E41
0x180008df4  mov     edx, [r13+4]
0x180008df8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008dff  cmp     edx, [r14]
0x180008e02  cmovbe  edx, [r14]
0x180008e06  mov     rax, [rcx]
0x180008e09  mov     rax, [rax+18h]
0x180008e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e12  mov     [r13+10h], rax
0x180008e16  mov     rdx, rax
0x180008e19  test    rax, rax
0x180008e1c  jz      loc_180008D16
0x180008e22  mov     rcx, [rsi]
0x180008e25  xor     r9d, r9d
0x180008e28  mov     r8d, [r14]
0x180008e2b  mov     rax, [rcx+18h]
0x180008e2f  mov     rcx, rsi
0x180008e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e37  mov     ebx, eax
0x180008e39  test    eax, eax
0x180008e3b  js      loc_180008ED7
0x180008e41  inc     ebp
0x180008e43  jmp     loc_180008D68
0x180008e48  xor     r14d, r14d
0x180008e4b  xor     ebp, ebp
0x180008e4d  cmp     [r15], ebp
0x180008e50  jbe     loc_180008ED7
0x180008e56  mov     rcx, [r12]
0x180008e5a  lea     rsi, ds:0[rbp*2]
0x180008e62  add     rsi, rbp
0x180008e65  mov     edx, r14d
0x180008e68  test    byte ptr [rdi+rsi*8+18h], 1
0x180008e6d  jz      short loc_180008E7A
0x180008e6f  mov     rax, [rdi+rsi*8+28h]
0x180008e74  mov     [r14+rcx], rax
0x180008e78  jmp     short loc_180008E8C
0x180008e7a  mov     r8d, [rdi+rsi*8+20h]; Size
0x180008e7f  add     rcx, rdx; void *
0x180008e82  mov     rdx, [rdi+rsi*8+28h]; Src
0x180008e87  call    memcpy_0
0x180008e8c  add     r14d, [rdi+rsi*8+1Ch]
0x180008e91  inc     ebp
0x180008e93  cmp     ebp, [r15]
0x180008e96  jb      short loc_180008E56
0x180008e98  xor     esi, esi
0x180008e9a  cmp     [r15], esi
0x180008e9d  jbe     short loc_180008ED7
0x180008e9f  lea     rbp, [rsi+rsi*2]
0x180008ea3  test    byte ptr [rdi+rbp*8+18h], 1
0x180008ea8  jnz     short loc_180008ED0
0x180008eaa  mov     rdx, [rdi+rbp*8+28h]
0x180008eaf  test    rdx, rdx
0x180008eb2  jz      short loc_180008ED0
0x180008eb4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008ebb  mov     rax, [rcx]
0x180008ebe  mov     rax, [rax+28h]
0x180008ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec7  mov     qword ptr [rdi+rbp*8+28h], 0
0x180008ed0  inc     esi
0x180008ed2  cmp     esi, [r15]
0x180008ed5  jb      short loc_180008E9F
0x180008ed7  mov     eax, ebx
0x180008ed9  add     rsp, 38h
0x180008edd  pop     r15
0x180008edf  pop     r14
0x180008ee1  pop     r13
0x180008ee3  pop     r12
0x180008ee5  pop     rdi
0x180008ee6  pop     rsi
0x180008ee7  pop     rbp
0x180008ee8  pop     rbx
0x180008ee9  retn
```
