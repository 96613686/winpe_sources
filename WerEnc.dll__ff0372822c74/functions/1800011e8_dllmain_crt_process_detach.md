# dllmain_crt_process_detach

- ea: `0x1800011e8`
- end: `0x18000126b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800011e8`
- `0x180001574`
- `0x1800015ac`
- `0x1800016d4`
- `0x18000170c`
- `0x18000189c`
- `0x1800018c8`
- `0x180001908`
- `0x180001958`

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

  if ( dword_180006150 <= 0 )
    return 0;
  --dword_180006150;
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
0x1800011e8  mov     [rsp+arg_0], rbx
0x1800011ed  push    rdi
0x1800011ee  sub     rsp, 30h
0x1800011f2  mov     dil, cl
0x1800011f5  mov     eax, cs:dword_180006150
0x1800011fb  test    eax, eax
0x1800011fd  jg      short loc_18000120C
0x1800011ff  xor     eax, eax
0x180001201  mov     rbx, [rsp+38h+arg_0]
0x180001206  add     rsp, 30h
0x18000120a  pop     rdi
0x18000120b  retn
0x18000120c  dec     eax
0x18000120e  mov     cs:dword_180006150, eax
0x180001214  call    __scrt_acquire_startup_lock
0x180001219  mov     bl, al
0x18000121b  mov     [rsp+38h+var_18], al
0x18000121f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001226  jnz     short loc_18000125E
0x180001228  call    __scrt_dllmain_uninitialize_c
0x18000122d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001232  call    _RTC_Terminate
0x180001237  mov     cs:__scrt_current_native_startup_state, 0
0x180001241  mov     cl, bl
0x180001243  call    __scrt_release_startup_lock
0x180001248  xor     edx, edx
0x18000124a  mov     cl, dil
0x18000124d  call    __scrt_uninitialize_crt
0x180001252  movzx   ebx, al
0x180001255  call    __scrt_dllmain_uninitialize_critical
0x18000125a  mov     eax, ebx
0x18000125c  jmp     short loc_180001201
0x18000125e  mov     ecx, 7
0x180001263  call    __scrt_fastfail
0x180002c69  push    rbp
0x180002c6b  sub     rsp, 20h
0x180002c6f  mov     rbp, rdx
0x180002c72  mov     cl, [rbp+20h]
0x180002c75  call    __scrt_release_startup_lock
0x180002c7a  nop
0x180002c7b  add     rsp, 20h
0x180002c7f  pop     rbp
0x180002c80  retn
0x180002c82  push    rbp
0x180002c84  sub     rsp, 20h
0x180002c88  mov     rbp, rdx
0x180002c8b  add     rsp, 20h
0x180002c8f  pop     rbp
0x180002c90  jmp     __scrt_dllmain_uninitialize_critical
```
