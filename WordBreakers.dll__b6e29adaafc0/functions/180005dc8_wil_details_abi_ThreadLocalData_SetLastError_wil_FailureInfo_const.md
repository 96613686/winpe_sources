# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005dc8`
- end: `0x18000604d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800046e0`

## callees

- `0x18000390c`
- `0x180005678`
- `0x180005dc8`
- `0x18000b612`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006017`
- `msvcrt!memcpy_s` at `0x180006017`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f88`

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
0x180005dc8  push    rbx
0x180005dca  push    rbp
0x180005dcb  push    rsi
0x180005dcc  push    rdi
0x180005dcd  push    r12
0x180005dcf  push    r13
0x180005dd1  push    r14
0x180005dd3  push    r15
0x180005dd5  sub     rsp, 28h
0x180005dd9  mov     esi, [rcx+10h]
0x180005ddc  xor     r12d, r12d
0x180005ddf  mov     r15, rdx
0x180005de2  mov     rbx, rcx
0x180005de5  mov     ebp, 50h ; 'P'
0x180005dea  cmp     [rcx+18h], r12
0x180005dee  jnz     short loc_180005E25
0x180005df0  test    esi, esi
0x180005df2  jz      short loc_180005E25
0x180005df4  mov     edx, 190h; dwBytes
0x180005df9  lea     ecx, [rbp-48h]; dwFlags
0x180005dfc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005e01  mov     [rbx+18h], rax
0x180005e05  test    rax, rax
0x180005e08  jz      short loc_180005E25
0x180005e0a  mov     dword ptr [rbx+20h], 5
0x180005e11  lea     rcx, [rax+190h]
0x180005e18  jmp     short loc_180005E20
0x180005e1a  mov     [rax], bp
0x180005e1d  add     rax, rbp
0x180005e20  cmp     rax, rcx
0x180005e23  jnz     short loc_180005E1A
0x180005e25  mov     rdi, [rbx+18h]
0x180005e29  test    rdi, rdi
0x180005e2c  jz      loc_18000603C
0x180005e32  test    esi, esi
0x180005e34  jz      short loc_180005E6C
0x180005e36  movzx   eax, word ptr [rbx+20h]
0x180005e3a  mov     rcx, rdi
0x180005e3d  lea     rdx, [rax+rax*4]
0x180005e41  shl     rdx, 4
0x180005e45  add     rdx, rdi
0x180005e48  cmp     rdi, rdx
0x180005e4b  jz      short loc_180005E6C
0x180005e4d  mov     r8d, [rbx+10h]
0x180005e51  cmp     [rcx+4], r8d
0x180005e55  jbe     short loc_180005E64
0x180005e57  mov     eax, [r15+8]
0x180005e5b  cmp     [rcx+8], eax
0x180005e5e  jz      loc_18000603C
0x180005e64  add     rcx, rbp
0x180005e67  cmp     rcx, rdx
0x180005e6a  jnz     short loc_180005E51
0x180005e6c  movzx   eax, word ptr [rbx+22h]
0x180005e70  mov     r8d, 1
0x180005e76  movzx   ecx, word ptr [rbx+20h]
0x180005e7a  add     eax, r8d
0x180005e7d  xor     edx, edx
0x180005e7f  div     ecx
0x180005e81  mov     ecx, r8d
0x180005e84  movzx   eax, dx
0x180005e87  mov     [rbx+22h], dx
0x180005e8b  lea     rsi, [rax+rax*4]
0x180005e8f  mov     rax, [rbx+8]
0x180005e93  shl     rsi, 4
0x180005e97  lock xadd [rax], ecx
0x180005e9b  add     ecx, r8d
0x180005e9e  lea     r13, [rsi+rdi]
0x180005ea2  mov     [rsi+rdi+4], ecx
0x180005ea6  lea     rbx, [rdi+20h]
0x180005eaa  mov     eax, [r15+8]
0x180005eae  add     rbx, rsi
0x180005eb1  mov     [rsi+rdi+8], eax
0x180005eb5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005eb9  mov     [r13+10h], r12
0x180005ebd  movzx   eax, word ptr [r15+40h]
0x180005ec2  mov     [rsi+rdi+18h], ax
0x180005ec7  mov     al, [r15]
0x180005eca  mov     [rsi+rdi+1Ah], al
0x180005ece  mov     [rbx], r12
0x180005ed1  mov     rax, [r15+88h]
0x180005ed8  mov     [rsi+rdi+28h], rax
0x180005edd  mov     rax, [r15+90h]
0x180005ee4  mov     [rsi+rdi+30h], rax
0x180005ee9  mov     [rsi+rdi+38h], r12
0x180005eee  mov     rcx, [r15+38h]
0x180005ef2  test    rcx, rcx
0x180005ef5  jnz     short loc_180005EFC
0x180005ef7  mov     edx, r8d
0x180005efa  jmp     short loc_180005F0C
0x180005efc  mov     rax, r14
0x180005eff  inc     rax
0x180005f02  cmp     [rcx+rax], r12b
0x180005f06  jnz     short loc_180005EFF
0x180005f08  lea     rdx, [rax+1]
0x180005f0c  mov     rcx, [r15+80h]
0x180005f13  test    rcx, rcx
0x180005f16  jz      short loc_180005F28
0x180005f18  mov     rax, r14
0x180005f1b  inc     rax
0x180005f1e  cmp     [rcx+rax], r12b
0x180005f22  jnz     short loc_180005F1B
0x180005f24  lea     r8, [rax+1]; unsigned __int64
0x180005f28  mov     rcx, [r15+18h]
0x180005f2c  test    rcx, rcx
0x180005f2f  jnz     short loc_180005F36
0x180005f31  lea     eax, [rcx+2]
0x180005f34  jmp     short loc_180005F4B
0x180005f36  mov     rax, r14
0x180005f39  inc     rax
0x180005f3c  cmp     [rcx+rax*2], r12w
0x180005f41  jnz     short loc_180005F39
0x180005f43  lea     rax, ds:2[rax*2]
0x180005f4b  lea     rbp, [r8+rax]
0x180005f4f  add     rbp, rdx
0x180005f52  cmp     [rsi+rdi+40h], r12
0x180005f57  jz      short loc_180005F60
0x180005f59  cmp     [rsi+rdi+48h], rbp
0x180005f5e  jnb     short loc_180005FA2
0x180005f60  mov     rdx, rbp; dwBytes
0x180005f63  mov     ecx, 8; dwFlags
0x180005f68  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005f6d  mov     r12, rax
0x180005f70  test    rax, rax
0x180005f73  jz      short loc_180005F9F
0x180005f75  mov     rbx, [rsi+rdi+40h]
0x180005f7a  call    cs:__imp_GetProcessHeap
0x180005f80  mov     r8, rbx; lpMem
0x180005f83  xor     edx, edx; dwFlags
0x180005f85  mov     rcx, rax; hHeap
0x180005f88  call    cs:__imp_HeapFree
0x180005f8e  lea     rbx, [rdi+20h]
0x180005f92  mov     [rsi+rdi+40h], r12
0x180005f97  add     rbx, rsi
0x180005f9a  mov     [rsi+rdi+48h], rbp
0x180005f9f  xor     r12d, r12d
0x180005fa2  mov     rcx, [rsi+rdi+40h]
0x180005fa7  test    rcx, rcx
0x180005faa  jz      loc_18000603C
0x180005fb0  mov     rbp, [rsi+rdi+48h]
0x180005fb5  lea     r9, [r13+10h]
0x180005fb9  mov     r8, [r15+38h]
0x180005fbd  add     rbp, rcx
0x180005fc0  mov     rdx, rbp
0x180005fc3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005fc8  mov     r8, [r15+80h]
0x180005fcf  mov     r9, rbx
0x180005fd2  mov     rdx, rbp
0x180005fd5  mov     rcx, rax
0x180005fd8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005fdd  mov     rbx, rax
0x180005fe0  cmp     rax, rbp
0x180005fe3  jz      short loc_180006027
0x180005fe5  mov     r8, [r15+18h]; Source
0x180005fe9  test    r8, r8
0x180005fec  jz      short loc_180006027
0x180005fee  cmp     [r8], r12w
0x180005ff2  jz      short loc_180006027
0x180005ff4  inc     r14
0x180005ff7  cmp     [r8+r14*2], r12w
0x180005ffc  jnz     short loc_180005FF4
0x180005ffe  mov     rdx, rbp
0x180006001  lea     r14, ds:2[r14*2]
0x180006009  sub     rdx, rbx; DestinationSize
0x18000600c  cmp     rdx, r14
0x18000600f  jb      short loc_180006027
0x180006011  mov     r9, r14; SourceSize
0x180006014  mov     rcx, rbx; Destination
0x180006017  call    cs:__imp_memcpy_s
0x18000601d  mov     [rsi+rdi+38h], rbx
0x180006022  add     rbx, r14
0x180006025  jmp     short loc_18000602C
0x180006027  mov     [rsi+rdi+38h], r12
0x18000602c  sub     rbp, rbx
0x18000602f  xor     edx, edx; Val
0x180006031  mov     r8, rbp; Size
0x180006034  mov     rcx, rbx; void *
0x180006037  call    memset_0
0x18000603c  add     rsp, 28h
0x180006040  pop     r15
0x180006042  pop     r14
0x180006044  pop     r13
0x180006046  pop     r12
0x180006048  pop     rdi
0x180006049  pop     rsi
0x18000604a  pop     rbp
0x18000604b  pop     rbx
0x18000604c  retn
```
