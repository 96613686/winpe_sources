# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c0a4`
- end: `0x18000c2bd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800081c0`

## callees

- `0x180002de0`
- `0x180009ccc`
- `0x18000c0a4`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c19a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c19a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c18c`

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
0x18000c0a4  push    rbx
0x18000c0a6  push    rbp
0x18000c0a7  push    rsi
0x18000c0a8  push    rdi
0x18000c0a9  push    r12
0x18000c0ab  push    r13
0x18000c0ad  push    r14
0x18000c0af  push    r15
0x18000c0b1  sub     rsp, 28h
0x18000c0b5  mov     [rcx+4], r8d
0x18000c0b9  xor     r13d, r13d
0x18000c0bc  mov     eax, [rdx+8]
0x18000c0bf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000c0c3  mov     [rcx+8], eax
0x18000c0c6  mov     rdi, rcx
0x18000c0c9  mov     [rcx+10h], r13
0x18000c0cd  mov     r12, rdx
0x18000c0d0  movzx   eax, word ptr [rdx+40h]
0x18000c0d4  mov     [rcx+18h], ax
0x18000c0d8  mov     al, [rdx]
0x18000c0da  mov     [rcx+1Ah], al
0x18000c0dd  mov     [rcx+20h], r13
0x18000c0e1  mov     rax, [rdx+88h]
0x18000c0e8  mov     [rcx+28h], rax
0x18000c0ec  mov     rax, [rdx+90h]
0x18000c0f3  mov     [rcx+30h], rax
0x18000c0f7  mov     [rcx+38h], r13
0x18000c0fb  mov     rcx, [rdx+38h]
0x18000c0ff  lea     edx, [rbp+2]
0x18000c102  test    rcx, rcx
0x18000c105  jnz     short loc_18000C10C
0x18000c107  mov     r8d, edx
0x18000c10a  jmp     short loc_18000C11C
0x18000c10c  mov     rax, rbp
0x18000c10f  inc     rax
0x18000c112  cmp     [rcx+rax], r13b
0x18000c116  jnz     short loc_18000C10F
0x18000c118  lea     r8, [rax+1]; unsigned __int64
0x18000c11c  mov     rcx, [r12+80h]
0x18000c124  test    rcx, rcx
0x18000c127  jz      short loc_18000C139
0x18000c129  mov     rax, rbp
0x18000c12c  inc     rax
0x18000c12f  cmp     [rcx+rax], r13b
0x18000c133  jnz     short loc_18000C12C
0x18000c135  lea     rdx, [rax+1]
0x18000c139  mov     rcx, [r12+18h]
0x18000c13e  test    rcx, rcx
0x18000c141  jnz     short loc_18000C148
0x18000c143  lea     eax, [rcx+2]
0x18000c146  jmp     short loc_18000C15D
0x18000c148  mov     rax, rbp
0x18000c14b  inc     rax
0x18000c14e  cmp     [rcx+rax*2], r13w
0x18000c153  jnz     short loc_18000C14B
0x18000c155  lea     rax, ds:2[rax*2]
0x18000c15d  lea     r14, [rdx+rax]
0x18000c161  add     r14, r8
0x18000c164  lea     rsi, [rdi+48h]
0x18000c168  cmp     [rdi+40h], r13
0x18000c16c  jz      short loc_18000C173
0x18000c16e  cmp     [rsi], r14
0x18000c171  jnb     short loc_18000C1A7
0x18000c173  mov     rdx, r14; dwBytes
0x18000c176  mov     ecx, 8; dwFlags
0x18000c17b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c180  mov     r15, rax
0x18000c183  test    rax, rax
0x18000c186  jz      short loc_18000C1A7
0x18000c188  mov     rbx, [rdi+40h]
0x18000c18c  call    cs:__imp_GetProcessHeap
0x18000c192  mov     r8, rbx; lpMem
0x18000c195  xor     edx, edx; dwFlags
0x18000c197  mov     rcx, rax; hHeap
0x18000c19a  call    cs:__imp_HeapFree
0x18000c1a0  mov     [rdi+40h], r15
0x18000c1a4  mov     [rsi], r14
0x18000c1a7  mov     rbx, [rdi+40h]
0x18000c1ab  test    rbx, rbx
0x18000c1ae  jz      loc_18000C2AC
0x18000c1b4  mov     rdx, [rsi]; DestinationSize
0x18000c1b7  lea     rsi, [rdx+rbx]
0x18000c1bb  cmp     rbx, rsi
0x18000c1be  jz      short loc_18000C1FE
0x18000c1c0  mov     r8, [r12+38h]; Source
0x18000c1c5  test    r8, r8
0x18000c1c8  jz      short loc_18000C1FE
0x18000c1ca  cmp     [r8], r13b
0x18000c1cd  jz      short loc_18000C1FE
0x18000c1cf  mov     rax, rbp
0x18000c1d2  inc     rax
0x18000c1d5  cmp     [r8+rax], r13b
0x18000c1d9  jnz     short loc_18000C1D2
0x18000c1db  lea     r14, [rax+1]
0x18000c1df  cmp     rdx, r14
0x18000c1e2  jnb     short loc_18000C1EA
0x18000c1e4  mov     [rdi+10h], r13
0x18000c1e8  jmp     short loc_18000C207
0x18000c1ea  mov     r9, r14; SourceSize
0x18000c1ed  mov     rcx, rbx; Destination
0x18000c1f0  call    memcpy_s
0x18000c1f5  mov     [rdi+10h], rbx
0x18000c1f9  add     rbx, r14
0x18000c1fc  jmp     short loc_18000C202
0x18000c1fe  mov     [rdi+10h], r13
0x18000c202  cmp     rbx, rsi
0x18000c205  jz      short loc_18000C24E
0x18000c207  mov     r8, [r12+80h]; Source
0x18000c20f  test    r8, r8
0x18000c212  jz      short loc_18000C24E
0x18000c214  cmp     [r8], r13b
0x18000c217  jz      short loc_18000C24E
0x18000c219  mov     rax, rbp
0x18000c21c  inc     rax
0x18000c21f  cmp     [r8+rax], r13b
0x18000c223  jnz     short loc_18000C21C
0x18000c225  mov     rdx, rsi
0x18000c228  lea     r14, [rax+1]
0x18000c22c  sub     rdx, rbx; DestinationSize
0x18000c22f  cmp     rdx, r14
0x18000c232  jnb     short loc_18000C23A
0x18000c234  mov     [rdi+20h], r13
0x18000c238  jmp     short loc_18000C257
0x18000c23a  mov     r9, r14; SourceSize
0x18000c23d  mov     rcx, rbx; Destination
0x18000c240  call    memcpy_s
0x18000c245  mov     [rdi+20h], rbx
0x18000c249  add     rbx, r14
0x18000c24c  jmp     short loc_18000C252
0x18000c24e  mov     [rdi+20h], r13
0x18000c252  cmp     rbx, rsi
0x18000c255  jz      short loc_18000C298
0x18000c257  mov     r8, [r12+18h]; Source
0x18000c25c  test    r8, r8
0x18000c25f  jz      short loc_18000C298
0x18000c261  cmp     [r8], r13w
0x18000c265  jz      short loc_18000C298
0x18000c267  inc     rbp
0x18000c26a  cmp     [r8+rbp*2], r13w
0x18000c26f  jnz     short loc_18000C267
0x18000c271  mov     rdx, rsi
0x18000c274  lea     r14, ds:2[rbp*2]
0x18000c27c  sub     rdx, rbx; DestinationSize
0x18000c27f  cmp     rdx, r14
0x18000c282  jb      short loc_18000C298
0x18000c284  mov     r9, r14; SourceSize
0x18000c287  mov     rcx, rbx; Destination
0x18000c28a  call    memcpy_s
0x18000c28f  mov     [rdi+38h], rbx
0x18000c293  add     rbx, r14
0x18000c296  jmp     short loc_18000C29C
0x18000c298  mov     [rdi+38h], r13
0x18000c29c  sub     rsi, rbx
0x18000c29f  xor     edx, edx; Val
0x18000c2a1  mov     r8, rsi; Size
0x18000c2a4  mov     rcx, rbx; void *
0x18000c2a7  call    memset_0
0x18000c2ac  add     rsp, 28h
0x18000c2b0  pop     r15
0x18000c2b2  pop     r14
0x18000c2b4  pop     r13
0x18000c2b6  pop     r12
0x18000c2b8  pop     rdi
0x18000c2b9  pop     rsi
0x18000c2ba  pop     rbp
0x18000c2bb  pop     rbx
0x18000c2bc  retn
```
