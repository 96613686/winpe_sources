# dllmain_crt_process_detach

- ea: `0x180001fa8`
- end: `0x18000202b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001e50`

## callees

- `0x180001fa8`
- `0x18000224c`
- `0x180002374`
- `0x1800023ac`
- `0x18000253c`
- `0x180002568`
- `0x18000270c`
- `0x180002754`
- `0x1800027a4`

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

  if ( dword_18003BD10 <= 0 )
    return 0;
  --dword_18003BD10;
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
0x180001fa8  mov     [rsp+arg_0], rbx
0x180001fad  push    rdi
0x180001fae  sub     rsp, 30h
0x180001fb2  mov     dil, cl
0x180001fb5  mov     eax, cs:dword_18003BD10
0x180001fbb  test    eax, eax
0x180001fbd  jg      short loc_180001FCC
0x180001fbf  xor     eax, eax
0x180001fc1  mov     rbx, [rsp+38h+arg_0]
0x180001fc6  add     rsp, 30h
0x180001fca  pop     rdi
0x180001fcb  retn
0x180001fcc  dec     eax
0x180001fce  mov     cs:dword_18003BD10, eax
0x180001fd4  call    __scrt_acquire_startup_lock
0x180001fd9  mov     bl, al
0x180001fdb  mov     [rsp+38h+var_18], al
0x180001fdf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001fe6  jnz     short loc_18000201E
0x180001fe8  call    __scrt_dllmain_uninitialize_c
0x180001fed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001ff2  call    _RTC_Terminate
0x180001ff7  mov     cs:__scrt_current_native_startup_state, 0
0x180002001  mov     cl, bl
0x180002003  call    __scrt_release_startup_lock
0x180002008  xor     edx, edx
0x18000200a  mov     cl, dil
0x18000200d  call    __scrt_uninitialize_crt
0x180002012  movzx   ebx, al
0x180002015  call    __scrt_dllmain_uninitialize_critical
0x18000201a  mov     eax, ebx
0x18000201c  jmp     short loc_180001FC1
0x18000201e  mov     ecx, 7
0x180002023  call    __scrt_fastfail
0x180029969  push    rbp
0x18002996b  sub     rsp, 20h
0x18002996f  mov     rbp, rdx
0x180029972  mov     cl, [rbp+20h]
0x180029975  call    __scrt_release_startup_lock
0x18002997a  nop
0x18002997b  add     rsp, 20h
0x18002997f  pop     rbp
0x180029980  retn
0x180029982  push    rbp
0x180029984  sub     rsp, 20h
0x180029988  mov     rbp, rdx
0x18002998b  add     rsp, 20h
0x18002998f  pop     rbp
0x180029990  jmp     __scrt_dllmain_uninitialize_critical
```
