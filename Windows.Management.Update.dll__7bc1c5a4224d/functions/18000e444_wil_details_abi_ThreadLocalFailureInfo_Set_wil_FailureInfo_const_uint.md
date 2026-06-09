# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000e444`
- end: `0x18000e65d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b720`

## callees

- `0x1800033e8`
- `0x18000cac0`
- `0x18000e444`
- `0x180010108`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e52c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e52c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e53a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e53a`

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
0x18000e444  push    rbx
0x18000e446  push    rbp
0x18000e447  push    rsi
0x18000e448  push    rdi
0x18000e449  push    r12
0x18000e44b  push    r13
0x18000e44d  push    r14
0x18000e44f  push    r15
0x18000e451  sub     rsp, 28h
0x18000e455  mov     [rcx+4], r8d
0x18000e459  xor     r13d, r13d
0x18000e45c  mov     eax, [rdx+8]
0x18000e45f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000e463  mov     [rcx+8], eax
0x18000e466  mov     rdi, rcx
0x18000e469  mov     [rcx+10h], r13
0x18000e46d  mov     r12, rdx
0x18000e470  movzx   eax, word ptr [rdx+40h]
0x18000e474  mov     [rcx+18h], ax
0x18000e478  mov     al, [rdx]
0x18000e47a  mov     [rcx+1Ah], al
0x18000e47d  mov     [rcx+20h], r13
0x18000e481  mov     rax, [rdx+88h]
0x18000e488  mov     [rcx+28h], rax
0x18000e48c  mov     rax, [rdx+90h]
0x18000e493  mov     [rcx+30h], rax
0x18000e497  mov     [rcx+38h], r13
0x18000e49b  mov     rcx, [rdx+38h]
0x18000e49f  lea     edx, [rbp+2]
0x18000e4a2  test    rcx, rcx
0x18000e4a5  jnz     short loc_18000E4AC
0x18000e4a7  mov     r8d, edx
0x18000e4aa  jmp     short loc_18000E4BC
0x18000e4ac  mov     rax, rbp
0x18000e4af  inc     rax
0x18000e4b2  cmp     [rcx+rax], r13b
0x18000e4b6  jnz     short loc_18000E4AF
0x18000e4b8  lea     r8, [rax+1]; unsigned __int64
0x18000e4bc  mov     rcx, [r12+80h]
0x18000e4c4  test    rcx, rcx
0x18000e4c7  jz      short loc_18000E4D9
0x18000e4c9  mov     rax, rbp
0x18000e4cc  inc     rax
0x18000e4cf  cmp     [rcx+rax], r13b
0x18000e4d3  jnz     short loc_18000E4CC
0x18000e4d5  lea     rdx, [rax+1]
0x18000e4d9  mov     rcx, [r12+18h]
0x18000e4de  test    rcx, rcx
0x18000e4e1  jnz     short loc_18000E4E8
0x18000e4e3  lea     eax, [rcx+2]
0x18000e4e6  jmp     short loc_18000E4FD
0x18000e4e8  mov     rax, rbp
0x18000e4eb  inc     rax
0x18000e4ee  cmp     [rcx+rax*2], r13w
0x18000e4f3  jnz     short loc_18000E4EB
0x18000e4f5  lea     rax, ds:2[rax*2]
0x18000e4fd  lea     r14, [rdx+rax]
0x18000e501  add     r14, r8
0x18000e504  lea     rsi, [rdi+48h]
0x18000e508  cmp     [rdi+40h], r13
0x18000e50c  jz      short loc_18000E513
0x18000e50e  cmp     [rsi], r14
0x18000e511  jnb     short loc_18000E547
0x18000e513  mov     rdx, r14; dwBytes
0x18000e516  mov     ecx, 8; dwFlags
0x18000e51b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e520  mov     r15, rax
0x18000e523  test    rax, rax
0x18000e526  jz      short loc_18000E547
0x18000e528  mov     rbx, [rdi+40h]
0x18000e52c  call    cs:__imp_GetProcessHeap
0x18000e532  mov     r8, rbx; lpMem
0x18000e535  xor     edx, edx; dwFlags
0x18000e537  mov     rcx, rax; hHeap
0x18000e53a  call    cs:__imp_HeapFree
0x18000e540  mov     [rdi+40h], r15
0x18000e544  mov     [rsi], r14
0x18000e547  mov     rbx, [rdi+40h]
0x18000e54b  test    rbx, rbx
0x18000e54e  jz      loc_18000E64C
0x18000e554  mov     rdx, [rsi]; DestinationSize
0x18000e557  lea     rsi, [rdx+rbx]
0x18000e55b  cmp     rbx, rsi
0x18000e55e  jz      short loc_18000E59E
0x18000e560  mov     r8, [r12+38h]; Source
0x18000e565  test    r8, r8
0x18000e568  jz      short loc_18000E59E
0x18000e56a  cmp     [r8], r13b
0x18000e56d  jz      short loc_18000E59E
0x18000e56f  mov     rax, rbp
0x18000e572  inc     rax
0x18000e575  cmp     [r8+rax], r13b
0x18000e579  jnz     short loc_18000E572
0x18000e57b  lea     r14, [rax+1]
0x18000e57f  cmp     rdx, r14
0x18000e582  jnb     short loc_18000E58A
0x18000e584  mov     [rdi+10h], r13
0x18000e588  jmp     short loc_18000E5A7
0x18000e58a  mov     r9, r14; SourceSize
0x18000e58d  mov     rcx, rbx; Destination
0x18000e590  call    memcpy_s
0x18000e595  mov     [rdi+10h], rbx
0x18000e599  add     rbx, r14
0x18000e59c  jmp     short loc_18000E5A2
0x18000e59e  mov     [rdi+10h], r13
0x18000e5a2  cmp     rbx, rsi
0x18000e5a5  jz      short loc_18000E5EE
0x18000e5a7  mov     r8, [r12+80h]; Source
0x18000e5af  test    r8, r8
0x18000e5b2  jz      short loc_18000E5EE
0x18000e5b4  cmp     [r8], r13b
0x18000e5b7  jz      short loc_18000E5EE
0x18000e5b9  mov     rax, rbp
0x18000e5bc  inc     rax
0x18000e5bf  cmp     [r8+rax], r13b
0x18000e5c3  jnz     short loc_18000E5BC
0x18000e5c5  mov     rdx, rsi
0x18000e5c8  lea     r14, [rax+1]
0x18000e5cc  sub     rdx, rbx; DestinationSize
0x18000e5cf  cmp     rdx, r14
0x18000e5d2  jnb     short loc_18000E5DA
0x18000e5d4  mov     [rdi+20h], r13
0x18000e5d8  jmp     short loc_18000E5F7
0x18000e5da  mov     r9, r14; SourceSize
0x18000e5dd  mov     rcx, rbx; Destination
0x18000e5e0  call    memcpy_s
0x18000e5e5  mov     [rdi+20h], rbx
0x18000e5e9  add     rbx, r14
0x18000e5ec  jmp     short loc_18000E5F2
0x18000e5ee  mov     [rdi+20h], r13
0x18000e5f2  cmp     rbx, rsi
0x18000e5f5  jz      short loc_18000E638
0x18000e5f7  mov     r8, [r12+18h]; Source
0x18000e5fc  test    r8, r8
0x18000e5ff  jz      short loc_18000E638
0x18000e601  cmp     [r8], r13w
0x18000e605  jz      short loc_18000E638
0x18000e607  inc     rbp
0x18000e60a  cmp     [r8+rbp*2], r13w
0x18000e60f  jnz     short loc_18000E607
0x18000e611  mov     rdx, rsi
0x18000e614  lea     r14, ds:2[rbp*2]
0x18000e61c  sub     rdx, rbx; DestinationSize
0x18000e61f  cmp     rdx, r14
0x18000e622  jb      short loc_18000E638
0x18000e624  mov     r9, r14; SourceSize
0x18000e627  mov     rcx, rbx; Destination
0x18000e62a  call    memcpy_s
0x18000e62f  mov     [rdi+38h], rbx
0x18000e633  add     rbx, r14
0x18000e636  jmp     short loc_18000E63C
0x18000e638  mov     [rdi+38h], r13
0x18000e63c  sub     rsi, rbx
0x18000e63f  xor     edx, edx; Val
0x18000e641  mov     r8, rsi; Size
0x18000e644  mov     rcx, rbx; void *
0x18000e647  call    memset_0
0x18000e64c  add     rsp, 28h
0x18000e650  pop     r15
0x18000e652  pop     r14
0x18000e654  pop     r13
0x18000e656  pop     r12
0x18000e658  pop     rdi
0x18000e659  pop     rsi
0x18000e65a  pop     rbp
0x18000e65b  pop     rbx
0x18000e65c  retn
```
