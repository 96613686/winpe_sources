# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000902c`
- end: `0x1800092b8`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `652`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800052e0`

## callees

- `0x180002cd0`
- `0x180006ffc`
- `0x18000902c`
- `0x18000c5e2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000927e`
- `msvcrt!memcpy_s` at `0x18000927e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091e1`

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
0x18000902c  mov     [rsp+arg_10], rbx
0x180009031  push    rbp
0x180009032  push    rsi
0x180009033  push    rdi
0x180009034  push    r12
0x180009036  push    r13
0x180009038  push    r14
0x18000903a  push    r15
0x18000903c  sub     rsp, 20h
0x180009040  mov     esi, [rcx+10h]
0x180009043  xor     r12d, r12d
0x180009046  mov     r15, rdx
0x180009049  mov     rbx, rcx
0x18000904c  mov     ebp, 50h ; 'P'
0x180009051  cmp     [rcx+18h], r12
0x180009055  jnz     short loc_18000908C
0x180009057  test    esi, esi
0x180009059  jz      short loc_18000908C
0x18000905b  mov     edx, 190h; dwBytes
0x180009060  lea     ecx, [rbp-48h]; dwFlags
0x180009063  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009068  mov     [rbx+18h], rax
0x18000906c  test    rax, rax
0x18000906f  jz      short loc_18000908C
0x180009071  mov     dword ptr [rbx+20h], 5
0x180009078  lea     rcx, [rax+190h]
0x18000907f  jmp     short loc_180009087
0x180009081  mov     [rax], bp
0x180009084  add     rax, rbp
0x180009087  cmp     rax, rcx
0x18000908a  jnz     short loc_180009081
0x18000908c  mov     rdi, [rbx+18h]
0x180009090  test    rdi, rdi
0x180009093  jz      loc_1800092A3
0x180009099  test    esi, esi
0x18000909b  jz      short loc_1800090D3
0x18000909d  movzx   eax, word ptr [rbx+20h]
0x1800090a1  mov     rcx, rdi
0x1800090a4  lea     rdx, [rax+rax*4]
0x1800090a8  shl     rdx, 4
0x1800090ac  add     rdx, rdi
0x1800090af  cmp     rdi, rdx
0x1800090b2  jz      short loc_1800090D3
0x1800090b4  mov     r8d, [rbx+10h]
0x1800090b8  cmp     [rcx+4], r8d
0x1800090bc  jbe     short loc_1800090CB
0x1800090be  mov     eax, [r15+8]
0x1800090c2  cmp     [rcx+8], eax
0x1800090c5  jz      loc_1800092A3
0x1800090cb  add     rcx, rbp
0x1800090ce  cmp     rcx, rdx
0x1800090d1  jnz     short loc_1800090B8
0x1800090d3  movzx   eax, word ptr [rbx+22h]
0x1800090d7  mov     r8d, 1
0x1800090dd  movzx   ecx, word ptr [rbx+20h]
0x1800090e1  add     eax, r8d
0x1800090e4  xor     edx, edx
0x1800090e6  div     ecx
0x1800090e8  mov     ecx, r8d
0x1800090eb  movzx   eax, dx
0x1800090ee  mov     [rbx+22h], dx
0x1800090f2  lea     rsi, [rax+rax*4]
0x1800090f6  mov     rax, [rbx+8]
0x1800090fa  shl     rsi, 4
0x1800090fe  lock xadd [rax], ecx
0x180009102  add     ecx, r8d
0x180009105  lea     r13, [rsi+rdi]
0x180009109  mov     [rsi+rdi+4], ecx
0x18000910d  lea     rbx, [rdi+20h]
0x180009111  mov     eax, [r15+8]
0x180009115  add     rbx, rsi
0x180009118  mov     [rsi+rdi+8], eax
0x18000911c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009120  mov     [r13+10h], r12
0x180009124  movzx   eax, word ptr [r15+40h]
0x180009129  mov     [rsi+rdi+18h], ax
0x18000912e  mov     al, [r15]
0x180009131  mov     [rsi+rdi+1Ah], al
0x180009135  mov     [rbx], r12
0x180009138  mov     rax, [r15+88h]
0x18000913f  mov     [rsi+rdi+28h], rax
0x180009144  mov     rax, [r15+90h]
0x18000914b  mov     [rsi+rdi+30h], rax
0x180009150  mov     [rsi+rdi+38h], r12
0x180009155  mov     rcx, [r15+38h]
0x180009159  test    rcx, rcx
0x18000915c  jnz     short loc_180009163
0x18000915e  mov     edx, r8d
0x180009161  jmp     short loc_180009173
0x180009163  mov     rax, r14
0x180009166  inc     rax
0x180009169  cmp     [rcx+rax], r12b
0x18000916d  jnz     short loc_180009166
0x18000916f  lea     rdx, [rax+1]
0x180009173  mov     rcx, [r15+80h]
0x18000917a  test    rcx, rcx
0x18000917d  jz      short loc_18000918F
0x18000917f  mov     rax, r14
0x180009182  inc     rax
0x180009185  cmp     [rcx+rax], r12b
0x180009189  jnz     short loc_180009182
0x18000918b  lea     r8, [rax+1]; unsigned __int64
0x18000918f  mov     rcx, [r15+18h]
0x180009193  test    rcx, rcx
0x180009196  jnz     short loc_18000919D
0x180009198  lea     eax, [rcx+2]
0x18000919b  jmp     short loc_1800091B2
0x18000919d  mov     rax, r14
0x1800091a0  inc     rax
0x1800091a3  cmp     [rcx+rax*2], r12w
0x1800091a8  jnz     short loc_1800091A0
0x1800091aa  lea     rax, ds:2[rax*2]
0x1800091b2  lea     rbp, [r8+rax]
0x1800091b6  add     rbp, rdx
0x1800091b9  cmp     [rsi+rdi+40h], r12
0x1800091be  jz      short loc_1800091C7
0x1800091c0  cmp     [rsi+rdi+48h], rbp
0x1800091c5  jnb     short loc_180009209
0x1800091c7  mov     rdx, rbp; dwBytes
0x1800091ca  mov     ecx, 8; dwFlags
0x1800091cf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800091d4  mov     r12, rax
0x1800091d7  test    rax, rax
0x1800091da  jz      short loc_180009206
0x1800091dc  mov     rbx, [rsi+rdi+40h]
0x1800091e1  call    cs:__imp_GetProcessHeap
0x1800091e7  mov     r8, rbx; lpMem
0x1800091ea  xor     edx, edx; dwFlags
0x1800091ec  mov     rcx, rax; hHeap
0x1800091ef  call    cs:__imp_HeapFree
0x1800091f5  lea     rbx, [rdi+20h]
0x1800091f9  mov     [rsi+rdi+40h], r12
0x1800091fe  add     rbx, rsi
0x180009201  mov     [rsi+rdi+48h], rbp
0x180009206  xor     r12d, r12d
0x180009209  mov     rcx, [rsi+rdi+40h]
0x18000920e  test    rcx, rcx
0x180009211  jz      loc_1800092A3
0x180009217  mov     rbp, [rsi+rdi+48h]
0x18000921c  lea     r9, [r13+10h]
0x180009220  mov     r8, [r15+38h]
0x180009224  add     rbp, rcx
0x180009227  mov     rdx, rbp
0x18000922a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000922f  mov     r8, [r15+80h]
0x180009236  mov     r9, rbx
0x180009239  mov     rdx, rbp
0x18000923c  mov     rcx, rax
0x18000923f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009244  mov     rbx, rax
0x180009247  cmp     rax, rbp
0x18000924a  jz      short loc_18000928E
0x18000924c  mov     r8, [r15+18h]; Source
0x180009250  test    r8, r8
0x180009253  jz      short loc_18000928E
0x180009255  cmp     [r8], r12w
0x180009259  jz      short loc_18000928E
0x18000925b  inc     r14
0x18000925e  cmp     [r8+r14*2], r12w
0x180009263  jnz     short loc_18000925B
0x180009265  mov     rdx, rbp
0x180009268  lea     r14, ds:2[r14*2]
0x180009270  sub     rdx, rbx; DestinationSize
0x180009273  cmp     rdx, r14
0x180009276  jb      short loc_18000928E
0x180009278  mov     r9, r14; SourceSize
0x18000927b  mov     rcx, rbx; Destination
0x18000927e  call    cs:__imp_memcpy_s
0x180009284  mov     [rsi+rdi+38h], rbx
0x180009289  add     rbx, r14
0x18000928c  jmp     short loc_180009293
0x18000928e  mov     [rsi+rdi+38h], r12
0x180009293  sub     rbp, rbx
0x180009296  xor     edx, edx; Val
0x180009298  mov     r8, rbp; Size
0x18000929b  mov     rcx, rbx; void *
0x18000929e  call    memset_0
0x1800092a3  mov     rbx, [rsp+58h+arg_10]
0x1800092a8  add     rsp, 20h
0x1800092ac  pop     r15
0x1800092ae  pop     r14
0x1800092b0  pop     r13
0x1800092b2  pop     r12
0x1800092b4  pop     rdi
0x1800092b5  pop     rsi
0x1800092b6  pop     rbp
0x1800092b7  retn
```
