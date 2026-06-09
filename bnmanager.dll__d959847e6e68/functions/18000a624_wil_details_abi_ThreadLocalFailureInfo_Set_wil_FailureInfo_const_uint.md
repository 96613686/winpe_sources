# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a624`
- end: `0x18000a83d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007c00`

## callees

- `0x180002290`
- `0x180008e98`
- `0x18000a624`
- `0x18000c398`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a71a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a71a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a70c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a70c`

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
0x18000a624  push    rbx
0x18000a626  push    rbp
0x18000a627  push    rsi
0x18000a628  push    rdi
0x18000a629  push    r12
0x18000a62b  push    r13
0x18000a62d  push    r14
0x18000a62f  push    r15
0x18000a631  sub     rsp, 28h
0x18000a635  mov     [rcx+4], r8d
0x18000a639  xor     r13d, r13d
0x18000a63c  mov     eax, [rdx+8]
0x18000a63f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a643  mov     [rcx+8], eax
0x18000a646  mov     rdi, rcx
0x18000a649  mov     [rcx+10h], r13
0x18000a64d  mov     r12, rdx
0x18000a650  movzx   eax, word ptr [rdx+40h]
0x18000a654  mov     [rcx+18h], ax
0x18000a658  mov     al, [rdx]
0x18000a65a  mov     [rcx+1Ah], al
0x18000a65d  mov     [rcx+20h], r13
0x18000a661  mov     rax, [rdx+88h]
0x18000a668  mov     [rcx+28h], rax
0x18000a66c  mov     rax, [rdx+90h]
0x18000a673  mov     [rcx+30h], rax
0x18000a677  mov     [rcx+38h], r13
0x18000a67b  mov     rcx, [rdx+38h]
0x18000a67f  lea     edx, [rbp+2]
0x18000a682  test    rcx, rcx
0x18000a685  jnz     short loc_18000A68C
0x18000a687  mov     r8d, edx
0x18000a68a  jmp     short loc_18000A69C
0x18000a68c  mov     rax, rbp
0x18000a68f  inc     rax
0x18000a692  cmp     [rcx+rax], r13b
0x18000a696  jnz     short loc_18000A68F
0x18000a698  lea     r8, [rax+1]; unsigned __int64
0x18000a69c  mov     rcx, [r12+80h]
0x18000a6a4  test    rcx, rcx
0x18000a6a7  jz      short loc_18000A6B9
0x18000a6a9  mov     rax, rbp
0x18000a6ac  inc     rax
0x18000a6af  cmp     [rcx+rax], r13b
0x18000a6b3  jnz     short loc_18000A6AC
0x18000a6b5  lea     rdx, [rax+1]
0x18000a6b9  mov     rcx, [r12+18h]
0x18000a6be  test    rcx, rcx
0x18000a6c1  jnz     short loc_18000A6C8
0x18000a6c3  lea     eax, [rcx+2]
0x18000a6c6  jmp     short loc_18000A6DD
0x18000a6c8  mov     rax, rbp
0x18000a6cb  inc     rax
0x18000a6ce  cmp     [rcx+rax*2], r13w
0x18000a6d3  jnz     short loc_18000A6CB
0x18000a6d5  lea     rax, ds:2[rax*2]
0x18000a6dd  lea     r14, [rdx+rax]
0x18000a6e1  add     r14, r8
0x18000a6e4  lea     rsi, [rdi+48h]
0x18000a6e8  cmp     [rdi+40h], r13
0x18000a6ec  jz      short loc_18000A6F3
0x18000a6ee  cmp     [rsi], r14
0x18000a6f1  jnb     short loc_18000A727
0x18000a6f3  mov     rdx, r14; dwBytes
0x18000a6f6  mov     ecx, 8; dwFlags
0x18000a6fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a700  mov     r15, rax
0x18000a703  test    rax, rax
0x18000a706  jz      short loc_18000A727
0x18000a708  mov     rbx, [rdi+40h]
0x18000a70c  call    cs:__imp_GetProcessHeap
0x18000a712  mov     r8, rbx; lpMem
0x18000a715  xor     edx, edx; dwFlags
0x18000a717  mov     rcx, rax; hHeap
0x18000a71a  call    cs:__imp_HeapFree
0x18000a720  mov     [rdi+40h], r15
0x18000a724  mov     [rsi], r14
0x18000a727  mov     rbx, [rdi+40h]
0x18000a72b  test    rbx, rbx
0x18000a72e  jz      loc_18000A82C
0x18000a734  mov     rdx, [rsi]; DestinationSize
0x18000a737  lea     rsi, [rdx+rbx]
0x18000a73b  cmp     rbx, rsi
0x18000a73e  jz      short loc_18000A77E
0x18000a740  mov     r8, [r12+38h]; Source
0x18000a745  test    r8, r8
0x18000a748  jz      short loc_18000A77E
0x18000a74a  cmp     [r8], r13b
0x18000a74d  jz      short loc_18000A77E
0x18000a74f  mov     rax, rbp
0x18000a752  inc     rax
0x18000a755  cmp     [r8+rax], r13b
0x18000a759  jnz     short loc_18000A752
0x18000a75b  lea     r14, [rax+1]
0x18000a75f  cmp     rdx, r14
0x18000a762  jnb     short loc_18000A76A
0x18000a764  mov     [rdi+10h], r13
0x18000a768  jmp     short loc_18000A787
0x18000a76a  mov     r9, r14; SourceSize
0x18000a76d  mov     rcx, rbx; Destination
0x18000a770  call    memcpy_s
0x18000a775  mov     [rdi+10h], rbx
0x18000a779  add     rbx, r14
0x18000a77c  jmp     short loc_18000A782
0x18000a77e  mov     [rdi+10h], r13
0x18000a782  cmp     rbx, rsi
0x18000a785  jz      short loc_18000A7CE
0x18000a787  mov     r8, [r12+80h]; Source
0x18000a78f  test    r8, r8
0x18000a792  jz      short loc_18000A7CE
0x18000a794  cmp     [r8], r13b
0x18000a797  jz      short loc_18000A7CE
0x18000a799  mov     rax, rbp
0x18000a79c  inc     rax
0x18000a79f  cmp     [r8+rax], r13b
0x18000a7a3  jnz     short loc_18000A79C
0x18000a7a5  mov     rdx, rsi
0x18000a7a8  lea     r14, [rax+1]
0x18000a7ac  sub     rdx, rbx; DestinationSize
0x18000a7af  cmp     rdx, r14
0x18000a7b2  jnb     short loc_18000A7BA
0x18000a7b4  mov     [rdi+20h], r13
0x18000a7b8  jmp     short loc_18000A7D7
0x18000a7ba  mov     r9, r14; SourceSize
0x18000a7bd  mov     rcx, rbx; Destination
0x18000a7c0  call    memcpy_s
0x18000a7c5  mov     [rdi+20h], rbx
0x18000a7c9  add     rbx, r14
0x18000a7cc  jmp     short loc_18000A7D2
0x18000a7ce  mov     [rdi+20h], r13
0x18000a7d2  cmp     rbx, rsi
0x18000a7d5  jz      short loc_18000A818
0x18000a7d7  mov     r8, [r12+18h]; Source
0x18000a7dc  test    r8, r8
0x18000a7df  jz      short loc_18000A818
0x18000a7e1  cmp     [r8], r13w
0x18000a7e5  jz      short loc_18000A818
0x18000a7e7  inc     rbp
0x18000a7ea  cmp     [r8+rbp*2], r13w
0x18000a7ef  jnz     short loc_18000A7E7
0x18000a7f1  mov     rdx, rsi
0x18000a7f4  lea     r14, ds:2[rbp*2]
0x18000a7fc  sub     rdx, rbx; DestinationSize
0x18000a7ff  cmp     rdx, r14
0x18000a802  jb      short loc_18000A818
0x18000a804  mov     r9, r14; SourceSize
0x18000a807  mov     rcx, rbx; Destination
0x18000a80a  call    memcpy_s
0x18000a80f  mov     [rdi+38h], rbx
0x18000a813  add     rbx, r14
0x18000a816  jmp     short loc_18000A81C
0x18000a818  mov     [rdi+38h], r13
0x18000a81c  sub     rsi, rbx
0x18000a81f  xor     edx, edx; Val
0x18000a821  mov     r8, rsi; Size
0x18000a824  mov     rcx, rbx; void *
0x18000a827  call    memset_0
0x18000a82c  add     rsp, 28h
0x18000a830  pop     r15
0x18000a832  pop     r14
0x18000a834  pop     r13
0x18000a836  pop     r12
0x18000a838  pop     rdi
0x18000a839  pop     rsi
0x18000a83a  pop     rbp
0x18000a83b  pop     rbx
0x18000a83c  retn
```
