# dllmain_crt_process_detach

- ea: `0x180015e08`
- end: `0x180015e8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180015cb0`

## callees

- `0x180015e08`
- `0x18001609c`
- `0x1800161c4`
- `0x1800161fc`
- `0x18001638c`
- `0x1800163b8`
- `0x180016518`
- `0x180016560`
- `0x1800165b0`

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

  if ( dword_180098DB0 <= 0 )
    return 0;
  --dword_180098DB0;
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
0x180015e08  mov     [rsp+arg_0], rbx
0x180015e0d  push    rdi
0x180015e0e  sub     rsp, 30h
0x180015e12  mov     dil, cl
0x180015e15  mov     eax, cs:dword_180098DB0
0x180015e1b  test    eax, eax
0x180015e1d  jg      short loc_180015E2C
0x180015e1f  xor     eax, eax
0x180015e21  mov     rbx, [rsp+38h+arg_0]
0x180015e26  add     rsp, 30h
0x180015e2a  pop     rdi
0x180015e2b  retn
0x180015e2c  dec     eax
0x180015e2e  mov     cs:dword_180098DB0, eax
0x180015e34  call    __scrt_acquire_startup_lock
0x180015e39  mov     bl, al
0x180015e3b  mov     [rsp+38h+var_18], al
0x180015e3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180015e46  jnz     short loc_180015E7E
0x180015e48  call    __scrt_dllmain_uninitialize_c
0x180015e4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180015e52  call    _RTC_Terminate
0x180015e57  mov     cs:__scrt_current_native_startup_state, 0
0x180015e61  mov     cl, bl
0x180015e63  call    __scrt_release_startup_lock
0x180015e68  xor     edx, edx
0x180015e6a  mov     cl, dil
0x180015e6d  call    __scrt_uninitialize_crt
0x180015e72  movzx   ebx, al
0x180015e75  call    __scrt_dllmain_uninitialize_critical
0x180015e7a  mov     eax, ebx
0x180015e7c  jmp     short loc_180015E21
0x180015e7e  mov     ecx, 7
0x180015e83  call    __scrt_fastfail
0x180026de7  push    rbp
0x180026de9  sub     rsp, 20h
0x180026ded  mov     rbp, rdx
0x180026df0  mov     cl, [rbp+20h]
0x180026df3  call    __scrt_release_startup_lock
0x180026df8  nop
0x180026df9  add     rsp, 20h
0x180026dfd  pop     rbp
0x180026dfe  retn
0x180026e00  push    rbp
0x180026e02  sub     rsp, 20h
0x180026e06  mov     rbp, rdx
0x180026e09  add     rsp, 20h
0x180026e0d  pop     rbp
0x180026e0e  jmp     __scrt_dllmain_uninitialize_critical
```
