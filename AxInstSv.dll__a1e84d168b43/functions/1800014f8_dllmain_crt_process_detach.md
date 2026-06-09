# dllmain_crt_process_detach

- ea: `0x1800014f8`
- end: `0x18000157b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800013a0`

## callees

- `0x1800014f8`
- `0x180001810`
- `0x180001938`
- `0x180001970`
- `0x180001b00`
- `0x180001b2c`
- `0x180001c98`
- `0x180001ce0`
- `0x180001d30`

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

  if ( dword_180021350 <= 0 )
    return 0;
  --dword_180021350;
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
0x1800014f8  mov     [rsp+arg_0], rbx
0x1800014fd  push    rdi
0x1800014fe  sub     rsp, 30h
0x180001502  mov     dil, cl
0x180001505  mov     eax, cs:dword_180021350
0x18000150b  test    eax, eax
0x18000150d  jg      short loc_18000151C
0x18000150f  xor     eax, eax
0x180001511  mov     rbx, [rsp+38h+arg_0]
0x180001516  add     rsp, 30h
0x18000151a  pop     rdi
0x18000151b  retn
0x18000151c  dec     eax
0x18000151e  mov     cs:dword_180021350, eax
0x180001524  call    __scrt_acquire_startup_lock
0x180001529  mov     bl, al
0x18000152b  mov     [rsp+38h+var_18], al
0x18000152f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001536  jnz     short loc_18000156E
0x180001538  call    __scrt_dllmain_uninitialize_c
0x18000153d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001542  call    _RTC_Terminate
0x180001547  mov     cs:__scrt_current_native_startup_state, 0
0x180001551  mov     cl, bl
0x180001553  call    __scrt_release_startup_lock
0x180001558  xor     edx, edx
0x18000155a  mov     cl, dil
0x18000155d  call    __scrt_uninitialize_crt
0x180001562  movzx   ebx, al
0x180001565  call    __scrt_dllmain_uninitialize_critical
0x18000156a  mov     eax, ebx
0x18000156c  jmp     short loc_180001511
0x18000156e  mov     ecx, 7
0x180001573  call    __scrt_fastfail
0x1800143b9  push    rbp
0x1800143bb  sub     rsp, 20h
0x1800143bf  mov     rbp, rdx
0x1800143c2  mov     cl, [rbp+20h]
0x1800143c5  call    __scrt_release_startup_lock
0x1800143ca  nop
0x1800143cb  add     rsp, 20h
0x1800143cf  pop     rbp
0x1800143d0  retn
0x1800143d2  push    rbp
0x1800143d4  sub     rsp, 20h
0x1800143d8  mov     rbp, rdx
0x1800143db  add     rsp, 20h
0x1800143df  pop     rbp
0x1800143e0  jmp     __scrt_dllmain_uninitialize_critical
```
