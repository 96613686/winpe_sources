# dllmain_crt_process_detach

- ea: `0x1800029a8`
- end: `0x180002a2b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002850`

## callees

- `0x1800029a8`
- `0x180002be4`
- `0x180002d0c`
- `0x180002d44`
- `0x180002ed4`
- `0x180002f00`
- `0x18000309c`
- `0x1800030e4`
- `0x180003134`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180019430 <= 0 )
    return 0;
  --dword_180019430;
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
0x1800029a8  mov     [rsp+arg_0], rbx
0x1800029ad  push    rdi
0x1800029ae  sub     rsp, 30h
0x1800029b2  mov     dil, cl
0x1800029b5  mov     eax, cs:dword_180019430
0x1800029bb  test    eax, eax
0x1800029bd  jg      short loc_1800029CC
0x1800029bf  xor     eax, eax
0x1800029c1  mov     rbx, [rsp+38h+arg_0]
0x1800029c6  add     rsp, 30h
0x1800029ca  pop     rdi
0x1800029cb  retn
0x1800029cc  dec     eax
0x1800029ce  mov     cs:dword_180019430, eax
0x1800029d4  call    __scrt_acquire_startup_lock
0x1800029d9  mov     bl, al
0x1800029db  mov     [rsp+38h+var_18], al
0x1800029df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800029e6  jnz     short loc_180002A1E
0x1800029e8  call    __scrt_dllmain_uninitialize_c
0x1800029ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800029f2  call    _RTC_Terminate
0x1800029f7  mov     cs:__scrt_current_native_startup_state, 0
0x180002a01  mov     cl, bl
0x180002a03  call    __scrt_release_startup_lock
0x180002a08  xor     edx, edx
0x180002a0a  mov     cl, dil
0x180002a0d  call    __scrt_uninitialize_crt
0x180002a12  movzx   ebx, al
0x180002a15  call    __scrt_dllmain_uninitialize_critical
0x180002a1a  mov     eax, ebx
0x180002a1c  jmp     short loc_1800029C1
0x180002a1e  mov     ecx, 7
0x180002a23  call    __scrt_fastfail
0x180010ca9  push    rbp
0x180010cab  sub     rsp, 20h
0x180010caf  mov     rbp, rdx
0x180010cb2  mov     cl, [rbp+20h]
0x180010cb5  call    __scrt_release_startup_lock
0x180010cba  nop
0x180010cbb  add     rsp, 20h
0x180010cbf  pop     rbp
0x180010cc0  retn
0x180010cc2  push    rbp
0x180010cc4  sub     rsp, 20h
0x180010cc8  mov     rbp, rdx
0x180010ccb  add     rsp, 20h
0x180010ccf  pop     rbp
0x180010cd0  jmp     __scrt_dllmain_uninitialize_critical
```
