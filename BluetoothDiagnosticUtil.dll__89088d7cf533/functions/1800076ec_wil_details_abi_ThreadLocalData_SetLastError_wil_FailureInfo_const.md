# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800076ec`
- end: `0x180007984`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005160`

## callees

- `0x180003348`
- `0x1800067a4`
- `0x1800076ec`
- `0x180009c5e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007947`
- `msvcrt!memcpy_s` at `0x180007947`
- `KERNEL32!HeapFree` at `0x1800078b2`
- `KERNEL32!HeapFree` at `0x1800078b2`
- `KERNEL32!GetProcessHeap` at `0x18000789e`
- `KERNEL32!GetProcessHeap` at `0x18000789e`

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
0x1800076ec  push    rbx
0x1800076ee  push    rbp
0x1800076ef  push    rsi
0x1800076f0  push    rdi
0x1800076f1  push    r12
0x1800076f3  push    r13
0x1800076f5  push    r14
0x1800076f7  push    r15
0x1800076f9  sub     rsp, 28h
0x1800076fd  mov     esi, [rcx+10h]
0x180007700  xor     r12d, r12d
0x180007703  mov     r15, rdx
0x180007706  mov     rbx, rcx
0x180007709  mov     ebp, 50h ; 'P'
0x18000770e  cmp     [rcx+18h], r12
0x180007712  jnz     short loc_180007749
0x180007714  test    esi, esi
0x180007716  jz      short loc_180007749
0x180007718  mov     edx, 190h; dwBytes
0x18000771d  lea     ecx, [rbp-48h]; dwFlags
0x180007720  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007725  mov     [rbx+18h], rax
0x180007729  test    rax, rax
0x18000772c  jz      short loc_180007749
0x18000772e  mov     dword ptr [rbx+20h], 5
0x180007735  lea     rcx, [rax+190h]
0x18000773c  jmp     short loc_180007744
0x18000773e  mov     [rax], bp
0x180007741  add     rax, rbp
0x180007744  cmp     rax, rcx
0x180007747  jnz     short loc_18000773E
0x180007749  mov     rdi, [rbx+18h]
0x18000774d  test    rdi, rdi
0x180007750  jz      loc_180007972
0x180007756  test    esi, esi
0x180007758  jz      short loc_180007790
0x18000775a  movzx   eax, word ptr [rbx+20h]
0x18000775e  mov     rcx, rdi
0x180007761  lea     rdx, [rax+rax*4]
0x180007765  shl     rdx, 4
0x180007769  add     rdx, rdi
0x18000776c  cmp     rdi, rdx
0x18000776f  jz      short loc_180007790
0x180007771  mov     r8d, [rbx+10h]
0x180007775  cmp     [rcx+4], r8d
0x180007779  jbe     short loc_180007788
0x18000777b  mov     eax, [r15+8]
0x18000777f  cmp     [rcx+8], eax
0x180007782  jz      loc_180007972
0x180007788  add     rcx, rbp
0x18000778b  cmp     rcx, rdx
0x18000778e  jnz     short loc_180007775
0x180007790  movzx   eax, word ptr [rbx+22h]
0x180007794  mov     r8d, 1
0x18000779a  movzx   ecx, word ptr [rbx+20h]
0x18000779e  add     eax, r8d
0x1800077a1  xor     edx, edx
0x1800077a3  div     ecx
0x1800077a5  mov     ecx, r8d
0x1800077a8  movzx   eax, dx
0x1800077ab  mov     [rbx+22h], dx
0x1800077af  lea     rsi, [rax+rax*4]
0x1800077b3  mov     rax, [rbx+8]
0x1800077b7  shl     rsi, 4
0x1800077bb  lock xadd [rax], ecx
0x1800077bf  add     ecx, r8d
0x1800077c2  lea     r13, [rsi+rdi]
0x1800077c6  mov     [rsi+rdi+4], ecx
0x1800077ca  lea     rbx, [rdi+20h]
0x1800077ce  mov     eax, [r15+8]
0x1800077d2  add     rbx, rsi
0x1800077d5  mov     [rsi+rdi+8], eax
0x1800077d9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800077dd  mov     [r13+10h], r12
0x1800077e1  movzx   eax, word ptr [r15+40h]
0x1800077e6  mov     [rsi+rdi+18h], ax
0x1800077eb  mov     al, [r15]
0x1800077ee  mov     [rsi+rdi+1Ah], al
0x1800077f2  mov     [rbx], r12
0x1800077f5  mov     rax, [r15+88h]
0x1800077fc  mov     [rsi+rdi+28h], rax
0x180007801  mov     rax, [r15+90h]
0x180007808  mov     [rsi+rdi+30h], rax
0x18000780d  mov     [rsi+rdi+38h], r12
0x180007812  mov     rcx, [r15+38h]
0x180007816  test    rcx, rcx
0x180007819  jnz     short loc_180007820
0x18000781b  mov     edx, r8d
0x18000781e  jmp     short loc_180007830
0x180007820  mov     rax, r14
0x180007823  inc     rax
0x180007826  cmp     [rcx+rax], r12b
0x18000782a  jnz     short loc_180007823
0x18000782c  lea     rdx, [rax+1]
0x180007830  mov     rcx, [r15+80h]
0x180007837  test    rcx, rcx
0x18000783a  jz      short loc_18000784C
0x18000783c  mov     rax, r14
0x18000783f  inc     rax
0x180007842  cmp     [rcx+rax], r12b
0x180007846  jnz     short loc_18000783F
0x180007848  lea     r8, [rax+1]; unsigned __int64
0x18000784c  mov     rcx, [r15+18h]
0x180007850  test    rcx, rcx
0x180007853  jnz     short loc_18000785A
0x180007855  lea     eax, [rcx+2]
0x180007858  jmp     short loc_18000786F
0x18000785a  mov     rax, r14
0x18000785d  inc     rax
0x180007860  cmp     [rcx+rax*2], r12w
0x180007865  jnz     short loc_18000785D
0x180007867  lea     rax, ds:2[rax*2]
0x18000786f  lea     rbp, [r8+rax]
0x180007873  add     rbp, rdx
0x180007876  cmp     [rsi+rdi+40h], r12
0x18000787b  jz      short loc_180007884
0x18000787d  cmp     [rsi+rdi+48h], rbp
0x180007882  jnb     short loc_1800078D2
0x180007884  mov     rdx, rbp; dwBytes
0x180007887  mov     ecx, 8; dwFlags
0x18000788c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007891  mov     r12, rax
0x180007894  test    rax, rax
0x180007897  jz      short loc_1800078CF
0x180007899  mov     rbx, [rsi+rdi+40h]
0x18000789e  call    cs:__imp_GetProcessHeap
0x1800078a5  nop     dword ptr [rax+rax+00h]
0x1800078aa  mov     r8, rbx; lpMem
0x1800078ad  xor     edx, edx; dwFlags
0x1800078af  mov     rcx, rax; hHeap
0x1800078b2  call    cs:__imp_HeapFree
0x1800078b9  nop     dword ptr [rax+rax+00h]
0x1800078be  lea     rbx, [rdi+20h]
0x1800078c2  mov     [rsi+rdi+40h], r12
0x1800078c7  add     rbx, rsi
0x1800078ca  mov     [rsi+rdi+48h], rbp
0x1800078cf  xor     r12d, r12d
0x1800078d2  mov     rcx, [rsi+rdi+40h]
0x1800078d7  test    rcx, rcx
0x1800078da  jz      loc_180007972
0x1800078e0  mov     rbp, [rsi+rdi+48h]
0x1800078e5  lea     r9, [r13+10h]
0x1800078e9  mov     r8, [r15+38h]
0x1800078ed  add     rbp, rcx
0x1800078f0  mov     rdx, rbp
0x1800078f3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800078f8  mov     r8, [r15+80h]
0x1800078ff  mov     r9, rbx
0x180007902  mov     rdx, rbp
0x180007905  mov     rcx, rax
0x180007908  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000790d  mov     rbx, rax
0x180007910  cmp     rax, rbp
0x180007913  jz      short loc_18000795D
0x180007915  mov     r8, [r15+18h]; Source
0x180007919  test    r8, r8
0x18000791c  jz      short loc_18000795D
0x18000791e  cmp     [r8], r12w
0x180007922  jz      short loc_18000795D
0x180007924  inc     r14
0x180007927  cmp     [r8+r14*2], r12w
0x18000792c  jnz     short loc_180007924
0x18000792e  mov     rdx, rbp
0x180007931  lea     r14, ds:2[r14*2]
0x180007939  sub     rdx, rbx; DestinationSize
0x18000793c  cmp     rdx, r14
0x18000793f  jb      short loc_18000795D
0x180007941  mov     r9, r14; SourceSize
0x180007944  mov     rcx, rbx; Destination
0x180007947  call    cs:__imp_memcpy_s
0x18000794e  nop     dword ptr [rax+rax+00h]
0x180007953  mov     [rsi+rdi+38h], rbx
0x180007958  add     rbx, r14
0x18000795b  jmp     short loc_180007962
0x18000795d  mov     [rsi+rdi+38h], r12
0x180007962  sub     rbp, rbx
0x180007965  xor     edx, edx; Val
0x180007967  mov     r8, rbp; Size
0x18000796a  mov     rcx, rbx; void *
0x18000796d  call    memset_0
0x180007972  add     rsp, 28h
0x180007976  pop     r15
0x180007978  pop     r14
0x18000797a  pop     r13
0x18000797c  pop     r12
0x18000797e  pop     rdi
0x18000797f  pop     rsi
0x180007980  pop     rbp
0x180007981  pop     rbx
0x180007982  retn
```
