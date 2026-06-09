# dllmain_crt_process_detach

- ea: `0x1800031b8`
- end: `0x18000323b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003060`

## callees

- `0x1800031b8`
- `0x1800036b4`
- `0x1800037dc`
- `0x180003814`
- `0x1800039a4`
- `0x1800039d0`
- `0x180003b7c`
- `0x180003bc4`
- `0x180003c14`

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

  if ( dword_180021610 <= 0 )
    return 0;
  --dword_180021610;
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
0x1800031b8  mov     [rsp+arg_0], rbx
0x1800031bd  push    rdi
0x1800031be  sub     rsp, 30h
0x1800031c2  mov     dil, cl
0x1800031c5  mov     eax, cs:dword_180021610
0x1800031cb  test    eax, eax
0x1800031cd  jg      short loc_1800031DC
0x1800031cf  xor     eax, eax
0x1800031d1  mov     rbx, [rsp+38h+arg_0]
0x1800031d6  add     rsp, 30h
0x1800031da  pop     rdi
0x1800031db  retn
0x1800031dc  dec     eax
0x1800031de  mov     cs:dword_180021610, eax
0x1800031e4  call    __scrt_acquire_startup_lock
0x1800031e9  mov     bl, al
0x1800031eb  mov     [rsp+38h+var_18], al
0x1800031ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800031f6  jnz     short loc_18000322E
0x1800031f8  call    __scrt_dllmain_uninitialize_c
0x1800031fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003202  call    _RTC_Terminate
0x180003207  mov     cs:__scrt_current_native_startup_state, 0
0x180003211  mov     cl, bl
0x180003213  call    __scrt_release_startup_lock
0x180003218  xor     edx, edx
0x18000321a  mov     cl, dil
0x18000321d  call    __scrt_uninitialize_crt
0x180003222  movzx   ebx, al
0x180003225  call    __scrt_dllmain_uninitialize_critical
0x18000322a  mov     eax, ebx
0x18000322c  jmp     short loc_1800031D1
0x18000322e  mov     ecx, 7
0x180003233  call    __scrt_fastfail
0x18001752b  push    rbp
0x18001752d  sub     rsp, 20h
0x180017531  mov     rbp, rdx
0x180017534  mov     cl, [rbp+20h]
0x180017537  call    __scrt_release_startup_lock
0x18001753c  nop
0x18001753d  add     rsp, 20h
0x180017541  pop     rbp
0x180017542  retn
0x180017544  push    rbp
0x180017546  sub     rsp, 20h
0x18001754a  mov     rbp, rdx
0x18001754d  add     rsp, 20h
0x180017551  pop     rbp
0x180017552  jmp     __scrt_dllmain_uninitialize_critical
```
