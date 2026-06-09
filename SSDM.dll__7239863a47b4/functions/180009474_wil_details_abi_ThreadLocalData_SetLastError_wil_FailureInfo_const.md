# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009474`
- end: `0x1800096f9`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800086a0`

## callees

- `0x18000694c`
- `0x180007bf4`
- `0x180009474`
- `0x18000e962`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800096c3`
- `msvcrt!memcpy_s` at `0x1800096c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009626`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009626`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009634`

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
0x180009474  push    rbx
0x180009476  push    rbp
0x180009477  push    rsi
0x180009478  push    rdi
0x180009479  push    r12
0x18000947b  push    r13
0x18000947d  push    r14
0x18000947f  push    r15
0x180009481  sub     rsp, 28h
0x180009485  mov     esi, [rcx+10h]
0x180009488  xor     r12d, r12d
0x18000948b  mov     r15, rdx
0x18000948e  mov     rbx, rcx
0x180009491  mov     ebp, 50h ; 'P'
0x180009496  cmp     [rcx+18h], r12
0x18000949a  jnz     short loc_1800094D1
0x18000949c  test    esi, esi
0x18000949e  jz      short loc_1800094D1
0x1800094a0  mov     edx, 190h; dwBytes
0x1800094a5  lea     ecx, [rbp-48h]; dwFlags
0x1800094a8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800094ad  mov     [rbx+18h], rax
0x1800094b1  test    rax, rax
0x1800094b4  jz      short loc_1800094D1
0x1800094b6  mov     dword ptr [rbx+20h], 5
0x1800094bd  lea     rcx, [rax+190h]
0x1800094c4  jmp     short loc_1800094CC
0x1800094c6  mov     [rax], bp
0x1800094c9  add     rax, rbp
0x1800094cc  cmp     rax, rcx
0x1800094cf  jnz     short loc_1800094C6
0x1800094d1  mov     rdi, [rbx+18h]
0x1800094d5  test    rdi, rdi
0x1800094d8  jz      loc_1800096E8
0x1800094de  test    esi, esi
0x1800094e0  jz      short loc_180009518
0x1800094e2  movzx   eax, word ptr [rbx+20h]
0x1800094e6  mov     rcx, rdi
0x1800094e9  lea     rdx, [rax+rax*4]
0x1800094ed  shl     rdx, 4
0x1800094f1  add     rdx, rdi
0x1800094f4  cmp     rdi, rdx
0x1800094f7  jz      short loc_180009518
0x1800094f9  mov     r8d, [rbx+10h]
0x1800094fd  cmp     [rcx+4], r8d
0x180009501  jbe     short loc_180009510
0x180009503  mov     eax, [r15+8]
0x180009507  cmp     [rcx+8], eax
0x18000950a  jz      loc_1800096E8
0x180009510  add     rcx, rbp
0x180009513  cmp     rcx, rdx
0x180009516  jnz     short loc_1800094FD
0x180009518  movzx   eax, word ptr [rbx+22h]
0x18000951c  mov     r8d, 1
0x180009522  movzx   ecx, word ptr [rbx+20h]
0x180009526  add     eax, r8d
0x180009529  xor     edx, edx
0x18000952b  div     ecx
0x18000952d  mov     ecx, r8d
0x180009530  movzx   eax, dx
0x180009533  mov     [rbx+22h], dx
0x180009537  lea     rsi, [rax+rax*4]
0x18000953b  mov     rax, [rbx+8]
0x18000953f  shl     rsi, 4
0x180009543  lock xadd [rax], ecx
0x180009547  add     ecx, r8d
0x18000954a  lea     r13, [rsi+rdi]
0x18000954e  mov     [rsi+rdi+4], ecx
0x180009552  lea     rbx, [rdi+20h]
0x180009556  mov     eax, [r15+8]
0x18000955a  add     rbx, rsi
0x18000955d  mov     [rsi+rdi+8], eax
0x180009561  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009565  mov     [r13+10h], r12
0x180009569  movzx   eax, word ptr [r15+40h]
0x18000956e  mov     [rsi+rdi+18h], ax
0x180009573  mov     al, [r15]
0x180009576  mov     [rsi+rdi+1Ah], al
0x18000957a  mov     [rbx], r12
0x18000957d  mov     rax, [r15+88h]
0x180009584  mov     [rsi+rdi+28h], rax
0x180009589  mov     rax, [r15+90h]
0x180009590  mov     [rsi+rdi+30h], rax
0x180009595  mov     [rsi+rdi+38h], r12
0x18000959a  mov     rcx, [r15+38h]
0x18000959e  test    rcx, rcx
0x1800095a1  jnz     short loc_1800095A8
0x1800095a3  mov     edx, r8d
0x1800095a6  jmp     short loc_1800095B8
0x1800095a8  mov     rax, r14
0x1800095ab  inc     rax
0x1800095ae  cmp     [rcx+rax], r12b
0x1800095b2  jnz     short loc_1800095AB
0x1800095b4  lea     rdx, [rax+1]
0x1800095b8  mov     rcx, [r15+80h]
0x1800095bf  test    rcx, rcx
0x1800095c2  jz      short loc_1800095D4
0x1800095c4  mov     rax, r14
0x1800095c7  inc     rax
0x1800095ca  cmp     [rcx+rax], r12b
0x1800095ce  jnz     short loc_1800095C7
0x1800095d0  lea     r8, [rax+1]; unsigned __int64
0x1800095d4  mov     rcx, [r15+18h]
0x1800095d8  test    rcx, rcx
0x1800095db  jnz     short loc_1800095E2
0x1800095dd  lea     eax, [rcx+2]
0x1800095e0  jmp     short loc_1800095F7
0x1800095e2  mov     rax, r14
0x1800095e5  inc     rax
0x1800095e8  cmp     [rcx+rax*2], r12w
0x1800095ed  jnz     short loc_1800095E5
0x1800095ef  lea     rax, ds:2[rax*2]
0x1800095f7  lea     rbp, [r8+rax]
0x1800095fb  add     rbp, rdx
0x1800095fe  cmp     [rsi+rdi+40h], r12
0x180009603  jz      short loc_18000960C
0x180009605  cmp     [rsi+rdi+48h], rbp
0x18000960a  jnb     short loc_18000964E
0x18000960c  mov     rdx, rbp; dwBytes
0x18000960f  mov     ecx, 8; dwFlags
0x180009614  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009619  mov     r12, rax
0x18000961c  test    rax, rax
0x18000961f  jz      short loc_18000964B
0x180009621  mov     rbx, [rsi+rdi+40h]
0x180009626  call    cs:__imp_GetProcessHeap
0x18000962c  mov     r8, rbx; lpMem
0x18000962f  xor     edx, edx; dwFlags
0x180009631  mov     rcx, rax; hHeap
0x180009634  call    cs:__imp_HeapFree
0x18000963a  lea     rbx, [rdi+20h]
0x18000963e  mov     [rsi+rdi+40h], r12
0x180009643  add     rbx, rsi
0x180009646  mov     [rsi+rdi+48h], rbp
0x18000964b  xor     r12d, r12d
0x18000964e  mov     rcx, [rsi+rdi+40h]
0x180009653  test    rcx, rcx
0x180009656  jz      loc_1800096E8
0x18000965c  mov     rbp, [rsi+rdi+48h]
0x180009661  lea     r9, [r13+10h]
0x180009665  mov     r8, [r15+38h]
0x180009669  add     rbp, rcx
0x18000966c  mov     rdx, rbp
0x18000966f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009674  mov     r8, [r15+80h]
0x18000967b  mov     r9, rbx
0x18000967e  mov     rdx, rbp
0x180009681  mov     rcx, rax
0x180009684  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009689  mov     rbx, rax
0x18000968c  cmp     rax, rbp
0x18000968f  jz      short loc_1800096D3
0x180009691  mov     r8, [r15+18h]; Source
0x180009695  test    r8, r8
0x180009698  jz      short loc_1800096D3
0x18000969a  cmp     [r8], r12w
0x18000969e  jz      short loc_1800096D3
0x1800096a0  inc     r14
0x1800096a3  cmp     [r8+r14*2], r12w
0x1800096a8  jnz     short loc_1800096A0
0x1800096aa  mov     rdx, rbp
0x1800096ad  lea     r14, ds:2[r14*2]
0x1800096b5  sub     rdx, rbx; DestinationSize
0x1800096b8  cmp     rdx, r14
0x1800096bb  jb      short loc_1800096D3
0x1800096bd  mov     r9, r14; SourceSize
0x1800096c0  mov     rcx, rbx; Destination
0x1800096c3  call    cs:__imp_memcpy_s
0x1800096c9  mov     [rsi+rdi+38h], rbx
0x1800096ce  add     rbx, r14
0x1800096d1  jmp     short loc_1800096D8
0x1800096d3  mov     [rsi+rdi+38h], r12
0x1800096d8  sub     rbp, rbx
0x1800096db  xor     edx, edx; Val
0x1800096dd  mov     r8, rbp; Size
0x1800096e0  mov     rcx, rbx; void *
0x1800096e3  call    memset_0
0x1800096e8  add     rsp, 28h
0x1800096ec  pop     r15
0x1800096ee  pop     r14
0x1800096f0  pop     r13
0x1800096f2  pop     r12
0x1800096f4  pop     rdi
0x1800096f5  pop     rsi
0x1800096f6  pop     rbp
0x1800096f7  pop     rbx
0x1800096f8  retn
```
