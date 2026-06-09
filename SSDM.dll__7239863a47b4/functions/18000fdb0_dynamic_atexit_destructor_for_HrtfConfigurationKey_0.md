# _dynamic_atexit_destructor_for__HrtfConfigurationKey___0

- ea: `0x18000fdb0`
- end: `0x18000fdeb`
- name: `_dynamic_atexit_destructor_for__HrtfConfigurationKey___0`
- size: `59`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000fdb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fdc5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fdc5`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__HrtfConfigurationKey___0()
{
  __int64 result; // rax

  if ( (unsigned __int64)qword_18001FB98 >= 8 )
    operator delete((void *)qword_18001FB80);
  result = 0;
  qword_18001FB98 = 7;
  qword_18001FB90 = 0;
  LOWORD(qword_18001FB80) = 0;
  return result;
}

```

## disassembly

```asm
0x18000fdb0  sub     rsp, 28h
0x18000fdb4  cmp     cs:qword_18001FB98, 8
0x18000fdbc  jb      short loc_18000FDCB
0x18000fdbe  mov     rcx, cs:qword_18001FB80
0x18000fdc5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fdcb  xor     eax, eax
0x18000fdcd  mov     cs:qword_18001FB98, 7
0x18000fdd8  mov     cs:qword_18001FB90, rax
0x18000fddf  mov     word ptr cs:qword_18001FB80, ax
0x18000fde6  add     rsp, 28h
0x18000fdea  retn
```
