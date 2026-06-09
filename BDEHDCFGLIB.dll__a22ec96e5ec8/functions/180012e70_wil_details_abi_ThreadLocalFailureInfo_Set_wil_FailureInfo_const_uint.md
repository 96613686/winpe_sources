# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180012e70`
- end: `0x18001308c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011a90`

## callees

- `0x180012b30`
- `0x180012e70`
- `0x18001358e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012fbc`
- `msvcrt!memcpy_s` at `0x18001300d`
- `msvcrt!memcpy_s` at `0x180013058`
- `msvcrt!memcpy_s` at `0x180012fbc`
- `msvcrt!memcpy_s` at `0x18001300d`
- `msvcrt!memcpy_s` at `0x180013058`
- `KERNEL32!GetProcessHeap` at `0x180012f58`
- `KERNEL32!GetProcessHeap` at `0x180012f58`
- `KERNEL32!HeapFree` at `0x180012f66`
- `KERNEL32!HeapFree` at `0x180012f66`

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
0x180012e70  push    rbx
0x180012e72  push    rbp
0x180012e73  push    rsi
0x180012e74  push    rdi
0x180012e75  push    r12
0x180012e77  push    r13
0x180012e79  push    r14
0x180012e7b  push    r15
0x180012e7d  sub     rsp, 28h
0x180012e81  mov     [rcx+4], r8d
0x180012e85  xor     r13d, r13d
0x180012e88  mov     eax, [rdx+8]
0x180012e8b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180012e8f  mov     [rcx+8], eax
0x180012e92  mov     rdi, rcx
0x180012e95  mov     [rcx+10h], r13
0x180012e99  mov     r12, rdx
0x180012e9c  movzx   eax, word ptr [rdx+40h]
0x180012ea0  mov     [rcx+18h], ax
0x180012ea4  mov     al, [rdx]
0x180012ea6  mov     [rcx+1Ah], al
0x180012ea9  mov     [rcx+20h], r13
0x180012ead  mov     rax, [rdx+88h]
0x180012eb4  mov     [rcx+28h], rax
0x180012eb8  mov     rax, [rdx+90h]
0x180012ebf  mov     [rcx+30h], rax
0x180012ec3  mov     [rcx+38h], r13
0x180012ec7  mov     rcx, [rdx+38h]
0x180012ecb  lea     edx, [rbp+2]
0x180012ece  test    rcx, rcx
0x180012ed1  jnz     short loc_180012ED8
0x180012ed3  mov     r8d, edx
0x180012ed6  jmp     short loc_180012EE8
0x180012ed8  mov     rax, rbp
0x180012edb  inc     rax
0x180012ede  cmp     [rcx+rax], r13b
0x180012ee2  jnz     short loc_180012EDB
0x180012ee4  lea     r8, [rax+1]; unsigned __int64
0x180012ee8  mov     rcx, [r12+80h]
0x180012ef0  test    rcx, rcx
0x180012ef3  jz      short loc_180012F05
0x180012ef5  mov     rax, rbp
0x180012ef8  inc     rax
0x180012efb  cmp     [rcx+rax], r13b
0x180012eff  jnz     short loc_180012EF8
0x180012f01  lea     rdx, [rax+1]
0x180012f05  mov     rcx, [r12+18h]
0x180012f0a  test    rcx, rcx
0x180012f0d  jnz     short loc_180012F14
0x180012f0f  lea     eax, [rcx+2]
0x180012f12  jmp     short loc_180012F29
0x180012f14  mov     rax, rbp
0x180012f17  inc     rax
0x180012f1a  cmp     [rcx+rax*2], r13w
0x180012f1f  jnz     short loc_180012F17
0x180012f21  lea     rax, ds:2[rax*2]
0x180012f29  lea     r14, [rdx+rax]
0x180012f2d  add     r14, r8
0x180012f30  lea     rsi, [rdi+48h]
0x180012f34  cmp     [rdi+40h], r13
0x180012f38  jz      short loc_180012F3F
0x180012f3a  cmp     [rsi], r14
0x180012f3d  jnb     short loc_180012F73
0x180012f3f  mov     rdx, r14; dwBytes
0x180012f42  mov     ecx, 8; dwFlags
0x180012f47  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012f4c  mov     r15, rax
0x180012f4f  test    rax, rax
0x180012f52  jz      short loc_180012F73
0x180012f54  mov     rbx, [rdi+40h]
0x180012f58  call    cs:__imp_GetProcessHeap
0x180012f5e  mov     r8, rbx; lpMem
0x180012f61  xor     edx, edx; dwFlags
0x180012f63  mov     rcx, rax; hHeap
0x180012f66  call    cs:__imp_HeapFree
0x180012f6c  mov     [rdi+40h], r15
0x180012f70  mov     [rsi], r14
0x180012f73  mov     rbx, [rdi+40h]
0x180012f77  test    rbx, rbx
0x180012f7a  jz      loc_18001307B
0x180012f80  mov     rdx, [rsi]; DestinationSize
0x180012f83  lea     rsi, [rdx+rbx]
0x180012f87  cmp     rbx, rsi
0x180012f8a  jz      short loc_180012FCB
0x180012f8c  mov     r8, [r12+38h]; Source
0x180012f91  test    r8, r8
0x180012f94  jz      short loc_180012FCB
0x180012f96  cmp     [r8], r13b
0x180012f99  jz      short loc_180012FCB
0x180012f9b  mov     rax, rbp
0x180012f9e  inc     rax
0x180012fa1  cmp     [r8+rax], r13b
0x180012fa5  jnz     short loc_180012F9E
0x180012fa7  lea     r14, [rax+1]
0x180012fab  cmp     rdx, r14
0x180012fae  jnb     short loc_180012FB6
0x180012fb0  mov     [rdi+10h], r13
0x180012fb4  jmp     short loc_180012FD4
0x180012fb6  mov     r9, r14; SourceSize
0x180012fb9  mov     rcx, rbx; Destination
0x180012fbc  call    cs:__imp_memcpy_s
0x180012fc2  mov     [rdi+10h], rbx
0x180012fc6  add     rbx, r14
0x180012fc9  jmp     short loc_180012FCF
0x180012fcb  mov     [rdi+10h], r13
0x180012fcf  cmp     rbx, rsi
0x180012fd2  jz      short loc_18001301C
0x180012fd4  mov     r8, [r12+80h]; Source
0x180012fdc  test    r8, r8
0x180012fdf  jz      short loc_18001301C
0x180012fe1  cmp     [r8], r13b
0x180012fe4  jz      short loc_18001301C
0x180012fe6  mov     rax, rbp
0x180012fe9  inc     rax
0x180012fec  cmp     [r8+rax], r13b
0x180012ff0  jnz     short loc_180012FE9
0x180012ff2  mov     rdx, rsi
0x180012ff5  lea     r14, [rax+1]
0x180012ff9  sub     rdx, rbx; DestinationSize
0x180012ffc  cmp     rdx, r14
0x180012fff  jnb     short loc_180013007
0x180013001  mov     [rdi+20h], r13
0x180013005  jmp     short loc_180013025
0x180013007  mov     r9, r14; SourceSize
0x18001300a  mov     rcx, rbx; Destination
0x18001300d  call    cs:__imp_memcpy_s
0x180013013  mov     [rdi+20h], rbx
0x180013017  add     rbx, r14
0x18001301a  jmp     short loc_180013020
0x18001301c  mov     [rdi+20h], r13
0x180013020  cmp     rbx, rsi
0x180013023  jz      short loc_180013067
0x180013025  mov     r8, [r12+18h]; Source
0x18001302a  test    r8, r8
0x18001302d  jz      short loc_180013067
0x18001302f  cmp     [r8], r13w
0x180013033  jz      short loc_180013067
0x180013035  inc     rbp
0x180013038  cmp     [r8+rbp*2], r13w
0x18001303d  jnz     short loc_180013035
0x18001303f  mov     rdx, rsi
0x180013042  lea     r14, ds:2[rbp*2]
0x18001304a  sub     rdx, rbx; DestinationSize
0x18001304d  cmp     rdx, r14
0x180013050  jb      short loc_180013067
0x180013052  mov     r9, r14; SourceSize
0x180013055  mov     rcx, rbx; Destination
0x180013058  call    cs:__imp_memcpy_s
0x18001305e  mov     [rdi+38h], rbx
0x180013062  add     rbx, r14
0x180013065  jmp     short loc_18001306B
0x180013067  mov     [rdi+38h], r13
0x18001306b  sub     rsi, rbx
0x18001306e  xor     edx, edx; Val
0x180013070  mov     r8, rsi; Size
0x180013073  mov     rcx, rbx; void *
0x180013076  call    memset_0
0x18001307b  add     rsp, 28h
0x18001307f  pop     r15
0x180013081  pop     r14
0x180013083  pop     r13
0x180013085  pop     r12
0x180013087  pop     rdi
0x180013088  pop     rsi
0x180013089  pop     rbp
0x18001308a  pop     rbx
0x18001308b  retn
```
