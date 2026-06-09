# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400073d4`
- end: `0x1400075ed`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004ac0`

## callees

- `0x14000221c`
- `0x140005d18`
- `0x1400073d4`
- `0x140009088`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074ca`

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
0x1400073d4  push    rbx
0x1400073d6  push    rbp
0x1400073d7  push    rsi
0x1400073d8  push    rdi
0x1400073d9  push    r12
0x1400073db  push    r13
0x1400073dd  push    r14
0x1400073df  push    r15
0x1400073e1  sub     rsp, 28h
0x1400073e5  mov     [rcx+4], r8d
0x1400073e9  xor     r13d, r13d
0x1400073ec  mov     eax, [rdx+8]
0x1400073ef  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400073f3  mov     [rcx+8], eax
0x1400073f6  mov     rdi, rcx
0x1400073f9  mov     [rcx+10h], r13
0x1400073fd  mov     r12, rdx
0x140007400  movzx   eax, word ptr [rdx+40h]
0x140007404  mov     [rcx+18h], ax
0x140007408  mov     al, [rdx]
0x14000740a  mov     [rcx+1Ah], al
0x14000740d  mov     [rcx+20h], r13
0x140007411  mov     rax, [rdx+88h]
0x140007418  mov     [rcx+28h], rax
0x14000741c  mov     rax, [rdx+90h]
0x140007423  mov     [rcx+30h], rax
0x140007427  mov     [rcx+38h], r13
0x14000742b  mov     rcx, [rdx+38h]
0x14000742f  lea     edx, [rbp+2]
0x140007432  test    rcx, rcx
0x140007435  jnz     short loc_14000743C
0x140007437  mov     r8d, edx
0x14000743a  jmp     short loc_14000744C
0x14000743c  mov     rax, rbp
0x14000743f  inc     rax
0x140007442  cmp     [rcx+rax], r13b
0x140007446  jnz     short loc_14000743F
0x140007448  lea     r8, [rax+1]; unsigned __int64
0x14000744c  mov     rcx, [r12+80h]
0x140007454  test    rcx, rcx
0x140007457  jz      short loc_140007469
0x140007459  mov     rax, rbp
0x14000745c  inc     rax
0x14000745f  cmp     [rcx+rax], r13b
0x140007463  jnz     short loc_14000745C
0x140007465  lea     rdx, [rax+1]
0x140007469  mov     rcx, [r12+18h]
0x14000746e  test    rcx, rcx
0x140007471  jnz     short loc_140007478
0x140007473  lea     eax, [rcx+2]
0x140007476  jmp     short loc_14000748D
0x140007478  mov     rax, rbp
0x14000747b  inc     rax
0x14000747e  cmp     [rcx+rax*2], r13w
0x140007483  jnz     short loc_14000747B
0x140007485  lea     rax, ds:2[rax*2]
0x14000748d  lea     r14, [rdx+rax]
0x140007491  add     r14, r8
0x140007494  lea     rsi, [rdi+48h]
0x140007498  cmp     [rdi+40h], r13
0x14000749c  jz      short loc_1400074A3
0x14000749e  cmp     [rsi], r14
0x1400074a1  jnb     short loc_1400074D7
0x1400074a3  mov     rdx, r14; dwBytes
0x1400074a6  mov     ecx, 8; dwFlags
0x1400074ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400074b0  mov     r15, rax
0x1400074b3  test    rax, rax
0x1400074b6  jz      short loc_1400074D7
0x1400074b8  mov     rbx, [rdi+40h]
0x1400074bc  call    cs:__imp_GetProcessHeap
0x1400074c2  mov     r8, rbx; lpMem
0x1400074c5  xor     edx, edx; dwFlags
0x1400074c7  mov     rcx, rax; hHeap
0x1400074ca  call    cs:__imp_HeapFree
0x1400074d0  mov     [rdi+40h], r15
0x1400074d4  mov     [rsi], r14
0x1400074d7  mov     rbx, [rdi+40h]
0x1400074db  test    rbx, rbx
0x1400074de  jz      loc_1400075DC
0x1400074e4  mov     rdx, [rsi]; DestinationSize
0x1400074e7  lea     rsi, [rdx+rbx]
0x1400074eb  cmp     rbx, rsi
0x1400074ee  jz      short loc_14000752E
0x1400074f0  mov     r8, [r12+38h]; Source
0x1400074f5  test    r8, r8
0x1400074f8  jz      short loc_14000752E
0x1400074fa  cmp     [r8], r13b
0x1400074fd  jz      short loc_14000752E
0x1400074ff  mov     rax, rbp
0x140007502  inc     rax
0x140007505  cmp     [r8+rax], r13b
0x140007509  jnz     short loc_140007502
0x14000750b  lea     r14, [rax+1]
0x14000750f  cmp     rdx, r14
0x140007512  jnb     short loc_14000751A
0x140007514  mov     [rdi+10h], r13
0x140007518  jmp     short loc_140007537
0x14000751a  mov     r9, r14; SourceSize
0x14000751d  mov     rcx, rbx; Destination
0x140007520  call    memcpy_s
0x140007525  mov     [rdi+10h], rbx
0x140007529  add     rbx, r14
0x14000752c  jmp     short loc_140007532
0x14000752e  mov     [rdi+10h], r13
0x140007532  cmp     rbx, rsi
0x140007535  jz      short loc_14000757E
0x140007537  mov     r8, [r12+80h]; Source
0x14000753f  test    r8, r8
0x140007542  jz      short loc_14000757E
0x140007544  cmp     [r8], r13b
0x140007547  jz      short loc_14000757E
0x140007549  mov     rax, rbp
0x14000754c  inc     rax
0x14000754f  cmp     [r8+rax], r13b
0x140007553  jnz     short loc_14000754C
0x140007555  mov     rdx, rsi
0x140007558  lea     r14, [rax+1]
0x14000755c  sub     rdx, rbx; DestinationSize
0x14000755f  cmp     rdx, r14
0x140007562  jnb     short loc_14000756A
0x140007564  mov     [rdi+20h], r13
0x140007568  jmp     short loc_140007587
0x14000756a  mov     r9, r14; SourceSize
0x14000756d  mov     rcx, rbx; Destination
0x140007570  call    memcpy_s
0x140007575  mov     [rdi+20h], rbx
0x140007579  add     rbx, r14
0x14000757c  jmp     short loc_140007582
0x14000757e  mov     [rdi+20h], r13
0x140007582  cmp     rbx, rsi
0x140007585  jz      short loc_1400075C8
0x140007587  mov     r8, [r12+18h]; Source
0x14000758c  test    r8, r8
0x14000758f  jz      short loc_1400075C8
0x140007591  cmp     [r8], r13w
0x140007595  jz      short loc_1400075C8
0x140007597  inc     rbp
0x14000759a  cmp     [r8+rbp*2], r13w
0x14000759f  jnz     short loc_140007597
0x1400075a1  mov     rdx, rsi
0x1400075a4  lea     r14, ds:2[rbp*2]
0x1400075ac  sub     rdx, rbx; DestinationSize
0x1400075af  cmp     rdx, r14
0x1400075b2  jb      short loc_1400075C8
0x1400075b4  mov     r9, r14; SourceSize
0x1400075b7  mov     rcx, rbx; Destination
0x1400075ba  call    memcpy_s
0x1400075bf  mov     [rdi+38h], rbx
0x1400075c3  add     rbx, r14
0x1400075c6  jmp     short loc_1400075CC
0x1400075c8  mov     [rdi+38h], r13
0x1400075cc  sub     rsi, rbx
0x1400075cf  xor     edx, edx; Val
0x1400075d1  mov     r8, rsi; Size
0x1400075d4  mov     rcx, rbx; void *
0x1400075d7  call    memset_0
0x1400075dc  add     rsp, 28h
0x1400075e0  pop     r15
0x1400075e2  pop     r14
0x1400075e4  pop     r13
0x1400075e6  pop     r12
0x1400075e8  pop     rdi
0x1400075e9  pop     rsi
0x1400075ea  pop     rbp
0x1400075eb  pop     rbx
0x1400075ec  retn
```
