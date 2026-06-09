# dllmain_crt_process_detach

- ea: `0x18000d088`
- end: `0x18000d10b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000cf30`

## callees

- `0x18000d088`
- `0x18000d3cc`
- `0x18000d4f4`
- `0x18000d52c`
- `0x18000d6bc`
- `0x18000d6e8`
- `0x18000dc70`
- `0x18000dcb8`
- `0x18000dd08`

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

  if ( dword_180037A90 <= 0 )
    return 0;
  --dword_180037A90;
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
0x18000d088  mov     [rsp+arg_0], rbx
0x18000d08d  push    rdi
0x18000d08e  sub     rsp, 30h
0x18000d092  mov     dil, cl
0x18000d095  mov     eax, cs:dword_180037A90
0x18000d09b  test    eax, eax
0x18000d09d  jg      short loc_18000D0AC
0x18000d09f  xor     eax, eax
0x18000d0a1  mov     rbx, [rsp+38h+arg_0]
0x18000d0a6  add     rsp, 30h
0x18000d0aa  pop     rdi
0x18000d0ab  retn
0x18000d0ac  dec     eax
0x18000d0ae  mov     cs:dword_180037A90, eax
0x18000d0b4  call    __scrt_acquire_startup_lock
0x18000d0b9  mov     bl, al
0x18000d0bb  mov     [rsp+38h+var_18], al
0x18000d0bf  cmp     cs:__scrt_current_native_startup_state, 2
0x18000d0c6  jnz     short loc_18000D0FE
0x18000d0c8  call    __scrt_dllmain_uninitialize_c
0x18000d0cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000d0d2  call    _RTC_Terminate
0x18000d0d7  mov     cs:__scrt_current_native_startup_state, 0
0x18000d0e1  mov     cl, bl
0x18000d0e3  call    __scrt_release_startup_lock
0x18000d0e8  xor     edx, edx
0x18000d0ea  mov     cl, dil
0x18000d0ed  call    __scrt_uninitialize_crt
0x18000d0f2  movzx   ebx, al
0x18000d0f5  call    __scrt_dllmain_uninitialize_critical
0x18000d0fa  mov     eax, ebx
0x18000d0fc  jmp     short loc_18000D0A1
0x18000d0fe  mov     ecx, 7
0x18000d103  call    __scrt_fastfail
0x180025856  push    rbp
0x180025858  sub     rsp, 20h
0x18002585c  mov     rbp, rdx
0x18002585f  mov     cl, [rbp+20h]
0x180025862  call    __scrt_release_startup_lock
0x180025867  nop
0x180025868  add     rsp, 20h
0x18002586c  pop     rbp
0x18002586d  retn
0x18002586f  push    rbp
0x180025871  sub     rsp, 20h
0x180025875  mov     rbp, rdx
0x180025878  add     rsp, 20h
0x18002587c  pop     rbp
0x18002587d  jmp     __scrt_dllmain_uninitialize_critical
```
