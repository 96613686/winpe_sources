# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180014bf0`
- end: `0x180014ecc`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `732`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800151a0`

## callees

- `0x180012e70`
- `0x180014bf0`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180014cfd`
- `KERNEL32!HeapFree` at `0x180014cfd`
- `KERNEL32!GetProcessHeap` at `0x180014cef`
- `KERNEL32!GetProcessHeap` at `0x180014cef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180014df2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180014e75`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180014df2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180014e75`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180014de6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180014e69`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180014de6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180014e69`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  bool v10; // zf
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rbp
  unsigned __int64 *v17; // rdi
  LPVOID v18; // r15
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  char *v21; // rbx
  unsigned __int64 v22; // rcx
  char **v23; // rdi
  _BYTE *v24; // rdx
  char *v25; // rbp
  __int64 v26; // rax
  __int64 v27; // r15
  _BYTE *v28; // rdx
  char **v29; // rdi
  __int64 v30; // rax
  size_t v31; // r15
  _WORD *v32; // rdx
  char **v33; // rdi
  size_t v34; // rsi

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  v5 = -1;
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
      v10 = *(_BYTE *)(v6 + v9++ + 1) == 0;
    while ( !v10 );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v11 = *((_QWORD *)a2 + 16);
  if ( v11 )
  {
    v12 = -1;
    do
      v10 = *(_BYTE *)(v11 + v12++ + 1) == 0;
    while ( !v10 );
    v7 = v12 + 1;
  }
  v13 = *((_QWORD *)a2 + 3);
  if ( v13 )
  {
    v15 = -1;
    do
      v10 = *(_WORD *)(v13 + 2 * v15++ + 2) == 0;
    while ( !v10 );
    v14 = 2 * v15 + 2;
  }
  else
  {
    v14 = 2;
  }
  v16 = v8 + v14 + v7;
  v17 = (unsigned __int64 *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v17 < v16 )
  {
    v18 = wil::details::ProcessHeapAlloc(8u, v8 + v14 + v7);
    if ( v18 )
    {
      v19 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v19);
      *((_QWORD *)this + 8) = v18;
      *v17 = v16;
    }
  }
  v21 = (char *)*((_QWORD *)this + 8);
  if ( v21 )
  {
    v22 = *v17;
    v23 = (char **)((char *)this + 16);
    v24 = (_BYTE *)*((_QWORD *)a2 + 7);
    v25 = &v21[v22];
    if ( v21 != &v21[v22] && v24 && *v24 )
    {
      v26 = -1;
      do
        v10 = v24[++v26] == 0;
      while ( !v10 );
      v27 = v26 + 1;
      if ( v22 < v26 + 1 )
      {
        if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
          *v23 = 0;
        v28 = (_BYTE *)*((_QWORD *)a2 + 16);
        v29 = (char **)((char *)this + 32);
LABEL_37:
        if ( v28 && *v28 )
        {
          v30 = -1;
          do
            v10 = v28[++v30] == 0;
          while ( !v10 );
          v31 = v30 + 1;
          if ( v25 - v21 < (unsigned __int64)(v30 + 1) )
          {
            if ( v29 )
              *v29 = 0;
            v32 = (_WORD *)*((_QWORD *)a2 + 3);
            v33 = (char **)((char *)this + 56);
LABEL_55:
            if ( v32 && *v32 )
            {
              do
                v10 = v32[++v5] == 0;
              while ( !v10 );
              v34 = 2 * v5 + 2;
              if ( v25 - v21 >= v34 )
              {
                if ( v34 )
                {
                  if ( v21 )
                  {
                    _mm_lfence();
                    memmove(v21, v32, v34);
                  }
                  else
                  {
                    *_errno() = 22;
                    _invalid_parameter_noinfo();
                  }
                }
                if ( v33 )
                  *v33 = v21;
                v21 += v34;
LABEL_68:
                memset(v21, 0, v25 - v21);
                return;
              }
            }
LABEL_66:
            if ( v33 )
              *v33 = 0;
            goto LABEL_68;
          }
          if ( v30 != -1 )
          {
            if ( v21 )
            {
              _mm_lfence();
              memmove(v21, v28, v31);
            }
            else
            {
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
          }
          if ( v29 )
            *v29 = v21;
          v21 += v31;
LABEL_54:
          v32 = (_WORD *)*((_QWORD *)a2 + 3);
          v33 = (char **)((char *)this + 56);
          if ( v21 == v25 )
            goto LABEL_66;
          goto LABEL_55;
        }
LABEL_52:
        if ( v29 )
          *v29 = 0;
        goto LABEL_54;
      }
      if ( v26 != -1 )
      {
        _mm_lfence();
        memmove(*((void **)this + 8), v24, v26 + 1);
      }
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v23 = v21;
      v21 += v27;
    }
    else if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
    {
      *v23 = 0;
    }
    v28 = (_BYTE *)*((_QWORD *)a2 + 16);
    v29 = (char **)((char *)this + 32);
    if ( v21 == v25 )
      goto LABEL_52;
    goto LABEL_37;
  }
}

```

