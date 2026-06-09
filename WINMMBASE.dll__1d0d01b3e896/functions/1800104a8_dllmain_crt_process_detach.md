# dllmain_crt_process_detach

- ea: `0x1800104a8`
- end: `0x18001052b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010350`

## callees

- `0x1800104a8`
- `0x180010710`
- `0x180010838`
- `0x180010870`
- `0x180010a00`
- `0x180010a2c`
- `0x180010bcc`
- `0x180010c14`
- `0x180010c64`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_18002C450 <= 0 )
    return 0;
  --dword_18002C450;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x1800104a8  mov     [rsp+arg_0], rbx
0x1800104ad  push    rdi
0x1800104ae  sub     rsp, 30h
0x1800104b2  mov     dil, cl
0x1800104b5  mov     eax, cs:dword_18002C450
0x1800104bb  test    eax, eax
0x1800104bd  jg      short loc_1800104CC
0x1800104bf  xor     eax, eax
0x1800104c1  mov     rbx, [rsp+38h+arg_0]
0x1800104c6  add     rsp, 30h
0x1800104ca  pop     rdi
0x1800104cb  retn
0x1800104cc  dec     eax
0x1800104ce  mov     cs:dword_18002C450, eax
0x1800104d4  call    __scrt_acquire_startup_lock
0x1800104d9  mov     bl, al
0x1800104db  mov     [rsp+38h+var_18], al
0x1800104df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800104e6  jnz     short loc_18001051E
0x1800104e8  call    __scrt_dllmain_uninitialize_c
0x1800104ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800104f2  call    _RTC_Terminate
0x1800104f7  mov     cs:__scrt_current_native_startup_state, 0
0x180010501  mov     cl, bl
0x180010503  call    __scrt_release_startup_lock
0x180010508  xor     edx, edx
0x18001050a  mov     cl, dil
0x18001050d  call    __scrt_uninitialize_crt
0x180010512  movzx   ebx, al
0x180010515  call    __scrt_dllmain_uninitialize_critical
0x18001051a  mov     eax, ebx
0x18001051c  jmp     short loc_1800104C1
0x18001051e  mov     ecx, 7
0x180010523  call    __scrt_fastfail
0x180020a65  push    rbp
0x180020a67  sub     rsp, 20h
0x180020a6b  mov     rbp, rdx
0x180020a6e  mov     cl, [rbp+20h]
0x180020a71  call    __scrt_release_startup_lock
0x180020a76  nop
0x180020a77  add     rsp, 20h
0x180020a7b  pop     rbp
0x180020a7c  retn
0x180020a7e  push    rbp
0x180020a80  sub     rsp, 20h
0x180020a84  mov     rbp, rdx
0x180020a87  add     rsp, 20h
0x180020a8b  pop     rbp
0x180020a8c  jmp     __scrt_dllmain_uninitialize_critical
```
