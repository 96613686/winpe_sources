# dllmain_crt_process_detach

- ea: `0x180004a58`
- end: `0x180004adb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004900`

## callees

- `0x180004a58`
- `0x180004cb8`
- `0x180004de0`
- `0x180004e18`
- `0x180004fa8`
- `0x180004fd4`
- `0x18000517c`
- `0x1800051c4`
- `0x180005214`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C1F0 <= 0 )
    return 0;
  --dword_18001C1F0;
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
0x180004a58  mov     [rsp+arg_0], rbx
0x180004a5d  push    rdi
0x180004a5e  sub     rsp, 30h
0x180004a62  mov     dil, cl
0x180004a65  mov     eax, cs:dword_18001C1F0
0x180004a6b  test    eax, eax
0x180004a6d  jg      short loc_180004A7C
0x180004a6f  xor     eax, eax
0x180004a71  mov     rbx, [rsp+38h+arg_0]
0x180004a76  add     rsp, 30h
0x180004a7a  pop     rdi
0x180004a7b  retn
0x180004a7c  dec     eax
0x180004a7e  mov     cs:dword_18001C1F0, eax
0x180004a84  call    __scrt_acquire_startup_lock
0x180004a89  mov     bl, al
0x180004a8b  mov     [rsp+38h+var_18], al
0x180004a8f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004a96  jnz     short loc_180004ACE
0x180004a98  call    __scrt_dllmain_uninitialize_c
0x180004a9d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004aa2  call    _RTC_Terminate
0x180004aa7  mov     cs:__scrt_current_native_startup_state, 0
0x180004ab1  mov     cl, bl
0x180004ab3  call    __scrt_release_startup_lock
0x180004ab8  xor     edx, edx
0x180004aba  mov     cl, dil
0x180004abd  call    __scrt_uninitialize_crt
0x180004ac2  movzx   ebx, al
0x180004ac5  call    __scrt_dllmain_uninitialize_critical
0x180004aca  mov     eax, ebx
0x180004acc  jmp     short loc_180004A71
0x180004ace  mov     ecx, 7
0x180004ad3  call    __scrt_fastfail
0x180013731  push    rbp
0x180013733  sub     rsp, 20h
0x180013737  mov     rbp, rdx
0x18001373a  mov     cl, [rbp+20h]
0x18001373d  call    __scrt_release_startup_lock
0x180013742  nop
0x180013743  add     rsp, 20h
0x180013747  pop     rbp
0x180013748  retn
0x18001374a  push    rbp
0x18001374c  sub     rsp, 20h
0x180013750  mov     rbp, rdx
0x180013753  add     rsp, 20h
0x180013757  pop     rbp
0x180013758  jmp     __scrt_dllmain_uninitialize_critical
```
