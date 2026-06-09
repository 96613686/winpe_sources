# dllmain_crt_process_detach

- ea: `0x180001a98`
- end: `0x180001b1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001940`

## callees

- `0x180001a98`
- `0x180001df8`
- `0x180001e30`
- `0x180001f58`
- `0x180001f90`
- `0x180002120`
- `0x18000214c`
- `0x1800021ec`
- `0x18000223c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_180013290 <= 0 )
    return 0;
  --dword_180013290;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180001a98  mov     [rsp+arg_0], rbx
0x180001a9d  push    rdi
0x180001a9e  sub     rsp, 30h
0x180001aa2  mov     dil, cl
0x180001aa5  mov     eax, cs:dword_180013290
0x180001aab  test    eax, eax
0x180001aad  jg      short loc_180001ABC
0x180001aaf  xor     eax, eax
0x180001ab1  mov     rbx, [rsp+38h+arg_0]
0x180001ab6  add     rsp, 30h
0x180001aba  pop     rdi
0x180001abb  retn
0x180001abc  dec     eax
0x180001abe  mov     cs:dword_180013290, eax
0x180001ac4  call    __scrt_acquire_startup_lock
0x180001ac9  mov     bl, al
0x180001acb  mov     [rsp+38h+var_18], al
0x180001acf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001ad6  jnz     short loc_180001B0E
0x180001ad8  call    __scrt_dllmain_uninitialize_c
0x180001add  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001ae2  call    _RTC_Terminate
0x180001ae7  mov     cs:__scrt_current_native_startup_state, 0
0x180001af1  mov     cl, bl
0x180001af3  call    __scrt_release_startup_lock
0x180001af8  xor     edx, edx
0x180001afa  mov     cl, dil
0x180001afd  call    __scrt_uninitialize_crt
0x180001b02  movzx   ebx, al
0x180001b05  call    __scrt_dllmain_uninitialize_critical
0x180001b0a  mov     eax, ebx
0x180001b0c  jmp     short loc_180001AB1
0x180001b0e  mov     ecx, 7
0x180001b13  call    __scrt_fastfail
0x180008c59  push    rbp
0x180008c5b  sub     rsp, 20h
0x180008c5f  mov     rbp, rdx
0x180008c62  mov     cl, [rbp+20h]
0x180008c65  call    __scrt_release_startup_lock
0x180008c6a  nop
0x180008c6b  add     rsp, 20h
0x180008c6f  pop     rbp
0x180008c70  retn
0x180008c72  push    rbp
0x180008c74  sub     rsp, 20h
0x180008c78  mov     rbp, rdx
0x180008c7b  add     rsp, 20h
0x180008c7f  pop     rbp
0x180008c80  jmp     __scrt_dllmain_uninitialize_critical
```
