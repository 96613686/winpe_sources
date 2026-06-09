# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140004970`
- end: `0x140004b89`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003420`

## callees

- `0x140001e7e`
- `0x140004478`
- `0x140004970`
- `0x140005958`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004a66`
- `KERNEL32!HeapFree` at `0x140004a66`
- `KERNEL32!GetProcessHeap` at `0x140004a58`
- `KERNEL32!GetProcessHeap` at `0x140004a58`

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
0x140004970  push    rbx
0x140004972  push    rbp
0x140004973  push    rsi
0x140004974  push    rdi
0x140004975  push    r12
0x140004977  push    r13
0x140004979  push    r14
0x14000497b  push    r15
0x14000497d  sub     rsp, 28h
0x140004981  mov     [rcx+4], r8d
0x140004985  xor     r13d, r13d
0x140004988  mov     eax, [rdx+8]
0x14000498b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000498f  mov     [rcx+8], eax
0x140004992  mov     rdi, rcx
0x140004995  mov     [rcx+10h], r13
0x140004999  mov     r12, rdx
0x14000499c  movzx   eax, word ptr [rdx+40h]
0x1400049a0  mov     [rcx+18h], ax
0x1400049a4  mov     al, [rdx]
0x1400049a6  mov     [rcx+1Ah], al
0x1400049a9  mov     [rcx+20h], r13
0x1400049ad  mov     rax, [rdx+88h]
0x1400049b4  mov     [rcx+28h], rax
0x1400049b8  mov     rax, [rdx+90h]
0x1400049bf  mov     [rcx+30h], rax
0x1400049c3  mov     [rcx+38h], r13
0x1400049c7  mov     rcx, [rdx+38h]
0x1400049cb  lea     edx, [rbp+2]
0x1400049ce  test    rcx, rcx
0x1400049d1  jnz     short loc_1400049D8
0x1400049d3  mov     r8d, edx
0x1400049d6  jmp     short loc_1400049E8
0x1400049d8  mov     rax, rbp
0x1400049db  inc     rax
0x1400049de  cmp     [rcx+rax], r13b
0x1400049e2  jnz     short loc_1400049DB
0x1400049e4  lea     r8, [rax+1]; unsigned __int64
0x1400049e8  mov     rcx, [r12+80h]
0x1400049f0  test    rcx, rcx
0x1400049f3  jz      short loc_140004A05
0x1400049f5  mov     rax, rbp
0x1400049f8  inc     rax
0x1400049fb  cmp     [rcx+rax], r13b
0x1400049ff  jnz     short loc_1400049F8
0x140004a01  lea     rdx, [rax+1]
0x140004a05  mov     rcx, [r12+18h]
0x140004a0a  test    rcx, rcx
0x140004a0d  jnz     short loc_140004A14
0x140004a0f  lea     eax, [rcx+2]
0x140004a12  jmp     short loc_140004A29
0x140004a14  mov     rax, rbp
0x140004a17  inc     rax
0x140004a1a  cmp     [rcx+rax*2], r13w
0x140004a1f  jnz     short loc_140004A17
0x140004a21  lea     rax, ds:2[rax*2]
0x140004a29  lea     r14, [rdx+rax]
0x140004a2d  add     r14, r8
0x140004a30  lea     rsi, [rdi+48h]
0x140004a34  cmp     [rdi+40h], r13
0x140004a38  jz      short loc_140004A3F
0x140004a3a  cmp     [rsi], r14
0x140004a3d  jnb     short loc_140004A73
0x140004a3f  mov     rdx, r14; dwBytes
0x140004a42  mov     ecx, 8; dwFlags
0x140004a47  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004a4c  mov     r15, rax
0x140004a4f  test    rax, rax
0x140004a52  jz      short loc_140004A73
0x140004a54  mov     rbx, [rdi+40h]
0x140004a58  call    cs:__imp_GetProcessHeap
0x140004a5e  mov     r8, rbx; lpMem
0x140004a61  xor     edx, edx; dwFlags
0x140004a63  mov     rcx, rax; hHeap
0x140004a66  call    cs:__imp_HeapFree
0x140004a6c  mov     [rdi+40h], r15
0x140004a70  mov     [rsi], r14
0x140004a73  mov     rbx, [rdi+40h]
0x140004a77  test    rbx, rbx
0x140004a7a  jz      loc_140004B78
0x140004a80  mov     rdx, [rsi]; DestinationSize
0x140004a83  lea     rsi, [rdx+rbx]
0x140004a87  cmp     rbx, rsi
0x140004a8a  jz      short loc_140004ACA
0x140004a8c  mov     r8, [r12+38h]; Source
0x140004a91  test    r8, r8
0x140004a94  jz      short loc_140004ACA
0x140004a96  cmp     [r8], r13b
0x140004a99  jz      short loc_140004ACA
0x140004a9b  mov     rax, rbp
0x140004a9e  inc     rax
0x140004aa1  cmp     [r8+rax], r13b
0x140004aa5  jnz     short loc_140004A9E
0x140004aa7  lea     r14, [rax+1]
0x140004aab  cmp     rdx, r14
0x140004aae  jnb     short loc_140004AB6
0x140004ab0  mov     [rdi+10h], r13
0x140004ab4  jmp     short loc_140004AD3
0x140004ab6  mov     r9, r14; SourceSize
0x140004ab9  mov     rcx, rbx; Destination
0x140004abc  call    memcpy_s
0x140004ac1  mov     [rdi+10h], rbx
0x140004ac5  add     rbx, r14
0x140004ac8  jmp     short loc_140004ACE
0x140004aca  mov     [rdi+10h], r13
0x140004ace  cmp     rbx, rsi
0x140004ad1  jz      short loc_140004B1A
0x140004ad3  mov     r8, [r12+80h]; Source
0x140004adb  test    r8, r8
0x140004ade  jz      short loc_140004B1A
0x140004ae0  cmp     [r8], r13b
0x140004ae3  jz      short loc_140004B1A
0x140004ae5  mov     rax, rbp
0x140004ae8  inc     rax
0x140004aeb  cmp     [r8+rax], r13b
0x140004aef  jnz     short loc_140004AE8
0x140004af1  mov     rdx, rsi
0x140004af4  lea     r14, [rax+1]
0x140004af8  sub     rdx, rbx; DestinationSize
0x140004afb  cmp     rdx, r14
0x140004afe  jnb     short loc_140004B06
0x140004b00  mov     [rdi+20h], r13
0x140004b04  jmp     short loc_140004B23
0x140004b06  mov     r9, r14; SourceSize
0x140004b09  mov     rcx, rbx; Destination
0x140004b0c  call    memcpy_s
0x140004b11  mov     [rdi+20h], rbx
0x140004b15  add     rbx, r14
0x140004b18  jmp     short loc_140004B1E
0x140004b1a  mov     [rdi+20h], r13
0x140004b1e  cmp     rbx, rsi
0x140004b21  jz      short loc_140004B64
0x140004b23  mov     r8, [r12+18h]; Source
0x140004b28  test    r8, r8
0x140004b2b  jz      short loc_140004B64
0x140004b2d  cmp     [r8], r13w
0x140004b31  jz      short loc_140004B64
0x140004b33  inc     rbp
0x140004b36  cmp     [r8+rbp*2], r13w
0x140004b3b  jnz     short loc_140004B33
0x140004b3d  mov     rdx, rsi
0x140004b40  lea     r14, ds:2[rbp*2]
0x140004b48  sub     rdx, rbx; DestinationSize
0x140004b4b  cmp     rdx, r14
0x140004b4e  jb      short loc_140004B64
0x140004b50  mov     r9, r14; SourceSize
0x140004b53  mov     rcx, rbx; Destination
0x140004b56  call    memcpy_s
0x140004b5b  mov     [rdi+38h], rbx
0x140004b5f  add     rbx, r14
0x140004b62  jmp     short loc_140004B68
0x140004b64  mov     [rdi+38h], r13
0x140004b68  sub     rsi, rbx
0x140004b6b  xor     edx, edx; Val
0x140004b6d  mov     r8, rsi; Size
0x140004b70  mov     rcx, rbx; void *
0x140004b73  call    memset_0
0x140004b78  add     rsp, 28h
0x140004b7c  pop     r15
0x140004b7e  pop     r14
0x140004b80  pop     r13
0x140004b82  pop     r12
0x140004b84  pop     rdi
0x140004b85  pop     rsi
0x140004b86  pop     rbp
0x140004b87  pop     rbx
0x140004b88  retn
```
