# winrt::to_hstring<char const *,0>(char const * const &)

- ea: `0x180005d34`
- end: `0x180005db0`
- name: `??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## callees

- `0x1800020e5`
- `0x180005d34`
- `0x18000972c`

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
  const char *v7; // rdx
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
0x180005d34  push    rbx
0x180005d36  push    rbp
0x180005d37  push    rsi
0x180005d38  push    rdi
0x180005d39  push    r14
0x180005d3b  sub     rsp, 40h
0x180005d3f  mov     rbp, [rdx]
0x180005d42  xor     ebx, ebx
0x180005d44  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005d48  mov     rdi, rcx
0x180005d4b  inc     rsi
0x180005d4e  cmp     [rsi+rbp], bl
0x180005d51  jnz     short loc_180005D4B
0x180005d53  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x180005d57  mov     r9d, esi; cbMultiByte
0x180005d5a  mov     r8, rbp; lpMultiByteStr
0x180005d5d  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x180005d62  xor     edx, edx; dwFlags
0x180005d64  mov     ecx, 0FDE9h; CodePage
0x180005d69  call    MultiByteToWideChar_0
0x180005d6e  mov     r14d, eax
0x180005d71  test    eax, eax
0x180005d73  jz      short loc_180005D9F
0x180005d75  mov     ecx, eax; this
0x180005d77  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180005d7c  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180005d81  mov     r9d, esi; cbMultiByte
0x180005d84  mov     r8, rbp; lpMultiByteStr
0x180005d87  mov     ecx, 0FDE9h; CodePage
0x180005d8c  mov     rbx, rax
0x180005d8f  mov     rdx, [rax+10h]
0x180005d93  mov     [rsp+68h+lpWideCharStr], rdx; lpWideCharStr
0x180005d98  xor     edx, edx; dwFlags
0x180005d9a  call    MultiByteToWideChar_0
0x180005d9f  mov     rax, rdi
0x180005da2  mov     [rdi], rbx
0x180005da5  add     rsp, 40h
0x180005da9  pop     r14
0x180005dab  pop     rdi
0x180005dac  pop     rsi
0x180005dad  pop     rbp
0x180005dae  pop     rbx
0x180005daf  retn
```
