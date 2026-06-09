# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800077d0`
- end: `0x1800079e9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005040`

## callees

- `0x180002958`
- `0x18000654c`
- `0x1800077d0`
- `0x180008b08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078c6`

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
0x1800077d0  push    rbx
0x1800077d2  push    rbp
0x1800077d3  push    rsi
0x1800077d4  push    rdi
0x1800077d5  push    r12
0x1800077d7  push    r13
0x1800077d9  push    r14
0x1800077db  push    r15
0x1800077dd  sub     rsp, 28h
0x1800077e1  mov     [rcx+4], r8d
0x1800077e5  xor     r13d, r13d
0x1800077e8  mov     eax, [rdx+8]
0x1800077eb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800077ef  mov     [rcx+8], eax
0x1800077f2  mov     rdi, rcx
0x1800077f5  mov     [rcx+10h], r13
0x1800077f9  mov     r12, rdx
0x1800077fc  movzx   eax, word ptr [rdx+40h]
0x180007800  mov     [rcx+18h], ax
0x180007804  mov     al, [rdx]
0x180007806  mov     [rcx+1Ah], al
0x180007809  mov     [rcx+20h], r13
0x18000780d  mov     rax, [rdx+88h]
0x180007814  mov     [rcx+28h], rax
0x180007818  mov     rax, [rdx+90h]
0x18000781f  mov     [rcx+30h], rax
0x180007823  mov     [rcx+38h], r13
0x180007827  mov     rcx, [rdx+38h]
0x18000782b  lea     edx, [rbp+2]
0x18000782e  test    rcx, rcx
0x180007831  jnz     short loc_180007838
0x180007833  mov     r8d, edx
0x180007836  jmp     short loc_180007848
0x180007838  mov     rax, rbp
0x18000783b  inc     rax
0x18000783e  cmp     [rcx+rax], r13b
0x180007842  jnz     short loc_18000783B
0x180007844  lea     r8, [rax+1]; unsigned __int64
0x180007848  mov     rcx, [r12+80h]
0x180007850  test    rcx, rcx
0x180007853  jz      short loc_180007865
0x180007855  mov     rax, rbp
0x180007858  inc     rax
0x18000785b  cmp     [rcx+rax], r13b
0x18000785f  jnz     short loc_180007858
0x180007861  lea     rdx, [rax+1]
0x180007865  mov     rcx, [r12+18h]
0x18000786a  test    rcx, rcx
0x18000786d  jnz     short loc_180007874
0x18000786f  lea     eax, [rcx+2]
0x180007872  jmp     short loc_180007889
0x180007874  mov     rax, rbp
0x180007877  inc     rax
0x18000787a  cmp     [rcx+rax*2], r13w
0x18000787f  jnz     short loc_180007877
0x180007881  lea     rax, ds:2[rax*2]
0x180007889  lea     r14, [rdx+rax]
0x18000788d  add     r14, r8
0x180007890  lea     rsi, [rdi+48h]
0x180007894  cmp     [rdi+40h], r13
0x180007898  jz      short loc_18000789F
0x18000789a  cmp     [rsi], r14
0x18000789d  jnb     short loc_1800078D3
0x18000789f  mov     rdx, r14; dwBytes
0x1800078a2  mov     ecx, 8; dwFlags
0x1800078a7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800078ac  mov     r15, rax
0x1800078af  test    rax, rax
0x1800078b2  jz      short loc_1800078D3
0x1800078b4  mov     rbx, [rdi+40h]
0x1800078b8  call    cs:__imp_GetProcessHeap
0x1800078be  mov     r8, rbx; lpMem
0x1800078c1  xor     edx, edx; dwFlags
0x1800078c3  mov     rcx, rax; hHeap
0x1800078c6  call    cs:__imp_HeapFree
0x1800078cc  mov     [rdi+40h], r15
0x1800078d0  mov     [rsi], r14
0x1800078d3  mov     rbx, [rdi+40h]
0x1800078d7  test    rbx, rbx
0x1800078da  jz      loc_1800079D8
0x1800078e0  mov     rdx, [rsi]; DestinationSize
0x1800078e3  lea     rsi, [rdx+rbx]
0x1800078e7  cmp     rbx, rsi
0x1800078ea  jz      short loc_18000792A
0x1800078ec  mov     r8, [r12+38h]; Source
0x1800078f1  test    r8, r8
0x1800078f4  jz      short loc_18000792A
0x1800078f6  cmp     [r8], r13b
0x1800078f9  jz      short loc_18000792A
0x1800078fb  mov     rax, rbp
0x1800078fe  inc     rax
0x180007901  cmp     [r8+rax], r13b
0x180007905  jnz     short loc_1800078FE
0x180007907  lea     r14, [rax+1]
0x18000790b  cmp     rdx, r14
0x18000790e  jnb     short loc_180007916
0x180007910  mov     [rdi+10h], r13
0x180007914  jmp     short loc_180007933
0x180007916  mov     r9, r14; SourceSize
0x180007919  mov     rcx, rbx; Destination
0x18000791c  call    memcpy_s
0x180007921  mov     [rdi+10h], rbx
0x180007925  add     rbx, r14
0x180007928  jmp     short loc_18000792E
0x18000792a  mov     [rdi+10h], r13
0x18000792e  cmp     rbx, rsi
0x180007931  jz      short loc_18000797A
0x180007933  mov     r8, [r12+80h]; Source
0x18000793b  test    r8, r8
0x18000793e  jz      short loc_18000797A
0x180007940  cmp     [r8], r13b
0x180007943  jz      short loc_18000797A
0x180007945  mov     rax, rbp
0x180007948  inc     rax
0x18000794b  cmp     [r8+rax], r13b
0x18000794f  jnz     short loc_180007948
0x180007951  mov     rdx, rsi
0x180007954  lea     r14, [rax+1]
0x180007958  sub     rdx, rbx; DestinationSize
0x18000795b  cmp     rdx, r14
0x18000795e  jnb     short loc_180007966
0x180007960  mov     [rdi+20h], r13
0x180007964  jmp     short loc_180007983
0x180007966  mov     r9, r14; SourceSize
0x180007969  mov     rcx, rbx; Destination
0x18000796c  call    memcpy_s
0x180007971  mov     [rdi+20h], rbx
0x180007975  add     rbx, r14
0x180007978  jmp     short loc_18000797E
0x18000797a  mov     [rdi+20h], r13
0x18000797e  cmp     rbx, rsi
0x180007981  jz      short loc_1800079C4
0x180007983  mov     r8, [r12+18h]; Source
0x180007988  test    r8, r8
0x18000798b  jz      short loc_1800079C4
0x18000798d  cmp     [r8], r13w
0x180007991  jz      short loc_1800079C4
0x180007993  inc     rbp
0x180007996  cmp     [r8+rbp*2], r13w
0x18000799b  jnz     short loc_180007993
0x18000799d  mov     rdx, rsi
0x1800079a0  lea     r14, ds:2[rbp*2]
0x1800079a8  sub     rdx, rbx; DestinationSize
0x1800079ab  cmp     rdx, r14
0x1800079ae  jb      short loc_1800079C4
0x1800079b0  mov     r9, r14; SourceSize
0x1800079b3  mov     rcx, rbx; Destination
0x1800079b6  call    memcpy_s
0x1800079bb  mov     [rdi+38h], rbx
0x1800079bf  add     rbx, r14
0x1800079c2  jmp     short loc_1800079C8
0x1800079c4  mov     [rdi+38h], r13
0x1800079c8  sub     rsi, rbx
0x1800079cb  xor     edx, edx; Val
0x1800079cd  mov     r8, rsi; Size
0x1800079d0  mov     rcx, rbx; void *
0x1800079d3  call    memset_0
0x1800079d8  add     rsp, 28h
0x1800079dc  pop     r15
0x1800079de  pop     r14
0x1800079e0  pop     r13
0x1800079e2  pop     r12
0x1800079e4  pop     rdi
0x1800079e5  pop     rsi
0x1800079e6  pop     rbp
0x1800079e7  pop     rbx
0x1800079e8  retn
```
