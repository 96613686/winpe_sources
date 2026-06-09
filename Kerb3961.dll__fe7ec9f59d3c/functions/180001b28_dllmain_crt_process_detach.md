# dllmain_crt_process_detach

- ea: `0x180001b28`
- end: `0x180001bab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x180001b28`
- `0x180001d70`
- `0x180001e98`
- `0x180001ed0`
- `0x180002060`
- `0x18000208c`
- `0x180002210`
- `0x180002258`
- `0x1800022a8`

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

  if ( dword_1800298B0 <= 0 )
    return 0;
  --dword_1800298B0;
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
0x180001b28  mov     [rsp+arg_0], rbx
0x180001b2d  push    rdi
0x180001b2e  sub     rsp, 30h
0x180001b32  mov     dil, cl
0x180001b35  mov     eax, cs:dword_1800298B0
0x180001b3b  test    eax, eax
0x180001b3d  jg      short loc_180001B4C
0x180001b3f  xor     eax, eax
0x180001b41  mov     rbx, [rsp+38h+arg_0]
0x180001b46  add     rsp, 30h
0x180001b4a  pop     rdi
0x180001b4b  retn
0x180001b4c  dec     eax
0x180001b4e  mov     cs:dword_1800298B0, eax
0x180001b54  call    __scrt_acquire_startup_lock
0x180001b59  mov     bl, al
0x180001b5b  mov     [rsp+38h+var_18], al
0x180001b5f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001b66  jnz     short loc_180001B9E
0x180001b68  call    __scrt_dllmain_uninitialize_c
0x180001b6d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001b72  call    _RTC_Terminate
0x180001b77  mov     cs:__scrt_current_native_startup_state, 0
0x180001b81  mov     cl, bl
0x180001b83  call    __scrt_release_startup_lock
0x180001b88  xor     edx, edx
0x180001b8a  mov     cl, dil
0x180001b8d  call    __scrt_uninitialize_crt
0x180001b92  movzx   ebx, al
0x180001b95  call    __scrt_dllmain_uninitialize_critical
0x180001b9a  mov     eax, ebx
0x180001b9c  jmp     short loc_180001B41
0x180001b9e  mov     ecx, 7
0x180001ba3  call    __scrt_fastfail
0x18001d409  push    rbp
0x18001d40b  sub     rsp, 20h
0x18001d40f  mov     rbp, rdx
0x18001d412  mov     cl, [rbp+20h]
0x18001d415  call    __scrt_release_startup_lock
0x18001d41a  nop
0x18001d41b  add     rsp, 20h
0x18001d41f  pop     rbp
0x18001d420  retn
0x18001d422  push    rbp
0x18001d424  sub     rsp, 20h
0x18001d428  mov     rbp, rdx
0x18001d42b  add     rsp, 20h
0x18001d42f  pop     rbp
0x18001d430  jmp     __scrt_dllmain_uninitialize_critical
```
