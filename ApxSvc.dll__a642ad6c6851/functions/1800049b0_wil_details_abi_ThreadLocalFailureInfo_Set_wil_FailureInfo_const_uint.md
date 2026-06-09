# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800049b0`
- end: `0x180004bc9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800035f0`

## callees

- `0x180001ef2`
- `0x180004648`
- `0x1800049b0`
- `0x180005990`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a98`

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
0x1800049b0  push    rbx
0x1800049b2  push    rbp
0x1800049b3  push    rsi
0x1800049b4  push    rdi
0x1800049b5  push    r12
0x1800049b7  push    r13
0x1800049b9  push    r14
0x1800049bb  push    r15
0x1800049bd  sub     rsp, 28h
0x1800049c1  mov     [rcx+4], r8d
0x1800049c5  xor     r13d, r13d
0x1800049c8  mov     eax, [rdx+8]
0x1800049cb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800049cf  mov     [rcx+8], eax
0x1800049d2  mov     rdi, rcx
0x1800049d5  mov     [rcx+10h], r13
0x1800049d9  mov     r12, rdx
0x1800049dc  movzx   eax, word ptr [rdx+40h]
0x1800049e0  mov     [rcx+18h], ax
0x1800049e4  mov     al, [rdx]
0x1800049e6  mov     [rcx+1Ah], al
0x1800049e9  mov     [rcx+20h], r13
0x1800049ed  mov     rax, [rdx+88h]
0x1800049f4  mov     [rcx+28h], rax
0x1800049f8  mov     rax, [rdx+90h]
0x1800049ff  mov     [rcx+30h], rax
0x180004a03  mov     [rcx+38h], r13
0x180004a07  mov     rcx, [rdx+38h]
0x180004a0b  lea     edx, [rbp+2]
0x180004a0e  test    rcx, rcx
0x180004a11  jnz     short loc_180004A18
0x180004a13  mov     r8d, edx
0x180004a16  jmp     short loc_180004A28
0x180004a18  mov     rax, rbp
0x180004a1b  inc     rax
0x180004a1e  cmp     [rcx+rax], r13b
0x180004a22  jnz     short loc_180004A1B
0x180004a24  lea     r8, [rax+1]; unsigned __int64
0x180004a28  mov     rcx, [r12+80h]
0x180004a30  test    rcx, rcx
0x180004a33  jz      short loc_180004A45
0x180004a35  mov     rax, rbp
0x180004a38  inc     rax
0x180004a3b  cmp     [rcx+rax], r13b
0x180004a3f  jnz     short loc_180004A38
0x180004a41  lea     rdx, [rax+1]
0x180004a45  mov     rcx, [r12+18h]
0x180004a4a  test    rcx, rcx
0x180004a4d  jnz     short loc_180004A54
0x180004a4f  lea     eax, [rcx+2]
0x180004a52  jmp     short loc_180004A69
0x180004a54  mov     rax, rbp
0x180004a57  inc     rax
0x180004a5a  cmp     [rcx+rax*2], r13w
0x180004a5f  jnz     short loc_180004A57
0x180004a61  lea     rax, ds:2[rax*2]
0x180004a69  lea     r14, [rdx+rax]
0x180004a6d  add     r14, r8
0x180004a70  lea     rsi, [rdi+48h]
0x180004a74  cmp     [rdi+40h], r13
0x180004a78  jz      short loc_180004A7F
0x180004a7a  cmp     [rsi], r14
0x180004a7d  jnb     short loc_180004AB3
0x180004a7f  mov     rdx, r14; dwBytes
0x180004a82  mov     ecx, 8; dwFlags
0x180004a87  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a8c  mov     r15, rax
0x180004a8f  test    rax, rax
0x180004a92  jz      short loc_180004AB3
0x180004a94  mov     rbx, [rdi+40h]
0x180004a98  call    cs:__imp_GetProcessHeap
0x180004a9e  mov     r8, rbx; lpMem
0x180004aa1  xor     edx, edx; dwFlags
0x180004aa3  mov     rcx, rax; hHeap
0x180004aa6  call    cs:__imp_HeapFree
0x180004aac  mov     [rdi+40h], r15
0x180004ab0  mov     [rsi], r14
0x180004ab3  mov     rbx, [rdi+40h]
0x180004ab7  test    rbx, rbx
0x180004aba  jz      loc_180004BB8
0x180004ac0  mov     rdx, [rsi]; DestinationSize
0x180004ac3  lea     rsi, [rdx+rbx]
0x180004ac7  cmp     rbx, rsi
0x180004aca  jz      short loc_180004B0A
0x180004acc  mov     r8, [r12+38h]; Source
0x180004ad1  test    r8, r8
0x180004ad4  jz      short loc_180004B0A
0x180004ad6  cmp     [r8], r13b
0x180004ad9  jz      short loc_180004B0A
0x180004adb  mov     rax, rbp
0x180004ade  inc     rax
0x180004ae1  cmp     [r8+rax], r13b
0x180004ae5  jnz     short loc_180004ADE
0x180004ae7  lea     r14, [rax+1]
0x180004aeb  cmp     rdx, r14
0x180004aee  jnb     short loc_180004AF6
0x180004af0  mov     [rdi+10h], r13
0x180004af4  jmp     short loc_180004B13
0x180004af6  mov     r9, r14; SourceSize
0x180004af9  mov     rcx, rbx; Destination
0x180004afc  call    memcpy_s
0x180004b01  mov     [rdi+10h], rbx
0x180004b05  add     rbx, r14
0x180004b08  jmp     short loc_180004B0E
0x180004b0a  mov     [rdi+10h], r13
0x180004b0e  cmp     rbx, rsi
0x180004b11  jz      short loc_180004B5A
0x180004b13  mov     r8, [r12+80h]; Source
0x180004b1b  test    r8, r8
0x180004b1e  jz      short loc_180004B5A
0x180004b20  cmp     [r8], r13b
0x180004b23  jz      short loc_180004B5A
0x180004b25  mov     rax, rbp
0x180004b28  inc     rax
0x180004b2b  cmp     [r8+rax], r13b
0x180004b2f  jnz     short loc_180004B28
0x180004b31  mov     rdx, rsi
0x180004b34  lea     r14, [rax+1]
0x180004b38  sub     rdx, rbx; DestinationSize
0x180004b3b  cmp     rdx, r14
0x180004b3e  jnb     short loc_180004B46
0x180004b40  mov     [rdi+20h], r13
0x180004b44  jmp     short loc_180004B63
0x180004b46  mov     r9, r14; SourceSize
0x180004b49  mov     rcx, rbx; Destination
0x180004b4c  call    memcpy_s
0x180004b51  mov     [rdi+20h], rbx
0x180004b55  add     rbx, r14
0x180004b58  jmp     short loc_180004B5E
0x180004b5a  mov     [rdi+20h], r13
0x180004b5e  cmp     rbx, rsi
0x180004b61  jz      short loc_180004BA4
0x180004b63  mov     r8, [r12+18h]; Source
0x180004b68  test    r8, r8
0x180004b6b  jz      short loc_180004BA4
0x180004b6d  cmp     [r8], r13w
0x180004b71  jz      short loc_180004BA4
0x180004b73  inc     rbp
0x180004b76  cmp     [r8+rbp*2], r13w
0x180004b7b  jnz     short loc_180004B73
0x180004b7d  mov     rdx, rsi
0x180004b80  lea     r14, ds:2[rbp*2]
0x180004b88  sub     rdx, rbx; DestinationSize
0x180004b8b  cmp     rdx, r14
0x180004b8e  jb      short loc_180004BA4
0x180004b90  mov     r9, r14; SourceSize
0x180004b93  mov     rcx, rbx; Destination
0x180004b96  call    memcpy_s
0x180004b9b  mov     [rdi+38h], rbx
0x180004b9f  add     rbx, r14
0x180004ba2  jmp     short loc_180004BA8
0x180004ba4  mov     [rdi+38h], r13
0x180004ba8  sub     rsi, rbx
0x180004bab  xor     edx, edx; Val
0x180004bad  mov     r8, rsi; Size
0x180004bb0  mov     rcx, rbx; void *
0x180004bb3  call    memset_0
0x180004bb8  add     rsp, 28h
0x180004bbc  pop     r15
0x180004bbe  pop     r14
0x180004bc0  pop     r13
0x180004bc2  pop     r12
0x180004bc4  pop     rdi
0x180004bc5  pop     rsi
0x180004bc6  pop     rbp
0x180004bc7  pop     rbx
0x180004bc8  retn
```
