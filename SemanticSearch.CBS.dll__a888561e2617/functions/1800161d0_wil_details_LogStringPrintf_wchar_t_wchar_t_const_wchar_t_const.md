# wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)

- ea: `0x1800161d0`
- end: `0x18001628d`
- name: `?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ`
- size: `189`
- prototype: `wchar_t *(wchar_t *Buffer, wchar_t *, const wchar_t *, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016290`

## callees

- `0x1800161c0`
- `0x1800161d0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180016236`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180016236`

## pseudocode

```c
wchar_t *wil::details::LogStringPrintf(wchar_t *Buffer, wchar_t *a2, const wchar_t *a3, const wchar_t *a4, ...)
{
  unsigned __int64 v5; // rbp
  __int64 v8; // rbx
  size_t v9; // rbp
  unsigned __int64 *v10; // rax
  int v11; // eax
  const wchar_t *ArgList; // [rsp+88h] [rbp+20h] BYREF

  ArgList = a4;
  v5 = a2 - Buffer;
  v8 = -1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFF )
    {
      *Buffer = 0;
    }
    else
    {
      v9 = v5 - 1;
      v10 = _local_stdio_printf_options();
      v11 = __stdio_common_vswprintf(*v10 | 1, Buffer, v9, a3, 0, (va_list)&ArgList);
      if ( v11 < 0 )
        v11 = -1;
      if ( v11 < 0 || v11 >= v9 )
        Buffer[v9] = 0;
    }
  }
  if ( a2 == Buffer )
    return Buffer;
  while ( Buffer[++v8] != 0 )
    ;
  return &Buffer[v8];
}

```

## disassembly

```asm
0x1800161d0  mov     [rsp+arg_10], r8
0x1800161d5  mov     [rsp+arg_18], r9
0x1800161da  push    rbx
0x1800161db  push    rbp
0x1800161dc  push    rsi
0x1800161dd  push    rdi
0x1800161de  push    r14
0x1800161e0  push    r15
0x1800161e2  sub     rsp, 38h
0x1800161e6  mov     rbp, rdx
0x1800161e9  lea     rsi, [rsp+68h+arg_18]
0x1800161f1  sub     rbp, rcx
0x1800161f4  mov     r15, r8
0x1800161f7  sar     rbp, 1
0x1800161fa  mov     r14, rdx
0x1800161fd  mov     rdi, rcx
0x180016200  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180016207  jz      short loc_180016259
0x180016209  cmp     rbp, 7FFFFFFFh
0x180016210  ja      short loc_180016254
0x180016212  dec     rbp
0x180016215  call    __local_stdio_printf_options
0x18001621a  mov     [rsp+68h+ArgList], rsi; ArgList
0x18001621f  mov     r9, r15; Format
0x180016222  xor     esi, esi
0x180016224  mov     r8, rbp; BufferCount
0x180016227  mov     rdx, rdi; Buffer
0x18001622a  mov     [rsp+68h+Locale], rsi; Locale
0x18001622f  mov     rcx, [rax]
0x180016232  or      rcx, 1; Options
0x180016236  call    cs:__imp___stdio_common_vswprintf
0x18001623c  test    eax, eax
0x18001623e  cmovs   eax, ebx
0x180016241  test    eax, eax
0x180016243  js      short loc_18001624E
0x180016245  cdqe
0x180016247  cmp     rax, rbp
0x18001624a  ja      short loc_18001624E
0x18001624c  jnz     short loc_180016259
0x18001624e  mov     [rdi+rbp*2], si
0x180016252  jmp     short loc_180016259
0x180016254  xor     esi, esi
0x180016256  mov     [rcx], si
0x180016259  cmp     r14, rdi
0x18001625c  jnz     short loc_180016270
0x18001625e  mov     rax, rdi
0x180016261  add     rsp, 38h
0x180016265  pop     r15
0x180016267  pop     r14
0x180016269  pop     rdi
0x18001626a  pop     rsi
0x18001626b  pop     rbp
0x18001626c  pop     rbx
0x18001626d  retn
0x180016270  cmp     word ptr [rdi+rbx*2+2], 0
0x180016276  lea     rbx, [rbx+1]
0x18001627a  jnz     short loc_180016270
0x18001627c  lea     rax, [rdi+rbx*2]
0x180016280  add     rsp, 38h
0x180016284  pop     r15
0x180016286  pop     r14
0x180016288  pop     rdi
0x180016289  pop     rsi
0x18001628a  pop     rbp
0x18001628b  pop     rbx
0x18001628c  retn
```
