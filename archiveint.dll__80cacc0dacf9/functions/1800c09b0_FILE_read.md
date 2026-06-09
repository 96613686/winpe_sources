# FILE_read

- ea: `0x1800c09b0`
- end: `0x1800c0a22`
- name: `FILE_read`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006c00`
- `0x1800c09b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c09f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c09f8`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x1800c09ee`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x1800c09ee`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800c09dc`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800c09dc`

## string_xrefs

- `0x1800c09fe`: `Error reading file`

## pseudocode

```c
size_t __fastcall FILE_read(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  size_t v5; // rdi
  unsigned int *v6; // rax

  *a3 = a2[3];
  v5 = fread((void *)a2[3], 1u, a2[1], (FILE *)*a2);
  if ( v5 < a2[1] && (unsigned int)_o_ferror(*a2) )
  {
    v6 = (unsigned int *)_o__errno();
    archive_set_error(a1, *v6, "Error reading file");
  }
  return v5;
}

```

## disassembly

```asm
0x1800c09b0  mov     [rsp+arg_0], rbx
0x1800c09b5  mov     [rsp+arg_8], rsi
0x1800c09ba  push    rdi
0x1800c09bb  sub     rsp, 20h
0x1800c09bf  mov     rax, [rdx+18h]
0x1800c09c3  mov     rbx, rdx
0x1800c09c6  mov     [r8], rax
0x1800c09c9  mov     rsi, rcx
0x1800c09cc  mov     r9, [rdx]; Stream
0x1800c09cf  mov     r8, [rdx+8]; ElementCount
0x1800c09d3  mov     edx, 1; ElementSize
0x1800c09d8  mov     rcx, [rbx+18h]; Buffer
0x1800c09dc  call    cs:__imp_fread
0x1800c09e2  mov     rdi, rax
0x1800c09e5  cmp     rax, [rbx+8]
0x1800c09e9  jnb     short loc_1800C0A0F
0x1800c09eb  mov     rcx, [rbx]
0x1800c09ee  call    cs:__imp__o_ferror
0x1800c09f4  test    eax, eax
0x1800c09f6  jz      short loc_1800C0A0F
0x1800c09f8  call    cs:__imp__o__errno
0x1800c09fe  lea     r8, aErrorReadingFi; "Error reading file"
0x1800c0a05  mov     rcx, rsi
0x1800c0a08  mov     edx, [rax]
0x1800c0a0a  call    archive_set_error
0x1800c0a0f  mov     rbx, [rsp+28h+arg_0]
0x1800c0a14  mov     rax, rdi
0x1800c0a17  mov     rsi, [rsp+28h+arg_8]
0x1800c0a1c  add     rsp, 20h
0x1800c0a20  pop     rdi
0x1800c0a21  retn
```
