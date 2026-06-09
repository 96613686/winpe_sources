# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007528`
- end: `0x180007741`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004c80`

## callees

- `0x1800026b4`
- `0x180005ea8`
- `0x180007528`
- `0x180008a94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000761e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000761e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007610`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007610`

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
0x180007528  push    rbx
0x18000752a  push    rbp
0x18000752b  push    rsi
0x18000752c  push    rdi
0x18000752d  push    r12
0x18000752f  push    r13
0x180007531  push    r14
0x180007533  push    r15
0x180007535  sub     rsp, 28h
0x180007539  mov     [rcx+4], r8d
0x18000753d  xor     r13d, r13d
0x180007540  mov     eax, [rdx+8]
0x180007543  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007547  mov     [rcx+8], eax
0x18000754a  mov     rdi, rcx
0x18000754d  mov     [rcx+10h], r13
0x180007551  mov     r12, rdx
0x180007554  movzx   eax, word ptr [rdx+40h]
0x180007558  mov     [rcx+18h], ax
0x18000755c  mov     al, [rdx]
0x18000755e  mov     [rcx+1Ah], al
0x180007561  mov     [rcx+20h], r13
0x180007565  mov     rax, [rdx+88h]
0x18000756c  mov     [rcx+28h], rax
0x180007570  mov     rax, [rdx+90h]
0x180007577  mov     [rcx+30h], rax
0x18000757b  mov     [rcx+38h], r13
0x18000757f  mov     rcx, [rdx+38h]
0x180007583  lea     edx, [rbp+2]
0x180007586  test    rcx, rcx
0x180007589  jnz     short loc_180007590
0x18000758b  mov     r8d, edx
0x18000758e  jmp     short loc_1800075A0
0x180007590  mov     rax, rbp
0x180007593  inc     rax
0x180007596  cmp     [rcx+rax], r13b
0x18000759a  jnz     short loc_180007593
0x18000759c  lea     r8, [rax+1]; unsigned __int64
0x1800075a0  mov     rcx, [r12+80h]
0x1800075a8  test    rcx, rcx
0x1800075ab  jz      short loc_1800075BD
0x1800075ad  mov     rax, rbp
0x1800075b0  inc     rax
0x1800075b3  cmp     [rcx+rax], r13b
0x1800075b7  jnz     short loc_1800075B0
0x1800075b9  lea     rdx, [rax+1]
0x1800075bd  mov     rcx, [r12+18h]
0x1800075c2  test    rcx, rcx
0x1800075c5  jnz     short loc_1800075CC
0x1800075c7  lea     eax, [rcx+2]
0x1800075ca  jmp     short loc_1800075E1
0x1800075cc  mov     rax, rbp
0x1800075cf  inc     rax
0x1800075d2  cmp     [rcx+rax*2], r13w
0x1800075d7  jnz     short loc_1800075CF
0x1800075d9  lea     rax, ds:2[rax*2]
0x1800075e1  lea     r14, [rdx+rax]
0x1800075e5  add     r14, r8
0x1800075e8  lea     rsi, [rdi+48h]
0x1800075ec  cmp     [rdi+40h], r13
0x1800075f0  jz      short loc_1800075F7
0x1800075f2  cmp     [rsi], r14
0x1800075f5  jnb     short loc_18000762B
0x1800075f7  mov     rdx, r14; dwBytes
0x1800075fa  mov     ecx, 8; dwFlags
0x1800075ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007604  mov     r15, rax
0x180007607  test    rax, rax
0x18000760a  jz      short loc_18000762B
0x18000760c  mov     rbx, [rdi+40h]
0x180007610  call    cs:__imp_GetProcessHeap
0x180007616  mov     r8, rbx; lpMem
0x180007619  xor     edx, edx; dwFlags
0x18000761b  mov     rcx, rax; hHeap
0x18000761e  call    cs:__imp_HeapFree
0x180007624  mov     [rdi+40h], r15
0x180007628  mov     [rsi], r14
0x18000762b  mov     rbx, [rdi+40h]
0x18000762f  test    rbx, rbx
0x180007632  jz      loc_180007730
0x180007638  mov     rdx, [rsi]; DestinationSize
0x18000763b  lea     rsi, [rdx+rbx]
0x18000763f  cmp     rbx, rsi
0x180007642  jz      short loc_180007682
0x180007644  mov     r8, [r12+38h]; Source
0x180007649  test    r8, r8
0x18000764c  jz      short loc_180007682
0x18000764e  cmp     [r8], r13b
0x180007651  jz      short loc_180007682
0x180007653  mov     rax, rbp
0x180007656  inc     rax
0x180007659  cmp     [r8+rax], r13b
0x18000765d  jnz     short loc_180007656
0x18000765f  lea     r14, [rax+1]
0x180007663  cmp     rdx, r14
0x180007666  jnb     short loc_18000766E
0x180007668  mov     [rdi+10h], r13
0x18000766c  jmp     short loc_18000768B
0x18000766e  mov     r9, r14; SourceSize
0x180007671  mov     rcx, rbx; Destination
0x180007674  call    memcpy_s
0x180007679  mov     [rdi+10h], rbx
0x18000767d  add     rbx, r14
0x180007680  jmp     short loc_180007686
0x180007682  mov     [rdi+10h], r13
0x180007686  cmp     rbx, rsi
0x180007689  jz      short loc_1800076D2
0x18000768b  mov     r8, [r12+80h]; Source
0x180007693  test    r8, r8
0x180007696  jz      short loc_1800076D2
0x180007698  cmp     [r8], r13b
0x18000769b  jz      short loc_1800076D2
0x18000769d  mov     rax, rbp
0x1800076a0  inc     rax
0x1800076a3  cmp     [r8+rax], r13b
0x1800076a7  jnz     short loc_1800076A0
0x1800076a9  mov     rdx, rsi
0x1800076ac  lea     r14, [rax+1]
0x1800076b0  sub     rdx, rbx; DestinationSize
0x1800076b3  cmp     rdx, r14
0x1800076b6  jnb     short loc_1800076BE
0x1800076b8  mov     [rdi+20h], r13
0x1800076bc  jmp     short loc_1800076DB
0x1800076be  mov     r9, r14; SourceSize
0x1800076c1  mov     rcx, rbx; Destination
0x1800076c4  call    memcpy_s
0x1800076c9  mov     [rdi+20h], rbx
0x1800076cd  add     rbx, r14
0x1800076d0  jmp     short loc_1800076D6
0x1800076d2  mov     [rdi+20h], r13
0x1800076d6  cmp     rbx, rsi
0x1800076d9  jz      short loc_18000771C
0x1800076db  mov     r8, [r12+18h]; Source
0x1800076e0  test    r8, r8
0x1800076e3  jz      short loc_18000771C
0x1800076e5  cmp     [r8], r13w
0x1800076e9  jz      short loc_18000771C
0x1800076eb  inc     rbp
0x1800076ee  cmp     [r8+rbp*2], r13w
0x1800076f3  jnz     short loc_1800076EB
0x1800076f5  mov     rdx, rsi
0x1800076f8  lea     r14, ds:2[rbp*2]
0x180007700  sub     rdx, rbx; DestinationSize
0x180007703  cmp     rdx, r14
0x180007706  jb      short loc_18000771C
0x180007708  mov     r9, r14; SourceSize
0x18000770b  mov     rcx, rbx; Destination
0x18000770e  call    memcpy_s
0x180007713  mov     [rdi+38h], rbx
0x180007717  add     rbx, r14
0x18000771a  jmp     short loc_180007720
0x18000771c  mov     [rdi+38h], r13
0x180007720  sub     rsi, rbx
0x180007723  xor     edx, edx; Val
0x180007725  mov     r8, rsi; Size
0x180007728  mov     rcx, rbx; void *
0x18000772b  call    memset_0
0x180007730  add     rsp, 28h
0x180007734  pop     r15
0x180007736  pop     r14
0x180007738  pop     r13
0x18000773a  pop     r12
0x18000773c  pop     rdi
0x18000773d  pop     rsi
0x18000773e  pop     rbp
0x18000773f  pop     rbx
0x180007740  retn
```
