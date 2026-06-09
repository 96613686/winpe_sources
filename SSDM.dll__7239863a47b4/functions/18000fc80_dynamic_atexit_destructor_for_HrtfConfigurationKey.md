# _dynamic_atexit_destructor_for__HrtfConfigurationKey__

- ea: `0x18000fc80`
- end: `0x18000fcbb`
- name: `_dynamic_atexit_destructor_for__HrtfConfigurationKey__`
- size: `59`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000fc80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc95`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc95`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__HrtfConfigurationKey__()
{
  __int64 result; // rax

  if ( (unsigned __int64)qword_18001FB78 >= 8 )
    operator delete((void *)qword_18001FB60);
  result = 0;
  qword_18001FB78 = 7;
  qword_18001FB70 = 0;
  LOWORD(qword_18001FB60) = 0;
  return result;
}

```

## disassembly

```asm
0x18000fc80  sub     rsp, 28h
0x18000fc84  cmp     cs:qword_18001FB78, 8
0x18000fc8c  jb      short loc_18000FC9B
0x18000fc8e  mov     rcx, cs:qword_18001FB60
0x18000fc95  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fc9b  xor     eax, eax
0x18000fc9d  mov     cs:qword_18001FB78, 7
0x18000fca8  mov     cs:qword_18001FB70, rax
0x18000fcaf  mov     word ptr cs:qword_18001FB60, ax
0x18000fcb6  add     rsp, 28h
0x18000fcba  retn
```
