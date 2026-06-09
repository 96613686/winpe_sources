# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800080d4`
- end: `0x18000836c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050f0`

## callees

- `0x180002b10`
- `0x180006468`
- `0x1800080d4`
- `0x18003d4ca`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000832f`
- `msvcrt!memcpy_s` at `0x18000832f`
- `KERNEL32!GetProcessHeap` at `0x180008286`
- `KERNEL32!GetProcessHeap` at `0x180008286`
- `KERNEL32!HeapFree` at `0x18000829a`
- `KERNEL32!HeapFree` at `0x18000829a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x1800080d4  push    rbx
0x1800080d6  push    rbp
0x1800080d7  push    rsi
0x1800080d8  push    rdi
0x1800080d9  push    r12
0x1800080db  push    r13
0x1800080dd  push    r14
0x1800080df  push    r15
0x1800080e1  sub     rsp, 28h
0x1800080e5  mov     esi, [rcx+10h]
0x1800080e8  xor     r12d, r12d
0x1800080eb  mov     r15, rdx
0x1800080ee  mov     rbx, rcx
0x1800080f1  mov     ebp, 50h ; 'P'
0x1800080f6  cmp     [rcx+18h], r12
0x1800080fa  jnz     short loc_180008131
0x1800080fc  test    esi, esi
0x1800080fe  jz      short loc_180008131
0x180008100  mov     edx, 190h; dwBytes
0x180008105  lea     ecx, [rbp-48h]; dwFlags
0x180008108  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000810d  mov     [rbx+18h], rax
0x180008111  test    rax, rax
0x180008114  jz      short loc_180008131
0x180008116  mov     dword ptr [rbx+20h], 5
0x18000811d  lea     rcx, [rax+190h]
0x180008124  jmp     short loc_18000812C
0x180008126  mov     [rax], bp
0x180008129  add     rax, rbp
0x18000812c  cmp     rax, rcx
0x18000812f  jnz     short loc_180008126
0x180008131  mov     rdi, [rbx+18h]
0x180008135  test    rdi, rdi
0x180008138  jz      loc_18000835A
0x18000813e  test    esi, esi
0x180008140  jz      short loc_180008178
0x180008142  movzx   eax, word ptr [rbx+20h]
0x180008146  mov     rcx, rdi
0x180008149  lea     rdx, [rax+rax*4]
0x18000814d  shl     rdx, 4
0x180008151  add     rdx, rdi
0x180008154  cmp     rdi, rdx
0x180008157  jz      short loc_180008178
0x180008159  mov     r8d, [rbx+10h]
0x18000815d  cmp     [rcx+4], r8d
0x180008161  jbe     short loc_180008170
0x180008163  mov     eax, [r15+8]
0x180008167  cmp     [rcx+8], eax
0x18000816a  jz      loc_18000835A
0x180008170  add     rcx, rbp
0x180008173  cmp     rcx, rdx
0x180008176  jnz     short loc_18000815D
0x180008178  movzx   eax, word ptr [rbx+22h]
0x18000817c  mov     r8d, 1
0x180008182  movzx   ecx, word ptr [rbx+20h]
0x180008186  add     eax, r8d
0x180008189  xor     edx, edx
0x18000818b  div     ecx
0x18000818d  mov     ecx, r8d
0x180008190  movzx   eax, dx
0x180008193  mov     [rbx+22h], dx
0x180008197  lea     rsi, [rax+rax*4]
0x18000819b  mov     rax, [rbx+8]
0x18000819f  shl     rsi, 4
0x1800081a3  lock xadd [rax], ecx
0x1800081a7  add     ecx, r8d
0x1800081aa  lea     r13, [rsi+rdi]
0x1800081ae  mov     [rsi+rdi+4], ecx
0x1800081b2  lea     rbx, [rdi+20h]
0x1800081b6  mov     eax, [r15+8]
0x1800081ba  add     rbx, rsi
0x1800081bd  mov     [rsi+rdi+8], eax
0x1800081c1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800081c5  mov     [r13+10h], r12
0x1800081c9  movzx   eax, word ptr [r15+40h]
0x1800081ce  mov     [rsi+rdi+18h], ax
0x1800081d3  mov     al, [r15]
0x1800081d6  mov     [rsi+rdi+1Ah], al
0x1800081da  mov     [rbx], r12
0x1800081dd  mov     rax, [r15+88h]
0x1800081e4  mov     [rsi+rdi+28h], rax
0x1800081e9  mov     rax, [r15+90h]
0x1800081f0  mov     [rsi+rdi+30h], rax
0x1800081f5  mov     [rsi+rdi+38h], r12
0x1800081fa  mov     rcx, [r15+38h]
0x1800081fe  test    rcx, rcx
0x180008201  jnz     short loc_180008208
0x180008203  mov     edx, r8d
0x180008206  jmp     short loc_180008218
0x180008208  mov     rax, r14
0x18000820b  inc     rax
0x18000820e  cmp     [rcx+rax], r12b
0x180008212  jnz     short loc_18000820B
0x180008214  lea     rdx, [rax+1]
0x180008218  mov     rcx, [r15+80h]
0x18000821f  test    rcx, rcx
0x180008222  jz      short loc_180008234
0x180008224  mov     rax, r14
0x180008227  inc     rax
0x18000822a  cmp     [rcx+rax], r12b
0x18000822e  jnz     short loc_180008227
0x180008230  lea     r8, [rax+1]; unsigned __int64
0x180008234  mov     rcx, [r15+18h]
0x180008238  test    rcx, rcx
0x18000823b  jnz     short loc_180008242
0x18000823d  lea     eax, [rcx+2]
0x180008240  jmp     short loc_180008257
0x180008242  mov     rax, r14
0x180008245  inc     rax
0x180008248  cmp     [rcx+rax*2], r12w
0x18000824d  jnz     short loc_180008245
0x18000824f  lea     rax, ds:2[rax*2]
0x180008257  lea     rbp, [r8+rax]
0x18000825b  add     rbp, rdx
0x18000825e  cmp     [rsi+rdi+40h], r12
0x180008263  jz      short loc_18000826C
0x180008265  cmp     [rsi+rdi+48h], rbp
0x18000826a  jnb     short loc_1800082BA
0x18000826c  mov     rdx, rbp; dwBytes
0x18000826f  mov     ecx, 8; dwFlags
0x180008274  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008279  mov     r12, rax
0x18000827c  test    rax, rax
0x18000827f  jz      short loc_1800082B7
0x180008281  mov     rbx, [rsi+rdi+40h]
0x180008286  call    cs:__imp_GetProcessHeap
0x18000828d  nop     dword ptr [rax+rax+00h]
0x180008292  mov     r8, rbx; lpMem
0x180008295  xor     edx, edx; dwFlags
0x180008297  mov     rcx, rax; hHeap
0x18000829a  call    cs:__imp_HeapFree
0x1800082a1  nop     dword ptr [rax+rax+00h]
0x1800082a6  lea     rbx, [rdi+20h]
0x1800082aa  mov     [rsi+rdi+40h], r12
0x1800082af  add     rbx, rsi
0x1800082b2  mov     [rsi+rdi+48h], rbp
0x1800082b7  xor     r12d, r12d
0x1800082ba  mov     rcx, [rsi+rdi+40h]
0x1800082bf  test    rcx, rcx
0x1800082c2  jz      loc_18000835A
0x1800082c8  mov     rbp, [rsi+rdi+48h]
0x1800082cd  lea     r9, [r13+10h]
0x1800082d1  mov     r8, [r15+38h]
0x1800082d5  add     rbp, rcx
0x1800082d8  mov     rdx, rbp
0x1800082db  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800082e0  mov     r8, [r15+80h]
0x1800082e7  mov     r9, rbx
0x1800082ea  mov     rdx, rbp
0x1800082ed  mov     rcx, rax
0x1800082f0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800082f5  mov     rbx, rax
0x1800082f8  cmp     rax, rbp
0x1800082fb  jz      short loc_180008345
0x1800082fd  mov     r8, [r15+18h]; Source
0x180008301  test    r8, r8
0x180008304  jz      short loc_180008345
0x180008306  cmp     [r8], r12w
0x18000830a  jz      short loc_180008345
0x18000830c  inc     r14
0x18000830f  cmp     [r8+r14*2], r12w
0x180008314  jnz     short loc_18000830C
0x180008316  mov     rdx, rbp
0x180008319  lea     r14, ds:2[r14*2]
0x180008321  sub     rdx, rbx; DestinationSize
0x180008324  cmp     rdx, r14
0x180008327  jb      short loc_180008345
0x180008329  mov     r9, r14; SourceSize
0x18000832c  mov     rcx, rbx; Destination
0x18000832f  call    cs:__imp_memcpy_s
0x180008336  nop     dword ptr [rax+rax+00h]
0x18000833b  mov     [rsi+rdi+38h], rbx
0x180008340  add     rbx, r14
0x180008343  jmp     short loc_18000834A
0x180008345  mov     [rsi+rdi+38h], r12
0x18000834a  sub     rbp, rbx
0x18000834d  xor     edx, edx; Val
0x18000834f  mov     r8, rbp; Size
0x180008352  mov     rcx, rbx; void *
0x180008355  call    memset_0
0x18000835a  add     rsp, 28h
0x18000835e  pop     r15
0x180008360  pop     r14
0x180008362  pop     r13
0x180008364  pop     r12
0x180008366  pop     rdi
0x180008367  pop     rsi
0x180008368  pop     rbp
0x180008369  pop     rbx
0x18000836a  retn
```
