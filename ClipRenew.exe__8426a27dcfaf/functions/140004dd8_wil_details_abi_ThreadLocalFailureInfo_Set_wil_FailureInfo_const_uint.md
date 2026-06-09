# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140004dd8`
- end: `0x140004ff4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400038d0`

## callees

- `0x140004a94`
- `0x140004dd8`
- `0x14001346e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004f24`
- `msvcrt!memcpy_s` at `0x140004f75`
- `msvcrt!memcpy_s` at `0x140004fc0`
- `msvcrt!memcpy_s` at `0x140004f24`
- `msvcrt!memcpy_s` at `0x140004f75`
- `msvcrt!memcpy_s` at `0x140004fc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ec0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004ece`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004ece`

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
0x140004dd8  push    rbx
0x140004dda  push    rbp
0x140004ddb  push    rsi
0x140004ddc  push    rdi
0x140004ddd  push    r12
0x140004ddf  push    r13
0x140004de1  push    r14
0x140004de3  push    r15
0x140004de5  sub     rsp, 28h
0x140004de9  mov     [rcx+4], r8d
0x140004ded  xor     r13d, r13d
0x140004df0  mov     eax, [rdx+8]
0x140004df3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140004df7  mov     [rcx+8], eax
0x140004dfa  mov     rdi, rcx
0x140004dfd  mov     [rcx+10h], r13
0x140004e01  mov     r12, rdx
0x140004e04  movzx   eax, word ptr [rdx+40h]
0x140004e08  mov     [rcx+18h], ax
0x140004e0c  mov     al, [rdx]
0x140004e0e  mov     [rcx+1Ah], al
0x140004e11  mov     [rcx+20h], r13
0x140004e15  mov     rax, [rdx+88h]
0x140004e1c  mov     [rcx+28h], rax
0x140004e20  mov     rax, [rdx+90h]
0x140004e27  mov     [rcx+30h], rax
0x140004e2b  mov     [rcx+38h], r13
0x140004e2f  mov     rcx, [rdx+38h]
0x140004e33  lea     edx, [rbp+2]
0x140004e36  test    rcx, rcx
0x140004e39  jnz     short loc_140004E40
0x140004e3b  mov     r8d, edx
0x140004e3e  jmp     short loc_140004E50
0x140004e40  mov     rax, rbp
0x140004e43  inc     rax
0x140004e46  cmp     [rcx+rax], r13b
0x140004e4a  jnz     short loc_140004E43
0x140004e4c  lea     r8, [rax+1]; unsigned __int64
0x140004e50  mov     rcx, [r12+80h]
0x140004e58  test    rcx, rcx
0x140004e5b  jz      short loc_140004E6D
0x140004e5d  mov     rax, rbp
0x140004e60  inc     rax
0x140004e63  cmp     [rcx+rax], r13b
0x140004e67  jnz     short loc_140004E60
0x140004e69  lea     rdx, [rax+1]
0x140004e6d  mov     rcx, [r12+18h]
0x140004e72  test    rcx, rcx
0x140004e75  jnz     short loc_140004E7C
0x140004e77  lea     eax, [rcx+2]
0x140004e7a  jmp     short loc_140004E91
0x140004e7c  mov     rax, rbp
0x140004e7f  inc     rax
0x140004e82  cmp     [rcx+rax*2], r13w
0x140004e87  jnz     short loc_140004E7F
0x140004e89  lea     rax, ds:2[rax*2]
0x140004e91  lea     r14, [rdx+rax]
0x140004e95  add     r14, r8
0x140004e98  lea     rsi, [rdi+48h]
0x140004e9c  cmp     [rdi+40h], r13
0x140004ea0  jz      short loc_140004EA7
0x140004ea2  cmp     [rsi], r14
0x140004ea5  jnb     short loc_140004EDB
0x140004ea7  mov     rdx, r14; dwBytes
0x140004eaa  mov     ecx, 8; dwFlags
0x140004eaf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004eb4  mov     r15, rax
0x140004eb7  test    rax, rax
0x140004eba  jz      short loc_140004EDB
0x140004ebc  mov     rbx, [rdi+40h]
0x140004ec0  call    cs:__imp_GetProcessHeap
0x140004ec6  mov     r8, rbx; lpMem
0x140004ec9  xor     edx, edx; dwFlags
0x140004ecb  mov     rcx, rax; hHeap
0x140004ece  call    cs:__imp_HeapFree
0x140004ed4  mov     [rdi+40h], r15
0x140004ed8  mov     [rsi], r14
0x140004edb  mov     rbx, [rdi+40h]
0x140004edf  test    rbx, rbx
0x140004ee2  jz      loc_140004FE3
0x140004ee8  mov     rdx, [rsi]; DestinationSize
0x140004eeb  lea     rsi, [rdx+rbx]
0x140004eef  cmp     rbx, rsi
0x140004ef2  jz      short loc_140004F33
0x140004ef4  mov     r8, [r12+38h]; Source
0x140004ef9  test    r8, r8
0x140004efc  jz      short loc_140004F33
0x140004efe  cmp     [r8], r13b
0x140004f01  jz      short loc_140004F33
0x140004f03  mov     rax, rbp
0x140004f06  inc     rax
0x140004f09  cmp     [r8+rax], r13b
0x140004f0d  jnz     short loc_140004F06
0x140004f0f  lea     r14, [rax+1]
0x140004f13  cmp     rdx, r14
0x140004f16  jnb     short loc_140004F1E
0x140004f18  mov     [rdi+10h], r13
0x140004f1c  jmp     short loc_140004F3C
0x140004f1e  mov     r9, r14; SourceSize
0x140004f21  mov     rcx, rbx; Destination
0x140004f24  call    cs:__imp_memcpy_s
0x140004f2a  mov     [rdi+10h], rbx
0x140004f2e  add     rbx, r14
0x140004f31  jmp     short loc_140004F37
0x140004f33  mov     [rdi+10h], r13
0x140004f37  cmp     rbx, rsi
0x140004f3a  jz      short loc_140004F84
0x140004f3c  mov     r8, [r12+80h]; Source
0x140004f44  test    r8, r8
0x140004f47  jz      short loc_140004F84
0x140004f49  cmp     [r8], r13b
0x140004f4c  jz      short loc_140004F84
0x140004f4e  mov     rax, rbp
0x140004f51  inc     rax
0x140004f54  cmp     [r8+rax], r13b
0x140004f58  jnz     short loc_140004F51
0x140004f5a  mov     rdx, rsi
0x140004f5d  lea     r14, [rax+1]
0x140004f61  sub     rdx, rbx; DestinationSize
0x140004f64  cmp     rdx, r14
0x140004f67  jnb     short loc_140004F6F
0x140004f69  mov     [rdi+20h], r13
0x140004f6d  jmp     short loc_140004F8D
0x140004f6f  mov     r9, r14; SourceSize
0x140004f72  mov     rcx, rbx; Destination
0x140004f75  call    cs:__imp_memcpy_s
0x140004f7b  mov     [rdi+20h], rbx
0x140004f7f  add     rbx, r14
0x140004f82  jmp     short loc_140004F88
0x140004f84  mov     [rdi+20h], r13
0x140004f88  cmp     rbx, rsi
0x140004f8b  jz      short loc_140004FCF
0x140004f8d  mov     r8, [r12+18h]; Source
0x140004f92  test    r8, r8
0x140004f95  jz      short loc_140004FCF
0x140004f97  cmp     [r8], r13w
0x140004f9b  jz      short loc_140004FCF
0x140004f9d  inc     rbp
0x140004fa0  cmp     [r8+rbp*2], r13w
0x140004fa5  jnz     short loc_140004F9D
0x140004fa7  mov     rdx, rsi
0x140004faa  lea     r14, ds:2[rbp*2]
0x140004fb2  sub     rdx, rbx; DestinationSize
0x140004fb5  cmp     rdx, r14
0x140004fb8  jb      short loc_140004FCF
0x140004fba  mov     r9, r14; SourceSize
0x140004fbd  mov     rcx, rbx; Destination
0x140004fc0  call    cs:__imp_memcpy_s
0x140004fc6  mov     [rdi+38h], rbx
0x140004fca  add     rbx, r14
0x140004fcd  jmp     short loc_140004FD3
0x140004fcf  mov     [rdi+38h], r13
0x140004fd3  sub     rsi, rbx
0x140004fd6  xor     edx, edx; Val
0x140004fd8  mov     r8, rsi; Size
0x140004fdb  mov     rcx, rbx; void *
0x140004fde  call    memset_0
0x140004fe3  add     rsp, 28h
0x140004fe7  pop     r15
0x140004fe9  pop     r14
0x140004feb  pop     r13
0x140004fed  pop     r12
0x140004fef  pop     rdi
0x140004ff0  pop     rsi
0x140004ff1  pop     rbp
0x140004ff2  pop     rbx
0x140004ff3  retn
```
