# dllmain_crt_process_detach

- ea: `0x1800070c8`
- end: `0x18000714b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180006f70`

## callees

- `0x1800070c8`
- `0x1800073d4`
- `0x18000740c`
- `0x180007534`
- `0x18000756c`
- `0x1800076fc`
- `0x180007728`
- `0x180007768`
- `0x1800077b8`

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

  if ( dword_1800120D0 <= 0 )
    return 0;
  --dword_1800120D0;
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
0x1800070c8  mov     [rsp+arg_0], rbx
0x1800070cd  push    rdi
0x1800070ce  sub     rsp, 30h
0x1800070d2  mov     dil, cl
0x1800070d5  mov     eax, cs:dword_1800120D0
0x1800070db  test    eax, eax
0x1800070dd  jg      short loc_1800070EC
0x1800070df  xor     eax, eax
0x1800070e1  mov     rbx, [rsp+38h+arg_0]
0x1800070e6  add     rsp, 30h
0x1800070ea  pop     rdi
0x1800070eb  retn
0x1800070ec  dec     eax
0x1800070ee  mov     cs:dword_1800120D0, eax
0x1800070f4  call    __scrt_acquire_startup_lock
0x1800070f9  mov     bl, al
0x1800070fb  mov     [rsp+38h+var_18], al
0x1800070ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180007106  jnz     short loc_18000713E
0x180007108  call    __scrt_dllmain_uninitialize_c
0x18000710d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180007112  call    _RTC_Terminate
0x180007117  mov     cs:__scrt_current_native_startup_state, 0
0x180007121  mov     cl, bl
0x180007123  call    __scrt_release_startup_lock
0x180007128  xor     edx, edx
0x18000712a  mov     cl, dil
0x18000712d  call    __scrt_uninitialize_crt
0x180007132  movzx   ebx, al
0x180007135  call    __scrt_dllmain_uninitialize_critical
0x18000713a  mov     eax, ebx
0x18000713c  jmp     short loc_1800070E1
0x18000713e  mov     ecx, 7
0x180007143  call    __scrt_fastfail
0x18000be79  push    rbp
0x18000be7b  sub     rsp, 20h
0x18000be7f  mov     rbp, rdx
0x18000be82  mov     cl, [rbp+20h]
0x18000be85  call    __scrt_release_startup_lock
0x18000be8a  nop
0x18000be8b  add     rsp, 20h
0x18000be8f  pop     rbp
0x18000be90  retn
0x18000be92  push    rbp
0x18000be94  sub     rsp, 20h
0x18000be98  mov     rbp, rdx
0x18000be9b  add     rsp, 20h
0x18000be9f  pop     rbp
0x18000bea0  jmp     __scrt_dllmain_uninitialize_critical
```
