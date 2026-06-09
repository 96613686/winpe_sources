# dllmain_crt_process_detach

- ea: `0x180001e08`
- end: `0x180001e8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001cb0`

## callees

- `0x180001e08`
- `0x180002088`
- `0x1800021b0`
- `0x1800021e8`
- `0x180002378`
- `0x1800023a4`
- `0x18000263c`
- `0x180002684`
- `0x1800026d4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800225B0 <= 0 )
    return 0;
  --dword_1800225B0;
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
0x180001e08  mov     [rsp+arg_0], rbx
0x180001e0d  push    rdi
0x180001e0e  sub     rsp, 30h
0x180001e12  mov     dil, cl
0x180001e15  mov     eax, cs:dword_1800225B0
0x180001e1b  test    eax, eax
0x180001e1d  jg      short loc_180001E2C
0x180001e1f  xor     eax, eax
0x180001e21  mov     rbx, [rsp+38h+arg_0]
0x180001e26  add     rsp, 30h
0x180001e2a  pop     rdi
0x180001e2b  retn
0x180001e2c  dec     eax
0x180001e2e  mov     cs:dword_1800225B0, eax
0x180001e34  call    __scrt_acquire_startup_lock
0x180001e39  mov     bl, al
0x180001e3b  mov     [rsp+38h+var_18], al
0x180001e3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001e46  jnz     short loc_180001E7E
0x180001e48  call    __scrt_dllmain_uninitialize_c
0x180001e4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001e52  call    _RTC_Terminate
0x180001e57  mov     cs:__scrt_current_native_startup_state, 0
0x180001e61  mov     cl, bl
0x180001e63  call    __scrt_release_startup_lock
0x180001e68  xor     edx, edx
0x180001e6a  mov     cl, dil
0x180001e6d  call    __scrt_uninitialize_crt
0x180001e72  movzx   ebx, al
0x180001e75  call    __scrt_dllmain_uninitialize_critical
0x180001e7a  mov     eax, ebx
0x180001e7c  jmp     short loc_180001E21
0x180001e7e  mov     ecx, 7
0x180001e83  call    __scrt_fastfail
0x180015fe9  push    rbp
0x180015feb  sub     rsp, 20h
0x180015fef  mov     rbp, rdx
0x180015ff2  mov     cl, [rbp+20h]
0x180015ff5  call    __scrt_release_startup_lock
0x180015ffa  nop
0x180015ffb  add     rsp, 20h
0x180015fff  pop     rbp
0x180016000  retn
0x180016002  push    rbp
0x180016004  sub     rsp, 20h
0x180016008  mov     rbp, rdx
0x18001600b  add     rsp, 20h
0x18001600f  pop     rbp
0x180016010  jmp     __scrt_dllmain_uninitialize_critical
```
