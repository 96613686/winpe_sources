# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005190`
- end: `0x1400053a9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003920`

## callees

- `0x140002690`
- `0x140004abc`
- `0x140005190`
- `0x1400058c8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005286`
- `KERNEL32!HeapFree` at `0x140005286`
- `KERNEL32!GetProcessHeap` at `0x140005278`
- `KERNEL32!GetProcessHeap` at `0x140005278`

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
0x140005190  push    rbx
0x140005192  push    rbp
0x140005193  push    rsi
0x140005194  push    rdi
0x140005195  push    r12
0x140005197  push    r13
0x140005199  push    r14
0x14000519b  push    r15
0x14000519d  sub     rsp, 28h
0x1400051a1  mov     [rcx+4], r8d
0x1400051a5  xor     r13d, r13d
0x1400051a8  mov     eax, [rdx+8]
0x1400051ab  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400051af  mov     [rcx+8], eax
0x1400051b2  mov     rdi, rcx
0x1400051b5  mov     [rcx+10h], r13
0x1400051b9  mov     r12, rdx
0x1400051bc  movzx   eax, word ptr [rdx+40h]
0x1400051c0  mov     [rcx+18h], ax
0x1400051c4  mov     al, [rdx]
0x1400051c6  mov     [rcx+1Ah], al
0x1400051c9  mov     [rcx+20h], r13
0x1400051cd  mov     rax, [rdx+88h]
0x1400051d4  mov     [rcx+28h], rax
0x1400051d8  mov     rax, [rdx+90h]
0x1400051df  mov     [rcx+30h], rax
0x1400051e3  mov     [rcx+38h], r13
0x1400051e7  mov     rcx, [rdx+38h]
0x1400051eb  lea     edx, [rbp+2]
0x1400051ee  test    rcx, rcx
0x1400051f1  jnz     short loc_1400051F8
0x1400051f3  mov     r8d, edx
0x1400051f6  jmp     short loc_140005208
0x1400051f8  mov     rax, rbp
0x1400051fb  inc     rax
0x1400051fe  cmp     [rcx+rax], r13b
0x140005202  jnz     short loc_1400051FB
0x140005204  lea     r8, [rax+1]; unsigned __int64
0x140005208  mov     rcx, [r12+80h]
0x140005210  test    rcx, rcx
0x140005213  jz      short loc_140005225
0x140005215  mov     rax, rbp
0x140005218  inc     rax
0x14000521b  cmp     [rcx+rax], r13b
0x14000521f  jnz     short loc_140005218
0x140005221  lea     rdx, [rax+1]
0x140005225  mov     rcx, [r12+18h]
0x14000522a  test    rcx, rcx
0x14000522d  jnz     short loc_140005234
0x14000522f  lea     eax, [rcx+2]
0x140005232  jmp     short loc_140005249
0x140005234  mov     rax, rbp
0x140005237  inc     rax
0x14000523a  cmp     [rcx+rax*2], r13w
0x14000523f  jnz     short loc_140005237
0x140005241  lea     rax, ds:2[rax*2]
0x140005249  lea     r14, [rdx+rax]
0x14000524d  add     r14, r8
0x140005250  lea     rsi, [rdi+48h]
0x140005254  cmp     [rdi+40h], r13
0x140005258  jz      short loc_14000525F
0x14000525a  cmp     [rsi], r14
0x14000525d  jnb     short loc_140005293
0x14000525f  mov     rdx, r14; dwBytes
0x140005262  mov     ecx, 8; dwFlags
0x140005267  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000526c  mov     r15, rax
0x14000526f  test    rax, rax
0x140005272  jz      short loc_140005293
0x140005274  mov     rbx, [rdi+40h]
0x140005278  call    cs:__imp_GetProcessHeap
0x14000527e  mov     r8, rbx; lpMem
0x140005281  xor     edx, edx; dwFlags
0x140005283  mov     rcx, rax; hHeap
0x140005286  call    cs:__imp_HeapFree
0x14000528c  mov     [rdi+40h], r15
0x140005290  mov     [rsi], r14
0x140005293  mov     rbx, [rdi+40h]
0x140005297  test    rbx, rbx
0x14000529a  jz      loc_140005398
0x1400052a0  mov     rdx, [rsi]; DestinationSize
0x1400052a3  lea     rsi, [rdx+rbx]
0x1400052a7  cmp     rbx, rsi
0x1400052aa  jz      short loc_1400052EA
0x1400052ac  mov     r8, [r12+38h]; Source
0x1400052b1  test    r8, r8
0x1400052b4  jz      short loc_1400052EA
0x1400052b6  cmp     [r8], r13b
0x1400052b9  jz      short loc_1400052EA
0x1400052bb  mov     rax, rbp
0x1400052be  inc     rax
0x1400052c1  cmp     [r8+rax], r13b
0x1400052c5  jnz     short loc_1400052BE
0x1400052c7  lea     r14, [rax+1]
0x1400052cb  cmp     rdx, r14
0x1400052ce  jnb     short loc_1400052D6
0x1400052d0  mov     [rdi+10h], r13
0x1400052d4  jmp     short loc_1400052F3
0x1400052d6  mov     r9, r14; SourceSize
0x1400052d9  mov     rcx, rbx; Destination
0x1400052dc  call    memcpy_s
0x1400052e1  mov     [rdi+10h], rbx
0x1400052e5  add     rbx, r14
0x1400052e8  jmp     short loc_1400052EE
0x1400052ea  mov     [rdi+10h], r13
0x1400052ee  cmp     rbx, rsi
0x1400052f1  jz      short loc_14000533A
0x1400052f3  mov     r8, [r12+80h]; Source
0x1400052fb  test    r8, r8
0x1400052fe  jz      short loc_14000533A
0x140005300  cmp     [r8], r13b
0x140005303  jz      short loc_14000533A
0x140005305  mov     rax, rbp
0x140005308  inc     rax
0x14000530b  cmp     [r8+rax], r13b
0x14000530f  jnz     short loc_140005308
0x140005311  mov     rdx, rsi
0x140005314  lea     r14, [rax+1]
0x140005318  sub     rdx, rbx; DestinationSize
0x14000531b  cmp     rdx, r14
0x14000531e  jnb     short loc_140005326
0x140005320  mov     [rdi+20h], r13
0x140005324  jmp     short loc_140005343
0x140005326  mov     r9, r14; SourceSize
0x140005329  mov     rcx, rbx; Destination
0x14000532c  call    memcpy_s
0x140005331  mov     [rdi+20h], rbx
0x140005335  add     rbx, r14
0x140005338  jmp     short loc_14000533E
0x14000533a  mov     [rdi+20h], r13
0x14000533e  cmp     rbx, rsi
0x140005341  jz      short loc_140005384
0x140005343  mov     r8, [r12+18h]; Source
0x140005348  test    r8, r8
0x14000534b  jz      short loc_140005384
0x14000534d  cmp     [r8], r13w
0x140005351  jz      short loc_140005384
0x140005353  inc     rbp
0x140005356  cmp     [r8+rbp*2], r13w
0x14000535b  jnz     short loc_140005353
0x14000535d  mov     rdx, rsi
0x140005360  lea     r14, ds:2[rbp*2]
0x140005368  sub     rdx, rbx; DestinationSize
0x14000536b  cmp     rdx, r14
0x14000536e  jb      short loc_140005384
0x140005370  mov     r9, r14; SourceSize
0x140005373  mov     rcx, rbx; Destination
0x140005376  call    memcpy_s
0x14000537b  mov     [rdi+38h], rbx
0x14000537f  add     rbx, r14
0x140005382  jmp     short loc_140005388
0x140005384  mov     [rdi+38h], r13
0x140005388  sub     rsi, rbx
0x14000538b  xor     edx, edx; Val
0x14000538d  mov     r8, rsi; Size
0x140005390  mov     rcx, rbx; void *
0x140005393  call    memset_0
0x140005398  add     rsp, 28h
0x14000539c  pop     r15
0x14000539e  pop     r14
0x1400053a0  pop     r13
0x1400053a2  pop     r12
0x1400053a4  pop     rdi
0x1400053a5  pop     rsi
0x1400053a6  pop     rbp
0x1400053a7  pop     rbx
0x1400053a8  retn
```
