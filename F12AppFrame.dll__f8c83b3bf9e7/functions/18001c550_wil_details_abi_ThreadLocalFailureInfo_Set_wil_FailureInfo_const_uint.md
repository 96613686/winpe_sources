# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001c550`
- end: `0x18001c769`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019c70`

## callees

- `0x180002678`
- `0x18001bf38`
- `0x18001c550`
- `0x18001e360`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001c638`
- `KERNEL32!GetProcessHeap` at `0x18001c638`
- `KERNEL32!HeapFree` at `0x18001c646`
- `KERNEL32!HeapFree` at `0x18001c646`

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
0x18001c550  push    rbx
0x18001c552  push    rbp
0x18001c553  push    rsi
0x18001c554  push    rdi
0x18001c555  push    r12
0x18001c557  push    r13
0x18001c559  push    r14
0x18001c55b  push    r15
0x18001c55d  sub     rsp, 28h
0x18001c561  mov     [rcx+4], r8d
0x18001c565  xor     r13d, r13d
0x18001c568  mov     eax, [rdx+8]
0x18001c56b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001c56f  mov     [rcx+8], eax
0x18001c572  mov     rdi, rcx
0x18001c575  mov     [rcx+10h], r13
0x18001c579  mov     r12, rdx
0x18001c57c  movzx   eax, word ptr [rdx+40h]
0x18001c580  mov     [rcx+18h], ax
0x18001c584  mov     al, [rdx]
0x18001c586  mov     [rcx+1Ah], al
0x18001c589  mov     [rcx+20h], r13
0x18001c58d  mov     rax, [rdx+88h]
0x18001c594  mov     [rcx+28h], rax
0x18001c598  mov     rax, [rdx+90h]
0x18001c59f  mov     [rcx+30h], rax
0x18001c5a3  mov     [rcx+38h], r13
0x18001c5a7  mov     rcx, [rdx+38h]
0x18001c5ab  lea     edx, [rbp+2]
0x18001c5ae  test    rcx, rcx
0x18001c5b1  jnz     short loc_18001C5B8
0x18001c5b3  mov     r8d, edx
0x18001c5b6  jmp     short loc_18001C5C8
0x18001c5b8  mov     rax, rbp
0x18001c5bb  inc     rax
0x18001c5be  cmp     [rcx+rax], r13b
0x18001c5c2  jnz     short loc_18001C5BB
0x18001c5c4  lea     r8, [rax+1]; unsigned __int64
0x18001c5c8  mov     rcx, [r12+80h]
0x18001c5d0  test    rcx, rcx
0x18001c5d3  jz      short loc_18001C5E5
0x18001c5d5  mov     rax, rbp
0x18001c5d8  inc     rax
0x18001c5db  cmp     [rcx+rax], r13b
0x18001c5df  jnz     short loc_18001C5D8
0x18001c5e1  lea     rdx, [rax+1]
0x18001c5e5  mov     rcx, [r12+18h]
0x18001c5ea  test    rcx, rcx
0x18001c5ed  jnz     short loc_18001C5F4
0x18001c5ef  lea     eax, [rcx+2]
0x18001c5f2  jmp     short loc_18001C609
0x18001c5f4  mov     rax, rbp
0x18001c5f7  inc     rax
0x18001c5fa  cmp     [rcx+rax*2], r13w
0x18001c5ff  jnz     short loc_18001C5F7
0x18001c601  lea     rax, ds:2[rax*2]
0x18001c609  lea     r14, [rdx+rax]
0x18001c60d  add     r14, r8
0x18001c610  lea     rsi, [rdi+48h]
0x18001c614  cmp     [rdi+40h], r13
0x18001c618  jz      short loc_18001C61F
0x18001c61a  cmp     [rsi], r14
0x18001c61d  jnb     short loc_18001C653
0x18001c61f  mov     rdx, r14; dwBytes
0x18001c622  mov     ecx, 8; dwFlags
0x18001c627  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001c62c  mov     r15, rax
0x18001c62f  test    rax, rax
0x18001c632  jz      short loc_18001C653
0x18001c634  mov     rbx, [rdi+40h]
0x18001c638  call    cs:__imp_GetProcessHeap
0x18001c63e  mov     r8, rbx; lpMem
0x18001c641  xor     edx, edx; dwFlags
0x18001c643  mov     rcx, rax; hHeap
0x18001c646  call    cs:__imp_HeapFree
0x18001c64c  mov     [rdi+40h], r15
0x18001c650  mov     [rsi], r14
0x18001c653  mov     rbx, [rdi+40h]
0x18001c657  test    rbx, rbx
0x18001c65a  jz      loc_18001C758
0x18001c660  mov     rdx, [rsi]; DestinationSize
0x18001c663  lea     rsi, [rdx+rbx]
0x18001c667  cmp     rbx, rsi
0x18001c66a  jz      short loc_18001C6AA
0x18001c66c  mov     r8, [r12+38h]; Source
0x18001c671  test    r8, r8
0x18001c674  jz      short loc_18001C6AA
0x18001c676  cmp     [r8], r13b
0x18001c679  jz      short loc_18001C6AA
0x18001c67b  mov     rax, rbp
0x18001c67e  inc     rax
0x18001c681  cmp     [r8+rax], r13b
0x18001c685  jnz     short loc_18001C67E
0x18001c687  lea     r14, [rax+1]
0x18001c68b  cmp     rdx, r14
0x18001c68e  jnb     short loc_18001C696
0x18001c690  mov     [rdi+10h], r13
0x18001c694  jmp     short loc_18001C6B3
0x18001c696  mov     r9, r14; SourceSize
0x18001c699  mov     rcx, rbx; Destination
0x18001c69c  call    memcpy_s
0x18001c6a1  mov     [rdi+10h], rbx
0x18001c6a5  add     rbx, r14
0x18001c6a8  jmp     short loc_18001C6AE
0x18001c6aa  mov     [rdi+10h], r13
0x18001c6ae  cmp     rbx, rsi
0x18001c6b1  jz      short loc_18001C6FA
0x18001c6b3  mov     r8, [r12+80h]; Source
0x18001c6bb  test    r8, r8
0x18001c6be  jz      short loc_18001C6FA
0x18001c6c0  cmp     [r8], r13b
0x18001c6c3  jz      short loc_18001C6FA
0x18001c6c5  mov     rax, rbp
0x18001c6c8  inc     rax
0x18001c6cb  cmp     [r8+rax], r13b
0x18001c6cf  jnz     short loc_18001C6C8
0x18001c6d1  mov     rdx, rsi
0x18001c6d4  lea     r14, [rax+1]
0x18001c6d8  sub     rdx, rbx; DestinationSize
0x18001c6db  cmp     rdx, r14
0x18001c6de  jnb     short loc_18001C6E6
0x18001c6e0  mov     [rdi+20h], r13
0x18001c6e4  jmp     short loc_18001C703
0x18001c6e6  mov     r9, r14; SourceSize
0x18001c6e9  mov     rcx, rbx; Destination
0x18001c6ec  call    memcpy_s
0x18001c6f1  mov     [rdi+20h], rbx
0x18001c6f5  add     rbx, r14
0x18001c6f8  jmp     short loc_18001C6FE
0x18001c6fa  mov     [rdi+20h], r13
0x18001c6fe  cmp     rbx, rsi
0x18001c701  jz      short loc_18001C744
0x18001c703  mov     r8, [r12+18h]; Source
0x18001c708  test    r8, r8
0x18001c70b  jz      short loc_18001C744
0x18001c70d  cmp     [r8], r13w
0x18001c711  jz      short loc_18001C744
0x18001c713  inc     rbp
0x18001c716  cmp     [r8+rbp*2], r13w
0x18001c71b  jnz     short loc_18001C713
0x18001c71d  mov     rdx, rsi
0x18001c720  lea     r14, ds:2[rbp*2]
0x18001c728  sub     rdx, rbx; DestinationSize
0x18001c72b  cmp     rdx, r14
0x18001c72e  jb      short loc_18001C744
0x18001c730  mov     r9, r14; SourceSize
0x18001c733  mov     rcx, rbx; Destination
0x18001c736  call    memcpy_s
0x18001c73b  mov     [rdi+38h], rbx
0x18001c73f  add     rbx, r14
0x18001c742  jmp     short loc_18001C748
0x18001c744  mov     [rdi+38h], r13
0x18001c748  sub     rsi, rbx
0x18001c74b  xor     edx, edx; Val
0x18001c74d  mov     r8, rsi; Size
0x18001c750  mov     rcx, rbx; void *
0x18001c753  call    memset_0
0x18001c758  add     rsp, 28h
0x18001c75c  pop     r15
0x18001c75e  pop     r14
0x18001c760  pop     r13
0x18001c762  pop     r12
0x18001c764  pop     rdi
0x18001c765  pop     rsi
0x18001c766  pop     rbp
0x18001c767  pop     rbx
0x18001c768  retn
```
