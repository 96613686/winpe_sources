# dllmain_crt_process_detach

- ea: `0x180001b18`
- end: `0x180001b9b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800019c0`

## callees

- `0x180001b18`
- `0x180001d54`
- `0x180001e7c`
- `0x180001eb4`
- `0x180002044`
- `0x180002070`
- `0x180002298`
- `0x1800022e0`
- `0x180002330`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800333B0 <= 0 )
    return 0;
  --dword_1800333B0;
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
0x180001b18  mov     [rsp+arg_0], rbx
0x180001b1d  push    rdi
0x180001b1e  sub     rsp, 30h
0x180001b22  mov     dil, cl
0x180001b25  mov     eax, cs:dword_1800333B0
0x180001b2b  test    eax, eax
0x180001b2d  jg      short loc_180001B3C
0x180001b2f  xor     eax, eax
0x180001b31  mov     rbx, [rsp+38h+arg_0]
0x180001b36  add     rsp, 30h
0x180001b3a  pop     rdi
0x180001b3b  retn
0x180001b3c  dec     eax
0x180001b3e  mov     cs:dword_1800333B0, eax
0x180001b44  call    __scrt_acquire_startup_lock
0x180001b49  mov     bl, al
0x180001b4b  mov     [rsp+38h+var_18], al
0x180001b4f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001b56  jnz     short loc_180001B8E
0x180001b58  call    __scrt_dllmain_uninitialize_c
0x180001b5d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001b62  call    _RTC_Terminate
0x180001b67  mov     cs:__scrt_current_native_startup_state, 0
0x180001b71  mov     cl, bl
0x180001b73  call    __scrt_release_startup_lock
0x180001b78  xor     edx, edx
0x180001b7a  mov     cl, dil
0x180001b7d  call    __scrt_uninitialize_crt
0x180001b82  movzx   ebx, al
0x180001b85  call    __scrt_dllmain_uninitialize_critical
0x180001b8a  mov     eax, ebx
0x180001b8c  jmp     short loc_180001B31
0x180001b8e  mov     ecx, 7
0x180001b93  call    __scrt_fastfail
0x180029929  push    rbp
0x18002992b  sub     rsp, 20h
0x18002992f  mov     rbp, rdx
0x180029932  mov     cl, [rbp+20h]
0x180029935  call    __scrt_release_startup_lock
0x18002993a  nop
0x18002993b  add     rsp, 20h
0x18002993f  pop     rbp
0x180029940  retn
0x180029942  push    rbp
0x180029944  sub     rsp, 20h
0x180029948  mov     rbp, rdx
0x18002994b  add     rsp, 20h
0x18002994f  pop     rbp
0x180029950  jmp     __scrt_dllmain_uninitialize_critical
```
