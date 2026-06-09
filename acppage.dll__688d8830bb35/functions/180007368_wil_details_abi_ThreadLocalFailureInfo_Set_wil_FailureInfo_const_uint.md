# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007368`
- end: `0x180007584`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004a30`

## callees

- `0x180005d58`
- `0x180007368`
- `0x18001623a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800074b4`
- `msvcrt!memcpy_s` at `0x180007505`
- `msvcrt!memcpy_s` at `0x180007550`
- `msvcrt!memcpy_s` at `0x1800074b4`
- `msvcrt!memcpy_s` at `0x180007505`
- `msvcrt!memcpy_s` at `0x180007550`
- `KERNEL32!HeapFree` at `0x18000745e`
- `KERNEL32!HeapFree` at `0x18000745e`
- `KERNEL32!GetProcessHeap` at `0x180007450`
- `KERNEL32!GetProcessHeap` at `0x180007450`

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
0x180007368  push    rbx
0x18000736a  push    rbp
0x18000736b  push    rsi
0x18000736c  push    rdi
0x18000736d  push    r12
0x18000736f  push    r13
0x180007371  push    r14
0x180007373  push    r15
0x180007375  sub     rsp, 28h
0x180007379  mov     [rcx+4], r8d
0x18000737d  xor     r13d, r13d
0x180007380  mov     eax, [rdx+8]
0x180007383  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007387  mov     [rcx+8], eax
0x18000738a  mov     rdi, rcx
0x18000738d  mov     [rcx+10h], r13
0x180007391  mov     r12, rdx
0x180007394  movzx   eax, word ptr [rdx+40h]
0x180007398  mov     [rcx+18h], ax
0x18000739c  mov     al, [rdx]
0x18000739e  mov     [rcx+1Ah], al
0x1800073a1  mov     [rcx+20h], r13
0x1800073a5  mov     rax, [rdx+88h]
0x1800073ac  mov     [rcx+28h], rax
0x1800073b0  mov     rax, [rdx+90h]
0x1800073b7  mov     [rcx+30h], rax
0x1800073bb  mov     [rcx+38h], r13
0x1800073bf  mov     rcx, [rdx+38h]
0x1800073c3  lea     edx, [rbp+2]
0x1800073c6  test    rcx, rcx
0x1800073c9  jnz     short loc_1800073D0
0x1800073cb  mov     r8d, edx
0x1800073ce  jmp     short loc_1800073E0
0x1800073d0  mov     rax, rbp
0x1800073d3  inc     rax
0x1800073d6  cmp     [rcx+rax], r13b
0x1800073da  jnz     short loc_1800073D3
0x1800073dc  lea     r8, [rax+1]; unsigned __int64
0x1800073e0  mov     rcx, [r12+80h]
0x1800073e8  test    rcx, rcx
0x1800073eb  jz      short loc_1800073FD
0x1800073ed  mov     rax, rbp
0x1800073f0  inc     rax
0x1800073f3  cmp     [rcx+rax], r13b
0x1800073f7  jnz     short loc_1800073F0
0x1800073f9  lea     rdx, [rax+1]
0x1800073fd  mov     rcx, [r12+18h]
0x180007402  test    rcx, rcx
0x180007405  jnz     short loc_18000740C
0x180007407  lea     eax, [rcx+2]
0x18000740a  jmp     short loc_180007421
0x18000740c  mov     rax, rbp
0x18000740f  inc     rax
0x180007412  cmp     [rcx+rax*2], r13w
0x180007417  jnz     short loc_18000740F
0x180007419  lea     rax, ds:2[rax*2]
0x180007421  lea     r14, [rdx+rax]
0x180007425  add     r14, r8
0x180007428  lea     rsi, [rdi+48h]
0x18000742c  cmp     [rdi+40h], r13
0x180007430  jz      short loc_180007437
0x180007432  cmp     [rsi], r14
0x180007435  jnb     short loc_18000746B
0x180007437  mov     rdx, r14; dwBytes
0x18000743a  mov     ecx, 8; dwFlags
0x18000743f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007444  mov     r15, rax
0x180007447  test    rax, rax
0x18000744a  jz      short loc_18000746B
0x18000744c  mov     rbx, [rdi+40h]
0x180007450  call    cs:__imp_GetProcessHeap
0x180007456  mov     r8, rbx; lpMem
0x180007459  xor     edx, edx; dwFlags
0x18000745b  mov     rcx, rax; hHeap
0x18000745e  call    cs:__imp_HeapFree
0x180007464  mov     [rdi+40h], r15
0x180007468  mov     [rsi], r14
0x18000746b  mov     rbx, [rdi+40h]
0x18000746f  test    rbx, rbx
0x180007472  jz      loc_180007573
0x180007478  mov     rdx, [rsi]; DestinationSize
0x18000747b  lea     rsi, [rdx+rbx]
0x18000747f  cmp     rbx, rsi
0x180007482  jz      short loc_1800074C3
0x180007484  mov     r8, [r12+38h]; Source
0x180007489  test    r8, r8
0x18000748c  jz      short loc_1800074C3
0x18000748e  cmp     [r8], r13b
0x180007491  jz      short loc_1800074C3
0x180007493  mov     rax, rbp
0x180007496  inc     rax
0x180007499  cmp     [r8+rax], r13b
0x18000749d  jnz     short loc_180007496
0x18000749f  lea     r14, [rax+1]
0x1800074a3  cmp     rdx, r14
0x1800074a6  jnb     short loc_1800074AE
0x1800074a8  mov     [rdi+10h], r13
0x1800074ac  jmp     short loc_1800074CC
0x1800074ae  mov     r9, r14; SourceSize
0x1800074b1  mov     rcx, rbx; Destination
0x1800074b4  call    cs:__imp_memcpy_s
0x1800074ba  mov     [rdi+10h], rbx
0x1800074be  add     rbx, r14
0x1800074c1  jmp     short loc_1800074C7
0x1800074c3  mov     [rdi+10h], r13
0x1800074c7  cmp     rbx, rsi
0x1800074ca  jz      short loc_180007514
0x1800074cc  mov     r8, [r12+80h]; Source
0x1800074d4  test    r8, r8
0x1800074d7  jz      short loc_180007514
0x1800074d9  cmp     [r8], r13b
0x1800074dc  jz      short loc_180007514
0x1800074de  mov     rax, rbp
0x1800074e1  inc     rax
0x1800074e4  cmp     [r8+rax], r13b
0x1800074e8  jnz     short loc_1800074E1
0x1800074ea  mov     rdx, rsi
0x1800074ed  lea     r14, [rax+1]
0x1800074f1  sub     rdx, rbx; DestinationSize
0x1800074f4  cmp     rdx, r14
0x1800074f7  jnb     short loc_1800074FF
0x1800074f9  mov     [rdi+20h], r13
0x1800074fd  jmp     short loc_18000751D
0x1800074ff  mov     r9, r14; SourceSize
0x180007502  mov     rcx, rbx; Destination
0x180007505  call    cs:__imp_memcpy_s
0x18000750b  mov     [rdi+20h], rbx
0x18000750f  add     rbx, r14
0x180007512  jmp     short loc_180007518
0x180007514  mov     [rdi+20h], r13
0x180007518  cmp     rbx, rsi
0x18000751b  jz      short loc_18000755F
0x18000751d  mov     r8, [r12+18h]; Source
0x180007522  test    r8, r8
0x180007525  jz      short loc_18000755F
0x180007527  cmp     [r8], r13w
0x18000752b  jz      short loc_18000755F
0x18000752d  inc     rbp
0x180007530  cmp     [r8+rbp*2], r13w
0x180007535  jnz     short loc_18000752D
0x180007537  mov     rdx, rsi
0x18000753a  lea     r14, ds:2[rbp*2]
0x180007542  sub     rdx, rbx; DestinationSize
0x180007545  cmp     rdx, r14
0x180007548  jb      short loc_18000755F
0x18000754a  mov     r9, r14; SourceSize
0x18000754d  mov     rcx, rbx; Destination
0x180007550  call    cs:__imp_memcpy_s
0x180007556  mov     [rdi+38h], rbx
0x18000755a  add     rbx, r14
0x18000755d  jmp     short loc_180007563
0x18000755f  mov     [rdi+38h], r13
0x180007563  sub     rsi, rbx
0x180007566  xor     edx, edx; Val
0x180007568  mov     r8, rsi; Size
0x18000756b  mov     rcx, rbx; void *
0x18000756e  call    memset_0
0x180007573  add     rsp, 28h
0x180007577  pop     r15
0x180007579  pop     r14
0x18000757b  pop     r13
0x18000757d  pop     r12
0x18000757f  pop     rdi
0x180007580  pop     rsi
0x180007581  pop     rbp
0x180007582  pop     rbx
0x180007583  retn
```
