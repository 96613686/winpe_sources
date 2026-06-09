# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800155a4`
- end: `0x18001583c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012640`

## callees

- `0x180010a60`
- `0x18001393c`
- `0x1800155a4`
- `0x18001899e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800157ff`
- `msvcrt!memcpy_s` at `0x1800157ff`
- `KERNEL32!HeapFree` at `0x18001576a`
- `KERNEL32!HeapFree` at `0x18001576a`
- `KERNEL32!GetProcessHeap` at `0x180015756`
- `KERNEL32!GetProcessHeap` at `0x180015756`

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
0x1800155a4  push    rbx
0x1800155a6  push    rbp
0x1800155a7  push    rsi
0x1800155a8  push    rdi
0x1800155a9  push    r12
0x1800155ab  push    r13
0x1800155ad  push    r14
0x1800155af  push    r15
0x1800155b1  sub     rsp, 28h
0x1800155b5  mov     esi, [rcx+10h]
0x1800155b8  xor     r12d, r12d
0x1800155bb  mov     r15, rdx
0x1800155be  mov     rbx, rcx
0x1800155c1  mov     ebp, 50h ; 'P'
0x1800155c6  cmp     [rcx+18h], r12
0x1800155ca  jnz     short loc_180015601
0x1800155cc  test    esi, esi
0x1800155ce  jz      short loc_180015601
0x1800155d0  mov     edx, 190h; dwBytes
0x1800155d5  lea     ecx, [rbp-48h]; dwFlags
0x1800155d8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800155dd  mov     [rbx+18h], rax
0x1800155e1  test    rax, rax
0x1800155e4  jz      short loc_180015601
0x1800155e6  mov     dword ptr [rbx+20h], 5
0x1800155ed  lea     rcx, [rax+190h]
0x1800155f4  jmp     short loc_1800155FC
0x1800155f6  mov     [rax], bp
0x1800155f9  add     rax, rbp
0x1800155fc  cmp     rax, rcx
0x1800155ff  jnz     short loc_1800155F6
0x180015601  mov     rdi, [rbx+18h]
0x180015605  test    rdi, rdi
0x180015608  jz      loc_18001582A
0x18001560e  test    esi, esi
0x180015610  jz      short loc_180015648
0x180015612  movzx   eax, word ptr [rbx+20h]
0x180015616  mov     rcx, rdi
0x180015619  lea     rdx, [rax+rax*4]
0x18001561d  shl     rdx, 4
0x180015621  add     rdx, rdi
0x180015624  cmp     rdi, rdx
0x180015627  jz      short loc_180015648
0x180015629  mov     r8d, [rbx+10h]
0x18001562d  cmp     [rcx+4], r8d
0x180015631  jbe     short loc_180015640
0x180015633  mov     eax, [r15+8]
0x180015637  cmp     [rcx+8], eax
0x18001563a  jz      loc_18001582A
0x180015640  add     rcx, rbp
0x180015643  cmp     rcx, rdx
0x180015646  jnz     short loc_18001562D
0x180015648  movzx   eax, word ptr [rbx+22h]
0x18001564c  mov     r8d, 1
0x180015652  movzx   ecx, word ptr [rbx+20h]
0x180015656  add     eax, r8d
0x180015659  xor     edx, edx
0x18001565b  div     ecx
0x18001565d  mov     ecx, r8d
0x180015660  movzx   eax, dx
0x180015663  mov     [rbx+22h], dx
0x180015667  lea     rsi, [rax+rax*4]
0x18001566b  mov     rax, [rbx+8]
0x18001566f  shl     rsi, 4
0x180015673  lock xadd [rax], ecx
0x180015677  add     ecx, r8d
0x18001567a  lea     r13, [rsi+rdi]
0x18001567e  mov     [rsi+rdi+4], ecx
0x180015682  lea     rbx, [rdi+20h]
0x180015686  mov     eax, [r15+8]
0x18001568a  add     rbx, rsi
0x18001568d  mov     [rsi+rdi+8], eax
0x180015691  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015695  mov     [r13+10h], r12
0x180015699  movzx   eax, word ptr [r15+40h]
0x18001569e  mov     [rsi+rdi+18h], ax
0x1800156a3  mov     al, [r15]
0x1800156a6  mov     [rsi+rdi+1Ah], al
0x1800156aa  mov     [rbx], r12
0x1800156ad  mov     rax, [r15+88h]
0x1800156b4  mov     [rsi+rdi+28h], rax
0x1800156b9  mov     rax, [r15+90h]
0x1800156c0  mov     [rsi+rdi+30h], rax
0x1800156c5  mov     [rsi+rdi+38h], r12
0x1800156ca  mov     rcx, [r15+38h]
0x1800156ce  test    rcx, rcx
0x1800156d1  jnz     short loc_1800156D8
0x1800156d3  mov     edx, r8d
0x1800156d6  jmp     short loc_1800156E8
0x1800156d8  mov     rax, r14
0x1800156db  inc     rax
0x1800156de  cmp     [rcx+rax], r12b
0x1800156e2  jnz     short loc_1800156DB
0x1800156e4  lea     rdx, [rax+1]
0x1800156e8  mov     rcx, [r15+80h]
0x1800156ef  test    rcx, rcx
0x1800156f2  jz      short loc_180015704
0x1800156f4  mov     rax, r14
0x1800156f7  inc     rax
0x1800156fa  cmp     [rcx+rax], r12b
0x1800156fe  jnz     short loc_1800156F7
0x180015700  lea     r8, [rax+1]; unsigned __int64
0x180015704  mov     rcx, [r15+18h]
0x180015708  test    rcx, rcx
0x18001570b  jnz     short loc_180015712
0x18001570d  lea     eax, [rcx+2]
0x180015710  jmp     short loc_180015727
0x180015712  mov     rax, r14
0x180015715  inc     rax
0x180015718  cmp     [rcx+rax*2], r12w
0x18001571d  jnz     short loc_180015715
0x18001571f  lea     rax, ds:2[rax*2]
0x180015727  lea     rbp, [r8+rax]
0x18001572b  add     rbp, rdx
0x18001572e  cmp     [rsi+rdi+40h], r12
0x180015733  jz      short loc_18001573C
0x180015735  cmp     [rsi+rdi+48h], rbp
0x18001573a  jnb     short loc_18001578A
0x18001573c  mov     rdx, rbp; dwBytes
0x18001573f  mov     ecx, 8; dwFlags
0x180015744  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015749  mov     r12, rax
0x18001574c  test    rax, rax
0x18001574f  jz      short loc_180015787
0x180015751  mov     rbx, [rsi+rdi+40h]
0x180015756  call    cs:__imp_GetProcessHeap
0x18001575d  nop     dword ptr [rax+rax+00h]
0x180015762  mov     r8, rbx; lpMem
0x180015765  xor     edx, edx; dwFlags
0x180015767  mov     rcx, rax; hHeap
0x18001576a  call    cs:__imp_HeapFree
0x180015771  nop     dword ptr [rax+rax+00h]
0x180015776  lea     rbx, [rdi+20h]
0x18001577a  mov     [rsi+rdi+40h], r12
0x18001577f  add     rbx, rsi
0x180015782  mov     [rsi+rdi+48h], rbp
0x180015787  xor     r12d, r12d
0x18001578a  mov     rcx, [rsi+rdi+40h]
0x18001578f  test    rcx, rcx
0x180015792  jz      loc_18001582A
0x180015798  mov     rbp, [rsi+rdi+48h]
0x18001579d  lea     r9, [r13+10h]
0x1800157a1  mov     r8, [r15+38h]
0x1800157a5  add     rbp, rcx
0x1800157a8  mov     rdx, rbp
0x1800157ab  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800157b0  mov     r8, [r15+80h]
0x1800157b7  mov     r9, rbx
0x1800157ba  mov     rdx, rbp
0x1800157bd  mov     rcx, rax
0x1800157c0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800157c5  mov     rbx, rax
0x1800157c8  cmp     rax, rbp
0x1800157cb  jz      short loc_180015815
0x1800157cd  mov     r8, [r15+18h]; Source
0x1800157d1  test    r8, r8
0x1800157d4  jz      short loc_180015815
0x1800157d6  cmp     [r8], r12w
0x1800157da  jz      short loc_180015815
0x1800157dc  inc     r14
0x1800157df  cmp     [r8+r14*2], r12w
0x1800157e4  jnz     short loc_1800157DC
0x1800157e6  mov     rdx, rbp
0x1800157e9  lea     r14, ds:2[r14*2]
0x1800157f1  sub     rdx, rbx; DestinationSize
0x1800157f4  cmp     rdx, r14
0x1800157f7  jb      short loc_180015815
0x1800157f9  mov     r9, r14; SourceSize
0x1800157fc  mov     rcx, rbx; Destination
0x1800157ff  call    cs:__imp_memcpy_s
0x180015806  nop     dword ptr [rax+rax+00h]
0x18001580b  mov     [rsi+rdi+38h], rbx
0x180015810  add     rbx, r14
0x180015813  jmp     short loc_18001581A
0x180015815  mov     [rsi+rdi+38h], r12
0x18001581a  sub     rbp, rbx
0x18001581d  xor     edx, edx; Val
0x18001581f  mov     r8, rbp; Size
0x180015822  mov     rcx, rbx; void *
0x180015825  call    memset_0
0x18001582a  add     rsp, 28h
0x18001582e  pop     r15
0x180015830  pop     r14
0x180015832  pop     r13
0x180015834  pop     r12
0x180015836  pop     rdi
0x180015837  pop     rsi
0x180015838  pop     rbp
0x180015839  pop     rbx
0x18001583a  retn
```
