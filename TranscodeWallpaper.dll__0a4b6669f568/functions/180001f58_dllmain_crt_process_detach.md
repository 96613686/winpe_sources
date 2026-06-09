# dllmain_crt_process_detach

- ea: `0x180001f58`
- end: `0x180001fdb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001e00`

## callees

- `0x180001f58`
- `0x180002194`
- `0x1800022bc`
- `0x1800022f4`
- `0x180002484`
- `0x1800024b0`
- `0x1800026d8`
- `0x180002720`
- `0x180002770`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180016430 <= 0 )
    return 0;
  --dword_180016430;
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
0x180001f58  mov     [rsp+arg_0], rbx
0x180001f5d  push    rdi
0x180001f5e  sub     rsp, 30h
0x180001f62  mov     dil, cl
0x180001f65  mov     eax, cs:dword_180016430
0x180001f6b  test    eax, eax
0x180001f6d  jg      short loc_180001F7C
0x180001f6f  xor     eax, eax
0x180001f71  mov     rbx, [rsp+38h+arg_0]
0x180001f76  add     rsp, 30h
0x180001f7a  pop     rdi
0x180001f7b  retn
0x180001f7c  dec     eax
0x180001f7e  mov     cs:dword_180016430, eax
0x180001f84  call    __scrt_acquire_startup_lock
0x180001f89  mov     bl, al
0x180001f8b  mov     [rsp+38h+var_18], al
0x180001f8f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001f96  jnz     short loc_180001FCE
0x180001f98  call    __scrt_dllmain_uninitialize_c
0x180001f9d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001fa2  call    _RTC_Terminate
0x180001fa7  mov     cs:__scrt_current_native_startup_state, 0
0x180001fb1  mov     cl, bl
0x180001fb3  call    __scrt_release_startup_lock
0x180001fb8  xor     edx, edx
0x180001fba  mov     cl, dil
0x180001fbd  call    __scrt_uninitialize_crt
0x180001fc2  movzx   ebx, al
0x180001fc5  call    __scrt_dllmain_uninitialize_critical
0x180001fca  mov     eax, ebx
0x180001fcc  jmp     short loc_180001F71
0x180001fce  mov     ecx, 7
0x180001fd3  call    __scrt_fastfail
0x18000de09  push    rbp
0x18000de0b  sub     rsp, 20h
0x18000de0f  mov     rbp, rdx
0x18000de12  mov     cl, [rbp+20h]
0x18000de15  call    __scrt_release_startup_lock
0x18000de1a  nop
0x18000de1b  add     rsp, 20h
0x18000de1f  pop     rbp
0x18000de20  retn
0x18000de22  push    rbp
0x18000de24  sub     rsp, 20h
0x18000de28  mov     rbp, rdx
0x18000de2b  add     rsp, 20h
0x18000de2f  pop     rbp
0x18000de30  jmp     __scrt_dllmain_uninitialize_critical
```
