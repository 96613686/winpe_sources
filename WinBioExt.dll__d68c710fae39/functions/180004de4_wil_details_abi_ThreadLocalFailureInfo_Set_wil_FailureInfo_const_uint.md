# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004de4`
- end: `0x180004ffd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800038b0`

## callees

- `0x180002084`
- `0x1800048f8`
- `0x180004de4`
- `0x180005d78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ecc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ecc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eda`

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
0x180004de4  push    rbx
0x180004de6  push    rbp
0x180004de7  push    rsi
0x180004de8  push    rdi
0x180004de9  push    r12
0x180004deb  push    r13
0x180004ded  push    r14
0x180004def  push    r15
0x180004df1  sub     rsp, 28h
0x180004df5  mov     [rcx+4], r8d
0x180004df9  xor     r13d, r13d
0x180004dfc  mov     eax, [rdx+8]
0x180004dff  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004e03  mov     [rcx+8], eax
0x180004e06  mov     rdi, rcx
0x180004e09  mov     [rcx+10h], r13
0x180004e0d  mov     r12, rdx
0x180004e10  movzx   eax, word ptr [rdx+40h]
0x180004e14  mov     [rcx+18h], ax
0x180004e18  mov     al, [rdx]
0x180004e1a  mov     [rcx+1Ah], al
0x180004e1d  mov     [rcx+20h], r13
0x180004e21  mov     rax, [rdx+88h]
0x180004e28  mov     [rcx+28h], rax
0x180004e2c  mov     rax, [rdx+90h]
0x180004e33  mov     [rcx+30h], rax
0x180004e37  mov     [rcx+38h], r13
0x180004e3b  mov     rcx, [rdx+38h]
0x180004e3f  lea     edx, [rbp+2]
0x180004e42  test    rcx, rcx
0x180004e45  jnz     short loc_180004E4C
0x180004e47  mov     r8d, edx
0x180004e4a  jmp     short loc_180004E5C
0x180004e4c  mov     rax, rbp
0x180004e4f  inc     rax
0x180004e52  cmp     [rcx+rax], r13b
0x180004e56  jnz     short loc_180004E4F
0x180004e58  lea     r8, [rax+1]; unsigned __int64
0x180004e5c  mov     rcx, [r12+80h]
0x180004e64  test    rcx, rcx
0x180004e67  jz      short loc_180004E79
0x180004e69  mov     rax, rbp
0x180004e6c  inc     rax
0x180004e6f  cmp     [rcx+rax], r13b
0x180004e73  jnz     short loc_180004E6C
0x180004e75  lea     rdx, [rax+1]
0x180004e79  mov     rcx, [r12+18h]
0x180004e7e  test    rcx, rcx
0x180004e81  jnz     short loc_180004E88
0x180004e83  lea     eax, [rcx+2]
0x180004e86  jmp     short loc_180004E9D
0x180004e88  mov     rax, rbp
0x180004e8b  inc     rax
0x180004e8e  cmp     [rcx+rax*2], r13w
0x180004e93  jnz     short loc_180004E8B
0x180004e95  lea     rax, ds:2[rax*2]
0x180004e9d  lea     r14, [rdx+rax]
0x180004ea1  add     r14, r8
0x180004ea4  lea     rsi, [rdi+48h]
0x180004ea8  cmp     [rdi+40h], r13
0x180004eac  jz      short loc_180004EB3
0x180004eae  cmp     [rsi], r14
0x180004eb1  jnb     short loc_180004EE7
0x180004eb3  mov     rdx, r14; dwBytes
0x180004eb6  mov     ecx, 8; dwFlags
0x180004ebb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ec0  mov     r15, rax
0x180004ec3  test    rax, rax
0x180004ec6  jz      short loc_180004EE7
0x180004ec8  mov     rbx, [rdi+40h]
0x180004ecc  call    cs:__imp_GetProcessHeap
0x180004ed2  mov     r8, rbx; lpMem
0x180004ed5  xor     edx, edx; dwFlags
0x180004ed7  mov     rcx, rax; hHeap
0x180004eda  call    cs:__imp_HeapFree
0x180004ee0  mov     [rdi+40h], r15
0x180004ee4  mov     [rsi], r14
0x180004ee7  mov     rbx, [rdi+40h]
0x180004eeb  test    rbx, rbx
0x180004eee  jz      loc_180004FEC
0x180004ef4  mov     rdx, [rsi]; DestinationSize
0x180004ef7  lea     rsi, [rdx+rbx]
0x180004efb  cmp     rbx, rsi
0x180004efe  jz      short loc_180004F3E
0x180004f00  mov     r8, [r12+38h]; Source
0x180004f05  test    r8, r8
0x180004f08  jz      short loc_180004F3E
0x180004f0a  cmp     [r8], r13b
0x180004f0d  jz      short loc_180004F3E
0x180004f0f  mov     rax, rbp
0x180004f12  inc     rax
0x180004f15  cmp     [r8+rax], r13b
0x180004f19  jnz     short loc_180004F12
0x180004f1b  lea     r14, [rax+1]
0x180004f1f  cmp     rdx, r14
0x180004f22  jnb     short loc_180004F2A
0x180004f24  mov     [rdi+10h], r13
0x180004f28  jmp     short loc_180004F47
0x180004f2a  mov     r9, r14; SourceSize
0x180004f2d  mov     rcx, rbx; Destination
0x180004f30  call    memcpy_s
0x180004f35  mov     [rdi+10h], rbx
0x180004f39  add     rbx, r14
0x180004f3c  jmp     short loc_180004F42
0x180004f3e  mov     [rdi+10h], r13
0x180004f42  cmp     rbx, rsi
0x180004f45  jz      short loc_180004F8E
0x180004f47  mov     r8, [r12+80h]; Source
0x180004f4f  test    r8, r8
0x180004f52  jz      short loc_180004F8E
0x180004f54  cmp     [r8], r13b
0x180004f57  jz      short loc_180004F8E
0x180004f59  mov     rax, rbp
0x180004f5c  inc     rax
0x180004f5f  cmp     [r8+rax], r13b
0x180004f63  jnz     short loc_180004F5C
0x180004f65  mov     rdx, rsi
0x180004f68  lea     r14, [rax+1]
0x180004f6c  sub     rdx, rbx; DestinationSize
0x180004f6f  cmp     rdx, r14
0x180004f72  jnb     short loc_180004F7A
0x180004f74  mov     [rdi+20h], r13
0x180004f78  jmp     short loc_180004F97
0x180004f7a  mov     r9, r14; SourceSize
0x180004f7d  mov     rcx, rbx; Destination
0x180004f80  call    memcpy_s
0x180004f85  mov     [rdi+20h], rbx
0x180004f89  add     rbx, r14
0x180004f8c  jmp     short loc_180004F92
0x180004f8e  mov     [rdi+20h], r13
0x180004f92  cmp     rbx, rsi
0x180004f95  jz      short loc_180004FD8
0x180004f97  mov     r8, [r12+18h]; Source
0x180004f9c  test    r8, r8
0x180004f9f  jz      short loc_180004FD8
0x180004fa1  cmp     [r8], r13w
0x180004fa5  jz      short loc_180004FD8
0x180004fa7  inc     rbp
0x180004faa  cmp     [r8+rbp*2], r13w
0x180004faf  jnz     short loc_180004FA7
0x180004fb1  mov     rdx, rsi
0x180004fb4  lea     r14, ds:2[rbp*2]
0x180004fbc  sub     rdx, rbx; DestinationSize
0x180004fbf  cmp     rdx, r14
0x180004fc2  jb      short loc_180004FD8
0x180004fc4  mov     r9, r14; SourceSize
0x180004fc7  mov     rcx, rbx; Destination
0x180004fca  call    memcpy_s
0x180004fcf  mov     [rdi+38h], rbx
0x180004fd3  add     rbx, r14
0x180004fd6  jmp     short loc_180004FDC
0x180004fd8  mov     [rdi+38h], r13
0x180004fdc  sub     rsi, rbx
0x180004fdf  xor     edx, edx; Val
0x180004fe1  mov     r8, rsi; Size
0x180004fe4  mov     rcx, rbx; void *
0x180004fe7  call    memset_0
0x180004fec  add     rsp, 28h
0x180004ff0  pop     r15
0x180004ff2  pop     r14
0x180004ff4  pop     r13
0x180004ff6  pop     r12
0x180004ff8  pop     rdi
0x180004ff9  pop     rsi
0x180004ffa  pop     rbp
0x180004ffb  pop     rbx
0x180004ffc  retn
```
