# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006198`
- end: `0x18000641d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004500`

## callees

- `0x18000349c`
- `0x1800055ac`
- `0x180006198`
- `0x180021822`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800063e7`
- `msvcrt!memcpy_s` at `0x1800063e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000634a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000634a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006358`

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
0x180006198  push    rbx
0x18000619a  push    rbp
0x18000619b  push    rsi
0x18000619c  push    rdi
0x18000619d  push    r12
0x18000619f  push    r13
0x1800061a1  push    r14
0x1800061a3  push    r15
0x1800061a5  sub     rsp, 28h
0x1800061a9  mov     esi, [rcx+10h]
0x1800061ac  xor     r12d, r12d
0x1800061af  mov     r15, rdx
0x1800061b2  mov     rbx, rcx
0x1800061b5  mov     ebp, 50h ; 'P'
0x1800061ba  cmp     [rcx+18h], r12
0x1800061be  jnz     short loc_1800061F5
0x1800061c0  test    esi, esi
0x1800061c2  jz      short loc_1800061F5
0x1800061c4  mov     edx, 190h; dwBytes
0x1800061c9  lea     ecx, [rbp-48h]; dwFlags
0x1800061cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800061d1  mov     [rbx+18h], rax
0x1800061d5  test    rax, rax
0x1800061d8  jz      short loc_1800061F5
0x1800061da  mov     dword ptr [rbx+20h], 5
0x1800061e1  lea     rcx, [rax+190h]
0x1800061e8  jmp     short loc_1800061F0
0x1800061ea  mov     [rax], bp
0x1800061ed  add     rax, rbp
0x1800061f0  cmp     rax, rcx
0x1800061f3  jnz     short loc_1800061EA
0x1800061f5  mov     rdi, [rbx+18h]
0x1800061f9  test    rdi, rdi
0x1800061fc  jz      loc_18000640C
0x180006202  test    esi, esi
0x180006204  jz      short loc_18000623C
0x180006206  movzx   eax, word ptr [rbx+20h]
0x18000620a  mov     rcx, rdi
0x18000620d  lea     rdx, [rax+rax*4]
0x180006211  shl     rdx, 4
0x180006215  add     rdx, rdi
0x180006218  cmp     rdi, rdx
0x18000621b  jz      short loc_18000623C
0x18000621d  mov     r8d, [rbx+10h]
0x180006221  cmp     [rcx+4], r8d
0x180006225  jbe     short loc_180006234
0x180006227  mov     eax, [r15+8]
0x18000622b  cmp     [rcx+8], eax
0x18000622e  jz      loc_18000640C
0x180006234  add     rcx, rbp
0x180006237  cmp     rcx, rdx
0x18000623a  jnz     short loc_180006221
0x18000623c  movzx   eax, word ptr [rbx+22h]
0x180006240  mov     r8d, 1
0x180006246  movzx   ecx, word ptr [rbx+20h]
0x18000624a  add     eax, r8d
0x18000624d  xor     edx, edx
0x18000624f  div     ecx
0x180006251  mov     ecx, r8d
0x180006254  movzx   eax, dx
0x180006257  mov     [rbx+22h], dx
0x18000625b  lea     rsi, [rax+rax*4]
0x18000625f  mov     rax, [rbx+8]
0x180006263  shl     rsi, 4
0x180006267  lock xadd [rax], ecx
0x18000626b  add     ecx, r8d
0x18000626e  lea     r13, [rsi+rdi]
0x180006272  mov     [rsi+rdi+4], ecx
0x180006276  lea     rbx, [rdi+20h]
0x18000627a  mov     eax, [r15+8]
0x18000627e  add     rbx, rsi
0x180006281  mov     [rsi+rdi+8], eax
0x180006285  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006289  mov     [r13+10h], r12
0x18000628d  movzx   eax, word ptr [r15+40h]
0x180006292  mov     [rsi+rdi+18h], ax
0x180006297  mov     al, [r15]
0x18000629a  mov     [rsi+rdi+1Ah], al
0x18000629e  mov     [rbx], r12
0x1800062a1  mov     rax, [r15+88h]
0x1800062a8  mov     [rsi+rdi+28h], rax
0x1800062ad  mov     rax, [r15+90h]
0x1800062b4  mov     [rsi+rdi+30h], rax
0x1800062b9  mov     [rsi+rdi+38h], r12
0x1800062be  mov     rcx, [r15+38h]
0x1800062c2  test    rcx, rcx
0x1800062c5  jnz     short loc_1800062CC
0x1800062c7  mov     edx, r8d
0x1800062ca  jmp     short loc_1800062DC
0x1800062cc  mov     rax, r14
0x1800062cf  inc     rax
0x1800062d2  cmp     [rcx+rax], r12b
0x1800062d6  jnz     short loc_1800062CF
0x1800062d8  lea     rdx, [rax+1]
0x1800062dc  mov     rcx, [r15+80h]
0x1800062e3  test    rcx, rcx
0x1800062e6  jz      short loc_1800062F8
0x1800062e8  mov     rax, r14
0x1800062eb  inc     rax
0x1800062ee  cmp     [rcx+rax], r12b
0x1800062f2  jnz     short loc_1800062EB
0x1800062f4  lea     r8, [rax+1]; unsigned __int64
0x1800062f8  mov     rcx, [r15+18h]
0x1800062fc  test    rcx, rcx
0x1800062ff  jnz     short loc_180006306
0x180006301  lea     eax, [rcx+2]
0x180006304  jmp     short loc_18000631B
0x180006306  mov     rax, r14
0x180006309  inc     rax
0x18000630c  cmp     [rcx+rax*2], r12w
0x180006311  jnz     short loc_180006309
0x180006313  lea     rax, ds:2[rax*2]
0x18000631b  lea     rbp, [r8+rax]
0x18000631f  add     rbp, rdx
0x180006322  cmp     [rsi+rdi+40h], r12
0x180006327  jz      short loc_180006330
0x180006329  cmp     [rsi+rdi+48h], rbp
0x18000632e  jnb     short loc_180006372
0x180006330  mov     rdx, rbp; dwBytes
0x180006333  mov     ecx, 8; dwFlags
0x180006338  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000633d  mov     r12, rax
0x180006340  test    rax, rax
0x180006343  jz      short loc_18000636F
0x180006345  mov     rbx, [rsi+rdi+40h]
0x18000634a  call    cs:__imp_GetProcessHeap
0x180006350  mov     r8, rbx; lpMem
0x180006353  xor     edx, edx; dwFlags
0x180006355  mov     rcx, rax; hHeap
0x180006358  call    cs:__imp_HeapFree
0x18000635e  lea     rbx, [rdi+20h]
0x180006362  mov     [rsi+rdi+40h], r12
0x180006367  add     rbx, rsi
0x18000636a  mov     [rsi+rdi+48h], rbp
0x18000636f  xor     r12d, r12d
0x180006372  mov     rcx, [rsi+rdi+40h]
0x180006377  test    rcx, rcx
0x18000637a  jz      loc_18000640C
0x180006380  mov     rbp, [rsi+rdi+48h]
0x180006385  lea     r9, [r13+10h]
0x180006389  mov     r8, [r15+38h]
0x18000638d  add     rbp, rcx
0x180006390  mov     rdx, rbp
0x180006393  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006398  mov     r8, [r15+80h]
0x18000639f  mov     r9, rbx
0x1800063a2  mov     rdx, rbp
0x1800063a5  mov     rcx, rax
0x1800063a8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800063ad  mov     rbx, rax
0x1800063b0  cmp     rax, rbp
0x1800063b3  jz      short loc_1800063F7
0x1800063b5  mov     r8, [r15+18h]; Source
0x1800063b9  test    r8, r8
0x1800063bc  jz      short loc_1800063F7
0x1800063be  cmp     [r8], r12w
0x1800063c2  jz      short loc_1800063F7
0x1800063c4  inc     r14
0x1800063c7  cmp     [r8+r14*2], r12w
0x1800063cc  jnz     short loc_1800063C4
0x1800063ce  mov     rdx, rbp
0x1800063d1  lea     r14, ds:2[r14*2]
0x1800063d9  sub     rdx, rbx; DestinationSize
0x1800063dc  cmp     rdx, r14
0x1800063df  jb      short loc_1800063F7
0x1800063e1  mov     r9, r14; SourceSize
0x1800063e4  mov     rcx, rbx; Destination
0x1800063e7  call    cs:__imp_memcpy_s
0x1800063ed  mov     [rsi+rdi+38h], rbx
0x1800063f2  add     rbx, r14
0x1800063f5  jmp     short loc_1800063FC
0x1800063f7  mov     [rsi+rdi+38h], r12
0x1800063fc  sub     rbp, rbx
0x1800063ff  xor     edx, edx; Val
0x180006401  mov     r8, rbp; Size
0x180006404  mov     rcx, rbx; void *
0x180006407  call    memset_0
0x18000640c  add     rsp, 28h
0x180006410  pop     r15
0x180006412  pop     r14
0x180006414  pop     r13
0x180006416  pop     r12
0x180006418  pop     rdi
0x180006419  pop     rsi
0x18000641a  pop     rbp
0x18000641b  pop     rbx
0x18000641c  retn
```
