# dllmain_crt_process_detach

- ea: `0x180029e18`
- end: `0x180029e9b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180029cc0`

## callees

- `0x180029e18`
- `0x18002a054`
- `0x18002a17c`
- `0x18002a1b4`
- `0x18002a344`
- `0x18002a370`
- `0x18002a53c`
- `0x18002a584`
- `0x18002a5d4`

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

  if ( dword_1800524B0 <= 0 )
    return 0;
  --dword_1800524B0;
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
0x180029e18  mov     [rsp+arg_0], rbx
0x180029e1d  push    rdi
0x180029e1e  sub     rsp, 30h
0x180029e22  mov     dil, cl
0x180029e25  mov     eax, cs:dword_1800524B0
0x180029e2b  test    eax, eax
0x180029e2d  jg      short loc_180029E3C
0x180029e2f  xor     eax, eax
0x180029e31  mov     rbx, [rsp+38h+arg_0]
0x180029e36  add     rsp, 30h
0x180029e3a  pop     rdi
0x180029e3b  retn
0x180029e3c  dec     eax
0x180029e3e  mov     cs:dword_1800524B0, eax
0x180029e44  call    __scrt_acquire_startup_lock
0x180029e49  mov     bl, al
0x180029e4b  mov     [rsp+38h+var_18], al
0x180029e4f  cmp     cs:__scrt_current_native_startup_state, 2
0x180029e56  jnz     short loc_180029E8E
0x180029e58  call    __scrt_dllmain_uninitialize_c
0x180029e5d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180029e62  call    _RTC_Terminate
0x180029e67  mov     cs:__scrt_current_native_startup_state, 0
0x180029e71  mov     cl, bl
0x180029e73  call    __scrt_release_startup_lock
0x180029e78  xor     edx, edx
0x180029e7a  mov     cl, dil
0x180029e7d  call    __scrt_uninitialize_crt
0x180029e82  movzx   ebx, al
0x180029e85  call    __scrt_dllmain_uninitialize_critical
0x180029e8a  mov     eax, ebx
0x180029e8c  jmp     short loc_180029E31
0x180029e8e  mov     ecx, 7
0x180029e93  call    __scrt_fastfail
0x18004003b  push    rbp
0x18004003d  sub     rsp, 20h
0x180040041  mov     rbp, rdx
0x180040044  mov     cl, [rbp+20h]
0x180040047  call    __scrt_release_startup_lock
0x18004004c  nop
0x18004004d  add     rsp, 20h
0x180040051  pop     rbp
0x180040052  retn
0x180040054  push    rbp
0x180040056  sub     rsp, 20h
0x18004005a  mov     rbp, rdx
0x18004005d  add     rsp, 20h
0x180040061  pop     rbp
0x180040062  jmp     __scrt_dllmain_uninitialize_critical
```
