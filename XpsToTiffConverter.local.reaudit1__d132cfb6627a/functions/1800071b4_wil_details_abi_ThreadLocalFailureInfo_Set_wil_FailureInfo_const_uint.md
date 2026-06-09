# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800071b4`
- end: `0x1800073cd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004a30`

## callees

- `0x1800020e4`
- `0x180005b98`
- `0x1800071b4`
- `0x180008f08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000729c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000729c`

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
0x1800071b4  push    rbx
0x1800071b6  push    rbp
0x1800071b7  push    rsi
0x1800071b8  push    rdi
0x1800071b9  push    r12
0x1800071bb  push    r13
0x1800071bd  push    r14
0x1800071bf  push    r15
0x1800071c1  sub     rsp, 28h
0x1800071c5  mov     [rcx+4], r8d
0x1800071c9  xor     r13d, r13d
0x1800071cc  mov     eax, [rdx+8]
0x1800071cf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800071d3  mov     [rcx+8], eax
0x1800071d6  mov     rdi, rcx
0x1800071d9  mov     [rcx+10h], r13
0x1800071dd  mov     r12, rdx
0x1800071e0  movzx   eax, word ptr [rdx+40h]
0x1800071e4  mov     [rcx+18h], ax
0x1800071e8  mov     al, [rdx]
0x1800071ea  mov     [rcx+1Ah], al
0x1800071ed  mov     [rcx+20h], r13
0x1800071f1  mov     rax, [rdx+88h]
0x1800071f8  mov     [rcx+28h], rax
0x1800071fc  mov     rax, [rdx+90h]
0x180007203  mov     [rcx+30h], rax
0x180007207  mov     [rcx+38h], r13
0x18000720b  mov     rcx, [rdx+38h]
0x18000720f  lea     edx, [rbp+2]
0x180007212  test    rcx, rcx
0x180007215  jnz     short loc_18000721C
0x180007217  mov     r8d, edx
0x18000721a  jmp     short loc_18000722C
0x18000721c  mov     rax, rbp
0x18000721f  inc     rax
0x180007222  cmp     [rcx+rax], r13b
0x180007226  jnz     short loc_18000721F
0x180007228  lea     r8, [rax+1]; unsigned __int64
0x18000722c  mov     rcx, [r12+80h]
0x180007234  test    rcx, rcx
0x180007237  jz      short loc_180007249
0x180007239  mov     rax, rbp
0x18000723c  inc     rax
0x18000723f  cmp     [rcx+rax], r13b
0x180007243  jnz     short loc_18000723C
0x180007245  lea     rdx, [rax+1]
0x180007249  mov     rcx, [r12+18h]
0x18000724e  test    rcx, rcx
0x180007251  jnz     short loc_180007258
0x180007253  lea     eax, [rcx+2]
0x180007256  jmp     short loc_18000726D
0x180007258  mov     rax, rbp
0x18000725b  inc     rax
0x18000725e  cmp     [rcx+rax*2], r13w
0x180007263  jnz     short loc_18000725B
0x180007265  lea     rax, ds:2[rax*2]
0x18000726d  lea     r14, [rdx+rax]
0x180007271  add     r14, r8
0x180007274  lea     rsi, [rdi+48h]
0x180007278  cmp     [rdi+40h], r13
0x18000727c  jz      short loc_180007283
0x18000727e  cmp     [rsi], r14
0x180007281  jnb     short loc_1800072B7
0x180007283  mov     rdx, r14; dwBytes
0x180007286  mov     ecx, 8; dwFlags
0x18000728b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007290  mov     r15, rax
0x180007293  test    rax, rax
0x180007296  jz      short loc_1800072B7
0x180007298  mov     rbx, [rdi+40h]
0x18000729c  call    cs:__imp_GetProcessHeap
0x1800072a2  mov     r8, rbx; lpMem
0x1800072a5  xor     edx, edx; dwFlags
0x1800072a7  mov     rcx, rax; hHeap
0x1800072aa  call    cs:__imp_HeapFree
0x1800072b0  mov     [rdi+40h], r15
0x1800072b4  mov     [rsi], r14
0x1800072b7  mov     rbx, [rdi+40h]
0x1800072bb  test    rbx, rbx
0x1800072be  jz      loc_1800073BC
0x1800072c4  mov     rdx, [rsi]; DestinationSize
0x1800072c7  lea     rsi, [rdx+rbx]
0x1800072cb  cmp     rbx, rsi
0x1800072ce  jz      short loc_18000730E
0x1800072d0  mov     r8, [r12+38h]; Source
0x1800072d5  test    r8, r8
0x1800072d8  jz      short loc_18000730E
0x1800072da  cmp     [r8], r13b
0x1800072dd  jz      short loc_18000730E
0x1800072df  mov     rax, rbp
0x1800072e2  inc     rax
0x1800072e5  cmp     [r8+rax], r13b
0x1800072e9  jnz     short loc_1800072E2
0x1800072eb  lea     r14, [rax+1]
0x1800072ef  cmp     rdx, r14
0x1800072f2  jnb     short loc_1800072FA
0x1800072f4  mov     [rdi+10h], r13
0x1800072f8  jmp     short loc_180007317
0x1800072fa  mov     r9, r14; SourceSize
0x1800072fd  mov     rcx, rbx; Destination
0x180007300  call    memcpy_s
0x180007305  mov     [rdi+10h], rbx
0x180007309  add     rbx, r14
0x18000730c  jmp     short loc_180007312
0x18000730e  mov     [rdi+10h], r13
0x180007312  cmp     rbx, rsi
0x180007315  jz      short loc_18000735E
0x180007317  mov     r8, [r12+80h]; Source
0x18000731f  test    r8, r8
0x180007322  jz      short loc_18000735E
0x180007324  cmp     [r8], r13b
0x180007327  jz      short loc_18000735E
0x180007329  mov     rax, rbp
0x18000732c  inc     rax
0x18000732f  cmp     [r8+rax], r13b
0x180007333  jnz     short loc_18000732C
0x180007335  mov     rdx, rsi
0x180007338  lea     r14, [rax+1]
0x18000733c  sub     rdx, rbx; DestinationSize
0x18000733f  cmp     rdx, r14
0x180007342  jnb     short loc_18000734A
0x180007344  mov     [rdi+20h], r13
0x180007348  jmp     short loc_180007367
0x18000734a  mov     r9, r14; SourceSize
0x18000734d  mov     rcx, rbx; Destination
0x180007350  call    memcpy_s
0x180007355  mov     [rdi+20h], rbx
0x180007359  add     rbx, r14
0x18000735c  jmp     short loc_180007362
0x18000735e  mov     [rdi+20h], r13
0x180007362  cmp     rbx, rsi
0x180007365  jz      short loc_1800073A8
0x180007367  mov     r8, [r12+18h]; Source
0x18000736c  test    r8, r8
0x18000736f  jz      short loc_1800073A8
0x180007371  cmp     [r8], r13w
0x180007375  jz      short loc_1800073A8
0x180007377  inc     rbp
0x18000737a  cmp     [r8+rbp*2], r13w
0x18000737f  jnz     short loc_180007377
0x180007381  mov     rdx, rsi
0x180007384  lea     r14, ds:2[rbp*2]
0x18000738c  sub     rdx, rbx; DestinationSize
0x18000738f  cmp     rdx, r14
0x180007392  jb      short loc_1800073A8
0x180007394  mov     r9, r14; SourceSize
0x180007397  mov     rcx, rbx; Destination
0x18000739a  call    memcpy_s
0x18000739f  mov     [rdi+38h], rbx
0x1800073a3  add     rbx, r14
0x1800073a6  jmp     short loc_1800073AC
0x1800073a8  mov     [rdi+38h], r13
0x1800073ac  sub     rsi, rbx
0x1800073af  xor     edx, edx; Val
0x1800073b1  mov     r8, rsi; Size
0x1800073b4  mov     rcx, rbx; void *
0x1800073b7  call    memset_0
0x1800073bc  add     rsp, 28h
0x1800073c0  pop     r15
0x1800073c2  pop     r14
0x1800073c4  pop     r13
0x1800073c6  pop     r12
0x1800073c8  pop     rdi
0x1800073c9  pop     rsi
0x1800073ca  pop     rbp
0x1800073cb  pop     rbx
0x1800073cc  retn
```
