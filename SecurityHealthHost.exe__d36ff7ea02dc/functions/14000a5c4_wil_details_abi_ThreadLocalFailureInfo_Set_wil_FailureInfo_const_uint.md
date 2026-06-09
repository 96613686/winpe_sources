# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000a5c4`
- end: `0x14000a7dd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400088b0`

## callees

- `0x1400022ec`
- `0x140009228`
- `0x14000a5c4`
- `0x14000bfd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a6ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a6ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a6ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a6ba`

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
0x14000a5c4  push    rbx
0x14000a5c6  push    rbp
0x14000a5c7  push    rsi
0x14000a5c8  push    rdi
0x14000a5c9  push    r12
0x14000a5cb  push    r13
0x14000a5cd  push    r14
0x14000a5cf  push    r15
0x14000a5d1  sub     rsp, 28h
0x14000a5d5  mov     [rcx+4], r8d
0x14000a5d9  xor     r13d, r13d
0x14000a5dc  mov     eax, [rdx+8]
0x14000a5df  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000a5e3  mov     [rcx+8], eax
0x14000a5e6  mov     rdi, rcx
0x14000a5e9  mov     [rcx+10h], r13
0x14000a5ed  mov     r12, rdx
0x14000a5f0  movzx   eax, word ptr [rdx+40h]
0x14000a5f4  mov     [rcx+18h], ax
0x14000a5f8  mov     al, [rdx]
0x14000a5fa  mov     [rcx+1Ah], al
0x14000a5fd  mov     [rcx+20h], r13
0x14000a601  mov     rax, [rdx+88h]
0x14000a608  mov     [rcx+28h], rax
0x14000a60c  mov     rax, [rdx+90h]
0x14000a613  mov     [rcx+30h], rax
0x14000a617  mov     [rcx+38h], r13
0x14000a61b  mov     rcx, [rdx+38h]
0x14000a61f  lea     edx, [rbp+2]
0x14000a622  test    rcx, rcx
0x14000a625  jnz     short loc_14000A62C
0x14000a627  mov     r8d, edx
0x14000a62a  jmp     short loc_14000A63C
0x14000a62c  mov     rax, rbp
0x14000a62f  inc     rax
0x14000a632  cmp     [rcx+rax], r13b
0x14000a636  jnz     short loc_14000A62F
0x14000a638  lea     r8, [rax+1]; unsigned __int64
0x14000a63c  mov     rcx, [r12+80h]
0x14000a644  test    rcx, rcx
0x14000a647  jz      short loc_14000A659
0x14000a649  mov     rax, rbp
0x14000a64c  inc     rax
0x14000a64f  cmp     [rcx+rax], r13b
0x14000a653  jnz     short loc_14000A64C
0x14000a655  lea     rdx, [rax+1]
0x14000a659  mov     rcx, [r12+18h]
0x14000a65e  test    rcx, rcx
0x14000a661  jnz     short loc_14000A668
0x14000a663  lea     eax, [rcx+2]
0x14000a666  jmp     short loc_14000A67D
0x14000a668  mov     rax, rbp
0x14000a66b  inc     rax
0x14000a66e  cmp     [rcx+rax*2], r13w
0x14000a673  jnz     short loc_14000A66B
0x14000a675  lea     rax, ds:2[rax*2]
0x14000a67d  lea     r14, [rdx+rax]
0x14000a681  add     r14, r8
0x14000a684  lea     rsi, [rdi+48h]
0x14000a688  cmp     [rdi+40h], r13
0x14000a68c  jz      short loc_14000A693
0x14000a68e  cmp     [rsi], r14
0x14000a691  jnb     short loc_14000A6C7
0x14000a693  mov     rdx, r14; dwBytes
0x14000a696  mov     ecx, 8; dwFlags
0x14000a69b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a6a0  mov     r15, rax
0x14000a6a3  test    rax, rax
0x14000a6a6  jz      short loc_14000A6C7
0x14000a6a8  mov     rbx, [rdi+40h]
0x14000a6ac  call    cs:__imp_GetProcessHeap
0x14000a6b2  mov     r8, rbx; lpMem
0x14000a6b5  xor     edx, edx; dwFlags
0x14000a6b7  mov     rcx, rax; hHeap
0x14000a6ba  call    cs:__imp_HeapFree
0x14000a6c0  mov     [rdi+40h], r15
0x14000a6c4  mov     [rsi], r14
0x14000a6c7  mov     rbx, [rdi+40h]
0x14000a6cb  test    rbx, rbx
0x14000a6ce  jz      loc_14000A7CC
0x14000a6d4  mov     rdx, [rsi]; DestinationSize
0x14000a6d7  lea     rsi, [rdx+rbx]
0x14000a6db  cmp     rbx, rsi
0x14000a6de  jz      short loc_14000A71E
0x14000a6e0  mov     r8, [r12+38h]; Source
0x14000a6e5  test    r8, r8
0x14000a6e8  jz      short loc_14000A71E
0x14000a6ea  cmp     [r8], r13b
0x14000a6ed  jz      short loc_14000A71E
0x14000a6ef  mov     rax, rbp
0x14000a6f2  inc     rax
0x14000a6f5  cmp     [r8+rax], r13b
0x14000a6f9  jnz     short loc_14000A6F2
0x14000a6fb  lea     r14, [rax+1]
0x14000a6ff  cmp     rdx, r14
0x14000a702  jnb     short loc_14000A70A
0x14000a704  mov     [rdi+10h], r13
0x14000a708  jmp     short loc_14000A727
0x14000a70a  mov     r9, r14; SourceSize
0x14000a70d  mov     rcx, rbx; Destination
0x14000a710  call    memcpy_s
0x14000a715  mov     [rdi+10h], rbx
0x14000a719  add     rbx, r14
0x14000a71c  jmp     short loc_14000A722
0x14000a71e  mov     [rdi+10h], r13
0x14000a722  cmp     rbx, rsi
0x14000a725  jz      short loc_14000A76E
0x14000a727  mov     r8, [r12+80h]; Source
0x14000a72f  test    r8, r8
0x14000a732  jz      short loc_14000A76E
0x14000a734  cmp     [r8], r13b
0x14000a737  jz      short loc_14000A76E
0x14000a739  mov     rax, rbp
0x14000a73c  inc     rax
0x14000a73f  cmp     [r8+rax], r13b
0x14000a743  jnz     short loc_14000A73C
0x14000a745  mov     rdx, rsi
0x14000a748  lea     r14, [rax+1]
0x14000a74c  sub     rdx, rbx; DestinationSize
0x14000a74f  cmp     rdx, r14
0x14000a752  jnb     short loc_14000A75A
0x14000a754  mov     [rdi+20h], r13
0x14000a758  jmp     short loc_14000A777
0x14000a75a  mov     r9, r14; SourceSize
0x14000a75d  mov     rcx, rbx; Destination
0x14000a760  call    memcpy_s
0x14000a765  mov     [rdi+20h], rbx
0x14000a769  add     rbx, r14
0x14000a76c  jmp     short loc_14000A772
0x14000a76e  mov     [rdi+20h], r13
0x14000a772  cmp     rbx, rsi
0x14000a775  jz      short loc_14000A7B8
0x14000a777  mov     r8, [r12+18h]; Source
0x14000a77c  test    r8, r8
0x14000a77f  jz      short loc_14000A7B8
0x14000a781  cmp     [r8], r13w
0x14000a785  jz      short loc_14000A7B8
0x14000a787  inc     rbp
0x14000a78a  cmp     [r8+rbp*2], r13w
0x14000a78f  jnz     short loc_14000A787
0x14000a791  mov     rdx, rsi
0x14000a794  lea     r14, ds:2[rbp*2]
0x14000a79c  sub     rdx, rbx; DestinationSize
0x14000a79f  cmp     rdx, r14
0x14000a7a2  jb      short loc_14000A7B8
0x14000a7a4  mov     r9, r14; SourceSize
0x14000a7a7  mov     rcx, rbx; Destination
0x14000a7aa  call    memcpy_s
0x14000a7af  mov     [rdi+38h], rbx
0x14000a7b3  add     rbx, r14
0x14000a7b6  jmp     short loc_14000A7BC
0x14000a7b8  mov     [rdi+38h], r13
0x14000a7bc  sub     rsi, rbx
0x14000a7bf  xor     edx, edx; Val
0x14000a7c1  mov     r8, rsi; Size
0x14000a7c4  mov     rcx, rbx; void *
0x14000a7c7  call    memset_0
0x14000a7cc  add     rsp, 28h
0x14000a7d0  pop     r15
0x14000a7d2  pop     r14
0x14000a7d4  pop     r13
0x14000a7d6  pop     r12
0x14000a7d8  pop     rdi
0x14000a7d9  pop     rsi
0x14000a7da  pop     rbp
0x14000a7db  pop     rbx
0x14000a7dc  retn
```
