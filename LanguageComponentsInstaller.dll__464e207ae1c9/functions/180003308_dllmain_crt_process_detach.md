# dllmain_crt_process_detach

- ea: `0x180003308`
- end: `0x18000338b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800031b0`

## callees

- `0x180003308`
- `0x18000367c`
- `0x1800037a4`
- `0x1800037dc`
- `0x18000396c`
- `0x180003998`
- `0x180003e64`
- `0x180003eac`
- `0x180003efc`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180037518 <= 0 )
    return 0;
  --dword_180037518;
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
0x180003308  mov     [rsp+arg_0], rbx
0x18000330d  push    rdi
0x18000330e  sub     rsp, 30h
0x180003312  mov     dil, cl
0x180003315  mov     eax, cs:dword_180037518
0x18000331b  test    eax, eax
0x18000331d  jg      short loc_18000332C
0x18000331f  xor     eax, eax
0x180003321  mov     rbx, [rsp+38h+arg_0]
0x180003326  add     rsp, 30h
0x18000332a  pop     rdi
0x18000332b  retn
0x18000332c  dec     eax
0x18000332e  mov     cs:dword_180037518, eax
0x180003334  call    __scrt_acquire_startup_lock
0x180003339  mov     bl, al
0x18000333b  mov     [rsp+38h+var_18], al
0x18000333f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003346  jnz     short loc_18000337E
0x180003348  call    __scrt_dllmain_uninitialize_c
0x18000334d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003352  call    _RTC_Terminate
0x180003357  mov     cs:__scrt_current_native_startup_state, 0
0x180003361  mov     cl, bl
0x180003363  call    __scrt_release_startup_lock
0x180003368  xor     edx, edx
0x18000336a  mov     cl, dil
0x18000336d  call    __scrt_uninitialize_crt
0x180003372  movzx   ebx, al
0x180003375  call    __scrt_dllmain_uninitialize_critical
0x18000337a  mov     eax, ebx
0x18000337c  jmp     short loc_180003321
0x18000337e  mov     ecx, 7
0x180003383  call    __scrt_fastfail
0x180027d89  push    rbp
0x180027d8b  sub     rsp, 20h
0x180027d8f  mov     rbp, rdx
0x180027d92  mov     cl, [rbp+20h]
0x180027d95  call    __scrt_release_startup_lock
0x180027d9a  nop
0x180027d9b  add     rsp, 20h
0x180027d9f  pop     rbp
0x180027da0  retn
0x180027da2  push    rbp
0x180027da4  sub     rsp, 20h
0x180027da8  mov     rbp, rdx
0x180027dab  add     rsp, 20h
0x180027daf  pop     rbp
0x180027db0  jmp     __scrt_dllmain_uninitialize_critical
```
