# dllmain_crt_process_detach

- ea: `0x180003a68`
- end: `0x180003aeb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003910`

## callees

- `0x180003a68`
- `0x180003d74`
- `0x180003dac`
- `0x180003ed4`
- `0x180003f0c`
- `0x18000409c`
- `0x1800040c8`
- `0x180004168`
- `0x1800041b8`

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

  if ( dword_1805E06F0 <= 0 )
    return 0;
  --dword_1805E06F0;
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
0x180003a68  mov     [rsp+arg_0], rbx
0x180003a6d  push    rdi
0x180003a6e  sub     rsp, 30h
0x180003a72  mov     dil, cl
0x180003a75  mov     eax, cs:dword_1805E06F0
0x180003a7b  test    eax, eax
0x180003a7d  jg      short loc_180003A8C
0x180003a7f  xor     eax, eax
0x180003a81  mov     rbx, [rsp+38h+arg_0]
0x180003a86  add     rsp, 30h
0x180003a8a  pop     rdi
0x180003a8b  retn
0x180003a8c  dec     eax
0x180003a8e  mov     cs:dword_1805E06F0, eax
0x180003a94  call    __scrt_acquire_startup_lock
0x180003a99  mov     bl, al
0x180003a9b  mov     [rsp+38h+var_18], al
0x180003a9f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003aa6  jnz     short loc_180003ADE
0x180003aa8  call    __scrt_dllmain_uninitialize_c
0x180003aad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003ab2  call    _RTC_Terminate
0x180003ab7  mov     cs:__scrt_current_native_startup_state, 0
0x180003ac1  mov     cl, bl
0x180003ac3  call    __scrt_release_startup_lock
0x180003ac8  xor     edx, edx
0x180003aca  mov     cl, dil
0x180003acd  call    __scrt_uninitialize_crt
0x180003ad2  movzx   ebx, al
0x180003ad5  call    __scrt_dllmain_uninitialize_critical
0x180003ada  mov     eax, ebx
0x180003adc  jmp     short loc_180003A81
0x180003ade  mov     ecx, 7
0x180003ae3  call    __scrt_fastfail
0x18000b374  push    rbp
0x18000b376  sub     rsp, 20h
0x18000b37a  mov     rbp, rdx
0x18000b37d  mov     cl, [rbp+20h]
0x18000b380  call    __scrt_release_startup_lock
0x18000b385  nop
0x18000b386  add     rsp, 20h
0x18000b38a  pop     rbp
0x18000b38b  retn
0x18000b38d  push    rbp
0x18000b38f  sub     rsp, 20h
0x18000b393  mov     rbp, rdx
0x18000b396  add     rsp, 20h
0x18000b39a  pop     rbp
0x18000b39b  jmp     __scrt_dllmain_uninitialize_critical
```
