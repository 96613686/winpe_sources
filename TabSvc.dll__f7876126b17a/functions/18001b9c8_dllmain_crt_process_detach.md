# dllmain_crt_process_detach

- ea: `0x18001b9c8`
- end: `0x18001ba4b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001b870`

## callees

- `0x18001b9c8`
- `0x18001bc44`
- `0x18001bd6c`
- `0x18001bda4`
- `0x18001bf34`
- `0x18001bf60`
- `0x18001c16c`
- `0x18001c1b4`
- `0x18001c204`

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

  if ( dword_1800418D0 <= 0 )
    return 0;
  --dword_1800418D0;
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
0x18001b9c8  mov     [rsp+arg_0], rbx
0x18001b9cd  push    rdi
0x18001b9ce  sub     rsp, 30h
0x18001b9d2  mov     dil, cl
0x18001b9d5  mov     eax, cs:dword_1800418D0
0x18001b9db  test    eax, eax
0x18001b9dd  jg      short loc_18001B9EC
0x18001b9df  xor     eax, eax
0x18001b9e1  mov     rbx, [rsp+38h+arg_0]
0x18001b9e6  add     rsp, 30h
0x18001b9ea  pop     rdi
0x18001b9eb  retn
0x18001b9ec  dec     eax
0x18001b9ee  mov     cs:dword_1800418D0, eax
0x18001b9f4  call    __scrt_acquire_startup_lock
0x18001b9f9  mov     bl, al
0x18001b9fb  mov     [rsp+38h+var_18], al
0x18001b9ff  cmp     cs:__scrt_current_native_startup_state, 2
0x18001ba06  jnz     short loc_18001BA3E
0x18001ba08  call    __scrt_dllmain_uninitialize_c
0x18001ba0d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001ba12  call    _RTC_Terminate
0x18001ba17  mov     cs:__scrt_current_native_startup_state, 0
0x18001ba21  mov     cl, bl
0x18001ba23  call    __scrt_release_startup_lock
0x18001ba28  xor     edx, edx
0x18001ba2a  mov     cl, dil
0x18001ba2d  call    __scrt_uninitialize_crt
0x18001ba32  movzx   ebx, al
0x18001ba35  call    __scrt_dllmain_uninitialize_critical
0x18001ba3a  mov     eax, ebx
0x18001ba3c  jmp     short loc_18001B9E1
0x18001ba3e  mov     ecx, 7
0x18001ba43  call    __scrt_fastfail
0x18002ff7d  push    rbp
0x18002ff7f  sub     rsp, 20h
0x18002ff83  mov     rbp, rdx
0x18002ff86  mov     cl, [rbp+20h]
0x18002ff89  call    __scrt_release_startup_lock
0x18002ff8e  nop
0x18002ff8f  add     rsp, 20h
0x18002ff93  pop     rbp
0x18002ff94  retn
0x18002ff96  push    rbp
0x18002ff98  sub     rsp, 20h
0x18002ff9c  mov     rbp, rdx
0x18002ff9f  add     rsp, 20h
0x18002ffa3  pop     rbp
0x18002ffa4  jmp     __scrt_dllmain_uninitialize_critical
```
