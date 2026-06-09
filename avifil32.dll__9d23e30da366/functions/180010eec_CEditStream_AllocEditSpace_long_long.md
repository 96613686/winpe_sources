# CEditStream::AllocEditSpace(long,long)

- ea: `0x180010eec`
- end: `0x180011009`
- name: `?AllocEditSpace@CEditStream@@AEAAJJJ@Z`
- size: `285`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011404`
- `0x180011594`
- `0x180011a64`
- `0x180012224`

## callees

- `0x180010eec`
- `0x180017365`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180010f86`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180010f86`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010f67`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010f67`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180010f8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180010f8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010f5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010f74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010f5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010f74`

## pseudocode

```c
__int64 __fastcall CEditStream::AllocEditSpace(CEditStream *this, int a2, unsigned int a3)
{
  __int64 v4; // rdi
  signed int v5; // ecx
  unsigned int v7; // eax
  unsigned int v8; // ebp
  HGLOBAL v9; // rax
  HGLOBAL v10; // rax
  HGLOBAL v11; // rax
  LPVOID v12; // rax
  int v14; // eax

  v4 = a2;
  v5 = *((_DWORD *)this + 55);
  if ( (int)(a3 + *((_DWORD *)this + 54)) > v5 )
  {
    v7 = a3 + 8;
    if ( a3 + 8 < a3 )
      return 2147942934LL;
    if ( v7 <= 0x10 )
      v7 = 16;
    v8 = v5 + v7;
    if ( v5 + v7 < v7 || !is_mul_ok(v8, 0x38u) )
      return 2147942934LL;
    v9 = GlobalHandle(*((LPCVOID *)this + 29));
    GlobalUnlock(v9);
    v10 = GlobalHandle(*((LPCVOID *)this + 29));
    v11 = GlobalReAlloc(v10, 56LL * v8, 0x2042u);
    v12 = GlobalLock(v11);
    if ( !v12 )
      return 2147762279LL;
    *((_QWORD *)this + 29) = v12;
    *((_DWORD *)this + 55) = v8;
  }
  if ( (unsigned int)v4 + a3 < (unsigned int)v4 )
    return 2147942934LL;
  if ( (int)v4 >= 0 )
  {
    v14 = *((_DWORD *)this + 54);
    if ( (int)v4 < v14 )
      memmove_0(
        (void *)(*((_QWORD *)this + 29) + 56LL * ((unsigned int)v4 + a3)),
        (const void *)(*((_QWORD *)this + 29) + 56 * v4),
        56LL * (v14 - (int)v4));
  }
  *((_DWORD *)this + 54) += a3;
  return 0;
}

```

## disassembly

```asm
0x180010eec  mov     [rsp+arg_8], rbx
0x180010ef1  mov     [rsp+arg_10], rbp
0x180010ef6  push    rsi
0x180010ef7  push    rdi
0x180010ef8  push    r14
0x180010efa  sub     rsp, 20h
0x180010efe  mov     rbx, rcx
0x180010f01  movsxd  rdi, edx
0x180010f04  mov     ecx, [rcx+0DCh]
0x180010f0a  mov     esi, r8d
0x180010f0d  mov     r9d, [rbx+0D8h]
0x180010f14  add     r9d, r8d
0x180010f17  cmp     r9d, ecx
0x180010f1a  jle     loc_180010FAE
0x180010f20  lea     eax, [r8+8]
0x180010f24  cmp     eax, r8d
0x180010f27  jb      loc_180010FB5
0x180010f2d  mov     edx, 10h
0x180010f32  cmp     eax, edx
0x180010f34  cmovbe  eax, edx
0x180010f37  lea     ebp, [rcx+rax]
0x180010f3a  cmp     ebp, eax
0x180010f3c  jb      short loc_180010FB5
0x180010f3e  mov     ecx, ebp
0x180010f40  lea     eax, [rdx+28h]
0x180010f43  mul     rcx
0x180010f46  mov     [rsp+38h+arg_0], 0
0x180010f4f  mov     r14, rax
0x180010f52  test    rdx, rdx
0x180010f55  jnz     short loc_180010FB5
0x180010f57  mov     rcx, [rbx+0E8h]; pMem
0x180010f5e  call    cs:__imp_GlobalHandle
0x180010f64  mov     rcx, rax; hMem
0x180010f67  call    cs:__imp_GlobalUnlock
0x180010f6d  mov     rcx, [rbx+0E8h]; pMem
0x180010f74  call    cs:__imp_GlobalHandle
0x180010f7a  mov     r8d, 2042h; uFlags
0x180010f80  mov     rdx, r14; dwBytes
0x180010f83  mov     rcx, rax; hMem
0x180010f86  call    cs:__imp_GlobalReAlloc
0x180010f8c  mov     rcx, rax; hMem
0x180010f8f  call    cs:__imp_GlobalLock
0x180010f95  test    rax, rax
0x180010f98  jnz     short loc_180010FA1
0x180010f9a  mov     eax, 80044067h
0x180010f9f  jmp     short loc_180010FF6
0x180010fa1  mov     [rbx+0E8h], rax
0x180010fa8  mov     [rbx+0DCh], ebp
0x180010fae  lea     ecx, [rdi+rsi]
0x180010fb1  cmp     ecx, edi
0x180010fb3  jnb     short loc_180010FBC
0x180010fb5  mov     eax, 80070216h
0x180010fba  jmp     short loc_180010FF6
0x180010fbc  test    edi, edi
0x180010fbe  js      short loc_180010FEE
0x180010fc0  mov     eax, [rbx+0D8h]
0x180010fc6  cmp     edi, eax
0x180010fc8  jge     short loc_180010FEE
0x180010fca  mov     r9, [rbx+0E8h]
0x180010fd1  sub     eax, edi
0x180010fd3  cdqe
0x180010fd5  imul    r8, rax, 38h ; '8'; Size
0x180010fd9  imul    rdx, rdi, 38h ; '8'
0x180010fdd  mov     eax, ecx
0x180010fdf  imul    rcx, rax, 38h ; '8'
0x180010fe3  add     rdx, r9; Src
0x180010fe6  add     rcx, r9; void *
0x180010fe9  call    memmove_0
0x180010fee  add     [rbx+0D8h], esi
0x180010ff4  xor     eax, eax
0x180010ff6  mov     rbx, [rsp+38h+arg_8]
0x180010ffb  mov     rbp, [rsp+38h+arg_10]
0x180011000  add     rsp, 20h
0x180011004  pop     r14
0x180011006  pop     rdi
0x180011007  pop     rsi
0x180011008  retn
```
