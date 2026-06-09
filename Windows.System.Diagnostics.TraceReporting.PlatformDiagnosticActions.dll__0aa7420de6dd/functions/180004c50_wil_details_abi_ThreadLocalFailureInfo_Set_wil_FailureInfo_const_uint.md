# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004c50`
- end: `0x180004e69`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003700`

## callees

- `0x180002058`
- `0x180004758`
- `0x180004c50`
- `0x180005bf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d38`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x180004c50  push    rbx
0x180004c52  push    rbp
0x180004c53  push    rsi
0x180004c54  push    rdi
0x180004c55  push    r12
0x180004c57  push    r13
0x180004c59  push    r14
0x180004c5b  push    r15
0x180004c5d  sub     rsp, 28h
0x180004c61  mov     [rcx+4], r8d
0x180004c65  xor     r13d, r13d
0x180004c68  mov     eax, [rdx+8]
0x180004c6b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004c6f  mov     [rcx+8], eax
0x180004c72  mov     rdi, rcx
0x180004c75  mov     [rcx+10h], r13
0x180004c79  mov     r12, rdx
0x180004c7c  movzx   eax, word ptr [rdx+40h]
0x180004c80  mov     [rcx+18h], ax
0x180004c84  mov     al, [rdx]
0x180004c86  mov     [rcx+1Ah], al
0x180004c89  mov     [rcx+20h], r13
0x180004c8d  mov     rax, [rdx+88h]
0x180004c94  mov     [rcx+28h], rax
0x180004c98  mov     rax, [rdx+90h]
0x180004c9f  mov     [rcx+30h], rax
0x180004ca3  mov     [rcx+38h], r13
0x180004ca7  mov     rcx, [rdx+38h]
0x180004cab  lea     edx, [rbp+2]
0x180004cae  test    rcx, rcx
0x180004cb1  jnz     short loc_180004CB8
0x180004cb3  mov     r8d, edx
0x180004cb6  jmp     short loc_180004CC8
0x180004cb8  mov     rax, rbp
0x180004cbb  inc     rax
0x180004cbe  cmp     [rcx+rax], r13b
0x180004cc2  jnz     short loc_180004CBB
0x180004cc4  lea     r8, [rax+1]; unsigned __int64
0x180004cc8  mov     rcx, [r12+80h]
0x180004cd0  test    rcx, rcx
0x180004cd3  jz      short loc_180004CE5
0x180004cd5  mov     rax, rbp
0x180004cd8  inc     rax
0x180004cdb  cmp     [rcx+rax], r13b
0x180004cdf  jnz     short loc_180004CD8
0x180004ce1  lea     rdx, [rax+1]
0x180004ce5  mov     rcx, [r12+18h]
0x180004cea  test    rcx, rcx
0x180004ced  jnz     short loc_180004CF4
0x180004cef  lea     eax, [rcx+2]
0x180004cf2  jmp     short loc_180004D09
0x180004cf4  mov     rax, rbp
0x180004cf7  inc     rax
0x180004cfa  cmp     [rcx+rax*2], r13w
0x180004cff  jnz     short loc_180004CF7
0x180004d01  lea     rax, ds:2[rax*2]
0x180004d09  lea     r14, [rdx+rax]
0x180004d0d  add     r14, r8
0x180004d10  lea     rsi, [rdi+48h]
0x180004d14  cmp     [rdi+40h], r13
0x180004d18  jz      short loc_180004D1F
0x180004d1a  cmp     [rsi], r14
0x180004d1d  jnb     short loc_180004D53
0x180004d1f  mov     rdx, r14; dwBytes
0x180004d22  mov     ecx, 8; dwFlags
0x180004d27  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d2c  mov     r15, rax
0x180004d2f  test    rax, rax
0x180004d32  jz      short loc_180004D53
0x180004d34  mov     rbx, [rdi+40h]
0x180004d38  call    cs:__imp_GetProcessHeap
0x180004d3e  mov     r8, rbx; lpMem
0x180004d41  xor     edx, edx; dwFlags
0x180004d43  mov     rcx, rax; hHeap
0x180004d46  call    cs:__imp_HeapFree
0x180004d4c  mov     [rdi+40h], r15
0x180004d50  mov     [rsi], r14
0x180004d53  mov     rbx, [rdi+40h]
0x180004d57  test    rbx, rbx
0x180004d5a  jz      loc_180004E58
0x180004d60  mov     rdx, [rsi]; DestinationSize
0x180004d63  lea     rsi, [rdx+rbx]
0x180004d67  cmp     rbx, rsi
0x180004d6a  jz      short loc_180004DAA
0x180004d6c  mov     r8, [r12+38h]; Source
0x180004d71  test    r8, r8
0x180004d74  jz      short loc_180004DAA
0x180004d76  cmp     [r8], r13b
0x180004d79  jz      short loc_180004DAA
0x180004d7b  mov     rax, rbp
0x180004d7e  inc     rax
0x180004d81  cmp     [r8+rax], r13b
0x180004d85  jnz     short loc_180004D7E
0x180004d87  lea     r14, [rax+1]
0x180004d8b  cmp     rdx, r14
0x180004d8e  jnb     short loc_180004D96
0x180004d90  mov     [rdi+10h], r13
0x180004d94  jmp     short loc_180004DB3
0x180004d96  mov     r9, r14; SourceSize
0x180004d99  mov     rcx, rbx; Destination
0x180004d9c  call    memcpy_s
0x180004da1  mov     [rdi+10h], rbx
0x180004da5  add     rbx, r14
0x180004da8  jmp     short loc_180004DAE
0x180004daa  mov     [rdi+10h], r13
0x180004dae  cmp     rbx, rsi
0x180004db1  jz      short loc_180004DFA
0x180004db3  mov     r8, [r12+80h]; Source
0x180004dbb  test    r8, r8
0x180004dbe  jz      short loc_180004DFA
0x180004dc0  cmp     [r8], r13b
0x180004dc3  jz      short loc_180004DFA
0x180004dc5  mov     rax, rbp
0x180004dc8  inc     rax
0x180004dcb  cmp     [r8+rax], r13b
0x180004dcf  jnz     short loc_180004DC8
0x180004dd1  mov     rdx, rsi
0x180004dd4  lea     r14, [rax+1]
0x180004dd8  sub     rdx, rbx; DestinationSize
0x180004ddb  cmp     rdx, r14
0x180004dde  jnb     short loc_180004DE6
0x180004de0  mov     [rdi+20h], r13
0x180004de4  jmp     short loc_180004E03
0x180004de6  mov     r9, r14; SourceSize
0x180004de9  mov     rcx, rbx; Destination
0x180004dec  call    memcpy_s
0x180004df1  mov     [rdi+20h], rbx
0x180004df5  add     rbx, r14
0x180004df8  jmp     short loc_180004DFE
0x180004dfa  mov     [rdi+20h], r13
0x180004dfe  cmp     rbx, rsi
0x180004e01  jz      short loc_180004E44
0x180004e03  mov     r8, [r12+18h]; Source
0x180004e08  test    r8, r8
0x180004e0b  jz      short loc_180004E44
0x180004e0d  cmp     [r8], r13w
0x180004e11  jz      short loc_180004E44
0x180004e13  inc     rbp
0x180004e16  cmp     [r8+rbp*2], r13w
0x180004e1b  jnz     short loc_180004E13
0x180004e1d  mov     rdx, rsi
0x180004e20  lea     r14, ds:2[rbp*2]
0x180004e28  sub     rdx, rbx; DestinationSize
0x180004e2b  cmp     rdx, r14
0x180004e2e  jb      short loc_180004E44
0x180004e30  mov     r9, r14; SourceSize
0x180004e33  mov     rcx, rbx; Destination
0x180004e36  call    memcpy_s
0x180004e3b  mov     [rdi+38h], rbx
0x180004e3f  add     rbx, r14
0x180004e42  jmp     short loc_180004E48
0x180004e44  mov     [rdi+38h], r13
0x180004e48  sub     rsi, rbx
0x180004e4b  xor     edx, edx; Val
0x180004e4d  mov     r8, rsi; Size
0x180004e50  mov     rcx, rbx; void *
0x180004e53  call    memset_0
0x180004e58  add     rsp, 28h
0x180004e5c  pop     r15
0x180004e5e  pop     r14
0x180004e60  pop     r13
0x180004e62  pop     r12
0x180004e64  pop     rdi
0x180004e65  pop     rsi
0x180004e66  pop     rbp
0x180004e67  pop     rbx
0x180004e68  retn
```
