# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007cd4`
- end: `0x180007eed`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005210`

## callees

- `0x1800024ac`
- `0x180006478`
- `0x180007cd4`
- `0x1800099e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dca`

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
0x180007cd4  push    rbx
0x180007cd6  push    rbp
0x180007cd7  push    rsi
0x180007cd8  push    rdi
0x180007cd9  push    r12
0x180007cdb  push    r13
0x180007cdd  push    r14
0x180007cdf  push    r15
0x180007ce1  sub     rsp, 28h
0x180007ce5  mov     [rcx+4], r8d
0x180007ce9  xor     r13d, r13d
0x180007cec  mov     eax, [rdx+8]
0x180007cef  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007cf3  mov     [rcx+8], eax
0x180007cf6  mov     rdi, rcx
0x180007cf9  mov     [rcx+10h], r13
0x180007cfd  mov     r12, rdx
0x180007d00  movzx   eax, word ptr [rdx+40h]
0x180007d04  mov     [rcx+18h], ax
0x180007d08  mov     al, [rdx]
0x180007d0a  mov     [rcx+1Ah], al
0x180007d0d  mov     [rcx+20h], r13
0x180007d11  mov     rax, [rdx+88h]
0x180007d18  mov     [rcx+28h], rax
0x180007d1c  mov     rax, [rdx+90h]
0x180007d23  mov     [rcx+30h], rax
0x180007d27  mov     [rcx+38h], r13
0x180007d2b  mov     rcx, [rdx+38h]
0x180007d2f  lea     edx, [rbp+2]
0x180007d32  test    rcx, rcx
0x180007d35  jnz     short loc_180007D3C
0x180007d37  mov     r8d, edx
0x180007d3a  jmp     short loc_180007D4C
0x180007d3c  mov     rax, rbp
0x180007d3f  inc     rax
0x180007d42  cmp     [rcx+rax], r13b
0x180007d46  jnz     short loc_180007D3F
0x180007d48  lea     r8, [rax+1]; unsigned __int64
0x180007d4c  mov     rcx, [r12+80h]
0x180007d54  test    rcx, rcx
0x180007d57  jz      short loc_180007D69
0x180007d59  mov     rax, rbp
0x180007d5c  inc     rax
0x180007d5f  cmp     [rcx+rax], r13b
0x180007d63  jnz     short loc_180007D5C
0x180007d65  lea     rdx, [rax+1]
0x180007d69  mov     rcx, [r12+18h]
0x180007d6e  test    rcx, rcx
0x180007d71  jnz     short loc_180007D78
0x180007d73  lea     eax, [rcx+2]
0x180007d76  jmp     short loc_180007D8D
0x180007d78  mov     rax, rbp
0x180007d7b  inc     rax
0x180007d7e  cmp     [rcx+rax*2], r13w
0x180007d83  jnz     short loc_180007D7B
0x180007d85  lea     rax, ds:2[rax*2]
0x180007d8d  lea     r14, [rdx+rax]
0x180007d91  add     r14, r8
0x180007d94  lea     rsi, [rdi+48h]
0x180007d98  cmp     [rdi+40h], r13
0x180007d9c  jz      short loc_180007DA3
0x180007d9e  cmp     [rsi], r14
0x180007da1  jnb     short loc_180007DD7
0x180007da3  mov     rdx, r14; dwBytes
0x180007da6  mov     ecx, 8; dwFlags
0x180007dab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007db0  mov     r15, rax
0x180007db3  test    rax, rax
0x180007db6  jz      short loc_180007DD7
0x180007db8  mov     rbx, [rdi+40h]
0x180007dbc  call    cs:__imp_GetProcessHeap
0x180007dc2  mov     r8, rbx; lpMem
0x180007dc5  xor     edx, edx; dwFlags
0x180007dc7  mov     rcx, rax; hHeap
0x180007dca  call    cs:__imp_HeapFree
0x180007dd0  mov     [rdi+40h], r15
0x180007dd4  mov     [rsi], r14
0x180007dd7  mov     rbx, [rdi+40h]
0x180007ddb  test    rbx, rbx
0x180007dde  jz      loc_180007EDC
0x180007de4  mov     rdx, [rsi]; DestinationSize
0x180007de7  lea     rsi, [rdx+rbx]
0x180007deb  cmp     rbx, rsi
0x180007dee  jz      short loc_180007E2E
0x180007df0  mov     r8, [r12+38h]; Source
0x180007df5  test    r8, r8
0x180007df8  jz      short loc_180007E2E
0x180007dfa  cmp     [r8], r13b
0x180007dfd  jz      short loc_180007E2E
0x180007dff  mov     rax, rbp
0x180007e02  inc     rax
0x180007e05  cmp     [r8+rax], r13b
0x180007e09  jnz     short loc_180007E02
0x180007e0b  lea     r14, [rax+1]
0x180007e0f  cmp     rdx, r14
0x180007e12  jnb     short loc_180007E1A
0x180007e14  mov     [rdi+10h], r13
0x180007e18  jmp     short loc_180007E37
0x180007e1a  mov     r9, r14; SourceSize
0x180007e1d  mov     rcx, rbx; Destination
0x180007e20  call    memcpy_s
0x180007e25  mov     [rdi+10h], rbx
0x180007e29  add     rbx, r14
0x180007e2c  jmp     short loc_180007E32
0x180007e2e  mov     [rdi+10h], r13
0x180007e32  cmp     rbx, rsi
0x180007e35  jz      short loc_180007E7E
0x180007e37  mov     r8, [r12+80h]; Source
0x180007e3f  test    r8, r8
0x180007e42  jz      short loc_180007E7E
0x180007e44  cmp     [r8], r13b
0x180007e47  jz      short loc_180007E7E
0x180007e49  mov     rax, rbp
0x180007e4c  inc     rax
0x180007e4f  cmp     [r8+rax], r13b
0x180007e53  jnz     short loc_180007E4C
0x180007e55  mov     rdx, rsi
0x180007e58  lea     r14, [rax+1]
0x180007e5c  sub     rdx, rbx; DestinationSize
0x180007e5f  cmp     rdx, r14
0x180007e62  jnb     short loc_180007E6A
0x180007e64  mov     [rdi+20h], r13
0x180007e68  jmp     short loc_180007E87
0x180007e6a  mov     r9, r14; SourceSize
0x180007e6d  mov     rcx, rbx; Destination
0x180007e70  call    memcpy_s
0x180007e75  mov     [rdi+20h], rbx
0x180007e79  add     rbx, r14
0x180007e7c  jmp     short loc_180007E82
0x180007e7e  mov     [rdi+20h], r13
0x180007e82  cmp     rbx, rsi
0x180007e85  jz      short loc_180007EC8
0x180007e87  mov     r8, [r12+18h]; Source
0x180007e8c  test    r8, r8
0x180007e8f  jz      short loc_180007EC8
0x180007e91  cmp     [r8], r13w
0x180007e95  jz      short loc_180007EC8
0x180007e97  inc     rbp
0x180007e9a  cmp     [r8+rbp*2], r13w
0x180007e9f  jnz     short loc_180007E97
0x180007ea1  mov     rdx, rsi
0x180007ea4  lea     r14, ds:2[rbp*2]
0x180007eac  sub     rdx, rbx; DestinationSize
0x180007eaf  cmp     rdx, r14
0x180007eb2  jb      short loc_180007EC8
0x180007eb4  mov     r9, r14; SourceSize
0x180007eb7  mov     rcx, rbx; Destination
0x180007eba  call    memcpy_s
0x180007ebf  mov     [rdi+38h], rbx
0x180007ec3  add     rbx, r14
0x180007ec6  jmp     short loc_180007ECC
0x180007ec8  mov     [rdi+38h], r13
0x180007ecc  sub     rsi, rbx
0x180007ecf  xor     edx, edx; Val
0x180007ed1  mov     r8, rsi; Size
0x180007ed4  mov     rcx, rbx; void *
0x180007ed7  call    memset_0
0x180007edc  add     rsp, 28h
0x180007ee0  pop     r15
0x180007ee2  pop     r14
0x180007ee4  pop     r13
0x180007ee6  pop     r12
0x180007ee8  pop     rdi
0x180007ee9  pop     rsi
0x180007eea  pop     rbp
0x180007eeb  pop     rbx
0x180007eec  retn
```
