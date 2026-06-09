# __acrt_can_use_vista_locale_apis

- ea: `0x18034ebdc`
- end: `0x18034ec0a`
- name: `__acrt_can_use_vista_locale_apis`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18034bb14`

## callees

- `0x18034e06c`

## string_xrefs

- `0x18034ebe0`: `CompareStringEx`
- `0x18034ebf3`: `CompareStringEx`

## pseudocode

```c
bool _acrt_can_use_vista_locale_apis()
{
  return try_get_function_0(1u, "CompareStringEx", (unsigned int *)L"\a", (unsigned int *)"CompareStringEx") != 0;
}

```

## disassembly

```asm
0x18034ebdc  sub     rsp, 28h
0x18034ebe0  lea     r9, aComparestringe_0
0x18034ebe7  mov     ecx, 1
0x18034ebec  lea     r8, asc_180402FC0
0x18034ebf3  lea     rdx, aComparestringe_0
0x18034ebfa  call    try_get_function_0
0x18034ebff  test    rax, rax
0x18034ec02  setnz   al
0x18034ec05  add     rsp, 28h
0x18034ec09  retn
```
