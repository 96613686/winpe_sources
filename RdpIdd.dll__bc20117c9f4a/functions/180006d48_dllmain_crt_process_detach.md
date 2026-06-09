# dllmain_crt_process_detach

- ea: `0x180006d48`
- end: `0x180006dcb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180006bf0`

## callees

- `0x180006d48`
- `0x180006fc8`
- `0x1800070f0`
- `0x180007128`
- `0x1800072b8`
- `0x1800072e4`
- `0x180007870`
- `0x1800078b8`
- `0x180007908`

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

  if ( dword_180057AB0 <= 0 )
    return 0;
  --dword_180057AB0;
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
0x180006d48  mov     [rsp+arg_0], rbx
0x180006d4d  push    rdi
0x180006d4e  sub     rsp, 30h
0x180006d52  mov     dil, cl
0x180006d55  mov     eax, cs:dword_180057AB0
0x180006d5b  test    eax, eax
0x180006d5d  jg      short loc_180006D6C
0x180006d5f  xor     eax, eax
0x180006d61  mov     rbx, [rsp+38h+arg_0]
0x180006d66  add     rsp, 30h
0x180006d6a  pop     rdi
0x180006d6b  retn
0x180006d6c  dec     eax
0x180006d6e  mov     cs:dword_180057AB0, eax
0x180006d74  call    __scrt_acquire_startup_lock
0x180006d79  mov     bl, al
0x180006d7b  mov     [rsp+38h+var_18], al
0x180006d7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180006d86  jnz     short loc_180006DBE
0x180006d88  call    __scrt_dllmain_uninitialize_c
0x180006d8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180006d92  call    _RTC_Terminate
0x180006d97  mov     cs:__scrt_current_native_startup_state, 0
0x180006da1  mov     cl, bl
0x180006da3  call    __scrt_release_startup_lock
0x180006da8  xor     edx, edx
0x180006daa  mov     cl, dil
0x180006dad  call    __scrt_uninitialize_crt
0x180006db2  movzx   ebx, al
0x180006db5  call    __scrt_dllmain_uninitialize_critical
0x180006dba  mov     eax, ebx
0x180006dbc  jmp     short loc_180006D61
0x180006dbe  mov     ecx, 7
0x180006dc3  call    __scrt_fastfail
0x18003b569  push    rbp
0x18003b56b  sub     rsp, 20h
0x18003b56f  mov     rbp, rdx
0x18003b572  mov     cl, [rbp+20h]
0x18003b575  call    __scrt_release_startup_lock
0x18003b57a  nop
0x18003b57b  add     rsp, 20h
0x18003b57f  pop     rbp
0x18003b580  retn
0x18003b582  push    rbp
0x18003b584  sub     rsp, 20h
0x18003b588  mov     rbp, rdx
0x18003b58b  add     rsp, 20h
0x18003b58f  pop     rbp
0x18003b590  jmp     __scrt_dllmain_uninitialize_critical
```
