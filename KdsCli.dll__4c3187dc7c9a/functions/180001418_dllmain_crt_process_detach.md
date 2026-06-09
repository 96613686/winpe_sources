# dllmain_crt_process_detach

- ea: `0x180001418`
- end: `0x18000149b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012c0`

## callees

- `0x180001418`
- `0x180001724`
- `0x18000175c`
- `0x180001884`
- `0x1800018bc`
- `0x180001a4c`
- `0x180001a78`
- `0x180001b18`
- `0x180001b68`

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

  if ( dword_180023310 <= 0 )
    return 0;
  --dword_180023310;
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
0x180001418  mov     [rsp+arg_0], rbx
0x18000141d  push    rdi
0x18000141e  sub     rsp, 30h
0x180001422  mov     dil, cl
0x180001425  mov     eax, cs:dword_180023310
0x18000142b  test    eax, eax
0x18000142d  jg      short loc_18000143C
0x18000142f  xor     eax, eax
0x180001431  mov     rbx, [rsp+38h+arg_0]
0x180001436  add     rsp, 30h
0x18000143a  pop     rdi
0x18000143b  retn
0x18000143c  dec     eax
0x18000143e  mov     cs:dword_180023310, eax
0x180001444  call    __scrt_acquire_startup_lock
0x180001449  mov     bl, al
0x18000144b  mov     [rsp+38h+var_18], al
0x18000144f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001456  jnz     short loc_18000148E
0x180001458  call    __scrt_dllmain_uninitialize_c
0x18000145d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001462  call    _RTC_Terminate
0x180001467  mov     cs:__scrt_current_native_startup_state, 0
0x180001471  mov     cl, bl
0x180001473  call    __scrt_release_startup_lock
0x180001478  xor     edx, edx
0x18000147a  mov     cl, dil
0x18000147d  call    __scrt_uninitialize_crt
0x180001482  movzx   ebx, al
0x180001485  call    __scrt_dllmain_uninitialize_critical
0x18000148a  mov     eax, ebx
0x18000148c  jmp     short loc_180001431
0x18000148e  mov     ecx, 7
0x180001493  call    __scrt_fastfail
0x18001a749  push    rbp
0x18001a74b  sub     rsp, 20h
0x18001a74f  mov     rbp, rdx
0x18001a752  mov     cl, [rbp+20h]
0x18001a755  call    __scrt_release_startup_lock
0x18001a75a  nop
0x18001a75b  add     rsp, 20h
0x18001a75f  pop     rbp
0x18001a760  retn
0x18001a762  push    rbp
0x18001a764  sub     rsp, 20h
0x18001a768  mov     rbp, rdx
0x18001a76b  add     rsp, 20h
0x18001a76f  pop     rbp
0x18001a770  jmp     __scrt_dllmain_uninitialize_critical
```
