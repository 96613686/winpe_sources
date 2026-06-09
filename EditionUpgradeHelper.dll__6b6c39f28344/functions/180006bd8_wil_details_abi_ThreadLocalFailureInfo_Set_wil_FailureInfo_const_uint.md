# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006bd8`
- end: `0x180006df1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004670`

## callees

- `0x1800024d4`
- `0x1800057d8`
- `0x180006bd8`
- `0x180007ed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cce`

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
0x180006bd8  push    rbx
0x180006bda  push    rbp
0x180006bdb  push    rsi
0x180006bdc  push    rdi
0x180006bdd  push    r12
0x180006bdf  push    r13
0x180006be1  push    r14
0x180006be3  push    r15
0x180006be5  sub     rsp, 28h
0x180006be9  mov     [rcx+4], r8d
0x180006bed  xor     r13d, r13d
0x180006bf0  mov     eax, [rdx+8]
0x180006bf3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006bf7  mov     [rcx+8], eax
0x180006bfa  mov     rdi, rcx
0x180006bfd  mov     [rcx+10h], r13
0x180006c01  mov     r12, rdx
0x180006c04  movzx   eax, word ptr [rdx+40h]
0x180006c08  mov     [rcx+18h], ax
0x180006c0c  mov     al, [rdx]
0x180006c0e  mov     [rcx+1Ah], al
0x180006c11  mov     [rcx+20h], r13
0x180006c15  mov     rax, [rdx+88h]
0x180006c1c  mov     [rcx+28h], rax
0x180006c20  mov     rax, [rdx+90h]
0x180006c27  mov     [rcx+30h], rax
0x180006c2b  mov     [rcx+38h], r13
0x180006c2f  mov     rcx, [rdx+38h]
0x180006c33  lea     edx, [rbp+2]
0x180006c36  test    rcx, rcx
0x180006c39  jnz     short loc_180006C40
0x180006c3b  mov     r8d, edx
0x180006c3e  jmp     short loc_180006C50
0x180006c40  mov     rax, rbp
0x180006c43  inc     rax
0x180006c46  cmp     [rcx+rax], r13b
0x180006c4a  jnz     short loc_180006C43
0x180006c4c  lea     r8, [rax+1]; unsigned __int64
0x180006c50  mov     rcx, [r12+80h]
0x180006c58  test    rcx, rcx
0x180006c5b  jz      short loc_180006C6D
0x180006c5d  mov     rax, rbp
0x180006c60  inc     rax
0x180006c63  cmp     [rcx+rax], r13b
0x180006c67  jnz     short loc_180006C60
0x180006c69  lea     rdx, [rax+1]
0x180006c6d  mov     rcx, [r12+18h]
0x180006c72  test    rcx, rcx
0x180006c75  jnz     short loc_180006C7C
0x180006c77  lea     eax, [rcx+2]
0x180006c7a  jmp     short loc_180006C91
0x180006c7c  mov     rax, rbp
0x180006c7f  inc     rax
0x180006c82  cmp     [rcx+rax*2], r13w
0x180006c87  jnz     short loc_180006C7F
0x180006c89  lea     rax, ds:2[rax*2]
0x180006c91  lea     r14, [rdx+rax]
0x180006c95  add     r14, r8
0x180006c98  lea     rsi, [rdi+48h]
0x180006c9c  cmp     [rdi+40h], r13
0x180006ca0  jz      short loc_180006CA7
0x180006ca2  cmp     [rsi], r14
0x180006ca5  jnb     short loc_180006CDB
0x180006ca7  mov     rdx, r14; dwBytes
0x180006caa  mov     ecx, 8; dwFlags
0x180006caf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006cb4  mov     r15, rax
0x180006cb7  test    rax, rax
0x180006cba  jz      short loc_180006CDB
0x180006cbc  mov     rbx, [rdi+40h]
0x180006cc0  call    cs:__imp_GetProcessHeap
0x180006cc6  mov     r8, rbx; lpMem
0x180006cc9  xor     edx, edx; dwFlags
0x180006ccb  mov     rcx, rax; hHeap
0x180006cce  call    cs:__imp_HeapFree
0x180006cd4  mov     [rdi+40h], r15
0x180006cd8  mov     [rsi], r14
0x180006cdb  mov     rbx, [rdi+40h]
0x180006cdf  test    rbx, rbx
0x180006ce2  jz      loc_180006DE0
0x180006ce8  mov     rdx, [rsi]; DestinationSize
0x180006ceb  lea     rsi, [rdx+rbx]
0x180006cef  cmp     rbx, rsi
0x180006cf2  jz      short loc_180006D32
0x180006cf4  mov     r8, [r12+38h]; Source
0x180006cf9  test    r8, r8
0x180006cfc  jz      short loc_180006D32
0x180006cfe  cmp     [r8], r13b
0x180006d01  jz      short loc_180006D32
0x180006d03  mov     rax, rbp
0x180006d06  inc     rax
0x180006d09  cmp     [r8+rax], r13b
0x180006d0d  jnz     short loc_180006D06
0x180006d0f  lea     r14, [rax+1]
0x180006d13  cmp     rdx, r14
0x180006d16  jnb     short loc_180006D1E
0x180006d18  mov     [rdi+10h], r13
0x180006d1c  jmp     short loc_180006D3B
0x180006d1e  mov     r9, r14; SourceSize
0x180006d21  mov     rcx, rbx; Destination
0x180006d24  call    memcpy_s
0x180006d29  mov     [rdi+10h], rbx
0x180006d2d  add     rbx, r14
0x180006d30  jmp     short loc_180006D36
0x180006d32  mov     [rdi+10h], r13
0x180006d36  cmp     rbx, rsi
0x180006d39  jz      short loc_180006D82
0x180006d3b  mov     r8, [r12+80h]; Source
0x180006d43  test    r8, r8
0x180006d46  jz      short loc_180006D82
0x180006d48  cmp     [r8], r13b
0x180006d4b  jz      short loc_180006D82
0x180006d4d  mov     rax, rbp
0x180006d50  inc     rax
0x180006d53  cmp     [r8+rax], r13b
0x180006d57  jnz     short loc_180006D50
0x180006d59  mov     rdx, rsi
0x180006d5c  lea     r14, [rax+1]
0x180006d60  sub     rdx, rbx; DestinationSize
0x180006d63  cmp     rdx, r14
0x180006d66  jnb     short loc_180006D6E
0x180006d68  mov     [rdi+20h], r13
0x180006d6c  jmp     short loc_180006D8B
0x180006d6e  mov     r9, r14; SourceSize
0x180006d71  mov     rcx, rbx; Destination
0x180006d74  call    memcpy_s
0x180006d79  mov     [rdi+20h], rbx
0x180006d7d  add     rbx, r14
0x180006d80  jmp     short loc_180006D86
0x180006d82  mov     [rdi+20h], r13
0x180006d86  cmp     rbx, rsi
0x180006d89  jz      short loc_180006DCC
0x180006d8b  mov     r8, [r12+18h]; Source
0x180006d90  test    r8, r8
0x180006d93  jz      short loc_180006DCC
0x180006d95  cmp     [r8], r13w
0x180006d99  jz      short loc_180006DCC
0x180006d9b  inc     rbp
0x180006d9e  cmp     [r8+rbp*2], r13w
0x180006da3  jnz     short loc_180006D9B
0x180006da5  mov     rdx, rsi
0x180006da8  lea     r14, ds:2[rbp*2]
0x180006db0  sub     rdx, rbx; DestinationSize
0x180006db3  cmp     rdx, r14
0x180006db6  jb      short loc_180006DCC
0x180006db8  mov     r9, r14; SourceSize
0x180006dbb  mov     rcx, rbx; Destination
0x180006dbe  call    memcpy_s
0x180006dc3  mov     [rdi+38h], rbx
0x180006dc7  add     rbx, r14
0x180006dca  jmp     short loc_180006DD0
0x180006dcc  mov     [rdi+38h], r13
0x180006dd0  sub     rsi, rbx
0x180006dd3  xor     edx, edx; Val
0x180006dd5  mov     r8, rsi; Size
0x180006dd8  mov     rcx, rbx; void *
0x180006ddb  call    memset_0
0x180006de0  add     rsp, 28h
0x180006de4  pop     r15
0x180006de6  pop     r14
0x180006de8  pop     r13
0x180006dea  pop     r12
0x180006dec  pop     rdi
0x180006ded  pop     rsi
0x180006dee  pop     rbp
0x180006def  pop     rbx
0x180006df0  retn
```
