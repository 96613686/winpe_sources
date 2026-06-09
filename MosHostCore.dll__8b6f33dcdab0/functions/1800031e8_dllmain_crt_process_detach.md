# dllmain_crt_process_detach

- ea: `0x1800031e8`
- end: `0x18000326b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003090`

## callees

- `0x1800031e8`
- `0x180003440`
- `0x180003568`
- `0x1800035a0`
- `0x180003730`
- `0x18000375c`
- `0x180003c94`
- `0x180003cdc`
- `0x180003d2c`

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

  if ( dword_1800353D0 <= 0 )
    return 0;
  --dword_1800353D0;
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
0x1800031e8  mov     [rsp+arg_0], rbx
0x1800031ed  push    rdi
0x1800031ee  sub     rsp, 30h
0x1800031f2  mov     dil, cl
0x1800031f5  mov     eax, cs:dword_1800353D0
0x1800031fb  test    eax, eax
0x1800031fd  jg      short loc_18000320C
0x1800031ff  xor     eax, eax
0x180003201  mov     rbx, [rsp+38h+arg_0]
0x180003206  add     rsp, 30h
0x18000320a  pop     rdi
0x18000320b  retn
0x18000320c  dec     eax
0x18000320e  mov     cs:dword_1800353D0, eax
0x180003214  call    __scrt_acquire_startup_lock
0x180003219  mov     bl, al
0x18000321b  mov     [rsp+38h+var_18], al
0x18000321f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003226  jnz     short loc_18000325E
0x180003228  call    __scrt_dllmain_uninitialize_c
0x18000322d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003232  call    _RTC_Terminate
0x180003237  mov     cs:__scrt_current_native_startup_state, 0
0x180003241  mov     cl, bl
0x180003243  call    __scrt_release_startup_lock
0x180003248  xor     edx, edx
0x18000324a  mov     cl, dil
0x18000324d  call    __scrt_uninitialize_crt
0x180003252  movzx   ebx, al
0x180003255  call    __scrt_dllmain_uninitialize_critical
0x18000325a  mov     eax, ebx
0x18000325c  jmp     short loc_180003201
0x18000325e  mov     ecx, 7
0x180003263  call    __scrt_fastfail
0x180022fc9  push    rbp
0x180022fcb  sub     rsp, 20h
0x180022fcf  mov     rbp, rdx
0x180022fd2  mov     cl, [rbp+20h]
0x180022fd5  call    __scrt_release_startup_lock
0x180022fda  nop
0x180022fdb  add     rsp, 20h
0x180022fdf  pop     rbp
0x180022fe0  retn
0x180022fe2  push    rbp
0x180022fe4  sub     rsp, 20h
0x180022fe8  mov     rbp, rdx
0x180022feb  add     rsp, 20h
0x180022fef  pop     rbp
0x180022ff0  jmp     __scrt_dllmain_uninitialize_critical
```
