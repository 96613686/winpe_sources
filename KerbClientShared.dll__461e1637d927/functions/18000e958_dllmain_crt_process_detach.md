# dllmain_crt_process_detach

- ea: `0x18000e958`
- end: `0x18000e9db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000e800`

## callees

- `0x18000e958`
- `0x18000eb94`
- `0x18000ecbc`
- `0x18000ecf4`
- `0x18000ee84`
- `0x18000eeb0`
- `0x18000f06c`
- `0x18000f0b4`
- `0x18000f104`

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

  if ( dword_1800331F0 <= 0 )
    return 0;
  --dword_1800331F0;
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
0x18000e958  mov     [rsp+arg_0], rbx
0x18000e95d  push    rdi
0x18000e95e  sub     rsp, 30h
0x18000e962  mov     dil, cl
0x18000e965  mov     eax, cs:dword_1800331F0
0x18000e96b  test    eax, eax
0x18000e96d  jg      short loc_18000E97C
0x18000e96f  xor     eax, eax
0x18000e971  mov     rbx, [rsp+38h+arg_0]
0x18000e976  add     rsp, 30h
0x18000e97a  pop     rdi
0x18000e97b  retn
0x18000e97c  dec     eax
0x18000e97e  mov     cs:dword_1800331F0, eax
0x18000e984  call    __scrt_acquire_startup_lock
0x18000e989  mov     bl, al
0x18000e98b  mov     [rsp+38h+var_18], al
0x18000e98f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000e996  jnz     short loc_18000E9CE
0x18000e998  call    __scrt_dllmain_uninitialize_c
0x18000e99d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000e9a2  call    _RTC_Terminate
0x18000e9a7  mov     cs:__scrt_current_native_startup_state, 0
0x18000e9b1  mov     cl, bl
0x18000e9b3  call    __scrt_release_startup_lock
0x18000e9b8  xor     edx, edx
0x18000e9ba  mov     cl, dil
0x18000e9bd  call    __scrt_uninitialize_crt
0x18000e9c2  movzx   ebx, al
0x18000e9c5  call    __scrt_dllmain_uninitialize_critical
0x18000e9ca  mov     eax, ebx
0x18000e9cc  jmp     short loc_18000E971
0x18000e9ce  mov     ecx, 7
0x18000e9d3  call    __scrt_fastfail
0x1800284bf  push    rbp
0x1800284c1  sub     rsp, 20h
0x1800284c5  mov     rbp, rdx
0x1800284c8  mov     cl, [rbp+20h]
0x1800284cb  call    __scrt_release_startup_lock
0x1800284d0  nop
0x1800284d1  add     rsp, 20h
0x1800284d5  pop     rbp
0x1800284d6  retn
0x1800284d8  push    rbp
0x1800284da  sub     rsp, 20h
0x1800284de  mov     rbp, rdx
0x1800284e1  add     rsp, 20h
0x1800284e5  pop     rbp
0x1800284e6  jmp     __scrt_dllmain_uninitialize_critical
```
