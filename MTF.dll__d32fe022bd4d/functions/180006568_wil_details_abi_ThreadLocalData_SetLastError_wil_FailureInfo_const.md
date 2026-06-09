# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006568`
- end: `0x1800067ed`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004810`

## callees

- `0x180003a38`
- `0x18000599c`
- `0x180006568`
- `0x18002bc62`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800067b7`
- `msvcrt!memcpy_s` at `0x1800067b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000671a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000671a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006728`

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
0x180006568  push    rbx
0x18000656a  push    rbp
0x18000656b  push    rsi
0x18000656c  push    rdi
0x18000656d  push    r12
0x18000656f  push    r13
0x180006571  push    r14
0x180006573  push    r15
0x180006575  sub     rsp, 28h
0x180006579  mov     esi, [rcx+10h]
0x18000657c  xor     r12d, r12d
0x18000657f  mov     r15, rdx
0x180006582  mov     rbx, rcx
0x180006585  mov     ebp, 50h ; 'P'
0x18000658a  cmp     [rcx+18h], r12
0x18000658e  jnz     short loc_1800065C5
0x180006590  test    esi, esi
0x180006592  jz      short loc_1800065C5
0x180006594  mov     edx, 190h; dwBytes
0x180006599  lea     ecx, [rbp-48h]; dwFlags
0x18000659c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800065a1  mov     [rbx+18h], rax
0x1800065a5  test    rax, rax
0x1800065a8  jz      short loc_1800065C5
0x1800065aa  mov     dword ptr [rbx+20h], 5
0x1800065b1  lea     rcx, [rax+190h]
0x1800065b8  jmp     short loc_1800065C0
0x1800065ba  mov     [rax], bp
0x1800065bd  add     rax, rbp
0x1800065c0  cmp     rax, rcx
0x1800065c3  jnz     short loc_1800065BA
0x1800065c5  mov     rdi, [rbx+18h]
0x1800065c9  test    rdi, rdi
0x1800065cc  jz      loc_1800067DC
0x1800065d2  test    esi, esi
0x1800065d4  jz      short loc_18000660C
0x1800065d6  movzx   eax, word ptr [rbx+20h]
0x1800065da  mov     rcx, rdi
0x1800065dd  lea     rdx, [rax+rax*4]
0x1800065e1  shl     rdx, 4
0x1800065e5  add     rdx, rdi
0x1800065e8  cmp     rdi, rdx
0x1800065eb  jz      short loc_18000660C
0x1800065ed  mov     r8d, [rbx+10h]
0x1800065f1  cmp     [rcx+4], r8d
0x1800065f5  jbe     short loc_180006604
0x1800065f7  mov     eax, [r15+8]
0x1800065fb  cmp     [rcx+8], eax
0x1800065fe  jz      loc_1800067DC
0x180006604  add     rcx, rbp
0x180006607  cmp     rcx, rdx
0x18000660a  jnz     short loc_1800065F1
0x18000660c  movzx   eax, word ptr [rbx+22h]
0x180006610  mov     r8d, 1
0x180006616  movzx   ecx, word ptr [rbx+20h]
0x18000661a  add     eax, r8d
0x18000661d  xor     edx, edx
0x18000661f  div     ecx
0x180006621  mov     ecx, r8d
0x180006624  movzx   eax, dx
0x180006627  mov     [rbx+22h], dx
0x18000662b  lea     rsi, [rax+rax*4]
0x18000662f  mov     rax, [rbx+8]
0x180006633  shl     rsi, 4
0x180006637  lock xadd [rax], ecx
0x18000663b  add     ecx, r8d
0x18000663e  lea     r13, [rsi+rdi]
0x180006642  mov     [rsi+rdi+4], ecx
0x180006646  lea     rbx, [rdi+20h]
0x18000664a  mov     eax, [r15+8]
0x18000664e  add     rbx, rsi
0x180006651  mov     [rsi+rdi+8], eax
0x180006655  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006659  mov     [r13+10h], r12
0x18000665d  movzx   eax, word ptr [r15+40h]
0x180006662  mov     [rsi+rdi+18h], ax
0x180006667  mov     al, [r15]
0x18000666a  mov     [rsi+rdi+1Ah], al
0x18000666e  mov     [rbx], r12
0x180006671  mov     rax, [r15+88h]
0x180006678  mov     [rsi+rdi+28h], rax
0x18000667d  mov     rax, [r15+90h]
0x180006684  mov     [rsi+rdi+30h], rax
0x180006689  mov     [rsi+rdi+38h], r12
0x18000668e  mov     rcx, [r15+38h]
0x180006692  test    rcx, rcx
0x180006695  jnz     short loc_18000669C
0x180006697  mov     edx, r8d
0x18000669a  jmp     short loc_1800066AC
0x18000669c  mov     rax, r14
0x18000669f  inc     rax
0x1800066a2  cmp     [rcx+rax], r12b
0x1800066a6  jnz     short loc_18000669F
0x1800066a8  lea     rdx, [rax+1]
0x1800066ac  mov     rcx, [r15+80h]
0x1800066b3  test    rcx, rcx
0x1800066b6  jz      short loc_1800066C8
0x1800066b8  mov     rax, r14
0x1800066bb  inc     rax
0x1800066be  cmp     [rcx+rax], r12b
0x1800066c2  jnz     short loc_1800066BB
0x1800066c4  lea     r8, [rax+1]; unsigned __int64
0x1800066c8  mov     rcx, [r15+18h]
0x1800066cc  test    rcx, rcx
0x1800066cf  jnz     short loc_1800066D6
0x1800066d1  lea     eax, [rcx+2]
0x1800066d4  jmp     short loc_1800066EB
0x1800066d6  mov     rax, r14
0x1800066d9  inc     rax
0x1800066dc  cmp     [rcx+rax*2], r12w
0x1800066e1  jnz     short loc_1800066D9
0x1800066e3  lea     rax, ds:2[rax*2]
0x1800066eb  lea     rbp, [r8+rax]
0x1800066ef  add     rbp, rdx
0x1800066f2  cmp     [rsi+rdi+40h], r12
0x1800066f7  jz      short loc_180006700
0x1800066f9  cmp     [rsi+rdi+48h], rbp
0x1800066fe  jnb     short loc_180006742
0x180006700  mov     rdx, rbp; dwBytes
0x180006703  mov     ecx, 8; dwFlags
0x180006708  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000670d  mov     r12, rax
0x180006710  test    rax, rax
0x180006713  jz      short loc_18000673F
0x180006715  mov     rbx, [rsi+rdi+40h]
0x18000671a  call    cs:__imp_GetProcessHeap
0x180006720  mov     r8, rbx; lpMem
0x180006723  xor     edx, edx; dwFlags
0x180006725  mov     rcx, rax; hHeap
0x180006728  call    cs:__imp_HeapFree
0x18000672e  lea     rbx, [rdi+20h]
0x180006732  mov     [rsi+rdi+40h], r12
0x180006737  add     rbx, rsi
0x18000673a  mov     [rsi+rdi+48h], rbp
0x18000673f  xor     r12d, r12d
0x180006742  mov     rcx, [rsi+rdi+40h]
0x180006747  test    rcx, rcx
0x18000674a  jz      loc_1800067DC
0x180006750  mov     rbp, [rsi+rdi+48h]
0x180006755  lea     r9, [r13+10h]
0x180006759  mov     r8, [r15+38h]
0x18000675d  add     rbp, rcx
0x180006760  mov     rdx, rbp
0x180006763  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006768  mov     r8, [r15+80h]
0x18000676f  mov     r9, rbx
0x180006772  mov     rdx, rbp
0x180006775  mov     rcx, rax
0x180006778  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000677d  mov     rbx, rax
0x180006780  cmp     rax, rbp
0x180006783  jz      short loc_1800067C7
0x180006785  mov     r8, [r15+18h]; Source
0x180006789  test    r8, r8
0x18000678c  jz      short loc_1800067C7
0x18000678e  cmp     [r8], r12w
0x180006792  jz      short loc_1800067C7
0x180006794  inc     r14
0x180006797  cmp     [r8+r14*2], r12w
0x18000679c  jnz     short loc_180006794
0x18000679e  mov     rdx, rbp
0x1800067a1  lea     r14, ds:2[r14*2]
0x1800067a9  sub     rdx, rbx; DestinationSize
0x1800067ac  cmp     rdx, r14
0x1800067af  jb      short loc_1800067C7
0x1800067b1  mov     r9, r14; SourceSize
0x1800067b4  mov     rcx, rbx; Destination
0x1800067b7  call    cs:__imp_memcpy_s
0x1800067bd  mov     [rsi+rdi+38h], rbx
0x1800067c2  add     rbx, r14
0x1800067c5  jmp     short loc_1800067CC
0x1800067c7  mov     [rsi+rdi+38h], r12
0x1800067cc  sub     rbp, rbx
0x1800067cf  xor     edx, edx; Val
0x1800067d1  mov     r8, rbp; Size
0x1800067d4  mov     rcx, rbx; void *
0x1800067d7  call    memset_0
0x1800067dc  add     rsp, 28h
0x1800067e0  pop     r15
0x1800067e2  pop     r14
0x1800067e4  pop     r13
0x1800067e6  pop     r12
0x1800067e8  pop     rdi
0x1800067e9  pop     rsi
0x1800067ea  pop     rbp
0x1800067eb  pop     rbx
0x1800067ec  retn
```
