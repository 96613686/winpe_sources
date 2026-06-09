# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a210`
- end: `0x18000a429`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007390`

## callees

- `0x1800042f4`
- `0x1800088e0`
- `0x18000a210`
- `0x18000cd84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a306`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a306`

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
                memcpy_s_0(v20, v22 - v20, v29, 2 * v3 + 2);
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
          memcpy_s_0(v20, v22 - v20, v26, v27 + 1);
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
      memcpy_s_0(*((void *const *)this + 8), v21, v23, v24 + 1);
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
0x18000a210  push    rbx
0x18000a212  push    rbp
0x18000a213  push    rsi
0x18000a214  push    rdi
0x18000a215  push    r12
0x18000a217  push    r13
0x18000a219  push    r14
0x18000a21b  push    r15
0x18000a21d  sub     rsp, 28h
0x18000a221  mov     [rcx+4], r8d
0x18000a225  xor     r13d, r13d
0x18000a228  mov     eax, [rdx+8]
0x18000a22b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a22f  mov     [rcx+8], eax
0x18000a232  mov     rdi, rcx
0x18000a235  mov     [rcx+10h], r13
0x18000a239  mov     r12, rdx
0x18000a23c  movzx   eax, word ptr [rdx+40h]
0x18000a240  mov     [rcx+18h], ax
0x18000a244  mov     al, [rdx]
0x18000a246  mov     [rcx+1Ah], al
0x18000a249  mov     [rcx+20h], r13
0x18000a24d  mov     rax, [rdx+88h]
0x18000a254  mov     [rcx+28h], rax
0x18000a258  mov     rax, [rdx+90h]
0x18000a25f  mov     [rcx+30h], rax
0x18000a263  mov     [rcx+38h], r13
0x18000a267  mov     rcx, [rdx+38h]
0x18000a26b  lea     edx, [rbp+2]
0x18000a26e  test    rcx, rcx
0x18000a271  jnz     short loc_18000A278
0x18000a273  mov     r8d, edx
0x18000a276  jmp     short loc_18000A288
0x18000a278  mov     rax, rbp
0x18000a27b  inc     rax
0x18000a27e  cmp     [rcx+rax], r13b
0x18000a282  jnz     short loc_18000A27B
0x18000a284  lea     r8, [rax+1]; unsigned __int64
0x18000a288  mov     rcx, [r12+80h]
0x18000a290  test    rcx, rcx
0x18000a293  jz      short loc_18000A2A5
0x18000a295  mov     rax, rbp
0x18000a298  inc     rax
0x18000a29b  cmp     [rcx+rax], r13b
0x18000a29f  jnz     short loc_18000A298
0x18000a2a1  lea     rdx, [rax+1]
0x18000a2a5  mov     rcx, [r12+18h]
0x18000a2aa  test    rcx, rcx
0x18000a2ad  jnz     short loc_18000A2B4
0x18000a2af  lea     eax, [rcx+2]
0x18000a2b2  jmp     short loc_18000A2C9
0x18000a2b4  mov     rax, rbp
0x18000a2b7  inc     rax
0x18000a2ba  cmp     [rcx+rax*2], r13w
0x18000a2bf  jnz     short loc_18000A2B7
0x18000a2c1  lea     rax, ds:2[rax*2]
0x18000a2c9  lea     r14, [rdx+rax]
0x18000a2cd  add     r14, r8
0x18000a2d0  lea     rsi, [rdi+48h]
0x18000a2d4  cmp     [rdi+40h], r13
0x18000a2d8  jz      short loc_18000A2DF
0x18000a2da  cmp     [rsi], r14
0x18000a2dd  jnb     short loc_18000A313
0x18000a2df  mov     rdx, r14; dwBytes
0x18000a2e2  mov     ecx, 8; dwFlags
0x18000a2e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a2ec  mov     r15, rax
0x18000a2ef  test    rax, rax
0x18000a2f2  jz      short loc_18000A313
0x18000a2f4  mov     rbx, [rdi+40h]
0x18000a2f8  call    cs:__imp_GetProcessHeap
0x18000a2fe  mov     r8, rbx; lpMem
0x18000a301  xor     edx, edx; dwFlags
0x18000a303  mov     rcx, rax; hHeap
0x18000a306  call    cs:__imp_HeapFree
0x18000a30c  mov     [rdi+40h], r15
0x18000a310  mov     [rsi], r14
0x18000a313  mov     rbx, [rdi+40h]
0x18000a317  test    rbx, rbx
0x18000a31a  jz      loc_18000A418
0x18000a320  mov     rdx, [rsi]; DestinationSize
0x18000a323  lea     rsi, [rdx+rbx]
0x18000a327  cmp     rbx, rsi
0x18000a32a  jz      short loc_18000A36A
0x18000a32c  mov     r8, [r12+38h]; Source
0x18000a331  test    r8, r8
0x18000a334  jz      short loc_18000A36A
0x18000a336  cmp     [r8], r13b
0x18000a339  jz      short loc_18000A36A
0x18000a33b  mov     rax, rbp
0x18000a33e  inc     rax
0x18000a341  cmp     [r8+rax], r13b
0x18000a345  jnz     short loc_18000A33E
0x18000a347  lea     r14, [rax+1]
0x18000a34b  cmp     rdx, r14
0x18000a34e  jnb     short loc_18000A356
0x18000a350  mov     [rdi+10h], r13
0x18000a354  jmp     short loc_18000A373
0x18000a356  mov     r9, r14; SourceSize
0x18000a359  mov     rcx, rbx; Destination
0x18000a35c  call    memcpy_s_0
0x18000a361  mov     [rdi+10h], rbx
0x18000a365  add     rbx, r14
0x18000a368  jmp     short loc_18000A36E
0x18000a36a  mov     [rdi+10h], r13
0x18000a36e  cmp     rbx, rsi
0x18000a371  jz      short loc_18000A3BA
0x18000a373  mov     r8, [r12+80h]; Source
0x18000a37b  test    r8, r8
0x18000a37e  jz      short loc_18000A3BA
0x18000a380  cmp     [r8], r13b
0x18000a383  jz      short loc_18000A3BA
0x18000a385  mov     rax, rbp
0x18000a388  inc     rax
0x18000a38b  cmp     [r8+rax], r13b
0x18000a38f  jnz     short loc_18000A388
0x18000a391  mov     rdx, rsi
0x18000a394  lea     r14, [rax+1]
0x18000a398  sub     rdx, rbx; DestinationSize
0x18000a39b  cmp     rdx, r14
0x18000a39e  jnb     short loc_18000A3A6
0x18000a3a0  mov     [rdi+20h], r13
0x18000a3a4  jmp     short loc_18000A3C3
0x18000a3a6  mov     r9, r14; SourceSize
0x18000a3a9  mov     rcx, rbx; Destination
0x18000a3ac  call    memcpy_s_0
0x18000a3b1  mov     [rdi+20h], rbx
0x18000a3b5  add     rbx, r14
0x18000a3b8  jmp     short loc_18000A3BE
0x18000a3ba  mov     [rdi+20h], r13
0x18000a3be  cmp     rbx, rsi
0x18000a3c1  jz      short loc_18000A404
0x18000a3c3  mov     r8, [r12+18h]; Source
0x18000a3c8  test    r8, r8
0x18000a3cb  jz      short loc_18000A404
0x18000a3cd  cmp     [r8], r13w
0x18000a3d1  jz      short loc_18000A404
0x18000a3d3  inc     rbp
0x18000a3d6  cmp     [r8+rbp*2], r13w
0x18000a3db  jnz     short loc_18000A3D3
0x18000a3dd  mov     rdx, rsi
0x18000a3e0  lea     r14, ds:2[rbp*2]
0x18000a3e8  sub     rdx, rbx; DestinationSize
0x18000a3eb  cmp     rdx, r14
0x18000a3ee  jb      short loc_18000A404
0x18000a3f0  mov     r9, r14; SourceSize
0x18000a3f3  mov     rcx, rbx; Destination
0x18000a3f6  call    memcpy_s_0
0x18000a3fb  mov     [rdi+38h], rbx
0x18000a3ff  add     rbx, r14
0x18000a402  jmp     short loc_18000A408
0x18000a404  mov     [rdi+38h], r13
0x18000a408  sub     rsi, rbx
0x18000a40b  xor     edx, edx; Val
0x18000a40d  mov     r8, rsi; Size
0x18000a410  mov     rcx, rbx; void *
0x18000a413  call    memset_0
0x18000a418  add     rsp, 28h
0x18000a41c  pop     r15
0x18000a41e  pop     r14
0x18000a420  pop     r13
0x18000a422  pop     r12
0x18000a424  pop     rdi
0x18000a425  pop     rsi
0x18000a426  pop     rbp
0x18000a427  pop     rbx
0x18000a428  retn
```
