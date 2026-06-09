# dllmain_crt_process_detach

- ea: `0x180001508`
- end: `0x18000158b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800013b0`

## callees

- `0x180001508`
- `0x180001798`
- `0x1800018c0`
- `0x1800018f8`
- `0x180001a88`
- `0x180001ab4`
- `0x180001c14`
- `0x180001c5c`
- `0x180001cac`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_1800071D0 <= 0 )
    return 0;
  --dword_1800071D0;
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
0x180001508  mov     [rsp+arg_0], rbx
0x18000150d  push    rdi
0x18000150e  sub     rsp, 30h
0x180001512  mov     dil, cl
0x180001515  mov     eax, cs:dword_1800071D0
0x18000151b  test    eax, eax
0x18000151d  jg      short loc_18000152C
0x18000151f  xor     eax, eax
0x180001521  mov     rbx, [rsp+38h+arg_0]
0x180001526  add     rsp, 30h
0x18000152a  pop     rdi
0x18000152b  retn
0x18000152c  dec     eax
0x18000152e  mov     cs:dword_1800071D0, eax
0x180001534  call    __scrt_acquire_startup_lock
0x180001539  mov     bl, al
0x18000153b  mov     [rsp+38h+var_18], al
0x18000153f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001546  jnz     short loc_18000157E
0x180001548  call    __scrt_dllmain_uninitialize_c
0x18000154d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001552  call    _RTC_Terminate
0x180001557  mov     cs:__scrt_current_native_startup_state, 0
0x180001561  mov     cl, bl
0x180001563  call    __scrt_release_startup_lock
0x180001568  xor     edx, edx
0x18000156a  mov     cl, dil
0x18000156d  call    __scrt_uninitialize_crt
0x180001572  movzx   ebx, al
0x180001575  call    __scrt_dllmain_uninitialize_critical
0x18000157a  mov     eax, ebx
0x18000157c  jmp     short loc_180001521
0x18000157e  mov     ecx, 7
0x180001583  call    __scrt_fastfail
0x180003bc9  push    rbp
0x180003bcb  sub     rsp, 20h
0x180003bcf  mov     rbp, rdx
0x180003bd2  mov     cl, [rbp+20h]
0x180003bd5  call    __scrt_release_startup_lock
0x180003bda  nop
0x180003bdb  add     rsp, 20h
0x180003bdf  pop     rbp
0x180003be0  retn
0x180003be2  push    rbp
0x180003be4  sub     rsp, 20h
0x180003be8  mov     rbp, rdx
0x180003beb  add     rsp, 20h
0x180003bef  pop     rbp
0x180003bf0  jmp     __scrt_dllmain_uninitialize_critical
```
