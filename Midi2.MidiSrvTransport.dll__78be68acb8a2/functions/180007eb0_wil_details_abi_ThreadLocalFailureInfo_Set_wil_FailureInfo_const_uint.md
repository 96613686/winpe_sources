# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007eb0`
- end: `0x1800080c9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005700`

## callees

- `0x180002ff8`
- `0x180006c1c`
- `0x180007eb0`
- `0x180009228`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fa6`

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
0x180007eb0  push    rbx
0x180007eb2  push    rbp
0x180007eb3  push    rsi
0x180007eb4  push    rdi
0x180007eb5  push    r12
0x180007eb7  push    r13
0x180007eb9  push    r14
0x180007ebb  push    r15
0x180007ebd  sub     rsp, 28h
0x180007ec1  mov     [rcx+4], r8d
0x180007ec5  xor     r13d, r13d
0x180007ec8  mov     eax, [rdx+8]
0x180007ecb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007ecf  mov     [rcx+8], eax
0x180007ed2  mov     rdi, rcx
0x180007ed5  mov     [rcx+10h], r13
0x180007ed9  mov     r12, rdx
0x180007edc  movzx   eax, word ptr [rdx+40h]
0x180007ee0  mov     [rcx+18h], ax
0x180007ee4  mov     al, [rdx]
0x180007ee6  mov     [rcx+1Ah], al
0x180007ee9  mov     [rcx+20h], r13
0x180007eed  mov     rax, [rdx+88h]
0x180007ef4  mov     [rcx+28h], rax
0x180007ef8  mov     rax, [rdx+90h]
0x180007eff  mov     [rcx+30h], rax
0x180007f03  mov     [rcx+38h], r13
0x180007f07  mov     rcx, [rdx+38h]
0x180007f0b  lea     edx, [rbp+2]
0x180007f0e  test    rcx, rcx
0x180007f11  jnz     short loc_180007F18
0x180007f13  mov     r8d, edx
0x180007f16  jmp     short loc_180007F28
0x180007f18  mov     rax, rbp
0x180007f1b  inc     rax
0x180007f1e  cmp     [rcx+rax], r13b
0x180007f22  jnz     short loc_180007F1B
0x180007f24  lea     r8, [rax+1]; unsigned __int64
0x180007f28  mov     rcx, [r12+80h]
0x180007f30  test    rcx, rcx
0x180007f33  jz      short loc_180007F45
0x180007f35  mov     rax, rbp
0x180007f38  inc     rax
0x180007f3b  cmp     [rcx+rax], r13b
0x180007f3f  jnz     short loc_180007F38
0x180007f41  lea     rdx, [rax+1]
0x180007f45  mov     rcx, [r12+18h]
0x180007f4a  test    rcx, rcx
0x180007f4d  jnz     short loc_180007F54
0x180007f4f  lea     eax, [rcx+2]
0x180007f52  jmp     short loc_180007F69
0x180007f54  mov     rax, rbp
0x180007f57  inc     rax
0x180007f5a  cmp     [rcx+rax*2], r13w
0x180007f5f  jnz     short loc_180007F57
0x180007f61  lea     rax, ds:2[rax*2]
0x180007f69  lea     r14, [rdx+rax]
0x180007f6d  add     r14, r8
0x180007f70  lea     rsi, [rdi+48h]
0x180007f74  cmp     [rdi+40h], r13
0x180007f78  jz      short loc_180007F7F
0x180007f7a  cmp     [rsi], r14
0x180007f7d  jnb     short loc_180007FB3
0x180007f7f  mov     rdx, r14; dwBytes
0x180007f82  mov     ecx, 8; dwFlags
0x180007f87  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007f8c  mov     r15, rax
0x180007f8f  test    rax, rax
0x180007f92  jz      short loc_180007FB3
0x180007f94  mov     rbx, [rdi+40h]
0x180007f98  call    cs:__imp_GetProcessHeap
0x180007f9e  mov     r8, rbx; lpMem
0x180007fa1  xor     edx, edx; dwFlags
0x180007fa3  mov     rcx, rax; hHeap
0x180007fa6  call    cs:__imp_HeapFree
0x180007fac  mov     [rdi+40h], r15
0x180007fb0  mov     [rsi], r14
0x180007fb3  mov     rbx, [rdi+40h]
0x180007fb7  test    rbx, rbx
0x180007fba  jz      loc_1800080B8
0x180007fc0  mov     rdx, [rsi]; DestinationSize
0x180007fc3  lea     rsi, [rdx+rbx]
0x180007fc7  cmp     rbx, rsi
0x180007fca  jz      short loc_18000800A
0x180007fcc  mov     r8, [r12+38h]; Source
0x180007fd1  test    r8, r8
0x180007fd4  jz      short loc_18000800A
0x180007fd6  cmp     [r8], r13b
0x180007fd9  jz      short loc_18000800A
0x180007fdb  mov     rax, rbp
0x180007fde  inc     rax
0x180007fe1  cmp     [r8+rax], r13b
0x180007fe5  jnz     short loc_180007FDE
0x180007fe7  lea     r14, [rax+1]
0x180007feb  cmp     rdx, r14
0x180007fee  jnb     short loc_180007FF6
0x180007ff0  mov     [rdi+10h], r13
0x180007ff4  jmp     short loc_180008013
0x180007ff6  mov     r9, r14; SourceSize
0x180007ff9  mov     rcx, rbx; Destination
0x180007ffc  call    memcpy_s
0x180008001  mov     [rdi+10h], rbx
0x180008005  add     rbx, r14
0x180008008  jmp     short loc_18000800E
0x18000800a  mov     [rdi+10h], r13
0x18000800e  cmp     rbx, rsi
0x180008011  jz      short loc_18000805A
0x180008013  mov     r8, [r12+80h]; Source
0x18000801b  test    r8, r8
0x18000801e  jz      short loc_18000805A
0x180008020  cmp     [r8], r13b
0x180008023  jz      short loc_18000805A
0x180008025  mov     rax, rbp
0x180008028  inc     rax
0x18000802b  cmp     [r8+rax], r13b
0x18000802f  jnz     short loc_180008028
0x180008031  mov     rdx, rsi
0x180008034  lea     r14, [rax+1]
0x180008038  sub     rdx, rbx; DestinationSize
0x18000803b  cmp     rdx, r14
0x18000803e  jnb     short loc_180008046
0x180008040  mov     [rdi+20h], r13
0x180008044  jmp     short loc_180008063
0x180008046  mov     r9, r14; SourceSize
0x180008049  mov     rcx, rbx; Destination
0x18000804c  call    memcpy_s
0x180008051  mov     [rdi+20h], rbx
0x180008055  add     rbx, r14
0x180008058  jmp     short loc_18000805E
0x18000805a  mov     [rdi+20h], r13
0x18000805e  cmp     rbx, rsi
0x180008061  jz      short loc_1800080A4
0x180008063  mov     r8, [r12+18h]; Source
0x180008068  test    r8, r8
0x18000806b  jz      short loc_1800080A4
0x18000806d  cmp     [r8], r13w
0x180008071  jz      short loc_1800080A4
0x180008073  inc     rbp
0x180008076  cmp     [r8+rbp*2], r13w
0x18000807b  jnz     short loc_180008073
0x18000807d  mov     rdx, rsi
0x180008080  lea     r14, ds:2[rbp*2]
0x180008088  sub     rdx, rbx; DestinationSize
0x18000808b  cmp     rdx, r14
0x18000808e  jb      short loc_1800080A4
0x180008090  mov     r9, r14; SourceSize
0x180008093  mov     rcx, rbx; Destination
0x180008096  call    memcpy_s
0x18000809b  mov     [rdi+38h], rbx
0x18000809f  add     rbx, r14
0x1800080a2  jmp     short loc_1800080A8
0x1800080a4  mov     [rdi+38h], r13
0x1800080a8  sub     rsi, rbx
0x1800080ab  xor     edx, edx; Val
0x1800080ad  mov     r8, rsi; Size
0x1800080b0  mov     rcx, rbx; void *
0x1800080b3  call    memset_0
0x1800080b8  add     rsp, 28h
0x1800080bc  pop     r15
0x1800080be  pop     r14
0x1800080c0  pop     r13
0x1800080c2  pop     r12
0x1800080c4  pop     rdi
0x1800080c5  pop     rsi
0x1800080c6  pop     rbp
0x1800080c7  pop     rbx
0x1800080c8  retn
```
