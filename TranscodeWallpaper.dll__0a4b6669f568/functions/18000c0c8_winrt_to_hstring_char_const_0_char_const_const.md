# winrt::to_hstring<char const *,0>(char const * const &)

- ea: `0x18000c0c8`
- end: `0x18000c144`
- name: `??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z`
- size: `124`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(struct winrt::impl::shared_hstring_header **, const CHAR **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## callees

- `0x180002e35`
- `0x180006cc4`
- `0x18000c0c8`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::to_hstring<char const *,0>(
        struct winrt::impl::shared_hstring_header **a1,
        const CHAR **a2)
{
  const CHAR *v2; // rbp
  struct winrt::impl::shared_hstring_header *v3; // rbx
  __int64 v4; // rsi
  unsigned int v6; // eax
  unsigned int v7; // edx
  int cchWideChar; // r14d
  struct winrt::impl::shared_hstring_header **result; // rax

  v2 = *a2;
  v3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  v6 = MultiByteToWideChar_0(0xFDE9u, 0, v2, v4, 0, 0);
  cchWideChar = v6;
  if ( v6 )
  {
    v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v6, v7);
    MultiByteToWideChar_0(0xFDE9u, 0, v2, v4, *((LPWSTR *)v3 + 2), cchWideChar);
  }
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18000c0c8  push    rbx
0x18000c0ca  push    rbp
0x18000c0cb  push    rsi
0x18000c0cc  push    rdi
0x18000c0cd  push    r14
0x18000c0cf  sub     rsp, 40h
0x18000c0d3  mov     rbp, [rdx]
0x18000c0d6  xor     ebx, ebx
0x18000c0d8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c0dc  mov     rdi, rcx
0x18000c0df  inc     rsi
0x18000c0e2  cmp     [rsi+rbp], bl
0x18000c0e5  jnz     short loc_18000C0DF
0x18000c0e7  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x18000c0eb  mov     r9d, esi; cbMultiByte
0x18000c0ee  mov     r8, rbp; lpMultiByteStr
0x18000c0f1  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x18000c0f6  xor     edx, edx; dwFlags
0x18000c0f8  mov     ecx, 0FDE9h; CodePage
0x18000c0fd  call    MultiByteToWideChar_0
0x18000c102  mov     r14d, eax
0x18000c105  test    eax, eax
0x18000c107  jz      short loc_18000C133
0x18000c109  mov     ecx, eax; this
0x18000c10b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000c110  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x18000c115  mov     r9d, esi; cbMultiByte
0x18000c118  mov     r8, rbp; lpMultiByteStr
0x18000c11b  mov     ecx, 0FDE9h; CodePage
0x18000c120  mov     rbx, rax
0x18000c123  mov     rdx, [rax+10h]
0x18000c127  mov     [rsp+68h+lpWideCharStr], rdx; lpWideCharStr
0x18000c12c  xor     edx, edx; dwFlags
0x18000c12e  call    MultiByteToWideChar_0
0x18000c133  mov     rax, rdi
0x18000c136  mov     [rdi], rbx
0x18000c139  add     rsp, 40h
0x18000c13d  pop     r14
0x18000c13f  pop     rdi
0x18000c140  pop     rsi
0x18000c141  pop     rbp
0x18000c142  pop     rbx
0x18000c143  retn
```