## disassembly

```asm
0x180014bf0  mov     [rsp+arg_10], rbx
0x180014bf5  push    rbp
0x180014bf6  push    rsi
0x180014bf7  push    r12
0x180014bf9  push    r13
0x180014bfb  push    r14
0x180014bfd  sub     rsp, 20h
0x180014c01  mov     [rcx+4], r8d
0x180014c05  xor     r12d, r12d
0x180014c08  mov     eax, [rdx+8]
0x180014c0b  mov     r14, rcx
0x180014c0e  mov     [rcx+8], eax
0x180014c11  mov     r13, rdx
0x180014c14  mov     [rcx+10h], r12
0x180014c18  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180014c1f  movzx   eax, word ptr [rdx+40h]
0x180014c23  mov     [rcx+18h], ax
0x180014c27  movzx   eax, byte ptr [rdx]
0x180014c2a  mov     [rcx+1Ah], al
0x180014c2d  mov     [rcx+20h], r12
0x180014c31  mov     rax, [rdx+88h]
0x180014c38  mov     [rcx+28h], rax
0x180014c3c  mov     rax, [rdx+90h]
0x180014c43  mov     [rcx+30h], rax
0x180014c47  mov     [rcx+38h], r12
0x180014c4b  mov     rcx, [rdx+38h]
0x180014c4f  mov     edx, 1
0x180014c54  test    rcx, rcx
0x180014c57  jnz     short loc_180014C5E
0x180014c59  mov     r8d, edx
0x180014c5c  jmp     short loc_180014C70
0x180014c5e  mov     rax, rsi
0x180014c61  cmp     [rcx+rax+1], r12b
0x180014c66  lea     rax, [rax+1]
0x180014c6a  jnz     short loc_180014C61
0x180014c6c  lea     r8, [rax+1]; unsigned __int64
0x180014c70  mov     rcx, [r13+80h]
0x180014c77  test    rcx, rcx
0x180014c7a  jz      short loc_180014C8F
0x180014c7c  mov     rax, rsi
0x180014c7f  nop
0x180014c80  cmp     [rcx+rax+1], r12b
0x180014c85  lea     rax, [rax+1]
0x180014c89  jnz     short loc_180014C80
0x180014c8b  lea     rdx, [rax+1]
0x180014c8f  mov     rcx, [r13+18h]
0x180014c93  test    rcx, rcx
0x180014c96  jnz     short loc_180014C9F
0x180014c98  mov     eax, 2
0x180014c9d  jmp     short loc_180014CB6
0x180014c9f  mov     rax, rsi
0x180014ca2  cmp     [rcx+rax*2+2], r12w
0x180014ca8  lea     rax, [rax+1]
0x180014cac  jnz     short loc_180014CA2
0x180014cae  lea     rax, ds:2[rax*2]
0x180014cb6  mov     [rsp+48h+arg_0], rdi
0x180014cbb  lea     rbp, [rax+rdx]
0x180014cbf  add     rbp, r8
0x180014cc2  mov     [rsp+48h+arg_8], r15
0x180014cc7  lea     rdi, [r14+48h]
0x180014ccb  cmp     [r14+40h], r12
0x180014ccf  jz      short loc_180014CD6
0x180014cd1  cmp     [rdi], rbp
0x180014cd4  jnb     short loc_180014D0A
0x180014cd6  mov     rdx, rbp; dwBytes
0x180014cd9  mov     ecx, 8; dwFlags
0x180014cde  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014ce3  mov     r15, rax
0x180014ce6  test    rax, rax
0x180014ce9  jz      short loc_180014D0A
0x180014ceb  mov     rbx, [r14+40h]
0x180014cef  call    cs:__imp_GetProcessHeap
0x180014cf5  mov     r8, rbx; lpMem
0x180014cf8  xor     edx, edx; dwFlags
0x180014cfa  mov     rcx, rax; hHeap
0x180014cfd  call    cs:__imp_HeapFree
0x180014d03  mov     [r14+40h], r15
0x180014d07  mov     [rdi], rbp
0x180014d0a  mov     rbx, [r14+40h]
0x180014d0e  test    rbx, rbx
0x180014d11  jz      loc_180014EB0
0x180014d17  mov     rcx, [rdi]
0x180014d1a  lea     rdi, [r14+10h]
0x180014d1e  mov     rdx, [r13+38h]; Src
0x180014d22  lea     rbp, [rcx+rbx]
0x180014d26  cmp     rbx, rbp
0x180014d29  jz      short loc_180014D89
0x180014d2b  test    rdx, rdx
0x180014d2e  jz      short loc_180014D89
0x180014d30  cmp     byte ptr [rdx], 0
0x180014d33  jz      short loc_180014D89
0x180014d35  mov     rax, rsi
0x180014d38  nop     dword ptr [rax+rax+00000000h]
0x180014d40  cmp     byte ptr [rdx+rax+1], 0
0x180014d45  lea     rax, [rax+1]
0x180014d49  jnz     short loc_180014D40
0x180014d4b  lea     r15, [rax+1]
0x180014d4f  cmp     rcx, r15
0x180014d52  jnb     short loc_180014D69
0x180014d54  test    rdi, rdi
0x180014d57  jz      short loc_180014D5C
0x180014d59  mov     [rdi], r12
0x180014d5c  mov     rdx, [r13+80h]
0x180014d63  lea     rdi, [r14+20h]
0x180014d67  jmp     short loc_180014DA1
0x180014d69  test    r15, r15
0x180014d6c  jz      short loc_180014D7C
0x180014d6e  lfence
0x180014d71  mov     r8, r15; Size
0x180014d74  mov     rcx, rbx; void *
0x180014d77  call    memmove
0x180014d7c  test    rdi, rdi
0x180014d7f  jz      short loc_180014D84
0x180014d81  mov     [rdi], rbx
0x180014d84  add     rbx, r15
0x180014d87  jmp     short loc_180014D91
0x180014d89  test    rdi, rdi
0x180014d8c  jz      short loc_180014D91
0x180014d8e  mov     [rdi], r12
0x180014d91  mov     rdx, [r13+80h]; Src
0x180014d98  lea     rdi, [r14+20h]
0x180014d9c  cmp     rbx, rbp
0x180014d9f  jz      short loc_180014E15
0x180014da1  test    rdx, rdx
0x180014da4  jz      short loc_180014E15
0x180014da6  cmp     byte ptr [rdx], 0
0x180014da9  jz      short loc_180014E15
0x180014dab  mov     rax, rsi
0x180014dae  xchg    ax, ax
0x180014db0  cmp     byte ptr [rdx+rax+1], 0
0x180014db5  lea     rax, [rax+1]
0x180014db9  jnz     short loc_180014DB0
0x180014dbb  lea     r15, [rax+1]
0x180014dbf  mov     rax, rbp
0x180014dc2  sub     rax, rbx
0x180014dc5  cmp     rax, r15
0x180014dc8  jnb     short loc_180014DDC
0x180014dca  test    rdi, rdi
0x180014dcd  jz      short loc_180014DD2
0x180014dcf  mov     [rdi], r12
0x180014dd2  mov     rdx, [r13+18h]
0x180014dd6  lea     rdi, [r14+38h]
0x180014dda  jmp     short loc_180014E2A
0x180014ddc  test    r15, r15
0x180014ddf  jz      short loc_180014E08
0x180014de1  test    rbx, rbx
0x180014de4  jnz     short loc_180014DFA
0x180014de6  call    cs:__imp__errno
0x180014dec  mov     dword ptr [rax], 16h
0x180014df2  call    cs:__imp__invalid_parameter_noinfo
0x180014df8  jmp     short loc_180014E08
0x180014dfa  lfence
0x180014dfd  mov     r8, r15; Size
0x180014e00  mov     rcx, rbx; void *
0x180014e03  call    memmove
0x180014e08  test    rdi, rdi
0x180014e0b  jz      short loc_180014E10
0x180014e0d  mov     [rdi], rbx
0x180014e10  add     rbx, r15
0x180014e13  jmp     short loc_180014E1D
0x180014e15  test    rdi, rdi
0x180014e18  jz      short loc_180014E1D
0x180014e1a  mov     [rdi], r12
0x180014e1d  mov     rdx, [r13+18h]; Src
0x180014e21  lea     rdi, [r14+38h]
0x180014e25  cmp     rbx, rbp
0x180014e28  jz      short loc_180014E98
0x180014e2a  test    rdx, rdx
0x180014e2d  jz      short loc_180014E98
0x180014e2f  cmp     word ptr [rdx], 0
0x180014e33  jz      short loc_180014E98
0x180014e35  nop     word ptr [rax+rax+00000000h]
0x180014e40  cmp     word ptr [rdx+rsi*2+2], 0
0x180014e46  lea     rsi, [rsi+1]
0x180014e4a  jnz     short loc_180014E40
0x180014e4c  mov     rax, rbp
0x180014e4f  lea     rsi, ds:2[rsi*2]
0x180014e57  sub     rax, rbx
0x180014e5a  cmp     rax, rsi
0x180014e5d  jb      short loc_180014E98
0x180014e5f  test    rsi, rsi
0x180014e62  jz      short loc_180014E8B
0x180014e64  test    rbx, rbx
0x180014e67  jnz     short loc_180014E7D
0x180014e69  call    cs:__imp__errno
0x180014e6f  mov     dword ptr [rax], 16h
0x180014e75  call    cs:__imp__invalid_parameter_noinfo
0x180014e7b  jmp     short loc_180014E8B
0x180014e7d  lfence
0x180014e80  mov     r8, rsi; Size
0x180014e83  mov     rcx, rbx; void *
0x180014e86  call    memmove
0x180014e8b  test    rdi, rdi
0x180014e8e  jz      short loc_180014E93
0x180014e90  mov     [rdi], rbx
0x180014e93  add     rbx, rsi
0x180014e96  jmp     short loc_180014EA0
0x180014e98  test    rdi, rdi
0x180014e9b  jz      short loc_180014EA0
0x180014e9d  mov     [rdi], r12
0x180014ea0  sub     rbp, rbx
0x180014ea3  xor     edx, edx; Val
0x180014ea5  mov     r8, rbp; Size
0x180014ea8  mov     rcx, rbx; void *
0x180014eab  call    memset
0x180014eb0  mov     r15, [rsp+48h+arg_8]
0x180014eb5  mov     rdi, [rsp+48h+arg_0]
0x180014eba  mov     rbx, [rsp+48h+arg_10]
0x180014ebf  add     rsp, 20h
0x180014ec3  pop     r14
0x180014ec5  pop     r13
0x180014ec7  pop     r12
0x180014ec9  pop     rsi
0x180014eca  pop     rbp
0x180014ecb  retn
```
