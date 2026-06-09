# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400063a0`
- end: `0x1400065bc`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005120`

## callees

- `0x14000195f`
- `0x140006054`
- `0x1400063a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400064ec`
- `msvcrt!memcpy_s` at `0x14000653d`
- `msvcrt!memcpy_s` at `0x140006588`
- `msvcrt!memcpy_s` at `0x1400064ec`
- `msvcrt!memcpy_s` at `0x14000653d`
- `msvcrt!memcpy_s` at `0x140006588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006488`

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
0x1400063a0  push    rbx
0x1400063a2  push    rbp
0x1400063a3  push    rsi
0x1400063a4  push    rdi
0x1400063a5  push    r12
0x1400063a7  push    r13
0x1400063a9  push    r14
0x1400063ab  push    r15
0x1400063ad  sub     rsp, 28h
0x1400063b1  mov     [rcx+4], r8d
0x1400063b5  xor     r13d, r13d
0x1400063b8  mov     eax, [rdx+8]
0x1400063bb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400063bf  mov     [rcx+8], eax
0x1400063c2  mov     rdi, rcx
0x1400063c5  mov     [rcx+10h], r13
0x1400063c9  mov     r12, rdx
0x1400063cc  movzx   eax, word ptr [rdx+40h]
0x1400063d0  mov     [rcx+18h], ax
0x1400063d4  mov     al, [rdx]
0x1400063d6  mov     [rcx+1Ah], al
0x1400063d9  mov     [rcx+20h], r13
0x1400063dd  mov     rax, [rdx+88h]
0x1400063e4  mov     [rcx+28h], rax
0x1400063e8  mov     rax, [rdx+90h]
0x1400063ef  mov     [rcx+30h], rax
0x1400063f3  mov     [rcx+38h], r13
0x1400063f7  mov     rcx, [rdx+38h]
0x1400063fb  lea     edx, [rbp+2]
0x1400063fe  test    rcx, rcx
0x140006401  jnz     short loc_140006408
0x140006403  mov     r8d, edx
0x140006406  jmp     short loc_140006418
0x140006408  mov     rax, rbp
0x14000640b  inc     rax
0x14000640e  cmp     [rcx+rax], r13b
0x140006412  jnz     short loc_14000640B
0x140006414  lea     r8, [rax+1]; unsigned __int64
0x140006418  mov     rcx, [r12+80h]
0x140006420  test    rcx, rcx
0x140006423  jz      short loc_140006435
0x140006425  mov     rax, rbp
0x140006428  inc     rax
0x14000642b  cmp     [rcx+rax], r13b
0x14000642f  jnz     short loc_140006428
0x140006431  lea     rdx, [rax+1]
0x140006435  mov     rcx, [r12+18h]
0x14000643a  test    rcx, rcx
0x14000643d  jnz     short loc_140006444
0x14000643f  lea     eax, [rcx+2]
0x140006442  jmp     short loc_140006459
0x140006444  mov     rax, rbp
0x140006447  inc     rax
0x14000644a  cmp     [rcx+rax*2], r13w
0x14000644f  jnz     short loc_140006447
0x140006451  lea     rax, ds:2[rax*2]
0x140006459  lea     r14, [rdx+rax]
0x14000645d  add     r14, r8
0x140006460  lea     rsi, [rdi+48h]
0x140006464  cmp     [rdi+40h], r13
0x140006468  jz      short loc_14000646F
0x14000646a  cmp     [rsi], r14
0x14000646d  jnb     short loc_1400064A3
0x14000646f  mov     rdx, r14; dwBytes
0x140006472  mov     ecx, 8; dwFlags
0x140006477  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000647c  mov     r15, rax
0x14000647f  test    rax, rax
0x140006482  jz      short loc_1400064A3
0x140006484  mov     rbx, [rdi+40h]
0x140006488  call    cs:__imp_GetProcessHeap
0x14000648e  mov     r8, rbx; lpMem
0x140006491  xor     edx, edx; dwFlags
0x140006493  mov     rcx, rax; hHeap
0x140006496  call    cs:__imp_HeapFree
0x14000649c  mov     [rdi+40h], r15
0x1400064a0  mov     [rsi], r14
0x1400064a3  mov     rbx, [rdi+40h]
0x1400064a7  test    rbx, rbx
0x1400064aa  jz      loc_1400065AB
0x1400064b0  mov     rdx, [rsi]; DestinationSize
0x1400064b3  lea     rsi, [rdx+rbx]
0x1400064b7  cmp     rbx, rsi
0x1400064ba  jz      short loc_1400064FB
0x1400064bc  mov     r8, [r12+38h]; Source
0x1400064c1  test    r8, r8
0x1400064c4  jz      short loc_1400064FB
0x1400064c6  cmp     [r8], r13b
0x1400064c9  jz      short loc_1400064FB
0x1400064cb  mov     rax, rbp
0x1400064ce  inc     rax
0x1400064d1  cmp     [r8+rax], r13b
0x1400064d5  jnz     short loc_1400064CE
0x1400064d7  lea     r14, [rax+1]
0x1400064db  cmp     rdx, r14
0x1400064de  jnb     short loc_1400064E6
0x1400064e0  mov     [rdi+10h], r13
0x1400064e4  jmp     short loc_140006504
0x1400064e6  mov     r9, r14; SourceSize
0x1400064e9  mov     rcx, rbx; Destination
0x1400064ec  call    cs:__imp_memcpy_s
0x1400064f2  mov     [rdi+10h], rbx
0x1400064f6  add     rbx, r14
0x1400064f9  jmp     short loc_1400064FF
0x1400064fb  mov     [rdi+10h], r13
0x1400064ff  cmp     rbx, rsi
0x140006502  jz      short loc_14000654C
0x140006504  mov     r8, [r12+80h]; Source
0x14000650c  test    r8, r8
0x14000650f  jz      short loc_14000654C
0x140006511  cmp     [r8], r13b
0x140006514  jz      short loc_14000654C
0x140006516  mov     rax, rbp
0x140006519  inc     rax
0x14000651c  cmp     [r8+rax], r13b
0x140006520  jnz     short loc_140006519
0x140006522  mov     rdx, rsi
0x140006525  lea     r14, [rax+1]
0x140006529  sub     rdx, rbx; DestinationSize
0x14000652c  cmp     rdx, r14
0x14000652f  jnb     short loc_140006537
0x140006531  mov     [rdi+20h], r13
0x140006535  jmp     short loc_140006555
0x140006537  mov     r9, r14; SourceSize
0x14000653a  mov     rcx, rbx; Destination
0x14000653d  call    cs:__imp_memcpy_s
0x140006543  mov     [rdi+20h], rbx
0x140006547  add     rbx, r14
0x14000654a  jmp     short loc_140006550
0x14000654c  mov     [rdi+20h], r13
0x140006550  cmp     rbx, rsi
0x140006553  jz      short loc_140006597
0x140006555  mov     r8, [r12+18h]; Source
0x14000655a  test    r8, r8
0x14000655d  jz      short loc_140006597
0x14000655f  cmp     [r8], r13w
0x140006563  jz      short loc_140006597
0x140006565  inc     rbp
0x140006568  cmp     [r8+rbp*2], r13w
0x14000656d  jnz     short loc_140006565
0x14000656f  mov     rdx, rsi
0x140006572  lea     r14, ds:2[rbp*2]
0x14000657a  sub     rdx, rbx; DestinationSize
0x14000657d  cmp     rdx, r14
0x140006580  jb      short loc_140006597
0x140006582  mov     r9, r14; SourceSize
0x140006585  mov     rcx, rbx; Destination
0x140006588  call    cs:__imp_memcpy_s
0x14000658e  mov     [rdi+38h], rbx
0x140006592  add     rbx, r14
0x140006595  jmp     short loc_14000659B
0x140006597  mov     [rdi+38h], r13
0x14000659b  sub     rsi, rbx
0x14000659e  xor     edx, edx; Val
0x1400065a0  mov     r8, rsi; Size
0x1400065a3  mov     rcx, rbx; void *
0x1400065a6  call    memset_0
0x1400065ab  add     rsp, 28h
0x1400065af  pop     r15
0x1400065b1  pop     r14
0x1400065b3  pop     r13
0x1400065b5  pop     r12
0x1400065b7  pop     rdi
0x1400065b8  pop     rsi
0x1400065b9  pop     rbp
0x1400065ba  pop     rbx
0x1400065bb  retn
```
