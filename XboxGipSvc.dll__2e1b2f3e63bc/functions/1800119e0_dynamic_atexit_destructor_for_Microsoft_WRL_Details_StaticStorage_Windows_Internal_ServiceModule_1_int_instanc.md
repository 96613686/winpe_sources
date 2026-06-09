# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___

- ea: `0x1800119e0`
- end: `0x180011a11`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800119e0`
- `0x180012010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___()
{
  __int64 result; // rax

  if ( byte_18001A618 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))qword_18001A608)(&qword_18001A608, 0);
    byte_18001A618 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800119e0  sub     rsp, 28h
0x1800119e4  cmp     cs:byte_18001A618, 0
0x1800119eb  jz      short loc_180011A0C
0x1800119ed  mov     rax, cs:qword_18001A608
0x1800119f4  lea     rcx, qword_18001A608
0x1800119fb  xor     edx, edx
0x1800119fd  mov     rax, [rax]
0x180011a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a05  mov     cs:byte_18001A618, 0
0x180011a0c  add     rsp, 28h
0x180011a10  retn
```
