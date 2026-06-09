# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005bc4`
- end: `0x180005ddd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004620`

## callees

- `0x180002cb4`
- `0x180005678`
- `0x180005bc4`
- `0x180006fa4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cba`

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
0x180005bc4  push    rbx
0x180005bc6  push    rbp
0x180005bc7  push    rsi
0x180005bc8  push    rdi
0x180005bc9  push    r12
0x180005bcb  push    r13
0x180005bcd  push    r14
0x180005bcf  push    r15
0x180005bd1  sub     rsp, 28h
0x180005bd5  mov     [rcx+4], r8d
0x180005bd9  xor     r13d, r13d
0x180005bdc  mov     eax, [rdx+8]
0x180005bdf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005be3  mov     [rcx+8], eax
0x180005be6  mov     rdi, rcx
0x180005be9  mov     [rcx+10h], r13
0x180005bed  mov     r12, rdx
0x180005bf0  movzx   eax, word ptr [rdx+40h]
0x180005bf4  mov     [rcx+18h], ax
0x180005bf8  mov     al, [rdx]
0x180005bfa  mov     [rcx+1Ah], al
0x180005bfd  mov     [rcx+20h], r13
0x180005c01  mov     rax, [rdx+88h]
0x180005c08  mov     [rcx+28h], rax
0x180005c0c  mov     rax, [rdx+90h]
0x180005c13  mov     [rcx+30h], rax
0x180005c17  mov     [rcx+38h], r13
0x180005c1b  mov     rcx, [rdx+38h]
0x180005c1f  lea     edx, [rbp+2]
0x180005c22  test    rcx, rcx
0x180005c25  jnz     short loc_180005C2C
0x180005c27  mov     r8d, edx
0x180005c2a  jmp     short loc_180005C3C
0x180005c2c  mov     rax, rbp
0x180005c2f  inc     rax
0x180005c32  cmp     [rcx+rax], r13b
0x180005c36  jnz     short loc_180005C2F
0x180005c38  lea     r8, [rax+1]; unsigned __int64
0x180005c3c  mov     rcx, [r12+80h]
0x180005c44  test    rcx, rcx
0x180005c47  jz      short loc_180005C59
0x180005c49  mov     rax, rbp
0x180005c4c  inc     rax
0x180005c4f  cmp     [rcx+rax], r13b
0x180005c53  jnz     short loc_180005C4C
0x180005c55  lea     rdx, [rax+1]
0x180005c59  mov     rcx, [r12+18h]
0x180005c5e  test    rcx, rcx
0x180005c61  jnz     short loc_180005C68
0x180005c63  lea     eax, [rcx+2]
0x180005c66  jmp     short loc_180005C7D
0x180005c68  mov     rax, rbp
0x180005c6b  inc     rax
0x180005c6e  cmp     [rcx+rax*2], r13w
0x180005c73  jnz     short loc_180005C6B
0x180005c75  lea     rax, ds:2[rax*2]
0x180005c7d  lea     r14, [rdx+rax]
0x180005c81  add     r14, r8
0x180005c84  lea     rsi, [rdi+48h]
0x180005c88  cmp     [rdi+40h], r13
0x180005c8c  jz      short loc_180005C93
0x180005c8e  cmp     [rsi], r14
0x180005c91  jnb     short loc_180005CC7
0x180005c93  mov     rdx, r14; dwBytes
0x180005c96  mov     ecx, 8; dwFlags
0x180005c9b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005ca0  mov     r15, rax
0x180005ca3  test    rax, rax
0x180005ca6  jz      short loc_180005CC7
0x180005ca8  mov     rbx, [rdi+40h]
0x180005cac  call    cs:__imp_GetProcessHeap
0x180005cb2  mov     r8, rbx; lpMem
0x180005cb5  xor     edx, edx; dwFlags
0x180005cb7  mov     rcx, rax; hHeap
0x180005cba  call    cs:__imp_HeapFree
0x180005cc0  mov     [rdi+40h], r15
0x180005cc4  mov     [rsi], r14
0x180005cc7  mov     rbx, [rdi+40h]
0x180005ccb  test    rbx, rbx
0x180005cce  jz      loc_180005DCC
0x180005cd4  mov     rdx, [rsi]; DestinationSize
0x180005cd7  lea     rsi, [rdx+rbx]
0x180005cdb  cmp     rbx, rsi
0x180005cde  jz      short loc_180005D1E
0x180005ce0  mov     r8, [r12+38h]; Source
0x180005ce5  test    r8, r8
0x180005ce8  jz      short loc_180005D1E
0x180005cea  cmp     [r8], r13b
0x180005ced  jz      short loc_180005D1E
0x180005cef  mov     rax, rbp
0x180005cf2  inc     rax
0x180005cf5  cmp     [r8+rax], r13b
0x180005cf9  jnz     short loc_180005CF2
0x180005cfb  lea     r14, [rax+1]
0x180005cff  cmp     rdx, r14
0x180005d02  jnb     short loc_180005D0A
0x180005d04  mov     [rdi+10h], r13
0x180005d08  jmp     short loc_180005D27
0x180005d0a  mov     r9, r14; SourceSize
0x180005d0d  mov     rcx, rbx; Destination
0x180005d10  call    memcpy_s
0x180005d15  mov     [rdi+10h], rbx
0x180005d19  add     rbx, r14
0x180005d1c  jmp     short loc_180005D22
0x180005d1e  mov     [rdi+10h], r13
0x180005d22  cmp     rbx, rsi
0x180005d25  jz      short loc_180005D6E
0x180005d27  mov     r8, [r12+80h]; Source
0x180005d2f  test    r8, r8
0x180005d32  jz      short loc_180005D6E
0x180005d34  cmp     [r8], r13b
0x180005d37  jz      short loc_180005D6E
0x180005d39  mov     rax, rbp
0x180005d3c  inc     rax
0x180005d3f  cmp     [r8+rax], r13b
0x180005d43  jnz     short loc_180005D3C
0x180005d45  mov     rdx, rsi
0x180005d48  lea     r14, [rax+1]
0x180005d4c  sub     rdx, rbx; DestinationSize
0x180005d4f  cmp     rdx, r14
0x180005d52  jnb     short loc_180005D5A
0x180005d54  mov     [rdi+20h], r13
0x180005d58  jmp     short loc_180005D77
0x180005d5a  mov     r9, r14; SourceSize
0x180005d5d  mov     rcx, rbx; Destination
0x180005d60  call    memcpy_s
0x180005d65  mov     [rdi+20h], rbx
0x180005d69  add     rbx, r14
0x180005d6c  jmp     short loc_180005D72
0x180005d6e  mov     [rdi+20h], r13
0x180005d72  cmp     rbx, rsi
0x180005d75  jz      short loc_180005DB8
0x180005d77  mov     r8, [r12+18h]; Source
0x180005d7c  test    r8, r8
0x180005d7f  jz      short loc_180005DB8
0x180005d81  cmp     [r8], r13w
0x180005d85  jz      short loc_180005DB8
0x180005d87  inc     rbp
0x180005d8a  cmp     [r8+rbp*2], r13w
0x180005d8f  jnz     short loc_180005D87
0x180005d91  mov     rdx, rsi
0x180005d94  lea     r14, ds:2[rbp*2]
0x180005d9c  sub     rdx, rbx; DestinationSize
0x180005d9f  cmp     rdx, r14
0x180005da2  jb      short loc_180005DB8
0x180005da4  mov     r9, r14; SourceSize
0x180005da7  mov     rcx, rbx; Destination
0x180005daa  call    memcpy_s
0x180005daf  mov     [rdi+38h], rbx
0x180005db3  add     rbx, r14
0x180005db6  jmp     short loc_180005DBC
0x180005db8  mov     [rdi+38h], r13
0x180005dbc  sub     rsi, rbx
0x180005dbf  xor     edx, edx; Val
0x180005dc1  mov     r8, rsi; Size
0x180005dc4  mov     rcx, rbx; void *
0x180005dc7  call    memset_0
0x180005dcc  add     rsp, 28h
0x180005dd0  pop     r15
0x180005dd2  pop     r14
0x180005dd4  pop     r13
0x180005dd6  pop     r12
0x180005dd8  pop     rdi
0x180005dd9  pop     rsi
0x180005dda  pop     rbp
0x180005ddb  pop     rbx
0x180005ddc  retn
```
