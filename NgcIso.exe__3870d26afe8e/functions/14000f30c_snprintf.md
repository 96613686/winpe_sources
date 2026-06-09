# snprintf

- ea: `0x14000f30c`
- end: `0x14000f36e`
- name: `snprintf`
- size: `98`
- prototype: `int(char *const Buffer, const size_t BufferCount, const char *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400398bc`

## callees

- `0x14000f2fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x14000f357`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x14000f357`

## pseudocode

```c
int snprintf(char *const Buffer, const size_t BufferCount, const char *const Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = __stdio_common_vsprintf(*v6 | 2, Buffer, BufferCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x14000f30c  mov     rax, rsp
0x14000f30f  mov     [rax+18h], r8
0x14000f313  mov     [rax+20h], r9
0x14000f317  push    rbx
0x14000f318  push    rbp
0x14000f319  push    rsi
0x14000f31a  push    rdi
0x14000f31b  sub     rsp, 48h
0x14000f31f  mov     rsi, r8
0x14000f322  mov     qword ptr [rax-38h], 0
0x14000f32a  mov     rbx, rdx
0x14000f32d  lea     rbp, [rax+20h]
0x14000f331  mov     rdi, rcx
0x14000f334  call    __local_stdio_printf_options
0x14000f339  mov     [rsp+68h+ArgList], rbp; ArgList
0x14000f33e  mov     r9, rsi; Format
0x14000f341  mov     r8, rbx; BufferCount
0x14000f344  mov     [rsp+68h+Locale], 0; Locale
0x14000f34d  mov     rdx, rdi; Buffer
0x14000f350  mov     rcx, [rax]
0x14000f353  or      rcx, 2; Options
0x14000f357  call    cs:__imp___stdio_common_vsprintf
0x14000f35d  or      ecx, 0FFFFFFFFh
0x14000f360  test    eax, eax
0x14000f362  cmovs   eax, ecx
0x14000f365  add     rsp, 48h
0x14000f369  pop     rdi
0x14000f36a  pop     rsi
0x14000f36b  pop     rbp
0x14000f36c  pop     rbx
0x14000f36d  retn
```
