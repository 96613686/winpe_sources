# dllmain_crt_process_detach

- ea: `0x18000e528`
- end: `0x18000e5ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000e3d0`

## callees

- `0x18000e528`
- `0x18000e810`
- `0x18000e848`
- `0x18000e970`
- `0x18000e9a8`
- `0x18000eb38`
- `0x18000eb64`
- `0x18000eba4`
- `0x18000ebf4`

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

  if ( dword_18001B110 <= 0 )
    return 0;
  --dword_18001B110;
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
0x18000e528  mov     [rsp+arg_0], rbx
0x18000e52d  push    rdi
0x18000e52e  sub     rsp, 30h
0x18000e532  mov     dil, cl
0x18000e535  mov     eax, cs:dword_18001B110
0x18000e53b  test    eax, eax
0x18000e53d  jg      short loc_18000E54C
0x18000e53f  xor     eax, eax
0x18000e541  mov     rbx, [rsp+38h+arg_0]
0x18000e546  add     rsp, 30h
0x18000e54a  pop     rdi
0x18000e54b  retn
0x18000e54c  dec     eax
0x18000e54e  mov     cs:dword_18001B110, eax
0x18000e554  call    __scrt_acquire_startup_lock
0x18000e559  mov     bl, al
0x18000e55b  mov     [rsp+38h+var_18], al
0x18000e55f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000e566  jnz     short loc_18000E59E
0x18000e568  call    __scrt_dllmain_uninitialize_c
0x18000e56d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000e572  call    _RTC_Terminate
0x18000e577  mov     cs:__scrt_current_native_startup_state, 0
0x18000e581  mov     cl, bl
0x18000e583  call    __scrt_release_startup_lock
0x18000e588  xor     edx, edx
0x18000e58a  mov     cl, dil
0x18000e58d  call    __scrt_uninitialize_crt
0x18000e592  movzx   ebx, al
0x18000e595  call    __scrt_dllmain_uninitialize_critical
0x18000e59a  mov     eax, ebx
0x18000e59c  jmp     short loc_18000E541
0x18000e59e  mov     ecx, 7
0x18000e5a3  call    __scrt_fastfail
0x180011559  push    rbp
0x18001155b  sub     rsp, 20h
0x18001155f  mov     rbp, rdx
0x180011562  mov     cl, [rbp+20h]
0x180011565  call    __scrt_release_startup_lock
0x18001156a  nop
0x18001156b  add     rsp, 20h
0x18001156f  pop     rbp
0x180011570  retn
0x180011572  push    rbp
0x180011574  sub     rsp, 20h
0x180011578  mov     rbp, rdx
0x18001157b  add     rsp, 20h
0x18001157f  pop     rbp
0x180011580  jmp     __scrt_dllmain_uninitialize_critical
```
