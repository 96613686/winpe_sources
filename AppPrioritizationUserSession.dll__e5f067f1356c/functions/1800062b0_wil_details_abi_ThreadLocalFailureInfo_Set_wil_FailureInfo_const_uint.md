# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800062b0`
- end: `0x1800064c9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b30`

## callees

- `0x1800032a4`
- `0x180005c44`
- `0x1800062b0`
- `0x180007730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006398`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006398`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063a6`

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
0x1800062b0  push    rbx
0x1800062b2  push    rbp
0x1800062b3  push    rsi
0x1800062b4  push    rdi
0x1800062b5  push    r12
0x1800062b7  push    r13
0x1800062b9  push    r14
0x1800062bb  push    r15
0x1800062bd  sub     rsp, 28h
0x1800062c1  mov     [rcx+4], r8d
0x1800062c5  xor     r13d, r13d
0x1800062c8  mov     eax, [rdx+8]
0x1800062cb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800062cf  mov     [rcx+8], eax
0x1800062d2  mov     rdi, rcx
0x1800062d5  mov     [rcx+10h], r13
0x1800062d9  mov     r12, rdx
0x1800062dc  movzx   eax, word ptr [rdx+40h]
0x1800062e0  mov     [rcx+18h], ax
0x1800062e4  mov     al, [rdx]
0x1800062e6  mov     [rcx+1Ah], al
0x1800062e9  mov     [rcx+20h], r13
0x1800062ed  mov     rax, [rdx+88h]
0x1800062f4  mov     [rcx+28h], rax
0x1800062f8  mov     rax, [rdx+90h]
0x1800062ff  mov     [rcx+30h], rax
0x180006303  mov     [rcx+38h], r13
0x180006307  mov     rcx, [rdx+38h]
0x18000630b  lea     edx, [rbp+2]
0x18000630e  test    rcx, rcx
0x180006311  jnz     short loc_180006318
0x180006313  mov     r8d, edx
0x180006316  jmp     short loc_180006328
0x180006318  mov     rax, rbp
0x18000631b  inc     rax
0x18000631e  cmp     [rcx+rax], r13b
0x180006322  jnz     short loc_18000631B
0x180006324  lea     r8, [rax+1]; unsigned __int64
0x180006328  mov     rcx, [r12+80h]
0x180006330  test    rcx, rcx
0x180006333  jz      short loc_180006345
0x180006335  mov     rax, rbp
0x180006338  inc     rax
0x18000633b  cmp     [rcx+rax], r13b
0x18000633f  jnz     short loc_180006338
0x180006341  lea     rdx, [rax+1]
0x180006345  mov     rcx, [r12+18h]
0x18000634a  test    rcx, rcx
0x18000634d  jnz     short loc_180006354
0x18000634f  lea     eax, [rcx+2]
0x180006352  jmp     short loc_180006369
0x180006354  mov     rax, rbp
0x180006357  inc     rax
0x18000635a  cmp     [rcx+rax*2], r13w
0x18000635f  jnz     short loc_180006357
0x180006361  lea     rax, ds:2[rax*2]
0x180006369  lea     r14, [rdx+rax]
0x18000636d  add     r14, r8
0x180006370  lea     rsi, [rdi+48h]
0x180006374  cmp     [rdi+40h], r13
0x180006378  jz      short loc_18000637F
0x18000637a  cmp     [rsi], r14
0x18000637d  jnb     short loc_1800063B3
0x18000637f  mov     rdx, r14; dwBytes
0x180006382  mov     ecx, 8; dwFlags
0x180006387  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000638c  mov     r15, rax
0x18000638f  test    rax, rax
0x180006392  jz      short loc_1800063B3
0x180006394  mov     rbx, [rdi+40h]
0x180006398  call    cs:__imp_GetProcessHeap
0x18000639e  mov     r8, rbx; lpMem
0x1800063a1  xor     edx, edx; dwFlags
0x1800063a3  mov     rcx, rax; hHeap
0x1800063a6  call    cs:__imp_HeapFree
0x1800063ac  mov     [rdi+40h], r15
0x1800063b0  mov     [rsi], r14
0x1800063b3  mov     rbx, [rdi+40h]
0x1800063b7  test    rbx, rbx
0x1800063ba  jz      loc_1800064B8
0x1800063c0  mov     rdx, [rsi]; DestinationSize
0x1800063c3  lea     rsi, [rdx+rbx]
0x1800063c7  cmp     rbx, rsi
0x1800063ca  jz      short loc_18000640A
0x1800063cc  mov     r8, [r12+38h]; Source
0x1800063d1  test    r8, r8
0x1800063d4  jz      short loc_18000640A
0x1800063d6  cmp     [r8], r13b
0x1800063d9  jz      short loc_18000640A
0x1800063db  mov     rax, rbp
0x1800063de  inc     rax
0x1800063e1  cmp     [r8+rax], r13b
0x1800063e5  jnz     short loc_1800063DE
0x1800063e7  lea     r14, [rax+1]
0x1800063eb  cmp     rdx, r14
0x1800063ee  jnb     short loc_1800063F6
0x1800063f0  mov     [rdi+10h], r13
0x1800063f4  jmp     short loc_180006413
0x1800063f6  mov     r9, r14; SourceSize
0x1800063f9  mov     rcx, rbx; Destination
0x1800063fc  call    memcpy_s
0x180006401  mov     [rdi+10h], rbx
0x180006405  add     rbx, r14
0x180006408  jmp     short loc_18000640E
0x18000640a  mov     [rdi+10h], r13
0x18000640e  cmp     rbx, rsi
0x180006411  jz      short loc_18000645A
0x180006413  mov     r8, [r12+80h]; Source
0x18000641b  test    r8, r8
0x18000641e  jz      short loc_18000645A
0x180006420  cmp     [r8], r13b
0x180006423  jz      short loc_18000645A
0x180006425  mov     rax, rbp
0x180006428  inc     rax
0x18000642b  cmp     [r8+rax], r13b
0x18000642f  jnz     short loc_180006428
0x180006431  mov     rdx, rsi
0x180006434  lea     r14, [rax+1]
0x180006438  sub     rdx, rbx; DestinationSize
0x18000643b  cmp     rdx, r14
0x18000643e  jnb     short loc_180006446
0x180006440  mov     [rdi+20h], r13
0x180006444  jmp     short loc_180006463
0x180006446  mov     r9, r14; SourceSize
0x180006449  mov     rcx, rbx; Destination
0x18000644c  call    memcpy_s
0x180006451  mov     [rdi+20h], rbx
0x180006455  add     rbx, r14
0x180006458  jmp     short loc_18000645E
0x18000645a  mov     [rdi+20h], r13
0x18000645e  cmp     rbx, rsi
0x180006461  jz      short loc_1800064A4
0x180006463  mov     r8, [r12+18h]; Source
0x180006468  test    r8, r8
0x18000646b  jz      short loc_1800064A4
0x18000646d  cmp     [r8], r13w
0x180006471  jz      short loc_1800064A4
0x180006473  inc     rbp
0x180006476  cmp     [r8+rbp*2], r13w
0x18000647b  jnz     short loc_180006473
0x18000647d  mov     rdx, rsi
0x180006480  lea     r14, ds:2[rbp*2]
0x180006488  sub     rdx, rbx; DestinationSize
0x18000648b  cmp     rdx, r14
0x18000648e  jb      short loc_1800064A4
0x180006490  mov     r9, r14; SourceSize
0x180006493  mov     rcx, rbx; Destination
0x180006496  call    memcpy_s
0x18000649b  mov     [rdi+38h], rbx
0x18000649f  add     rbx, r14
0x1800064a2  jmp     short loc_1800064A8
0x1800064a4  mov     [rdi+38h], r13
0x1800064a8  sub     rsi, rbx
0x1800064ab  xor     edx, edx; Val
0x1800064ad  mov     r8, rsi; Size
0x1800064b0  mov     rcx, rbx; void *
0x1800064b3  call    memset_0
0x1800064b8  add     rsp, 28h
0x1800064bc  pop     r15
0x1800064be  pop     r14
0x1800064c0  pop     r13
0x1800064c2  pop     r12
0x1800064c4  pop     rdi
0x1800064c5  pop     rsi
0x1800064c6  pop     rbp
0x1800064c7  pop     rbx
0x1800064c8  retn
```
