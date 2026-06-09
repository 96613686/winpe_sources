# dllmain_crt_process_detach

- ea: `0x1800029e8`
- end: `0x180002a6b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002890`

## callees

- `0x1800029e8`
- `0x180002c24`
- `0x180002d4c`
- `0x180002d84`
- `0x180002f14`
- `0x180002f40`
- `0x180003478`
- `0x1800034c0`
- `0x180003510`

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

  if ( dword_180027718 <= 0 )
    return 0;
  --dword_180027718;
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
0x1800029e8  mov     [rsp+arg_0], rbx
0x1800029ed  push    rdi
0x1800029ee  sub     rsp, 30h
0x1800029f2  mov     dil, cl
0x1800029f5  mov     eax, cs:dword_180027718
0x1800029fb  test    eax, eax
0x1800029fd  jg      short loc_180002A0C
0x1800029ff  xor     eax, eax
0x180002a01  mov     rbx, [rsp+38h+arg_0]
0x180002a06  add     rsp, 30h
0x180002a0a  pop     rdi
0x180002a0b  retn
0x180002a0c  dec     eax
0x180002a0e  mov     cs:dword_180027718, eax
0x180002a14  call    __scrt_acquire_startup_lock
0x180002a19  mov     bl, al
0x180002a1b  mov     [rsp+38h+var_18], al
0x180002a1f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002a26  jnz     short loc_180002A5E
0x180002a28  call    __scrt_dllmain_uninitialize_c
0x180002a2d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002a32  call    _RTC_Terminate
0x180002a37  mov     cs:__scrt_current_native_startup_state, 0
0x180002a41  mov     cl, bl
0x180002a43  call    __scrt_release_startup_lock
0x180002a48  xor     edx, edx
0x180002a4a  mov     cl, dil
0x180002a4d  call    __scrt_uninitialize_crt
0x180002a52  movzx   ebx, al
0x180002a55  call    __scrt_dllmain_uninitialize_critical
0x180002a5a  mov     eax, ebx
0x180002a5c  jmp     short loc_180002A01
0x180002a5e  mov     ecx, 7
0x180002a63  call    __scrt_fastfail
0x18001a619  push    rbp
0x18001a61b  sub     rsp, 20h
0x18001a61f  mov     rbp, rdx
0x18001a622  mov     cl, [rbp+20h]
0x18001a625  call    __scrt_release_startup_lock
0x18001a62a  nop
0x18001a62b  add     rsp, 20h
0x18001a62f  pop     rbp
0x18001a630  retn
0x18001a632  push    rbp
0x18001a634  sub     rsp, 20h
0x18001a638  mov     rbp, rdx
0x18001a63b  add     rsp, 20h
0x18001a63f  pop     rbp
0x18001a640  jmp     __scrt_dllmain_uninitialize_critical
```
