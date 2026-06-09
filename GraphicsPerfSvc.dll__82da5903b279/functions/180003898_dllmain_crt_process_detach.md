# dllmain_crt_process_detach

- ea: `0x180003898`
- end: `0x18000391b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003740`

## callees

- `0x180003898`
- `0x180003ad4`
- `0x180003bfc`
- `0x180003c34`
- `0x180003dc4`
- `0x180003df0`
- `0x1800042cc`
- `0x180004314`
- `0x180004364`

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

  if ( dword_1800427F0 <= 0 )
    return 0;
  --dword_1800427F0;
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
0x180003898  mov     [rsp+arg_0], rbx
0x18000389d  push    rdi
0x18000389e  sub     rsp, 30h
0x1800038a2  mov     dil, cl
0x1800038a5  mov     eax, cs:dword_1800427F0
0x1800038ab  test    eax, eax
0x1800038ad  jg      short loc_1800038BC
0x1800038af  xor     eax, eax
0x1800038b1  mov     rbx, [rsp+38h+arg_0]
0x1800038b6  add     rsp, 30h
0x1800038ba  pop     rdi
0x1800038bb  retn
0x1800038bc  dec     eax
0x1800038be  mov     cs:dword_1800427F0, eax
0x1800038c4  call    __scrt_acquire_startup_lock
0x1800038c9  mov     bl, al
0x1800038cb  mov     [rsp+38h+var_18], al
0x1800038cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800038d6  jnz     short loc_18000390E
0x1800038d8  call    __scrt_dllmain_uninitialize_c
0x1800038dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800038e2  call    _RTC_Terminate
0x1800038e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800038f1  mov     cl, bl
0x1800038f3  call    __scrt_release_startup_lock
0x1800038f8  xor     edx, edx
0x1800038fa  mov     cl, dil
0x1800038fd  call    __scrt_uninitialize_crt
0x180003902  movzx   ebx, al
0x180003905  call    __scrt_dllmain_uninitialize_critical
0x18000390a  mov     eax, ebx
0x18000390c  jmp     short loc_1800038B1
0x18000390e  mov     ecx, 7
0x180003913  call    __scrt_fastfail
0x18002f1a9  push    rbp
0x18002f1ab  sub     rsp, 20h
0x18002f1af  mov     rbp, rdx
0x18002f1b2  mov     cl, [rbp+20h]
0x18002f1b5  call    __scrt_release_startup_lock
0x18002f1ba  nop
0x18002f1bb  add     rsp, 20h
0x18002f1bf  pop     rbp
0x18002f1c0  retn
0x18002f1c2  push    rbp
0x18002f1c4  sub     rsp, 20h
0x18002f1c8  mov     rbp, rdx
0x18002f1cb  add     rsp, 20h
0x18002f1cf  pop     rbp
0x18002f1d0  jmp     __scrt_dllmain_uninitialize_critical
```
