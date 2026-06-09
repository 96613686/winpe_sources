# dllmain_crt_process_detach

- ea: `0x180008868`
- end: `0x1800088eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180008710`

## callees

- `0x180008868`
- `0x180008aa4`
- `0x180008bcc`
- `0x180008c04`
- `0x180008d94`
- `0x180008dc0`
- `0x180008f5c`
- `0x180008fa4`
- `0x180008ff4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18000F2D0 <= 0 )
    return 0;
  --dword_18000F2D0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180008868  mov     [rsp+arg_0], rbx
0x18000886d  push    rdi
0x18000886e  sub     rsp, 30h
0x180008872  mov     dil, cl
0x180008875  mov     eax, cs:dword_18000F2D0
0x18000887b  test    eax, eax
0x18000887d  jg      short loc_18000888C
0x18000887f  xor     eax, eax
0x180008881  mov     rbx, [rsp+38h+arg_0]
0x180008886  add     rsp, 30h
0x18000888a  pop     rdi
0x18000888b  retn
0x18000888c  dec     eax
0x18000888e  mov     cs:dword_18000F2D0, eax
0x180008894  call    __scrt_acquire_startup_lock
0x180008899  mov     bl, al
0x18000889b  mov     [rsp+38h+var_18], al
0x18000889f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800088a6  jnz     short loc_1800088DE
0x1800088a8  call    __scrt_dllmain_uninitialize_c
0x1800088ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800088b2  call    _RTC_Terminate
0x1800088b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800088c1  mov     cl, bl
0x1800088c3  call    __scrt_release_startup_lock
0x1800088c8  xor     edx, edx
0x1800088ca  mov     cl, dil
0x1800088cd  call    __scrt_uninitialize_crt
0x1800088d2  movzx   ebx, al
0x1800088d5  call    __scrt_dllmain_uninitialize_critical
0x1800088da  mov     eax, ebx
0x1800088dc  jmp     short loc_180008881
0x1800088de  mov     ecx, 7
0x1800088e3  call    __scrt_fastfail
0x18000996f  push    rbp
0x180009971  sub     rsp, 20h
0x180009975  mov     rbp, rdx
0x180009978  mov     cl, [rbp+20h]
0x18000997b  call    __scrt_release_startup_lock
0x180009980  nop
0x180009981  add     rsp, 20h
0x180009985  pop     rbp
0x180009986  retn
0x180009988  push    rbp
0x18000998a  sub     rsp, 20h
0x18000998e  mov     rbp, rdx
0x180009991  add     rsp, 20h
0x180009995  pop     rbp
0x180009996  jmp     __scrt_dllmain_uninitialize_critical
```
