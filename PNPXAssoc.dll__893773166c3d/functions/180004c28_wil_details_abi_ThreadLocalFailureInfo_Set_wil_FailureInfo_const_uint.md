# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004c28`
- end: `0x180004e44`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038a0`

## callees

- `0x1800048e8`
- `0x180004c28`
- `0x180012dce`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004d74`
- `msvcrt!memcpy_s` at `0x180004dc5`
- `msvcrt!memcpy_s` at `0x180004e10`
- `msvcrt!memcpy_s` at `0x180004d74`
- `msvcrt!memcpy_s` at `0x180004dc5`
- `msvcrt!memcpy_s` at `0x180004e10`
- `KERNEL32!HeapFree` at `0x180004d1e`
- `KERNEL32!HeapFree` at `0x180004d1e`
- `KERNEL32!GetProcessHeap` at `0x180004d10`
- `KERNEL32!GetProcessHeap` at `0x180004d10`

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
0x180004c28  push    rbx
0x180004c2a  push    rbp
0x180004c2b  push    rsi
0x180004c2c  push    rdi
0x180004c2d  push    r12
0x180004c2f  push    r13
0x180004c31  push    r14
0x180004c33  push    r15
0x180004c35  sub     rsp, 28h
0x180004c39  mov     [rcx+4], r8d
0x180004c3d  xor     r13d, r13d
0x180004c40  mov     eax, [rdx+8]
0x180004c43  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004c47  mov     [rcx+8], eax
0x180004c4a  mov     rdi, rcx
0x180004c4d  mov     [rcx+10h], r13
0x180004c51  mov     r12, rdx
0x180004c54  movzx   eax, word ptr [rdx+40h]
0x180004c58  mov     [rcx+18h], ax
0x180004c5c  mov     al, [rdx]
0x180004c5e  mov     [rcx+1Ah], al
0x180004c61  mov     [rcx+20h], r13
0x180004c65  mov     rax, [rdx+88h]
0x180004c6c  mov     [rcx+28h], rax
0x180004c70  mov     rax, [rdx+90h]
0x180004c77  mov     [rcx+30h], rax
0x180004c7b  mov     [rcx+38h], r13
0x180004c7f  mov     rcx, [rdx+38h]
0x180004c83  lea     edx, [rbp+2]
0x180004c86  test    rcx, rcx
0x180004c89  jnz     short loc_180004C90
0x180004c8b  mov     r8d, edx
0x180004c8e  jmp     short loc_180004CA0
0x180004c90  mov     rax, rbp
0x180004c93  inc     rax
0x180004c96  cmp     [rcx+rax], r13b
0x180004c9a  jnz     short loc_180004C93
0x180004c9c  lea     r8, [rax+1]; unsigned __int64
0x180004ca0  mov     rcx, [r12+80h]
0x180004ca8  test    rcx, rcx
0x180004cab  jz      short loc_180004CBD
0x180004cad  mov     rax, rbp
0x180004cb0  inc     rax
0x180004cb3  cmp     [rcx+rax], r13b
0x180004cb7  jnz     short loc_180004CB0
0x180004cb9  lea     rdx, [rax+1]
0x180004cbd  mov     rcx, [r12+18h]
0x180004cc2  test    rcx, rcx
0x180004cc5  jnz     short loc_180004CCC
0x180004cc7  lea     eax, [rcx+2]
0x180004cca  jmp     short loc_180004CE1
0x180004ccc  mov     rax, rbp
0x180004ccf  inc     rax
0x180004cd2  cmp     [rcx+rax*2], r13w
0x180004cd7  jnz     short loc_180004CCF
0x180004cd9  lea     rax, ds:2[rax*2]
0x180004ce1  lea     r14, [rdx+rax]
0x180004ce5  add     r14, r8
0x180004ce8  lea     rsi, [rdi+48h]
0x180004cec  cmp     [rdi+40h], r13
0x180004cf0  jz      short loc_180004CF7
0x180004cf2  cmp     [rsi], r14
0x180004cf5  jnb     short loc_180004D2B
0x180004cf7  mov     rdx, r14; dwBytes
0x180004cfa  mov     ecx, 8; dwFlags
0x180004cff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d04  mov     r15, rax
0x180004d07  test    rax, rax
0x180004d0a  jz      short loc_180004D2B
0x180004d0c  mov     rbx, [rdi+40h]
0x180004d10  call    cs:__imp_GetProcessHeap
0x180004d16  mov     r8, rbx; lpMem
0x180004d19  xor     edx, edx; dwFlags
0x180004d1b  mov     rcx, rax; hHeap
0x180004d1e  call    cs:__imp_HeapFree
0x180004d24  mov     [rdi+40h], r15
0x180004d28  mov     [rsi], r14
0x180004d2b  mov     rbx, [rdi+40h]
0x180004d2f  test    rbx, rbx
0x180004d32  jz      loc_180004E33
0x180004d38  mov     rdx, [rsi]; DestinationSize
0x180004d3b  lea     rsi, [rdx+rbx]
0x180004d3f  cmp     rbx, rsi
0x180004d42  jz      short loc_180004D83
0x180004d44  mov     r8, [r12+38h]; Source
0x180004d49  test    r8, r8
0x180004d4c  jz      short loc_180004D83
0x180004d4e  cmp     [r8], r13b
0x180004d51  jz      short loc_180004D83
0x180004d53  mov     rax, rbp
0x180004d56  inc     rax
0x180004d59  cmp     [r8+rax], r13b
0x180004d5d  jnz     short loc_180004D56
0x180004d5f  lea     r14, [rax+1]
0x180004d63  cmp     rdx, r14
0x180004d66  jnb     short loc_180004D6E
0x180004d68  mov     [rdi+10h], r13
0x180004d6c  jmp     short loc_180004D8C
0x180004d6e  mov     r9, r14; SourceSize
0x180004d71  mov     rcx, rbx; Destination
0x180004d74  call    cs:__imp_memcpy_s
0x180004d7a  mov     [rdi+10h], rbx
0x180004d7e  add     rbx, r14
0x180004d81  jmp     short loc_180004D87
0x180004d83  mov     [rdi+10h], r13
0x180004d87  cmp     rbx, rsi
0x180004d8a  jz      short loc_180004DD4
0x180004d8c  mov     r8, [r12+80h]; Source
0x180004d94  test    r8, r8
0x180004d97  jz      short loc_180004DD4
0x180004d99  cmp     [r8], r13b
0x180004d9c  jz      short loc_180004DD4
0x180004d9e  mov     rax, rbp
0x180004da1  inc     rax
0x180004da4  cmp     [r8+rax], r13b
0x180004da8  jnz     short loc_180004DA1
0x180004daa  mov     rdx, rsi
0x180004dad  lea     r14, [rax+1]
0x180004db1  sub     rdx, rbx; DestinationSize
0x180004db4  cmp     rdx, r14
0x180004db7  jnb     short loc_180004DBF
0x180004db9  mov     [rdi+20h], r13
0x180004dbd  jmp     short loc_180004DDD
0x180004dbf  mov     r9, r14; SourceSize
0x180004dc2  mov     rcx, rbx; Destination
0x180004dc5  call    cs:__imp_memcpy_s
0x180004dcb  mov     [rdi+20h], rbx
0x180004dcf  add     rbx, r14
0x180004dd2  jmp     short loc_180004DD8
0x180004dd4  mov     [rdi+20h], r13
0x180004dd8  cmp     rbx, rsi
0x180004ddb  jz      short loc_180004E1F
0x180004ddd  mov     r8, [r12+18h]; Source
0x180004de2  test    r8, r8
0x180004de5  jz      short loc_180004E1F
0x180004de7  cmp     [r8], r13w
0x180004deb  jz      short loc_180004E1F
0x180004ded  inc     rbp
0x180004df0  cmp     [r8+rbp*2], r13w
0x180004df5  jnz     short loc_180004DED
0x180004df7  mov     rdx, rsi
0x180004dfa  lea     r14, ds:2[rbp*2]
0x180004e02  sub     rdx, rbx; DestinationSize
0x180004e05  cmp     rdx, r14
0x180004e08  jb      short loc_180004E1F
0x180004e0a  mov     r9, r14; SourceSize
0x180004e0d  mov     rcx, rbx; Destination
0x180004e10  call    cs:__imp_memcpy_s
0x180004e16  mov     [rdi+38h], rbx
0x180004e1a  add     rbx, r14
0x180004e1d  jmp     short loc_180004E23
0x180004e1f  mov     [rdi+38h], r13
0x180004e23  sub     rsi, rbx
0x180004e26  xor     edx, edx; Val
0x180004e28  mov     r8, rsi; Size
0x180004e2b  mov     rcx, rbx; void *
0x180004e2e  call    memset_0
0x180004e33  add     rsp, 28h
0x180004e37  pop     r15
0x180004e39  pop     r14
0x180004e3b  pop     r13
0x180004e3d  pop     r12
0x180004e3f  pop     rdi
0x180004e40  pop     rsi
0x180004e41  pop     rbp
0x180004e42  pop     rbx
0x180004e43  retn
```
