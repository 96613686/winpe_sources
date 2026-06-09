# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18002e2cc`
- end: `0x18002e551`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a5f0`

## callees

- `0x1800268ef`
- `0x1800279a0`
- `0x18002bdbc`
- `0x18002e2cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002e51b`
- `msvcrt!memcpy_s` at `0x18002e51b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e48c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e47e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e47e`

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
0x18002e2cc  push    rbx
0x18002e2ce  push    rbp
0x18002e2cf  push    rsi
0x18002e2d0  push    rdi
0x18002e2d1  push    r12
0x18002e2d3  push    r13
0x18002e2d5  push    r14
0x18002e2d7  push    r15
0x18002e2d9  sub     rsp, 28h
0x18002e2dd  mov     esi, [rcx+10h]
0x18002e2e0  xor     r12d, r12d
0x18002e2e3  mov     r15, rdx
0x18002e2e6  mov     rbx, rcx
0x18002e2e9  mov     ebp, 50h ; 'P'
0x18002e2ee  cmp     [rcx+18h], r12
0x18002e2f2  jnz     short loc_18002E329
0x18002e2f4  test    esi, esi
0x18002e2f6  jz      short loc_18002E329
0x18002e2f8  mov     edx, 190h; dwBytes
0x18002e2fd  lea     ecx, [rbp-48h]; dwFlags
0x18002e300  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002e305  mov     [rbx+18h], rax
0x18002e309  test    rax, rax
0x18002e30c  jz      short loc_18002E329
0x18002e30e  mov     dword ptr [rbx+20h], 5
0x18002e315  lea     rcx, [rax+190h]
0x18002e31c  jmp     short loc_18002E324
0x18002e31e  mov     [rax], bp
0x18002e321  add     rax, rbp
0x18002e324  cmp     rax, rcx
0x18002e327  jnz     short loc_18002E31E
0x18002e329  mov     rdi, [rbx+18h]
0x18002e32d  test    rdi, rdi
0x18002e330  jz      loc_18002E540
0x18002e336  test    esi, esi
0x18002e338  jz      short loc_18002E370
0x18002e33a  movzx   eax, word ptr [rbx+20h]
0x18002e33e  mov     rcx, rdi
0x18002e341  lea     rdx, [rax+rax*4]
0x18002e345  shl     rdx, 4
0x18002e349  add     rdx, rdi
0x18002e34c  cmp     rdi, rdx
0x18002e34f  jz      short loc_18002E370
0x18002e351  mov     r8d, [rbx+10h]
0x18002e355  cmp     [rcx+4], r8d
0x18002e359  jbe     short loc_18002E368
0x18002e35b  mov     eax, [r15+8]
0x18002e35f  cmp     [rcx+8], eax
0x18002e362  jz      loc_18002E540
0x18002e368  add     rcx, rbp
0x18002e36b  cmp     rcx, rdx
0x18002e36e  jnz     short loc_18002E355
0x18002e370  movzx   eax, word ptr [rbx+22h]
0x18002e374  mov     r8d, 1
0x18002e37a  movzx   ecx, word ptr [rbx+20h]
0x18002e37e  add     eax, r8d
0x18002e381  xor     edx, edx
0x18002e383  div     ecx
0x18002e385  mov     ecx, r8d
0x18002e388  movzx   eax, dx
0x18002e38b  mov     [rbx+22h], dx
0x18002e38f  lea     rsi, [rax+rax*4]
0x18002e393  mov     rax, [rbx+8]
0x18002e397  shl     rsi, 4
0x18002e39b  lock xadd [rax], ecx
0x18002e39f  add     ecx, r8d
0x18002e3a2  lea     r13, [rsi+rdi]
0x18002e3a6  mov     [rsi+rdi+4], ecx
0x18002e3aa  lea     rbx, [rdi+20h]
0x18002e3ae  mov     eax, [r15+8]
0x18002e3b2  add     rbx, rsi
0x18002e3b5  mov     [rsi+rdi+8], eax
0x18002e3b9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e3bd  mov     [r13+10h], r12
0x18002e3c1  movzx   eax, word ptr [r15+40h]
0x18002e3c6  mov     [rsi+rdi+18h], ax
0x18002e3cb  mov     al, [r15]
0x18002e3ce  mov     [rsi+rdi+1Ah], al
0x18002e3d2  mov     [rbx], r12
0x18002e3d5  mov     rax, [r15+88h]
0x18002e3dc  mov     [rsi+rdi+28h], rax
0x18002e3e1  mov     rax, [r15+90h]
0x18002e3e8  mov     [rsi+rdi+30h], rax
0x18002e3ed  mov     [rsi+rdi+38h], r12
0x18002e3f2  mov     rcx, [r15+38h]
0x18002e3f6  test    rcx, rcx
0x18002e3f9  jnz     short loc_18002E400
0x18002e3fb  mov     edx, r8d
0x18002e3fe  jmp     short loc_18002E410
0x18002e400  mov     rax, r14
0x18002e403  inc     rax
0x18002e406  cmp     [rcx+rax], r12b
0x18002e40a  jnz     short loc_18002E403
0x18002e40c  lea     rdx, [rax+1]
0x18002e410  mov     rcx, [r15+80h]
0x18002e417  test    rcx, rcx
0x18002e41a  jz      short loc_18002E42C
0x18002e41c  mov     rax, r14
0x18002e41f  inc     rax
0x18002e422  cmp     [rcx+rax], r12b
0x18002e426  jnz     short loc_18002E41F
0x18002e428  lea     r8, [rax+1]; unsigned __int64
0x18002e42c  mov     rcx, [r15+18h]
0x18002e430  test    rcx, rcx
0x18002e433  jnz     short loc_18002E43A
0x18002e435  lea     eax, [rcx+2]
0x18002e438  jmp     short loc_18002E44F
0x18002e43a  mov     rax, r14
0x18002e43d  inc     rax
0x18002e440  cmp     [rcx+rax*2], r12w
0x18002e445  jnz     short loc_18002E43D
0x18002e447  lea     rax, ds:2[rax*2]
0x18002e44f  lea     rbp, [r8+rax]
0x18002e453  add     rbp, rdx
0x18002e456  cmp     [rsi+rdi+40h], r12
0x18002e45b  jz      short loc_18002E464
0x18002e45d  cmp     [rsi+rdi+48h], rbp
0x18002e462  jnb     short loc_18002E4A6
0x18002e464  mov     rdx, rbp; dwBytes
0x18002e467  mov     ecx, 8; dwFlags
0x18002e46c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002e471  mov     r12, rax
0x18002e474  test    rax, rax
0x18002e477  jz      short loc_18002E4A3
0x18002e479  mov     rbx, [rsi+rdi+40h]
0x18002e47e  call    cs:__imp_GetProcessHeap
0x18002e484  mov     r8, rbx; lpMem
0x18002e487  xor     edx, edx; dwFlags
0x18002e489  mov     rcx, rax; hHeap
0x18002e48c  call    cs:__imp_HeapFree
0x18002e492  lea     rbx, [rdi+20h]
0x18002e496  mov     [rsi+rdi+40h], r12
0x18002e49b  add     rbx, rsi
0x18002e49e  mov     [rsi+rdi+48h], rbp
0x18002e4a3  xor     r12d, r12d
0x18002e4a6  mov     rcx, [rsi+rdi+40h]
0x18002e4ab  test    rcx, rcx
0x18002e4ae  jz      loc_18002E540
0x18002e4b4  mov     rbp, [rsi+rdi+48h]
0x18002e4b9  lea     r9, [r13+10h]
0x18002e4bd  mov     r8, [r15+38h]
0x18002e4c1  add     rbp, rcx
0x18002e4c4  mov     rdx, rbp
0x18002e4c7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002e4cc  mov     r8, [r15+80h]
0x18002e4d3  mov     r9, rbx
0x18002e4d6  mov     rdx, rbp
0x18002e4d9  mov     rcx, rax
0x18002e4dc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002e4e1  mov     rbx, rax
0x18002e4e4  cmp     rax, rbp
0x18002e4e7  jz      short loc_18002E52B
0x18002e4e9  mov     r8, [r15+18h]; Source
0x18002e4ed  test    r8, r8
0x18002e4f0  jz      short loc_18002E52B
0x18002e4f2  cmp     [r8], r12w
0x18002e4f6  jz      short loc_18002E52B
0x18002e4f8  inc     r14
0x18002e4fb  cmp     [r8+r14*2], r12w
0x18002e500  jnz     short loc_18002E4F8
0x18002e502  mov     rdx, rbp
0x18002e505  lea     r14, ds:2[r14*2]
0x18002e50d  sub     rdx, rbx; DestinationSize
0x18002e510  cmp     rdx, r14
0x18002e513  jb      short loc_18002E52B
0x18002e515  mov     r9, r14; SourceSize
0x18002e518  mov     rcx, rbx; Destination
0x18002e51b  call    cs:__imp_memcpy_s
0x18002e521  mov     [rsi+rdi+38h], rbx
0x18002e526  add     rbx, r14
0x18002e529  jmp     short loc_18002E530
0x18002e52b  mov     [rsi+rdi+38h], r12
0x18002e530  sub     rbp, rbx
0x18002e533  xor     edx, edx; Val
0x18002e535  mov     r8, rbp; Size
0x18002e538  mov     rcx, rbx; void *
0x18002e53b  call    memset_0
0x18002e540  add     rsp, 28h
0x18002e544  pop     r15
0x18002e546  pop     r14
0x18002e548  pop     r13
0x18002e54a  pop     r12
0x18002e54c  pop     rdi
0x18002e54d  pop     rsi
0x18002e54e  pop     rbp
0x18002e54f  pop     rbx
0x18002e550  retn
```
