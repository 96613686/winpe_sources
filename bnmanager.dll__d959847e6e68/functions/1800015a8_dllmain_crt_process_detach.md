# dllmain_crt_process_detach

- ea: `0x1800015a8`
- end: `0x18000162b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x1800015a8`
- `0x18000181c`
- `0x180001944`
- `0x18000197c`
- `0x180001b0c`
- `0x180001b38`
- `0x180002028`
- `0x180002070`
- `0x1800020c0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180014690 <= 0 )
    return 0;
  --dword_180014690;
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
0x1800015a8  mov     [rsp+arg_0], rbx
0x1800015ad  push    rdi
0x1800015ae  sub     rsp, 30h
0x1800015b2  mov     dil, cl
0x1800015b5  mov     eax, cs:dword_180014690
0x1800015bb  test    eax, eax
0x1800015bd  jg      short loc_1800015CC
0x1800015bf  xor     eax, eax
0x1800015c1  mov     rbx, [rsp+38h+arg_0]
0x1800015c6  add     rsp, 30h
0x1800015ca  pop     rdi
0x1800015cb  retn
0x1800015cc  dec     eax
0x1800015ce  mov     cs:dword_180014690, eax
0x1800015d4  call    __scrt_acquire_startup_lock
0x1800015d9  mov     bl, al
0x1800015db  mov     [rsp+38h+var_18], al
0x1800015df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800015e6  jnz     short loc_18000161E
0x1800015e8  call    __scrt_dllmain_uninitialize_c
0x1800015ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800015f2  call    _RTC_Terminate
0x1800015f7  mov     cs:__scrt_current_native_startup_state, 0
0x180001601  mov     cl, bl
0x180001603  call    __scrt_release_startup_lock
0x180001608  xor     edx, edx
0x18000160a  mov     cl, dil
0x18000160d  call    __scrt_uninitialize_crt
0x180001612  movzx   ebx, al
0x180001615  call    __scrt_dllmain_uninitialize_critical
0x18000161a  mov     eax, ebx
0x18000161c  jmp     short loc_1800015C1
0x18000161e  mov     ecx, 7
0x180001623  call    __scrt_fastfail
0x18000cb59  push    rbp
0x18000cb5b  sub     rsp, 20h
0x18000cb5f  mov     rbp, rdx
0x18000cb62  mov     cl, [rbp+20h]
0x18000cb65  call    __scrt_release_startup_lock
0x18000cb6a  nop
0x18000cb6b  add     rsp, 20h
0x18000cb6f  pop     rbp
0x18000cb70  retn
0x18000cb72  push    rbp
0x18000cb74  sub     rsp, 20h
0x18000cb78  mov     rbp, rdx
0x18000cb7b  add     rsp, 20h
0x18000cb7f  pop     rbp
0x18000cb80  jmp     __scrt_dllmain_uninitialize_critical
```
