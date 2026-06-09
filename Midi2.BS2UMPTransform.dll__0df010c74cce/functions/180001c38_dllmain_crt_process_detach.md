# dllmain_crt_process_detach

- ea: `0x180001c38`
- end: `0x180001cbb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001ae0`

## callees

- `0x180001c38`
- `0x180001ef4`
- `0x18000201c`
- `0x180002054`
- `0x1800021e4`
- `0x180002210`
- `0x1800023d0`
- `0x180002418`
- `0x180002468`

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

  if ( dword_180012390 <= 0 )
    return 0;
  --dword_180012390;
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
0x180001c38  mov     [rsp+arg_0], rbx
0x180001c3d  push    rdi
0x180001c3e  sub     rsp, 30h
0x180001c42  mov     dil, cl
0x180001c45  mov     eax, cs:dword_180012390
0x180001c4b  test    eax, eax
0x180001c4d  jg      short loc_180001C5C
0x180001c4f  xor     eax, eax
0x180001c51  mov     rbx, [rsp+38h+arg_0]
0x180001c56  add     rsp, 30h
0x180001c5a  pop     rdi
0x180001c5b  retn
0x180001c5c  dec     eax
0x180001c5e  mov     cs:dword_180012390, eax
0x180001c64  call    __scrt_acquire_startup_lock
0x180001c69  mov     bl, al
0x180001c6b  mov     [rsp+38h+var_18], al
0x180001c6f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001c76  jnz     short loc_180001CAE
0x180001c78  call    __scrt_dllmain_uninitialize_c
0x180001c7d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001c82  call    _RTC_Terminate
0x180001c87  mov     cs:__scrt_current_native_startup_state, 0
0x180001c91  mov     cl, bl
0x180001c93  call    __scrt_release_startup_lock
0x180001c98  xor     edx, edx
0x180001c9a  mov     cl, dil
0x180001c9d  call    __scrt_uninitialize_crt
0x180001ca2  movzx   ebx, al
0x180001ca5  call    __scrt_dllmain_uninitialize_critical
0x180001caa  mov     eax, ebx
0x180001cac  jmp     short loc_180001C51
0x180001cae  mov     ecx, 7
0x180001cb3  call    __scrt_fastfail
0x18000b499  push    rbp
0x18000b49b  sub     rsp, 20h
0x18000b49f  mov     rbp, rdx
0x18000b4a2  mov     cl, [rbp+20h]
0x18000b4a5  call    __scrt_release_startup_lock
0x18000b4aa  nop
0x18000b4ab  add     rsp, 20h
0x18000b4af  pop     rbp
0x18000b4b0  retn
0x18000b4b2  push    rbp
0x18000b4b4  sub     rsp, 20h
0x18000b4b8  mov     rbp, rdx
0x18000b4bb  add     rsp, 20h
0x18000b4bf  pop     rbp
0x18000b4c0  jmp     __scrt_dllmain_uninitialize_critical
```
