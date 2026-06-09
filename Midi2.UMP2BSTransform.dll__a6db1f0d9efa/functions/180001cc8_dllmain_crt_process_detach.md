# dllmain_crt_process_detach

- ea: `0x180001cc8`
- end: `0x180001d4b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001b70`

## callees

- `0x180001cc8`
- `0x180001f84`
- `0x1800020ac`
- `0x1800020e4`
- `0x180002274`
- `0x1800022a0`
- `0x180002460`
- `0x1800024a8`
- `0x1800024f8`

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

  if ( dword_180015430 <= 0 )
    return 0;
  --dword_180015430;
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
0x180001cc8  mov     [rsp+arg_0], rbx
0x180001ccd  push    rdi
0x180001cce  sub     rsp, 30h
0x180001cd2  mov     dil, cl
0x180001cd5  mov     eax, cs:dword_180015430
0x180001cdb  test    eax, eax
0x180001cdd  jg      short loc_180001CEC
0x180001cdf  xor     eax, eax
0x180001ce1  mov     rbx, [rsp+38h+arg_0]
0x180001ce6  add     rsp, 30h
0x180001cea  pop     rdi
0x180001ceb  retn
0x180001cec  dec     eax
0x180001cee  mov     cs:dword_180015430, eax
0x180001cf4  call    __scrt_acquire_startup_lock
0x180001cf9  mov     bl, al
0x180001cfb  mov     [rsp+38h+var_18], al
0x180001cff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001d06  jnz     short loc_180001D3E
0x180001d08  call    __scrt_dllmain_uninitialize_c
0x180001d0d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001d12  call    _RTC_Terminate
0x180001d17  mov     cs:__scrt_current_native_startup_state, 0
0x180001d21  mov     cl, bl
0x180001d23  call    __scrt_release_startup_lock
0x180001d28  xor     edx, edx
0x180001d2a  mov     cl, dil
0x180001d2d  call    __scrt_uninitialize_crt
0x180001d32  movzx   ebx, al
0x180001d35  call    __scrt_dllmain_uninitialize_critical
0x180001d3a  mov     eax, ebx
0x180001d3c  jmp     short loc_180001CE1
0x180001d3e  mov     ecx, 7
0x180001d43  call    __scrt_fastfail
0x18000e999  push    rbp
0x18000e99b  sub     rsp, 20h
0x18000e99f  mov     rbp, rdx
0x18000e9a2  mov     cl, [rbp+20h]
0x18000e9a5  call    __scrt_release_startup_lock
0x18000e9aa  nop
0x18000e9ab  add     rsp, 20h
0x18000e9af  pop     rbp
0x18000e9b0  retn
0x18000e9b2  push    rbp
0x18000e9b4  sub     rsp, 20h
0x18000e9b8  mov     rbp, rdx
0x18000e9bb  add     rsp, 20h
0x18000e9bf  pop     rbp
0x18000e9c0  jmp     __scrt_dllmain_uninitialize_critical
```
