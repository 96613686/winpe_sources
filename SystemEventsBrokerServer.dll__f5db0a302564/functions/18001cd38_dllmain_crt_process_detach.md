# dllmain_crt_process_detach

- ea: `0x18001cd38`
- end: `0x18001cdbb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001cbe0`

## callees

- `0x18001cd38`
- `0x18001cfb8`
- `0x18001d0e0`
- `0x18001d118`
- `0x18001d2a8`
- `0x18001d2d4`
- `0x18001d478`
- `0x18001d4c0`
- `0x18001d510`

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

  if ( dword_180036D58 <= 0 )
    return 0;
  --dword_180036D58;
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
0x18001cd38  mov     [rsp+arg_0], rbx
0x18001cd3d  push    rdi
0x18001cd3e  sub     rsp, 30h
0x18001cd42  mov     dil, cl
0x18001cd45  mov     eax, cs:dword_180036D58
0x18001cd4b  test    eax, eax
0x18001cd4d  jg      short loc_18001CD5C
0x18001cd4f  xor     eax, eax
0x18001cd51  mov     rbx, [rsp+38h+arg_0]
0x18001cd56  add     rsp, 30h
0x18001cd5a  pop     rdi
0x18001cd5b  retn
0x18001cd5c  dec     eax
0x18001cd5e  mov     cs:dword_180036D58, eax
0x18001cd64  call    __scrt_acquire_startup_lock
0x18001cd69  mov     bl, al
0x18001cd6b  mov     [rsp+38h+var_18], al
0x18001cd6f  cmp     cs:__scrt_current_native_startup_state, 2
0x18001cd76  jnz     short loc_18001CDAE
0x18001cd78  call    __scrt_dllmain_uninitialize_c
0x18001cd7d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001cd82  call    _RTC_Terminate
0x18001cd87  mov     cs:__scrt_current_native_startup_state, 0
0x18001cd91  mov     cl, bl
0x18001cd93  call    __scrt_release_startup_lock
0x18001cd98  xor     edx, edx
0x18001cd9a  mov     cl, dil
0x18001cd9d  call    __scrt_uninitialize_crt
0x18001cda2  movzx   ebx, al
0x18001cda5  call    __scrt_dllmain_uninitialize_critical
0x18001cdaa  mov     eax, ebx
0x18001cdac  jmp     short loc_18001CD51
0x18001cdae  mov     ecx, 7
0x18001cdb3  call    __scrt_fastfail
0x180025bb4  push    rbp
0x180025bb6  sub     rsp, 20h
0x180025bba  mov     rbp, rdx
0x180025bbd  mov     cl, [rbp+20h]
0x180025bc0  call    __scrt_release_startup_lock
0x180025bc5  nop
0x180025bc6  add     rsp, 20h
0x180025bca  pop     rbp
0x180025bcb  retn
0x180025bcd  push    rbp
0x180025bcf  sub     rsp, 20h
0x180025bd3  mov     rbp, rdx
0x180025bd6  add     rsp, 20h
0x180025bda  pop     rbp
0x180025bdb  jmp     __scrt_dllmain_uninitialize_critical
```
