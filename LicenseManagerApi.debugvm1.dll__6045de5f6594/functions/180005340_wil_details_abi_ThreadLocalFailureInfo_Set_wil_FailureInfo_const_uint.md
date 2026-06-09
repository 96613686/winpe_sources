# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005340`
- end: `0x180005559`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003e20`

## callees

- `0x1800022ea`
- `0x180004e58`
- `0x180005340`
- `0x1800062e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005428`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005428`

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
0x180005340  push    rbx
0x180005342  push    rbp
0x180005343  push    rsi
0x180005344  push    rdi
0x180005345  push    r12
0x180005347  push    r13
0x180005349  push    r14
0x18000534b  push    r15
0x18000534d  sub     rsp, 28h
0x180005351  mov     [rcx+4], r8d
0x180005355  xor     r13d, r13d
0x180005358  mov     eax, [rdx+8]
0x18000535b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000535f  mov     [rcx+8], eax
0x180005362  mov     rdi, rcx
0x180005365  mov     [rcx+10h], r13
0x180005369  mov     r12, rdx
0x18000536c  movzx   eax, word ptr [rdx+40h]
0x180005370  mov     [rcx+18h], ax
0x180005374  mov     al, [rdx]
0x180005376  mov     [rcx+1Ah], al
0x180005379  mov     [rcx+20h], r13
0x18000537d  mov     rax, [rdx+88h]
0x180005384  mov     [rcx+28h], rax
0x180005388  mov     rax, [rdx+90h]
0x18000538f  mov     [rcx+30h], rax
0x180005393  mov     [rcx+38h], r13
0x180005397  mov     rcx, [rdx+38h]
0x18000539b  lea     edx, [rbp+2]
0x18000539e  test    rcx, rcx
0x1800053a1  jnz     short loc_1800053A8
0x1800053a3  mov     r8d, edx
0x1800053a6  jmp     short loc_1800053B8
0x1800053a8  mov     rax, rbp
0x1800053ab  inc     rax
0x1800053ae  cmp     [rcx+rax], r13b
0x1800053b2  jnz     short loc_1800053AB
0x1800053b4  lea     r8, [rax+1]; unsigned __int64
0x1800053b8  mov     rcx, [r12+80h]
0x1800053c0  test    rcx, rcx
0x1800053c3  jz      short loc_1800053D5
0x1800053c5  mov     rax, rbp
0x1800053c8  inc     rax
0x1800053cb  cmp     [rcx+rax], r13b
0x1800053cf  jnz     short loc_1800053C8
0x1800053d1  lea     rdx, [rax+1]
0x1800053d5  mov     rcx, [r12+18h]
0x1800053da  test    rcx, rcx
0x1800053dd  jnz     short loc_1800053E4
0x1800053df  lea     eax, [rcx+2]
0x1800053e2  jmp     short loc_1800053F9
0x1800053e4  mov     rax, rbp
0x1800053e7  inc     rax
0x1800053ea  cmp     [rcx+rax*2], r13w
0x1800053ef  jnz     short loc_1800053E7
0x1800053f1  lea     rax, ds:2[rax*2]
0x1800053f9  lea     r14, [rdx+rax]
0x1800053fd  add     r14, r8
0x180005400  lea     rsi, [rdi+48h]
0x180005404  cmp     [rdi+40h], r13
0x180005408  jz      short loc_18000540F
0x18000540a  cmp     [rsi], r14
0x18000540d  jnb     short loc_180005443
0x18000540f  mov     rdx, r14; dwBytes
0x180005412  mov     ecx, 8; dwFlags
0x180005417  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000541c  mov     r15, rax
0x18000541f  test    rax, rax
0x180005422  jz      short loc_180005443
0x180005424  mov     rbx, [rdi+40h]
0x180005428  call    cs:__imp_GetProcessHeap
0x18000542e  mov     r8, rbx; lpMem
0x180005431  xor     edx, edx; dwFlags
0x180005433  mov     rcx, rax; hHeap
0x180005436  call    cs:__imp_HeapFree
0x18000543c  mov     [rdi+40h], r15
0x180005440  mov     [rsi], r14
0x180005443  mov     rbx, [rdi+40h]
0x180005447  test    rbx, rbx
0x18000544a  jz      loc_180005548
0x180005450  mov     rdx, [rsi]; DestinationSize
0x180005453  lea     rsi, [rdx+rbx]
0x180005457  cmp     rbx, rsi
0x18000545a  jz      short loc_18000549A
0x18000545c  mov     r8, [r12+38h]; Source
0x180005461  test    r8, r8
0x180005464  jz      short loc_18000549A
0x180005466  cmp     [r8], r13b
0x180005469  jz      short loc_18000549A
0x18000546b  mov     rax, rbp
0x18000546e  inc     rax
0x180005471  cmp     [r8+rax], r13b
0x180005475  jnz     short loc_18000546E
0x180005477  lea     r14, [rax+1]
0x18000547b  cmp     rdx, r14
0x18000547e  jnb     short loc_180005486
0x180005480  mov     [rdi+10h], r13
0x180005484  jmp     short loc_1800054A3
0x180005486  mov     r9, r14; SourceSize
0x180005489  mov     rcx, rbx; Destination
0x18000548c  call    memcpy_s
0x180005491  mov     [rdi+10h], rbx
0x180005495  add     rbx, r14
0x180005498  jmp     short loc_18000549E
0x18000549a  mov     [rdi+10h], r13
0x18000549e  cmp     rbx, rsi
0x1800054a1  jz      short loc_1800054EA
0x1800054a3  mov     r8, [r12+80h]; Source
0x1800054ab  test    r8, r8
0x1800054ae  jz      short loc_1800054EA
0x1800054b0  cmp     [r8], r13b
0x1800054b3  jz      short loc_1800054EA
0x1800054b5  mov     rax, rbp
0x1800054b8  inc     rax
0x1800054bb  cmp     [r8+rax], r13b
0x1800054bf  jnz     short loc_1800054B8
0x1800054c1  mov     rdx, rsi
0x1800054c4  lea     r14, [rax+1]
0x1800054c8  sub     rdx, rbx; DestinationSize
0x1800054cb  cmp     rdx, r14
0x1800054ce  jnb     short loc_1800054D6
0x1800054d0  mov     [rdi+20h], r13
0x1800054d4  jmp     short loc_1800054F3
0x1800054d6  mov     r9, r14; SourceSize
0x1800054d9  mov     rcx, rbx; Destination
0x1800054dc  call    memcpy_s
0x1800054e1  mov     [rdi+20h], rbx
0x1800054e5  add     rbx, r14
0x1800054e8  jmp     short loc_1800054EE
0x1800054ea  mov     [rdi+20h], r13
0x1800054ee  cmp     rbx, rsi
0x1800054f1  jz      short loc_180005534
0x1800054f3  mov     r8, [r12+18h]; Source
0x1800054f8  test    r8, r8
0x1800054fb  jz      short loc_180005534
0x1800054fd  cmp     [r8], r13w
0x180005501  jz      short loc_180005534
0x180005503  inc     rbp
0x180005506  cmp     [r8+rbp*2], r13w
0x18000550b  jnz     short loc_180005503
0x18000550d  mov     rdx, rsi
0x180005510  lea     r14, ds:2[rbp*2]
0x180005518  sub     rdx, rbx; DestinationSize
0x18000551b  cmp     rdx, r14
0x18000551e  jb      short loc_180005534
0x180005520  mov     r9, r14; SourceSize
0x180005523  mov     rcx, rbx; Destination
0x180005526  call    memcpy_s
0x18000552b  mov     [rdi+38h], rbx
0x18000552f  add     rbx, r14
0x180005532  jmp     short loc_180005538
0x180005534  mov     [rdi+38h], r13
0x180005538  sub     rsi, rbx
0x18000553b  xor     edx, edx; Val
0x18000553d  mov     r8, rsi; Size
0x180005540  mov     rcx, rbx; void *
0x180005543  call    memset_0
0x180005548  add     rsp, 28h
0x18000554c  pop     r15
0x18000554e  pop     r14
0x180005550  pop     r13
0x180005552  pop     r12
0x180005554  pop     rdi
0x180005555  pop     rsi
0x180005556  pop     rbp
0x180005557  pop     rbx
0x180005558  retn
```
