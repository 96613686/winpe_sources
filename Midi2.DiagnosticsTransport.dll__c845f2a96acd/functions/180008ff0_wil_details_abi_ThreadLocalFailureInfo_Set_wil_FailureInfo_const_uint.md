# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008ff0`
- end: `0x180009209`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006860`

## callees

- `0x180004170`
- `0x180007d6c`
- `0x180008ff0`
- `0x18000a328`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e6`

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
0x180008ff0  push    rbx
0x180008ff2  push    rbp
0x180008ff3  push    rsi
0x180008ff4  push    rdi
0x180008ff5  push    r12
0x180008ff7  push    r13
0x180008ff9  push    r14
0x180008ffb  push    r15
0x180008ffd  sub     rsp, 28h
0x180009001  mov     [rcx+4], r8d
0x180009005  xor     r13d, r13d
0x180009008  mov     eax, [rdx+8]
0x18000900b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000900f  mov     [rcx+8], eax
0x180009012  mov     rdi, rcx
0x180009015  mov     [rcx+10h], r13
0x180009019  mov     r12, rdx
0x18000901c  movzx   eax, word ptr [rdx+40h]
0x180009020  mov     [rcx+18h], ax
0x180009024  mov     al, [rdx]
0x180009026  mov     [rcx+1Ah], al
0x180009029  mov     [rcx+20h], r13
0x18000902d  mov     rax, [rdx+88h]
0x180009034  mov     [rcx+28h], rax
0x180009038  mov     rax, [rdx+90h]
0x18000903f  mov     [rcx+30h], rax
0x180009043  mov     [rcx+38h], r13
0x180009047  mov     rcx, [rdx+38h]
0x18000904b  lea     edx, [rbp+2]
0x18000904e  test    rcx, rcx
0x180009051  jnz     short loc_180009058
0x180009053  mov     r8d, edx
0x180009056  jmp     short loc_180009068
0x180009058  mov     rax, rbp
0x18000905b  inc     rax
0x18000905e  cmp     [rcx+rax], r13b
0x180009062  jnz     short loc_18000905B
0x180009064  lea     r8, [rax+1]; unsigned __int64
0x180009068  mov     rcx, [r12+80h]
0x180009070  test    rcx, rcx
0x180009073  jz      short loc_180009085
0x180009075  mov     rax, rbp
0x180009078  inc     rax
0x18000907b  cmp     [rcx+rax], r13b
0x18000907f  jnz     short loc_180009078
0x180009081  lea     rdx, [rax+1]
0x180009085  mov     rcx, [r12+18h]
0x18000908a  test    rcx, rcx
0x18000908d  jnz     short loc_180009094
0x18000908f  lea     eax, [rcx+2]
0x180009092  jmp     short loc_1800090A9
0x180009094  mov     rax, rbp
0x180009097  inc     rax
0x18000909a  cmp     [rcx+rax*2], r13w
0x18000909f  jnz     short loc_180009097
0x1800090a1  lea     rax, ds:2[rax*2]
0x1800090a9  lea     r14, [rdx+rax]
0x1800090ad  add     r14, r8
0x1800090b0  lea     rsi, [rdi+48h]
0x1800090b4  cmp     [rdi+40h], r13
0x1800090b8  jz      short loc_1800090BF
0x1800090ba  cmp     [rsi], r14
0x1800090bd  jnb     short loc_1800090F3
0x1800090bf  mov     rdx, r14; dwBytes
0x1800090c2  mov     ecx, 8; dwFlags
0x1800090c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800090cc  mov     r15, rax
0x1800090cf  test    rax, rax
0x1800090d2  jz      short loc_1800090F3
0x1800090d4  mov     rbx, [rdi+40h]
0x1800090d8  call    cs:__imp_GetProcessHeap
0x1800090de  mov     r8, rbx; lpMem
0x1800090e1  xor     edx, edx; dwFlags
0x1800090e3  mov     rcx, rax; hHeap
0x1800090e6  call    cs:__imp_HeapFree
0x1800090ec  mov     [rdi+40h], r15
0x1800090f0  mov     [rsi], r14
0x1800090f3  mov     rbx, [rdi+40h]
0x1800090f7  test    rbx, rbx
0x1800090fa  jz      loc_1800091F8
0x180009100  mov     rdx, [rsi]; DestinationSize
0x180009103  lea     rsi, [rdx+rbx]
0x180009107  cmp     rbx, rsi
0x18000910a  jz      short loc_18000914A
0x18000910c  mov     r8, [r12+38h]; Source
0x180009111  test    r8, r8
0x180009114  jz      short loc_18000914A
0x180009116  cmp     [r8], r13b
0x180009119  jz      short loc_18000914A
0x18000911b  mov     rax, rbp
0x18000911e  inc     rax
0x180009121  cmp     [r8+rax], r13b
0x180009125  jnz     short loc_18000911E
0x180009127  lea     r14, [rax+1]
0x18000912b  cmp     rdx, r14
0x18000912e  jnb     short loc_180009136
0x180009130  mov     [rdi+10h], r13
0x180009134  jmp     short loc_180009153
0x180009136  mov     r9, r14; SourceSize
0x180009139  mov     rcx, rbx; Destination
0x18000913c  call    memcpy_s
0x180009141  mov     [rdi+10h], rbx
0x180009145  add     rbx, r14
0x180009148  jmp     short loc_18000914E
0x18000914a  mov     [rdi+10h], r13
0x18000914e  cmp     rbx, rsi
0x180009151  jz      short loc_18000919A
0x180009153  mov     r8, [r12+80h]; Source
0x18000915b  test    r8, r8
0x18000915e  jz      short loc_18000919A
0x180009160  cmp     [r8], r13b
0x180009163  jz      short loc_18000919A
0x180009165  mov     rax, rbp
0x180009168  inc     rax
0x18000916b  cmp     [r8+rax], r13b
0x18000916f  jnz     short loc_180009168
0x180009171  mov     rdx, rsi
0x180009174  lea     r14, [rax+1]
0x180009178  sub     rdx, rbx; DestinationSize
0x18000917b  cmp     rdx, r14
0x18000917e  jnb     short loc_180009186
0x180009180  mov     [rdi+20h], r13
0x180009184  jmp     short loc_1800091A3
0x180009186  mov     r9, r14; SourceSize
0x180009189  mov     rcx, rbx; Destination
0x18000918c  call    memcpy_s
0x180009191  mov     [rdi+20h], rbx
0x180009195  add     rbx, r14
0x180009198  jmp     short loc_18000919E
0x18000919a  mov     [rdi+20h], r13
0x18000919e  cmp     rbx, rsi
0x1800091a1  jz      short loc_1800091E4
0x1800091a3  mov     r8, [r12+18h]; Source
0x1800091a8  test    r8, r8
0x1800091ab  jz      short loc_1800091E4
0x1800091ad  cmp     [r8], r13w
0x1800091b1  jz      short loc_1800091E4
0x1800091b3  inc     rbp
0x1800091b6  cmp     [r8+rbp*2], r13w
0x1800091bb  jnz     short loc_1800091B3
0x1800091bd  mov     rdx, rsi
0x1800091c0  lea     r14, ds:2[rbp*2]
0x1800091c8  sub     rdx, rbx; DestinationSize
0x1800091cb  cmp     rdx, r14
0x1800091ce  jb      short loc_1800091E4
0x1800091d0  mov     r9, r14; SourceSize
0x1800091d3  mov     rcx, rbx; Destination
0x1800091d6  call    memcpy_s
0x1800091db  mov     [rdi+38h], rbx
0x1800091df  add     rbx, r14
0x1800091e2  jmp     short loc_1800091E8
0x1800091e4  mov     [rdi+38h], r13
0x1800091e8  sub     rsi, rbx
0x1800091eb  xor     edx, edx; Val
0x1800091ed  mov     r8, rsi; Size
0x1800091f0  mov     rcx, rbx; void *
0x1800091f3  call    memset_0
0x1800091f8  add     rsp, 28h
0x1800091fc  pop     r15
0x1800091fe  pop     r14
0x180009200  pop     r13
0x180009202  pop     r12
0x180009204  pop     rdi
0x180009205  pop     rsi
0x180009206  pop     rbp
0x180009207  pop     rbx
0x180009208  retn
```
