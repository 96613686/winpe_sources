# dllmain_crt_process_detach

- ea: `0x180003f58`
- end: `0x180003fdb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003e00`

## callees

- `0x180003f58`
- `0x1800042e4`
- `0x18000440c`
- `0x180004444`
- `0x1800045d4`
- `0x180004600`
- `0x180004dac`
- `0x180004df4`
- `0x180004e44`

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

  if ( dword_18005F850 <= 0 )
    return 0;
  --dword_18005F850;
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
0x180003f58  mov     [rsp+arg_0], rbx
0x180003f5d  push    rdi
0x180003f5e  sub     rsp, 30h
0x180003f62  mov     dil, cl
0x180003f65  mov     eax, cs:dword_18005F850
0x180003f6b  test    eax, eax
0x180003f6d  jg      short loc_180003F7C
0x180003f6f  xor     eax, eax
0x180003f71  mov     rbx, [rsp+38h+arg_0]
0x180003f76  add     rsp, 30h
0x180003f7a  pop     rdi
0x180003f7b  retn
0x180003f7c  dec     eax
0x180003f7e  mov     cs:dword_18005F850, eax
0x180003f84  call    __scrt_acquire_startup_lock
0x180003f89  mov     bl, al
0x180003f8b  mov     [rsp+38h+var_18], al
0x180003f8f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003f96  jnz     short loc_180003FCE
0x180003f98  call    __scrt_dllmain_uninitialize_c
0x180003f9d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003fa2  call    _RTC_Terminate
0x180003fa7  mov     cs:__scrt_current_native_startup_state, 0
0x180003fb1  mov     cl, bl
0x180003fb3  call    __scrt_release_startup_lock
0x180003fb8  xor     edx, edx
0x180003fba  mov     cl, dil
0x180003fbd  call    __scrt_uninitialize_crt
0x180003fc2  movzx   ebx, al
0x180003fc5  call    __scrt_dllmain_uninitialize_critical
0x180003fca  mov     eax, ebx
0x180003fcc  jmp     short loc_180003F71
0x180003fce  mov     ecx, 7
0x180003fd3  call    __scrt_fastfail
0x1800301b9  push    rbp
0x1800301bb  sub     rsp, 20h
0x1800301bf  mov     rbp, rdx
0x1800301c2  mov     cl, [rbp+20h]
0x1800301c5  call    __scrt_release_startup_lock
0x1800301ca  nop
0x1800301cb  add     rsp, 20h
0x1800301cf  pop     rbp
0x1800301d0  retn
0x1800301d2  push    rbp
0x1800301d4  sub     rsp, 20h
0x1800301d8  mov     rbp, rdx
0x1800301db  add     rsp, 20h
0x1800301df  pop     rbp
0x1800301e0  jmp     __scrt_dllmain_uninitialize_critical
```
