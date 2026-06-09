# dllmain_crt_process_detach

- ea: `0x1800074f8`
- end: `0x180007578`
- name: `dllmain_crt_process_detach`
- size: `128`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180007390`
- `0x180007578`

## callees

- `0x1800074f8`
- `0x180007720`
- `0x180007848`
- `0x180007878`
- `0x1800079ec`
- `0x180007a10`
- `0x180007e80`
- `0x180007eb8`
- `0x18000803c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  DWORD v7; // edx
  HINSTANCE v8; // rcx
  LPVOID v9; // r8

  if ( dword_18003DBB0 <= 0 )
    return 0;
  --dword_18003DBB0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state == 2 )
  {
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
  else
  {
    _scrt_fastfail(7);
    __debugbreak();
    return dllmain_dispatch(v8, v7, v9);
  }
}

```

## disassembly

```asm
0x1800074f8  mov     [rsp+arg_0], rbx
0x1800074fd  push    rdi
0x1800074fe  sub     rsp, 30h
0x180007502  mov     dil, cl
0x180007505  mov     eax, cs:dword_18003DBB0
0x18000750b  test    eax, eax
0x18000750d  jg      short loc_18000751C
0x18000750f  xor     eax, eax
0x180007511  mov     rbx, [rsp+38h+arg_0]
0x180007516  add     rsp, 30h
0x18000751a  pop     rdi
0x18000751b  retn
0x18000751c  dec     eax
0x18000751e  mov     cs:dword_18003DBB0, eax
0x180007524  call    __scrt_acquire_startup_lock
0x180007529  mov     bl, al
0x18000752b  mov     [rsp+38h+var_18], al
0x18000752f  cmp     cs:__scrt_current_native_startup_state, 2
0x180007536  jnz     short loc_18000756B
0x180007538  call    __scrt_dllmain_uninitialize_c
0x18000753d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180007542  call    _RTC_Terminate
0x180007547  and     cs:__scrt_current_native_startup_state, 0
0x18000754e  mov     cl, bl
0x180007550  call    __scrt_release_startup_lock
0x180007555  xor     edx, edx
0x180007557  mov     cl, dil
0x18000755a  call    __scrt_uninitialize_crt
0x18000755f  movzx   ebx, al
0x180007562  call    __scrt_dllmain_uninitialize_critical
0x180007567  mov     eax, ebx
0x180007569  jmp     short loc_180007511
0x18000756b  mov     ecx, 7
0x180007570  call    __scrt_fastfail
0x180007575  nop
0x180007576  nop
0x180007577  int     3; Trap to Debugger
0x180024e91  push    rbp
0x180024e93  sub     rsp, 20h
0x180024e97  mov     rbp, rdx
0x180024e9a  mov     cl, [rbp+20h]
0x180024e9d  call    __scrt_release_startup_lock
0x180024ea2  nop
0x180024ea3  add     rsp, 20h
0x180024ea7  pop     rbp
0x180024ea8  retn
0x180024eaa  push    rbp
0x180024eac  sub     rsp, 20h
0x180024eb0  mov     rbp, rdx
0x180024eb3  add     rsp, 20h
0x180024eb7  pop     rbp
0x180024eb8  jmp     __scrt_dllmain_uninitialize_critical
```
