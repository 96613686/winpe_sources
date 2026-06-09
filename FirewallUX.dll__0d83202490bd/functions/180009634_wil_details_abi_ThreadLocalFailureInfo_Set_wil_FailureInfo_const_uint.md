# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009634`
- end: `0x18000984d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006f30`

## callees

- `0x180002c04`
- `0x18000877c`
- `0x180009634`
- `0x18000bbe8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000971c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000971c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000972a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000972a`

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
0x180009634  push    rbx
0x180009636  push    rbp
0x180009637  push    rsi
0x180009638  push    rdi
0x180009639  push    r12
0x18000963b  push    r13
0x18000963d  push    r14
0x18000963f  push    r15
0x180009641  sub     rsp, 28h
0x180009645  mov     [rcx+4], r8d
0x180009649  xor     r13d, r13d
0x18000964c  mov     eax, [rdx+8]
0x18000964f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009653  mov     [rcx+8], eax
0x180009656  mov     rdi, rcx
0x180009659  mov     [rcx+10h], r13
0x18000965d  mov     r12, rdx
0x180009660  movzx   eax, word ptr [rdx+40h]
0x180009664  mov     [rcx+18h], ax
0x180009668  mov     al, [rdx]
0x18000966a  mov     [rcx+1Ah], al
0x18000966d  mov     [rcx+20h], r13
0x180009671  mov     rax, [rdx+88h]
0x180009678  mov     [rcx+28h], rax
0x18000967c  mov     rax, [rdx+90h]
0x180009683  mov     [rcx+30h], rax
0x180009687  mov     [rcx+38h], r13
0x18000968b  mov     rcx, [rdx+38h]
0x18000968f  lea     edx, [rbp+2]
0x180009692  test    rcx, rcx
0x180009695  jnz     short loc_18000969C
0x180009697  mov     r8d, edx
0x18000969a  jmp     short loc_1800096AC
0x18000969c  mov     rax, rbp
0x18000969f  inc     rax
0x1800096a2  cmp     [rcx+rax], r13b
0x1800096a6  jnz     short loc_18000969F
0x1800096a8  lea     r8, [rax+1]; unsigned __int64
0x1800096ac  mov     rcx, [r12+80h]
0x1800096b4  test    rcx, rcx
0x1800096b7  jz      short loc_1800096C9
0x1800096b9  mov     rax, rbp
0x1800096bc  inc     rax
0x1800096bf  cmp     [rcx+rax], r13b
0x1800096c3  jnz     short loc_1800096BC
0x1800096c5  lea     rdx, [rax+1]
0x1800096c9  mov     rcx, [r12+18h]
0x1800096ce  test    rcx, rcx
0x1800096d1  jnz     short loc_1800096D8
0x1800096d3  lea     eax, [rcx+2]
0x1800096d6  jmp     short loc_1800096ED
0x1800096d8  mov     rax, rbp
0x1800096db  inc     rax
0x1800096de  cmp     [rcx+rax*2], r13w
0x1800096e3  jnz     short loc_1800096DB
0x1800096e5  lea     rax, ds:2[rax*2]
0x1800096ed  lea     r14, [rdx+rax]
0x1800096f1  add     r14, r8
0x1800096f4  lea     rsi, [rdi+48h]
0x1800096f8  cmp     [rdi+40h], r13
0x1800096fc  jz      short loc_180009703
0x1800096fe  cmp     [rsi], r14
0x180009701  jnb     short loc_180009737
0x180009703  mov     rdx, r14; dwBytes
0x180009706  mov     ecx, 8; dwFlags
0x18000970b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009710  mov     r15, rax
0x180009713  test    rax, rax
0x180009716  jz      short loc_180009737
0x180009718  mov     rbx, [rdi+40h]
0x18000971c  call    cs:__imp_GetProcessHeap
0x180009722  mov     r8, rbx; lpMem
0x180009725  xor     edx, edx; dwFlags
0x180009727  mov     rcx, rax; hHeap
0x18000972a  call    cs:__imp_HeapFree
0x180009730  mov     [rdi+40h], r15
0x180009734  mov     [rsi], r14
0x180009737  mov     rbx, [rdi+40h]
0x18000973b  test    rbx, rbx
0x18000973e  jz      loc_18000983C
0x180009744  mov     rdx, [rsi]; DestinationSize
0x180009747  lea     rsi, [rdx+rbx]
0x18000974b  cmp     rbx, rsi
0x18000974e  jz      short loc_18000978E
0x180009750  mov     r8, [r12+38h]; Source
0x180009755  test    r8, r8
0x180009758  jz      short loc_18000978E
0x18000975a  cmp     [r8], r13b
0x18000975d  jz      short loc_18000978E
0x18000975f  mov     rax, rbp
0x180009762  inc     rax
0x180009765  cmp     [r8+rax], r13b
0x180009769  jnz     short loc_180009762
0x18000976b  lea     r14, [rax+1]
0x18000976f  cmp     rdx, r14
0x180009772  jnb     short loc_18000977A
0x180009774  mov     [rdi+10h], r13
0x180009778  jmp     short loc_180009797
0x18000977a  mov     r9, r14; SourceSize
0x18000977d  mov     rcx, rbx; Destination
0x180009780  call    memcpy_s
0x180009785  mov     [rdi+10h], rbx
0x180009789  add     rbx, r14
0x18000978c  jmp     short loc_180009792
0x18000978e  mov     [rdi+10h], r13
0x180009792  cmp     rbx, rsi
0x180009795  jz      short loc_1800097DE
0x180009797  mov     r8, [r12+80h]; Source
0x18000979f  test    r8, r8
0x1800097a2  jz      short loc_1800097DE
0x1800097a4  cmp     [r8], r13b
0x1800097a7  jz      short loc_1800097DE
0x1800097a9  mov     rax, rbp
0x1800097ac  inc     rax
0x1800097af  cmp     [r8+rax], r13b
0x1800097b3  jnz     short loc_1800097AC
0x1800097b5  mov     rdx, rsi
0x1800097b8  lea     r14, [rax+1]
0x1800097bc  sub     rdx, rbx; DestinationSize
0x1800097bf  cmp     rdx, r14
0x1800097c2  jnb     short loc_1800097CA
0x1800097c4  mov     [rdi+20h], r13
0x1800097c8  jmp     short loc_1800097E7
0x1800097ca  mov     r9, r14; SourceSize
0x1800097cd  mov     rcx, rbx; Destination
0x1800097d0  call    memcpy_s
0x1800097d5  mov     [rdi+20h], rbx
0x1800097d9  add     rbx, r14
0x1800097dc  jmp     short loc_1800097E2
0x1800097de  mov     [rdi+20h], r13
0x1800097e2  cmp     rbx, rsi
0x1800097e5  jz      short loc_180009828
0x1800097e7  mov     r8, [r12+18h]; Source
0x1800097ec  test    r8, r8
0x1800097ef  jz      short loc_180009828
0x1800097f1  cmp     [r8], r13w
0x1800097f5  jz      short loc_180009828
0x1800097f7  inc     rbp
0x1800097fa  cmp     [r8+rbp*2], r13w
0x1800097ff  jnz     short loc_1800097F7
0x180009801  mov     rdx, rsi
0x180009804  lea     r14, ds:2[rbp*2]
0x18000980c  sub     rdx, rbx; DestinationSize
0x18000980f  cmp     rdx, r14
0x180009812  jb      short loc_180009828
0x180009814  mov     r9, r14; SourceSize
0x180009817  mov     rcx, rbx; Destination
0x18000981a  call    memcpy_s
0x18000981f  mov     [rdi+38h], rbx
0x180009823  add     rbx, r14
0x180009826  jmp     short loc_18000982C
0x180009828  mov     [rdi+38h], r13
0x18000982c  sub     rsi, rbx
0x18000982f  xor     edx, edx; Val
0x180009831  mov     r8, rsi; Size
0x180009834  mov     rcx, rbx; void *
0x180009837  call    memset_0
0x18000983c  add     rsp, 28h
0x180009840  pop     r15
0x180009842  pop     r14
0x180009844  pop     r13
0x180009846  pop     r12
0x180009848  pop     rdi
0x180009849  pop     rsi
0x18000984a  pop     rbp
0x18000984b  pop     rbx
0x18000984c  retn
```
