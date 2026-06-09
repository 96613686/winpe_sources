# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180010d9c`
- end: `0x18001102d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d0e0`

## callees

- `0x1800053c4`
- `0x18000a8c8`
- `0x18000e7b0`
- `0x180010d9c`
- `0x180013758`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010f4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f62`

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
0x180010d9c  push    rbx
0x180010d9e  push    rbp
0x180010d9f  push    rsi
0x180010da0  push    rdi
0x180010da1  push    r12
0x180010da3  push    r13
0x180010da5  push    r14
0x180010da7  push    r15
0x180010da9  sub     rsp, 28h
0x180010dad  mov     esi, [rcx+10h]
0x180010db0  xor     r12d, r12d
0x180010db3  mov     r15, rdx
0x180010db6  mov     rbx, rcx
0x180010db9  mov     ebp, 50h ; 'P'
0x180010dbe  cmp     [rcx+18h], r12
0x180010dc2  jnz     short loc_180010DF9
0x180010dc4  test    esi, esi
0x180010dc6  jz      short loc_180010DF9
0x180010dc8  mov     edx, 190h; dwBytes
0x180010dcd  lea     ecx, [rbp-48h]; dwFlags
0x180010dd0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010dd5  mov     [rbx+18h], rax
0x180010dd9  test    rax, rax
0x180010ddc  jz      short loc_180010DF9
0x180010dde  mov     dword ptr [rbx+20h], 5
0x180010de5  lea     rcx, [rax+190h]
0x180010dec  jmp     short loc_180010DF4
0x180010dee  mov     [rax], bp
0x180010df1  add     rax, rbp
0x180010df4  cmp     rax, rcx
0x180010df7  jnz     short loc_180010DEE
0x180010df9  mov     rdi, [rbx+18h]
0x180010dfd  test    rdi, rdi
0x180010e00  jz      loc_18001101B
0x180010e06  test    esi, esi
0x180010e08  jz      short loc_180010E40
0x180010e0a  movzx   eax, word ptr [rbx+20h]
0x180010e0e  mov     rcx, rdi
0x180010e11  lea     rdx, [rax+rax*4]
0x180010e15  shl     rdx, 4
0x180010e19  add     rdx, rdi
0x180010e1c  cmp     rdi, rdx
0x180010e1f  jz      short loc_180010E40
0x180010e21  mov     r8d, [rbx+10h]
0x180010e25  cmp     [rcx+4], r8d
0x180010e29  jbe     short loc_180010E38
0x180010e2b  mov     eax, [r15+8]
0x180010e2f  cmp     [rcx+8], eax
0x180010e32  jz      loc_18001101B
0x180010e38  add     rcx, rbp
0x180010e3b  cmp     rcx, rdx
0x180010e3e  jnz     short loc_180010E25
0x180010e40  movzx   eax, word ptr [rbx+22h]
0x180010e44  mov     r8d, 1
0x180010e4a  movzx   ecx, word ptr [rbx+20h]
0x180010e4e  add     eax, r8d
0x180010e51  xor     edx, edx
0x180010e53  div     ecx
0x180010e55  mov     ecx, r8d
0x180010e58  movzx   eax, dx
0x180010e5b  mov     [rbx+22h], dx
0x180010e5f  lea     rsi, [rax+rax*4]
0x180010e63  mov     rax, [rbx+8]
0x180010e67  shl     rsi, 4
0x180010e6b  lock xadd [rax], ecx
0x180010e6f  add     ecx, r8d
0x180010e72  lea     r13, [rsi+rdi]
0x180010e76  mov     [rsi+rdi+4], ecx
0x180010e7a  lea     rbx, [rdi+20h]
0x180010e7e  mov     eax, [r15+8]
0x180010e82  add     rbx, rsi
0x180010e85  mov     [rsi+rdi+8], eax
0x180010e89  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010e8d  mov     [r13+10h], r12
0x180010e91  movzx   eax, word ptr [r15+40h]
0x180010e96  mov     [rsi+rdi+18h], ax
0x180010e9b  mov     al, [r15]
0x180010e9e  mov     [rsi+rdi+1Ah], al
0x180010ea2  mov     [rbx], r12
0x180010ea5  mov     rax, [r15+88h]
0x180010eac  mov     [rsi+rdi+28h], rax
0x180010eb1  mov     rax, [r15+90h]
0x180010eb8  mov     [rsi+rdi+30h], rax
0x180010ebd  mov     [rsi+rdi+38h], r12
0x180010ec2  mov     rcx, [r15+38h]
0x180010ec6  test    rcx, rcx
0x180010ec9  jnz     short loc_180010ED0
0x180010ecb  mov     edx, r8d
0x180010ece  jmp     short loc_180010EE0
0x180010ed0  mov     rax, r14
0x180010ed3  inc     rax
0x180010ed6  cmp     [rcx+rax], r12b
0x180010eda  jnz     short loc_180010ED3
0x180010edc  lea     rdx, [rax+1]
0x180010ee0  mov     rcx, [r15+80h]
0x180010ee7  test    rcx, rcx
0x180010eea  jz      short loc_180010EFC
0x180010eec  mov     rax, r14
0x180010eef  inc     rax
0x180010ef2  cmp     [rcx+rax], r12b
0x180010ef6  jnz     short loc_180010EEF
0x180010ef8  lea     r8, [rax+1]; unsigned __int64
0x180010efc  mov     rcx, [r15+18h]
0x180010f00  test    rcx, rcx
0x180010f03  jnz     short loc_180010F0A
0x180010f05  lea     eax, [rcx+2]
0x180010f08  jmp     short loc_180010F1F
0x180010f0a  mov     rax, r14
0x180010f0d  inc     rax
0x180010f10  cmp     [rcx+rax*2], r12w
0x180010f15  jnz     short loc_180010F0D
0x180010f17  lea     rax, ds:2[rax*2]
0x180010f1f  lea     rbp, [r8+rax]
0x180010f23  add     rbp, rdx
0x180010f26  cmp     [rsi+rdi+40h], r12
0x180010f2b  jz      short loc_180010F34
0x180010f2d  cmp     [rsi+rdi+48h], rbp
0x180010f32  jnb     short loc_180010F82
0x180010f34  mov     rdx, rbp; dwBytes
0x180010f37  mov     ecx, 8; dwFlags
0x180010f3c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010f41  mov     r12, rax
0x180010f44  test    rax, rax
0x180010f47  jz      short loc_180010F7F
0x180010f49  mov     rbx, [rsi+rdi+40h]
0x180010f4e  call    cs:__imp_GetProcessHeap
0x180010f55  nop     dword ptr [rax+rax+00h]
0x180010f5a  mov     r8, rbx; lpMem
0x180010f5d  xor     edx, edx; dwFlags
0x180010f5f  mov     rcx, rax; hHeap
0x180010f62  call    cs:__imp_HeapFree
0x180010f69  nop     dword ptr [rax+rax+00h]
0x180010f6e  lea     rbx, [rdi+20h]
0x180010f72  mov     [rsi+rdi+40h], r12
0x180010f77  add     rbx, rsi
0x180010f7a  mov     [rsi+rdi+48h], rbp
0x180010f7f  xor     r12d, r12d
0x180010f82  mov     rcx, [rsi+rdi+40h]
0x180010f87  test    rcx, rcx
0x180010f8a  jz      loc_18001101B
0x180010f90  mov     rbp, [rsi+rdi+48h]
0x180010f95  lea     r9, [r13+10h]
0x180010f99  mov     r8, [r15+38h]
0x180010f9d  add     rbp, rcx
0x180010fa0  mov     rdx, rbp
0x180010fa3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010fa8  mov     r8, [r15+80h]
0x180010faf  mov     r9, rbx
0x180010fb2  mov     rdx, rbp
0x180010fb5  mov     rcx, rax
0x180010fb8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010fbd  mov     rbx, rax
0x180010fc0  cmp     rax, rbp
0x180010fc3  jz      short loc_180011006
0x180010fc5  mov     r8, [r15+18h]; Source
0x180010fc9  test    r8, r8
0x180010fcc  jz      short loc_180011006
0x180010fce  cmp     [r8], r12w
0x180010fd2  jz      short loc_180011006
0x180010fd4  inc     r14
0x180010fd7  cmp     [r8+r14*2], r12w
0x180010fdc  jnz     short loc_180010FD4
0x180010fde  mov     rdx, rbp
0x180010fe1  lea     r14, ds:2[r14*2]
0x180010fe9  sub     rdx, rbx; DestinationSize
0x180010fec  cmp     rdx, r14
0x180010fef  jb      short loc_180011006
0x180010ff1  mov     r9, r14; SourceSize
0x180010ff4  mov     rcx, rbx; Destination
0x180010ff7  call    memcpy_s
0x180010ffc  mov     [rsi+rdi+38h], rbx
0x180011001  add     rbx, r14
0x180011004  jmp     short loc_18001100B
0x180011006  mov     [rsi+rdi+38h], r12
0x18001100b  sub     rbp, rbx
0x18001100e  xor     edx, edx; Val
0x180011010  mov     r8, rbp; Size
0x180011013  mov     rcx, rbx; void *
0x180011016  call    memset_0
0x18001101b  add     rsp, 28h
0x18001101f  pop     r15
0x180011021  pop     r14
0x180011023  pop     r13
0x180011025  pop     r12
0x180011027  pop     rdi
0x180011028  pop     rsi
0x180011029  pop     rbp
0x18001102a  pop     rbx
0x18001102b  retn
```
