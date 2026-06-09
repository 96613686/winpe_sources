# printf

- ea: `0x140001fc8`
- end: `0x14000201e`
- name: `printf`
- size: `86`
- prototype: `int(const char *const Format, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002430`

## callees

- `0x140001034`
- `0x140001e6c`
- `0x140001e9c`

## pseudocode

```c
int printf(const char *const Format, ...)
{
  FILE *v1; // rbx
  unsigned __int64 *v2; // rax
  va_list va; // [rsp+68h] [rbp+10h] BYREF

  va_start(va, Format);
  v1 = o___acrt_iob_func_0(1u);
  v2 = _local_stdio_printf_options();
  return o___stdio_common_vfprintf_0(*v2, v1, Format, 0, va);
}

```

## disassembly

```asm
0x140001fc8  mov     rax, rsp
0x140001fcb  mov     [rax+8], rcx
0x140001fcf  mov     [rax+10h], rdx
0x140001fd3  mov     [rax+18h], r8
0x140001fd7  mov     [rax+20h], r9
0x140001fdb  push    rbx
0x140001fdc  push    rdi
0x140001fdd  sub     rsp, 48h
0x140001fe1  mov     ecx, 1; Ix
0x140001fe6  mov     qword ptr [rax-28h], 0
0x140001fee  lea     rdi, [rax+10h]
0x140001ff2  call    _o___acrt_iob_func_0
0x140001ff7  mov     rbx, rax
0x140001ffa  call    __local_stdio_printf_options
0x140001fff  mov     r8, [rsp+58h+Format]; Format
0x140002004  xor     r9d, r9d; Locale
0x140002007  mov     rdx, rbx; Stream
0x14000200a  mov     [rsp+58h+ArgList], rdi; ArgList
0x14000200f  mov     rcx, [rax]; Options
0x140002012  call    _o___stdio_common_vfprintf_0
0x140002017  add     rsp, 48h
0x14000201b  pop     rdi
0x14000201c  pop     rbx
0x14000201d  retn
```
