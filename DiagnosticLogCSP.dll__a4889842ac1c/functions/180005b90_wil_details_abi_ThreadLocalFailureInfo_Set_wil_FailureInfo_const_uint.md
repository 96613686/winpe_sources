# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005b90`
- end: `0x180005da9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047d0`

## callees

- `0x18000262c`
- `0x180005828`
- `0x180005b90`
- `0x180006bd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c86`

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
                memcpy_s_0(v20, v22 - v20, v29, 2 * v3 + 2);
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
          memcpy_s_0(v20, v22 - v20, v26, v27 + 1);
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
      memcpy_s_0(*((void *const *)this + 8), v21, v23, v24 + 1);
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
0x180005b90  push    rbx
0x180005b92  push    rbp
0x180005b93  push    rsi
0x180005b94  push    rdi
0x180005b95  push    r12
0x180005b97  push    r13
0x180005b99  push    r14
0x180005b9b  push    r15
0x180005b9d  sub     rsp, 28h
0x180005ba1  mov     [rcx+4], r8d
0x180005ba5  xor     r13d, r13d
0x180005ba8  mov     eax, [rdx+8]
0x180005bab  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005baf  mov     [rcx+8], eax
0x180005bb2  mov     rdi, rcx
0x180005bb5  mov     [rcx+10h], r13
0x180005bb9  mov     r12, rdx
0x180005bbc  movzx   eax, word ptr [rdx+40h]
0x180005bc0  mov     [rcx+18h], ax
0x180005bc4  mov     al, [rdx]
0x180005bc6  mov     [rcx+1Ah], al
0x180005bc9  mov     [rcx+20h], r13
0x180005bcd  mov     rax, [rdx+88h]
0x180005bd4  mov     [rcx+28h], rax
0x180005bd8  mov     rax, [rdx+90h]
0x180005bdf  mov     [rcx+30h], rax
0x180005be3  mov     [rcx+38h], r13
0x180005be7  mov     rcx, [rdx+38h]
0x180005beb  lea     edx, [rbp+2]
0x180005bee  test    rcx, rcx
0x180005bf1  jnz     short loc_180005BF8
0x180005bf3  mov     r8d, edx
0x180005bf6  jmp     short loc_180005C08
0x180005bf8  mov     rax, rbp
0x180005bfb  inc     rax
0x180005bfe  cmp     [rcx+rax], r13b
0x180005c02  jnz     short loc_180005BFB
0x180005c04  lea     r8, [rax+1]; unsigned __int64
0x180005c08  mov     rcx, [r12+80h]
0x180005c10  test    rcx, rcx
0x180005c13  jz      short loc_180005C25
0x180005c15  mov     rax, rbp
0x180005c18  inc     rax
0x180005c1b  cmp     [rcx+rax], r13b
0x180005c1f  jnz     short loc_180005C18
0x180005c21  lea     rdx, [rax+1]
0x180005c25  mov     rcx, [r12+18h]
0x180005c2a  test    rcx, rcx
0x180005c2d  jnz     short loc_180005C34
0x180005c2f  lea     eax, [rcx+2]
0x180005c32  jmp     short loc_180005C49
0x180005c34  mov     rax, rbp
0x180005c37  inc     rax
0x180005c3a  cmp     [rcx+rax*2], r13w
0x180005c3f  jnz     short loc_180005C37
0x180005c41  lea     rax, ds:2[rax*2]
0x180005c49  lea     r14, [rdx+rax]
0x180005c4d  add     r14, r8
0x180005c50  lea     rsi, [rdi+48h]
0x180005c54  cmp     [rdi+40h], r13
0x180005c58  jz      short loc_180005C5F
0x180005c5a  cmp     [rsi], r14
0x180005c5d  jnb     short loc_180005C93
0x180005c5f  mov     rdx, r14; dwBytes
0x180005c62  mov     ecx, 8; dwFlags
0x180005c67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005c6c  mov     r15, rax
0x180005c6f  test    rax, rax
0x180005c72  jz      short loc_180005C93
0x180005c74  mov     rbx, [rdi+40h]
0x180005c78  call    cs:__imp_GetProcessHeap
0x180005c7e  mov     r8, rbx; lpMem
0x180005c81  xor     edx, edx; dwFlags
0x180005c83  mov     rcx, rax; hHeap
0x180005c86  call    cs:__imp_HeapFree
0x180005c8c  mov     [rdi+40h], r15
0x180005c90  mov     [rsi], r14
0x180005c93  mov     rbx, [rdi+40h]
0x180005c97  test    rbx, rbx
0x180005c9a  jz      loc_180005D98
0x180005ca0  mov     rdx, [rsi]; DestinationSize
0x180005ca3  lea     rsi, [rdx+rbx]
0x180005ca7  cmp     rbx, rsi
0x180005caa  jz      short loc_180005CEA
0x180005cac  mov     r8, [r12+38h]; Source
0x180005cb1  test    r8, r8
0x180005cb4  jz      short loc_180005CEA
0x180005cb6  cmp     [r8], r13b
0x180005cb9  jz      short loc_180005CEA
0x180005cbb  mov     rax, rbp
0x180005cbe  inc     rax
0x180005cc1  cmp     [r8+rax], r13b
0x180005cc5  jnz     short loc_180005CBE
0x180005cc7  lea     r14, [rax+1]
0x180005ccb  cmp     rdx, r14
0x180005cce  jnb     short loc_180005CD6
0x180005cd0  mov     [rdi+10h], r13
0x180005cd4  jmp     short loc_180005CF3
0x180005cd6  mov     r9, r14; SourceSize
0x180005cd9  mov     rcx, rbx; Destination
0x180005cdc  call    memcpy_s_0
0x180005ce1  mov     [rdi+10h], rbx
0x180005ce5  add     rbx, r14
0x180005ce8  jmp     short loc_180005CEE
0x180005cea  mov     [rdi+10h], r13
0x180005cee  cmp     rbx, rsi
0x180005cf1  jz      short loc_180005D3A
0x180005cf3  mov     r8, [r12+80h]; Source
0x180005cfb  test    r8, r8
0x180005cfe  jz      short loc_180005D3A
0x180005d00  cmp     [r8], r13b
0x180005d03  jz      short loc_180005D3A
0x180005d05  mov     rax, rbp
0x180005d08  inc     rax
0x180005d0b  cmp     [r8+rax], r13b
0x180005d0f  jnz     short loc_180005D08
0x180005d11  mov     rdx, rsi
0x180005d14  lea     r14, [rax+1]
0x180005d18  sub     rdx, rbx; DestinationSize
0x180005d1b  cmp     rdx, r14
0x180005d1e  jnb     short loc_180005D26
0x180005d20  mov     [rdi+20h], r13
0x180005d24  jmp     short loc_180005D43
0x180005d26  mov     r9, r14; SourceSize
0x180005d29  mov     rcx, rbx; Destination
0x180005d2c  call    memcpy_s_0
0x180005d31  mov     [rdi+20h], rbx
0x180005d35  add     rbx, r14
0x180005d38  jmp     short loc_180005D3E
0x180005d3a  mov     [rdi+20h], r13
0x180005d3e  cmp     rbx, rsi
0x180005d41  jz      short loc_180005D84
0x180005d43  mov     r8, [r12+18h]; Source
0x180005d48  test    r8, r8
0x180005d4b  jz      short loc_180005D84
0x180005d4d  cmp     [r8], r13w
0x180005d51  jz      short loc_180005D84
0x180005d53  inc     rbp
0x180005d56  cmp     [r8+rbp*2], r13w
0x180005d5b  jnz     short loc_180005D53
0x180005d5d  mov     rdx, rsi
0x180005d60  lea     r14, ds:2[rbp*2]
0x180005d68  sub     rdx, rbx; DestinationSize
0x180005d6b  cmp     rdx, r14
0x180005d6e  jb      short loc_180005D84
0x180005d70  mov     r9, r14; SourceSize
0x180005d73  mov     rcx, rbx; Destination
0x180005d76  call    memcpy_s_0
0x180005d7b  mov     [rdi+38h], rbx
0x180005d7f  add     rbx, r14
0x180005d82  jmp     short loc_180005D88
0x180005d84  mov     [rdi+38h], r13
0x180005d88  sub     rsi, rbx
0x180005d8b  xor     edx, edx; Val
0x180005d8d  mov     r8, rsi; Size
0x180005d90  mov     rcx, rbx; void *
0x180005d93  call    memset_0
0x180005d98  add     rsp, 28h
0x180005d9c  pop     r15
0x180005d9e  pop     r14
0x180005da0  pop     r13
0x180005da2  pop     r12
0x180005da4  pop     rdi
0x180005da5  pop     rsi
0x180005da6  pop     rbp
0x180005da7  pop     rbx
0x180005da8  retn
```
