# __crtCreateEventExW

- ea: `0x18030b6f8`
- end: `0x18030b733`
- name: `__crtCreateEventExW`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18030f918`

## callees

- `0x18030b6f8`
- `0x180358070`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18030b72c`

## pseudocode

```c
HANDLE __fastcall _crtCreateEventExW(struct _SECURITY_ATTRIBUTES *a1, const WCHAR *a2, char a3)
{
  if ( _security_cookie != qword_1804C6730 )
    return (HANDLE)((__int64 (*)(void))(_security_cookie ^ qword_1804C6730))();
  else
    return CreateEventW(a1, a3 & 1, a3 & 2, a2);
}

```

## disassembly

```asm
0x18030b6f8  sub     rsp, 38h
0x18030b6fc  mov     rax, cs:qword_1804C6730
0x18030b703  mov     r10d, r8d
0x18030b706  xor     rax, cs:__security_cookie
0x18030b70d  jz      short loc_18030B71A
0x18030b70f  call    cs:__guard_dispatch_icall_fptr
0x18030b715  add     rsp, 38h
0x18030b719  retn
0x18030b71a  and     r10d, 1
0x18030b71e  mov     r9, rdx
0x18030b721  mov     edx, r10d
0x18030b724  and     r8d, 2
0x18030b728  add     rsp, 38h
0x18030b72c  jmp     cs:__imp_CreateEventW
```
