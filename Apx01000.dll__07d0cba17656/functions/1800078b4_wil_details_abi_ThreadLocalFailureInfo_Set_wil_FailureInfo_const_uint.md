# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800078b4`
- end: `0x180007acd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004fa0`

## callees

- `0x1800027c8`
- `0x1800061f8`
- `0x1800078b4`
- `0x180009568`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799c`

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
0x1800078b4  push    rbx
0x1800078b6  push    rbp
0x1800078b7  push    rsi
0x1800078b8  push    rdi
0x1800078b9  push    r12
0x1800078bb  push    r13
0x1800078bd  push    r14
0x1800078bf  push    r15
0x1800078c1  sub     rsp, 28h
0x1800078c5  mov     [rcx+4], r8d
0x1800078c9  xor     r13d, r13d
0x1800078cc  mov     eax, [rdx+8]
0x1800078cf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800078d3  mov     [rcx+8], eax
0x1800078d6  mov     rdi, rcx
0x1800078d9  mov     [rcx+10h], r13
0x1800078dd  mov     r12, rdx
0x1800078e0  movzx   eax, word ptr [rdx+40h]
0x1800078e4  mov     [rcx+18h], ax
0x1800078e8  mov     al, [rdx]
0x1800078ea  mov     [rcx+1Ah], al
0x1800078ed  mov     [rcx+20h], r13
0x1800078f1  mov     rax, [rdx+88h]
0x1800078f8  mov     [rcx+28h], rax
0x1800078fc  mov     rax, [rdx+90h]
0x180007903  mov     [rcx+30h], rax
0x180007907  mov     [rcx+38h], r13
0x18000790b  mov     rcx, [rdx+38h]
0x18000790f  lea     edx, [rbp+2]
0x180007912  test    rcx, rcx
0x180007915  jnz     short loc_18000791C
0x180007917  mov     r8d, edx
0x18000791a  jmp     short loc_18000792C
0x18000791c  mov     rax, rbp
0x18000791f  inc     rax
0x180007922  cmp     [rcx+rax], r13b
0x180007926  jnz     short loc_18000791F
0x180007928  lea     r8, [rax+1]; unsigned __int64
0x18000792c  mov     rcx, [r12+80h]
0x180007934  test    rcx, rcx
0x180007937  jz      short loc_180007949
0x180007939  mov     rax, rbp
0x18000793c  inc     rax
0x18000793f  cmp     [rcx+rax], r13b
0x180007943  jnz     short loc_18000793C
0x180007945  lea     rdx, [rax+1]
0x180007949  mov     rcx, [r12+18h]
0x18000794e  test    rcx, rcx
0x180007951  jnz     short loc_180007958
0x180007953  lea     eax, [rcx+2]
0x180007956  jmp     short loc_18000796D
0x180007958  mov     rax, rbp
0x18000795b  inc     rax
0x18000795e  cmp     [rcx+rax*2], r13w
0x180007963  jnz     short loc_18000795B
0x180007965  lea     rax, ds:2[rax*2]
0x18000796d  lea     r14, [rdx+rax]
0x180007971  add     r14, r8
0x180007974  lea     rsi, [rdi+48h]
0x180007978  cmp     [rdi+40h], r13
0x18000797c  jz      short loc_180007983
0x18000797e  cmp     [rsi], r14
0x180007981  jnb     short loc_1800079B7
0x180007983  mov     rdx, r14; dwBytes
0x180007986  mov     ecx, 8; dwFlags
0x18000798b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007990  mov     r15, rax
0x180007993  test    rax, rax
0x180007996  jz      short loc_1800079B7
0x180007998  mov     rbx, [rdi+40h]
0x18000799c  call    cs:__imp_GetProcessHeap
0x1800079a2  mov     r8, rbx; lpMem
0x1800079a5  xor     edx, edx; dwFlags
0x1800079a7  mov     rcx, rax; hHeap
0x1800079aa  call    cs:__imp_HeapFree
0x1800079b0  mov     [rdi+40h], r15
0x1800079b4  mov     [rsi], r14
0x1800079b7  mov     rbx, [rdi+40h]
0x1800079bb  test    rbx, rbx
0x1800079be  jz      loc_180007ABC
0x1800079c4  mov     rdx, [rsi]; DestinationSize
0x1800079c7  lea     rsi, [rdx+rbx]
0x1800079cb  cmp     rbx, rsi
0x1800079ce  jz      short loc_180007A0E
0x1800079d0  mov     r8, [r12+38h]; Source
0x1800079d5  test    r8, r8
0x1800079d8  jz      short loc_180007A0E
0x1800079da  cmp     [r8], r13b
0x1800079dd  jz      short loc_180007A0E
0x1800079df  mov     rax, rbp
0x1800079e2  inc     rax
0x1800079e5  cmp     [r8+rax], r13b
0x1800079e9  jnz     short loc_1800079E2
0x1800079eb  lea     r14, [rax+1]
0x1800079ef  cmp     rdx, r14
0x1800079f2  jnb     short loc_1800079FA
0x1800079f4  mov     [rdi+10h], r13
0x1800079f8  jmp     short loc_180007A17
0x1800079fa  mov     r9, r14; SourceSize
0x1800079fd  mov     rcx, rbx; Destination
0x180007a00  call    memcpy_s
0x180007a05  mov     [rdi+10h], rbx
0x180007a09  add     rbx, r14
0x180007a0c  jmp     short loc_180007A12
0x180007a0e  mov     [rdi+10h], r13
0x180007a12  cmp     rbx, rsi
0x180007a15  jz      short loc_180007A5E
0x180007a17  mov     r8, [r12+80h]; Source
0x180007a1f  test    r8, r8
0x180007a22  jz      short loc_180007A5E
0x180007a24  cmp     [r8], r13b
0x180007a27  jz      short loc_180007A5E
0x180007a29  mov     rax, rbp
0x180007a2c  inc     rax
0x180007a2f  cmp     [r8+rax], r13b
0x180007a33  jnz     short loc_180007A2C
0x180007a35  mov     rdx, rsi
0x180007a38  lea     r14, [rax+1]
0x180007a3c  sub     rdx, rbx; DestinationSize
0x180007a3f  cmp     rdx, r14
0x180007a42  jnb     short loc_180007A4A
0x180007a44  mov     [rdi+20h], r13
0x180007a48  jmp     short loc_180007A67
0x180007a4a  mov     r9, r14; SourceSize
0x180007a4d  mov     rcx, rbx; Destination
0x180007a50  call    memcpy_s
0x180007a55  mov     [rdi+20h], rbx
0x180007a59  add     rbx, r14
0x180007a5c  jmp     short loc_180007A62
0x180007a5e  mov     [rdi+20h], r13
0x180007a62  cmp     rbx, rsi
0x180007a65  jz      short loc_180007AA8
0x180007a67  mov     r8, [r12+18h]; Source
0x180007a6c  test    r8, r8
0x180007a6f  jz      short loc_180007AA8
0x180007a71  cmp     [r8], r13w
0x180007a75  jz      short loc_180007AA8
0x180007a77  inc     rbp
0x180007a7a  cmp     [r8+rbp*2], r13w
0x180007a7f  jnz     short loc_180007A77
0x180007a81  mov     rdx, rsi
0x180007a84  lea     r14, ds:2[rbp*2]
0x180007a8c  sub     rdx, rbx; DestinationSize
0x180007a8f  cmp     rdx, r14
0x180007a92  jb      short loc_180007AA8
0x180007a94  mov     r9, r14; SourceSize
0x180007a97  mov     rcx, rbx; Destination
0x180007a9a  call    memcpy_s
0x180007a9f  mov     [rdi+38h], rbx
0x180007aa3  add     rbx, r14
0x180007aa6  jmp     short loc_180007AAC
0x180007aa8  mov     [rdi+38h], r13
0x180007aac  sub     rsi, rbx
0x180007aaf  xor     edx, edx; Val
0x180007ab1  mov     r8, rsi; Size
0x180007ab4  mov     rcx, rbx; void *
0x180007ab7  call    memset_0
0x180007abc  add     rsp, 28h
0x180007ac0  pop     r15
0x180007ac2  pop     r14
0x180007ac4  pop     r13
0x180007ac6  pop     r12
0x180007ac8  pop     rdi
0x180007ac9  pop     rsi
0x180007aca  pop     rbp
0x180007acb  pop     rbx
0x180007acc  retn
```
