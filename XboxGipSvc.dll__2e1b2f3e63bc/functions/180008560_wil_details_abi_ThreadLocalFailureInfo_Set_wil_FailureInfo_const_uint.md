# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008560`
- end: `0x180008779`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007a90`

## callees

- `0x180002158`
- `0x180008288`
- `0x180008560`
- `0x180009478`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008648`

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
0x180008560  push    rbx
0x180008562  push    rbp
0x180008563  push    rsi
0x180008564  push    rdi
0x180008565  push    r12
0x180008567  push    r13
0x180008569  push    r14
0x18000856b  push    r15
0x18000856d  sub     rsp, 28h
0x180008571  mov     [rcx+4], r8d
0x180008575  xor     r13d, r13d
0x180008578  mov     eax, [rdx+8]
0x18000857b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000857f  mov     [rcx+8], eax
0x180008582  mov     rdi, rcx
0x180008585  mov     [rcx+10h], r13
0x180008589  mov     r12, rdx
0x18000858c  movzx   eax, word ptr [rdx+40h]
0x180008590  mov     [rcx+18h], ax
0x180008594  mov     al, [rdx]
0x180008596  mov     [rcx+1Ah], al
0x180008599  mov     [rcx+20h], r13
0x18000859d  mov     rax, [rdx+88h]
0x1800085a4  mov     [rcx+28h], rax
0x1800085a8  mov     rax, [rdx+90h]
0x1800085af  mov     [rcx+30h], rax
0x1800085b3  mov     [rcx+38h], r13
0x1800085b7  mov     rcx, [rdx+38h]
0x1800085bb  lea     edx, [rbp+2]
0x1800085be  test    rcx, rcx
0x1800085c1  jnz     short loc_1800085C8
0x1800085c3  mov     r8d, edx
0x1800085c6  jmp     short loc_1800085D8
0x1800085c8  mov     rax, rbp
0x1800085cb  inc     rax
0x1800085ce  cmp     [rcx+rax], r13b
0x1800085d2  jnz     short loc_1800085CB
0x1800085d4  lea     r8, [rax+1]; unsigned __int64
0x1800085d8  mov     rcx, [r12+80h]
0x1800085e0  test    rcx, rcx
0x1800085e3  jz      short loc_1800085F5
0x1800085e5  mov     rax, rbp
0x1800085e8  inc     rax
0x1800085eb  cmp     [rcx+rax], r13b
0x1800085ef  jnz     short loc_1800085E8
0x1800085f1  lea     rdx, [rax+1]
0x1800085f5  mov     rcx, [r12+18h]
0x1800085fa  test    rcx, rcx
0x1800085fd  jnz     short loc_180008604
0x1800085ff  lea     eax, [rcx+2]
0x180008602  jmp     short loc_180008619
0x180008604  mov     rax, rbp
0x180008607  inc     rax
0x18000860a  cmp     [rcx+rax*2], r13w
0x18000860f  jnz     short loc_180008607
0x180008611  lea     rax, ds:2[rax*2]
0x180008619  lea     r14, [rdx+rax]
0x18000861d  add     r14, r8
0x180008620  lea     rsi, [rdi+48h]
0x180008624  cmp     [rdi+40h], r13
0x180008628  jz      short loc_18000862F
0x18000862a  cmp     [rsi], r14
0x18000862d  jnb     short loc_180008663
0x18000862f  mov     rdx, r14; dwBytes
0x180008632  mov     ecx, 8; dwFlags
0x180008637  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000863c  mov     r15, rax
0x18000863f  test    rax, rax
0x180008642  jz      short loc_180008663
0x180008644  mov     rbx, [rdi+40h]
0x180008648  call    cs:__imp_GetProcessHeap
0x18000864e  mov     r8, rbx; lpMem
0x180008651  xor     edx, edx; dwFlags
0x180008653  mov     rcx, rax; hHeap
0x180008656  call    cs:__imp_HeapFree
0x18000865c  mov     [rdi+40h], r15
0x180008660  mov     [rsi], r14
0x180008663  mov     rbx, [rdi+40h]
0x180008667  test    rbx, rbx
0x18000866a  jz      loc_180008768
0x180008670  mov     rdx, [rsi]; DestinationSize
0x180008673  lea     rsi, [rdx+rbx]
0x180008677  cmp     rbx, rsi
0x18000867a  jz      short loc_1800086BA
0x18000867c  mov     r8, [r12+38h]; Source
0x180008681  test    r8, r8
0x180008684  jz      short loc_1800086BA
0x180008686  cmp     [r8], r13b
0x180008689  jz      short loc_1800086BA
0x18000868b  mov     rax, rbp
0x18000868e  inc     rax
0x180008691  cmp     [r8+rax], r13b
0x180008695  jnz     short loc_18000868E
0x180008697  lea     r14, [rax+1]
0x18000869b  cmp     rdx, r14
0x18000869e  jnb     short loc_1800086A6
0x1800086a0  mov     [rdi+10h], r13
0x1800086a4  jmp     short loc_1800086C3
0x1800086a6  mov     r9, r14; SourceSize
0x1800086a9  mov     rcx, rbx; Destination
0x1800086ac  call    memcpy_s
0x1800086b1  mov     [rdi+10h], rbx
0x1800086b5  add     rbx, r14
0x1800086b8  jmp     short loc_1800086BE
0x1800086ba  mov     [rdi+10h], r13
0x1800086be  cmp     rbx, rsi
0x1800086c1  jz      short loc_18000870A
0x1800086c3  mov     r8, [r12+80h]; Source
0x1800086cb  test    r8, r8
0x1800086ce  jz      short loc_18000870A
0x1800086d0  cmp     [r8], r13b
0x1800086d3  jz      short loc_18000870A
0x1800086d5  mov     rax, rbp
0x1800086d8  inc     rax
0x1800086db  cmp     [r8+rax], r13b
0x1800086df  jnz     short loc_1800086D8
0x1800086e1  mov     rdx, rsi
0x1800086e4  lea     r14, [rax+1]
0x1800086e8  sub     rdx, rbx; DestinationSize
0x1800086eb  cmp     rdx, r14
0x1800086ee  jnb     short loc_1800086F6
0x1800086f0  mov     [rdi+20h], r13
0x1800086f4  jmp     short loc_180008713
0x1800086f6  mov     r9, r14; SourceSize
0x1800086f9  mov     rcx, rbx; Destination
0x1800086fc  call    memcpy_s
0x180008701  mov     [rdi+20h], rbx
0x180008705  add     rbx, r14
0x180008708  jmp     short loc_18000870E
0x18000870a  mov     [rdi+20h], r13
0x18000870e  cmp     rbx, rsi
0x180008711  jz      short loc_180008754
0x180008713  mov     r8, [r12+18h]; Source
0x180008718  test    r8, r8
0x18000871b  jz      short loc_180008754
0x18000871d  cmp     [r8], r13w
0x180008721  jz      short loc_180008754
0x180008723  inc     rbp
0x180008726  cmp     [r8+rbp*2], r13w
0x18000872b  jnz     short loc_180008723
0x18000872d  mov     rdx, rsi
0x180008730  lea     r14, ds:2[rbp*2]
0x180008738  sub     rdx, rbx; DestinationSize
0x18000873b  cmp     rdx, r14
0x18000873e  jb      short loc_180008754
0x180008740  mov     r9, r14; SourceSize
0x180008743  mov     rcx, rbx; Destination
0x180008746  call    memcpy_s
0x18000874b  mov     [rdi+38h], rbx
0x18000874f  add     rbx, r14
0x180008752  jmp     short loc_180008758
0x180008754  mov     [rdi+38h], r13
0x180008758  sub     rsi, rbx
0x18000875b  xor     edx, edx; Val
0x18000875d  mov     r8, rsi; Size
0x180008760  mov     rcx, rbx; void *
0x180008763  call    memset_0
0x180008768  add     rsp, 28h
0x18000876c  pop     r15
0x18000876e  pop     r14
0x180008770  pop     r13
0x180008772  pop     r12
0x180008774  pop     rdi
0x180008775  pop     rsi
0x180008776  pop     rbp
0x180008777  pop     rbx
0x180008778  retn
```
