# dllmain_crt_process_detach

- ea: `0x1800020e8`
- end: `0x18000216b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001f90`

## callees

- `0x1800020e8`
- `0x18000238c`
- `0x1800024b4`
- `0x1800024ec`
- `0x18000267c`
- `0x1800026a8`
- `0x180002b68`
- `0x180002bb0`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180019750 <= 0 )
    return 0;
  --dword_180019750;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x1800020e8  mov     [rsp+arg_0], rbx
0x1800020ed  push    rdi
0x1800020ee  sub     rsp, 30h
0x1800020f2  mov     dil, cl
0x1800020f5  mov     eax, cs:dword_180019750
0x1800020fb  test    eax, eax
0x1800020fd  jg      short loc_18000210C
0x1800020ff  xor     eax, eax
0x180002101  mov     rbx, [rsp+38h+arg_0]
0x180002106  add     rsp, 30h
0x18000210a  pop     rdi
0x18000210b  retn
0x18000210c  dec     eax
0x18000210e  mov     cs:dword_180019750, eax
0x180002114  call    __scrt_acquire_startup_lock
0x180002119  mov     bl, al
0x18000211b  mov     [rsp+38h+var_18], al
0x18000211f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002126  jnz     short loc_18000215E
0x180002128  call    __scrt_dllmain_uninitialize_c
0x18000212d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002132  call    _RTC_Terminate
0x180002137  mov     cs:__scrt_current_native_startup_state, 0
0x180002141  mov     cl, bl
0x180002143  call    __scrt_release_startup_lock
0x180002148  xor     edx, edx
0x18000214a  mov     cl, dil
0x18000214d  call    __scrt_uninitialize_crt
0x180002152  movzx   ebx, al
0x180002155  call    __scrt_dllmain_uninitialize_critical
0x18000215a  mov     eax, ebx
0x18000215c  jmp     short loc_180002101
0x18000215e  mov     ecx, 7
0x180002163  call    __scrt_fastfail
0x180010369  push    rbp
0x18001036b  sub     rsp, 20h
0x18001036f  mov     rbp, rdx
0x180010372  mov     cl, [rbp+20h]
0x180010375  call    __scrt_release_startup_lock
0x18001037a  nop
0x18001037b  add     rsp, 20h
0x18001037f  pop     rbp
0x180010380  retn
0x180010382  push    rbp
0x180010384  sub     rsp, 20h
0x180010388  mov     rbp, rdx
0x18001038b  add     rsp, 20h
0x18001038f  pop     rbp
0x180010390  jmp     __scrt_dllmain_uninitialize_critical
```
