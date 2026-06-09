# dllmain_crt_process_detach

- ea: `0x180001668`
- end: `0x1800016eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x180001668`
- `0x180001974`
- `0x1800019ac`
- `0x180001ad4`
- `0x180001b0c`
- `0x180001c9c`
- `0x180001cc8`
- `0x180001d08`
- `0x180001d58`

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

  if ( dword_180039610 <= 0 )
    return 0;
  --dword_180039610;
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
0x180001668  mov     [rsp+arg_0], rbx
0x18000166d  push    rdi
0x18000166e  sub     rsp, 30h
0x180001672  mov     dil, cl
0x180001675  mov     eax, cs:dword_180039610
0x18000167b  test    eax, eax
0x18000167d  jg      short loc_18000168C
0x18000167f  xor     eax, eax
0x180001681  mov     rbx, [rsp+38h+arg_0]
0x180001686  add     rsp, 30h
0x18000168a  pop     rdi
0x18000168b  retn
0x18000168c  dec     eax
0x18000168e  mov     cs:dword_180039610, eax
0x180001694  call    __scrt_acquire_startup_lock
0x180001699  mov     bl, al
0x18000169b  mov     [rsp+38h+var_18], al
0x18000169f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800016a6  jnz     short loc_1800016DE
0x1800016a8  call    __scrt_dllmain_uninitialize_c
0x1800016ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800016b2  call    _RTC_Terminate
0x1800016b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800016c1  mov     cl, bl
0x1800016c3  call    __scrt_release_startup_lock
0x1800016c8  xor     edx, edx
0x1800016ca  mov     cl, dil
0x1800016cd  call    __scrt_uninitialize_crt
0x1800016d2  movzx   ebx, al
0x1800016d5  call    __scrt_dllmain_uninitialize_critical
0x1800016da  mov     eax, ebx
0x1800016dc  jmp     short loc_180001681
0x1800016de  mov     ecx, 7
0x1800016e3  call    __scrt_fastfail
0x180020fd9  push    rbp
0x180020fdb  sub     rsp, 20h
0x180020fdf  mov     rbp, rdx
0x180020fe2  mov     cl, [rbp+20h]
0x180020fe5  call    __scrt_release_startup_lock
0x180020fea  nop
0x180020feb  add     rsp, 20h
0x180020fef  pop     rbp
0x180020ff0  retn
0x180020ff2  push    rbp
0x180020ff4  sub     rsp, 20h
0x180020ff8  mov     rbp, rdx
0x180020ffb  add     rsp, 20h
0x180020fff  pop     rbp
0x180021000  jmp     __scrt_dllmain_uninitialize_critical
```
