# dllmain_crt_process_detach

- ea: `0x180001b28`
- end: `0x180001bab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x180001b28`
- `0x180001d64`
- `0x180001e8c`
- `0x180001ec4`
- `0x180002054`
- `0x180002080`
- `0x18000251c`
- `0x180002564`
- `0x1800025b4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800234D0 <= 0 )
    return 0;
  --dword_1800234D0;
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
0x180001b28  mov     [rsp+arg_0], rbx
0x180001b2d  push    rdi
0x180001b2e  sub     rsp, 30h
0x180001b32  mov     dil, cl
0x180001b35  mov     eax, cs:dword_1800234D0
0x180001b3b  test    eax, eax
0x180001b3d  jg      short loc_180001B4C
0x180001b3f  xor     eax, eax
0x180001b41  mov     rbx, [rsp+38h+arg_0]
0x180001b46  add     rsp, 30h
0x180001b4a  pop     rdi
0x180001b4b  retn
0x180001b4c  dec     eax
0x180001b4e  mov     cs:dword_1800234D0, eax
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
0x180017f19  push    rbp
0x180017f1b  sub     rsp, 20h
0x180017f1f  mov     rbp, rdx
0x180017f22  mov     cl, [rbp+20h]
0x180017f25  call    __scrt_release_startup_lock
0x180017f2a  nop
0x180017f2b  add     rsp, 20h
0x180017f2f  pop     rbp
0x180017f30  retn
0x180017f32  push    rbp
0x180017f34  sub     rsp, 20h
0x180017f38  mov     rbp, rdx
0x180017f3b  add     rsp, 20h
0x180017f3f  pop     rbp
0x180017f40  jmp     __scrt_dllmain_uninitialize_critical
```
