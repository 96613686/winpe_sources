# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180019808`
- end: `0x180019a99`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018470`

## callees

- `0x180001fd4`
- `0x180006698`
- `0x180017c3c`
- `0x180018eb4`
- `0x180019808`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800199ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800199ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800199ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800199ce`

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
0x180019808  push    rbx
0x18001980a  push    rbp
0x18001980b  push    rsi
0x18001980c  push    rdi
0x18001980d  push    r12
0x18001980f  push    r13
0x180019811  push    r14
0x180019813  push    r15
0x180019815  sub     rsp, 28h
0x180019819  mov     esi, [rcx+10h]
0x18001981c  xor     r12d, r12d
0x18001981f  mov     r15, rdx
0x180019822  mov     rbx, rcx
0x180019825  mov     ebp, 50h ; 'P'
0x18001982a  cmp     [rcx+18h], r12
0x18001982e  jnz     short loc_180019865
0x180019830  test    esi, esi
0x180019832  jz      short loc_180019865
0x180019834  mov     edx, 190h; dwBytes
0x180019839  lea     ecx, [rbp-48h]; dwFlags
0x18001983c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019841  mov     [rbx+18h], rax
0x180019845  test    rax, rax
0x180019848  jz      short loc_180019865
0x18001984a  mov     dword ptr [rbx+20h], 5
0x180019851  lea     rcx, [rax+190h]
0x180019858  jmp     short loc_180019860
0x18001985a  mov     [rax], bp
0x18001985d  add     rax, rbp
0x180019860  cmp     rax, rcx
0x180019863  jnz     short loc_18001985A
0x180019865  mov     rdi, [rbx+18h]
0x180019869  test    rdi, rdi
0x18001986c  jz      loc_180019A87
0x180019872  test    esi, esi
0x180019874  jz      short loc_1800198AC
0x180019876  movzx   eax, word ptr [rbx+20h]
0x18001987a  mov     rcx, rdi
0x18001987d  lea     rdx, [rax+rax*4]
0x180019881  shl     rdx, 4
0x180019885  add     rdx, rdi
0x180019888  cmp     rdi, rdx
0x18001988b  jz      short loc_1800198AC
0x18001988d  mov     r8d, [rbx+10h]
0x180019891  cmp     [rcx+4], r8d
0x180019895  jbe     short loc_1800198A4
0x180019897  mov     eax, [r15+8]
0x18001989b  cmp     [rcx+8], eax
0x18001989e  jz      loc_180019A87
0x1800198a4  add     rcx, rbp
0x1800198a7  cmp     rcx, rdx
0x1800198aa  jnz     short loc_180019891
0x1800198ac  movzx   eax, word ptr [rbx+22h]
0x1800198b0  mov     r8d, 1
0x1800198b6  movzx   ecx, word ptr [rbx+20h]
0x1800198ba  add     eax, r8d
0x1800198bd  xor     edx, edx
0x1800198bf  div     ecx
0x1800198c1  mov     ecx, r8d
0x1800198c4  movzx   eax, dx
0x1800198c7  mov     [rbx+22h], dx
0x1800198cb  lea     rsi, [rax+rax*4]
0x1800198cf  mov     rax, [rbx+8]
0x1800198d3  shl     rsi, 4
0x1800198d7  lock xadd [rax], ecx
0x1800198db  add     ecx, r8d
0x1800198de  lea     r13, [rsi+rdi]
0x1800198e2  mov     [rsi+rdi+4], ecx
0x1800198e6  lea     rbx, [rdi+20h]
0x1800198ea  mov     eax, [r15+8]
0x1800198ee  add     rbx, rsi
0x1800198f1  mov     [rsi+rdi+8], eax
0x1800198f5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800198f9  mov     [r13+10h], r12
0x1800198fd  movzx   eax, word ptr [r15+40h]
0x180019902  mov     [rsi+rdi+18h], ax
0x180019907  mov     al, [r15]
0x18001990a  mov     [rsi+rdi+1Ah], al
0x18001990e  mov     [rbx], r12
0x180019911  mov     rax, [r15+88h]
0x180019918  mov     [rsi+rdi+28h], rax
0x18001991d  mov     rax, [r15+90h]
0x180019924  mov     [rsi+rdi+30h], rax
0x180019929  mov     [rsi+rdi+38h], r12
0x18001992e  mov     rcx, [r15+38h]
0x180019932  test    rcx, rcx
0x180019935  jnz     short loc_18001993C
0x180019937  mov     edx, r8d
0x18001993a  jmp     short loc_18001994C
0x18001993c  mov     rax, r14
0x18001993f  inc     rax
0x180019942  cmp     [rcx+rax], r12b
0x180019946  jnz     short loc_18001993F
0x180019948  lea     rdx, [rax+1]
0x18001994c  mov     rcx, [r15+80h]
0x180019953  test    rcx, rcx
0x180019956  jz      short loc_180019968
0x180019958  mov     rax, r14
0x18001995b  inc     rax
0x18001995e  cmp     [rcx+rax], r12b
0x180019962  jnz     short loc_18001995B
0x180019964  lea     r8, [rax+1]; unsigned __int64
0x180019968  mov     rcx, [r15+18h]
0x18001996c  test    rcx, rcx
0x18001996f  jnz     short loc_180019976
0x180019971  lea     eax, [rcx+2]
0x180019974  jmp     short loc_18001998B
0x180019976  mov     rax, r14
0x180019979  inc     rax
0x18001997c  cmp     [rcx+rax*2], r12w
0x180019981  jnz     short loc_180019979
0x180019983  lea     rax, ds:2[rax*2]
0x18001998b  lea     rbp, [r8+rax]
0x18001998f  add     rbp, rdx
0x180019992  cmp     [rsi+rdi+40h], r12
0x180019997  jz      short loc_1800199A0
0x180019999  cmp     [rsi+rdi+48h], rbp
0x18001999e  jnb     short loc_1800199EE
0x1800199a0  mov     rdx, rbp; dwBytes
0x1800199a3  mov     ecx, 8; dwFlags
0x1800199a8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800199ad  mov     r12, rax
0x1800199b0  test    rax, rax
0x1800199b3  jz      short loc_1800199EB
0x1800199b5  mov     rbx, [rsi+rdi+40h]
0x1800199ba  call    cs:__imp_GetProcessHeap
0x1800199c1  nop     dword ptr [rax+rax+00h]
0x1800199c6  mov     r8, rbx; lpMem
0x1800199c9  xor     edx, edx; dwFlags
0x1800199cb  mov     rcx, rax; hHeap
0x1800199ce  call    cs:__imp_HeapFree
0x1800199d5  nop     dword ptr [rax+rax+00h]
0x1800199da  lea     rbx, [rdi+20h]
0x1800199de  mov     [rsi+rdi+40h], r12
0x1800199e3  add     rbx, rsi
0x1800199e6  mov     [rsi+rdi+48h], rbp
0x1800199eb  xor     r12d, r12d
0x1800199ee  mov     rcx, [rsi+rdi+40h]
0x1800199f3  test    rcx, rcx
0x1800199f6  jz      loc_180019A87
0x1800199fc  mov     rbp, [rsi+rdi+48h]
0x180019a01  lea     r9, [r13+10h]
0x180019a05  mov     r8, [r15+38h]
0x180019a09  add     rbp, rcx
0x180019a0c  mov     rdx, rbp
0x180019a0f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180019a14  mov     r8, [r15+80h]
0x180019a1b  mov     r9, rbx
0x180019a1e  mov     rdx, rbp
0x180019a21  mov     rcx, rax
0x180019a24  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180019a29  mov     rbx, rax
0x180019a2c  cmp     rax, rbp
0x180019a2f  jz      short loc_180019A72
0x180019a31  mov     r8, [r15+18h]; Source
0x180019a35  test    r8, r8
0x180019a38  jz      short loc_180019A72
0x180019a3a  cmp     [r8], r12w
0x180019a3e  jz      short loc_180019A72
0x180019a40  inc     r14
0x180019a43  cmp     [r8+r14*2], r12w
0x180019a48  jnz     short loc_180019A40
0x180019a4a  mov     rdx, rbp
0x180019a4d  lea     r14, ds:2[r14*2]
0x180019a55  sub     rdx, rbx; DestinationSize
0x180019a58  cmp     rdx, r14
0x180019a5b  jb      short loc_180019A72
0x180019a5d  mov     r9, r14; SourceSize
0x180019a60  mov     rcx, rbx; Destination
0x180019a63  call    memcpy_s
0x180019a68  mov     [rsi+rdi+38h], rbx
0x180019a6d  add     rbx, r14
0x180019a70  jmp     short loc_180019A77
0x180019a72  mov     [rsi+rdi+38h], r12
0x180019a77  sub     rbp, rbx
0x180019a7a  xor     edx, edx; Val
0x180019a7c  mov     r8, rbp; Size
0x180019a7f  mov     rcx, rbx; void *
0x180019a82  call    memset_0
0x180019a87  add     rsp, 28h
0x180019a8b  pop     r15
0x180019a8d  pop     r14
0x180019a8f  pop     r13
0x180019a91  pop     r12
0x180019a93  pop     rdi
0x180019a94  pop     rsi
0x180019a95  pop     rbp
0x180019a96  pop     rbx
0x180019a97  retn
```
