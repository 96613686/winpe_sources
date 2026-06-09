# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000927c`
- end: `0x180009508`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `652`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005a50`

## callees

- `0x180002f40`
- `0x1800070ec`
- `0x18000927c`
- `0x180010792`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800094ce`
- `msvcrt!memcpy_s` at `0x1800094ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009431`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000943f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000943f`

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
0x18000927c  mov     [rsp+arg_10], rbx
0x180009281  push    rbp
0x180009282  push    rsi
0x180009283  push    rdi
0x180009284  push    r12
0x180009286  push    r13
0x180009288  push    r14
0x18000928a  push    r15
0x18000928c  sub     rsp, 20h
0x180009290  mov     esi, [rcx+10h]
0x180009293  xor     r12d, r12d
0x180009296  mov     r15, rdx
0x180009299  mov     rbx, rcx
0x18000929c  mov     ebp, 50h ; 'P'
0x1800092a1  cmp     [rcx+18h], r12
0x1800092a5  jnz     short loc_1800092DC
0x1800092a7  test    esi, esi
0x1800092a9  jz      short loc_1800092DC
0x1800092ab  mov     edx, 190h; dwBytes
0x1800092b0  lea     ecx, [rbp-48h]; dwFlags
0x1800092b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800092b8  mov     [rbx+18h], rax
0x1800092bc  test    rax, rax
0x1800092bf  jz      short loc_1800092DC
0x1800092c1  mov     dword ptr [rbx+20h], 5
0x1800092c8  lea     rcx, [rax+190h]
0x1800092cf  jmp     short loc_1800092D7
0x1800092d1  mov     [rax], bp
0x1800092d4  add     rax, rbp
0x1800092d7  cmp     rax, rcx
0x1800092da  jnz     short loc_1800092D1
0x1800092dc  mov     rdi, [rbx+18h]
0x1800092e0  test    rdi, rdi
0x1800092e3  jz      loc_1800094F3
0x1800092e9  test    esi, esi
0x1800092eb  jz      short loc_180009323
0x1800092ed  movzx   eax, word ptr [rbx+20h]
0x1800092f1  mov     rcx, rdi
0x1800092f4  lea     rdx, [rax+rax*4]
0x1800092f8  shl     rdx, 4
0x1800092fc  add     rdx, rdi
0x1800092ff  cmp     rdi, rdx
0x180009302  jz      short loc_180009323
0x180009304  mov     r8d, [rbx+10h]
0x180009308  cmp     [rcx+4], r8d
0x18000930c  jbe     short loc_18000931B
0x18000930e  mov     eax, [r15+8]
0x180009312  cmp     [rcx+8], eax
0x180009315  jz      loc_1800094F3
0x18000931b  add     rcx, rbp
0x18000931e  cmp     rcx, rdx
0x180009321  jnz     short loc_180009308
0x180009323  movzx   eax, word ptr [rbx+22h]
0x180009327  mov     r8d, 1
0x18000932d  movzx   ecx, word ptr [rbx+20h]
0x180009331  add     eax, r8d
0x180009334  xor     edx, edx
0x180009336  div     ecx
0x180009338  mov     ecx, r8d
0x18000933b  movzx   eax, dx
0x18000933e  mov     [rbx+22h], dx
0x180009342  lea     rsi, [rax+rax*4]
0x180009346  mov     rax, [rbx+8]
0x18000934a  shl     rsi, 4
0x18000934e  lock xadd [rax], ecx
0x180009352  add     ecx, r8d
0x180009355  lea     r13, [rsi+rdi]
0x180009359  mov     [rsi+rdi+4], ecx
0x18000935d  lea     rbx, [rdi+20h]
0x180009361  mov     eax, [r15+8]
0x180009365  add     rbx, rsi
0x180009368  mov     [rsi+rdi+8], eax
0x18000936c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009370  mov     [r13+10h], r12
0x180009374  movzx   eax, word ptr [r15+40h]
0x180009379  mov     [rsi+rdi+18h], ax
0x18000937e  mov     al, [r15]
0x180009381  mov     [rsi+rdi+1Ah], al
0x180009385  mov     [rbx], r12
0x180009388  mov     rax, [r15+88h]
0x18000938f  mov     [rsi+rdi+28h], rax
0x180009394  mov     rax, [r15+90h]
0x18000939b  mov     [rsi+rdi+30h], rax
0x1800093a0  mov     [rsi+rdi+38h], r12
0x1800093a5  mov     rcx, [r15+38h]
0x1800093a9  test    rcx, rcx
0x1800093ac  jnz     short loc_1800093B3
0x1800093ae  mov     edx, r8d
0x1800093b1  jmp     short loc_1800093C3
0x1800093b3  mov     rax, r14
0x1800093b6  inc     rax
0x1800093b9  cmp     [rcx+rax], r12b
0x1800093bd  jnz     short loc_1800093B6
0x1800093bf  lea     rdx, [rax+1]
0x1800093c3  mov     rcx, [r15+80h]
0x1800093ca  test    rcx, rcx
0x1800093cd  jz      short loc_1800093DF
0x1800093cf  mov     rax, r14
0x1800093d2  inc     rax
0x1800093d5  cmp     [rcx+rax], r12b
0x1800093d9  jnz     short loc_1800093D2
0x1800093db  lea     r8, [rax+1]; unsigned __int64
0x1800093df  mov     rcx, [r15+18h]
0x1800093e3  test    rcx, rcx
0x1800093e6  jnz     short loc_1800093ED
0x1800093e8  lea     eax, [rcx+2]
0x1800093eb  jmp     short loc_180009402
0x1800093ed  mov     rax, r14
0x1800093f0  inc     rax
0x1800093f3  cmp     [rcx+rax*2], r12w
0x1800093f8  jnz     short loc_1800093F0
0x1800093fa  lea     rax, ds:2[rax*2]
0x180009402  lea     rbp, [r8+rax]
0x180009406  add     rbp, rdx
0x180009409  cmp     [rsi+rdi+40h], r12
0x18000940e  jz      short loc_180009417
0x180009410  cmp     [rsi+rdi+48h], rbp
0x180009415  jnb     short loc_180009459
0x180009417  mov     rdx, rbp; dwBytes
0x18000941a  mov     ecx, 8; dwFlags
0x18000941f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009424  mov     r12, rax
0x180009427  test    rax, rax
0x18000942a  jz      short loc_180009456
0x18000942c  mov     rbx, [rsi+rdi+40h]
0x180009431  call    cs:__imp_GetProcessHeap
0x180009437  mov     r8, rbx; lpMem
0x18000943a  xor     edx, edx; dwFlags
0x18000943c  mov     rcx, rax; hHeap
0x18000943f  call    cs:__imp_HeapFree
0x180009445  lea     rbx, [rdi+20h]
0x180009449  mov     [rsi+rdi+40h], r12
0x18000944e  add     rbx, rsi
0x180009451  mov     [rsi+rdi+48h], rbp
0x180009456  xor     r12d, r12d
0x180009459  mov     rcx, [rsi+rdi+40h]
0x18000945e  test    rcx, rcx
0x180009461  jz      loc_1800094F3
0x180009467  mov     rbp, [rsi+rdi+48h]
0x18000946c  lea     r9, [r13+10h]
0x180009470  mov     r8, [r15+38h]
0x180009474  add     rbp, rcx
0x180009477  mov     rdx, rbp
0x18000947a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000947f  mov     r8, [r15+80h]
0x180009486  mov     r9, rbx
0x180009489  mov     rdx, rbp
0x18000948c  mov     rcx, rax
0x18000948f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009494  mov     rbx, rax
0x180009497  cmp     rax, rbp
0x18000949a  jz      short loc_1800094DE
0x18000949c  mov     r8, [r15+18h]; Source
0x1800094a0  test    r8, r8
0x1800094a3  jz      short loc_1800094DE
0x1800094a5  cmp     [r8], r12w
0x1800094a9  jz      short loc_1800094DE
0x1800094ab  inc     r14
0x1800094ae  cmp     [r8+r14*2], r12w
0x1800094b3  jnz     short loc_1800094AB
0x1800094b5  mov     rdx, rbp
0x1800094b8  lea     r14, ds:2[r14*2]
0x1800094c0  sub     rdx, rbx; DestinationSize
0x1800094c3  cmp     rdx, r14
0x1800094c6  jb      short loc_1800094DE
0x1800094c8  mov     r9, r14; SourceSize
0x1800094cb  mov     rcx, rbx; Destination
0x1800094ce  call    cs:__imp_memcpy_s
0x1800094d4  mov     [rsi+rdi+38h], rbx
0x1800094d9  add     rbx, r14
0x1800094dc  jmp     short loc_1800094E3
0x1800094de  mov     [rsi+rdi+38h], r12
0x1800094e3  sub     rbp, rbx
0x1800094e6  xor     edx, edx; Val
0x1800094e8  mov     r8, rbp; Size
0x1800094eb  mov     rcx, rbx; void *
0x1800094ee  call    memset_0
0x1800094f3  mov     rbx, [rsp+58h+arg_10]
0x1800094f8  add     rsp, 20h
0x1800094fc  pop     r15
0x1800094fe  pop     r14
0x180009500  pop     r13
0x180009502  pop     r12
0x180009504  pop     rdi
0x180009505  pop     rsi
0x180009506  pop     rbp
0x180009507  retn
```
