# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005bc0`
- end: `0x180005e51`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004480`

## callees

- `0x180003290`
- `0x180003ec8`
- `0x1800057b4`
- `0x180005bc0`
- `0x180006534`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005d72`
- `KERNEL32!GetProcessHeap` at `0x180005d72`
- `KERNEL32!HeapFree` at `0x180005d86`
- `KERNEL32!HeapFree` at `0x180005d86`

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
0x180005bc0  push    rbx
0x180005bc2  push    rbp
0x180005bc3  push    rsi
0x180005bc4  push    rdi
0x180005bc5  push    r12
0x180005bc7  push    r13
0x180005bc9  push    r14
0x180005bcb  push    r15
0x180005bcd  sub     rsp, 28h
0x180005bd1  mov     esi, [rcx+10h]
0x180005bd4  xor     r12d, r12d
0x180005bd7  mov     r15, rdx
0x180005bda  mov     rbx, rcx
0x180005bdd  mov     ebp, 50h ; 'P'
0x180005be2  cmp     [rcx+18h], r12
0x180005be6  jnz     short loc_180005C1D
0x180005be8  test    esi, esi
0x180005bea  jz      short loc_180005C1D
0x180005bec  mov     edx, 190h; dwBytes
0x180005bf1  lea     ecx, [rbp-48h]; dwFlags
0x180005bf4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005bf9  mov     [rbx+18h], rax
0x180005bfd  test    rax, rax
0x180005c00  jz      short loc_180005C1D
0x180005c02  mov     dword ptr [rbx+20h], 5
0x180005c09  lea     rcx, [rax+190h]
0x180005c10  jmp     short loc_180005C18
0x180005c12  mov     [rax], bp
0x180005c15  add     rax, rbp
0x180005c18  cmp     rax, rcx
0x180005c1b  jnz     short loc_180005C12
0x180005c1d  mov     rdi, [rbx+18h]
0x180005c21  test    rdi, rdi
0x180005c24  jz      loc_180005E3F
0x180005c2a  test    esi, esi
0x180005c2c  jz      short loc_180005C64
0x180005c2e  movzx   eax, word ptr [rbx+20h]
0x180005c32  mov     rcx, rdi
0x180005c35  lea     rdx, [rax+rax*4]
0x180005c39  shl     rdx, 4
0x180005c3d  add     rdx, rdi
0x180005c40  cmp     rdi, rdx
0x180005c43  jz      short loc_180005C64
0x180005c45  mov     r8d, [rbx+10h]
0x180005c49  cmp     [rcx+4], r8d
0x180005c4d  jbe     short loc_180005C5C
0x180005c4f  mov     eax, [r15+8]
0x180005c53  cmp     [rcx+8], eax
0x180005c56  jz      loc_180005E3F
0x180005c5c  add     rcx, rbp
0x180005c5f  cmp     rcx, rdx
0x180005c62  jnz     short loc_180005C49
0x180005c64  movzx   eax, word ptr [rbx+22h]
0x180005c68  mov     r8d, 1
0x180005c6e  movzx   ecx, word ptr [rbx+20h]
0x180005c72  add     eax, r8d
0x180005c75  xor     edx, edx
0x180005c77  div     ecx
0x180005c79  mov     ecx, r8d
0x180005c7c  movzx   eax, dx
0x180005c7f  mov     [rbx+22h], dx
0x180005c83  lea     rsi, [rax+rax*4]
0x180005c87  mov     rax, [rbx+8]
0x180005c8b  shl     rsi, 4
0x180005c8f  lock xadd [rax], ecx
0x180005c93  add     ecx, r8d
0x180005c96  lea     r13, [rsi+rdi]
0x180005c9a  mov     [rsi+rdi+4], ecx
0x180005c9e  lea     rbx, [rdi+20h]
0x180005ca2  mov     eax, [r15+8]
0x180005ca6  add     rbx, rsi
0x180005ca9  mov     [rsi+rdi+8], eax
0x180005cad  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005cb1  mov     [r13+10h], r12
0x180005cb5  movzx   eax, word ptr [r15+40h]
0x180005cba  mov     [rsi+rdi+18h], ax
0x180005cbf  mov     al, [r15]
0x180005cc2  mov     [rsi+rdi+1Ah], al
0x180005cc6  mov     [rbx], r12
0x180005cc9  mov     rax, [r15+88h]
0x180005cd0  mov     [rsi+rdi+28h], rax
0x180005cd5  mov     rax, [r15+90h]
0x180005cdc  mov     [rsi+rdi+30h], rax
0x180005ce1  mov     [rsi+rdi+38h], r12
0x180005ce6  mov     rcx, [r15+38h]
0x180005cea  test    rcx, rcx
0x180005ced  jnz     short loc_180005CF4
0x180005cef  mov     edx, r8d
0x180005cf2  jmp     short loc_180005D04
0x180005cf4  mov     rax, r14
0x180005cf7  inc     rax
0x180005cfa  cmp     [rcx+rax], r12b
0x180005cfe  jnz     short loc_180005CF7
0x180005d00  lea     rdx, [rax+1]
0x180005d04  mov     rcx, [r15+80h]
0x180005d0b  test    rcx, rcx
0x180005d0e  jz      short loc_180005D20
0x180005d10  mov     rax, r14
0x180005d13  inc     rax
0x180005d16  cmp     [rcx+rax], r12b
0x180005d1a  jnz     short loc_180005D13
0x180005d1c  lea     r8, [rax+1]; unsigned __int64
0x180005d20  mov     rcx, [r15+18h]
0x180005d24  test    rcx, rcx
0x180005d27  jnz     short loc_180005D2E
0x180005d29  lea     eax, [rcx+2]
0x180005d2c  jmp     short loc_180005D43
0x180005d2e  mov     rax, r14
0x180005d31  inc     rax
0x180005d34  cmp     [rcx+rax*2], r12w
0x180005d39  jnz     short loc_180005D31
0x180005d3b  lea     rax, ds:2[rax*2]
0x180005d43  lea     rbp, [r8+rax]
0x180005d47  add     rbp, rdx
0x180005d4a  cmp     [rsi+rdi+40h], r12
0x180005d4f  jz      short loc_180005D58
0x180005d51  cmp     [rsi+rdi+48h], rbp
0x180005d56  jnb     short loc_180005DA6
0x180005d58  mov     rdx, rbp; dwBytes
0x180005d5b  mov     ecx, 8; dwFlags
0x180005d60  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005d65  mov     r12, rax
0x180005d68  test    rax, rax
0x180005d6b  jz      short loc_180005DA3
0x180005d6d  mov     rbx, [rsi+rdi+40h]
0x180005d72  call    cs:__imp_GetProcessHeap
0x180005d79  nop     dword ptr [rax+rax+00h]
0x180005d7e  mov     r8, rbx; lpMem
0x180005d81  xor     edx, edx; dwFlags
0x180005d83  mov     rcx, rax; hHeap
0x180005d86  call    cs:__imp_HeapFree
0x180005d8d  nop     dword ptr [rax+rax+00h]
0x180005d92  lea     rbx, [rdi+20h]
0x180005d96  mov     [rsi+rdi+40h], r12
0x180005d9b  add     rbx, rsi
0x180005d9e  mov     [rsi+rdi+48h], rbp
0x180005da3  xor     r12d, r12d
0x180005da6  mov     rcx, [rsi+rdi+40h]
0x180005dab  test    rcx, rcx
0x180005dae  jz      loc_180005E3F
0x180005db4  mov     rbp, [rsi+rdi+48h]
0x180005db9  lea     r9, [r13+10h]
0x180005dbd  mov     r8, [r15+38h]
0x180005dc1  add     rbp, rcx
0x180005dc4  mov     rdx, rbp
0x180005dc7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005dcc  mov     r8, [r15+80h]
0x180005dd3  mov     r9, rbx
0x180005dd6  mov     rdx, rbp
0x180005dd9  mov     rcx, rax
0x180005ddc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005de1  mov     rbx, rax
0x180005de4  cmp     rax, rbp
0x180005de7  jz      short loc_180005E2A
0x180005de9  mov     r8, [r15+18h]; Source
0x180005ded  test    r8, r8
0x180005df0  jz      short loc_180005E2A
0x180005df2  cmp     [r8], r12w
0x180005df6  jz      short loc_180005E2A
0x180005df8  inc     r14
0x180005dfb  cmp     [r8+r14*2], r12w
0x180005e00  jnz     short loc_180005DF8
0x180005e02  mov     rdx, rbp
0x180005e05  lea     r14, ds:2[r14*2]
0x180005e0d  sub     rdx, rbx; DestinationSize
0x180005e10  cmp     rdx, r14
0x180005e13  jb      short loc_180005E2A
0x180005e15  mov     r9, r14; SourceSize
0x180005e18  mov     rcx, rbx; Destination
0x180005e1b  call    memcpy_s
0x180005e20  mov     [rsi+rdi+38h], rbx
0x180005e25  add     rbx, r14
0x180005e28  jmp     short loc_180005E2F
0x180005e2a  mov     [rsi+rdi+38h], r12
0x180005e2f  sub     rbp, rbx
0x180005e32  xor     edx, edx; Val
0x180005e34  mov     r8, rbp; Size
0x180005e37  mov     rcx, rbx; void *
0x180005e3a  call    memset_0
0x180005e3f  add     rsp, 28h
0x180005e43  pop     r15
0x180005e45  pop     r14
0x180005e47  pop     r13
0x180005e49  pop     r12
0x180005e4b  pop     rdi
0x180005e4c  pop     rsi
0x180005e4d  pop     rbp
0x180005e4e  pop     rbx
0x180005e4f  retn
```
