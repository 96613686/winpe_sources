# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a8a0`
- end: `0x18000aab9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007e40`

## callees

- `0x18000526c`
- `0x180009368`
- `0x18000a8a0`
- `0x18000be28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a996`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a988`

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
0x18000a8a0  push    rbx
0x18000a8a2  push    rbp
0x18000a8a3  push    rsi
0x18000a8a4  push    rdi
0x18000a8a5  push    r12
0x18000a8a7  push    r13
0x18000a8a9  push    r14
0x18000a8ab  push    r15
0x18000a8ad  sub     rsp, 28h
0x18000a8b1  mov     [rcx+4], r8d
0x18000a8b5  xor     r13d, r13d
0x18000a8b8  mov     eax, [rdx+8]
0x18000a8bb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a8bf  mov     [rcx+8], eax
0x18000a8c2  mov     rdi, rcx
0x18000a8c5  mov     [rcx+10h], r13
0x18000a8c9  mov     r12, rdx
0x18000a8cc  movzx   eax, word ptr [rdx+40h]
0x18000a8d0  mov     [rcx+18h], ax
0x18000a8d4  mov     al, [rdx]
0x18000a8d6  mov     [rcx+1Ah], al
0x18000a8d9  mov     [rcx+20h], r13
0x18000a8dd  mov     rax, [rdx+88h]
0x18000a8e4  mov     [rcx+28h], rax
0x18000a8e8  mov     rax, [rdx+90h]
0x18000a8ef  mov     [rcx+30h], rax
0x18000a8f3  mov     [rcx+38h], r13
0x18000a8f7  mov     rcx, [rdx+38h]
0x18000a8fb  lea     edx, [rbp+2]
0x18000a8fe  test    rcx, rcx
0x18000a901  jnz     short loc_18000A908
0x18000a903  mov     r8d, edx
0x18000a906  jmp     short loc_18000A918
0x18000a908  mov     rax, rbp
0x18000a90b  inc     rax
0x18000a90e  cmp     [rcx+rax], r13b
0x18000a912  jnz     short loc_18000A90B
0x18000a914  lea     r8, [rax+1]; unsigned __int64
0x18000a918  mov     rcx, [r12+80h]
0x18000a920  test    rcx, rcx
0x18000a923  jz      short loc_18000A935
0x18000a925  mov     rax, rbp
0x18000a928  inc     rax
0x18000a92b  cmp     [rcx+rax], r13b
0x18000a92f  jnz     short loc_18000A928
0x18000a931  lea     rdx, [rax+1]
0x18000a935  mov     rcx, [r12+18h]
0x18000a93a  test    rcx, rcx
0x18000a93d  jnz     short loc_18000A944
0x18000a93f  lea     eax, [rcx+2]
0x18000a942  jmp     short loc_18000A959
0x18000a944  mov     rax, rbp
0x18000a947  inc     rax
0x18000a94a  cmp     [rcx+rax*2], r13w
0x18000a94f  jnz     short loc_18000A947
0x18000a951  lea     rax, ds:2[rax*2]
0x18000a959  lea     r14, [rdx+rax]
0x18000a95d  add     r14, r8
0x18000a960  lea     rsi, [rdi+48h]
0x18000a964  cmp     [rdi+40h], r13
0x18000a968  jz      short loc_18000A96F
0x18000a96a  cmp     [rsi], r14
0x18000a96d  jnb     short loc_18000A9A3
0x18000a96f  mov     rdx, r14; dwBytes
0x18000a972  mov     ecx, 8; dwFlags
0x18000a977  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a97c  mov     r15, rax
0x18000a97f  test    rax, rax
0x18000a982  jz      short loc_18000A9A3
0x18000a984  mov     rbx, [rdi+40h]
0x18000a988  call    cs:__imp_GetProcessHeap
0x18000a98e  mov     r8, rbx; lpMem
0x18000a991  xor     edx, edx; dwFlags
0x18000a993  mov     rcx, rax; hHeap
0x18000a996  call    cs:__imp_HeapFree
0x18000a99c  mov     [rdi+40h], r15
0x18000a9a0  mov     [rsi], r14
0x18000a9a3  mov     rbx, [rdi+40h]
0x18000a9a7  test    rbx, rbx
0x18000a9aa  jz      loc_18000AAA8
0x18000a9b0  mov     rdx, [rsi]; DestinationSize
0x18000a9b3  lea     rsi, [rdx+rbx]
0x18000a9b7  cmp     rbx, rsi
0x18000a9ba  jz      short loc_18000A9FA
0x18000a9bc  mov     r8, [r12+38h]; Source
0x18000a9c1  test    r8, r8
0x18000a9c4  jz      short loc_18000A9FA
0x18000a9c6  cmp     [r8], r13b
0x18000a9c9  jz      short loc_18000A9FA
0x18000a9cb  mov     rax, rbp
0x18000a9ce  inc     rax
0x18000a9d1  cmp     [r8+rax], r13b
0x18000a9d5  jnz     short loc_18000A9CE
0x18000a9d7  lea     r14, [rax+1]
0x18000a9db  cmp     rdx, r14
0x18000a9de  jnb     short loc_18000A9E6
0x18000a9e0  mov     [rdi+10h], r13
0x18000a9e4  jmp     short loc_18000AA03
0x18000a9e6  mov     r9, r14; SourceSize
0x18000a9e9  mov     rcx, rbx; Destination
0x18000a9ec  call    memcpy_s
0x18000a9f1  mov     [rdi+10h], rbx
0x18000a9f5  add     rbx, r14
0x18000a9f8  jmp     short loc_18000A9FE
0x18000a9fa  mov     [rdi+10h], r13
0x18000a9fe  cmp     rbx, rsi
0x18000aa01  jz      short loc_18000AA4A
0x18000aa03  mov     r8, [r12+80h]; Source
0x18000aa0b  test    r8, r8
0x18000aa0e  jz      short loc_18000AA4A
0x18000aa10  cmp     [r8], r13b
0x18000aa13  jz      short loc_18000AA4A
0x18000aa15  mov     rax, rbp
0x18000aa18  inc     rax
0x18000aa1b  cmp     [r8+rax], r13b
0x18000aa1f  jnz     short loc_18000AA18
0x18000aa21  mov     rdx, rsi
0x18000aa24  lea     r14, [rax+1]
0x18000aa28  sub     rdx, rbx; DestinationSize
0x18000aa2b  cmp     rdx, r14
0x18000aa2e  jnb     short loc_18000AA36
0x18000aa30  mov     [rdi+20h], r13
0x18000aa34  jmp     short loc_18000AA53
0x18000aa36  mov     r9, r14; SourceSize
0x18000aa39  mov     rcx, rbx; Destination
0x18000aa3c  call    memcpy_s
0x18000aa41  mov     [rdi+20h], rbx
0x18000aa45  add     rbx, r14
0x18000aa48  jmp     short loc_18000AA4E
0x18000aa4a  mov     [rdi+20h], r13
0x18000aa4e  cmp     rbx, rsi
0x18000aa51  jz      short loc_18000AA94
0x18000aa53  mov     r8, [r12+18h]; Source
0x18000aa58  test    r8, r8
0x18000aa5b  jz      short loc_18000AA94
0x18000aa5d  cmp     [r8], r13w
0x18000aa61  jz      short loc_18000AA94
0x18000aa63  inc     rbp
0x18000aa66  cmp     [r8+rbp*2], r13w
0x18000aa6b  jnz     short loc_18000AA63
0x18000aa6d  mov     rdx, rsi
0x18000aa70  lea     r14, ds:2[rbp*2]
0x18000aa78  sub     rdx, rbx; DestinationSize
0x18000aa7b  cmp     rdx, r14
0x18000aa7e  jb      short loc_18000AA94
0x18000aa80  mov     r9, r14; SourceSize
0x18000aa83  mov     rcx, rbx; Destination
0x18000aa86  call    memcpy_s
0x18000aa8b  mov     [rdi+38h], rbx
0x18000aa8f  add     rbx, r14
0x18000aa92  jmp     short loc_18000AA98
0x18000aa94  mov     [rdi+38h], r13
0x18000aa98  sub     rsi, rbx
0x18000aa9b  xor     edx, edx; Val
0x18000aa9d  mov     r8, rsi; Size
0x18000aaa0  mov     rcx, rbx; void *
0x18000aaa3  call    memset_0
0x18000aaa8  add     rsp, 28h
0x18000aaac  pop     r15
0x18000aaae  pop     r14
0x18000aab0  pop     r13
0x18000aab2  pop     r12
0x18000aab4  pop     rdi
0x18000aab5  pop     rsi
0x18000aab6  pop     rbp
0x18000aab7  pop     rbx
0x18000aab8  retn
```
