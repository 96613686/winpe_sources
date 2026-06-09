# dllmain_crt_process_detach

- ea: `0x180002858`
- end: `0x1800028db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002700`

## callees

- `0x180002858`
- `0x180002bcc`
- `0x180002cf4`
- `0x180002d2c`
- `0x180002ebc`
- `0x180002ee8`
- `0x18000310c`
- `0x180003154`
- `0x1800031a4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C270 <= 0 )
    return 0;
  --dword_18001C270;
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
0x180002858  mov     [rsp+arg_0], rbx
0x18000285d  push    rdi
0x18000285e  sub     rsp, 30h
0x180002862  mov     dil, cl
0x180002865  mov     eax, cs:dword_18001C270
0x18000286b  test    eax, eax
0x18000286d  jg      short loc_18000287C
0x18000286f  xor     eax, eax
0x180002871  mov     rbx, [rsp+38h+arg_0]
0x180002876  add     rsp, 30h
0x18000287a  pop     rdi
0x18000287b  retn
0x18000287c  dec     eax
0x18000287e  mov     cs:dword_18001C270, eax
0x180002884  call    __scrt_acquire_startup_lock
0x180002889  mov     bl, al
0x18000288b  mov     [rsp+38h+var_18], al
0x18000288f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002896  jnz     short loc_1800028CE
0x180002898  call    __scrt_dllmain_uninitialize_c
0x18000289d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800028a2  call    _RTC_Terminate
0x1800028a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800028b1  mov     cl, bl
0x1800028b3  call    __scrt_release_startup_lock
0x1800028b8  xor     edx, edx
0x1800028ba  mov     cl, dil
0x1800028bd  call    __scrt_uninitialize_crt
0x1800028c2  movzx   ebx, al
0x1800028c5  call    __scrt_dllmain_uninitialize_critical
0x1800028ca  mov     eax, ebx
0x1800028cc  jmp     short loc_180002871
0x1800028ce  mov     ecx, 7
0x1800028d3  call    __scrt_fastfail
0x180010ef9  push    rbp
0x180010efb  sub     rsp, 20h
0x180010eff  mov     rbp, rdx
0x180010f02  mov     cl, [rbp+20h]
0x180010f05  call    __scrt_release_startup_lock
0x180010f0a  nop
0x180010f0b  add     rsp, 20h
0x180010f0f  pop     rbp
0x180010f10  retn
0x180010f12  push    rbp
0x180010f14  sub     rsp, 20h
0x180010f18  mov     rbp, rdx
0x180010f1b  add     rsp, 20h
0x180010f1f  pop     rbp
0x180010f20  jmp     __scrt_dllmain_uninitialize_critical
```
