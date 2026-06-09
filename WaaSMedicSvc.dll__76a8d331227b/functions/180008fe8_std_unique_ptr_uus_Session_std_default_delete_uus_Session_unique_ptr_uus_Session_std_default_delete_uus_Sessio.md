# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::~unique_ptr<uus::Session,std::default_delete<uus::Session>>(void)

- ea: `0x180008fe8`
- end: `0x180009009`
- name: `??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c402`

## callees

- `0x180008fe8`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180008fe8  sub     rsp, 28h
0x180008fec  mov     rcx, [rcx]
0x180008fef  test    rcx, rcx
0x180008ff2  jz      short loc_180009004
0x180008ff4  mov     rax, [rcx]
0x180008ff7  mov     edx, 1
0x180008ffc  mov     rax, [rax]
0x180008fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009004  add     rsp, 28h
0x180009008  retn
```
