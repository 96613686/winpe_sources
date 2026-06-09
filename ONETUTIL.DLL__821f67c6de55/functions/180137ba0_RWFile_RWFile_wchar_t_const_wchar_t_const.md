# RWFile::RWFile(wchar_t const *,wchar_t const *)

- ea: `0x180137ba0`
- end: `0x180137c5e`
- name: `??0RWFile@@QEAA@PEB_W0@Z`
- size: `190`
- prototype: `RWFile *(RWFile *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18013bc20`

## callees

- `0x180083790`
- `0x180137ba0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180137c40`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180137c40`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x180137bd5`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x180137bed`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x180137bd5`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x180137bed`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180137c24`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180137c24`

## pseudocode

```c
RWFile *__fastcall RWFile::RWFile(RWFile *this, const wchar_t *a2, const wchar_t *a3)
{
  FILE **v3; // rbx
  FILE **v5; // rcx
  const wchar_t *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  wchar_t *v11; // rax

  v3 = (FILE **)((char *)this + 8);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v5 = (FILE **)((char *)this + 8);
  v6 = a2;
  if ( a3 )
    goto LABEL_4;
  wfopen_s(v5, a2, L"rb+");
  if ( !*v3 )
  {
    a3 = L"wb+";
    a2 = v6;
    v5 = v3;
LABEL_4:
    wfopen_s(v5, a2, a3);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  v9 = v8 + 1;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  if ( dword_1802B0018 )
    v11 = (wchar_t *)COWSAllocator::AllocCurrentHeap(v10);
  else
    v11 = (wchar_t *)malloc(v10);
  *(_QWORD *)this = v11;
  do
    ++v7;
  while ( v6[v7] );
  wcscpy_s(v11, v7 + 1, v6);
  return this;
}

```

## disassembly

```asm
0x180137ba0  mov     [rsp+arg_0], rbx
0x180137ba5  mov     [rsp+arg_8], rbp
0x180137baa  mov     [rsp+arg_10], rsi
0x180137baf  push    rdi
0x180137bb0  sub     rsp, 20h
0x180137bb4  xor     ebp, ebp
0x180137bb6  lea     rbx, [rcx+8]
0x180137bba  mov     [rcx], rbp
0x180137bbd  mov     rsi, rcx
0x180137bc0  mov     [rbx], rbp
0x180137bc3  mov     rcx, rbx; Stream
0x180137bc6  mov     rdi, rdx
0x180137bc9  test    r8, r8
0x180137bcc  jnz     short loc_180137BED
0x180137bce  lea     r8, aRb_0; "rb+"
0x180137bd5  call    cs:_wfopen_s
0x180137bdb  cmp     [rbx], rbp
0x180137bde  jnz     short loc_180137BF3
0x180137be0  lea     r8, aWb; "wb+"
0x180137be7  mov     rdx, rdi; FileName
0x180137bea  mov     rcx, rbx; Stream
0x180137bed  call    cs:_wfopen_s
0x180137bf3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180137bf7  mov     rcx, rbx
0x180137bfa  inc     rcx
0x180137bfd  cmp     [rdi+rcx*2], bp
0x180137c01  jnz     short loc_180137BFA
0x180137c03  inc     rcx
0x180137c06  mov     eax, 2
0x180137c0b  mul     rcx
0x180137c0e  cmovo   rax, rbx
0x180137c12  cmp     cs:dword_1802B0018, ebp
0x180137c18  mov     rcx, rax; unsigned __int64
0x180137c1b  jz      short loc_180137C24
0x180137c1d  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180137c22  jmp     short loc_180137C2A
0x180137c24  call    cs:malloc
0x180137c2a  mov     [rsi], rax
0x180137c2d  inc     rbx
0x180137c30  cmp     [rdi+rbx*2], bp
0x180137c34  jnz     short loc_180137C2D
0x180137c36  lea     rdx, [rbx+1]; SizeInWords
0x180137c3a  mov     r8, rdi; Source
0x180137c3d  mov     rcx, rax; Destination
0x180137c40  call    cs:wcscpy_s
0x180137c46  mov     rbx, [rsp+28h+arg_0]
0x180137c4b  mov     rax, rsi
0x180137c4e  mov     rsi, [rsp+28h+arg_10]
0x180137c53  mov     rbp, [rsp+28h+arg_8]
0x180137c58  add     rsp, 20h
0x180137c5c  pop     rdi
0x180137c5d  retn
```
