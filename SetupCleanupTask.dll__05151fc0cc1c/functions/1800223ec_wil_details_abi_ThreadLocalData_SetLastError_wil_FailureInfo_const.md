# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800223ec`
- end: `0x180022671`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b7a0`

## callees

- `0x180018c6c`
- `0x18001f350`
- `0x1800223ec`
- `0x1800322d2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002263b`
- `msvcrt!memcpy_s` at `0x18002263b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002259e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002259e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225ac`

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
0x1800223ec  push    rbx
0x1800223ee  push    rbp
0x1800223ef  push    rsi
0x1800223f0  push    rdi
0x1800223f1  push    r12
0x1800223f3  push    r13
0x1800223f5  push    r14
0x1800223f7  push    r15
0x1800223f9  sub     rsp, 28h
0x1800223fd  mov     esi, [rcx+10h]
0x180022400  xor     r12d, r12d
0x180022403  mov     r15, rdx
0x180022406  mov     rbx, rcx
0x180022409  mov     ebp, 50h ; 'P'
0x18002240e  cmp     [rcx+18h], r12
0x180022412  jnz     short loc_180022449
0x180022414  test    esi, esi
0x180022416  jz      short loc_180022449
0x180022418  mov     edx, 190h; dwBytes
0x18002241d  lea     ecx, [rbp-48h]; dwFlags
0x180022420  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180022425  mov     [rbx+18h], rax
0x180022429  test    rax, rax
0x18002242c  jz      short loc_180022449
0x18002242e  mov     dword ptr [rbx+20h], 5
0x180022435  lea     rcx, [rax+190h]
0x18002243c  jmp     short loc_180022444
0x18002243e  mov     [rax], bp
0x180022441  add     rax, rbp
0x180022444  cmp     rax, rcx
0x180022447  jnz     short loc_18002243E
0x180022449  mov     rdi, [rbx+18h]
0x18002244d  test    rdi, rdi
0x180022450  jz      loc_180022660
0x180022456  test    esi, esi
0x180022458  jz      short loc_180022490
0x18002245a  movzx   eax, word ptr [rbx+20h]
0x18002245e  mov     rcx, rdi
0x180022461  lea     rdx, [rax+rax*4]
0x180022465  shl     rdx, 4
0x180022469  add     rdx, rdi
0x18002246c  cmp     rdi, rdx
0x18002246f  jz      short loc_180022490
0x180022471  mov     r8d, [rbx+10h]
0x180022475  cmp     [rcx+4], r8d
0x180022479  jbe     short loc_180022488
0x18002247b  mov     eax, [r15+8]
0x18002247f  cmp     [rcx+8], eax
0x180022482  jz      loc_180022660
0x180022488  add     rcx, rbp
0x18002248b  cmp     rcx, rdx
0x18002248e  jnz     short loc_180022475
0x180022490  movzx   eax, word ptr [rbx+22h]
0x180022494  mov     r8d, 1
0x18002249a  movzx   ecx, word ptr [rbx+20h]
0x18002249e  add     eax, r8d
0x1800224a1  xor     edx, edx
0x1800224a3  div     ecx
0x1800224a5  mov     ecx, r8d
0x1800224a8  movzx   eax, dx
0x1800224ab  mov     [rbx+22h], dx
0x1800224af  lea     rsi, [rax+rax*4]
0x1800224b3  mov     rax, [rbx+8]
0x1800224b7  shl     rsi, 4
0x1800224bb  lock xadd [rax], ecx
0x1800224bf  add     ecx, r8d
0x1800224c2  lea     r13, [rsi+rdi]
0x1800224c6  mov     [rsi+rdi+4], ecx
0x1800224ca  lea     rbx, [rdi+20h]
0x1800224ce  mov     eax, [r15+8]
0x1800224d2  add     rbx, rsi
0x1800224d5  mov     [rsi+rdi+8], eax
0x1800224d9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800224dd  mov     [r13+10h], r12
0x1800224e1  movzx   eax, word ptr [r15+40h]
0x1800224e6  mov     [rsi+rdi+18h], ax
0x1800224eb  mov     al, [r15]
0x1800224ee  mov     [rsi+rdi+1Ah], al
0x1800224f2  mov     [rbx], r12
0x1800224f5  mov     rax, [r15+88h]
0x1800224fc  mov     [rsi+rdi+28h], rax
0x180022501  mov     rax, [r15+90h]
0x180022508  mov     [rsi+rdi+30h], rax
0x18002250d  mov     [rsi+rdi+38h], r12
0x180022512  mov     rcx, [r15+38h]
0x180022516  test    rcx, rcx
0x180022519  jnz     short loc_180022520
0x18002251b  mov     edx, r8d
0x18002251e  jmp     short loc_180022530
0x180022520  mov     rax, r14
0x180022523  inc     rax
0x180022526  cmp     [rcx+rax], r12b
0x18002252a  jnz     short loc_180022523
0x18002252c  lea     rdx, [rax+1]
0x180022530  mov     rcx, [r15+80h]
0x180022537  test    rcx, rcx
0x18002253a  jz      short loc_18002254C
0x18002253c  mov     rax, r14
0x18002253f  inc     rax
0x180022542  cmp     [rcx+rax], r12b
0x180022546  jnz     short loc_18002253F
0x180022548  lea     r8, [rax+1]; unsigned __int64
0x18002254c  mov     rcx, [r15+18h]
0x180022550  test    rcx, rcx
0x180022553  jnz     short loc_18002255A
0x180022555  lea     eax, [rcx+2]
0x180022558  jmp     short loc_18002256F
0x18002255a  mov     rax, r14
0x18002255d  inc     rax
0x180022560  cmp     [rcx+rax*2], r12w
0x180022565  jnz     short loc_18002255D
0x180022567  lea     rax, ds:2[rax*2]
0x18002256f  lea     rbp, [r8+rax]
0x180022573  add     rbp, rdx
0x180022576  cmp     [rsi+rdi+40h], r12
0x18002257b  jz      short loc_180022584
0x18002257d  cmp     [rsi+rdi+48h], rbp
0x180022582  jnb     short loc_1800225C6
0x180022584  mov     rdx, rbp; dwBytes
0x180022587  mov     ecx, 8; dwFlags
0x18002258c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180022591  mov     r12, rax
0x180022594  test    rax, rax
0x180022597  jz      short loc_1800225C3
0x180022599  mov     rbx, [rsi+rdi+40h]
0x18002259e  call    cs:__imp_GetProcessHeap
0x1800225a4  mov     r8, rbx; lpMem
0x1800225a7  xor     edx, edx; dwFlags
0x1800225a9  mov     rcx, rax; hHeap
0x1800225ac  call    cs:__imp_HeapFree
0x1800225b2  lea     rbx, [rdi+20h]
0x1800225b6  mov     [rsi+rdi+40h], r12
0x1800225bb  add     rbx, rsi
0x1800225be  mov     [rsi+rdi+48h], rbp
0x1800225c3  xor     r12d, r12d
0x1800225c6  mov     rcx, [rsi+rdi+40h]
0x1800225cb  test    rcx, rcx
0x1800225ce  jz      loc_180022660
0x1800225d4  mov     rbp, [rsi+rdi+48h]
0x1800225d9  lea     r9, [r13+10h]
0x1800225dd  mov     r8, [r15+38h]
0x1800225e1  add     rbp, rcx
0x1800225e4  mov     rdx, rbp
0x1800225e7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800225ec  mov     r8, [r15+80h]
0x1800225f3  mov     r9, rbx
0x1800225f6  mov     rdx, rbp
0x1800225f9  mov     rcx, rax
0x1800225fc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180022601  mov     rbx, rax
0x180022604  cmp     rax, rbp
0x180022607  jz      short loc_18002264B
0x180022609  mov     r8, [r15+18h]; Source
0x18002260d  test    r8, r8
0x180022610  jz      short loc_18002264B
0x180022612  cmp     [r8], r12w
0x180022616  jz      short loc_18002264B
0x180022618  inc     r14
0x18002261b  cmp     [r8+r14*2], r12w
0x180022620  jnz     short loc_180022618
0x180022622  mov     rdx, rbp
0x180022625  lea     r14, ds:2[r14*2]
0x18002262d  sub     rdx, rbx; DestinationSize
0x180022630  cmp     rdx, r14
0x180022633  jb      short loc_18002264B
0x180022635  mov     r9, r14; SourceSize
0x180022638  mov     rcx, rbx; Destination
0x18002263b  call    cs:__imp_memcpy_s
0x180022641  mov     [rsi+rdi+38h], rbx
0x180022646  add     rbx, r14
0x180022649  jmp     short loc_180022650
0x18002264b  mov     [rsi+rdi+38h], r12
0x180022650  sub     rbp, rbx
0x180022653  xor     edx, edx; Val
0x180022655  mov     r8, rbp; Size
0x180022658  mov     rcx, rbx; void *
0x18002265b  call    memset_0
0x180022660  add     rsp, 28h
0x180022664  pop     r15
0x180022666  pop     r14
0x180022668  pop     r13
0x18002266a  pop     r12
0x18002266c  pop     rdi
0x18002266d  pop     rsi
0x18002266e  pop     rbp
0x18002266f  pop     rbx
0x180022670  retn
```
