# dllmain_crt_process_detach

- ea: `0x1800026f8`
- end: `0x18000277b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800025a0`

## callees

- `0x1800026f8`
- `0x180002934`
- `0x180002a5c`
- `0x180002a94`
- `0x180002c24`
- `0x180002c50`
- `0x180002dbc`
- `0x180002e04`
- `0x180002e54`

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

  if ( dword_1800181F0 <= 0 )
    return 0;
  --dword_1800181F0;
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
0x1800026f8  mov     [rsp+arg_0], rbx
0x1800026fd  push    rdi
0x1800026fe  sub     rsp, 30h
0x180002702  mov     dil, cl
0x180002705  mov     eax, cs:dword_1800181F0
0x18000270b  test    eax, eax
0x18000270d  jg      short loc_18000271C
0x18000270f  xor     eax, eax
0x180002711  mov     rbx, [rsp+38h+arg_0]
0x180002716  add     rsp, 30h
0x18000271a  pop     rdi
0x18000271b  retn
0x18000271c  dec     eax
0x18000271e  mov     cs:dword_1800181F0, eax
0x180002724  call    __scrt_acquire_startup_lock
0x180002729  mov     bl, al
0x18000272b  mov     [rsp+38h+var_18], al
0x18000272f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002736  jnz     short loc_18000276E
0x180002738  call    __scrt_dllmain_uninitialize_c
0x18000273d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002742  call    _RTC_Terminate
0x180002747  mov     cs:__scrt_current_native_startup_state, 0
0x180002751  mov     cl, bl
0x180002753  call    __scrt_release_startup_lock
0x180002758  xor     edx, edx
0x18000275a  mov     cl, dil
0x18000275d  call    __scrt_uninitialize_crt
0x180002762  movzx   ebx, al
0x180002765  call    __scrt_dllmain_uninitialize_critical
0x18000276a  mov     eax, ebx
0x18000276c  jmp     short loc_180002711
0x18000276e  mov     ecx, 7
0x180002773  call    __scrt_fastfail
0x180010609  push    rbp
0x18001060b  sub     rsp, 20h
0x18001060f  mov     rbp, rdx
0x180010612  mov     cl, [rbp+20h]
0x180010615  call    __scrt_release_startup_lock
0x18001061a  nop
0x18001061b  add     rsp, 20h
0x18001061f  pop     rbp
0x180010620  retn
0x180010622  push    rbp
0x180010624  sub     rsp, 20h
0x180010628  mov     rbp, rdx
0x18001062b  add     rsp, 20h
0x18001062f  pop     rbp
0x180010630  jmp     __scrt_dllmain_uninitialize_critical
```
