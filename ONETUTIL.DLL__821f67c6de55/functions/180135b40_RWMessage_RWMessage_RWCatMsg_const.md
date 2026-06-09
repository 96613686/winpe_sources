# RWMessage::RWMessage(RWCatMsg const *,...)

- ea: `0x180135b40`
- end: `0x180135c0d`
- name: `??0RWMessage@@QEAA@PEBURWCatMsg@@ZZ`
- size: `205`
- prototype: `RWMessage *(RWMessage *__hidden this, const struct RWCatMsg *, ...)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800081f0`
- `0x180008940`
- `0x18009d59c`
- `0x18009d740`
- `0x18009d7f0`
- `0x18009df04`
- `0x18009e020`
- `0x18009e0f0`
- `0x180134a60`
- `0x180135260`
- `0x1801352c0`
- `0x1801360a0`
- `0x180139300`
- `0x180139490`
- `0x18013a3a0`
- `0x18013a420`
- `0x18013b2e4`
- `0x18013b888`
- `0x18013bc20`
- `0x18013c1f0`
- `0x18013c250`
- `0x18013c2b0`
- `0x18013dac0`
- `0x18013db60`
- `0x18013dc00`

## callees

- `0x180001170`
- `0x180083790`
- `0x180135b40`
- `0x1801503e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180135be9`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180135be9`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x180135ba3`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x180135ba3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135bd2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135bd2`

## pseudocode

```c
RWMessage *RWMessage::RWMessage(RWMessage *this, const char **a2, ...)
{
  unsigned __int64 *v4; // rax
  char *v5; // rcx
  unsigned __int64 v7; // rbx
  char *v8; // rax
  char Buffer[512]; // [rsp+40h] [rbp-228h] BYREF
  va_list va; // [rsp+280h] [rbp+18h] BYREF

  va_start(va, a2);
  v4 = (unsigned __int64 *)sub_180001170();
  _stdio_common_vsnprintf_s(*v4, Buffer, 0x1F8u, 0xFFFFFFFFFFFFFFFFuLL, a2[2], 0, va);
  v5 = Buffer;
  while ( *v5++ )
    ;
  v7 = (unsigned int)v5 - (unsigned int)Buffer;
  if ( dword_1802B0018 )
    v8 = (char *)COWSAllocator::AllocCurrentHeap(v7);
  else
    v8 = (char *)malloc(v7);
  *(_QWORD *)this = v8;
  strncpy_s(v8, v7, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
  return this;
}

```

## disassembly

```asm
0x180135b40  mov     r11, rsp
0x180135b43  mov     [r11+10h], rdx
0x180135b47  mov     [r11+18h], r8
0x180135b4b  mov     [r11+20h], r9
0x180135b4f  push    rbx
0x180135b50  push    rsi
0x180135b51  push    rdi
0x180135b52  sub     rsp, 250h
0x180135b59  mov     rax, cs:__security_cookie
0x180135b60  xor     rax, rsp
0x180135b63  mov     [rsp+268h+var_28], rax
0x180135b6b  mov     rbx, rdx
0x180135b6e  lea     rsi, [r11+18h]
0x180135b72  mov     rdi, rcx
0x180135b75  call    sub_180001170
0x180135b7a  mov     [rsp+268h+ArgList], rsi; ArgList
0x180135b7f  lea     rdx, [rsp+268h+Buffer]; Buffer
0x180135b84  and     [rsp+268h+var_240], 0
0x180135b8a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180135b8e  mov     r9, rsi; MaxCount
0x180135b91  mov     r8d, 1F8h; BufferCount
0x180135b97  mov     rcx, [rax]; Options
0x180135b9a  mov     rax, [rbx+10h]
0x180135b9e  mov     [rsp+268h+Format], rax; Format
0x180135ba3  call    cs:__stdio_common_vsnprintf_s
0x180135ba9  lea     rcx, [rsp+268h+Buffer]
0x180135bae  mov     al, [rcx]
0x180135bb0  inc     rcx
0x180135bb3  test    al, al
0x180135bb5  jnz     short loc_180135BAE
0x180135bb7  lea     rax, [rsp+268h+Buffer]
0x180135bbc  sub     ecx, eax
0x180135bbe  cmp     cs:dword_1802B0018, 0
0x180135bc5  mov     ebx, ecx
0x180135bc7  mov     ecx, ebx; unsigned __int64
0x180135bc9  jz      short loc_180135BD2
0x180135bcb  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180135bd0  jmp     short loc_180135BD8
0x180135bd2  call    cs:malloc
0x180135bd8  mov     r9, rsi; MaxCount
0x180135bdb  mov     [rdi], rax
0x180135bde  lea     r8, [rsp+268h+Buffer]; Source
0x180135be3  mov     rdx, rbx; SizeInBytes
0x180135be6  mov     rcx, rax; Destination
0x180135be9  call    cs:strncpy_s
0x180135bef  mov     rax, rdi
0x180135bf2  mov     rcx, [rsp+268h+var_28]
0x180135bfa  xor     rcx, rsp
0x180135bfd  call    sub_1801503E0
0x180135c02  add     rsp, 250h
0x180135c09  pop     rdi
0x180135c0a  pop     rsi
0x180135c0b  pop     rbx
0x180135c0c  retn
```
