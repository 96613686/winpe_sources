# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800066f4`
- end: `0x180006979`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004800`

## callees

- `0x180003874`
- `0x1800059dc`
- `0x1800066f4`
- `0x18000c4f2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006943`
- `msvcrt!memcpy_s` at `0x180006943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068b4`

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
0x1800066f4  push    rbx
0x1800066f6  push    rbp
0x1800066f7  push    rsi
0x1800066f8  push    rdi
0x1800066f9  push    r12
0x1800066fb  push    r13
0x1800066fd  push    r14
0x1800066ff  push    r15
0x180006701  sub     rsp, 28h
0x180006705  mov     esi, [rcx+10h]
0x180006708  xor     r12d, r12d
0x18000670b  mov     r15, rdx
0x18000670e  mov     rbx, rcx
0x180006711  mov     ebp, 50h ; 'P'
0x180006716  cmp     [rcx+18h], r12
0x18000671a  jnz     short loc_180006751
0x18000671c  test    esi, esi
0x18000671e  jz      short loc_180006751
0x180006720  mov     edx, 190h; dwBytes
0x180006725  lea     ecx, [rbp-48h]; dwFlags
0x180006728  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000672d  mov     [rbx+18h], rax
0x180006731  test    rax, rax
0x180006734  jz      short loc_180006751
0x180006736  mov     dword ptr [rbx+20h], 5
0x18000673d  lea     rcx, [rax+190h]
0x180006744  jmp     short loc_18000674C
0x180006746  mov     [rax], bp
0x180006749  add     rax, rbp
0x18000674c  cmp     rax, rcx
0x18000674f  jnz     short loc_180006746
0x180006751  mov     rdi, [rbx+18h]
0x180006755  test    rdi, rdi
0x180006758  jz      loc_180006968
0x18000675e  test    esi, esi
0x180006760  jz      short loc_180006798
0x180006762  movzx   eax, word ptr [rbx+20h]
0x180006766  mov     rcx, rdi
0x180006769  lea     rdx, [rax+rax*4]
0x18000676d  shl     rdx, 4
0x180006771  add     rdx, rdi
0x180006774  cmp     rdi, rdx
0x180006777  jz      short loc_180006798
0x180006779  mov     r8d, [rbx+10h]
0x18000677d  cmp     [rcx+4], r8d
0x180006781  jbe     short loc_180006790
0x180006783  mov     eax, [r15+8]
0x180006787  cmp     [rcx+8], eax
0x18000678a  jz      loc_180006968
0x180006790  add     rcx, rbp
0x180006793  cmp     rcx, rdx
0x180006796  jnz     short loc_18000677D
0x180006798  movzx   eax, word ptr [rbx+22h]
0x18000679c  mov     r8d, 1
0x1800067a2  movzx   ecx, word ptr [rbx+20h]
0x1800067a6  add     eax, r8d
0x1800067a9  xor     edx, edx
0x1800067ab  div     ecx
0x1800067ad  mov     ecx, r8d
0x1800067b0  movzx   eax, dx
0x1800067b3  mov     [rbx+22h], dx
0x1800067b7  lea     rsi, [rax+rax*4]
0x1800067bb  mov     rax, [rbx+8]
0x1800067bf  shl     rsi, 4
0x1800067c3  lock xadd [rax], ecx
0x1800067c7  add     ecx, r8d
0x1800067ca  lea     r13, [rsi+rdi]
0x1800067ce  mov     [rsi+rdi+4], ecx
0x1800067d2  lea     rbx, [rdi+20h]
0x1800067d6  mov     eax, [r15+8]
0x1800067da  add     rbx, rsi
0x1800067dd  mov     [rsi+rdi+8], eax
0x1800067e1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800067e5  mov     [r13+10h], r12
0x1800067e9  movzx   eax, word ptr [r15+40h]
0x1800067ee  mov     [rsi+rdi+18h], ax
0x1800067f3  mov     al, [r15]
0x1800067f6  mov     [rsi+rdi+1Ah], al
0x1800067fa  mov     [rbx], r12
0x1800067fd  mov     rax, [r15+88h]
0x180006804  mov     [rsi+rdi+28h], rax
0x180006809  mov     rax, [r15+90h]
0x180006810  mov     [rsi+rdi+30h], rax
0x180006815  mov     [rsi+rdi+38h], r12
0x18000681a  mov     rcx, [r15+38h]
0x18000681e  test    rcx, rcx
0x180006821  jnz     short loc_180006828
0x180006823  mov     edx, r8d
0x180006826  jmp     short loc_180006838
0x180006828  mov     rax, r14
0x18000682b  inc     rax
0x18000682e  cmp     [rcx+rax], r12b
0x180006832  jnz     short loc_18000682B
0x180006834  lea     rdx, [rax+1]
0x180006838  mov     rcx, [r15+80h]
0x18000683f  test    rcx, rcx
0x180006842  jz      short loc_180006854
0x180006844  mov     rax, r14
0x180006847  inc     rax
0x18000684a  cmp     [rcx+rax], r12b
0x18000684e  jnz     short loc_180006847
0x180006850  lea     r8, [rax+1]; unsigned __int64
0x180006854  mov     rcx, [r15+18h]
0x180006858  test    rcx, rcx
0x18000685b  jnz     short loc_180006862
0x18000685d  lea     eax, [rcx+2]
0x180006860  jmp     short loc_180006877
0x180006862  mov     rax, r14
0x180006865  inc     rax
0x180006868  cmp     [rcx+rax*2], r12w
0x18000686d  jnz     short loc_180006865
0x18000686f  lea     rax, ds:2[rax*2]
0x180006877  lea     rbp, [r8+rax]
0x18000687b  add     rbp, rdx
0x18000687e  cmp     [rsi+rdi+40h], r12
0x180006883  jz      short loc_18000688C
0x180006885  cmp     [rsi+rdi+48h], rbp
0x18000688a  jnb     short loc_1800068CE
0x18000688c  mov     rdx, rbp; dwBytes
0x18000688f  mov     ecx, 8; dwFlags
0x180006894  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006899  mov     r12, rax
0x18000689c  test    rax, rax
0x18000689f  jz      short loc_1800068CB
0x1800068a1  mov     rbx, [rsi+rdi+40h]
0x1800068a6  call    cs:__imp_GetProcessHeap
0x1800068ac  mov     r8, rbx; lpMem
0x1800068af  xor     edx, edx; dwFlags
0x1800068b1  mov     rcx, rax; hHeap
0x1800068b4  call    cs:__imp_HeapFree
0x1800068ba  lea     rbx, [rdi+20h]
0x1800068be  mov     [rsi+rdi+40h], r12
0x1800068c3  add     rbx, rsi
0x1800068c6  mov     [rsi+rdi+48h], rbp
0x1800068cb  xor     r12d, r12d
0x1800068ce  mov     rcx, [rsi+rdi+40h]
0x1800068d3  test    rcx, rcx
0x1800068d6  jz      loc_180006968
0x1800068dc  mov     rbp, [rsi+rdi+48h]
0x1800068e1  lea     r9, [r13+10h]
0x1800068e5  mov     r8, [r15+38h]
0x1800068e9  add     rbp, rcx
0x1800068ec  mov     rdx, rbp
0x1800068ef  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800068f4  mov     r8, [r15+80h]
0x1800068fb  mov     r9, rbx
0x1800068fe  mov     rdx, rbp
0x180006901  mov     rcx, rax
0x180006904  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006909  mov     rbx, rax
0x18000690c  cmp     rax, rbp
0x18000690f  jz      short loc_180006953
0x180006911  mov     r8, [r15+18h]; Source
0x180006915  test    r8, r8
0x180006918  jz      short loc_180006953
0x18000691a  cmp     [r8], r12w
0x18000691e  jz      short loc_180006953
0x180006920  inc     r14
0x180006923  cmp     [r8+r14*2], r12w
0x180006928  jnz     short loc_180006920
0x18000692a  mov     rdx, rbp
0x18000692d  lea     r14, ds:2[r14*2]
0x180006935  sub     rdx, rbx; DestinationSize
0x180006938  cmp     rdx, r14
0x18000693b  jb      short loc_180006953
0x18000693d  mov     r9, r14; SourceSize
0x180006940  mov     rcx, rbx; Destination
0x180006943  call    cs:__imp_memcpy_s
0x180006949  mov     [rsi+rdi+38h], rbx
0x18000694e  add     rbx, r14
0x180006951  jmp     short loc_180006958
0x180006953  mov     [rsi+rdi+38h], r12
0x180006958  sub     rbp, rbx
0x18000695b  xor     edx, edx; Val
0x18000695d  mov     r8, rbp; Size
0x180006960  mov     rcx, rbx; void *
0x180006963  call    memset_0
0x180006968  add     rsp, 28h
0x18000696c  pop     r15
0x18000696e  pop     r14
0x180006970  pop     r13
0x180006972  pop     r12
0x180006974  pop     rdi
0x180006975  pop     rsi
0x180006976  pop     rbp
0x180006977  pop     rbx
0x180006978  retn
```
