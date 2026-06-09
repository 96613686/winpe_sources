# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005a10`
- end: `0x180005c29`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800044c0`

## callees

- `0x180002f7c`
- `0x180005518`
- `0x180005a10`
- `0x1800069f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005af8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005af8`

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
0x180005a10  push    rbx
0x180005a12  push    rbp
0x180005a13  push    rsi
0x180005a14  push    rdi
0x180005a15  push    r12
0x180005a17  push    r13
0x180005a19  push    r14
0x180005a1b  push    r15
0x180005a1d  sub     rsp, 28h
0x180005a21  mov     [rcx+4], r8d
0x180005a25  xor     r13d, r13d
0x180005a28  mov     eax, [rdx+8]
0x180005a2b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005a2f  mov     [rcx+8], eax
0x180005a32  mov     rdi, rcx
0x180005a35  mov     [rcx+10h], r13
0x180005a39  mov     r12, rdx
0x180005a3c  movzx   eax, word ptr [rdx+40h]
0x180005a40  mov     [rcx+18h], ax
0x180005a44  mov     al, [rdx]
0x180005a46  mov     [rcx+1Ah], al
0x180005a49  mov     [rcx+20h], r13
0x180005a4d  mov     rax, [rdx+88h]
0x180005a54  mov     [rcx+28h], rax
0x180005a58  mov     rax, [rdx+90h]
0x180005a5f  mov     [rcx+30h], rax
0x180005a63  mov     [rcx+38h], r13
0x180005a67  mov     rcx, [rdx+38h]
0x180005a6b  lea     edx, [rbp+2]
0x180005a6e  test    rcx, rcx
0x180005a71  jnz     short loc_180005A78
0x180005a73  mov     r8d, edx
0x180005a76  jmp     short loc_180005A88
0x180005a78  mov     rax, rbp
0x180005a7b  inc     rax
0x180005a7e  cmp     [rcx+rax], r13b
0x180005a82  jnz     short loc_180005A7B
0x180005a84  lea     r8, [rax+1]; unsigned __int64
0x180005a88  mov     rcx, [r12+80h]
0x180005a90  test    rcx, rcx
0x180005a93  jz      short loc_180005AA5
0x180005a95  mov     rax, rbp
0x180005a98  inc     rax
0x180005a9b  cmp     [rcx+rax], r13b
0x180005a9f  jnz     short loc_180005A98
0x180005aa1  lea     rdx, [rax+1]
0x180005aa5  mov     rcx, [r12+18h]
0x180005aaa  test    rcx, rcx
0x180005aad  jnz     short loc_180005AB4
0x180005aaf  lea     eax, [rcx+2]
0x180005ab2  jmp     short loc_180005AC9
0x180005ab4  mov     rax, rbp
0x180005ab7  inc     rax
0x180005aba  cmp     [rcx+rax*2], r13w
0x180005abf  jnz     short loc_180005AB7
0x180005ac1  lea     rax, ds:2[rax*2]
0x180005ac9  lea     r14, [rdx+rax]
0x180005acd  add     r14, r8
0x180005ad0  lea     rsi, [rdi+48h]
0x180005ad4  cmp     [rdi+40h], r13
0x180005ad8  jz      short loc_180005ADF
0x180005ada  cmp     [rsi], r14
0x180005add  jnb     short loc_180005B13
0x180005adf  mov     rdx, r14; dwBytes
0x180005ae2  mov     ecx, 8; dwFlags
0x180005ae7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005aec  mov     r15, rax
0x180005aef  test    rax, rax
0x180005af2  jz      short loc_180005B13
0x180005af4  mov     rbx, [rdi+40h]
0x180005af8  call    cs:__imp_GetProcessHeap
0x180005afe  mov     r8, rbx; lpMem
0x180005b01  xor     edx, edx; dwFlags
0x180005b03  mov     rcx, rax; hHeap
0x180005b06  call    cs:__imp_HeapFree
0x180005b0c  mov     [rdi+40h], r15
0x180005b10  mov     [rsi], r14
0x180005b13  mov     rbx, [rdi+40h]
0x180005b17  test    rbx, rbx
0x180005b1a  jz      loc_180005C18
0x180005b20  mov     rdx, [rsi]; DestinationSize
0x180005b23  lea     rsi, [rdx+rbx]
0x180005b27  cmp     rbx, rsi
0x180005b2a  jz      short loc_180005B6A
0x180005b2c  mov     r8, [r12+38h]; Source
0x180005b31  test    r8, r8
0x180005b34  jz      short loc_180005B6A
0x180005b36  cmp     [r8], r13b
0x180005b39  jz      short loc_180005B6A
0x180005b3b  mov     rax, rbp
0x180005b3e  inc     rax
0x180005b41  cmp     [r8+rax], r13b
0x180005b45  jnz     short loc_180005B3E
0x180005b47  lea     r14, [rax+1]
0x180005b4b  cmp     rdx, r14
0x180005b4e  jnb     short loc_180005B56
0x180005b50  mov     [rdi+10h], r13
0x180005b54  jmp     short loc_180005B73
0x180005b56  mov     r9, r14; SourceSize
0x180005b59  mov     rcx, rbx; Destination
0x180005b5c  call    memcpy_s
0x180005b61  mov     [rdi+10h], rbx
0x180005b65  add     rbx, r14
0x180005b68  jmp     short loc_180005B6E
0x180005b6a  mov     [rdi+10h], r13
0x180005b6e  cmp     rbx, rsi
0x180005b71  jz      short loc_180005BBA
0x180005b73  mov     r8, [r12+80h]; Source
0x180005b7b  test    r8, r8
0x180005b7e  jz      short loc_180005BBA
0x180005b80  cmp     [r8], r13b
0x180005b83  jz      short loc_180005BBA
0x180005b85  mov     rax, rbp
0x180005b88  inc     rax
0x180005b8b  cmp     [r8+rax], r13b
0x180005b8f  jnz     short loc_180005B88
0x180005b91  mov     rdx, rsi
0x180005b94  lea     r14, [rax+1]
0x180005b98  sub     rdx, rbx; DestinationSize
0x180005b9b  cmp     rdx, r14
0x180005b9e  jnb     short loc_180005BA6
0x180005ba0  mov     [rdi+20h], r13
0x180005ba4  jmp     short loc_180005BC3
0x180005ba6  mov     r9, r14; SourceSize
0x180005ba9  mov     rcx, rbx; Destination
0x180005bac  call    memcpy_s
0x180005bb1  mov     [rdi+20h], rbx
0x180005bb5  add     rbx, r14
0x180005bb8  jmp     short loc_180005BBE
0x180005bba  mov     [rdi+20h], r13
0x180005bbe  cmp     rbx, rsi
0x180005bc1  jz      short loc_180005C04
0x180005bc3  mov     r8, [r12+18h]; Source
0x180005bc8  test    r8, r8
0x180005bcb  jz      short loc_180005C04
0x180005bcd  cmp     [r8], r13w
0x180005bd1  jz      short loc_180005C04
0x180005bd3  inc     rbp
0x180005bd6  cmp     [r8+rbp*2], r13w
0x180005bdb  jnz     short loc_180005BD3
0x180005bdd  mov     rdx, rsi
0x180005be0  lea     r14, ds:2[rbp*2]
0x180005be8  sub     rdx, rbx; DestinationSize
0x180005beb  cmp     rdx, r14
0x180005bee  jb      short loc_180005C04
0x180005bf0  mov     r9, r14; SourceSize
0x180005bf3  mov     rcx, rbx; Destination
0x180005bf6  call    memcpy_s
0x180005bfb  mov     [rdi+38h], rbx
0x180005bff  add     rbx, r14
0x180005c02  jmp     short loc_180005C08
0x180005c04  mov     [rdi+38h], r13
0x180005c08  sub     rsi, rbx
0x180005c0b  xor     edx, edx; Val
0x180005c0d  mov     r8, rsi; Size
0x180005c10  mov     rcx, rbx; void *
0x180005c13  call    memset_0
0x180005c18  add     rsp, 28h
0x180005c1c  pop     r15
0x180005c1e  pop     r14
0x180005c20  pop     r13
0x180005c22  pop     r12
0x180005c24  pop     rdi
0x180005c25  pop     rsi
0x180005c26  pop     rbp
0x180005c27  pop     rbx
0x180005c28  retn
```
