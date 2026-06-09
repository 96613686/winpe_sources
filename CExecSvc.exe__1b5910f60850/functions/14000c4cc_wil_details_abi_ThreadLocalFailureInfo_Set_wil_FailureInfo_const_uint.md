# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c4cc`
- end: `0x14000c6e5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009570`

## callees

- `0x140002ecc`
- `0x14000ba08`
- `0x14000c4cc`
- `0x14000f330`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c5c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c5c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c5b4`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x14000c4cc  push    rbx
0x14000c4ce  push    rbp
0x14000c4cf  push    rsi
0x14000c4d0  push    rdi
0x14000c4d1  push    r12
0x14000c4d3  push    r13
0x14000c4d5  push    r14
0x14000c4d7  push    r15
0x14000c4d9  sub     rsp, 28h
0x14000c4dd  mov     [rcx+4], r8d
0x14000c4e1  xor     r13d, r13d
0x14000c4e4  mov     eax, [rdx+8]
0x14000c4e7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000c4eb  mov     [rcx+8], eax
0x14000c4ee  mov     rdi, rcx
0x14000c4f1  mov     [rcx+10h], r13
0x14000c4f5  mov     r12, rdx
0x14000c4f8  movzx   eax, word ptr [rdx+40h]
0x14000c4fc  mov     [rcx+18h], ax
0x14000c500  mov     al, [rdx]
0x14000c502  mov     [rcx+1Ah], al
0x14000c505  mov     [rcx+20h], r13
0x14000c509  mov     rax, [rdx+88h]
0x14000c510  mov     [rcx+28h], rax
0x14000c514  mov     rax, [rdx+90h]
0x14000c51b  mov     [rcx+30h], rax
0x14000c51f  mov     [rcx+38h], r13
0x14000c523  mov     rcx, [rdx+38h]
0x14000c527  lea     edx, [rbp+2]
0x14000c52a  test    rcx, rcx
0x14000c52d  jnz     short loc_14000C534
0x14000c52f  mov     r8d, edx
0x14000c532  jmp     short loc_14000C544
0x14000c534  mov     rax, rbp
0x14000c537  inc     rax
0x14000c53a  cmp     [rcx+rax], r13b
0x14000c53e  jnz     short loc_14000C537
0x14000c540  lea     r8, [rax+1]; unsigned __int64
0x14000c544  mov     rcx, [r12+80h]
0x14000c54c  test    rcx, rcx
0x14000c54f  jz      short loc_14000C561
0x14000c551  mov     rax, rbp
0x14000c554  inc     rax
0x14000c557  cmp     [rcx+rax], r13b
0x14000c55b  jnz     short loc_14000C554
0x14000c55d  lea     rdx, [rax+1]
0x14000c561  mov     rcx, [r12+18h]
0x14000c566  test    rcx, rcx
0x14000c569  jnz     short loc_14000C570
0x14000c56b  lea     eax, [rcx+2]
0x14000c56e  jmp     short loc_14000C585
0x14000c570  mov     rax, rbp
0x14000c573  inc     rax
0x14000c576  cmp     [rcx+rax*2], r13w
0x14000c57b  jnz     short loc_14000C573
0x14000c57d  lea     rax, ds:2[rax*2]
0x14000c585  lea     r14, [rdx+rax]
0x14000c589  add     r14, r8
0x14000c58c  lea     rsi, [rdi+48h]
0x14000c590  cmp     [rdi+40h], r13
0x14000c594  jz      short loc_14000C59B
0x14000c596  cmp     [rsi], r14
0x14000c599  jnb     short loc_14000C5CF
0x14000c59b  mov     rdx, r14; dwBytes
0x14000c59e  mov     ecx, 8; dwFlags
0x14000c5a3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c5a8  mov     r15, rax
0x14000c5ab  test    rax, rax
0x14000c5ae  jz      short loc_14000C5CF
0x14000c5b0  mov     rbx, [rdi+40h]
0x14000c5b4  call    cs:__imp_GetProcessHeap
0x14000c5ba  mov     r8, rbx; lpMem
0x14000c5bd  xor     edx, edx; dwFlags
0x14000c5bf  mov     rcx, rax; hHeap
0x14000c5c2  call    cs:__imp_HeapFree
0x14000c5c8  mov     [rdi+40h], r15
0x14000c5cc  mov     [rsi], r14
0x14000c5cf  mov     rbx, [rdi+40h]
0x14000c5d3  test    rbx, rbx
0x14000c5d6  jz      loc_14000C6D4
0x14000c5dc  mov     rdx, [rsi]; DestinationSize
0x14000c5df  lea     rsi, [rdx+rbx]
0x14000c5e3  cmp     rbx, rsi
0x14000c5e6  jz      short loc_14000C626
0x14000c5e8  mov     r8, [r12+38h]; Source
0x14000c5ed  test    r8, r8
0x14000c5f0  jz      short loc_14000C626
0x14000c5f2  cmp     [r8], r13b
0x14000c5f5  jz      short loc_14000C626
0x14000c5f7  mov     rax, rbp
0x14000c5fa  inc     rax
0x14000c5fd  cmp     [r8+rax], r13b
0x14000c601  jnz     short loc_14000C5FA
0x14000c603  lea     r14, [rax+1]
0x14000c607  cmp     rdx, r14
0x14000c60a  jnb     short loc_14000C612
0x14000c60c  mov     [rdi+10h], r13
0x14000c610  jmp     short loc_14000C62F
0x14000c612  mov     r9, r14; SourceSize
0x14000c615  mov     rcx, rbx; Destination
0x14000c618  call    memcpy_s
0x14000c61d  mov     [rdi+10h], rbx
0x14000c621  add     rbx, r14
0x14000c624  jmp     short loc_14000C62A
0x14000c626  mov     [rdi+10h], r13
0x14000c62a  cmp     rbx, rsi
0x14000c62d  jz      short loc_14000C676
0x14000c62f  mov     r8, [r12+80h]; Source
0x14000c637  test    r8, r8
0x14000c63a  jz      short loc_14000C676
0x14000c63c  cmp     [r8], r13b
0x14000c63f  jz      short loc_14000C676
0x14000c641  mov     rax, rbp
0x14000c644  inc     rax
0x14000c647  cmp     [r8+rax], r13b
0x14000c64b  jnz     short loc_14000C644
0x14000c64d  mov     rdx, rsi
0x14000c650  lea     r14, [rax+1]
0x14000c654  sub     rdx, rbx; DestinationSize
0x14000c657  cmp     rdx, r14
0x14000c65a  jnb     short loc_14000C662
0x14000c65c  mov     [rdi+20h], r13
0x14000c660  jmp     short loc_14000C67F
0x14000c662  mov     r9, r14; SourceSize
0x14000c665  mov     rcx, rbx; Destination
0x14000c668  call    memcpy_s
0x14000c66d  mov     [rdi+20h], rbx
0x14000c671  add     rbx, r14
0x14000c674  jmp     short loc_14000C67A
0x14000c676  mov     [rdi+20h], r13
0x14000c67a  cmp     rbx, rsi
0x14000c67d  jz      short loc_14000C6C0
0x14000c67f  mov     r8, [r12+18h]; Source
0x14000c684  test    r8, r8
0x14000c687  jz      short loc_14000C6C0
0x14000c689  cmp     [r8], r13w
0x14000c68d  jz      short loc_14000C6C0
0x14000c68f  inc     rbp
0x14000c692  cmp     [r8+rbp*2], r13w
0x14000c697  jnz     short loc_14000C68F
0x14000c699  mov     rdx, rsi
0x14000c69c  lea     r14, ds:2[rbp*2]
0x14000c6a4  sub     rdx, rbx; DestinationSize
0x14000c6a7  cmp     rdx, r14
0x14000c6aa  jb      short loc_14000C6C0
0x14000c6ac  mov     r9, r14; SourceSize
0x14000c6af  mov     rcx, rbx; Destination
0x14000c6b2  call    memcpy_s
0x14000c6b7  mov     [rdi+38h], rbx
0x14000c6bb  add     rbx, r14
0x14000c6be  jmp     short loc_14000C6C4
0x14000c6c0  mov     [rdi+38h], r13
0x14000c6c4  sub     rsi, rbx
0x14000c6c7  xor     edx, edx; Val
0x14000c6c9  mov     r8, rsi; Size
0x14000c6cc  mov     rcx, rbx; void *
0x14000c6cf  call    memset_0
0x14000c6d4  add     rsp, 28h
0x14000c6d8  pop     r15
0x14000c6da  pop     r14
0x14000c6dc  pop     r13
0x14000c6de  pop     r12
0x14000c6e0  pop     rdi
0x14000c6e1  pop     rsi
0x14000c6e2  pop     rbp
0x14000c6e3  pop     rbx
0x14000c6e4  retn
```
