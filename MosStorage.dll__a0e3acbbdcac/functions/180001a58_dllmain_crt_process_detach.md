# dllmain_crt_process_detach

- ea: `0x180001a58`
- end: `0x180001adb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x180001a58`
- `0x180001ca4`
- `0x180001dcc`
- `0x180001e04`
- `0x180001f94`
- `0x180001fc0`
- `0x1800022f8`
- `0x180002340`
- `0x180002390`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180018250 <= 0 )
    return 0;
  --dword_180018250;
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
0x180001a58  mov     [rsp+arg_0], rbx
0x180001a5d  push    rdi
0x180001a5e  sub     rsp, 30h
0x180001a62  mov     dil, cl
0x180001a65  mov     eax, cs:dword_180018250
0x180001a6b  test    eax, eax
0x180001a6d  jg      short loc_180001A7C
0x180001a6f  xor     eax, eax
0x180001a71  mov     rbx, [rsp+38h+arg_0]
0x180001a76  add     rsp, 30h
0x180001a7a  pop     rdi
0x180001a7b  retn
0x180001a7c  dec     eax
0x180001a7e  mov     cs:dword_180018250, eax
0x180001a84  call    __scrt_acquire_startup_lock
0x180001a89  mov     bl, al
0x180001a8b  mov     [rsp+38h+var_18], al
0x180001a8f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001a96  jnz     short loc_180001ACE
0x180001a98  call    __scrt_dllmain_uninitialize_c
0x180001a9d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001aa2  call    _RTC_Terminate
0x180001aa7  mov     cs:__scrt_current_native_startup_state, 0
0x180001ab1  mov     cl, bl
0x180001ab3  call    __scrt_release_startup_lock
0x180001ab8  xor     edx, edx
0x180001aba  mov     cl, dil
0x180001abd  call    __scrt_uninitialize_crt
0x180001ac2  movzx   ebx, al
0x180001ac5  call    __scrt_dllmain_uninitialize_critical
0x180001aca  mov     eax, ebx
0x180001acc  jmp     short loc_180001A71
0x180001ace  mov     ecx, 7
0x180001ad3  call    __scrt_fastfail
0x18000e889  push    rbp
0x18000e88b  sub     rsp, 20h
0x18000e88f  mov     rbp, rdx
0x18000e892  mov     cl, [rbp+20h]
0x18000e895  call    __scrt_release_startup_lock
0x18000e89a  nop
0x18000e89b  add     rsp, 20h
0x18000e89f  pop     rbp
0x18000e8a0  retn
0x18000e8a2  push    rbp
0x18000e8a4  sub     rsp, 20h
0x18000e8a8  mov     rbp, rdx
0x18000e8ab  add     rsp, 20h
0x18000e8af  pop     rbp
0x18000e8b0  jmp     __scrt_dllmain_uninitialize_critical
```
