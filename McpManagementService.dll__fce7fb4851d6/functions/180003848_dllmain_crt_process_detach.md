# dllmain_crt_process_detach

- ea: `0x180003848`
- end: `0x1800038cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800036f0`

## callees

- `0x180003848`
- `0x180003b08`
- `0x180003c30`
- `0x180003c68`
- `0x180003df8`
- `0x180003e24`
- `0x180004308`
- `0x180004350`
- `0x1800043a0`

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

  if ( dword_18003F4D0 <= 0 )
    return 0;
  --dword_18003F4D0;
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
0x180003848  mov     [rsp+arg_0], rbx
0x18000384d  push    rdi
0x18000384e  sub     rsp, 30h
0x180003852  mov     dil, cl
0x180003855  mov     eax, cs:dword_18003F4D0
0x18000385b  test    eax, eax
0x18000385d  jg      short loc_18000386C
0x18000385f  xor     eax, eax
0x180003861  mov     rbx, [rsp+38h+arg_0]
0x180003866  add     rsp, 30h
0x18000386a  pop     rdi
0x18000386b  retn
0x18000386c  dec     eax
0x18000386e  mov     cs:dword_18003F4D0, eax
0x180003874  call    __scrt_acquire_startup_lock
0x180003879  mov     bl, al
0x18000387b  mov     [rsp+38h+var_18], al
0x18000387f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003886  jnz     short loc_1800038BE
0x180003888  call    __scrt_dllmain_uninitialize_c
0x18000388d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003892  call    _RTC_Terminate
0x180003897  mov     cs:__scrt_current_native_startup_state, 0
0x1800038a1  mov     cl, bl
0x1800038a3  call    __scrt_release_startup_lock
0x1800038a8  xor     edx, edx
0x1800038aa  mov     cl, dil
0x1800038ad  call    __scrt_uninitialize_crt
0x1800038b2  movzx   ebx, al
0x1800038b5  call    __scrt_dllmain_uninitialize_critical
0x1800038ba  mov     eax, ebx
0x1800038bc  jmp     short loc_180003861
0x1800038be  mov     ecx, 7
0x1800038c3  call    __scrt_fastfail
0x180027a09  push    rbp
0x180027a0b  sub     rsp, 20h
0x180027a0f  mov     rbp, rdx
0x180027a12  mov     cl, [rbp+20h]
0x180027a15  call    __scrt_release_startup_lock
0x180027a1a  nop
0x180027a1b  add     rsp, 20h
0x180027a1f  pop     rbp
0x180027a20  retn
0x180027a22  push    rbp
0x180027a24  sub     rsp, 20h
0x180027a28  mov     rbp, rdx
0x180027a2b  add     rsp, 20h
0x180027a2f  pop     rbp
0x180027a30  jmp     __scrt_dllmain_uninitialize_critical
```
