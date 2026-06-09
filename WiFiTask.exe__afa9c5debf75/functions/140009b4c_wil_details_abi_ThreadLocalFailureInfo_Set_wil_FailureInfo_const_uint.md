# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140009b4c`
- end: `0x140009d65`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005980`

## callees

- `0x140002168`
- `0x140007d2c`
- `0x140009b4c`
- `0x14000c1a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009c34`

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
0x140009b4c  push    rbx
0x140009b4e  push    rbp
0x140009b4f  push    rsi
0x140009b50  push    rdi
0x140009b51  push    r12
0x140009b53  push    r13
0x140009b55  push    r14
0x140009b57  push    r15
0x140009b59  sub     rsp, 28h
0x140009b5d  mov     [rcx+4], r8d
0x140009b61  xor     r13d, r13d
0x140009b64  mov     eax, [rdx+8]
0x140009b67  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140009b6b  mov     [rcx+8], eax
0x140009b6e  mov     rdi, rcx
0x140009b71  mov     [rcx+10h], r13
0x140009b75  mov     r12, rdx
0x140009b78  movzx   eax, word ptr [rdx+40h]
0x140009b7c  mov     [rcx+18h], ax
0x140009b80  mov     al, [rdx]
0x140009b82  mov     [rcx+1Ah], al
0x140009b85  mov     [rcx+20h], r13
0x140009b89  mov     rax, [rdx+88h]
0x140009b90  mov     [rcx+28h], rax
0x140009b94  mov     rax, [rdx+90h]
0x140009b9b  mov     [rcx+30h], rax
0x140009b9f  mov     [rcx+38h], r13
0x140009ba3  mov     rcx, [rdx+38h]
0x140009ba7  lea     edx, [rbp+2]
0x140009baa  test    rcx, rcx
0x140009bad  jnz     short loc_140009BB4
0x140009baf  mov     r8d, edx
0x140009bb2  jmp     short loc_140009BC4
0x140009bb4  mov     rax, rbp
0x140009bb7  inc     rax
0x140009bba  cmp     [rcx+rax], r13b
0x140009bbe  jnz     short loc_140009BB7
0x140009bc0  lea     r8, [rax+1]; unsigned __int64
0x140009bc4  mov     rcx, [r12+80h]
0x140009bcc  test    rcx, rcx
0x140009bcf  jz      short loc_140009BE1
0x140009bd1  mov     rax, rbp
0x140009bd4  inc     rax
0x140009bd7  cmp     [rcx+rax], r13b
0x140009bdb  jnz     short loc_140009BD4
0x140009bdd  lea     rdx, [rax+1]
0x140009be1  mov     rcx, [r12+18h]
0x140009be6  test    rcx, rcx
0x140009be9  jnz     short loc_140009BF0
0x140009beb  lea     eax, [rcx+2]
0x140009bee  jmp     short loc_140009C05
0x140009bf0  mov     rax, rbp
0x140009bf3  inc     rax
0x140009bf6  cmp     [rcx+rax*2], r13w
0x140009bfb  jnz     short loc_140009BF3
0x140009bfd  lea     rax, ds:2[rax*2]
0x140009c05  lea     r14, [rdx+rax]
0x140009c09  add     r14, r8
0x140009c0c  lea     rsi, [rdi+48h]
0x140009c10  cmp     [rdi+40h], r13
0x140009c14  jz      short loc_140009C1B
0x140009c16  cmp     [rsi], r14
0x140009c19  jnb     short loc_140009C4F
0x140009c1b  mov     rdx, r14; dwBytes
0x140009c1e  mov     ecx, 8; dwFlags
0x140009c23  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009c28  mov     r15, rax
0x140009c2b  test    rax, rax
0x140009c2e  jz      short loc_140009C4F
0x140009c30  mov     rbx, [rdi+40h]
0x140009c34  call    cs:__imp_GetProcessHeap
0x140009c3a  mov     r8, rbx; lpMem
0x140009c3d  xor     edx, edx; dwFlags
0x140009c3f  mov     rcx, rax; hHeap
0x140009c42  call    cs:__imp_HeapFree
0x140009c48  mov     [rdi+40h], r15
0x140009c4c  mov     [rsi], r14
0x140009c4f  mov     rbx, [rdi+40h]
0x140009c53  test    rbx, rbx
0x140009c56  jz      loc_140009D54
0x140009c5c  mov     rdx, [rsi]; DestinationSize
0x140009c5f  lea     rsi, [rdx+rbx]
0x140009c63  cmp     rbx, rsi
0x140009c66  jz      short loc_140009CA6
0x140009c68  mov     r8, [r12+38h]; Source
0x140009c6d  test    r8, r8
0x140009c70  jz      short loc_140009CA6
0x140009c72  cmp     [r8], r13b
0x140009c75  jz      short loc_140009CA6
0x140009c77  mov     rax, rbp
0x140009c7a  inc     rax
0x140009c7d  cmp     [r8+rax], r13b
0x140009c81  jnz     short loc_140009C7A
0x140009c83  lea     r14, [rax+1]
0x140009c87  cmp     rdx, r14
0x140009c8a  jnb     short loc_140009C92
0x140009c8c  mov     [rdi+10h], r13
0x140009c90  jmp     short loc_140009CAF
0x140009c92  mov     r9, r14; SourceSize
0x140009c95  mov     rcx, rbx; Destination
0x140009c98  call    memcpy_s
0x140009c9d  mov     [rdi+10h], rbx
0x140009ca1  add     rbx, r14
0x140009ca4  jmp     short loc_140009CAA
0x140009ca6  mov     [rdi+10h], r13
0x140009caa  cmp     rbx, rsi
0x140009cad  jz      short loc_140009CF6
0x140009caf  mov     r8, [r12+80h]; Source
0x140009cb7  test    r8, r8
0x140009cba  jz      short loc_140009CF6
0x140009cbc  cmp     [r8], r13b
0x140009cbf  jz      short loc_140009CF6
0x140009cc1  mov     rax, rbp
0x140009cc4  inc     rax
0x140009cc7  cmp     [r8+rax], r13b
0x140009ccb  jnz     short loc_140009CC4
0x140009ccd  mov     rdx, rsi
0x140009cd0  lea     r14, [rax+1]
0x140009cd4  sub     rdx, rbx; DestinationSize
0x140009cd7  cmp     rdx, r14
0x140009cda  jnb     short loc_140009CE2
0x140009cdc  mov     [rdi+20h], r13
0x140009ce0  jmp     short loc_140009CFF
0x140009ce2  mov     r9, r14; SourceSize
0x140009ce5  mov     rcx, rbx; Destination
0x140009ce8  call    memcpy_s
0x140009ced  mov     [rdi+20h], rbx
0x140009cf1  add     rbx, r14
0x140009cf4  jmp     short loc_140009CFA
0x140009cf6  mov     [rdi+20h], r13
0x140009cfa  cmp     rbx, rsi
0x140009cfd  jz      short loc_140009D40
0x140009cff  mov     r8, [r12+18h]; Source
0x140009d04  test    r8, r8
0x140009d07  jz      short loc_140009D40
0x140009d09  cmp     [r8], r13w
0x140009d0d  jz      short loc_140009D40
0x140009d0f  inc     rbp
0x140009d12  cmp     [r8+rbp*2], r13w
0x140009d17  jnz     short loc_140009D0F
0x140009d19  mov     rdx, rsi
0x140009d1c  lea     r14, ds:2[rbp*2]
0x140009d24  sub     rdx, rbx; DestinationSize
0x140009d27  cmp     rdx, r14
0x140009d2a  jb      short loc_140009D40
0x140009d2c  mov     r9, r14; SourceSize
0x140009d2f  mov     rcx, rbx; Destination
0x140009d32  call    memcpy_s
0x140009d37  mov     [rdi+38h], rbx
0x140009d3b  add     rbx, r14
0x140009d3e  jmp     short loc_140009D44
0x140009d40  mov     [rdi+38h], r13
0x140009d44  sub     rsi, rbx
0x140009d47  xor     edx, edx; Val
0x140009d49  mov     r8, rsi; Size
0x140009d4c  mov     rcx, rbx; void *
0x140009d4f  call    memset_0
0x140009d54  add     rsp, 28h
0x140009d58  pop     r15
0x140009d5a  pop     r14
0x140009d5c  pop     r13
0x140009d5e  pop     r12
0x140009d60  pop     rdi
0x140009d61  pop     rsi
0x140009d62  pop     rbp
0x140009d63  pop     rbx
0x140009d64  retn
```
