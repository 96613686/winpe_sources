# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800063a8`
- end: `0x18000662d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800041a0`

## callees

- `0x180002ee0`
- `0x1800056bc`
- `0x1800063a8`
- `0x180007c62`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800065f7`
- `msvcrt!memcpy_s` at `0x1800065f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000655a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000655a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006568`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006568`

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
  char *v27; // rcx
  char *v28; // rbp
  char *v29; // rax
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
      v27 = *(char **)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = &v27[*(_QWORD *)(v12 + v7 + 72)];
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_BYTE **)a2 + 7), (_QWORD *)(v12 + v7 + 16));
        v30 = wil::details::WriteResultString<char const *>(v29, v28, *((_BYTE **)a2 + 16), v13);
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
0x1800063a8  push    rbx
0x1800063aa  push    rbp
0x1800063ab  push    rsi
0x1800063ac  push    rdi
0x1800063ad  push    r12
0x1800063af  push    r13
0x1800063b1  push    r14
0x1800063b3  push    r15
0x1800063b5  sub     rsp, 28h
0x1800063b9  mov     esi, [rcx+10h]
0x1800063bc  xor     r12d, r12d
0x1800063bf  mov     r15, rdx
0x1800063c2  mov     rbx, rcx
0x1800063c5  mov     ebp, 50h ; 'P'
0x1800063ca  cmp     [rcx+18h], r12
0x1800063ce  jnz     short loc_180006405
0x1800063d0  test    esi, esi
0x1800063d2  jz      short loc_180006405
0x1800063d4  mov     edx, 190h; dwBytes
0x1800063d9  lea     ecx, [rbp-48h]; dwFlags
0x1800063dc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800063e1  mov     [rbx+18h], rax
0x1800063e5  test    rax, rax
0x1800063e8  jz      short loc_180006405
0x1800063ea  mov     dword ptr [rbx+20h], 5
0x1800063f1  lea     rcx, [rax+190h]
0x1800063f8  jmp     short loc_180006400
0x1800063fa  mov     [rax], bp
0x1800063fd  add     rax, rbp
0x180006400  cmp     rax, rcx
0x180006403  jnz     short loc_1800063FA
0x180006405  mov     rdi, [rbx+18h]
0x180006409  test    rdi, rdi
0x18000640c  jz      loc_18000661C
0x180006412  test    esi, esi
0x180006414  jz      short loc_18000644C
0x180006416  movzx   eax, word ptr [rbx+20h]
0x18000641a  mov     rcx, rdi
0x18000641d  lea     rdx, [rax+rax*4]
0x180006421  shl     rdx, 4
0x180006425  add     rdx, rdi
0x180006428  cmp     rdi, rdx
0x18000642b  jz      short loc_18000644C
0x18000642d  mov     r8d, [rbx+10h]
0x180006431  cmp     [rcx+4], r8d
0x180006435  jbe     short loc_180006444
0x180006437  mov     eax, [r15+8]
0x18000643b  cmp     [rcx+8], eax
0x18000643e  jz      loc_18000661C
0x180006444  add     rcx, rbp
0x180006447  cmp     rcx, rdx
0x18000644a  jnz     short loc_180006431
0x18000644c  movzx   eax, word ptr [rbx+22h]
0x180006450  mov     r8d, 1
0x180006456  movzx   ecx, word ptr [rbx+20h]
0x18000645a  add     eax, r8d
0x18000645d  xor     edx, edx
0x18000645f  div     ecx
0x180006461  mov     ecx, r8d
0x180006464  movzx   eax, dx
0x180006467  mov     [rbx+22h], dx
0x18000646b  lea     rsi, [rax+rax*4]
0x18000646f  mov     rax, [rbx+8]
0x180006473  shl     rsi, 4
0x180006477  lock xadd [rax], ecx
0x18000647b  add     ecx, r8d
0x18000647e  lea     r13, [rsi+rdi]
0x180006482  mov     [rsi+rdi+4], ecx
0x180006486  lea     rbx, [rdi+20h]
0x18000648a  mov     eax, [r15+8]
0x18000648e  add     rbx, rsi
0x180006491  mov     [rsi+rdi+8], eax
0x180006495  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006499  mov     [r13+10h], r12
0x18000649d  movzx   eax, word ptr [r15+40h]
0x1800064a2  mov     [rsi+rdi+18h], ax
0x1800064a7  mov     al, [r15]
0x1800064aa  mov     [rsi+rdi+1Ah], al
0x1800064ae  mov     [rbx], r12
0x1800064b1  mov     rax, [r15+88h]
0x1800064b8  mov     [rsi+rdi+28h], rax
0x1800064bd  mov     rax, [r15+90h]
0x1800064c4  mov     [rsi+rdi+30h], rax
0x1800064c9  mov     [rsi+rdi+38h], r12
0x1800064ce  mov     rcx, [r15+38h]
0x1800064d2  test    rcx, rcx
0x1800064d5  jnz     short loc_1800064DC
0x1800064d7  mov     edx, r8d
0x1800064da  jmp     short loc_1800064EC
0x1800064dc  mov     rax, r14
0x1800064df  inc     rax
0x1800064e2  cmp     [rcx+rax], r12b
0x1800064e6  jnz     short loc_1800064DF
0x1800064e8  lea     rdx, [rax+1]
0x1800064ec  mov     rcx, [r15+80h]
0x1800064f3  test    rcx, rcx
0x1800064f6  jz      short loc_180006508
0x1800064f8  mov     rax, r14
0x1800064fb  inc     rax
0x1800064fe  cmp     [rcx+rax], r12b
0x180006502  jnz     short loc_1800064FB
0x180006504  lea     r8, [rax+1]; unsigned __int64
0x180006508  mov     rcx, [r15+18h]
0x18000650c  test    rcx, rcx
0x18000650f  jnz     short loc_180006516
0x180006511  lea     eax, [rcx+2]
0x180006514  jmp     short loc_18000652B
0x180006516  mov     rax, r14
0x180006519  inc     rax
0x18000651c  cmp     [rcx+rax*2], r12w
0x180006521  jnz     short loc_180006519
0x180006523  lea     rax, ds:2[rax*2]
0x18000652b  lea     rbp, [r8+rax]
0x18000652f  add     rbp, rdx
0x180006532  cmp     [rsi+rdi+40h], r12
0x180006537  jz      short loc_180006540
0x180006539  cmp     [rsi+rdi+48h], rbp
0x18000653e  jnb     short loc_180006582
0x180006540  mov     rdx, rbp; dwBytes
0x180006543  mov     ecx, 8; dwFlags
0x180006548  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000654d  mov     r12, rax
0x180006550  test    rax, rax
0x180006553  jz      short loc_18000657F
0x180006555  mov     rbx, [rsi+rdi+40h]
0x18000655a  call    cs:__imp_GetProcessHeap
0x180006560  mov     r8, rbx; lpMem
0x180006563  xor     edx, edx; dwFlags
0x180006565  mov     rcx, rax; hHeap
0x180006568  call    cs:__imp_HeapFree
0x18000656e  lea     rbx, [rdi+20h]
0x180006572  mov     [rsi+rdi+40h], r12
0x180006577  add     rbx, rsi
0x18000657a  mov     [rsi+rdi+48h], rbp
0x18000657f  xor     r12d, r12d
0x180006582  mov     rcx, [rsi+rdi+40h]
0x180006587  test    rcx, rcx
0x18000658a  jz      loc_18000661C
0x180006590  mov     rbp, [rsi+rdi+48h]
0x180006595  lea     r9, [r13+10h]
0x180006599  mov     r8, [r15+38h]
0x18000659d  add     rbp, rcx
0x1800065a0  mov     rdx, rbp
0x1800065a3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800065a8  mov     r8, [r15+80h]
0x1800065af  mov     r9, rbx
0x1800065b2  mov     rdx, rbp
0x1800065b5  mov     rcx, rax
0x1800065b8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800065bd  mov     rbx, rax
0x1800065c0  cmp     rax, rbp
0x1800065c3  jz      short loc_180006607
0x1800065c5  mov     r8, [r15+18h]; Source
0x1800065c9  test    r8, r8
0x1800065cc  jz      short loc_180006607
0x1800065ce  cmp     [r8], r12w
0x1800065d2  jz      short loc_180006607
0x1800065d4  inc     r14
0x1800065d7  cmp     [r8+r14*2], r12w
0x1800065dc  jnz     short loc_1800065D4
0x1800065de  mov     rdx, rbp
0x1800065e1  lea     r14, ds:2[r14*2]
0x1800065e9  sub     rdx, rbx; DestinationSize
0x1800065ec  cmp     rdx, r14
0x1800065ef  jb      short loc_180006607
0x1800065f1  mov     r9, r14; SourceSize
0x1800065f4  mov     rcx, rbx; Destination
0x1800065f7  call    cs:__imp_memcpy_s
0x1800065fd  mov     [rsi+rdi+38h], rbx
0x180006602  add     rbx, r14
0x180006605  jmp     short loc_18000660C
0x180006607  mov     [rsi+rdi+38h], r12
0x18000660c  sub     rbp, rbx
0x18000660f  xor     edx, edx; Val
0x180006611  mov     r8, rbp; Size
0x180006614  mov     rcx, rbx; void *
0x180006617  call    memset_0
0x18000661c  add     rsp, 28h
0x180006620  pop     r15
0x180006622  pop     r14
0x180006624  pop     r13
0x180006626  pop     r12
0x180006628  pop     rdi
0x180006629  pop     rsi
0x18000662a  pop     rbp
0x18000662b  pop     rbx
0x18000662c  retn
```
