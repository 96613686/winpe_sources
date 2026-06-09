# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180018e60`
- end: `0x180019079`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018180`

## callees

- `0x180001fd4`
- `0x180006620`
- `0x1800189d8`
- `0x180018e60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f56`

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
0x180018e60  push    rbx
0x180018e62  push    rbp
0x180018e63  push    rsi
0x180018e64  push    rdi
0x180018e65  push    r12
0x180018e67  push    r13
0x180018e69  push    r14
0x180018e6b  push    r15
0x180018e6d  sub     rsp, 28h
0x180018e71  mov     [rcx+4], r8d
0x180018e75  xor     r13d, r13d
0x180018e78  mov     eax, [rdx+8]
0x180018e7b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180018e7f  mov     [rcx+8], eax
0x180018e82  mov     rdi, rcx
0x180018e85  mov     [rcx+10h], r13
0x180018e89  mov     r12, rdx
0x180018e8c  movzx   eax, word ptr [rdx+40h]
0x180018e90  mov     [rcx+18h], ax
0x180018e94  mov     al, [rdx]
0x180018e96  mov     [rcx+1Ah], al
0x180018e99  mov     [rcx+20h], r13
0x180018e9d  mov     rax, [rdx+88h]
0x180018ea4  mov     [rcx+28h], rax
0x180018ea8  mov     rax, [rdx+90h]
0x180018eaf  mov     [rcx+30h], rax
0x180018eb3  mov     [rcx+38h], r13
0x180018eb7  mov     rcx, [rdx+38h]
0x180018ebb  lea     edx, [rbp+2]
0x180018ebe  test    rcx, rcx
0x180018ec1  jnz     short loc_180018EC8
0x180018ec3  mov     r8d, edx
0x180018ec6  jmp     short loc_180018ED8
0x180018ec8  mov     rax, rbp
0x180018ecb  inc     rax
0x180018ece  cmp     [rcx+rax], r13b
0x180018ed2  jnz     short loc_180018ECB
0x180018ed4  lea     r8, [rax+1]; unsigned __int64
0x180018ed8  mov     rcx, [r12+80h]
0x180018ee0  test    rcx, rcx
0x180018ee3  jz      short loc_180018EF5
0x180018ee5  mov     rax, rbp
0x180018ee8  inc     rax
0x180018eeb  cmp     [rcx+rax], r13b
0x180018eef  jnz     short loc_180018EE8
0x180018ef1  lea     rdx, [rax+1]
0x180018ef5  mov     rcx, [r12+18h]
0x180018efa  test    rcx, rcx
0x180018efd  jnz     short loc_180018F04
0x180018eff  lea     eax, [rcx+2]
0x180018f02  jmp     short loc_180018F19
0x180018f04  mov     rax, rbp
0x180018f07  inc     rax
0x180018f0a  cmp     [rcx+rax*2], r13w
0x180018f0f  jnz     short loc_180018F07
0x180018f11  lea     rax, ds:2[rax*2]
0x180018f19  lea     r14, [rdx+rax]
0x180018f1d  add     r14, r8
0x180018f20  lea     rsi, [rdi+48h]
0x180018f24  cmp     [rdi+40h], r13
0x180018f28  jz      short loc_180018F2F
0x180018f2a  cmp     [rsi], r14
0x180018f2d  jnb     short loc_180018F63
0x180018f2f  mov     rdx, r14; dwBytes
0x180018f32  mov     ecx, 8; dwFlags
0x180018f37  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180018f3c  mov     r15, rax
0x180018f3f  test    rax, rax
0x180018f42  jz      short loc_180018F63
0x180018f44  mov     rbx, [rdi+40h]
0x180018f48  call    cs:__imp_GetProcessHeap
0x180018f4e  mov     r8, rbx; lpMem
0x180018f51  xor     edx, edx; dwFlags
0x180018f53  mov     rcx, rax; hHeap
0x180018f56  call    cs:__imp_HeapFree
0x180018f5c  mov     [rdi+40h], r15
0x180018f60  mov     [rsi], r14
0x180018f63  mov     rbx, [rdi+40h]
0x180018f67  test    rbx, rbx
0x180018f6a  jz      loc_180019068
0x180018f70  mov     rdx, [rsi]; DestinationSize
0x180018f73  lea     rsi, [rdx+rbx]
0x180018f77  cmp     rbx, rsi
0x180018f7a  jz      short loc_180018FBA
0x180018f7c  mov     r8, [r12+38h]; Source
0x180018f81  test    r8, r8
0x180018f84  jz      short loc_180018FBA
0x180018f86  cmp     [r8], r13b
0x180018f89  jz      short loc_180018FBA
0x180018f8b  mov     rax, rbp
0x180018f8e  inc     rax
0x180018f91  cmp     [r8+rax], r13b
0x180018f95  jnz     short loc_180018F8E
0x180018f97  lea     r14, [rax+1]
0x180018f9b  cmp     rdx, r14
0x180018f9e  jnb     short loc_180018FA6
0x180018fa0  mov     [rdi+10h], r13
0x180018fa4  jmp     short loc_180018FC3
0x180018fa6  mov     r9, r14; SourceSize
0x180018fa9  mov     rcx, rbx; Destination
0x180018fac  call    memcpy_s
0x180018fb1  mov     [rdi+10h], rbx
0x180018fb5  add     rbx, r14
0x180018fb8  jmp     short loc_180018FBE
0x180018fba  mov     [rdi+10h], r13
0x180018fbe  cmp     rbx, rsi
0x180018fc1  jz      short loc_18001900A
0x180018fc3  mov     r8, [r12+80h]; Source
0x180018fcb  test    r8, r8
0x180018fce  jz      short loc_18001900A
0x180018fd0  cmp     [r8], r13b
0x180018fd3  jz      short loc_18001900A
0x180018fd5  mov     rax, rbp
0x180018fd8  inc     rax
0x180018fdb  cmp     [r8+rax], r13b
0x180018fdf  jnz     short loc_180018FD8
0x180018fe1  mov     rdx, rsi
0x180018fe4  lea     r14, [rax+1]
0x180018fe8  sub     rdx, rbx; DestinationSize
0x180018feb  cmp     rdx, r14
0x180018fee  jnb     short loc_180018FF6
0x180018ff0  mov     [rdi+20h], r13
0x180018ff4  jmp     short loc_180019013
0x180018ff6  mov     r9, r14; SourceSize
0x180018ff9  mov     rcx, rbx; Destination
0x180018ffc  call    memcpy_s
0x180019001  mov     [rdi+20h], rbx
0x180019005  add     rbx, r14
0x180019008  jmp     short loc_18001900E
0x18001900a  mov     [rdi+20h], r13
0x18001900e  cmp     rbx, rsi
0x180019011  jz      short loc_180019054
0x180019013  mov     r8, [r12+18h]; Source
0x180019018  test    r8, r8
0x18001901b  jz      short loc_180019054
0x18001901d  cmp     [r8], r13w
0x180019021  jz      short loc_180019054
0x180019023  inc     rbp
0x180019026  cmp     [r8+rbp*2], r13w
0x18001902b  jnz     short loc_180019023
0x18001902d  mov     rdx, rsi
0x180019030  lea     r14, ds:2[rbp*2]
0x180019038  sub     rdx, rbx; DestinationSize
0x18001903b  cmp     rdx, r14
0x18001903e  jb      short loc_180019054
0x180019040  mov     r9, r14; SourceSize
0x180019043  mov     rcx, rbx; Destination
0x180019046  call    memcpy_s
0x18001904b  mov     [rdi+38h], rbx
0x18001904f  add     rbx, r14
0x180019052  jmp     short loc_180019058
0x180019054  mov     [rdi+38h], r13
0x180019058  sub     rsi, rbx
0x18001905b  xor     edx, edx; Val
0x18001905d  mov     r8, rsi; Size
0x180019060  mov     rcx, rbx; void *
0x180019063  call    memset_0
0x180019068  add     rsp, 28h
0x18001906c  pop     r15
0x18001906e  pop     r14
0x180019070  pop     r13
0x180019072  pop     r12
0x180019074  pop     rdi
0x180019075  pop     rsi
0x180019076  pop     rbp
0x180019077  pop     rbx
0x180019078  retn
```
