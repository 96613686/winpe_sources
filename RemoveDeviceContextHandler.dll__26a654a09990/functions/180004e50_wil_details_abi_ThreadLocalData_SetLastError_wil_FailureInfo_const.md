# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180004e50`
- end: `0x1800050d5`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x18000358c`
- `0x180004b28`
- `0x180004e50`
- `0x18000c966`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000509f`
- `msvcrt!memcpy_s` at `0x18000509f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005010`

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
0x180004e50  push    rbx
0x180004e52  push    rbp
0x180004e53  push    rsi
0x180004e54  push    rdi
0x180004e55  push    r12
0x180004e57  push    r13
0x180004e59  push    r14
0x180004e5b  push    r15
0x180004e5d  sub     rsp, 28h
0x180004e61  mov     esi, [rcx+10h]
0x180004e64  xor     r12d, r12d
0x180004e67  mov     r15, rdx
0x180004e6a  mov     rbx, rcx
0x180004e6d  mov     ebp, 50h ; 'P'
0x180004e72  cmp     [rcx+18h], r12
0x180004e76  jnz     short loc_180004EAD
0x180004e78  test    esi, esi
0x180004e7a  jz      short loc_180004EAD
0x180004e7c  mov     edx, 190h; dwBytes
0x180004e81  lea     ecx, [rbp-48h]; dwFlags
0x180004e84  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e89  mov     [rbx+18h], rax
0x180004e8d  test    rax, rax
0x180004e90  jz      short loc_180004EAD
0x180004e92  mov     dword ptr [rbx+20h], 5
0x180004e99  lea     rcx, [rax+190h]
0x180004ea0  jmp     short loc_180004EA8
0x180004ea2  mov     [rax], bp
0x180004ea5  add     rax, rbp
0x180004ea8  cmp     rax, rcx
0x180004eab  jnz     short loc_180004EA2
0x180004ead  mov     rdi, [rbx+18h]
0x180004eb1  test    rdi, rdi
0x180004eb4  jz      loc_1800050C4
0x180004eba  test    esi, esi
0x180004ebc  jz      short loc_180004EF4
0x180004ebe  movzx   eax, word ptr [rbx+20h]
0x180004ec2  mov     rcx, rdi
0x180004ec5  lea     rdx, [rax+rax*4]
0x180004ec9  shl     rdx, 4
0x180004ecd  add     rdx, rdi
0x180004ed0  cmp     rdi, rdx
0x180004ed3  jz      short loc_180004EF4
0x180004ed5  mov     r8d, [rbx+10h]
0x180004ed9  cmp     [rcx+4], r8d
0x180004edd  jbe     short loc_180004EEC
0x180004edf  mov     eax, [r15+8]
0x180004ee3  cmp     [rcx+8], eax
0x180004ee6  jz      loc_1800050C4
0x180004eec  add     rcx, rbp
0x180004eef  cmp     rcx, rdx
0x180004ef2  jnz     short loc_180004ED9
0x180004ef4  movzx   eax, word ptr [rbx+22h]
0x180004ef8  mov     r8d, 1
0x180004efe  movzx   ecx, word ptr [rbx+20h]
0x180004f02  add     eax, r8d
0x180004f05  xor     edx, edx
0x180004f07  div     ecx
0x180004f09  mov     ecx, r8d
0x180004f0c  movzx   eax, dx
0x180004f0f  mov     [rbx+22h], dx
0x180004f13  lea     rsi, [rax+rax*4]
0x180004f17  mov     rax, [rbx+8]
0x180004f1b  shl     rsi, 4
0x180004f1f  lock xadd [rax], ecx
0x180004f23  add     ecx, r8d
0x180004f26  lea     r13, [rsi+rdi]
0x180004f2a  mov     [rsi+rdi+4], ecx
0x180004f2e  lea     rbx, [rdi+20h]
0x180004f32  mov     eax, [r15+8]
0x180004f36  add     rbx, rsi
0x180004f39  mov     [rsi+rdi+8], eax
0x180004f3d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004f41  mov     [r13+10h], r12
0x180004f45  movzx   eax, word ptr [r15+40h]
0x180004f4a  mov     [rsi+rdi+18h], ax
0x180004f4f  mov     al, [r15]
0x180004f52  mov     [rsi+rdi+1Ah], al
0x180004f56  mov     [rbx], r12
0x180004f59  mov     rax, [r15+88h]
0x180004f60  mov     [rsi+rdi+28h], rax
0x180004f65  mov     rax, [r15+90h]
0x180004f6c  mov     [rsi+rdi+30h], rax
0x180004f71  mov     [rsi+rdi+38h], r12
0x180004f76  mov     rcx, [r15+38h]
0x180004f7a  test    rcx, rcx
0x180004f7d  jnz     short loc_180004F84
0x180004f7f  mov     edx, r8d
0x180004f82  jmp     short loc_180004F94
0x180004f84  mov     rax, r14
0x180004f87  inc     rax
0x180004f8a  cmp     [rcx+rax], r12b
0x180004f8e  jnz     short loc_180004F87
0x180004f90  lea     rdx, [rax+1]
0x180004f94  mov     rcx, [r15+80h]
0x180004f9b  test    rcx, rcx
0x180004f9e  jz      short loc_180004FB0
0x180004fa0  mov     rax, r14
0x180004fa3  inc     rax
0x180004fa6  cmp     [rcx+rax], r12b
0x180004faa  jnz     short loc_180004FA3
0x180004fac  lea     r8, [rax+1]; unsigned __int64
0x180004fb0  mov     rcx, [r15+18h]
0x180004fb4  test    rcx, rcx
0x180004fb7  jnz     short loc_180004FBE
0x180004fb9  lea     eax, [rcx+2]
0x180004fbc  jmp     short loc_180004FD3
0x180004fbe  mov     rax, r14
0x180004fc1  inc     rax
0x180004fc4  cmp     [rcx+rax*2], r12w
0x180004fc9  jnz     short loc_180004FC1
0x180004fcb  lea     rax, ds:2[rax*2]
0x180004fd3  lea     rbp, [r8+rax]
0x180004fd7  add     rbp, rdx
0x180004fda  cmp     [rsi+rdi+40h], r12
0x180004fdf  jz      short loc_180004FE8
0x180004fe1  cmp     [rsi+rdi+48h], rbp
0x180004fe6  jnb     short loc_18000502A
0x180004fe8  mov     rdx, rbp; dwBytes
0x180004feb  mov     ecx, 8; dwFlags
0x180004ff0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ff5  mov     r12, rax
0x180004ff8  test    rax, rax
0x180004ffb  jz      short loc_180005027
0x180004ffd  mov     rbx, [rsi+rdi+40h]
0x180005002  call    cs:__imp_GetProcessHeap
0x180005008  mov     r8, rbx; lpMem
0x18000500b  xor     edx, edx; dwFlags
0x18000500d  mov     rcx, rax; hHeap
0x180005010  call    cs:__imp_HeapFree
0x180005016  lea     rbx, [rdi+20h]
0x18000501a  mov     [rsi+rdi+40h], r12
0x18000501f  add     rbx, rsi
0x180005022  mov     [rsi+rdi+48h], rbp
0x180005027  xor     r12d, r12d
0x18000502a  mov     rcx, [rsi+rdi+40h]
0x18000502f  test    rcx, rcx
0x180005032  jz      loc_1800050C4
0x180005038  mov     rbp, [rsi+rdi+48h]
0x18000503d  lea     r9, [r13+10h]
0x180005041  mov     r8, [r15+38h]
0x180005045  add     rbp, rcx
0x180005048  mov     rdx, rbp
0x18000504b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005050  mov     r8, [r15+80h]
0x180005057  mov     r9, rbx
0x18000505a  mov     rdx, rbp
0x18000505d  mov     rcx, rax
0x180005060  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005065  mov     rbx, rax
0x180005068  cmp     rax, rbp
0x18000506b  jz      short loc_1800050AF
0x18000506d  mov     r8, [r15+18h]; Source
0x180005071  test    r8, r8
0x180005074  jz      short loc_1800050AF
0x180005076  cmp     [r8], r12w
0x18000507a  jz      short loc_1800050AF
0x18000507c  inc     r14
0x18000507f  cmp     [r8+r14*2], r12w
0x180005084  jnz     short loc_18000507C
0x180005086  mov     rdx, rbp
0x180005089  lea     r14, ds:2[r14*2]
0x180005091  sub     rdx, rbx; DestinationSize
0x180005094  cmp     rdx, r14
0x180005097  jb      short loc_1800050AF
0x180005099  mov     r9, r14; SourceSize
0x18000509c  mov     rcx, rbx; Destination
0x18000509f  call    cs:__imp_memcpy_s
0x1800050a5  mov     [rsi+rdi+38h], rbx
0x1800050aa  add     rbx, r14
0x1800050ad  jmp     short loc_1800050B4
0x1800050af  mov     [rsi+rdi+38h], r12
0x1800050b4  sub     rbp, rbx
0x1800050b7  xor     edx, edx; Val
0x1800050b9  mov     r8, rbp; Size
0x1800050bc  mov     rcx, rbx; void *
0x1800050bf  call    memset_0
0x1800050c4  add     rsp, 28h
0x1800050c8  pop     r15
0x1800050ca  pop     r14
0x1800050cc  pop     r13
0x1800050ce  pop     r12
0x1800050d0  pop     rdi
0x1800050d1  pop     rsi
0x1800050d2  pop     rbp
0x1800050d3  pop     rbx
0x1800050d4  retn
```
