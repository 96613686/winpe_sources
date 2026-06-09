# dllmain_crt_process_detach

- ea: `0x18002a8a8`
- end: `0x18002a92b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002a750`

## callees

- `0x18002a8a8`
- `0x18002abc0`
- `0x18002abf8`
- `0x18002ad20`
- `0x18002ad58`
- `0x18002aee8`
- `0x18002af14`
- `0x18002af54`
- `0x18002afa4`

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

  if ( dword_180059310 <= 0 )
    return 0;
  --dword_180059310;
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
0x18002a8a8  mov     [rsp+arg_0], rbx
0x18002a8ad  push    rdi
0x18002a8ae  sub     rsp, 30h
0x18002a8b2  mov     dil, cl
0x18002a8b5  mov     eax, cs:dword_180059310
0x18002a8bb  test    eax, eax
0x18002a8bd  jg      short loc_18002A8CC
0x18002a8bf  xor     eax, eax
0x18002a8c1  mov     rbx, [rsp+38h+arg_0]
0x18002a8c6  add     rsp, 30h
0x18002a8ca  pop     rdi
0x18002a8cb  retn
0x18002a8cc  dec     eax
0x18002a8ce  mov     cs:dword_180059310, eax
0x18002a8d4  call    __scrt_acquire_startup_lock
0x18002a8d9  mov     bl, al
0x18002a8db  mov     [rsp+38h+var_18], al
0x18002a8df  cmp     cs:__scrt_current_native_startup_state, 2
0x18002a8e6  jnz     short loc_18002A91E
0x18002a8e8  call    __scrt_dllmain_uninitialize_c
0x18002a8ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18002a8f2  call    _RTC_Terminate
0x18002a8f7  mov     cs:__scrt_current_native_startup_state, 0
0x18002a901  mov     cl, bl
0x18002a903  call    __scrt_release_startup_lock
0x18002a908  xor     edx, edx
0x18002a90a  mov     cl, dil
0x18002a90d  call    __scrt_uninitialize_crt
0x18002a912  movzx   ebx, al
0x18002a915  call    __scrt_dllmain_uninitialize_critical
0x18002a91a  mov     eax, ebx
0x18002a91c  jmp     short loc_18002A8C1
0x18002a91e  mov     ecx, 7
0x18002a923  call    __scrt_fastfail
0x180045899  push    rbp
0x18004589b  sub     rsp, 20h
0x18004589f  mov     rbp, rdx
0x1800458a2  mov     cl, [rbp+20h]
0x1800458a5  call    __scrt_release_startup_lock
0x1800458aa  nop
0x1800458ab  add     rsp, 20h
0x1800458af  pop     rbp
0x1800458b0  retn
0x1800458b2  push    rbp
0x1800458b4  sub     rsp, 20h
0x1800458b8  mov     rbp, rdx
0x1800458bb  add     rsp, 20h
0x1800458bf  pop     rbp
0x1800458c0  jmp     __scrt_dllmain_uninitialize_critical
```
