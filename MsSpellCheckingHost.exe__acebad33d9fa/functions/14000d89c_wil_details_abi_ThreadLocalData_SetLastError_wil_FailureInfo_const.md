# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000d89c`
- end: `0x14000db21`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a310`

## callees

- `0x1400023f3`
- `0x140007770`
- `0x14000bc90`
- `0x14000d89c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000daeb`
- `msvcrt!memcpy_s` at `0x14000daeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000da4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000da4e`

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
0x14000d89c  push    rbx
0x14000d89e  push    rbp
0x14000d89f  push    rsi
0x14000d8a0  push    rdi
0x14000d8a1  push    r12
0x14000d8a3  push    r13
0x14000d8a5  push    r14
0x14000d8a7  push    r15
0x14000d8a9  sub     rsp, 28h
0x14000d8ad  mov     esi, [rcx+10h]
0x14000d8b0  xor     r12d, r12d
0x14000d8b3  mov     r15, rdx
0x14000d8b6  mov     rbx, rcx
0x14000d8b9  mov     ebp, 50h ; 'P'
0x14000d8be  cmp     [rcx+18h], r12
0x14000d8c2  jnz     short loc_14000D8F9
0x14000d8c4  test    esi, esi
0x14000d8c6  jz      short loc_14000D8F9
0x14000d8c8  mov     edx, 190h; dwBytes
0x14000d8cd  lea     ecx, [rbp-48h]; dwFlags
0x14000d8d0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000d8d5  mov     [rbx+18h], rax
0x14000d8d9  test    rax, rax
0x14000d8dc  jz      short loc_14000D8F9
0x14000d8de  mov     dword ptr [rbx+20h], 5
0x14000d8e5  lea     rcx, [rax+190h]
0x14000d8ec  jmp     short loc_14000D8F4
0x14000d8ee  mov     [rax], bp
0x14000d8f1  add     rax, rbp
0x14000d8f4  cmp     rax, rcx
0x14000d8f7  jnz     short loc_14000D8EE
0x14000d8f9  mov     rdi, [rbx+18h]
0x14000d8fd  test    rdi, rdi
0x14000d900  jz      loc_14000DB10
0x14000d906  test    esi, esi
0x14000d908  jz      short loc_14000D940
0x14000d90a  movzx   eax, word ptr [rbx+20h]
0x14000d90e  mov     rcx, rdi
0x14000d911  lea     rdx, [rax+rax*4]
0x14000d915  shl     rdx, 4
0x14000d919  add     rdx, rdi
0x14000d91c  cmp     rdi, rdx
0x14000d91f  jz      short loc_14000D940
0x14000d921  mov     r8d, [rbx+10h]
0x14000d925  cmp     [rcx+4], r8d
0x14000d929  jbe     short loc_14000D938
0x14000d92b  mov     eax, [r15+8]
0x14000d92f  cmp     [rcx+8], eax
0x14000d932  jz      loc_14000DB10
0x14000d938  add     rcx, rbp
0x14000d93b  cmp     rcx, rdx
0x14000d93e  jnz     short loc_14000D925
0x14000d940  movzx   eax, word ptr [rbx+22h]
0x14000d944  mov     r8d, 1
0x14000d94a  movzx   ecx, word ptr [rbx+20h]
0x14000d94e  add     eax, r8d
0x14000d951  xor     edx, edx
0x14000d953  div     ecx
0x14000d955  mov     ecx, r8d
0x14000d958  movzx   eax, dx
0x14000d95b  mov     [rbx+22h], dx
0x14000d95f  lea     rsi, [rax+rax*4]
0x14000d963  mov     rax, [rbx+8]
0x14000d967  shl     rsi, 4
0x14000d96b  lock xadd [rax], ecx
0x14000d96f  add     ecx, r8d
0x14000d972  lea     r13, [rsi+rdi]
0x14000d976  mov     [rsi+rdi+4], ecx
0x14000d97a  lea     rbx, [rdi+20h]
0x14000d97e  mov     eax, [r15+8]
0x14000d982  add     rbx, rsi
0x14000d985  mov     [rsi+rdi+8], eax
0x14000d989  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000d98d  mov     [r13+10h], r12
0x14000d991  movzx   eax, word ptr [r15+40h]
0x14000d996  mov     [rsi+rdi+18h], ax
0x14000d99b  mov     al, [r15]
0x14000d99e  mov     [rsi+rdi+1Ah], al
0x14000d9a2  mov     [rbx], r12
0x14000d9a5  mov     rax, [r15+88h]
0x14000d9ac  mov     [rsi+rdi+28h], rax
0x14000d9b1  mov     rax, [r15+90h]
0x14000d9b8  mov     [rsi+rdi+30h], rax
0x14000d9bd  mov     [rsi+rdi+38h], r12
0x14000d9c2  mov     rcx, [r15+38h]
0x14000d9c6  test    rcx, rcx
0x14000d9c9  jnz     short loc_14000D9D0
0x14000d9cb  mov     edx, r8d
0x14000d9ce  jmp     short loc_14000D9E0
0x14000d9d0  mov     rax, r14
0x14000d9d3  inc     rax
0x14000d9d6  cmp     [rcx+rax], r12b
0x14000d9da  jnz     short loc_14000D9D3
0x14000d9dc  lea     rdx, [rax+1]
0x14000d9e0  mov     rcx, [r15+80h]
0x14000d9e7  test    rcx, rcx
0x14000d9ea  jz      short loc_14000D9FC
0x14000d9ec  mov     rax, r14
0x14000d9ef  inc     rax
0x14000d9f2  cmp     [rcx+rax], r12b
0x14000d9f6  jnz     short loc_14000D9EF
0x14000d9f8  lea     r8, [rax+1]; unsigned __int64
0x14000d9fc  mov     rcx, [r15+18h]
0x14000da00  test    rcx, rcx
0x14000da03  jnz     short loc_14000DA0A
0x14000da05  lea     eax, [rcx+2]
0x14000da08  jmp     short loc_14000DA1F
0x14000da0a  mov     rax, r14
0x14000da0d  inc     rax
0x14000da10  cmp     [rcx+rax*2], r12w
0x14000da15  jnz     short loc_14000DA0D
0x14000da17  lea     rax, ds:2[rax*2]
0x14000da1f  lea     rbp, [r8+rax]
0x14000da23  add     rbp, rdx
0x14000da26  cmp     [rsi+rdi+40h], r12
0x14000da2b  jz      short loc_14000DA34
0x14000da2d  cmp     [rsi+rdi+48h], rbp
0x14000da32  jnb     short loc_14000DA76
0x14000da34  mov     rdx, rbp; dwBytes
0x14000da37  mov     ecx, 8; dwFlags
0x14000da3c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000da41  mov     r12, rax
0x14000da44  test    rax, rax
0x14000da47  jz      short loc_14000DA73
0x14000da49  mov     rbx, [rsi+rdi+40h]
0x14000da4e  call    cs:__imp_GetProcessHeap
0x14000da54  mov     r8, rbx; lpMem
0x14000da57  xor     edx, edx; dwFlags
0x14000da59  mov     rcx, rax; hHeap
0x14000da5c  call    cs:__imp_HeapFree
0x14000da62  lea     rbx, [rdi+20h]
0x14000da66  mov     [rsi+rdi+40h], r12
0x14000da6b  add     rbx, rsi
0x14000da6e  mov     [rsi+rdi+48h], rbp
0x14000da73  xor     r12d, r12d
0x14000da76  mov     rcx, [rsi+rdi+40h]
0x14000da7b  test    rcx, rcx
0x14000da7e  jz      loc_14000DB10
0x14000da84  mov     rbp, [rsi+rdi+48h]
0x14000da89  lea     r9, [r13+10h]
0x14000da8d  mov     r8, [r15+38h]
0x14000da91  add     rbp, rcx
0x14000da94  mov     rdx, rbp
0x14000da97  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000da9c  mov     r8, [r15+80h]
0x14000daa3  mov     r9, rbx
0x14000daa6  mov     rdx, rbp
0x14000daa9  mov     rcx, rax
0x14000daac  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000dab1  mov     rbx, rax
0x14000dab4  cmp     rax, rbp
0x14000dab7  jz      short loc_14000DAFB
0x14000dab9  mov     r8, [r15+18h]; Source
0x14000dabd  test    r8, r8
0x14000dac0  jz      short loc_14000DAFB
0x14000dac2  cmp     [r8], r12w
0x14000dac6  jz      short loc_14000DAFB
0x14000dac8  inc     r14
0x14000dacb  cmp     [r8+r14*2], r12w
0x14000dad0  jnz     short loc_14000DAC8
0x14000dad2  mov     rdx, rbp
0x14000dad5  lea     r14, ds:2[r14*2]
0x14000dadd  sub     rdx, rbx; DestinationSize
0x14000dae0  cmp     rdx, r14
0x14000dae3  jb      short loc_14000DAFB
0x14000dae5  mov     r9, r14; SourceSize
0x14000dae8  mov     rcx, rbx; Destination
0x14000daeb  call    cs:__imp_memcpy_s
0x14000daf1  mov     [rsi+rdi+38h], rbx
0x14000daf6  add     rbx, r14
0x14000daf9  jmp     short loc_14000DB00
0x14000dafb  mov     [rsi+rdi+38h], r12
0x14000db00  sub     rbp, rbx
0x14000db03  xor     edx, edx; Val
0x14000db05  mov     r8, rbp; Size
0x14000db08  mov     rcx, rbx; void *
0x14000db0b  call    memset_0
0x14000db10  add     rsp, 28h
0x14000db14  pop     r15
0x14000db16  pop     r14
0x14000db18  pop     r13
0x14000db1a  pop     r12
0x14000db1c  pop     rdi
0x14000db1d  pop     rsi
0x14000db1e  pop     rbp
0x14000db1f  pop     rbx
0x14000db20  retn
```
