# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005e40`
- end: `0x180006059`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004900`

## callees

- `0x180002648`
- `0x18000598c`
- `0x180005e40`
- `0x180007308`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f28`

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
0x180005e40  push    rbx
0x180005e42  push    rbp
0x180005e43  push    rsi
0x180005e44  push    rdi
0x180005e45  push    r12
0x180005e47  push    r13
0x180005e49  push    r14
0x180005e4b  push    r15
0x180005e4d  sub     rsp, 28h
0x180005e51  mov     [rcx+4], r8d
0x180005e55  xor     r13d, r13d
0x180005e58  mov     eax, [rdx+8]
0x180005e5b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005e5f  mov     [rcx+8], eax
0x180005e62  mov     rdi, rcx
0x180005e65  mov     [rcx+10h], r13
0x180005e69  mov     r12, rdx
0x180005e6c  movzx   eax, word ptr [rdx+40h]
0x180005e70  mov     [rcx+18h], ax
0x180005e74  mov     al, [rdx]
0x180005e76  mov     [rcx+1Ah], al
0x180005e79  mov     [rcx+20h], r13
0x180005e7d  mov     rax, [rdx+88h]
0x180005e84  mov     [rcx+28h], rax
0x180005e88  mov     rax, [rdx+90h]
0x180005e8f  mov     [rcx+30h], rax
0x180005e93  mov     [rcx+38h], r13
0x180005e97  mov     rcx, [rdx+38h]
0x180005e9b  lea     edx, [rbp+2]
0x180005e9e  test    rcx, rcx
0x180005ea1  jnz     short loc_180005EA8
0x180005ea3  mov     r8d, edx
0x180005ea6  jmp     short loc_180005EB8
0x180005ea8  mov     rax, rbp
0x180005eab  inc     rax
0x180005eae  cmp     [rcx+rax], r13b
0x180005eb2  jnz     short loc_180005EAB
0x180005eb4  lea     r8, [rax+1]; unsigned __int64
0x180005eb8  mov     rcx, [r12+80h]
0x180005ec0  test    rcx, rcx
0x180005ec3  jz      short loc_180005ED5
0x180005ec5  mov     rax, rbp
0x180005ec8  inc     rax
0x180005ecb  cmp     [rcx+rax], r13b
0x180005ecf  jnz     short loc_180005EC8
0x180005ed1  lea     rdx, [rax+1]
0x180005ed5  mov     rcx, [r12+18h]
0x180005eda  test    rcx, rcx
0x180005edd  jnz     short loc_180005EE4
0x180005edf  lea     eax, [rcx+2]
0x180005ee2  jmp     short loc_180005EF9
0x180005ee4  mov     rax, rbp
0x180005ee7  inc     rax
0x180005eea  cmp     [rcx+rax*2], r13w
0x180005eef  jnz     short loc_180005EE7
0x180005ef1  lea     rax, ds:2[rax*2]
0x180005ef9  lea     r14, [rdx+rax]
0x180005efd  add     r14, r8
0x180005f00  lea     rsi, [rdi+48h]
0x180005f04  cmp     [rdi+40h], r13
0x180005f08  jz      short loc_180005F0F
0x180005f0a  cmp     [rsi], r14
0x180005f0d  jnb     short loc_180005F43
0x180005f0f  mov     rdx, r14; dwBytes
0x180005f12  mov     ecx, 8; dwFlags
0x180005f17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005f1c  mov     r15, rax
0x180005f1f  test    rax, rax
0x180005f22  jz      short loc_180005F43
0x180005f24  mov     rbx, [rdi+40h]
0x180005f28  call    cs:__imp_GetProcessHeap
0x180005f2e  mov     r8, rbx; lpMem
0x180005f31  xor     edx, edx; dwFlags
0x180005f33  mov     rcx, rax; hHeap
0x180005f36  call    cs:__imp_HeapFree
0x180005f3c  mov     [rdi+40h], r15
0x180005f40  mov     [rsi], r14
0x180005f43  mov     rbx, [rdi+40h]
0x180005f47  test    rbx, rbx
0x180005f4a  jz      loc_180006048
0x180005f50  mov     rdx, [rsi]; DestinationSize
0x180005f53  lea     rsi, [rdx+rbx]
0x180005f57  cmp     rbx, rsi
0x180005f5a  jz      short loc_180005F9A
0x180005f5c  mov     r8, [r12+38h]; Source
0x180005f61  test    r8, r8
0x180005f64  jz      short loc_180005F9A
0x180005f66  cmp     [r8], r13b
0x180005f69  jz      short loc_180005F9A
0x180005f6b  mov     rax, rbp
0x180005f6e  inc     rax
0x180005f71  cmp     [r8+rax], r13b
0x180005f75  jnz     short loc_180005F6E
0x180005f77  lea     r14, [rax+1]
0x180005f7b  cmp     rdx, r14
0x180005f7e  jnb     short loc_180005F86
0x180005f80  mov     [rdi+10h], r13
0x180005f84  jmp     short loc_180005FA3
0x180005f86  mov     r9, r14; SourceSize
0x180005f89  mov     rcx, rbx; Destination
0x180005f8c  call    memcpy_s
0x180005f91  mov     [rdi+10h], rbx
0x180005f95  add     rbx, r14
0x180005f98  jmp     short loc_180005F9E
0x180005f9a  mov     [rdi+10h], r13
0x180005f9e  cmp     rbx, rsi
0x180005fa1  jz      short loc_180005FEA
0x180005fa3  mov     r8, [r12+80h]; Source
0x180005fab  test    r8, r8
0x180005fae  jz      short loc_180005FEA
0x180005fb0  cmp     [r8], r13b
0x180005fb3  jz      short loc_180005FEA
0x180005fb5  mov     rax, rbp
0x180005fb8  inc     rax
0x180005fbb  cmp     [r8+rax], r13b
0x180005fbf  jnz     short loc_180005FB8
0x180005fc1  mov     rdx, rsi
0x180005fc4  lea     r14, [rax+1]
0x180005fc8  sub     rdx, rbx; DestinationSize
0x180005fcb  cmp     rdx, r14
0x180005fce  jnb     short loc_180005FD6
0x180005fd0  mov     [rdi+20h], r13
0x180005fd4  jmp     short loc_180005FF3
0x180005fd6  mov     r9, r14; SourceSize
0x180005fd9  mov     rcx, rbx; Destination
0x180005fdc  call    memcpy_s
0x180005fe1  mov     [rdi+20h], rbx
0x180005fe5  add     rbx, r14
0x180005fe8  jmp     short loc_180005FEE
0x180005fea  mov     [rdi+20h], r13
0x180005fee  cmp     rbx, rsi
0x180005ff1  jz      short loc_180006034
0x180005ff3  mov     r8, [r12+18h]; Source
0x180005ff8  test    r8, r8
0x180005ffb  jz      short loc_180006034
0x180005ffd  cmp     [r8], r13w
0x180006001  jz      short loc_180006034
0x180006003  inc     rbp
0x180006006  cmp     [r8+rbp*2], r13w
0x18000600b  jnz     short loc_180006003
0x18000600d  mov     rdx, rsi
0x180006010  lea     r14, ds:2[rbp*2]
0x180006018  sub     rdx, rbx; DestinationSize
0x18000601b  cmp     rdx, r14
0x18000601e  jb      short loc_180006034
0x180006020  mov     r9, r14; SourceSize
0x180006023  mov     rcx, rbx; Destination
0x180006026  call    memcpy_s
0x18000602b  mov     [rdi+38h], rbx
0x18000602f  add     rbx, r14
0x180006032  jmp     short loc_180006038
0x180006034  mov     [rdi+38h], r13
0x180006038  sub     rsi, rbx
0x18000603b  xor     edx, edx; Val
0x18000603d  mov     r8, rsi; Size
0x180006040  mov     rcx, rbx; void *
0x180006043  call    memset_0
0x180006048  add     rsp, 28h
0x18000604c  pop     r15
0x18000604e  pop     r14
0x180006050  pop     r13
0x180006052  pop     r12
0x180006054  pop     rdi
0x180006055  pop     rsi
0x180006056  pop     rbp
0x180006057  pop     rbx
0x180006058  retn
```
