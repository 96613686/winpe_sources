# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800076b8`
- end: `0x1800078d4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004bf0`

## callees

- `0x180005ef0`
- `0x1800076b8`
- `0x18001380e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007804`
- `msvcrt!memcpy_s` at `0x180007855`
- `msvcrt!memcpy_s` at `0x1800078a0`
- `msvcrt!memcpy_s` at `0x180007804`
- `msvcrt!memcpy_s` at `0x180007855`
- `msvcrt!memcpy_s` at `0x1800078a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077a0`

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
0x1800076b8  push    rbx
0x1800076ba  push    rbp
0x1800076bb  push    rsi
0x1800076bc  push    rdi
0x1800076bd  push    r12
0x1800076bf  push    r13
0x1800076c1  push    r14
0x1800076c3  push    r15
0x1800076c5  sub     rsp, 28h
0x1800076c9  mov     [rcx+4], r8d
0x1800076cd  xor     r13d, r13d
0x1800076d0  mov     eax, [rdx+8]
0x1800076d3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800076d7  mov     [rcx+8], eax
0x1800076da  mov     rdi, rcx
0x1800076dd  mov     [rcx+10h], r13
0x1800076e1  mov     r12, rdx
0x1800076e4  movzx   eax, word ptr [rdx+40h]
0x1800076e8  mov     [rcx+18h], ax
0x1800076ec  mov     al, [rdx]
0x1800076ee  mov     [rcx+1Ah], al
0x1800076f1  mov     [rcx+20h], r13
0x1800076f5  mov     rax, [rdx+88h]
0x1800076fc  mov     [rcx+28h], rax
0x180007700  mov     rax, [rdx+90h]
0x180007707  mov     [rcx+30h], rax
0x18000770b  mov     [rcx+38h], r13
0x18000770f  mov     rcx, [rdx+38h]
0x180007713  lea     edx, [rbp+2]
0x180007716  test    rcx, rcx
0x180007719  jnz     short loc_180007720
0x18000771b  mov     r8d, edx
0x18000771e  jmp     short loc_180007730
0x180007720  mov     rax, rbp
0x180007723  inc     rax
0x180007726  cmp     [rcx+rax], r13b
0x18000772a  jnz     short loc_180007723
0x18000772c  lea     r8, [rax+1]; unsigned __int64
0x180007730  mov     rcx, [r12+80h]
0x180007738  test    rcx, rcx
0x18000773b  jz      short loc_18000774D
0x18000773d  mov     rax, rbp
0x180007740  inc     rax
0x180007743  cmp     [rcx+rax], r13b
0x180007747  jnz     short loc_180007740
0x180007749  lea     rdx, [rax+1]
0x18000774d  mov     rcx, [r12+18h]
0x180007752  test    rcx, rcx
0x180007755  jnz     short loc_18000775C
0x180007757  lea     eax, [rcx+2]
0x18000775a  jmp     short loc_180007771
0x18000775c  mov     rax, rbp
0x18000775f  inc     rax
0x180007762  cmp     [rcx+rax*2], r13w
0x180007767  jnz     short loc_18000775F
0x180007769  lea     rax, ds:2[rax*2]
0x180007771  lea     r14, [rdx+rax]
0x180007775  add     r14, r8
0x180007778  lea     rsi, [rdi+48h]
0x18000777c  cmp     [rdi+40h], r13
0x180007780  jz      short loc_180007787
0x180007782  cmp     [rsi], r14
0x180007785  jnb     short loc_1800077BB
0x180007787  mov     rdx, r14; dwBytes
0x18000778a  mov     ecx, 8; dwFlags
0x18000778f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007794  mov     r15, rax
0x180007797  test    rax, rax
0x18000779a  jz      short loc_1800077BB
0x18000779c  mov     rbx, [rdi+40h]
0x1800077a0  call    cs:__imp_GetProcessHeap
0x1800077a6  mov     r8, rbx; lpMem
0x1800077a9  xor     edx, edx; dwFlags
0x1800077ab  mov     rcx, rax; hHeap
0x1800077ae  call    cs:__imp_HeapFree
0x1800077b4  mov     [rdi+40h], r15
0x1800077b8  mov     [rsi], r14
0x1800077bb  mov     rbx, [rdi+40h]
0x1800077bf  test    rbx, rbx
0x1800077c2  jz      loc_1800078C3
0x1800077c8  mov     rdx, [rsi]; DestinationSize
0x1800077cb  lea     rsi, [rdx+rbx]
0x1800077cf  cmp     rbx, rsi
0x1800077d2  jz      short loc_180007813
0x1800077d4  mov     r8, [r12+38h]; Source
0x1800077d9  test    r8, r8
0x1800077dc  jz      short loc_180007813
0x1800077de  cmp     [r8], r13b
0x1800077e1  jz      short loc_180007813
0x1800077e3  mov     rax, rbp
0x1800077e6  inc     rax
0x1800077e9  cmp     [r8+rax], r13b
0x1800077ed  jnz     short loc_1800077E6
0x1800077ef  lea     r14, [rax+1]
0x1800077f3  cmp     rdx, r14
0x1800077f6  jnb     short loc_1800077FE
0x1800077f8  mov     [rdi+10h], r13
0x1800077fc  jmp     short loc_18000781C
0x1800077fe  mov     r9, r14; SourceSize
0x180007801  mov     rcx, rbx; Destination
0x180007804  call    cs:__imp_memcpy_s
0x18000780a  mov     [rdi+10h], rbx
0x18000780e  add     rbx, r14
0x180007811  jmp     short loc_180007817
0x180007813  mov     [rdi+10h], r13
0x180007817  cmp     rbx, rsi
0x18000781a  jz      short loc_180007864
0x18000781c  mov     r8, [r12+80h]; Source
0x180007824  test    r8, r8
0x180007827  jz      short loc_180007864
0x180007829  cmp     [r8], r13b
0x18000782c  jz      short loc_180007864
0x18000782e  mov     rax, rbp
0x180007831  inc     rax
0x180007834  cmp     [r8+rax], r13b
0x180007838  jnz     short loc_180007831
0x18000783a  mov     rdx, rsi
0x18000783d  lea     r14, [rax+1]
0x180007841  sub     rdx, rbx; DestinationSize
0x180007844  cmp     rdx, r14
0x180007847  jnb     short loc_18000784F
0x180007849  mov     [rdi+20h], r13
0x18000784d  jmp     short loc_18000786D
0x18000784f  mov     r9, r14; SourceSize
0x180007852  mov     rcx, rbx; Destination
0x180007855  call    cs:__imp_memcpy_s
0x18000785b  mov     [rdi+20h], rbx
0x18000785f  add     rbx, r14
0x180007862  jmp     short loc_180007868
0x180007864  mov     [rdi+20h], r13
0x180007868  cmp     rbx, rsi
0x18000786b  jz      short loc_1800078AF
0x18000786d  mov     r8, [r12+18h]; Source
0x180007872  test    r8, r8
0x180007875  jz      short loc_1800078AF
0x180007877  cmp     [r8], r13w
0x18000787b  jz      short loc_1800078AF
0x18000787d  inc     rbp
0x180007880  cmp     [r8+rbp*2], r13w
0x180007885  jnz     short loc_18000787D
0x180007887  mov     rdx, rsi
0x18000788a  lea     r14, ds:2[rbp*2]
0x180007892  sub     rdx, rbx; DestinationSize
0x180007895  cmp     rdx, r14
0x180007898  jb      short loc_1800078AF
0x18000789a  mov     r9, r14; SourceSize
0x18000789d  mov     rcx, rbx; Destination
0x1800078a0  call    cs:__imp_memcpy_s
0x1800078a6  mov     [rdi+38h], rbx
0x1800078aa  add     rbx, r14
0x1800078ad  jmp     short loc_1800078B3
0x1800078af  mov     [rdi+38h], r13
0x1800078b3  sub     rsi, rbx
0x1800078b6  xor     edx, edx; Val
0x1800078b8  mov     r8, rsi; Size
0x1800078bb  mov     rcx, rbx; void *
0x1800078be  call    memset_0
0x1800078c3  add     rsp, 28h
0x1800078c7  pop     r15
0x1800078c9  pop     r14
0x1800078cb  pop     r13
0x1800078cd  pop     r12
0x1800078cf  pop     rdi
0x1800078d0  pop     rsi
0x1800078d1  pop     rbp
0x1800078d2  pop     rbx
0x1800078d3  retn
```
