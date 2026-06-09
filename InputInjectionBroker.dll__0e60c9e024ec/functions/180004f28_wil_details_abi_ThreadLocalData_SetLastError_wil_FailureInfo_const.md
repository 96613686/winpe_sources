# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180004f28`
- end: `0x1800051ad`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003840`

## callees

- `0x180002c10`
- `0x1800047d8`
- `0x180004f28`
- `0x18001143a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005177`
- `msvcrt!memcpy_s` at `0x180005177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050e8`

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
0x180004f28  push    rbx
0x180004f2a  push    rbp
0x180004f2b  push    rsi
0x180004f2c  push    rdi
0x180004f2d  push    r12
0x180004f2f  push    r13
0x180004f31  push    r14
0x180004f33  push    r15
0x180004f35  sub     rsp, 28h
0x180004f39  mov     esi, [rcx+10h]
0x180004f3c  xor     r12d, r12d
0x180004f3f  mov     r15, rdx
0x180004f42  mov     rbx, rcx
0x180004f45  mov     ebp, 50h ; 'P'
0x180004f4a  cmp     [rcx+18h], r12
0x180004f4e  jnz     short loc_180004F85
0x180004f50  test    esi, esi
0x180004f52  jz      short loc_180004F85
0x180004f54  mov     edx, 190h; dwBytes
0x180004f59  lea     ecx, [rbp-48h]; dwFlags
0x180004f5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f61  mov     [rbx+18h], rax
0x180004f65  test    rax, rax
0x180004f68  jz      short loc_180004F85
0x180004f6a  mov     dword ptr [rbx+20h], 5
0x180004f71  lea     rcx, [rax+190h]
0x180004f78  jmp     short loc_180004F80
0x180004f7a  mov     [rax], bp
0x180004f7d  add     rax, rbp
0x180004f80  cmp     rax, rcx
0x180004f83  jnz     short loc_180004F7A
0x180004f85  mov     rdi, [rbx+18h]
0x180004f89  test    rdi, rdi
0x180004f8c  jz      loc_18000519C
0x180004f92  test    esi, esi
0x180004f94  jz      short loc_180004FCC
0x180004f96  movzx   eax, word ptr [rbx+20h]
0x180004f9a  mov     rcx, rdi
0x180004f9d  lea     rdx, [rax+rax*4]
0x180004fa1  shl     rdx, 4
0x180004fa5  add     rdx, rdi
0x180004fa8  cmp     rdi, rdx
0x180004fab  jz      short loc_180004FCC
0x180004fad  mov     r8d, [rbx+10h]
0x180004fb1  cmp     [rcx+4], r8d
0x180004fb5  jbe     short loc_180004FC4
0x180004fb7  mov     eax, [r15+8]
0x180004fbb  cmp     [rcx+8], eax
0x180004fbe  jz      loc_18000519C
0x180004fc4  add     rcx, rbp
0x180004fc7  cmp     rcx, rdx
0x180004fca  jnz     short loc_180004FB1
0x180004fcc  movzx   eax, word ptr [rbx+22h]
0x180004fd0  mov     r8d, 1
0x180004fd6  movzx   ecx, word ptr [rbx+20h]
0x180004fda  add     eax, r8d
0x180004fdd  xor     edx, edx
0x180004fdf  div     ecx
0x180004fe1  mov     ecx, r8d
0x180004fe4  movzx   eax, dx
0x180004fe7  mov     [rbx+22h], dx
0x180004feb  lea     rsi, [rax+rax*4]
0x180004fef  mov     rax, [rbx+8]
0x180004ff3  shl     rsi, 4
0x180004ff7  lock xadd [rax], ecx
0x180004ffb  add     ecx, r8d
0x180004ffe  lea     r13, [rsi+rdi]
0x180005002  mov     [rsi+rdi+4], ecx
0x180005006  lea     rbx, [rdi+20h]
0x18000500a  mov     eax, [r15+8]
0x18000500e  add     rbx, rsi
0x180005011  mov     [rsi+rdi+8], eax
0x180005015  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005019  mov     [r13+10h], r12
0x18000501d  movzx   eax, word ptr [r15+40h]
0x180005022  mov     [rsi+rdi+18h], ax
0x180005027  mov     al, [r15]
0x18000502a  mov     [rsi+rdi+1Ah], al
0x18000502e  mov     [rbx], r12
0x180005031  mov     rax, [r15+88h]
0x180005038  mov     [rsi+rdi+28h], rax
0x18000503d  mov     rax, [r15+90h]
0x180005044  mov     [rsi+rdi+30h], rax
0x180005049  mov     [rsi+rdi+38h], r12
0x18000504e  mov     rcx, [r15+38h]
0x180005052  test    rcx, rcx
0x180005055  jnz     short loc_18000505C
0x180005057  mov     edx, r8d
0x18000505a  jmp     short loc_18000506C
0x18000505c  mov     rax, r14
0x18000505f  inc     rax
0x180005062  cmp     [rcx+rax], r12b
0x180005066  jnz     short loc_18000505F
0x180005068  lea     rdx, [rax+1]
0x18000506c  mov     rcx, [r15+80h]
0x180005073  test    rcx, rcx
0x180005076  jz      short loc_180005088
0x180005078  mov     rax, r14
0x18000507b  inc     rax
0x18000507e  cmp     [rcx+rax], r12b
0x180005082  jnz     short loc_18000507B
0x180005084  lea     r8, [rax+1]; unsigned __int64
0x180005088  mov     rcx, [r15+18h]
0x18000508c  test    rcx, rcx
0x18000508f  jnz     short loc_180005096
0x180005091  lea     eax, [rcx+2]
0x180005094  jmp     short loc_1800050AB
0x180005096  mov     rax, r14
0x180005099  inc     rax
0x18000509c  cmp     [rcx+rax*2], r12w
0x1800050a1  jnz     short loc_180005099
0x1800050a3  lea     rax, ds:2[rax*2]
0x1800050ab  lea     rbp, [r8+rax]
0x1800050af  add     rbp, rdx
0x1800050b2  cmp     [rsi+rdi+40h], r12
0x1800050b7  jz      short loc_1800050C0
0x1800050b9  cmp     [rsi+rdi+48h], rbp
0x1800050be  jnb     short loc_180005102
0x1800050c0  mov     rdx, rbp; dwBytes
0x1800050c3  mov     ecx, 8; dwFlags
0x1800050c8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050cd  mov     r12, rax
0x1800050d0  test    rax, rax
0x1800050d3  jz      short loc_1800050FF
0x1800050d5  mov     rbx, [rsi+rdi+40h]
0x1800050da  call    cs:__imp_GetProcessHeap
0x1800050e0  mov     r8, rbx; lpMem
0x1800050e3  xor     edx, edx; dwFlags
0x1800050e5  mov     rcx, rax; hHeap
0x1800050e8  call    cs:__imp_HeapFree
0x1800050ee  lea     rbx, [rdi+20h]
0x1800050f2  mov     [rsi+rdi+40h], r12
0x1800050f7  add     rbx, rsi
0x1800050fa  mov     [rsi+rdi+48h], rbp
0x1800050ff  xor     r12d, r12d
0x180005102  mov     rcx, [rsi+rdi+40h]
0x180005107  test    rcx, rcx
0x18000510a  jz      loc_18000519C
0x180005110  mov     rbp, [rsi+rdi+48h]
0x180005115  lea     r9, [r13+10h]
0x180005119  mov     r8, [r15+38h]
0x18000511d  add     rbp, rcx
0x180005120  mov     rdx, rbp
0x180005123  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005128  mov     r8, [r15+80h]
0x18000512f  mov     r9, rbx
0x180005132  mov     rdx, rbp
0x180005135  mov     rcx, rax
0x180005138  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000513d  mov     rbx, rax
0x180005140  cmp     rax, rbp
0x180005143  jz      short loc_180005187
0x180005145  mov     r8, [r15+18h]; Source
0x180005149  test    r8, r8
0x18000514c  jz      short loc_180005187
0x18000514e  cmp     [r8], r12w
0x180005152  jz      short loc_180005187
0x180005154  inc     r14
0x180005157  cmp     [r8+r14*2], r12w
0x18000515c  jnz     short loc_180005154
0x18000515e  mov     rdx, rbp
0x180005161  lea     r14, ds:2[r14*2]
0x180005169  sub     rdx, rbx; DestinationSize
0x18000516c  cmp     rdx, r14
0x18000516f  jb      short loc_180005187
0x180005171  mov     r9, r14; SourceSize
0x180005174  mov     rcx, rbx; Destination
0x180005177  call    cs:__imp_memcpy_s
0x18000517d  mov     [rsi+rdi+38h], rbx
0x180005182  add     rbx, r14
0x180005185  jmp     short loc_18000518C
0x180005187  mov     [rsi+rdi+38h], r12
0x18000518c  sub     rbp, rbx
0x18000518f  xor     edx, edx; Val
0x180005191  mov     r8, rbp; Size
0x180005194  mov     rcx, rbx; void *
0x180005197  call    memset_0
0x18000519c  add     rsp, 28h
0x1800051a0  pop     r15
0x1800051a2  pop     r14
0x1800051a4  pop     r13
0x1800051a6  pop     r12
0x1800051a8  pop     rdi
0x1800051a9  pop     rsi
0x1800051aa  pop     rbp
0x1800051ab  pop     rbx
0x1800051ac  retn
```
