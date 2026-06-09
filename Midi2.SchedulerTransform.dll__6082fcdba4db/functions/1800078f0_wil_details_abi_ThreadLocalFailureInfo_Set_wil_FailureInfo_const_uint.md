# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800078f0`
- end: `0x180007b09`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005150`

## callees

- `0x180002a68`
- `0x18000665c`
- `0x1800078f0`
- `0x180008c28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079e6`

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
0x1800078f0  push    rbx
0x1800078f2  push    rbp
0x1800078f3  push    rsi
0x1800078f4  push    rdi
0x1800078f5  push    r12
0x1800078f7  push    r13
0x1800078f9  push    r14
0x1800078fb  push    r15
0x1800078fd  sub     rsp, 28h
0x180007901  mov     [rcx+4], r8d
0x180007905  xor     r13d, r13d
0x180007908  mov     eax, [rdx+8]
0x18000790b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000790f  mov     [rcx+8], eax
0x180007912  mov     rdi, rcx
0x180007915  mov     [rcx+10h], r13
0x180007919  mov     r12, rdx
0x18000791c  movzx   eax, word ptr [rdx+40h]
0x180007920  mov     [rcx+18h], ax
0x180007924  mov     al, [rdx]
0x180007926  mov     [rcx+1Ah], al
0x180007929  mov     [rcx+20h], r13
0x18000792d  mov     rax, [rdx+88h]
0x180007934  mov     [rcx+28h], rax
0x180007938  mov     rax, [rdx+90h]
0x18000793f  mov     [rcx+30h], rax
0x180007943  mov     [rcx+38h], r13
0x180007947  mov     rcx, [rdx+38h]
0x18000794b  lea     edx, [rbp+2]
0x18000794e  test    rcx, rcx
0x180007951  jnz     short loc_180007958
0x180007953  mov     r8d, edx
0x180007956  jmp     short loc_180007968
0x180007958  mov     rax, rbp
0x18000795b  inc     rax
0x18000795e  cmp     [rcx+rax], r13b
0x180007962  jnz     short loc_18000795B
0x180007964  lea     r8, [rax+1]; unsigned __int64
0x180007968  mov     rcx, [r12+80h]
0x180007970  test    rcx, rcx
0x180007973  jz      short loc_180007985
0x180007975  mov     rax, rbp
0x180007978  inc     rax
0x18000797b  cmp     [rcx+rax], r13b
0x18000797f  jnz     short loc_180007978
0x180007981  lea     rdx, [rax+1]
0x180007985  mov     rcx, [r12+18h]
0x18000798a  test    rcx, rcx
0x18000798d  jnz     short loc_180007994
0x18000798f  lea     eax, [rcx+2]
0x180007992  jmp     short loc_1800079A9
0x180007994  mov     rax, rbp
0x180007997  inc     rax
0x18000799a  cmp     [rcx+rax*2], r13w
0x18000799f  jnz     short loc_180007997
0x1800079a1  lea     rax, ds:2[rax*2]
0x1800079a9  lea     r14, [rdx+rax]
0x1800079ad  add     r14, r8
0x1800079b0  lea     rsi, [rdi+48h]
0x1800079b4  cmp     [rdi+40h], r13
0x1800079b8  jz      short loc_1800079BF
0x1800079ba  cmp     [rsi], r14
0x1800079bd  jnb     short loc_1800079F3
0x1800079bf  mov     rdx, r14; dwBytes
0x1800079c2  mov     ecx, 8; dwFlags
0x1800079c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800079cc  mov     r15, rax
0x1800079cf  test    rax, rax
0x1800079d2  jz      short loc_1800079F3
0x1800079d4  mov     rbx, [rdi+40h]
0x1800079d8  call    cs:__imp_GetProcessHeap
0x1800079de  mov     r8, rbx; lpMem
0x1800079e1  xor     edx, edx; dwFlags
0x1800079e3  mov     rcx, rax; hHeap
0x1800079e6  call    cs:__imp_HeapFree
0x1800079ec  mov     [rdi+40h], r15
0x1800079f0  mov     [rsi], r14
0x1800079f3  mov     rbx, [rdi+40h]
0x1800079f7  test    rbx, rbx
0x1800079fa  jz      loc_180007AF8
0x180007a00  mov     rdx, [rsi]; DestinationSize
0x180007a03  lea     rsi, [rdx+rbx]
0x180007a07  cmp     rbx, rsi
0x180007a0a  jz      short loc_180007A4A
0x180007a0c  mov     r8, [r12+38h]; Source
0x180007a11  test    r8, r8
0x180007a14  jz      short loc_180007A4A
0x180007a16  cmp     [r8], r13b
0x180007a19  jz      short loc_180007A4A
0x180007a1b  mov     rax, rbp
0x180007a1e  inc     rax
0x180007a21  cmp     [r8+rax], r13b
0x180007a25  jnz     short loc_180007A1E
0x180007a27  lea     r14, [rax+1]
0x180007a2b  cmp     rdx, r14
0x180007a2e  jnb     short loc_180007A36
0x180007a30  mov     [rdi+10h], r13
0x180007a34  jmp     short loc_180007A53
0x180007a36  mov     r9, r14; SourceSize
0x180007a39  mov     rcx, rbx; Destination
0x180007a3c  call    memcpy_s
0x180007a41  mov     [rdi+10h], rbx
0x180007a45  add     rbx, r14
0x180007a48  jmp     short loc_180007A4E
0x180007a4a  mov     [rdi+10h], r13
0x180007a4e  cmp     rbx, rsi
0x180007a51  jz      short loc_180007A9A
0x180007a53  mov     r8, [r12+80h]; Source
0x180007a5b  test    r8, r8
0x180007a5e  jz      short loc_180007A9A
0x180007a60  cmp     [r8], r13b
0x180007a63  jz      short loc_180007A9A
0x180007a65  mov     rax, rbp
0x180007a68  inc     rax
0x180007a6b  cmp     [r8+rax], r13b
0x180007a6f  jnz     short loc_180007A68
0x180007a71  mov     rdx, rsi
0x180007a74  lea     r14, [rax+1]
0x180007a78  sub     rdx, rbx; DestinationSize
0x180007a7b  cmp     rdx, r14
0x180007a7e  jnb     short loc_180007A86
0x180007a80  mov     [rdi+20h], r13
0x180007a84  jmp     short loc_180007AA3
0x180007a86  mov     r9, r14; SourceSize
0x180007a89  mov     rcx, rbx; Destination
0x180007a8c  call    memcpy_s
0x180007a91  mov     [rdi+20h], rbx
0x180007a95  add     rbx, r14
0x180007a98  jmp     short loc_180007A9E
0x180007a9a  mov     [rdi+20h], r13
0x180007a9e  cmp     rbx, rsi
0x180007aa1  jz      short loc_180007AE4
0x180007aa3  mov     r8, [r12+18h]; Source
0x180007aa8  test    r8, r8
0x180007aab  jz      short loc_180007AE4
0x180007aad  cmp     [r8], r13w
0x180007ab1  jz      short loc_180007AE4
0x180007ab3  inc     rbp
0x180007ab6  cmp     [r8+rbp*2], r13w
0x180007abb  jnz     short loc_180007AB3
0x180007abd  mov     rdx, rsi
0x180007ac0  lea     r14, ds:2[rbp*2]
0x180007ac8  sub     rdx, rbx; DestinationSize
0x180007acb  cmp     rdx, r14
0x180007ace  jb      short loc_180007AE4
0x180007ad0  mov     r9, r14; SourceSize
0x180007ad3  mov     rcx, rbx; Destination
0x180007ad6  call    memcpy_s
0x180007adb  mov     [rdi+38h], rbx
0x180007adf  add     rbx, r14
0x180007ae2  jmp     short loc_180007AE8
0x180007ae4  mov     [rdi+38h], r13
0x180007ae8  sub     rsi, rbx
0x180007aeb  xor     edx, edx; Val
0x180007aed  mov     r8, rsi; Size
0x180007af0  mov     rcx, rbx; void *
0x180007af3  call    memset_0
0x180007af8  add     rsp, 28h
0x180007afc  pop     r15
0x180007afe  pop     r14
0x180007b00  pop     r13
0x180007b02  pop     r12
0x180007b04  pop     rdi
0x180007b05  pop     rsi
0x180007b06  pop     rbp
0x180007b07  pop     rbx
0x180007b08  retn
```
