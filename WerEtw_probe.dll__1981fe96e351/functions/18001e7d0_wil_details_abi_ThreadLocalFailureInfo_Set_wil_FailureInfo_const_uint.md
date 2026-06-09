# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001e7d0`
- end: `0x18001e9e9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ca30`

## callees

- `0x180002420`
- `0x18001e448`
- `0x18001e7d0`
- `0x180020210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e8c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e8c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8b8`

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
0x18001e7d0  push    rbx
0x18001e7d2  push    rbp
0x18001e7d3  push    rsi
0x18001e7d4  push    rdi
0x18001e7d5  push    r12
0x18001e7d7  push    r13
0x18001e7d9  push    r14
0x18001e7db  push    r15
0x18001e7dd  sub     rsp, 28h
0x18001e7e1  mov     [rcx+4], r8d
0x18001e7e5  xor     r13d, r13d
0x18001e7e8  mov     eax, [rdx+8]
0x18001e7eb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001e7ef  mov     [rcx+8], eax
0x18001e7f2  mov     rdi, rcx
0x18001e7f5  mov     [rcx+10h], r13
0x18001e7f9  mov     r12, rdx
0x18001e7fc  movzx   eax, word ptr [rdx+40h]
0x18001e800  mov     [rcx+18h], ax
0x18001e804  mov     al, [rdx]
0x18001e806  mov     [rcx+1Ah], al
0x18001e809  mov     [rcx+20h], r13
0x18001e80d  mov     rax, [rdx+88h]
0x18001e814  mov     [rcx+28h], rax
0x18001e818  mov     rax, [rdx+90h]
0x18001e81f  mov     [rcx+30h], rax
0x18001e823  mov     [rcx+38h], r13
0x18001e827  mov     rcx, [rdx+38h]
0x18001e82b  lea     edx, [rbp+2]
0x18001e82e  test    rcx, rcx
0x18001e831  jnz     short loc_18001E838
0x18001e833  mov     r8d, edx
0x18001e836  jmp     short loc_18001E848
0x18001e838  mov     rax, rbp
0x18001e83b  inc     rax
0x18001e83e  cmp     [rcx+rax], r13b
0x18001e842  jnz     short loc_18001E83B
0x18001e844  lea     r8, [rax+1]; unsigned __int64
0x18001e848  mov     rcx, [r12+80h]
0x18001e850  test    rcx, rcx
0x18001e853  jz      short loc_18001E865
0x18001e855  mov     rax, rbp
0x18001e858  inc     rax
0x18001e85b  cmp     [rcx+rax], r13b
0x18001e85f  jnz     short loc_18001E858
0x18001e861  lea     rdx, [rax+1]
0x18001e865  mov     rcx, [r12+18h]
0x18001e86a  test    rcx, rcx
0x18001e86d  jnz     short loc_18001E874
0x18001e86f  lea     eax, [rcx+2]
0x18001e872  jmp     short loc_18001E889
0x18001e874  mov     rax, rbp
0x18001e877  inc     rax
0x18001e87a  cmp     [rcx+rax*2], r13w
0x18001e87f  jnz     short loc_18001E877
0x18001e881  lea     rax, ds:2[rax*2]
0x18001e889  lea     r14, [rdx+rax]
0x18001e88d  add     r14, r8
0x18001e890  lea     rsi, [rdi+48h]
0x18001e894  cmp     [rdi+40h], r13
0x18001e898  jz      short loc_18001E89F
0x18001e89a  cmp     [rsi], r14
0x18001e89d  jnb     short loc_18001E8D3
0x18001e89f  mov     rdx, r14; dwBytes
0x18001e8a2  mov     ecx, 8; dwFlags
0x18001e8a7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001e8ac  mov     r15, rax
0x18001e8af  test    rax, rax
0x18001e8b2  jz      short loc_18001E8D3
0x18001e8b4  mov     rbx, [rdi+40h]
0x18001e8b8  call    cs:__imp_GetProcessHeap
0x18001e8be  mov     r8, rbx; lpMem
0x18001e8c1  xor     edx, edx; dwFlags
0x18001e8c3  mov     rcx, rax; hHeap
0x18001e8c6  call    cs:__imp_HeapFree
0x18001e8cc  mov     [rdi+40h], r15
0x18001e8d0  mov     [rsi], r14
0x18001e8d3  mov     rbx, [rdi+40h]
0x18001e8d7  test    rbx, rbx
0x18001e8da  jz      loc_18001E9D8
0x18001e8e0  mov     rdx, [rsi]; DestinationSize
0x18001e8e3  lea     rsi, [rdx+rbx]
0x18001e8e7  cmp     rbx, rsi
0x18001e8ea  jz      short loc_18001E92A
0x18001e8ec  mov     r8, [r12+38h]; Source
0x18001e8f1  test    r8, r8
0x18001e8f4  jz      short loc_18001E92A
0x18001e8f6  cmp     [r8], r13b
0x18001e8f9  jz      short loc_18001E92A
0x18001e8fb  mov     rax, rbp
0x18001e8fe  inc     rax
0x18001e901  cmp     [r8+rax], r13b
0x18001e905  jnz     short loc_18001E8FE
0x18001e907  lea     r14, [rax+1]
0x18001e90b  cmp     rdx, r14
0x18001e90e  jnb     short loc_18001E916
0x18001e910  mov     [rdi+10h], r13
0x18001e914  jmp     short loc_18001E933
0x18001e916  mov     r9, r14; SourceSize
0x18001e919  mov     rcx, rbx; Destination
0x18001e91c  call    memcpy_s
0x18001e921  mov     [rdi+10h], rbx
0x18001e925  add     rbx, r14
0x18001e928  jmp     short loc_18001E92E
0x18001e92a  mov     [rdi+10h], r13
0x18001e92e  cmp     rbx, rsi
0x18001e931  jz      short loc_18001E97A
0x18001e933  mov     r8, [r12+80h]; Source
0x18001e93b  test    r8, r8
0x18001e93e  jz      short loc_18001E97A
0x18001e940  cmp     [r8], r13b
0x18001e943  jz      short loc_18001E97A
0x18001e945  mov     rax, rbp
0x18001e948  inc     rax
0x18001e94b  cmp     [r8+rax], r13b
0x18001e94f  jnz     short loc_18001E948
0x18001e951  mov     rdx, rsi
0x18001e954  lea     r14, [rax+1]
0x18001e958  sub     rdx, rbx; DestinationSize
0x18001e95b  cmp     rdx, r14
0x18001e95e  jnb     short loc_18001E966
0x18001e960  mov     [rdi+20h], r13
0x18001e964  jmp     short loc_18001E983
0x18001e966  mov     r9, r14; SourceSize
0x18001e969  mov     rcx, rbx; Destination
0x18001e96c  call    memcpy_s
0x18001e971  mov     [rdi+20h], rbx
0x18001e975  add     rbx, r14
0x18001e978  jmp     short loc_18001E97E
0x18001e97a  mov     [rdi+20h], r13
0x18001e97e  cmp     rbx, rsi
0x18001e981  jz      short loc_18001E9C4
0x18001e983  mov     r8, [r12+18h]; Source
0x18001e988  test    r8, r8
0x18001e98b  jz      short loc_18001E9C4
0x18001e98d  cmp     [r8], r13w
0x18001e991  jz      short loc_18001E9C4
0x18001e993  inc     rbp
0x18001e996  cmp     [r8+rbp*2], r13w
0x18001e99b  jnz     short loc_18001E993
0x18001e99d  mov     rdx, rsi
0x18001e9a0  lea     r14, ds:2[rbp*2]
0x18001e9a8  sub     rdx, rbx; DestinationSize
0x18001e9ab  cmp     rdx, r14
0x18001e9ae  jb      short loc_18001E9C4
0x18001e9b0  mov     r9, r14; SourceSize
0x18001e9b3  mov     rcx, rbx; Destination
0x18001e9b6  call    memcpy_s
0x18001e9bb  mov     [rdi+38h], rbx
0x18001e9bf  add     rbx, r14
0x18001e9c2  jmp     short loc_18001E9C8
0x18001e9c4  mov     [rdi+38h], r13
0x18001e9c8  sub     rsi, rbx
0x18001e9cb  xor     edx, edx; Val
0x18001e9cd  mov     r8, rsi; Size
0x18001e9d0  mov     rcx, rbx; void *
0x18001e9d3  call    memset_0
0x18001e9d8  add     rsp, 28h
0x18001e9dc  pop     r15
0x18001e9de  pop     r14
0x18001e9e0  pop     r13
0x18001e9e2  pop     r12
0x18001e9e4  pop     rdi
0x18001e9e5  pop     rsi
0x18001e9e6  pop     rbp
0x18001e9e7  pop     rbx
0x18001e9e8  retn
```
