# dllmain_crt_process_detach

- ea: `0x180001d08`
- end: `0x180001d8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001bb0`

## callees

- `0x180001d08`
- `0x180001f7c`
- `0x1800020a4`
- `0x1800020dc`
- `0x18000226c`
- `0x180002298`
- `0x1800023f8`
- `0x180002440`
- `0x180002490`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_180076350 <= 0 )
    return 0;
  --dword_180076350;
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
0x180001d08  mov     [rsp+arg_0], rbx
0x180001d0d  push    rdi
0x180001d0e  sub     rsp, 30h
0x180001d12  mov     dil, cl
0x180001d15  mov     eax, cs:dword_180076350
0x180001d1b  test    eax, eax
0x180001d1d  jg      short loc_180001D2C
0x180001d1f  xor     eax, eax
0x180001d21  mov     rbx, [rsp+38h+arg_0]
0x180001d26  add     rsp, 30h
0x180001d2a  pop     rdi
0x180001d2b  retn
0x180001d2c  dec     eax
0x180001d2e  mov     cs:dword_180076350, eax
0x180001d34  call    __scrt_acquire_startup_lock
0x180001d39  mov     bl, al
0x180001d3b  mov     [rsp+38h+var_18], al
0x180001d3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001d46  jnz     short loc_180001D7E
0x180001d48  call    __scrt_dllmain_uninitialize_c
0x180001d4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001d52  call    _RTC_Terminate
0x180001d57  mov     cs:__scrt_current_native_startup_state, 0
0x180001d61  mov     cl, bl
0x180001d63  call    __scrt_release_startup_lock
0x180001d68  xor     edx, edx
0x180001d6a  mov     cl, dil
0x180001d6d  call    __scrt_uninitialize_crt
0x180001d72  movzx   ebx, al
0x180001d75  call    __scrt_dllmain_uninitialize_critical
0x180001d7a  mov     eax, ebx
0x180001d7c  jmp     short loc_180001D21
0x180001d7e  mov     ecx, 7
0x180001d83  call    __scrt_fastfail
0x18005e179  push    rbp
0x18005e17b  sub     rsp, 20h
0x18005e17f  mov     rbp, rdx
0x18005e182  mov     cl, [rbp+20h]
0x18005e185  call    __scrt_release_startup_lock
0x18005e18a  nop
0x18005e18b  add     rsp, 20h
0x18005e18f  pop     rbp
0x18005e190  retn
0x18005e192  push    rbp
0x18005e194  sub     rsp, 20h
0x18005e198  mov     rbp, rdx
0x18005e19b  add     rsp, 20h
0x18005e19f  pop     rbp
0x18005e1a0  jmp     __scrt_dllmain_uninitialize_critical
```
