# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001d044`
- end: `0x18001d25d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cb70`

## callees

- `0x180002928`
- `0x180014c4c`
- `0x1800185ac`
- `0x18001d044`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d12c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d12c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d13a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d13a`

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
0x18001d044  push    rbx
0x18001d046  push    rbp
0x18001d047  push    rsi
0x18001d048  push    rdi
0x18001d049  push    r12
0x18001d04b  push    r13
0x18001d04d  push    r14
0x18001d04f  push    r15
0x18001d051  sub     rsp, 28h
0x18001d055  mov     [rcx+4], r8d
0x18001d059  xor     r13d, r13d
0x18001d05c  mov     eax, [rdx+8]
0x18001d05f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001d063  mov     [rcx+8], eax
0x18001d066  mov     rdi, rcx
0x18001d069  mov     [rcx+10h], r13
0x18001d06d  mov     r12, rdx
0x18001d070  movzx   eax, word ptr [rdx+40h]
0x18001d074  mov     [rcx+18h], ax
0x18001d078  mov     al, [rdx]
0x18001d07a  mov     [rcx+1Ah], al
0x18001d07d  mov     [rcx+20h], r13
0x18001d081  mov     rax, [rdx+88h]
0x18001d088  mov     [rcx+28h], rax
0x18001d08c  mov     rax, [rdx+90h]
0x18001d093  mov     [rcx+30h], rax
0x18001d097  mov     [rcx+38h], r13
0x18001d09b  mov     rcx, [rdx+38h]
0x18001d09f  lea     edx, [rbp+2]
0x18001d0a2  test    rcx, rcx
0x18001d0a5  jnz     short loc_18001D0AC
0x18001d0a7  mov     r8d, edx
0x18001d0aa  jmp     short loc_18001D0BC
0x18001d0ac  mov     rax, rbp
0x18001d0af  inc     rax
0x18001d0b2  cmp     [rcx+rax], r13b
0x18001d0b6  jnz     short loc_18001D0AF
0x18001d0b8  lea     r8, [rax+1]; unsigned __int64
0x18001d0bc  mov     rcx, [r12+80h]
0x18001d0c4  test    rcx, rcx
0x18001d0c7  jz      short loc_18001D0D9
0x18001d0c9  mov     rax, rbp
0x18001d0cc  inc     rax
0x18001d0cf  cmp     [rcx+rax], r13b
0x18001d0d3  jnz     short loc_18001D0CC
0x18001d0d5  lea     rdx, [rax+1]
0x18001d0d9  mov     rcx, [r12+18h]
0x18001d0de  test    rcx, rcx
0x18001d0e1  jnz     short loc_18001D0E8
0x18001d0e3  lea     eax, [rcx+2]
0x18001d0e6  jmp     short loc_18001D0FD
0x18001d0e8  mov     rax, rbp
0x18001d0eb  inc     rax
0x18001d0ee  cmp     [rcx+rax*2], r13w
0x18001d0f3  jnz     short loc_18001D0EB
0x18001d0f5  lea     rax, ds:2[rax*2]
0x18001d0fd  lea     r14, [rdx+rax]
0x18001d101  add     r14, r8
0x18001d104  lea     rsi, [rdi+48h]
0x18001d108  cmp     [rdi+40h], r13
0x18001d10c  jz      short loc_18001D113
0x18001d10e  cmp     [rsi], r14
0x18001d111  jnb     short loc_18001D147
0x18001d113  mov     rdx, r14; dwBytes
0x18001d116  mov     ecx, 8; dwFlags
0x18001d11b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001d120  mov     r15, rax
0x18001d123  test    rax, rax
0x18001d126  jz      short loc_18001D147
0x18001d128  mov     rbx, [rdi+40h]
0x18001d12c  call    cs:__imp_GetProcessHeap
0x18001d132  mov     r8, rbx; lpMem
0x18001d135  xor     edx, edx; dwFlags
0x18001d137  mov     rcx, rax; hHeap
0x18001d13a  call    cs:__imp_HeapFree
0x18001d140  mov     [rdi+40h], r15
0x18001d144  mov     [rsi], r14
0x18001d147  mov     rbx, [rdi+40h]
0x18001d14b  test    rbx, rbx
0x18001d14e  jz      loc_18001D24C
0x18001d154  mov     rdx, [rsi]; DestinationSize
0x18001d157  lea     rsi, [rdx+rbx]
0x18001d15b  cmp     rbx, rsi
0x18001d15e  jz      short loc_18001D19E
0x18001d160  mov     r8, [r12+38h]; Source
0x18001d165  test    r8, r8
0x18001d168  jz      short loc_18001D19E
0x18001d16a  cmp     [r8], r13b
0x18001d16d  jz      short loc_18001D19E
0x18001d16f  mov     rax, rbp
0x18001d172  inc     rax
0x18001d175  cmp     [r8+rax], r13b
0x18001d179  jnz     short loc_18001D172
0x18001d17b  lea     r14, [rax+1]
0x18001d17f  cmp     rdx, r14
0x18001d182  jnb     short loc_18001D18A
0x18001d184  mov     [rdi+10h], r13
0x18001d188  jmp     short loc_18001D1A7
0x18001d18a  mov     r9, r14; SourceSize
0x18001d18d  mov     rcx, rbx; Destination
0x18001d190  call    memcpy_s
0x18001d195  mov     [rdi+10h], rbx
0x18001d199  add     rbx, r14
0x18001d19c  jmp     short loc_18001D1A2
0x18001d19e  mov     [rdi+10h], r13
0x18001d1a2  cmp     rbx, rsi
0x18001d1a5  jz      short loc_18001D1EE
0x18001d1a7  mov     r8, [r12+80h]; Source
0x18001d1af  test    r8, r8
0x18001d1b2  jz      short loc_18001D1EE
0x18001d1b4  cmp     [r8], r13b
0x18001d1b7  jz      short loc_18001D1EE
0x18001d1b9  mov     rax, rbp
0x18001d1bc  inc     rax
0x18001d1bf  cmp     [r8+rax], r13b
0x18001d1c3  jnz     short loc_18001D1BC
0x18001d1c5  mov     rdx, rsi
0x18001d1c8  lea     r14, [rax+1]
0x18001d1cc  sub     rdx, rbx; DestinationSize
0x18001d1cf  cmp     rdx, r14
0x18001d1d2  jnb     short loc_18001D1DA
0x18001d1d4  mov     [rdi+20h], r13
0x18001d1d8  jmp     short loc_18001D1F7
0x18001d1da  mov     r9, r14; SourceSize
0x18001d1dd  mov     rcx, rbx; Destination
0x18001d1e0  call    memcpy_s
0x18001d1e5  mov     [rdi+20h], rbx
0x18001d1e9  add     rbx, r14
0x18001d1ec  jmp     short loc_18001D1F2
0x18001d1ee  mov     [rdi+20h], r13
0x18001d1f2  cmp     rbx, rsi
0x18001d1f5  jz      short loc_18001D238
0x18001d1f7  mov     r8, [r12+18h]; Source
0x18001d1fc  test    r8, r8
0x18001d1ff  jz      short loc_18001D238
0x18001d201  cmp     [r8], r13w
0x18001d205  jz      short loc_18001D238
0x18001d207  inc     rbp
0x18001d20a  cmp     [r8+rbp*2], r13w
0x18001d20f  jnz     short loc_18001D207
0x18001d211  mov     rdx, rsi
0x18001d214  lea     r14, ds:2[rbp*2]
0x18001d21c  sub     rdx, rbx; DestinationSize
0x18001d21f  cmp     rdx, r14
0x18001d222  jb      short loc_18001D238
0x18001d224  mov     r9, r14; SourceSize
0x18001d227  mov     rcx, rbx; Destination
0x18001d22a  call    memcpy_s
0x18001d22f  mov     [rdi+38h], rbx
0x18001d233  add     rbx, r14
0x18001d236  jmp     short loc_18001D23C
0x18001d238  mov     [rdi+38h], r13
0x18001d23c  sub     rsi, rbx
0x18001d23f  xor     edx, edx; Val
0x18001d241  mov     r8, rsi; Size
0x18001d244  mov     rcx, rbx; void *
0x18001d247  call    memset_0
0x18001d24c  add     rsp, 28h
0x18001d250  pop     r15
0x18001d252  pop     r14
0x18001d254  pop     r13
0x18001d256  pop     r12
0x18001d258  pop     rdi
0x18001d259  pop     rsi
0x18001d25a  pop     rbp
0x18001d25b  pop     rbx
0x18001d25c  retn
```
