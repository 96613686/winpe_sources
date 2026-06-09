# dllmain_crt_process_detach

- ea: `0x18000d898`
- end: `0x18000d91c`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d730`
- `0x18000d91c`

## callees

- `0x18000d0b8`
- `0x18000d1e0`
- `0x18000d210`
- `0x18000d394`
- `0x18000d3b8`
- `0x18000d898`
- `0x18000dc48`
- `0x18000e000`
- `0x18000e074`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx
  DWORD v9; // edx
  HINSTANCE v10; // rcx
  LPVOID v11; // r8

  if ( dword_180018920 <= 0 )
    return 0;
  --dword_180018920;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state == 2 )
  {
    _scrt_dllmain_uninitialize_c(v3);
    __scrt_uninitialize_type_info();
    RTC_Terminate();
    _scrt_current_native_startup_state = 0;
    LOBYTE(v5) = v4;
    _scrt_release_startup_lock(v5);
    LOBYTE(v6) = a1;
    v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
    _scrt_dllmain_uninitialize_critical(v8);
    return v7;
  }
  else
  {
    _scrt_fastfail(7);
    __debugbreak();
    return dllmain_dispatch(v10, v9, v11);
  }
}

```

## disassembly

```asm
0x18000d898  mov     [rsp+arg_0], rbx
0x18000d89d  push    rdi
0x18000d89e  sub     rsp, 30h
0x18000d8a2  mov     dil, cl
0x18000d8a5  mov     eax, cs:dword_180018920
0x18000d8ab  test    eax, eax
0x18000d8ad  jg      short loc_18000D8BC
0x18000d8af  xor     eax, eax
0x18000d8b1  mov     rbx, [rsp+38h+arg_0]
0x18000d8b6  add     rsp, 30h
0x18000d8ba  pop     rdi
0x18000d8bb  retn
0x18000d8bc  dec     eax
0x18000d8be  mov     cs:dword_180018920, eax
0x18000d8c4  call    __scrt_acquire_startup_lock
0x18000d8c9  mov     bl, al
0x18000d8cb  mov     [rsp+38h+var_18], al
0x18000d8cf  cmp     cs:__scrt_current_native_startup_state, 2
0x18000d8d6  jnz     short loc_18000D90F
0x18000d8d8  call    __scrt_dllmain_uninitialize_c
0x18000d8dd  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x18000d8e2  call    _RTC_Terminate
0x18000d8e7  and     cs:__scrt_current_native_startup_state, 0
0x18000d8ee  mov     cl, bl
0x18000d8f0  call    __scrt_release_startup_lock
0x18000d8f5  xor     edx, edx
0x18000d8f7  mov     cl, dil
0x18000d8fa  call    __scrt_uninitialize_crt
0x18000d8ff  neg     al
0x18000d901  sbb     ebx, ebx
0x18000d903  and     ebx, 1
0x18000d906  call    __scrt_dllmain_uninitialize_critical
0x18000d90b  mov     eax, ebx
0x18000d90d  jmp     short loc_18000D8B1
0x18000d90f  mov     ecx, 7
0x18000d914  call    __scrt_fastfail
0x18000d919  nop
0x18000d91a  nop
0x18000d91b  int     3; Trap to Debugger
0x18000f242  push    rbp
0x18000f244  sub     rsp, 20h
0x18000f248  mov     rbp, rdx
0x18000f24b  mov     cl, [rbp+20h]
0x18000f24e  call    __scrt_release_startup_lock
0x18000f253  nop
0x18000f254  add     rsp, 20h
0x18000f258  pop     rbp
0x18000f259  retn
0x18000f25b  push    rbp
0x18000f25d  sub     rsp, 20h
0x18000f261  mov     rbp, rdx
0x18000f264  add     rsp, 20h
0x18000f268  pop     rbp
0x18000f269  jmp     __scrt_dllmain_uninitialize_critical
```
