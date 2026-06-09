# dllmain_crt_process_detach

- ea: `0x180003348`
- end: `0x1800033cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800031f0`

## callees

- `0x180003348`
- `0x180003584`
- `0x1800036ac`
- `0x1800036e4`
- `0x180003874`
- `0x1800038a0`
- `0x180003a6c`
- `0x180003ab4`
- `0x180003b04`

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

  if ( dword_180043570 <= 0 )
    return 0;
  --dword_180043570;
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
0x180003348  mov     [rsp+arg_0], rbx
0x18000334d  push    rdi
0x18000334e  sub     rsp, 30h
0x180003352  mov     dil, cl
0x180003355  mov     eax, cs:dword_180043570
0x18000335b  test    eax, eax
0x18000335d  jg      short loc_18000336C
0x18000335f  xor     eax, eax
0x180003361  mov     rbx, [rsp+38h+arg_0]
0x180003366  add     rsp, 30h
0x18000336a  pop     rdi
0x18000336b  retn
0x18000336c  dec     eax
0x18000336e  mov     cs:dword_180043570, eax
0x180003374  call    __scrt_acquire_startup_lock
0x180003379  mov     bl, al
0x18000337b  mov     [rsp+38h+var_18], al
0x18000337f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003386  jnz     short loc_1800033BE
0x180003388  call    __scrt_dllmain_uninitialize_c
0x18000338d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003392  call    _RTC_Terminate
0x180003397  mov     cs:__scrt_current_native_startup_state, 0
0x1800033a1  mov     cl, bl
0x1800033a3  call    __scrt_release_startup_lock
0x1800033a8  xor     edx, edx
0x1800033aa  mov     cl, dil
0x1800033ad  call    __scrt_uninitialize_crt
0x1800033b2  movzx   ebx, al
0x1800033b5  call    __scrt_dllmain_uninitialize_critical
0x1800033ba  mov     eax, ebx
0x1800033bc  jmp     short loc_180003361
0x1800033be  mov     ecx, 7
0x1800033c3  call    __scrt_fastfail
0x18002e739  push    rbp
0x18002e73b  sub     rsp, 20h
0x18002e73f  mov     rbp, rdx
0x18002e742  mov     cl, [rbp+20h]
0x18002e745  call    __scrt_release_startup_lock
0x18002e74a  nop
0x18002e74b  add     rsp, 20h
0x18002e74f  pop     rbp
0x18002e750  retn
0x18002e752  push    rbp
0x18002e754  sub     rsp, 20h
0x18002e758  mov     rbp, rdx
0x18002e75b  add     rsp, 20h
0x18002e75f  pop     rbp
0x18002e760  jmp     __scrt_dllmain_uninitialize_critical
```
