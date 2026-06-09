# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c1ac`
- end: `0x14000c3c5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140002fcc`
- `0x140004978`
- `0x14000ac10`
- `0x14000c1ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c294`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c2a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c2a2`

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
0x14000c1ac  push    rbx
0x14000c1ae  push    rbp
0x14000c1af  push    rsi
0x14000c1b0  push    rdi
0x14000c1b1  push    r12
0x14000c1b3  push    r13
0x14000c1b5  push    r14
0x14000c1b7  push    r15
0x14000c1b9  sub     rsp, 28h
0x14000c1bd  mov     [rcx+4], r8d
0x14000c1c1  xor     r13d, r13d
0x14000c1c4  mov     eax, [rdx+8]
0x14000c1c7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000c1cb  mov     [rcx+8], eax
0x14000c1ce  mov     rdi, rcx
0x14000c1d1  mov     [rcx+10h], r13
0x14000c1d5  mov     r12, rdx
0x14000c1d8  movzx   eax, word ptr [rdx+40h]
0x14000c1dc  mov     [rcx+18h], ax
0x14000c1e0  mov     al, [rdx]
0x14000c1e2  mov     [rcx+1Ah], al
0x14000c1e5  mov     [rcx+20h], r13
0x14000c1e9  mov     rax, [rdx+88h]
0x14000c1f0  mov     [rcx+28h], rax
0x14000c1f4  mov     rax, [rdx+90h]
0x14000c1fb  mov     [rcx+30h], rax
0x14000c1ff  mov     [rcx+38h], r13
0x14000c203  mov     rcx, [rdx+38h]
0x14000c207  lea     edx, [rbp+2]
0x14000c20a  test    rcx, rcx
0x14000c20d  jnz     short loc_14000C214
0x14000c20f  mov     r8d, edx
0x14000c212  jmp     short loc_14000C224
0x14000c214  mov     rax, rbp
0x14000c217  inc     rax
0x14000c21a  cmp     [rcx+rax], r13b
0x14000c21e  jnz     short loc_14000C217
0x14000c220  lea     r8, [rax+1]; unsigned __int64
0x14000c224  mov     rcx, [r12+80h]
0x14000c22c  test    rcx, rcx
0x14000c22f  jz      short loc_14000C241
0x14000c231  mov     rax, rbp
0x14000c234  inc     rax
0x14000c237  cmp     [rcx+rax], r13b
0x14000c23b  jnz     short loc_14000C234
0x14000c23d  lea     rdx, [rax+1]
0x14000c241  mov     rcx, [r12+18h]
0x14000c246  test    rcx, rcx
0x14000c249  jnz     short loc_14000C250
0x14000c24b  lea     eax, [rcx+2]
0x14000c24e  jmp     short loc_14000C265
0x14000c250  mov     rax, rbp
0x14000c253  inc     rax
0x14000c256  cmp     [rcx+rax*2], r13w
0x14000c25b  jnz     short loc_14000C253
0x14000c25d  lea     rax, ds:2[rax*2]
0x14000c265  lea     r14, [rdx+rax]
0x14000c269  add     r14, r8
0x14000c26c  lea     rsi, [rdi+48h]
0x14000c270  cmp     [rdi+40h], r13
0x14000c274  jz      short loc_14000C27B
0x14000c276  cmp     [rsi], r14
0x14000c279  jnb     short loc_14000C2AF
0x14000c27b  mov     rdx, r14; dwBytes
0x14000c27e  mov     ecx, 8; dwFlags
0x14000c283  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c288  mov     r15, rax
0x14000c28b  test    rax, rax
0x14000c28e  jz      short loc_14000C2AF
0x14000c290  mov     rbx, [rdi+40h]
0x14000c294  call    cs:__imp_GetProcessHeap
0x14000c29a  mov     r8, rbx; lpMem
0x14000c29d  xor     edx, edx; dwFlags
0x14000c29f  mov     rcx, rax; hHeap
0x14000c2a2  call    cs:__imp_HeapFree
0x14000c2a8  mov     [rdi+40h], r15
0x14000c2ac  mov     [rsi], r14
0x14000c2af  mov     rbx, [rdi+40h]
0x14000c2b3  test    rbx, rbx
0x14000c2b6  jz      loc_14000C3B4
0x14000c2bc  mov     rdx, [rsi]; DestinationSize
0x14000c2bf  lea     rsi, [rdx+rbx]
0x14000c2c3  cmp     rbx, rsi
0x14000c2c6  jz      short loc_14000C306
0x14000c2c8  mov     r8, [r12+38h]; Source
0x14000c2cd  test    r8, r8
0x14000c2d0  jz      short loc_14000C306
0x14000c2d2  cmp     [r8], r13b
0x14000c2d5  jz      short loc_14000C306
0x14000c2d7  mov     rax, rbp
0x14000c2da  inc     rax
0x14000c2dd  cmp     [r8+rax], r13b
0x14000c2e1  jnz     short loc_14000C2DA
0x14000c2e3  lea     r14, [rax+1]
0x14000c2e7  cmp     rdx, r14
0x14000c2ea  jnb     short loc_14000C2F2
0x14000c2ec  mov     [rdi+10h], r13
0x14000c2f0  jmp     short loc_14000C30F
0x14000c2f2  mov     r9, r14; SourceSize
0x14000c2f5  mov     rcx, rbx; Destination
0x14000c2f8  call    memcpy_s
0x14000c2fd  mov     [rdi+10h], rbx
0x14000c301  add     rbx, r14
0x14000c304  jmp     short loc_14000C30A
0x14000c306  mov     [rdi+10h], r13
0x14000c30a  cmp     rbx, rsi
0x14000c30d  jz      short loc_14000C356
0x14000c30f  mov     r8, [r12+80h]; Source
0x14000c317  test    r8, r8
0x14000c31a  jz      short loc_14000C356
0x14000c31c  cmp     [r8], r13b
0x14000c31f  jz      short loc_14000C356
0x14000c321  mov     rax, rbp
0x14000c324  inc     rax
0x14000c327  cmp     [r8+rax], r13b
0x14000c32b  jnz     short loc_14000C324
0x14000c32d  mov     rdx, rsi
0x14000c330  lea     r14, [rax+1]
0x14000c334  sub     rdx, rbx; DestinationSize
0x14000c337  cmp     rdx, r14
0x14000c33a  jnb     short loc_14000C342
0x14000c33c  mov     [rdi+20h], r13
0x14000c340  jmp     short loc_14000C35F
0x14000c342  mov     r9, r14; SourceSize
0x14000c345  mov     rcx, rbx; Destination
0x14000c348  call    memcpy_s
0x14000c34d  mov     [rdi+20h], rbx
0x14000c351  add     rbx, r14
0x14000c354  jmp     short loc_14000C35A
0x14000c356  mov     [rdi+20h], r13
0x14000c35a  cmp     rbx, rsi
0x14000c35d  jz      short loc_14000C3A0
0x14000c35f  mov     r8, [r12+18h]; Source
0x14000c364  test    r8, r8
0x14000c367  jz      short loc_14000C3A0
0x14000c369  cmp     [r8], r13w
0x14000c36d  jz      short loc_14000C3A0
0x14000c36f  inc     rbp
0x14000c372  cmp     [r8+rbp*2], r13w
0x14000c377  jnz     short loc_14000C36F
0x14000c379  mov     rdx, rsi
0x14000c37c  lea     r14, ds:2[rbp*2]
0x14000c384  sub     rdx, rbx; DestinationSize
0x14000c387  cmp     rdx, r14
0x14000c38a  jb      short loc_14000C3A0
0x14000c38c  mov     r9, r14; SourceSize
0x14000c38f  mov     rcx, rbx; Destination
0x14000c392  call    memcpy_s
0x14000c397  mov     [rdi+38h], rbx
0x14000c39b  add     rbx, r14
0x14000c39e  jmp     short loc_14000C3A4
0x14000c3a0  mov     [rdi+38h], r13
0x14000c3a4  sub     rsi, rbx
0x14000c3a7  xor     edx, edx; Val
0x14000c3a9  mov     r8, rsi; Size
0x14000c3ac  mov     rcx, rbx; void *
0x14000c3af  call    memset_0
0x14000c3b4  add     rsp, 28h
0x14000c3b8  pop     r15
0x14000c3ba  pop     r14
0x14000c3bc  pop     r13
0x14000c3be  pop     r12
0x14000c3c0  pop     rdi
0x14000c3c1  pop     rsi
0x14000c3c2  pop     rbp
0x14000c3c3  pop     rbx
0x14000c3c4  retn
```
