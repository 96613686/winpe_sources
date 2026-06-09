# dllmain_crt_process_detach

- ea: `0x180001648`
- end: `0x1800016cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800014f0`

## callees

- `0x180001648`
- `0x1800019c0`
- `0x180001ae8`
- `0x180001b20`
- `0x180001cb0`
- `0x180001cdc`
- `0x180001e68`
- `0x180001eb0`
- `0x180001f00`

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

  if ( dword_180036DD0 <= 0 )
    return 0;
  --dword_180036DD0;
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
0x180001648  mov     [rsp+arg_0], rbx
0x18000164d  push    rdi
0x18000164e  sub     rsp, 30h
0x180001652  mov     dil, cl
0x180001655  mov     eax, cs:dword_180036DD0
0x18000165b  test    eax, eax
0x18000165d  jg      short loc_18000166C
0x18000165f  xor     eax, eax
0x180001661  mov     rbx, [rsp+38h+arg_0]
0x180001666  add     rsp, 30h
0x18000166a  pop     rdi
0x18000166b  retn
0x18000166c  dec     eax
0x18000166e  mov     cs:dword_180036DD0, eax
0x180001674  call    __scrt_acquire_startup_lock
0x180001679  mov     bl, al
0x18000167b  mov     [rsp+38h+var_18], al
0x18000167f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001686  jnz     short loc_1800016BE
0x180001688  call    __scrt_dllmain_uninitialize_c
0x18000168d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001692  call    _RTC_Terminate
0x180001697  mov     cs:__scrt_current_native_startup_state, 0
0x1800016a1  mov     cl, bl
0x1800016a3  call    __scrt_release_startup_lock
0x1800016a8  xor     edx, edx
0x1800016aa  mov     cl, dil
0x1800016ad  call    __scrt_uninitialize_crt
0x1800016b2  movzx   ebx, al
0x1800016b5  call    __scrt_dllmain_uninitialize_critical
0x1800016ba  mov     eax, ebx
0x1800016bc  jmp     short loc_180001661
0x1800016be  mov     ecx, 7
0x1800016c3  call    __scrt_fastfail
0x180027c89  push    rbp
0x180027c8b  sub     rsp, 20h
0x180027c8f  mov     rbp, rdx
0x180027c92  mov     cl, [rbp+20h]
0x180027c95  call    __scrt_release_startup_lock
0x180027c9a  nop
0x180027c9b  add     rsp, 20h
0x180027c9f  pop     rbp
0x180027ca0  retn
0x180027ca2  push    rbp
0x180027ca4  sub     rsp, 20h
0x180027ca8  mov     rbp, rdx
0x180027cab  add     rsp, 20h
0x180027caf  pop     rbp
0x180027cb0  jmp     __scrt_dllmain_uninitialize_critical
```
