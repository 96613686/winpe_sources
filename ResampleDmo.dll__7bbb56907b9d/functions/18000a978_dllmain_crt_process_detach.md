# dllmain_crt_process_detach

- ea: `0x18000a978`
- end: `0x18000a9fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000a820`

## callees

- `0x18000a978`
- `0x18000ad10`
- `0x18000ad48`
- `0x18000ae70`
- `0x18000aea8`
- `0x18000b038`
- `0x18000b064`
- `0x18000b104`
- `0x18000b154`

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

  if ( dword_1800B4B50 <= 0 )
    return 0;
  --dword_1800B4B50;
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
0x18000a978  mov     [rsp+arg_0], rbx
0x18000a97d  push    rdi
0x18000a97e  sub     rsp, 30h
0x18000a982  mov     dil, cl
0x18000a985  mov     eax, cs:dword_1800B4B50
0x18000a98b  test    eax, eax
0x18000a98d  jg      short loc_18000A99C
0x18000a98f  xor     eax, eax
0x18000a991  mov     rbx, [rsp+38h+arg_0]
0x18000a996  add     rsp, 30h
0x18000a99a  pop     rdi
0x18000a99b  retn
0x18000a99c  dec     eax
0x18000a99e  mov     cs:dword_1800B4B50, eax
0x18000a9a4  call    __scrt_acquire_startup_lock
0x18000a9a9  mov     bl, al
0x18000a9ab  mov     [rsp+38h+var_18], al
0x18000a9af  cmp     cs:__scrt_current_native_startup_state, 2
0x18000a9b6  jnz     short loc_18000A9EE
0x18000a9b8  call    __scrt_dllmain_uninitialize_c
0x18000a9bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000a9c2  call    _RTC_Terminate
0x18000a9c7  mov     cs:__scrt_current_native_startup_state, 0
0x18000a9d1  mov     cl, bl
0x18000a9d3  call    __scrt_release_startup_lock
0x18000a9d8  xor     edx, edx
0x18000a9da  mov     cl, dil
0x18000a9dd  call    __scrt_uninitialize_crt
0x18000a9e2  movzx   ebx, al
0x18000a9e5  call    __scrt_dllmain_uninitialize_critical
0x18000a9ea  mov     eax, ebx
0x18000a9ec  jmp     short loc_18000A991
0x18000a9ee  mov     ecx, 7
0x18000a9f3  call    __scrt_fastfail
0x18008473d  push    rbp
0x18008473f  sub     rsp, 20h
0x180084743  mov     rbp, rdx
0x180084746  mov     cl, [rbp+20h]
0x180084749  call    __scrt_release_startup_lock
0x18008474e  nop
0x18008474f  add     rsp, 20h
0x180084753  pop     rbp
0x180084754  retn
0x180084756  push    rbp
0x180084758  sub     rsp, 20h
0x18008475c  mov     rbp, rdx
0x18008475f  add     rsp, 20h
0x180084763  pop     rbp
0x180084764  jmp     __scrt_dllmain_uninitialize_critical
```
