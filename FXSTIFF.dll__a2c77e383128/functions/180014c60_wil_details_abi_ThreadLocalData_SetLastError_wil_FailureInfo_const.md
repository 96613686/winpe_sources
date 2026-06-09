# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180014c60`
- end: `0x180014ee5`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011fe0`

## callees

- `0x180010290`
- `0x18001315c`
- `0x180014c60`
- `0x180017bce`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014eaf`
- `msvcrt!memcpy_s` at `0x180014eaf`
- `KERNEL32!HeapFree` at `0x180014e20`
- `KERNEL32!HeapFree` at `0x180014e20`
- `KERNEL32!GetProcessHeap` at `0x180014e12`
- `KERNEL32!GetProcessHeap` at `0x180014e12`

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
0x180014c60  push    rbx
0x180014c62  push    rbp
0x180014c63  push    rsi
0x180014c64  push    rdi
0x180014c65  push    r12
0x180014c67  push    r13
0x180014c69  push    r14
0x180014c6b  push    r15
0x180014c6d  sub     rsp, 28h
0x180014c71  mov     esi, [rcx+10h]
0x180014c74  xor     r12d, r12d
0x180014c77  mov     r15, rdx
0x180014c7a  mov     rbx, rcx
0x180014c7d  mov     ebp, 50h ; 'P'
0x180014c82  cmp     [rcx+18h], r12
0x180014c86  jnz     short loc_180014CBD
0x180014c88  test    esi, esi
0x180014c8a  jz      short loc_180014CBD
0x180014c8c  mov     edx, 190h; dwBytes
0x180014c91  lea     ecx, [rbp-48h]; dwFlags
0x180014c94  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014c99  mov     [rbx+18h], rax
0x180014c9d  test    rax, rax
0x180014ca0  jz      short loc_180014CBD
0x180014ca2  mov     dword ptr [rbx+20h], 5
0x180014ca9  lea     rcx, [rax+190h]
0x180014cb0  jmp     short loc_180014CB8
0x180014cb2  mov     [rax], bp
0x180014cb5  add     rax, rbp
0x180014cb8  cmp     rax, rcx
0x180014cbb  jnz     short loc_180014CB2
0x180014cbd  mov     rdi, [rbx+18h]
0x180014cc1  test    rdi, rdi
0x180014cc4  jz      loc_180014ED4
0x180014cca  test    esi, esi
0x180014ccc  jz      short loc_180014D04
0x180014cce  movzx   eax, word ptr [rbx+20h]
0x180014cd2  mov     rcx, rdi
0x180014cd5  lea     rdx, [rax+rax*4]
0x180014cd9  shl     rdx, 4
0x180014cdd  add     rdx, rdi
0x180014ce0  cmp     rdi, rdx
0x180014ce3  jz      short loc_180014D04
0x180014ce5  mov     r8d, [rbx+10h]
0x180014ce9  cmp     [rcx+4], r8d
0x180014ced  jbe     short loc_180014CFC
0x180014cef  mov     eax, [r15+8]
0x180014cf3  cmp     [rcx+8], eax
0x180014cf6  jz      loc_180014ED4
0x180014cfc  add     rcx, rbp
0x180014cff  cmp     rcx, rdx
0x180014d02  jnz     short loc_180014CE9
0x180014d04  movzx   eax, word ptr [rbx+22h]
0x180014d08  mov     r8d, 1
0x180014d0e  movzx   ecx, word ptr [rbx+20h]
0x180014d12  add     eax, r8d
0x180014d15  xor     edx, edx
0x180014d17  div     ecx
0x180014d19  mov     ecx, r8d
0x180014d1c  movzx   eax, dx
0x180014d1f  mov     [rbx+22h], dx
0x180014d23  lea     rsi, [rax+rax*4]
0x180014d27  mov     rax, [rbx+8]
0x180014d2b  shl     rsi, 4
0x180014d2f  lock xadd [rax], ecx
0x180014d33  add     ecx, r8d
0x180014d36  lea     r13, [rsi+rdi]
0x180014d3a  mov     [rsi+rdi+4], ecx
0x180014d3e  lea     rbx, [rdi+20h]
0x180014d42  mov     eax, [r15+8]
0x180014d46  add     rbx, rsi
0x180014d49  mov     [rsi+rdi+8], eax
0x180014d4d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180014d51  mov     [r13+10h], r12
0x180014d55  movzx   eax, word ptr [r15+40h]
0x180014d5a  mov     [rsi+rdi+18h], ax
0x180014d5f  mov     al, [r15]
0x180014d62  mov     [rsi+rdi+1Ah], al
0x180014d66  mov     [rbx], r12
0x180014d69  mov     rax, [r15+88h]
0x180014d70  mov     [rsi+rdi+28h], rax
0x180014d75  mov     rax, [r15+90h]
0x180014d7c  mov     [rsi+rdi+30h], rax
0x180014d81  mov     [rsi+rdi+38h], r12
0x180014d86  mov     rcx, [r15+38h]
0x180014d8a  test    rcx, rcx
0x180014d8d  jnz     short loc_180014D94
0x180014d8f  mov     edx, r8d
0x180014d92  jmp     short loc_180014DA4
0x180014d94  mov     rax, r14
0x180014d97  inc     rax
0x180014d9a  cmp     [rcx+rax], r12b
0x180014d9e  jnz     short loc_180014D97
0x180014da0  lea     rdx, [rax+1]
0x180014da4  mov     rcx, [r15+80h]
0x180014dab  test    rcx, rcx
0x180014dae  jz      short loc_180014DC0
0x180014db0  mov     rax, r14
0x180014db3  inc     rax
0x180014db6  cmp     [rcx+rax], r12b
0x180014dba  jnz     short loc_180014DB3
0x180014dbc  lea     r8, [rax+1]; unsigned __int64
0x180014dc0  mov     rcx, [r15+18h]
0x180014dc4  test    rcx, rcx
0x180014dc7  jnz     short loc_180014DCE
0x180014dc9  lea     eax, [rcx+2]
0x180014dcc  jmp     short loc_180014DE3
0x180014dce  mov     rax, r14
0x180014dd1  inc     rax
0x180014dd4  cmp     [rcx+rax*2], r12w
0x180014dd9  jnz     short loc_180014DD1
0x180014ddb  lea     rax, ds:2[rax*2]
0x180014de3  lea     rbp, [r8+rax]
0x180014de7  add     rbp, rdx
0x180014dea  cmp     [rsi+rdi+40h], r12
0x180014def  jz      short loc_180014DF8
0x180014df1  cmp     [rsi+rdi+48h], rbp
0x180014df6  jnb     short loc_180014E3A
0x180014df8  mov     rdx, rbp; dwBytes
0x180014dfb  mov     ecx, 8; dwFlags
0x180014e00  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014e05  mov     r12, rax
0x180014e08  test    rax, rax
0x180014e0b  jz      short loc_180014E37
0x180014e0d  mov     rbx, [rsi+rdi+40h]
0x180014e12  call    cs:__imp_GetProcessHeap
0x180014e18  mov     r8, rbx; lpMem
0x180014e1b  xor     edx, edx; dwFlags
0x180014e1d  mov     rcx, rax; hHeap
0x180014e20  call    cs:__imp_HeapFree
0x180014e26  lea     rbx, [rdi+20h]
0x180014e2a  mov     [rsi+rdi+40h], r12
0x180014e2f  add     rbx, rsi
0x180014e32  mov     [rsi+rdi+48h], rbp
0x180014e37  xor     r12d, r12d
0x180014e3a  mov     rcx, [rsi+rdi+40h]
0x180014e3f  test    rcx, rcx
0x180014e42  jz      loc_180014ED4
0x180014e48  mov     rbp, [rsi+rdi+48h]
0x180014e4d  lea     r9, [r13+10h]
0x180014e51  mov     r8, [r15+38h]
0x180014e55  add     rbp, rcx
0x180014e58  mov     rdx, rbp
0x180014e5b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014e60  mov     r8, [r15+80h]
0x180014e67  mov     r9, rbx
0x180014e6a  mov     rdx, rbp
0x180014e6d  mov     rcx, rax
0x180014e70  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014e75  mov     rbx, rax
0x180014e78  cmp     rax, rbp
0x180014e7b  jz      short loc_180014EBF
0x180014e7d  mov     r8, [r15+18h]; Source
0x180014e81  test    r8, r8
0x180014e84  jz      short loc_180014EBF
0x180014e86  cmp     [r8], r12w
0x180014e8a  jz      short loc_180014EBF
0x180014e8c  inc     r14
0x180014e8f  cmp     [r8+r14*2], r12w
0x180014e94  jnz     short loc_180014E8C
0x180014e96  mov     rdx, rbp
0x180014e99  lea     r14, ds:2[r14*2]
0x180014ea1  sub     rdx, rbx; DestinationSize
0x180014ea4  cmp     rdx, r14
0x180014ea7  jb      short loc_180014EBF
0x180014ea9  mov     r9, r14; SourceSize
0x180014eac  mov     rcx, rbx; Destination
0x180014eaf  call    cs:__imp_memcpy_s
0x180014eb5  mov     [rsi+rdi+38h], rbx
0x180014eba  add     rbx, r14
0x180014ebd  jmp     short loc_180014EC4
0x180014ebf  mov     [rsi+rdi+38h], r12
0x180014ec4  sub     rbp, rbx
0x180014ec7  xor     edx, edx; Val
0x180014ec9  mov     r8, rbp; Size
0x180014ecc  mov     rcx, rbx; void *
0x180014ecf  call    memset_0
0x180014ed4  add     rsp, 28h
0x180014ed8  pop     r15
0x180014eda  pop     r14
0x180014edc  pop     r13
0x180014ede  pop     r12
0x180014ee0  pop     rdi
0x180014ee1  pop     rsi
0x180014ee2  pop     rbp
0x180014ee3  pop     rbx
0x180014ee4  retn
```
