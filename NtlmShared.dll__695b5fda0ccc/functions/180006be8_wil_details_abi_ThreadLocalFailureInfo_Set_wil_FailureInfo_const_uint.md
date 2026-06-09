# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006be8`
- end: `0x180006e04`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004260`

## callees

- `0x1800054b8`
- `0x180006be8`
- `0x18000c4a4`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006d34`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006d85`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006dd0`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006d34`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006d85`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006dd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cd0`

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
0x180006be8  push    rbx
0x180006bea  push    rbp
0x180006beb  push    rsi
0x180006bec  push    rdi
0x180006bed  push    r12
0x180006bef  push    r13
0x180006bf1  push    r14
0x180006bf3  push    r15
0x180006bf5  sub     rsp, 28h
0x180006bf9  mov     [rcx+4], r8d
0x180006bfd  xor     r13d, r13d
0x180006c00  mov     eax, [rdx+8]
0x180006c03  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006c07  mov     [rcx+8], eax
0x180006c0a  mov     rdi, rcx
0x180006c0d  mov     [rcx+10h], r13
0x180006c11  mov     r12, rdx
0x180006c14  movzx   eax, word ptr [rdx+40h]
0x180006c18  mov     [rcx+18h], ax
0x180006c1c  mov     al, [rdx]
0x180006c1e  mov     [rcx+1Ah], al
0x180006c21  mov     [rcx+20h], r13
0x180006c25  mov     rax, [rdx+88h]
0x180006c2c  mov     [rcx+28h], rax
0x180006c30  mov     rax, [rdx+90h]
0x180006c37  mov     [rcx+30h], rax
0x180006c3b  mov     [rcx+38h], r13
0x180006c3f  mov     rcx, [rdx+38h]
0x180006c43  lea     edx, [rbp+2]
0x180006c46  test    rcx, rcx
0x180006c49  jnz     short loc_180006C50
0x180006c4b  mov     r8d, edx
0x180006c4e  jmp     short loc_180006C60
0x180006c50  mov     rax, rbp
0x180006c53  inc     rax
0x180006c56  cmp     [rcx+rax], r13b
0x180006c5a  jnz     short loc_180006C53
0x180006c5c  lea     r8, [rax+1]; unsigned __int64
0x180006c60  mov     rcx, [r12+80h]
0x180006c68  test    rcx, rcx
0x180006c6b  jz      short loc_180006C7D
0x180006c6d  mov     rax, rbp
0x180006c70  inc     rax
0x180006c73  cmp     [rcx+rax], r13b
0x180006c77  jnz     short loc_180006C70
0x180006c79  lea     rdx, [rax+1]
0x180006c7d  mov     rcx, [r12+18h]
0x180006c82  test    rcx, rcx
0x180006c85  jnz     short loc_180006C8C
0x180006c87  lea     eax, [rcx+2]
0x180006c8a  jmp     short loc_180006CA1
0x180006c8c  mov     rax, rbp
0x180006c8f  inc     rax
0x180006c92  cmp     [rcx+rax*2], r13w
0x180006c97  jnz     short loc_180006C8F
0x180006c99  lea     rax, ds:2[rax*2]
0x180006ca1  lea     r14, [rdx+rax]
0x180006ca5  add     r14, r8
0x180006ca8  lea     rsi, [rdi+48h]
0x180006cac  cmp     [rdi+40h], r13
0x180006cb0  jz      short loc_180006CB7
0x180006cb2  cmp     [rsi], r14
0x180006cb5  jnb     short loc_180006CEB
0x180006cb7  mov     rdx, r14; dwBytes
0x180006cba  mov     ecx, 8; dwFlags
0x180006cbf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006cc4  mov     r15, rax
0x180006cc7  test    rax, rax
0x180006cca  jz      short loc_180006CEB
0x180006ccc  mov     rbx, [rdi+40h]
0x180006cd0  call    cs:__imp_GetProcessHeap
0x180006cd6  mov     r8, rbx; lpMem
0x180006cd9  xor     edx, edx; dwFlags
0x180006cdb  mov     rcx, rax; hHeap
0x180006cde  call    cs:__imp_HeapFree
0x180006ce4  mov     [rdi+40h], r15
0x180006ce8  mov     [rsi], r14
0x180006ceb  mov     rbx, [rdi+40h]
0x180006cef  test    rbx, rbx
0x180006cf2  jz      loc_180006DF3
0x180006cf8  mov     rdx, [rsi]; DestinationSize
0x180006cfb  lea     rsi, [rdx+rbx]
0x180006cff  cmp     rbx, rsi
0x180006d02  jz      short loc_180006D43
0x180006d04  mov     r8, [r12+38h]; Source
0x180006d09  test    r8, r8
0x180006d0c  jz      short loc_180006D43
0x180006d0e  cmp     [r8], r13b
0x180006d11  jz      short loc_180006D43
0x180006d13  mov     rax, rbp
0x180006d16  inc     rax
0x180006d19  cmp     [r8+rax], r13b
0x180006d1d  jnz     short loc_180006D16
0x180006d1f  lea     r14, [rax+1]
0x180006d23  cmp     rdx, r14
0x180006d26  jnb     short loc_180006D2E
0x180006d28  mov     [rdi+10h], r13
0x180006d2c  jmp     short loc_180006D4C
0x180006d2e  mov     r9, r14; SourceSize
0x180006d31  mov     rcx, rbx; Destination
0x180006d34  call    cs:__imp_memcpy_s
0x180006d3a  mov     [rdi+10h], rbx
0x180006d3e  add     rbx, r14
0x180006d41  jmp     short loc_180006D47
0x180006d43  mov     [rdi+10h], r13
0x180006d47  cmp     rbx, rsi
0x180006d4a  jz      short loc_180006D94
0x180006d4c  mov     r8, [r12+80h]; Source
0x180006d54  test    r8, r8
0x180006d57  jz      short loc_180006D94
0x180006d59  cmp     [r8], r13b
0x180006d5c  jz      short loc_180006D94
0x180006d5e  mov     rax, rbp
0x180006d61  inc     rax
0x180006d64  cmp     [r8+rax], r13b
0x180006d68  jnz     short loc_180006D61
0x180006d6a  mov     rdx, rsi
0x180006d6d  lea     r14, [rax+1]
0x180006d71  sub     rdx, rbx; DestinationSize
0x180006d74  cmp     rdx, r14
0x180006d77  jnb     short loc_180006D7F
0x180006d79  mov     [rdi+20h], r13
0x180006d7d  jmp     short loc_180006D9D
0x180006d7f  mov     r9, r14; SourceSize
0x180006d82  mov     rcx, rbx; Destination
0x180006d85  call    cs:__imp_memcpy_s
0x180006d8b  mov     [rdi+20h], rbx
0x180006d8f  add     rbx, r14
0x180006d92  jmp     short loc_180006D98
0x180006d94  mov     [rdi+20h], r13
0x180006d98  cmp     rbx, rsi
0x180006d9b  jz      short loc_180006DDF
0x180006d9d  mov     r8, [r12+18h]; Source
0x180006da2  test    r8, r8
0x180006da5  jz      short loc_180006DDF
0x180006da7  cmp     [r8], r13w
0x180006dab  jz      short loc_180006DDF
0x180006dad  inc     rbp
0x180006db0  cmp     [r8+rbp*2], r13w
0x180006db5  jnz     short loc_180006DAD
0x180006db7  mov     rdx, rsi
0x180006dba  lea     r14, ds:2[rbp*2]
0x180006dc2  sub     rdx, rbx; DestinationSize
0x180006dc5  cmp     rdx, r14
0x180006dc8  jb      short loc_180006DDF
0x180006dca  mov     r9, r14; SourceSize
0x180006dcd  mov     rcx, rbx; Destination
0x180006dd0  call    cs:__imp_memcpy_s
0x180006dd6  mov     [rdi+38h], rbx
0x180006dda  add     rbx, r14
0x180006ddd  jmp     short loc_180006DE3
0x180006ddf  mov     [rdi+38h], r13
0x180006de3  sub     rsi, rbx
0x180006de6  xor     edx, edx; Val
0x180006de8  mov     r8, rsi; Size
0x180006deb  mov     rcx, rbx; void *
0x180006dee  call    memset_0
0x180006df3  add     rsp, 28h
0x180006df7  pop     r15
0x180006df9  pop     r14
0x180006dfb  pop     r13
0x180006dfd  pop     r12
0x180006dff  pop     rdi
0x180006e00  pop     rsi
0x180006e01  pop     rbp
0x180006e02  pop     rbx
0x180006e03  retn
```
