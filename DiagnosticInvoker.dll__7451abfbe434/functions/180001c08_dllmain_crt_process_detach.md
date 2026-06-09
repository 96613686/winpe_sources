# dllmain_crt_process_detach

- ea: `0x180001c08`
- end: `0x180001c8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001ab0`

## callees

- `0x180001c08`
- `0x180001f14`
- `0x18000203c`
- `0x180002074`
- `0x180002204`
- `0x180002230`
- `0x1800023fc`
- `0x180002444`
- `0x180002494`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001D350 <= 0 )
    return 0;
  --dword_18001D350;
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
0x180001c08  mov     [rsp+arg_0], rbx
0x180001c0d  push    rdi
0x180001c0e  sub     rsp, 30h
0x180001c12  mov     dil, cl
0x180001c15  mov     eax, cs:dword_18001D350
0x180001c1b  test    eax, eax
0x180001c1d  jg      short loc_180001C2C
0x180001c1f  xor     eax, eax
0x180001c21  mov     rbx, [rsp+38h+arg_0]
0x180001c26  add     rsp, 30h
0x180001c2a  pop     rdi
0x180001c2b  retn
0x180001c2c  dec     eax
0x180001c2e  mov     cs:dword_18001D350, eax
0x180001c34  call    __scrt_acquire_startup_lock
0x180001c39  mov     bl, al
0x180001c3b  mov     [rsp+38h+var_18], al
0x180001c3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001c46  jnz     short loc_180001C7E
0x180001c48  call    __scrt_dllmain_uninitialize_c
0x180001c4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001c52  call    _RTC_Terminate
0x180001c57  mov     cs:__scrt_current_native_startup_state, 0
0x180001c61  mov     cl, bl
0x180001c63  call    __scrt_release_startup_lock
0x180001c68  xor     edx, edx
0x180001c6a  mov     cl, dil
0x180001c6d  call    __scrt_uninitialize_crt
0x180001c72  movzx   ebx, al
0x180001c75  call    __scrt_dllmain_uninitialize_critical
0x180001c7a  mov     eax, ebx
0x180001c7c  jmp     short loc_180001C21
0x180001c7e  mov     ecx, 7
0x180001c83  call    __scrt_fastfail
0x180010109  push    rbp
0x18001010b  sub     rsp, 20h
0x18001010f  mov     rbp, rdx
0x180010112  mov     cl, [rbp+20h]
0x180010115  call    __scrt_release_startup_lock
0x18001011a  nop
0x18001011b  add     rsp, 20h
0x18001011f  pop     rbp
0x180010120  retn
0x180010122  push    rbp
0x180010124  sub     rsp, 20h
0x180010128  mov     rbp, rdx
0x18001012b  add     rsp, 20h
0x18001012f  pop     rbp
0x180010130  jmp     __scrt_dllmain_uninitialize_critical
```
