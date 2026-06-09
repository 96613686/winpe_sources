# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180027de8`
- end: `0x18002800e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `550`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800254e0`

## callees

- `0x180002938`
- `0x180026880`
- `0x180027de8`
- `0x1800297d0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180027ed0`
- `KERNEL32!GetProcessHeap` at `0x180027ed0`
- `KERNEL32!HeapFree` at `0x180027ee4`
- `KERNEL32!HeapFree` at `0x180027ee4`

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
0x180027de8  push    rbx
0x180027dea  push    rbp
0x180027deb  push    rsi
0x180027dec  push    rdi
0x180027ded  push    r12
0x180027def  push    r13
0x180027df1  push    r14
0x180027df3  push    r15
0x180027df5  sub     rsp, 28h
0x180027df9  mov     [rcx+4], r8d
0x180027dfd  xor     r13d, r13d
0x180027e00  mov     eax, [rdx+8]
0x180027e03  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180027e07  mov     [rcx+8], eax
0x180027e0a  mov     rdi, rcx
0x180027e0d  mov     [rcx+10h], r13
0x180027e11  mov     r12, rdx
0x180027e14  movzx   eax, word ptr [rdx+40h]
0x180027e18  mov     [rcx+18h], ax
0x180027e1c  mov     al, [rdx]
0x180027e1e  mov     [rcx+1Ah], al
0x180027e21  mov     [rcx+20h], r13
0x180027e25  mov     rax, [rdx+88h]
0x180027e2c  mov     [rcx+28h], rax
0x180027e30  mov     rax, [rdx+90h]
0x180027e37  mov     [rcx+30h], rax
0x180027e3b  mov     [rcx+38h], r13
0x180027e3f  mov     rcx, [rdx+38h]
0x180027e43  lea     edx, [rbp+2]
0x180027e46  test    rcx, rcx
0x180027e49  jnz     short loc_180027E50
0x180027e4b  mov     r8d, edx
0x180027e4e  jmp     short loc_180027E60
0x180027e50  mov     rax, rbp
0x180027e53  inc     rax
0x180027e56  cmp     [rcx+rax], r13b
0x180027e5a  jnz     short loc_180027E53
0x180027e5c  lea     r8, [rax+1]; unsigned __int64
0x180027e60  mov     rcx, [r12+80h]
0x180027e68  test    rcx, rcx
0x180027e6b  jz      short loc_180027E7D
0x180027e6d  mov     rax, rbp
0x180027e70  inc     rax
0x180027e73  cmp     [rcx+rax], r13b
0x180027e77  jnz     short loc_180027E70
0x180027e79  lea     rdx, [rax+1]
0x180027e7d  mov     rcx, [r12+18h]
0x180027e82  test    rcx, rcx
0x180027e85  jnz     short loc_180027E8C
0x180027e87  lea     eax, [rcx+2]
0x180027e8a  jmp     short loc_180027EA1
0x180027e8c  mov     rax, rbp
0x180027e8f  inc     rax
0x180027e92  cmp     [rcx+rax*2], r13w
0x180027e97  jnz     short loc_180027E8F
0x180027e99  lea     rax, ds:2[rax*2]
0x180027ea1  lea     r14, [rdx+rax]
0x180027ea5  add     r14, r8
0x180027ea8  lea     rsi, [rdi+48h]
0x180027eac  cmp     [rdi+40h], r13
0x180027eb0  jz      short loc_180027EB7
0x180027eb2  cmp     [rsi], r14
0x180027eb5  jnb     short loc_180027EF7
0x180027eb7  mov     rdx, r14; dwBytes
0x180027eba  mov     ecx, 8; dwFlags
0x180027ebf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027ec4  mov     r15, rax
0x180027ec7  test    rax, rax
0x180027eca  jz      short loc_180027EF7
0x180027ecc  mov     rbx, [rdi+40h]
0x180027ed0  call    cs:__imp_GetProcessHeap
0x180027ed7  nop     dword ptr [rax+rax+00h]
0x180027edc  mov     r8, rbx; lpMem
0x180027edf  xor     edx, edx; dwFlags
0x180027ee1  mov     rcx, rax; hHeap
0x180027ee4  call    cs:__imp_HeapFree
0x180027eeb  nop     dword ptr [rax+rax+00h]
0x180027ef0  mov     [rdi+40h], r15
0x180027ef4  mov     [rsi], r14
0x180027ef7  mov     rbx, [rdi+40h]
0x180027efb  test    rbx, rbx
0x180027efe  jz      loc_180027FFC
0x180027f04  mov     rdx, [rsi]; DestinationSize
0x180027f07  lea     rsi, [rdx+rbx]
0x180027f0b  cmp     rbx, rsi
0x180027f0e  jz      short loc_180027F4E
0x180027f10  mov     r8, [r12+38h]; Source
0x180027f15  test    r8, r8
0x180027f18  jz      short loc_180027F4E
0x180027f1a  cmp     [r8], r13b
0x180027f1d  jz      short loc_180027F4E
0x180027f1f  mov     rax, rbp
0x180027f22  inc     rax
0x180027f25  cmp     [r8+rax], r13b
0x180027f29  jnz     short loc_180027F22
0x180027f2b  lea     r14, [rax+1]
0x180027f2f  cmp     rdx, r14
0x180027f32  jnb     short loc_180027F3A
0x180027f34  mov     [rdi+10h], r13
0x180027f38  jmp     short loc_180027F57
0x180027f3a  mov     r9, r14; SourceSize
0x180027f3d  mov     rcx, rbx; Destination
0x180027f40  call    memcpy_s_0
0x180027f45  mov     [rdi+10h], rbx
0x180027f49  add     rbx, r14
0x180027f4c  jmp     short loc_180027F52
0x180027f4e  mov     [rdi+10h], r13
0x180027f52  cmp     rbx, rsi
0x180027f55  jz      short loc_180027F9E
0x180027f57  mov     r8, [r12+80h]; Source
0x180027f5f  test    r8, r8
0x180027f62  jz      short loc_180027F9E
0x180027f64  cmp     [r8], r13b
0x180027f67  jz      short loc_180027F9E
0x180027f69  mov     rax, rbp
0x180027f6c  inc     rax
0x180027f6f  cmp     [r8+rax], r13b
0x180027f73  jnz     short loc_180027F6C
0x180027f75  mov     rdx, rsi
0x180027f78  lea     r14, [rax+1]
0x180027f7c  sub     rdx, rbx; DestinationSize
0x180027f7f  cmp     rdx, r14
0x180027f82  jnb     short loc_180027F8A
0x180027f84  mov     [rdi+20h], r13
0x180027f88  jmp     short loc_180027FA7
0x180027f8a  mov     r9, r14; SourceSize
0x180027f8d  mov     rcx, rbx; Destination
0x180027f90  call    memcpy_s_0
0x180027f95  mov     [rdi+20h], rbx
0x180027f99  add     rbx, r14
0x180027f9c  jmp     short loc_180027FA2
0x180027f9e  mov     [rdi+20h], r13
0x180027fa2  cmp     rbx, rsi
0x180027fa5  jz      short loc_180027FE8
0x180027fa7  mov     r8, [r12+18h]; Source
0x180027fac  test    r8, r8
0x180027faf  jz      short loc_180027FE8
0x180027fb1  cmp     [r8], r13w
0x180027fb5  jz      short loc_180027FE8
0x180027fb7  inc     rbp
0x180027fba  cmp     [r8+rbp*2], r13w
0x180027fbf  jnz     short loc_180027FB7
0x180027fc1  mov     rdx, rsi
0x180027fc4  lea     r14, ds:2[rbp*2]
0x180027fcc  sub     rdx, rbx; DestinationSize
0x180027fcf  cmp     rdx, r14
0x180027fd2  jb      short loc_180027FE8
0x180027fd4  mov     r9, r14; SourceSize
0x180027fd7  mov     rcx, rbx; Destination
0x180027fda  call    memcpy_s_0
0x180027fdf  mov     [rdi+38h], rbx
0x180027fe3  add     rbx, r14
0x180027fe6  jmp     short loc_180027FEC
0x180027fe8  mov     [rdi+38h], r13
0x180027fec  sub     rsi, rbx
0x180027fef  xor     edx, edx; Val
0x180027ff1  mov     r8, rsi; Size
0x180027ff4  mov     rcx, rbx; void *
0x180027ff7  call    memset_0
0x180027ffc  add     rsp, 28h
0x180028000  pop     r15
0x180028002  pop     r14
0x180028004  pop     r13
0x180028006  pop     r12
0x180028008  pop     rdi
0x180028009  pop     rsi
0x18002800a  pop     rbp
0x18002800b  pop     rbx
0x18002800c  retn
```
