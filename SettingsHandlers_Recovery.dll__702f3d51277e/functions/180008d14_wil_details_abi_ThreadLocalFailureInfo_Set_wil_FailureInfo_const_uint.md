# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008d14`
- end: `0x180008f2d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800060b0`

## callees

- `0x180002ed4`
- `0x180007358`
- `0x180008d14`
- `0x18000aa28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008dfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e0a`

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
0x180008d14  push    rbx
0x180008d16  push    rbp
0x180008d17  push    rsi
0x180008d18  push    rdi
0x180008d19  push    r12
0x180008d1b  push    r13
0x180008d1d  push    r14
0x180008d1f  push    r15
0x180008d21  sub     rsp, 28h
0x180008d25  mov     [rcx+4], r8d
0x180008d29  xor     r13d, r13d
0x180008d2c  mov     eax, [rdx+8]
0x180008d2f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008d33  mov     [rcx+8], eax
0x180008d36  mov     rdi, rcx
0x180008d39  mov     [rcx+10h], r13
0x180008d3d  mov     r12, rdx
0x180008d40  movzx   eax, word ptr [rdx+40h]
0x180008d44  mov     [rcx+18h], ax
0x180008d48  mov     al, [rdx]
0x180008d4a  mov     [rcx+1Ah], al
0x180008d4d  mov     [rcx+20h], r13
0x180008d51  mov     rax, [rdx+88h]
0x180008d58  mov     [rcx+28h], rax
0x180008d5c  mov     rax, [rdx+90h]
0x180008d63  mov     [rcx+30h], rax
0x180008d67  mov     [rcx+38h], r13
0x180008d6b  mov     rcx, [rdx+38h]
0x180008d6f  lea     edx, [rbp+2]
0x180008d72  test    rcx, rcx
0x180008d75  jnz     short loc_180008D7C
0x180008d77  mov     r8d, edx
0x180008d7a  jmp     short loc_180008D8C
0x180008d7c  mov     rax, rbp
0x180008d7f  inc     rax
0x180008d82  cmp     [rcx+rax], r13b
0x180008d86  jnz     short loc_180008D7F
0x180008d88  lea     r8, [rax+1]; unsigned __int64
0x180008d8c  mov     rcx, [r12+80h]
0x180008d94  test    rcx, rcx
0x180008d97  jz      short loc_180008DA9
0x180008d99  mov     rax, rbp
0x180008d9c  inc     rax
0x180008d9f  cmp     [rcx+rax], r13b
0x180008da3  jnz     short loc_180008D9C
0x180008da5  lea     rdx, [rax+1]
0x180008da9  mov     rcx, [r12+18h]
0x180008dae  test    rcx, rcx
0x180008db1  jnz     short loc_180008DB8
0x180008db3  lea     eax, [rcx+2]
0x180008db6  jmp     short loc_180008DCD
0x180008db8  mov     rax, rbp
0x180008dbb  inc     rax
0x180008dbe  cmp     [rcx+rax*2], r13w
0x180008dc3  jnz     short loc_180008DBB
0x180008dc5  lea     rax, ds:2[rax*2]
0x180008dcd  lea     r14, [rdx+rax]
0x180008dd1  add     r14, r8
0x180008dd4  lea     rsi, [rdi+48h]
0x180008dd8  cmp     [rdi+40h], r13
0x180008ddc  jz      short loc_180008DE3
0x180008dde  cmp     [rsi], r14
0x180008de1  jnb     short loc_180008E17
0x180008de3  mov     rdx, r14; dwBytes
0x180008de6  mov     ecx, 8; dwFlags
0x180008deb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008df0  mov     r15, rax
0x180008df3  test    rax, rax
0x180008df6  jz      short loc_180008E17
0x180008df8  mov     rbx, [rdi+40h]
0x180008dfc  call    cs:__imp_GetProcessHeap
0x180008e02  mov     r8, rbx; lpMem
0x180008e05  xor     edx, edx; dwFlags
0x180008e07  mov     rcx, rax; hHeap
0x180008e0a  call    cs:__imp_HeapFree
0x180008e10  mov     [rdi+40h], r15
0x180008e14  mov     [rsi], r14
0x180008e17  mov     rbx, [rdi+40h]
0x180008e1b  test    rbx, rbx
0x180008e1e  jz      loc_180008F1C
0x180008e24  mov     rdx, [rsi]; DestinationSize
0x180008e27  lea     rsi, [rdx+rbx]
0x180008e2b  cmp     rbx, rsi
0x180008e2e  jz      short loc_180008E6E
0x180008e30  mov     r8, [r12+38h]; Source
0x180008e35  test    r8, r8
0x180008e38  jz      short loc_180008E6E
0x180008e3a  cmp     [r8], r13b
0x180008e3d  jz      short loc_180008E6E
0x180008e3f  mov     rax, rbp
0x180008e42  inc     rax
0x180008e45  cmp     [r8+rax], r13b
0x180008e49  jnz     short loc_180008E42
0x180008e4b  lea     r14, [rax+1]
0x180008e4f  cmp     rdx, r14
0x180008e52  jnb     short loc_180008E5A
0x180008e54  mov     [rdi+10h], r13
0x180008e58  jmp     short loc_180008E77
0x180008e5a  mov     r9, r14; SourceSize
0x180008e5d  mov     rcx, rbx; Destination
0x180008e60  call    memcpy_s
0x180008e65  mov     [rdi+10h], rbx
0x180008e69  add     rbx, r14
0x180008e6c  jmp     short loc_180008E72
0x180008e6e  mov     [rdi+10h], r13
0x180008e72  cmp     rbx, rsi
0x180008e75  jz      short loc_180008EBE
0x180008e77  mov     r8, [r12+80h]; Source
0x180008e7f  test    r8, r8
0x180008e82  jz      short loc_180008EBE
0x180008e84  cmp     [r8], r13b
0x180008e87  jz      short loc_180008EBE
0x180008e89  mov     rax, rbp
0x180008e8c  inc     rax
0x180008e8f  cmp     [r8+rax], r13b
0x180008e93  jnz     short loc_180008E8C
0x180008e95  mov     rdx, rsi
0x180008e98  lea     r14, [rax+1]
0x180008e9c  sub     rdx, rbx; DestinationSize
0x180008e9f  cmp     rdx, r14
0x180008ea2  jnb     short loc_180008EAA
0x180008ea4  mov     [rdi+20h], r13
0x180008ea8  jmp     short loc_180008EC7
0x180008eaa  mov     r9, r14; SourceSize
0x180008ead  mov     rcx, rbx; Destination
0x180008eb0  call    memcpy_s
0x180008eb5  mov     [rdi+20h], rbx
0x180008eb9  add     rbx, r14
0x180008ebc  jmp     short loc_180008EC2
0x180008ebe  mov     [rdi+20h], r13
0x180008ec2  cmp     rbx, rsi
0x180008ec5  jz      short loc_180008F08
0x180008ec7  mov     r8, [r12+18h]; Source
0x180008ecc  test    r8, r8
0x180008ecf  jz      short loc_180008F08
0x180008ed1  cmp     [r8], r13w
0x180008ed5  jz      short loc_180008F08
0x180008ed7  inc     rbp
0x180008eda  cmp     [r8+rbp*2], r13w
0x180008edf  jnz     short loc_180008ED7
0x180008ee1  mov     rdx, rsi
0x180008ee4  lea     r14, ds:2[rbp*2]
0x180008eec  sub     rdx, rbx; DestinationSize
0x180008eef  cmp     rdx, r14
0x180008ef2  jb      short loc_180008F08
0x180008ef4  mov     r9, r14; SourceSize
0x180008ef7  mov     rcx, rbx; Destination
0x180008efa  call    memcpy_s
0x180008eff  mov     [rdi+38h], rbx
0x180008f03  add     rbx, r14
0x180008f06  jmp     short loc_180008F0C
0x180008f08  mov     [rdi+38h], r13
0x180008f0c  sub     rsi, rbx
0x180008f0f  xor     edx, edx; Val
0x180008f11  mov     r8, rsi; Size
0x180008f14  mov     rcx, rbx; void *
0x180008f17  call    memset_0
0x180008f1c  add     rsp, 28h
0x180008f20  pop     r15
0x180008f22  pop     r14
0x180008f24  pop     r13
0x180008f26  pop     r12
0x180008f28  pop     rdi
0x180008f29  pop     rsi
0x180008f2a  pop     rbp
0x180008f2b  pop     rbx
0x180008f2c  retn
```
