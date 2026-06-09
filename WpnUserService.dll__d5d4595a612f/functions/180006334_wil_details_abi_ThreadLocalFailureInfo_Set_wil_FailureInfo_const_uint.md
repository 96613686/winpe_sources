# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006334`
- end: `0x18000654d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d60`

## callees

- `0x18000354c`
- `0x180005e58`
- `0x180006334`
- `0x1800073b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000642a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000642a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000641c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000641c`

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
0x180006334  push    rbx
0x180006336  push    rbp
0x180006337  push    rsi
0x180006338  push    rdi
0x180006339  push    r12
0x18000633b  push    r13
0x18000633d  push    r14
0x18000633f  push    r15
0x180006341  sub     rsp, 28h
0x180006345  mov     [rcx+4], r8d
0x180006349  xor     r13d, r13d
0x18000634c  mov     eax, [rdx+8]
0x18000634f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006353  mov     [rcx+8], eax
0x180006356  mov     rdi, rcx
0x180006359  mov     [rcx+10h], r13
0x18000635d  mov     r12, rdx
0x180006360  movzx   eax, word ptr [rdx+40h]
0x180006364  mov     [rcx+18h], ax
0x180006368  mov     al, [rdx]
0x18000636a  mov     [rcx+1Ah], al
0x18000636d  mov     [rcx+20h], r13
0x180006371  mov     rax, [rdx+88h]
0x180006378  mov     [rcx+28h], rax
0x18000637c  mov     rax, [rdx+90h]
0x180006383  mov     [rcx+30h], rax
0x180006387  mov     [rcx+38h], r13
0x18000638b  mov     rcx, [rdx+38h]
0x18000638f  lea     edx, [rbp+2]
0x180006392  test    rcx, rcx
0x180006395  jnz     short loc_18000639C
0x180006397  mov     r8d, edx
0x18000639a  jmp     short loc_1800063AC
0x18000639c  mov     rax, rbp
0x18000639f  inc     rax
0x1800063a2  cmp     [rcx+rax], r13b
0x1800063a6  jnz     short loc_18000639F
0x1800063a8  lea     r8, [rax+1]; unsigned __int64
0x1800063ac  mov     rcx, [r12+80h]
0x1800063b4  test    rcx, rcx
0x1800063b7  jz      short loc_1800063C9
0x1800063b9  mov     rax, rbp
0x1800063bc  inc     rax
0x1800063bf  cmp     [rcx+rax], r13b
0x1800063c3  jnz     short loc_1800063BC
0x1800063c5  lea     rdx, [rax+1]
0x1800063c9  mov     rcx, [r12+18h]
0x1800063ce  test    rcx, rcx
0x1800063d1  jnz     short loc_1800063D8
0x1800063d3  lea     eax, [rcx+2]
0x1800063d6  jmp     short loc_1800063ED
0x1800063d8  mov     rax, rbp
0x1800063db  inc     rax
0x1800063de  cmp     [rcx+rax*2], r13w
0x1800063e3  jnz     short loc_1800063DB
0x1800063e5  lea     rax, ds:2[rax*2]
0x1800063ed  lea     r14, [rdx+rax]
0x1800063f1  add     r14, r8
0x1800063f4  lea     rsi, [rdi+48h]
0x1800063f8  cmp     [rdi+40h], r13
0x1800063fc  jz      short loc_180006403
0x1800063fe  cmp     [rsi], r14
0x180006401  jnb     short loc_180006437
0x180006403  mov     rdx, r14; dwBytes
0x180006406  mov     ecx, 8; dwFlags
0x18000640b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006410  mov     r15, rax
0x180006413  test    rax, rax
0x180006416  jz      short loc_180006437
0x180006418  mov     rbx, [rdi+40h]
0x18000641c  call    cs:__imp_GetProcessHeap
0x180006422  mov     r8, rbx; lpMem
0x180006425  xor     edx, edx; dwFlags
0x180006427  mov     rcx, rax; hHeap
0x18000642a  call    cs:__imp_HeapFree
0x180006430  mov     [rdi+40h], r15
0x180006434  mov     [rsi], r14
0x180006437  mov     rbx, [rdi+40h]
0x18000643b  test    rbx, rbx
0x18000643e  jz      loc_18000653C
0x180006444  mov     rdx, [rsi]; DestinationSize
0x180006447  lea     rsi, [rdx+rbx]
0x18000644b  cmp     rbx, rsi
0x18000644e  jz      short loc_18000648E
0x180006450  mov     r8, [r12+38h]; Source
0x180006455  test    r8, r8
0x180006458  jz      short loc_18000648E
0x18000645a  cmp     [r8], r13b
0x18000645d  jz      short loc_18000648E
0x18000645f  mov     rax, rbp
0x180006462  inc     rax
0x180006465  cmp     [r8+rax], r13b
0x180006469  jnz     short loc_180006462
0x18000646b  lea     r14, [rax+1]
0x18000646f  cmp     rdx, r14
0x180006472  jnb     short loc_18000647A
0x180006474  mov     [rdi+10h], r13
0x180006478  jmp     short loc_180006497
0x18000647a  mov     r9, r14; SourceSize
0x18000647d  mov     rcx, rbx; Destination
0x180006480  call    memcpy_s
0x180006485  mov     [rdi+10h], rbx
0x180006489  add     rbx, r14
0x18000648c  jmp     short loc_180006492
0x18000648e  mov     [rdi+10h], r13
0x180006492  cmp     rbx, rsi
0x180006495  jz      short loc_1800064DE
0x180006497  mov     r8, [r12+80h]; Source
0x18000649f  test    r8, r8
0x1800064a2  jz      short loc_1800064DE
0x1800064a4  cmp     [r8], r13b
0x1800064a7  jz      short loc_1800064DE
0x1800064a9  mov     rax, rbp
0x1800064ac  inc     rax
0x1800064af  cmp     [r8+rax], r13b
0x1800064b3  jnz     short loc_1800064AC
0x1800064b5  mov     rdx, rsi
0x1800064b8  lea     r14, [rax+1]
0x1800064bc  sub     rdx, rbx; DestinationSize
0x1800064bf  cmp     rdx, r14
0x1800064c2  jnb     short loc_1800064CA
0x1800064c4  mov     [rdi+20h], r13
0x1800064c8  jmp     short loc_1800064E7
0x1800064ca  mov     r9, r14; SourceSize
0x1800064cd  mov     rcx, rbx; Destination
0x1800064d0  call    memcpy_s
0x1800064d5  mov     [rdi+20h], rbx
0x1800064d9  add     rbx, r14
0x1800064dc  jmp     short loc_1800064E2
0x1800064de  mov     [rdi+20h], r13
0x1800064e2  cmp     rbx, rsi
0x1800064e5  jz      short loc_180006528
0x1800064e7  mov     r8, [r12+18h]; Source
0x1800064ec  test    r8, r8
0x1800064ef  jz      short loc_180006528
0x1800064f1  cmp     [r8], r13w
0x1800064f5  jz      short loc_180006528
0x1800064f7  inc     rbp
0x1800064fa  cmp     [r8+rbp*2], r13w
0x1800064ff  jnz     short loc_1800064F7
0x180006501  mov     rdx, rsi
0x180006504  lea     r14, ds:2[rbp*2]
0x18000650c  sub     rdx, rbx; DestinationSize
0x18000650f  cmp     rdx, r14
0x180006512  jb      short loc_180006528
0x180006514  mov     r9, r14; SourceSize
0x180006517  mov     rcx, rbx; Destination
0x18000651a  call    memcpy_s
0x18000651f  mov     [rdi+38h], rbx
0x180006523  add     rbx, r14
0x180006526  jmp     short loc_18000652C
0x180006528  mov     [rdi+38h], r13
0x18000652c  sub     rsi, rbx
0x18000652f  xor     edx, edx; Val
0x180006531  mov     r8, rsi; Size
0x180006534  mov     rcx, rbx; void *
0x180006537  call    memset_0
0x18000653c  add     rsp, 28h
0x180006540  pop     r15
0x180006542  pop     r14
0x180006544  pop     r13
0x180006546  pop     r12
0x180006548  pop     rdi
0x180006549  pop     rsi
0x18000654a  pop     rbp
0x18000654b  pop     rbx
0x18000654c  retn
```
