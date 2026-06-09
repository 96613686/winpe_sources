# dllmain_crt_process_detach

- ea: `0x180001cb8`
- end: `0x180001d3b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001b60`

## callees

- `0x180001cb8`
- `0x180001ef4`
- `0x18000201c`
- `0x180002054`
- `0x1800021e4`
- `0x180002210`
- `0x1800023ac`
- `0x1800023f4`
- `0x180002444`

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

  if ( dword_1800182B0 <= 0 )
    return 0;
  --dword_1800182B0;
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
0x180001cb8  mov     [rsp+arg_0], rbx
0x180001cbd  push    rdi
0x180001cbe  sub     rsp, 30h
0x180001cc2  mov     dil, cl
0x180001cc5  mov     eax, cs:dword_1800182B0
0x180001ccb  test    eax, eax
0x180001ccd  jg      short loc_180001CDC
0x180001ccf  xor     eax, eax
0x180001cd1  mov     rbx, [rsp+38h+arg_0]
0x180001cd6  add     rsp, 30h
0x180001cda  pop     rdi
0x180001cdb  retn
0x180001cdc  dec     eax
0x180001cde  mov     cs:dword_1800182B0, eax
0x180001ce4  call    __scrt_acquire_startup_lock
0x180001ce9  mov     bl, al
0x180001ceb  mov     [rsp+38h+var_18], al
0x180001cef  cmp     cs:__scrt_current_native_startup_state, 2
0x180001cf6  jnz     short loc_180001D2E
0x180001cf8  call    __scrt_dllmain_uninitialize_c
0x180001cfd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001d02  call    _RTC_Terminate
0x180001d07  mov     cs:__scrt_current_native_startup_state, 0
0x180001d11  mov     cl, bl
0x180001d13  call    __scrt_release_startup_lock
0x180001d18  xor     edx, edx
0x180001d1a  mov     cl, dil
0x180001d1d  call    __scrt_uninitialize_crt
0x180001d22  movzx   ebx, al
0x180001d25  call    __scrt_dllmain_uninitialize_critical
0x180001d2a  mov     eax, ebx
0x180001d2c  jmp     short loc_180001CD1
0x180001d2e  mov     ecx, 7
0x180001d33  call    __scrt_fastfail
0x180010119  push    rbp
0x18001011b  sub     rsp, 20h
0x18001011f  mov     rbp, rdx
0x180010122  mov     cl, [rbp+20h]
0x180010125  call    __scrt_release_startup_lock
0x18001012a  nop
0x18001012b  add     rsp, 20h
0x18001012f  pop     rbp
0x180010130  retn
0x180010132  push    rbp
0x180010134  sub     rsp, 20h
0x180010138  mov     rbp, rdx
0x18001013b  add     rsp, 20h
0x18001013f  pop     rbp
0x180010140  jmp     __scrt_dllmain_uninitialize_critical
```
