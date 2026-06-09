# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005a14`
- end: `0x140005c99`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004160`

## callees

- `0x14000314c`
- `0x1400050f8`
- `0x140005a14`
- `0x14000a33e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140005c63`
- `msvcrt!memcpy_s` at `0x140005c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bd4`

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
0x140005a14  push    rbx
0x140005a16  push    rbp
0x140005a17  push    rsi
0x140005a18  push    rdi
0x140005a19  push    r12
0x140005a1b  push    r13
0x140005a1d  push    r14
0x140005a1f  push    r15
0x140005a21  sub     rsp, 28h
0x140005a25  mov     esi, [rcx+10h]
0x140005a28  xor     r12d, r12d
0x140005a2b  mov     r15, rdx
0x140005a2e  mov     rbx, rcx
0x140005a31  mov     ebp, 50h ; 'P'
0x140005a36  cmp     [rcx+18h], r12
0x140005a3a  jnz     short loc_140005A71
0x140005a3c  test    esi, esi
0x140005a3e  jz      short loc_140005A71
0x140005a40  mov     edx, 190h; dwBytes
0x140005a45  lea     ecx, [rbp-48h]; dwFlags
0x140005a48  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005a4d  mov     [rbx+18h], rax
0x140005a51  test    rax, rax
0x140005a54  jz      short loc_140005A71
0x140005a56  mov     dword ptr [rbx+20h], 5
0x140005a5d  lea     rcx, [rax+190h]
0x140005a64  jmp     short loc_140005A6C
0x140005a66  mov     [rax], bp
0x140005a69  add     rax, rbp
0x140005a6c  cmp     rax, rcx
0x140005a6f  jnz     short loc_140005A66
0x140005a71  mov     rdi, [rbx+18h]
0x140005a75  test    rdi, rdi
0x140005a78  jz      loc_140005C88
0x140005a7e  test    esi, esi
0x140005a80  jz      short loc_140005AB8
0x140005a82  movzx   eax, word ptr [rbx+20h]
0x140005a86  mov     rcx, rdi
0x140005a89  lea     rdx, [rax+rax*4]
0x140005a8d  shl     rdx, 4
0x140005a91  add     rdx, rdi
0x140005a94  cmp     rdi, rdx
0x140005a97  jz      short loc_140005AB8
0x140005a99  mov     r8d, [rbx+10h]
0x140005a9d  cmp     [rcx+4], r8d
0x140005aa1  jbe     short loc_140005AB0
0x140005aa3  mov     eax, [r15+8]
0x140005aa7  cmp     [rcx+8], eax
0x140005aaa  jz      loc_140005C88
0x140005ab0  add     rcx, rbp
0x140005ab3  cmp     rcx, rdx
0x140005ab6  jnz     short loc_140005A9D
0x140005ab8  movzx   eax, word ptr [rbx+22h]
0x140005abc  mov     r8d, 1
0x140005ac2  movzx   ecx, word ptr [rbx+20h]
0x140005ac6  add     eax, r8d
0x140005ac9  xor     edx, edx
0x140005acb  div     ecx
0x140005acd  mov     ecx, r8d
0x140005ad0  movzx   eax, dx
0x140005ad3  mov     [rbx+22h], dx
0x140005ad7  lea     rsi, [rax+rax*4]
0x140005adb  mov     rax, [rbx+8]
0x140005adf  shl     rsi, 4
0x140005ae3  lock xadd [rax], ecx
0x140005ae7  add     ecx, r8d
0x140005aea  lea     r13, [rsi+rdi]
0x140005aee  mov     [rsi+rdi+4], ecx
0x140005af2  lea     rbx, [rdi+20h]
0x140005af6  mov     eax, [r15+8]
0x140005afa  add     rbx, rsi
0x140005afd  mov     [rsi+rdi+8], eax
0x140005b01  or      r14, 0FFFFFFFFFFFFFFFFh
0x140005b05  mov     [r13+10h], r12
0x140005b09  movzx   eax, word ptr [r15+40h]
0x140005b0e  mov     [rsi+rdi+18h], ax
0x140005b13  mov     al, [r15]
0x140005b16  mov     [rsi+rdi+1Ah], al
0x140005b1a  mov     [rbx], r12
0x140005b1d  mov     rax, [r15+88h]
0x140005b24  mov     [rsi+rdi+28h], rax
0x140005b29  mov     rax, [r15+90h]
0x140005b30  mov     [rsi+rdi+30h], rax
0x140005b35  mov     [rsi+rdi+38h], r12
0x140005b3a  mov     rcx, [r15+38h]
0x140005b3e  test    rcx, rcx
0x140005b41  jnz     short loc_140005B48
0x140005b43  mov     edx, r8d
0x140005b46  jmp     short loc_140005B58
0x140005b48  mov     rax, r14
0x140005b4b  inc     rax
0x140005b4e  cmp     [rcx+rax], r12b
0x140005b52  jnz     short loc_140005B4B
0x140005b54  lea     rdx, [rax+1]
0x140005b58  mov     rcx, [r15+80h]
0x140005b5f  test    rcx, rcx
0x140005b62  jz      short loc_140005B74
0x140005b64  mov     rax, r14
0x140005b67  inc     rax
0x140005b6a  cmp     [rcx+rax], r12b
0x140005b6e  jnz     short loc_140005B67
0x140005b70  lea     r8, [rax+1]; unsigned __int64
0x140005b74  mov     rcx, [r15+18h]
0x140005b78  test    rcx, rcx
0x140005b7b  jnz     short loc_140005B82
0x140005b7d  lea     eax, [rcx+2]
0x140005b80  jmp     short loc_140005B97
0x140005b82  mov     rax, r14
0x140005b85  inc     rax
0x140005b88  cmp     [rcx+rax*2], r12w
0x140005b8d  jnz     short loc_140005B85
0x140005b8f  lea     rax, ds:2[rax*2]
0x140005b97  lea     rbp, [r8+rax]
0x140005b9b  add     rbp, rdx
0x140005b9e  cmp     [rsi+rdi+40h], r12
0x140005ba3  jz      short loc_140005BAC
0x140005ba5  cmp     [rsi+rdi+48h], rbp
0x140005baa  jnb     short loc_140005BEE
0x140005bac  mov     rdx, rbp; dwBytes
0x140005baf  mov     ecx, 8; dwFlags
0x140005bb4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005bb9  mov     r12, rax
0x140005bbc  test    rax, rax
0x140005bbf  jz      short loc_140005BEB
0x140005bc1  mov     rbx, [rsi+rdi+40h]
0x140005bc6  call    cs:__imp_GetProcessHeap
0x140005bcc  mov     r8, rbx; lpMem
0x140005bcf  xor     edx, edx; dwFlags
0x140005bd1  mov     rcx, rax; hHeap
0x140005bd4  call    cs:__imp_HeapFree
0x140005bda  lea     rbx, [rdi+20h]
0x140005bde  mov     [rsi+rdi+40h], r12
0x140005be3  add     rbx, rsi
0x140005be6  mov     [rsi+rdi+48h], rbp
0x140005beb  xor     r12d, r12d
0x140005bee  mov     rcx, [rsi+rdi+40h]
0x140005bf3  test    rcx, rcx
0x140005bf6  jz      loc_140005C88
0x140005bfc  mov     rbp, [rsi+rdi+48h]
0x140005c01  lea     r9, [r13+10h]
0x140005c05  mov     r8, [r15+38h]
0x140005c09  add     rbp, rcx
0x140005c0c  mov     rdx, rbp
0x140005c0f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005c14  mov     r8, [r15+80h]
0x140005c1b  mov     r9, rbx
0x140005c1e  mov     rdx, rbp
0x140005c21  mov     rcx, rax
0x140005c24  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005c29  mov     rbx, rax
0x140005c2c  cmp     rax, rbp
0x140005c2f  jz      short loc_140005C73
0x140005c31  mov     r8, [r15+18h]; Source
0x140005c35  test    r8, r8
0x140005c38  jz      short loc_140005C73
0x140005c3a  cmp     [r8], r12w
0x140005c3e  jz      short loc_140005C73
0x140005c40  inc     r14
0x140005c43  cmp     [r8+r14*2], r12w
0x140005c48  jnz     short loc_140005C40
0x140005c4a  mov     rdx, rbp
0x140005c4d  lea     r14, ds:2[r14*2]
0x140005c55  sub     rdx, rbx; DestinationSize
0x140005c58  cmp     rdx, r14
0x140005c5b  jb      short loc_140005C73
0x140005c5d  mov     r9, r14; SourceSize
0x140005c60  mov     rcx, rbx; Destination
0x140005c63  call    cs:__imp_memcpy_s
0x140005c69  mov     [rsi+rdi+38h], rbx
0x140005c6e  add     rbx, r14
0x140005c71  jmp     short loc_140005C78
0x140005c73  mov     [rsi+rdi+38h], r12
0x140005c78  sub     rbp, rbx
0x140005c7b  xor     edx, edx; Val
0x140005c7d  mov     r8, rbp; Size
0x140005c80  mov     rcx, rbx; void *
0x140005c83  call    memset_0
0x140005c88  add     rsp, 28h
0x140005c8c  pop     r15
0x140005c8e  pop     r14
0x140005c90  pop     r13
0x140005c92  pop     r12
0x140005c94  pop     rdi
0x140005c95  pop     rsi
0x140005c96  pop     rbp
0x140005c97  pop     rbx
0x140005c98  retn
```
