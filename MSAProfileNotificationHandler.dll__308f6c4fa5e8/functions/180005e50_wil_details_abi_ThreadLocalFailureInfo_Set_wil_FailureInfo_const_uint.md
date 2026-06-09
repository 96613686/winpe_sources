# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005e50`
- end: `0x180006069`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004690`

## callees

- `0x1800028cc`
- `0x1800028f0`
- `0x18000577c`
- `0x180005e50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f46`

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
0x180005e50  push    rbx
0x180005e52  push    rbp
0x180005e53  push    rsi
0x180005e54  push    rdi
0x180005e55  push    r12
0x180005e57  push    r13
0x180005e59  push    r14
0x180005e5b  push    r15
0x180005e5d  sub     rsp, 28h
0x180005e61  mov     [rcx+4], r8d
0x180005e65  xor     r13d, r13d
0x180005e68  mov     eax, [rdx+8]
0x180005e6b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005e6f  mov     [rcx+8], eax
0x180005e72  mov     rdi, rcx
0x180005e75  mov     [rcx+10h], r13
0x180005e79  mov     r12, rdx
0x180005e7c  movzx   eax, word ptr [rdx+40h]
0x180005e80  mov     [rcx+18h], ax
0x180005e84  mov     al, [rdx]
0x180005e86  mov     [rcx+1Ah], al
0x180005e89  mov     [rcx+20h], r13
0x180005e8d  mov     rax, [rdx+88h]
0x180005e94  mov     [rcx+28h], rax
0x180005e98  mov     rax, [rdx+90h]
0x180005e9f  mov     [rcx+30h], rax
0x180005ea3  mov     [rcx+38h], r13
0x180005ea7  mov     rcx, [rdx+38h]
0x180005eab  lea     edx, [rbp+2]
0x180005eae  test    rcx, rcx
0x180005eb1  jnz     short loc_180005EB8
0x180005eb3  mov     r8d, edx
0x180005eb6  jmp     short loc_180005EC8
0x180005eb8  mov     rax, rbp
0x180005ebb  inc     rax
0x180005ebe  cmp     [rcx+rax], r13b
0x180005ec2  jnz     short loc_180005EBB
0x180005ec4  lea     r8, [rax+1]; unsigned __int64
0x180005ec8  mov     rcx, [r12+80h]
0x180005ed0  test    rcx, rcx
0x180005ed3  jz      short loc_180005EE5
0x180005ed5  mov     rax, rbp
0x180005ed8  inc     rax
0x180005edb  cmp     [rcx+rax], r13b
0x180005edf  jnz     short loc_180005ED8
0x180005ee1  lea     rdx, [rax+1]
0x180005ee5  mov     rcx, [r12+18h]
0x180005eea  test    rcx, rcx
0x180005eed  jnz     short loc_180005EF4
0x180005eef  lea     eax, [rcx+2]
0x180005ef2  jmp     short loc_180005F09
0x180005ef4  mov     rax, rbp
0x180005ef7  inc     rax
0x180005efa  cmp     [rcx+rax*2], r13w
0x180005eff  jnz     short loc_180005EF7
0x180005f01  lea     rax, ds:2[rax*2]
0x180005f09  lea     r14, [rdx+rax]
0x180005f0d  add     r14, r8
0x180005f10  lea     rsi, [rdi+48h]
0x180005f14  cmp     [rdi+40h], r13
0x180005f18  jz      short loc_180005F1F
0x180005f1a  cmp     [rsi], r14
0x180005f1d  jnb     short loc_180005F53
0x180005f1f  mov     rdx, r14; dwBytes
0x180005f22  mov     ecx, 8; dwFlags
0x180005f27  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005f2c  mov     r15, rax
0x180005f2f  test    rax, rax
0x180005f32  jz      short loc_180005F53
0x180005f34  mov     rbx, [rdi+40h]
0x180005f38  call    cs:__imp_GetProcessHeap
0x180005f3e  mov     r8, rbx; lpMem
0x180005f41  xor     edx, edx; dwFlags
0x180005f43  mov     rcx, rax; hHeap
0x180005f46  call    cs:__imp_HeapFree
0x180005f4c  mov     [rdi+40h], r15
0x180005f50  mov     [rsi], r14
0x180005f53  mov     rbx, [rdi+40h]
0x180005f57  test    rbx, rbx
0x180005f5a  jz      loc_180006058
0x180005f60  mov     rdx, [rsi]; DestinationSize
0x180005f63  lea     rsi, [rdx+rbx]
0x180005f67  cmp     rbx, rsi
0x180005f6a  jz      short loc_180005FAA
0x180005f6c  mov     r8, [r12+38h]; Source
0x180005f71  test    r8, r8
0x180005f74  jz      short loc_180005FAA
0x180005f76  cmp     [r8], r13b
0x180005f79  jz      short loc_180005FAA
0x180005f7b  mov     rax, rbp
0x180005f7e  inc     rax
0x180005f81  cmp     [r8+rax], r13b
0x180005f85  jnz     short loc_180005F7E
0x180005f87  lea     r14, [rax+1]
0x180005f8b  cmp     rdx, r14
0x180005f8e  jnb     short loc_180005F96
0x180005f90  mov     [rdi+10h], r13
0x180005f94  jmp     short loc_180005FB3
0x180005f96  mov     r9, r14; SourceSize
0x180005f99  mov     rcx, rbx; Destination
0x180005f9c  call    memcpy_s
0x180005fa1  mov     [rdi+10h], rbx
0x180005fa5  add     rbx, r14
0x180005fa8  jmp     short loc_180005FAE
0x180005faa  mov     [rdi+10h], r13
0x180005fae  cmp     rbx, rsi
0x180005fb1  jz      short loc_180005FFA
0x180005fb3  mov     r8, [r12+80h]; Source
0x180005fbb  test    r8, r8
0x180005fbe  jz      short loc_180005FFA
0x180005fc0  cmp     [r8], r13b
0x180005fc3  jz      short loc_180005FFA
0x180005fc5  mov     rax, rbp
0x180005fc8  inc     rax
0x180005fcb  cmp     [r8+rax], r13b
0x180005fcf  jnz     short loc_180005FC8
0x180005fd1  mov     rdx, rsi
0x180005fd4  lea     r14, [rax+1]
0x180005fd8  sub     rdx, rbx; DestinationSize
0x180005fdb  cmp     rdx, r14
0x180005fde  jnb     short loc_180005FE6
0x180005fe0  mov     [rdi+20h], r13
0x180005fe4  jmp     short loc_180006003
0x180005fe6  mov     r9, r14; SourceSize
0x180005fe9  mov     rcx, rbx; Destination
0x180005fec  call    memcpy_s
0x180005ff1  mov     [rdi+20h], rbx
0x180005ff5  add     rbx, r14
0x180005ff8  jmp     short loc_180005FFE
0x180005ffa  mov     [rdi+20h], r13
0x180005ffe  cmp     rbx, rsi
0x180006001  jz      short loc_180006044
0x180006003  mov     r8, [r12+18h]; Source
0x180006008  test    r8, r8
0x18000600b  jz      short loc_180006044
0x18000600d  cmp     [r8], r13w
0x180006011  jz      short loc_180006044
0x180006013  inc     rbp
0x180006016  cmp     [r8+rbp*2], r13w
0x18000601b  jnz     short loc_180006013
0x18000601d  mov     rdx, rsi
0x180006020  lea     r14, ds:2[rbp*2]
0x180006028  sub     rdx, rbx; DestinationSize
0x18000602b  cmp     rdx, r14
0x18000602e  jb      short loc_180006044
0x180006030  mov     r9, r14; SourceSize
0x180006033  mov     rcx, rbx; Destination
0x180006036  call    memcpy_s
0x18000603b  mov     [rdi+38h], rbx
0x18000603f  add     rbx, r14
0x180006042  jmp     short loc_180006048
0x180006044  mov     [rdi+38h], r13
0x180006048  sub     rsi, rbx
0x18000604b  xor     edx, edx; Val
0x18000604d  mov     r8, rsi; Size
0x180006050  mov     rcx, rbx; void *
0x180006053  call    memset_0
0x180006058  add     rsp, 28h
0x18000605c  pop     r15
0x18000605e  pop     r14
0x180006060  pop     r13
0x180006062  pop     r12
0x180006064  pop     rdi
0x180006065  pop     rsi
0x180006066  pop     rbp
0x180006067  pop     rbx
0x180006068  retn
```
