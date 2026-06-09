# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800084a4`
- end: `0x1800086bd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800059e0`

## callees

- `0x180002a28`
- `0x180006c38`
- `0x1800084a4`
- `0x18000a168`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000859a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000859a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000858c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000858c`

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
0x1800084a4  push    rbx
0x1800084a6  push    rbp
0x1800084a7  push    rsi
0x1800084a8  push    rdi
0x1800084a9  push    r12
0x1800084ab  push    r13
0x1800084ad  push    r14
0x1800084af  push    r15
0x1800084b1  sub     rsp, 28h
0x1800084b5  mov     [rcx+4], r8d
0x1800084b9  xor     r13d, r13d
0x1800084bc  mov     eax, [rdx+8]
0x1800084bf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800084c3  mov     [rcx+8], eax
0x1800084c6  mov     rdi, rcx
0x1800084c9  mov     [rcx+10h], r13
0x1800084cd  mov     r12, rdx
0x1800084d0  movzx   eax, word ptr [rdx+40h]
0x1800084d4  mov     [rcx+18h], ax
0x1800084d8  mov     al, [rdx]
0x1800084da  mov     [rcx+1Ah], al
0x1800084dd  mov     [rcx+20h], r13
0x1800084e1  mov     rax, [rdx+88h]
0x1800084e8  mov     [rcx+28h], rax
0x1800084ec  mov     rax, [rdx+90h]
0x1800084f3  mov     [rcx+30h], rax
0x1800084f7  mov     [rcx+38h], r13
0x1800084fb  mov     rcx, [rdx+38h]
0x1800084ff  lea     edx, [rbp+2]
0x180008502  test    rcx, rcx
0x180008505  jnz     short loc_18000850C
0x180008507  mov     r8d, edx
0x18000850a  jmp     short loc_18000851C
0x18000850c  mov     rax, rbp
0x18000850f  inc     rax
0x180008512  cmp     [rcx+rax], r13b
0x180008516  jnz     short loc_18000850F
0x180008518  lea     r8, [rax+1]; unsigned __int64
0x18000851c  mov     rcx, [r12+80h]
0x180008524  test    rcx, rcx
0x180008527  jz      short loc_180008539
0x180008529  mov     rax, rbp
0x18000852c  inc     rax
0x18000852f  cmp     [rcx+rax], r13b
0x180008533  jnz     short loc_18000852C
0x180008535  lea     rdx, [rax+1]
0x180008539  mov     rcx, [r12+18h]
0x18000853e  test    rcx, rcx
0x180008541  jnz     short loc_180008548
0x180008543  lea     eax, [rcx+2]
0x180008546  jmp     short loc_18000855D
0x180008548  mov     rax, rbp
0x18000854b  inc     rax
0x18000854e  cmp     [rcx+rax*2], r13w
0x180008553  jnz     short loc_18000854B
0x180008555  lea     rax, ds:2[rax*2]
0x18000855d  lea     r14, [rdx+rax]
0x180008561  add     r14, r8
0x180008564  lea     rsi, [rdi+48h]
0x180008568  cmp     [rdi+40h], r13
0x18000856c  jz      short loc_180008573
0x18000856e  cmp     [rsi], r14
0x180008571  jnb     short loc_1800085A7
0x180008573  mov     rdx, r14; dwBytes
0x180008576  mov     ecx, 8; dwFlags
0x18000857b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008580  mov     r15, rax
0x180008583  test    rax, rax
0x180008586  jz      short loc_1800085A7
0x180008588  mov     rbx, [rdi+40h]
0x18000858c  call    cs:__imp_GetProcessHeap
0x180008592  mov     r8, rbx; lpMem
0x180008595  xor     edx, edx; dwFlags
0x180008597  mov     rcx, rax; hHeap
0x18000859a  call    cs:__imp_HeapFree
0x1800085a0  mov     [rdi+40h], r15
0x1800085a4  mov     [rsi], r14
0x1800085a7  mov     rbx, [rdi+40h]
0x1800085ab  test    rbx, rbx
0x1800085ae  jz      loc_1800086AC
0x1800085b4  mov     rdx, [rsi]; DestinationSize
0x1800085b7  lea     rsi, [rdx+rbx]
0x1800085bb  cmp     rbx, rsi
0x1800085be  jz      short loc_1800085FE
0x1800085c0  mov     r8, [r12+38h]; Source
0x1800085c5  test    r8, r8
0x1800085c8  jz      short loc_1800085FE
0x1800085ca  cmp     [r8], r13b
0x1800085cd  jz      short loc_1800085FE
0x1800085cf  mov     rax, rbp
0x1800085d2  inc     rax
0x1800085d5  cmp     [r8+rax], r13b
0x1800085d9  jnz     short loc_1800085D2
0x1800085db  lea     r14, [rax+1]
0x1800085df  cmp     rdx, r14
0x1800085e2  jnb     short loc_1800085EA
0x1800085e4  mov     [rdi+10h], r13
0x1800085e8  jmp     short loc_180008607
0x1800085ea  mov     r9, r14; SourceSize
0x1800085ed  mov     rcx, rbx; Destination
0x1800085f0  call    memcpy_s
0x1800085f5  mov     [rdi+10h], rbx
0x1800085f9  add     rbx, r14
0x1800085fc  jmp     short loc_180008602
0x1800085fe  mov     [rdi+10h], r13
0x180008602  cmp     rbx, rsi
0x180008605  jz      short loc_18000864E
0x180008607  mov     r8, [r12+80h]; Source
0x18000860f  test    r8, r8
0x180008612  jz      short loc_18000864E
0x180008614  cmp     [r8], r13b
0x180008617  jz      short loc_18000864E
0x180008619  mov     rax, rbp
0x18000861c  inc     rax
0x18000861f  cmp     [r8+rax], r13b
0x180008623  jnz     short loc_18000861C
0x180008625  mov     rdx, rsi
0x180008628  lea     r14, [rax+1]
0x18000862c  sub     rdx, rbx; DestinationSize
0x18000862f  cmp     rdx, r14
0x180008632  jnb     short loc_18000863A
0x180008634  mov     [rdi+20h], r13
0x180008638  jmp     short loc_180008657
0x18000863a  mov     r9, r14; SourceSize
0x18000863d  mov     rcx, rbx; Destination
0x180008640  call    memcpy_s
0x180008645  mov     [rdi+20h], rbx
0x180008649  add     rbx, r14
0x18000864c  jmp     short loc_180008652
0x18000864e  mov     [rdi+20h], r13
0x180008652  cmp     rbx, rsi
0x180008655  jz      short loc_180008698
0x180008657  mov     r8, [r12+18h]; Source
0x18000865c  test    r8, r8
0x18000865f  jz      short loc_180008698
0x180008661  cmp     [r8], r13w
0x180008665  jz      short loc_180008698
0x180008667  inc     rbp
0x18000866a  cmp     [r8+rbp*2], r13w
0x18000866f  jnz     short loc_180008667
0x180008671  mov     rdx, rsi
0x180008674  lea     r14, ds:2[rbp*2]
0x18000867c  sub     rdx, rbx; DestinationSize
0x18000867f  cmp     rdx, r14
0x180008682  jb      short loc_180008698
0x180008684  mov     r9, r14; SourceSize
0x180008687  mov     rcx, rbx; Destination
0x18000868a  call    memcpy_s
0x18000868f  mov     [rdi+38h], rbx
0x180008693  add     rbx, r14
0x180008696  jmp     short loc_18000869C
0x180008698  mov     [rdi+38h], r13
0x18000869c  sub     rsi, rbx
0x18000869f  xor     edx, edx; Val
0x1800086a1  mov     r8, rsi; Size
0x1800086a4  mov     rcx, rbx; void *
0x1800086a7  call    memset_0
0x1800086ac  add     rsp, 28h
0x1800086b0  pop     r15
0x1800086b2  pop     r14
0x1800086b4  pop     r13
0x1800086b6  pop     r12
0x1800086b8  pop     rdi
0x1800086b9  pop     rsi
0x1800086ba  pop     rbp
0x1800086bb  pop     rbx
0x1800086bc  retn
```
