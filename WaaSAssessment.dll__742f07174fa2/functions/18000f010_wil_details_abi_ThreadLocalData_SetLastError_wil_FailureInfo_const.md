# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000f010`
- end: `0x18000f295`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d890`

## callees

- `0x18000a188`
- `0x18000edc0`
- `0x18000f010`
- `0x18001972e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f25f`
- `msvcrt!memcpy_s` at `0x18000f25f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1d0`

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
0x18000f010  push    rbx
0x18000f012  push    rbp
0x18000f013  push    rsi
0x18000f014  push    rdi
0x18000f015  push    r12
0x18000f017  push    r13
0x18000f019  push    r14
0x18000f01b  push    r15
0x18000f01d  sub     rsp, 28h
0x18000f021  mov     esi, [rcx+10h]
0x18000f024  xor     r12d, r12d
0x18000f027  mov     r15, rdx
0x18000f02a  mov     rbx, rcx
0x18000f02d  mov     ebp, 50h ; 'P'
0x18000f032  cmp     [rcx+18h], r12
0x18000f036  jnz     short loc_18000F06D
0x18000f038  test    esi, esi
0x18000f03a  jz      short loc_18000F06D
0x18000f03c  mov     edx, 190h; dwBytes
0x18000f041  lea     ecx, [rbp-48h]; dwFlags
0x18000f044  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f049  mov     [rbx+18h], rax
0x18000f04d  test    rax, rax
0x18000f050  jz      short loc_18000F06D
0x18000f052  mov     dword ptr [rbx+20h], 5
0x18000f059  lea     rcx, [rax+190h]
0x18000f060  jmp     short loc_18000F068
0x18000f062  mov     [rax], bp
0x18000f065  add     rax, rbp
0x18000f068  cmp     rax, rcx
0x18000f06b  jnz     short loc_18000F062
0x18000f06d  mov     rdi, [rbx+18h]
0x18000f071  test    rdi, rdi
0x18000f074  jz      loc_18000F284
0x18000f07a  test    esi, esi
0x18000f07c  jz      short loc_18000F0B4
0x18000f07e  movzx   eax, word ptr [rbx+20h]
0x18000f082  mov     rcx, rdi
0x18000f085  lea     rdx, [rax+rax*4]
0x18000f089  shl     rdx, 4
0x18000f08d  add     rdx, rdi
0x18000f090  cmp     rdi, rdx
0x18000f093  jz      short loc_18000F0B4
0x18000f095  mov     r8d, [rbx+10h]
0x18000f099  cmp     [rcx+4], r8d
0x18000f09d  jbe     short loc_18000F0AC
0x18000f09f  mov     eax, [r15+8]
0x18000f0a3  cmp     [rcx+8], eax
0x18000f0a6  jz      loc_18000F284
0x18000f0ac  add     rcx, rbp
0x18000f0af  cmp     rcx, rdx
0x18000f0b2  jnz     short loc_18000F099
0x18000f0b4  movzx   eax, word ptr [rbx+22h]
0x18000f0b8  mov     r8d, 1
0x18000f0be  movzx   ecx, word ptr [rbx+20h]
0x18000f0c2  add     eax, r8d
0x18000f0c5  xor     edx, edx
0x18000f0c7  div     ecx
0x18000f0c9  mov     ecx, r8d
0x18000f0cc  movzx   eax, dx
0x18000f0cf  mov     [rbx+22h], dx
0x18000f0d3  lea     rsi, [rax+rax*4]
0x18000f0d7  mov     rax, [rbx+8]
0x18000f0db  shl     rsi, 4
0x18000f0df  lock xadd [rax], ecx
0x18000f0e3  add     ecx, r8d
0x18000f0e6  lea     r13, [rsi+rdi]
0x18000f0ea  mov     [rsi+rdi+4], ecx
0x18000f0ee  lea     rbx, [rdi+20h]
0x18000f0f2  mov     eax, [r15+8]
0x18000f0f6  add     rbx, rsi
0x18000f0f9  mov     [rsi+rdi+8], eax
0x18000f0fd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f101  mov     [r13+10h], r12
0x18000f105  movzx   eax, word ptr [r15+40h]
0x18000f10a  mov     [rsi+rdi+18h], ax
0x18000f10f  mov     al, [r15]
0x18000f112  mov     [rsi+rdi+1Ah], al
0x18000f116  mov     [rbx], r12
0x18000f119  mov     rax, [r15+88h]
0x18000f120  mov     [rsi+rdi+28h], rax
0x18000f125  mov     rax, [r15+90h]
0x18000f12c  mov     [rsi+rdi+30h], rax
0x18000f131  mov     [rsi+rdi+38h], r12
0x18000f136  mov     rcx, [r15+38h]
0x18000f13a  test    rcx, rcx
0x18000f13d  jnz     short loc_18000F144
0x18000f13f  mov     edx, r8d
0x18000f142  jmp     short loc_18000F154
0x18000f144  mov     rax, r14
0x18000f147  inc     rax
0x18000f14a  cmp     [rcx+rax], r12b
0x18000f14e  jnz     short loc_18000F147
0x18000f150  lea     rdx, [rax+1]
0x18000f154  mov     rcx, [r15+80h]
0x18000f15b  test    rcx, rcx
0x18000f15e  jz      short loc_18000F170
0x18000f160  mov     rax, r14
0x18000f163  inc     rax
0x18000f166  cmp     [rcx+rax], r12b
0x18000f16a  jnz     short loc_18000F163
0x18000f16c  lea     r8, [rax+1]; unsigned __int64
0x18000f170  mov     rcx, [r15+18h]
0x18000f174  test    rcx, rcx
0x18000f177  jnz     short loc_18000F17E
0x18000f179  lea     eax, [rcx+2]
0x18000f17c  jmp     short loc_18000F193
0x18000f17e  mov     rax, r14
0x18000f181  inc     rax
0x18000f184  cmp     [rcx+rax*2], r12w
0x18000f189  jnz     short loc_18000F181
0x18000f18b  lea     rax, ds:2[rax*2]
0x18000f193  lea     rbp, [r8+rax]
0x18000f197  add     rbp, rdx
0x18000f19a  cmp     [rsi+rdi+40h], r12
0x18000f19f  jz      short loc_18000F1A8
0x18000f1a1  cmp     [rsi+rdi+48h], rbp
0x18000f1a6  jnb     short loc_18000F1EA
0x18000f1a8  mov     rdx, rbp; dwBytes
0x18000f1ab  mov     ecx, 8; dwFlags
0x18000f1b0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f1b5  mov     r12, rax
0x18000f1b8  test    rax, rax
0x18000f1bb  jz      short loc_18000F1E7
0x18000f1bd  mov     rbx, [rsi+rdi+40h]
0x18000f1c2  call    cs:__imp_GetProcessHeap
0x18000f1c8  mov     r8, rbx; lpMem
0x18000f1cb  xor     edx, edx; dwFlags
0x18000f1cd  mov     rcx, rax; hHeap
0x18000f1d0  call    cs:__imp_HeapFree
0x18000f1d6  lea     rbx, [rdi+20h]
0x18000f1da  mov     [rsi+rdi+40h], r12
0x18000f1df  add     rbx, rsi
0x18000f1e2  mov     [rsi+rdi+48h], rbp
0x18000f1e7  xor     r12d, r12d
0x18000f1ea  mov     rcx, [rsi+rdi+40h]
0x18000f1ef  test    rcx, rcx
0x18000f1f2  jz      loc_18000F284
0x18000f1f8  mov     rbp, [rsi+rdi+48h]
0x18000f1fd  lea     r9, [r13+10h]
0x18000f201  mov     r8, [r15+38h]
0x18000f205  add     rbp, rcx
0x18000f208  mov     rdx, rbp
0x18000f20b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f210  mov     r8, [r15+80h]
0x18000f217  mov     r9, rbx
0x18000f21a  mov     rdx, rbp
0x18000f21d  mov     rcx, rax
0x18000f220  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f225  mov     rbx, rax
0x18000f228  cmp     rax, rbp
0x18000f22b  jz      short loc_18000F26F
0x18000f22d  mov     r8, [r15+18h]; Source
0x18000f231  test    r8, r8
0x18000f234  jz      short loc_18000F26F
0x18000f236  cmp     [r8], r12w
0x18000f23a  jz      short loc_18000F26F
0x18000f23c  inc     r14
0x18000f23f  cmp     [r8+r14*2], r12w
0x18000f244  jnz     short loc_18000F23C
0x18000f246  mov     rdx, rbp
0x18000f249  lea     r14, ds:2[r14*2]
0x18000f251  sub     rdx, rbx; DestinationSize
0x18000f254  cmp     rdx, r14
0x18000f257  jb      short loc_18000F26F
0x18000f259  mov     r9, r14; SourceSize
0x18000f25c  mov     rcx, rbx; Destination
0x18000f25f  call    cs:__imp_memcpy_s
0x18000f265  mov     [rsi+rdi+38h], rbx
0x18000f26a  add     rbx, r14
0x18000f26d  jmp     short loc_18000F274
0x18000f26f  mov     [rsi+rdi+38h], r12
0x18000f274  sub     rbp, rbx
0x18000f277  xor     edx, edx; Val
0x18000f279  mov     r8, rbp; Size
0x18000f27c  mov     rcx, rbx; void *
0x18000f27f  call    memset_0
0x18000f284  add     rsp, 28h
0x18000f288  pop     r15
0x18000f28a  pop     r14
0x18000f28c  pop     r13
0x18000f28e  pop     r12
0x18000f290  pop     rdi
0x18000f291  pop     rsi
0x18000f292  pop     rbp
0x18000f293  pop     rbx
0x18000f294  retn
```
