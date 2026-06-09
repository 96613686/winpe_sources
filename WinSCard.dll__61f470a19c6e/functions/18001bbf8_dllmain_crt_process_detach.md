# dllmain_crt_process_detach

- ea: `0x18001bbf8`
- end: `0x18001bc7b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001baa0`

## callees

- `0x18001bbf8`
- `0x18001be50`
- `0x18001bf78`
- `0x18001bfb0`
- `0x18001c140`
- `0x18001c16c`
- `0x18001c2fc`
- `0x18001c344`
- `0x18001c394`

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

  if ( dword_1800452D0 <= 0 )
    return 0;
  --dword_1800452D0;
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
0x18001bbf8  mov     [rsp+arg_0], rbx
0x18001bbfd  push    rdi
0x18001bbfe  sub     rsp, 30h
0x18001bc02  mov     dil, cl
0x18001bc05  mov     eax, cs:dword_1800452D0
0x18001bc0b  test    eax, eax
0x18001bc0d  jg      short loc_18001BC1C
0x18001bc0f  xor     eax, eax
0x18001bc11  mov     rbx, [rsp+38h+arg_0]
0x18001bc16  add     rsp, 30h
0x18001bc1a  pop     rdi
0x18001bc1b  retn
0x18001bc1c  dec     eax
0x18001bc1e  mov     cs:dword_1800452D0, eax
0x18001bc24  call    __scrt_acquire_startup_lock
0x18001bc29  mov     bl, al
0x18001bc2b  mov     [rsp+38h+var_18], al
0x18001bc2f  cmp     cs:__scrt_current_native_startup_state, 2
0x18001bc36  jnz     short loc_18001BC6E
0x18001bc38  call    __scrt_dllmain_uninitialize_c
0x18001bc3d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001bc42  call    _RTC_Terminate
0x18001bc47  mov     cs:__scrt_current_native_startup_state, 0
0x18001bc51  mov     cl, bl
0x18001bc53  call    __scrt_release_startup_lock
0x18001bc58  xor     edx, edx
0x18001bc5a  mov     cl, dil
0x18001bc5d  call    __scrt_uninitialize_crt
0x18001bc62  movzx   ebx, al
0x18001bc65  call    __scrt_dllmain_uninitialize_critical
0x18001bc6a  mov     eax, ebx
0x18001bc6c  jmp     short loc_18001BC11
0x18001bc6e  mov     ecx, 7
0x18001bc73  call    __scrt_fastfail
0x1800319e6  push    rbp
0x1800319e8  sub     rsp, 20h
0x1800319ec  mov     rbp, rdx
0x1800319ef  mov     cl, [rbp+20h]
0x1800319f2  call    __scrt_release_startup_lock
0x1800319f7  nop
0x1800319f8  add     rsp, 20h
0x1800319fc  pop     rbp
0x1800319fd  retn
0x1800319ff  push    rbp
0x180031a01  sub     rsp, 20h
0x180031a05  mov     rbp, rdx
0x180031a08  add     rsp, 20h
0x180031a0c  pop     rbp
0x180031a0d  jmp     __scrt_dllmain_uninitialize_critical
```
