# dllmain_crt_process_detach

- ea: `0x180021818`
- end: `0x18002189b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800216c0`

## callees

- `0x180021818`
- `0x180021b30`
- `0x180021b68`
- `0x180021c90`
- `0x180021cc8`
- `0x180021e58`
- `0x180021e84`
- `0x180021f24`
- `0x180021f74`

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

  if ( dword_1800401B0 <= 0 )
    return 0;
  --dword_1800401B0;
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
0x180021818  mov     [rsp+arg_0], rbx
0x18002181d  push    rdi
0x18002181e  sub     rsp, 30h
0x180021822  mov     dil, cl
0x180021825  mov     eax, cs:dword_1800401B0
0x18002182b  test    eax, eax
0x18002182d  jg      short loc_18002183C
0x18002182f  xor     eax, eax
0x180021831  mov     rbx, [rsp+38h+arg_0]
0x180021836  add     rsp, 30h
0x18002183a  pop     rdi
0x18002183b  retn
0x18002183c  dec     eax
0x18002183e  mov     cs:dword_1800401B0, eax
0x180021844  call    __scrt_acquire_startup_lock
0x180021849  mov     bl, al
0x18002184b  mov     [rsp+38h+var_18], al
0x18002184f  cmp     cs:__scrt_current_native_startup_state, 2
0x180021856  jnz     short loc_18002188E
0x180021858  call    __scrt_dllmain_uninitialize_c
0x18002185d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180021862  call    _RTC_Terminate
0x180021867  mov     cs:__scrt_current_native_startup_state, 0
0x180021871  mov     cl, bl
0x180021873  call    __scrt_release_startup_lock
0x180021878  xor     edx, edx
0x18002187a  mov     cl, dil
0x18002187d  call    __scrt_uninitialize_crt
0x180021882  movzx   ebx, al
0x180021885  call    __scrt_dllmain_uninitialize_critical
0x18002188a  mov     eax, ebx
0x18002188c  jmp     short loc_180021831
0x18002188e  mov     ecx, 7
0x180021893  call    __scrt_fastfail
0x180032e69  push    rbp
0x180032e6b  sub     rsp, 20h
0x180032e6f  mov     rbp, rdx
0x180032e72  mov     cl, [rbp+20h]
0x180032e75  call    __scrt_release_startup_lock
0x180032e7a  nop
0x180032e7b  add     rsp, 20h
0x180032e7f  pop     rbp
0x180032e80  retn
0x180032e82  push    rbp
0x180032e84  sub     rsp, 20h
0x180032e88  mov     rbp, rdx
0x180032e8b  add     rsp, 20h
0x180032e8f  pop     rbp
0x180032e90  jmp     __scrt_dllmain_uninitialize_critical
```
