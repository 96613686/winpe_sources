# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000b284`
- end: `0x14000b49d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400096d0`

## callees

- `0x14000202c`
- `0x140006670`
- `0x14000b284`
- `0x14000cad8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b37a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b37a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b36c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b36c`

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
0x14000b284  push    rbx
0x14000b286  push    rbp
0x14000b287  push    rsi
0x14000b288  push    rdi
0x14000b289  push    r12
0x14000b28b  push    r13
0x14000b28d  push    r14
0x14000b28f  push    r15
0x14000b291  sub     rsp, 28h
0x14000b295  mov     [rcx+4], r8d
0x14000b299  xor     r13d, r13d
0x14000b29c  mov     eax, [rdx+8]
0x14000b29f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000b2a3  mov     [rcx+8], eax
0x14000b2a6  mov     rdi, rcx
0x14000b2a9  mov     [rcx+10h], r13
0x14000b2ad  mov     r12, rdx
0x14000b2b0  movzx   eax, word ptr [rdx+40h]
0x14000b2b4  mov     [rcx+18h], ax
0x14000b2b8  mov     al, [rdx]
0x14000b2ba  mov     [rcx+1Ah], al
0x14000b2bd  mov     [rcx+20h], r13
0x14000b2c1  mov     rax, [rdx+88h]
0x14000b2c8  mov     [rcx+28h], rax
0x14000b2cc  mov     rax, [rdx+90h]
0x14000b2d3  mov     [rcx+30h], rax
0x14000b2d7  mov     [rcx+38h], r13
0x14000b2db  mov     rcx, [rdx+38h]
0x14000b2df  lea     edx, [rbp+2]
0x14000b2e2  test    rcx, rcx
0x14000b2e5  jnz     short loc_14000B2EC
0x14000b2e7  mov     r8d, edx
0x14000b2ea  jmp     short loc_14000B2FC
0x14000b2ec  mov     rax, rbp
0x14000b2ef  inc     rax
0x14000b2f2  cmp     [rcx+rax], r13b
0x14000b2f6  jnz     short loc_14000B2EF
0x14000b2f8  lea     r8, [rax+1]; unsigned __int64
0x14000b2fc  mov     rcx, [r12+80h]
0x14000b304  test    rcx, rcx
0x14000b307  jz      short loc_14000B319
0x14000b309  mov     rax, rbp
0x14000b30c  inc     rax
0x14000b30f  cmp     [rcx+rax], r13b
0x14000b313  jnz     short loc_14000B30C
0x14000b315  lea     rdx, [rax+1]
0x14000b319  mov     rcx, [r12+18h]
0x14000b31e  test    rcx, rcx
0x14000b321  jnz     short loc_14000B328
0x14000b323  lea     eax, [rcx+2]
0x14000b326  jmp     short loc_14000B33D
0x14000b328  mov     rax, rbp
0x14000b32b  inc     rax
0x14000b32e  cmp     [rcx+rax*2], r13w
0x14000b333  jnz     short loc_14000B32B
0x14000b335  lea     rax, ds:2[rax*2]
0x14000b33d  lea     r14, [rdx+rax]
0x14000b341  add     r14, r8
0x14000b344  lea     rsi, [rdi+48h]
0x14000b348  cmp     [rdi+40h], r13
0x14000b34c  jz      short loc_14000B353
0x14000b34e  cmp     [rsi], r14
0x14000b351  jnb     short loc_14000B387
0x14000b353  mov     rdx, r14; dwBytes
0x14000b356  mov     ecx, 8; dwFlags
0x14000b35b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000b360  mov     r15, rax
0x14000b363  test    rax, rax
0x14000b366  jz      short loc_14000B387
0x14000b368  mov     rbx, [rdi+40h]
0x14000b36c  call    cs:__imp_GetProcessHeap
0x14000b372  mov     r8, rbx; lpMem
0x14000b375  xor     edx, edx; dwFlags
0x14000b377  mov     rcx, rax; hHeap
0x14000b37a  call    cs:__imp_HeapFree
0x14000b380  mov     [rdi+40h], r15
0x14000b384  mov     [rsi], r14
0x14000b387  mov     rbx, [rdi+40h]
0x14000b38b  test    rbx, rbx
0x14000b38e  jz      loc_14000B48C
0x14000b394  mov     rdx, [rsi]; DestinationSize
0x14000b397  lea     rsi, [rdx+rbx]
0x14000b39b  cmp     rbx, rsi
0x14000b39e  jz      short loc_14000B3DE
0x14000b3a0  mov     r8, [r12+38h]; Source
0x14000b3a5  test    r8, r8
0x14000b3a8  jz      short loc_14000B3DE
0x14000b3aa  cmp     [r8], r13b
0x14000b3ad  jz      short loc_14000B3DE
0x14000b3af  mov     rax, rbp
0x14000b3b2  inc     rax
0x14000b3b5  cmp     [r8+rax], r13b
0x14000b3b9  jnz     short loc_14000B3B2
0x14000b3bb  lea     r14, [rax+1]
0x14000b3bf  cmp     rdx, r14
0x14000b3c2  jnb     short loc_14000B3CA
0x14000b3c4  mov     [rdi+10h], r13
0x14000b3c8  jmp     short loc_14000B3E7
0x14000b3ca  mov     r9, r14; SourceSize
0x14000b3cd  mov     rcx, rbx; Destination
0x14000b3d0  call    memcpy_s
0x14000b3d5  mov     [rdi+10h], rbx
0x14000b3d9  add     rbx, r14
0x14000b3dc  jmp     short loc_14000B3E2
0x14000b3de  mov     [rdi+10h], r13
0x14000b3e2  cmp     rbx, rsi
0x14000b3e5  jz      short loc_14000B42E
0x14000b3e7  mov     r8, [r12+80h]; Source
0x14000b3ef  test    r8, r8
0x14000b3f2  jz      short loc_14000B42E
0x14000b3f4  cmp     [r8], r13b
0x14000b3f7  jz      short loc_14000B42E
0x14000b3f9  mov     rax, rbp
0x14000b3fc  inc     rax
0x14000b3ff  cmp     [r8+rax], r13b
0x14000b403  jnz     short loc_14000B3FC
0x14000b405  mov     rdx, rsi
0x14000b408  lea     r14, [rax+1]
0x14000b40c  sub     rdx, rbx; DestinationSize
0x14000b40f  cmp     rdx, r14
0x14000b412  jnb     short loc_14000B41A
0x14000b414  mov     [rdi+20h], r13
0x14000b418  jmp     short loc_14000B437
0x14000b41a  mov     r9, r14; SourceSize
0x14000b41d  mov     rcx, rbx; Destination
0x14000b420  call    memcpy_s
0x14000b425  mov     [rdi+20h], rbx
0x14000b429  add     rbx, r14
0x14000b42c  jmp     short loc_14000B432
0x14000b42e  mov     [rdi+20h], r13
0x14000b432  cmp     rbx, rsi
0x14000b435  jz      short loc_14000B478
0x14000b437  mov     r8, [r12+18h]; Source
0x14000b43c  test    r8, r8
0x14000b43f  jz      short loc_14000B478
0x14000b441  cmp     [r8], r13w
0x14000b445  jz      short loc_14000B478
0x14000b447  inc     rbp
0x14000b44a  cmp     [r8+rbp*2], r13w
0x14000b44f  jnz     short loc_14000B447
0x14000b451  mov     rdx, rsi
0x14000b454  lea     r14, ds:2[rbp*2]
0x14000b45c  sub     rdx, rbx; DestinationSize
0x14000b45f  cmp     rdx, r14
0x14000b462  jb      short loc_14000B478
0x14000b464  mov     r9, r14; SourceSize
0x14000b467  mov     rcx, rbx; Destination
0x14000b46a  call    memcpy_s
0x14000b46f  mov     [rdi+38h], rbx
0x14000b473  add     rbx, r14
0x14000b476  jmp     short loc_14000B47C
0x14000b478  mov     [rdi+38h], r13
0x14000b47c  sub     rsi, rbx
0x14000b47f  xor     edx, edx; Val
0x14000b481  mov     r8, rsi; Size
0x14000b484  mov     rcx, rbx; void *
0x14000b487  call    memset_0
0x14000b48c  add     rsp, 28h
0x14000b490  pop     r15
0x14000b492  pop     r14
0x14000b494  pop     r13
0x14000b496  pop     r12
0x14000b498  pop     rdi
0x14000b499  pop     rsi
0x14000b49a  pop     rbp
0x14000b49b  pop     rbx
0x14000b49c  retn
```
