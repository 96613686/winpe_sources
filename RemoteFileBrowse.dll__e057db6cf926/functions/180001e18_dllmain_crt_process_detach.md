# dllmain_crt_process_detach

- ea: `0x180001e18`
- end: `0x180001e9b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001cc0`

## callees

- `0x180001e18`
- `0x180002100`
- `0x180002228`
- `0x180002260`
- `0x1800023f0`
- `0x18000241c`
- `0x180002b2c`
- `0x180002b74`
- `0x180002bc4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180023470 <= 0 )
    return 0;
  --dword_180023470;
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
0x180001e18  mov     [rsp+arg_0], rbx
0x180001e1d  push    rdi
0x180001e1e  sub     rsp, 30h
0x180001e22  mov     dil, cl
0x180001e25  mov     eax, cs:dword_180023470
0x180001e2b  test    eax, eax
0x180001e2d  jg      short loc_180001E3C
0x180001e2f  xor     eax, eax
0x180001e31  mov     rbx, [rsp+38h+arg_0]
0x180001e36  add     rsp, 30h
0x180001e3a  pop     rdi
0x180001e3b  retn
0x180001e3c  dec     eax
0x180001e3e  mov     cs:dword_180023470, eax
0x180001e44  call    __scrt_acquire_startup_lock
0x180001e49  mov     bl, al
0x180001e4b  mov     [rsp+38h+var_18], al
0x180001e4f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001e56  jnz     short loc_180001E8E
0x180001e58  call    __scrt_dllmain_uninitialize_c
0x180001e5d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001e62  call    _RTC_Terminate
0x180001e67  mov     cs:__scrt_current_native_startup_state, 0
0x180001e71  mov     cl, bl
0x180001e73  call    __scrt_release_startup_lock
0x180001e78  xor     edx, edx
0x180001e7a  mov     cl, dil
0x180001e7d  call    __scrt_uninitialize_crt
0x180001e82  movzx   ebx, al
0x180001e85  call    __scrt_dllmain_uninitialize_critical
0x180001e8a  mov     eax, ebx
0x180001e8c  jmp     short loc_180001E31
0x180001e8e  mov     ecx, 7
0x180001e93  call    __scrt_fastfail
0x1800174c9  push    rbp
0x1800174cb  sub     rsp, 20h
0x1800174cf  mov     rbp, rdx
0x1800174d2  mov     cl, [rbp+20h]
0x1800174d5  call    __scrt_release_startup_lock
0x1800174da  nop
0x1800174db  add     rsp, 20h
0x1800174df  pop     rbp
0x1800174e0  retn
0x1800174e2  push    rbp
0x1800174e4  sub     rsp, 20h
0x1800174e8  mov     rbp, rdx
0x1800174eb  add     rsp, 20h
0x1800174ef  pop     rbp
0x1800174f0  jmp     __scrt_dllmain_uninitialize_critical
```
