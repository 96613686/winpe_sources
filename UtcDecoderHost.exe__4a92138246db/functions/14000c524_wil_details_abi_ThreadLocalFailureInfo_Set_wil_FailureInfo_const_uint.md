# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c524`
- end: `0x14000c73d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b270`

## callees

- `0x1400090ec`
- `0x14000bfc8`
- `0x14000c524`
- `0x14000d608`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c61a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c61a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c60c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c60c`

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
0x14000c524  push    rbx
0x14000c526  push    rbp
0x14000c527  push    rsi
0x14000c528  push    rdi
0x14000c529  push    r12
0x14000c52b  push    r13
0x14000c52d  push    r14
0x14000c52f  push    r15
0x14000c531  sub     rsp, 28h
0x14000c535  mov     [rcx+4], r8d
0x14000c539  xor     r13d, r13d
0x14000c53c  mov     eax, [rdx+8]
0x14000c53f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000c543  mov     [rcx+8], eax
0x14000c546  mov     rdi, rcx
0x14000c549  mov     [rcx+10h], r13
0x14000c54d  mov     r12, rdx
0x14000c550  movzx   eax, word ptr [rdx+40h]
0x14000c554  mov     [rcx+18h], ax
0x14000c558  mov     al, [rdx]
0x14000c55a  mov     [rcx+1Ah], al
0x14000c55d  mov     [rcx+20h], r13
0x14000c561  mov     rax, [rdx+88h]
0x14000c568  mov     [rcx+28h], rax
0x14000c56c  mov     rax, [rdx+90h]
0x14000c573  mov     [rcx+30h], rax
0x14000c577  mov     [rcx+38h], r13
0x14000c57b  mov     rcx, [rdx+38h]
0x14000c57f  lea     edx, [rbp+2]
0x14000c582  test    rcx, rcx
0x14000c585  jnz     short loc_14000C58C
0x14000c587  mov     r8d, edx
0x14000c58a  jmp     short loc_14000C59C
0x14000c58c  mov     rax, rbp
0x14000c58f  inc     rax
0x14000c592  cmp     [rcx+rax], r13b
0x14000c596  jnz     short loc_14000C58F
0x14000c598  lea     r8, [rax+1]; unsigned __int64
0x14000c59c  mov     rcx, [r12+80h]
0x14000c5a4  test    rcx, rcx
0x14000c5a7  jz      short loc_14000C5B9
0x14000c5a9  mov     rax, rbp
0x14000c5ac  inc     rax
0x14000c5af  cmp     [rcx+rax], r13b
0x14000c5b3  jnz     short loc_14000C5AC
0x14000c5b5  lea     rdx, [rax+1]
0x14000c5b9  mov     rcx, [r12+18h]
0x14000c5be  test    rcx, rcx
0x14000c5c1  jnz     short loc_14000C5C8
0x14000c5c3  lea     eax, [rcx+2]
0x14000c5c6  jmp     short loc_14000C5DD
0x14000c5c8  mov     rax, rbp
0x14000c5cb  inc     rax
0x14000c5ce  cmp     [rcx+rax*2], r13w
0x14000c5d3  jnz     short loc_14000C5CB
0x14000c5d5  lea     rax, ds:2[rax*2]
0x14000c5dd  lea     r14, [rdx+rax]
0x14000c5e1  add     r14, r8
0x14000c5e4  lea     rsi, [rdi+48h]
0x14000c5e8  cmp     [rdi+40h], r13
0x14000c5ec  jz      short loc_14000C5F3
0x14000c5ee  cmp     [rsi], r14
0x14000c5f1  jnb     short loc_14000C627
0x14000c5f3  mov     rdx, r14; dwBytes
0x14000c5f6  mov     ecx, 8; dwFlags
0x14000c5fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c600  mov     r15, rax
0x14000c603  test    rax, rax
0x14000c606  jz      short loc_14000C627
0x14000c608  mov     rbx, [rdi+40h]
0x14000c60c  call    cs:__imp_GetProcessHeap
0x14000c612  mov     r8, rbx; lpMem
0x14000c615  xor     edx, edx; dwFlags
0x14000c617  mov     rcx, rax; hHeap
0x14000c61a  call    cs:__imp_HeapFree
0x14000c620  mov     [rdi+40h], r15
0x14000c624  mov     [rsi], r14
0x14000c627  mov     rbx, [rdi+40h]
0x14000c62b  test    rbx, rbx
0x14000c62e  jz      loc_14000C72C
0x14000c634  mov     rdx, [rsi]; DestinationSize
0x14000c637  lea     rsi, [rdx+rbx]
0x14000c63b  cmp     rbx, rsi
0x14000c63e  jz      short loc_14000C67E
0x14000c640  mov     r8, [r12+38h]; Source
0x14000c645  test    r8, r8
0x14000c648  jz      short loc_14000C67E
0x14000c64a  cmp     [r8], r13b
0x14000c64d  jz      short loc_14000C67E
0x14000c64f  mov     rax, rbp
0x14000c652  inc     rax
0x14000c655  cmp     [r8+rax], r13b
0x14000c659  jnz     short loc_14000C652
0x14000c65b  lea     r14, [rax+1]
0x14000c65f  cmp     rdx, r14
0x14000c662  jnb     short loc_14000C66A
0x14000c664  mov     [rdi+10h], r13
0x14000c668  jmp     short loc_14000C687
0x14000c66a  mov     r9, r14; SourceSize
0x14000c66d  mov     rcx, rbx; Destination
0x14000c670  call    memcpy_s
0x14000c675  mov     [rdi+10h], rbx
0x14000c679  add     rbx, r14
0x14000c67c  jmp     short loc_14000C682
0x14000c67e  mov     [rdi+10h], r13
0x14000c682  cmp     rbx, rsi
0x14000c685  jz      short loc_14000C6CE
0x14000c687  mov     r8, [r12+80h]; Source
0x14000c68f  test    r8, r8
0x14000c692  jz      short loc_14000C6CE
0x14000c694  cmp     [r8], r13b
0x14000c697  jz      short loc_14000C6CE
0x14000c699  mov     rax, rbp
0x14000c69c  inc     rax
0x14000c69f  cmp     [r8+rax], r13b
0x14000c6a3  jnz     short loc_14000C69C
0x14000c6a5  mov     rdx, rsi
0x14000c6a8  lea     r14, [rax+1]
0x14000c6ac  sub     rdx, rbx; DestinationSize
0x14000c6af  cmp     rdx, r14
0x14000c6b2  jnb     short loc_14000C6BA
0x14000c6b4  mov     [rdi+20h], r13
0x14000c6b8  jmp     short loc_14000C6D7
0x14000c6ba  mov     r9, r14; SourceSize
0x14000c6bd  mov     rcx, rbx; Destination
0x14000c6c0  call    memcpy_s
0x14000c6c5  mov     [rdi+20h], rbx
0x14000c6c9  add     rbx, r14
0x14000c6cc  jmp     short loc_14000C6D2
0x14000c6ce  mov     [rdi+20h], r13
0x14000c6d2  cmp     rbx, rsi
0x14000c6d5  jz      short loc_14000C718
0x14000c6d7  mov     r8, [r12+18h]; Source
0x14000c6dc  test    r8, r8
0x14000c6df  jz      short loc_14000C718
0x14000c6e1  cmp     [r8], r13w
0x14000c6e5  jz      short loc_14000C718
0x14000c6e7  inc     rbp
0x14000c6ea  cmp     [r8+rbp*2], r13w
0x14000c6ef  jnz     short loc_14000C6E7
0x14000c6f1  mov     rdx, rsi
0x14000c6f4  lea     r14, ds:2[rbp*2]
0x14000c6fc  sub     rdx, rbx; DestinationSize
0x14000c6ff  cmp     rdx, r14
0x14000c702  jb      short loc_14000C718
0x14000c704  mov     r9, r14; SourceSize
0x14000c707  mov     rcx, rbx; Destination
0x14000c70a  call    memcpy_s
0x14000c70f  mov     [rdi+38h], rbx
0x14000c713  add     rbx, r14
0x14000c716  jmp     short loc_14000C71C
0x14000c718  mov     [rdi+38h], r13
0x14000c71c  sub     rsi, rbx
0x14000c71f  xor     edx, edx; Val
0x14000c721  mov     r8, rsi; Size
0x14000c724  mov     rcx, rbx; void *
0x14000c727  call    memset_0
0x14000c72c  add     rsp, 28h
0x14000c730  pop     r15
0x14000c732  pop     r14
0x14000c734  pop     r13
0x14000c736  pop     r12
0x14000c738  pop     rdi
0x14000c739  pop     rsi
0x14000c73a  pop     rbp
0x14000c73b  pop     rbx
0x14000c73c  retn
```
