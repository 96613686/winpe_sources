# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006968`
- end: `0x180006b81`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050a0`

## callees

- `0x1800020d0`
- `0x18000627c`
- `0x180006968`
- `0x1800080e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a50`

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
0x180006968  push    rbx
0x18000696a  push    rbp
0x18000696b  push    rsi
0x18000696c  push    rdi
0x18000696d  push    r12
0x18000696f  push    r13
0x180006971  push    r14
0x180006973  push    r15
0x180006975  sub     rsp, 28h
0x180006979  mov     [rcx+4], r8d
0x18000697d  xor     r13d, r13d
0x180006980  mov     eax, [rdx+8]
0x180006983  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006987  mov     [rcx+8], eax
0x18000698a  mov     rdi, rcx
0x18000698d  mov     [rcx+10h], r13
0x180006991  mov     r12, rdx
0x180006994  movzx   eax, word ptr [rdx+40h]
0x180006998  mov     [rcx+18h], ax
0x18000699c  mov     al, [rdx]
0x18000699e  mov     [rcx+1Ah], al
0x1800069a1  mov     [rcx+20h], r13
0x1800069a5  mov     rax, [rdx+88h]
0x1800069ac  mov     [rcx+28h], rax
0x1800069b0  mov     rax, [rdx+90h]
0x1800069b7  mov     [rcx+30h], rax
0x1800069bb  mov     [rcx+38h], r13
0x1800069bf  mov     rcx, [rdx+38h]
0x1800069c3  lea     edx, [rbp+2]
0x1800069c6  test    rcx, rcx
0x1800069c9  jnz     short loc_1800069D0
0x1800069cb  mov     r8d, edx
0x1800069ce  jmp     short loc_1800069E0
0x1800069d0  mov     rax, rbp
0x1800069d3  inc     rax
0x1800069d6  cmp     [rcx+rax], r13b
0x1800069da  jnz     short loc_1800069D3
0x1800069dc  lea     r8, [rax+1]; unsigned __int64
0x1800069e0  mov     rcx, [r12+80h]
0x1800069e8  test    rcx, rcx
0x1800069eb  jz      short loc_1800069FD
0x1800069ed  mov     rax, rbp
0x1800069f0  inc     rax
0x1800069f3  cmp     [rcx+rax], r13b
0x1800069f7  jnz     short loc_1800069F0
0x1800069f9  lea     rdx, [rax+1]
0x1800069fd  mov     rcx, [r12+18h]
0x180006a02  test    rcx, rcx
0x180006a05  jnz     short loc_180006A0C
0x180006a07  lea     eax, [rcx+2]
0x180006a0a  jmp     short loc_180006A21
0x180006a0c  mov     rax, rbp
0x180006a0f  inc     rax
0x180006a12  cmp     [rcx+rax*2], r13w
0x180006a17  jnz     short loc_180006A0F
0x180006a19  lea     rax, ds:2[rax*2]
0x180006a21  lea     r14, [rdx+rax]
0x180006a25  add     r14, r8
0x180006a28  lea     rsi, [rdi+48h]
0x180006a2c  cmp     [rdi+40h], r13
0x180006a30  jz      short loc_180006A37
0x180006a32  cmp     [rsi], r14
0x180006a35  jnb     short loc_180006A6B
0x180006a37  mov     rdx, r14; dwBytes
0x180006a3a  mov     ecx, 8; dwFlags
0x180006a3f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a44  mov     r15, rax
0x180006a47  test    rax, rax
0x180006a4a  jz      short loc_180006A6B
0x180006a4c  mov     rbx, [rdi+40h]
0x180006a50  call    cs:__imp_GetProcessHeap
0x180006a56  mov     r8, rbx; lpMem
0x180006a59  xor     edx, edx; dwFlags
0x180006a5b  mov     rcx, rax; hHeap
0x180006a5e  call    cs:__imp_HeapFree
0x180006a64  mov     [rdi+40h], r15
0x180006a68  mov     [rsi], r14
0x180006a6b  mov     rbx, [rdi+40h]
0x180006a6f  test    rbx, rbx
0x180006a72  jz      loc_180006B70
0x180006a78  mov     rdx, [rsi]; DestinationSize
0x180006a7b  lea     rsi, [rdx+rbx]
0x180006a7f  cmp     rbx, rsi
0x180006a82  jz      short loc_180006AC2
0x180006a84  mov     r8, [r12+38h]; Source
0x180006a89  test    r8, r8
0x180006a8c  jz      short loc_180006AC2
0x180006a8e  cmp     [r8], r13b
0x180006a91  jz      short loc_180006AC2
0x180006a93  mov     rax, rbp
0x180006a96  inc     rax
0x180006a99  cmp     [r8+rax], r13b
0x180006a9d  jnz     short loc_180006A96
0x180006a9f  lea     r14, [rax+1]
0x180006aa3  cmp     rdx, r14
0x180006aa6  jnb     short loc_180006AAE
0x180006aa8  mov     [rdi+10h], r13
0x180006aac  jmp     short loc_180006ACB
0x180006aae  mov     r9, r14; SourceSize
0x180006ab1  mov     rcx, rbx; Destination
0x180006ab4  call    memcpy_s_0
0x180006ab9  mov     [rdi+10h], rbx
0x180006abd  add     rbx, r14
0x180006ac0  jmp     short loc_180006AC6
0x180006ac2  mov     [rdi+10h], r13
0x180006ac6  cmp     rbx, rsi
0x180006ac9  jz      short loc_180006B12
0x180006acb  mov     r8, [r12+80h]; Source
0x180006ad3  test    r8, r8
0x180006ad6  jz      short loc_180006B12
0x180006ad8  cmp     [r8], r13b
0x180006adb  jz      short loc_180006B12
0x180006add  mov     rax, rbp
0x180006ae0  inc     rax
0x180006ae3  cmp     [r8+rax], r13b
0x180006ae7  jnz     short loc_180006AE0
0x180006ae9  mov     rdx, rsi
0x180006aec  lea     r14, [rax+1]
0x180006af0  sub     rdx, rbx; DestinationSize
0x180006af3  cmp     rdx, r14
0x180006af6  jnb     short loc_180006AFE
0x180006af8  mov     [rdi+20h], r13
0x180006afc  jmp     short loc_180006B1B
0x180006afe  mov     r9, r14; SourceSize
0x180006b01  mov     rcx, rbx; Destination
0x180006b04  call    memcpy_s_0
0x180006b09  mov     [rdi+20h], rbx
0x180006b0d  add     rbx, r14
0x180006b10  jmp     short loc_180006B16
0x180006b12  mov     [rdi+20h], r13
0x180006b16  cmp     rbx, rsi
0x180006b19  jz      short loc_180006B5C
0x180006b1b  mov     r8, [r12+18h]; Source
0x180006b20  test    r8, r8
0x180006b23  jz      short loc_180006B5C
0x180006b25  cmp     [r8], r13w
0x180006b29  jz      short loc_180006B5C
0x180006b2b  inc     rbp
0x180006b2e  cmp     [r8+rbp*2], r13w
0x180006b33  jnz     short loc_180006B2B
0x180006b35  mov     rdx, rsi
0x180006b38  lea     r14, ds:2[rbp*2]
0x180006b40  sub     rdx, rbx; DestinationSize
0x180006b43  cmp     rdx, r14
0x180006b46  jb      short loc_180006B5C
0x180006b48  mov     r9, r14; SourceSize
0x180006b4b  mov     rcx, rbx; Destination
0x180006b4e  call    memcpy_s_0
0x180006b53  mov     [rdi+38h], rbx
0x180006b57  add     rbx, r14
0x180006b5a  jmp     short loc_180006B60
0x180006b5c  mov     [rdi+38h], r13
0x180006b60  sub     rsi, rbx
0x180006b63  xor     edx, edx; Val
0x180006b65  mov     r8, rsi; Size
0x180006b68  mov     rcx, rbx; void *
0x180006b6b  call    memset_0
0x180006b70  add     rsp, 28h
0x180006b74  pop     r15
0x180006b76  pop     r14
0x180006b78  pop     r13
0x180006b7a  pop     r12
0x180006b7c  pop     rdi
0x180006b7d  pop     rsi
0x180006b7e  pop     rbp
0x180006b7f  pop     rbx
0x180006b80  retn
```
