# dllmain_crt_process_detach

- ea: `0x1800036c8`
- end: `0x18000374b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003570`

## callees

- `0x1800036c8`
- `0x180003984`
- `0x180003aac`
- `0x180003ae4`
- `0x180003c74`
- `0x180003ca0`
- `0x180004448`
- `0x180004490`
- `0x1800044e0`

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

  if ( dword_18002D7D0 <= 0 )
    return 0;
  --dword_18002D7D0;
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
0x1800036c8  mov     [rsp+arg_0], rbx
0x1800036cd  push    rdi
0x1800036ce  sub     rsp, 30h
0x1800036d2  mov     dil, cl
0x1800036d5  mov     eax, cs:dword_18002D7D0
0x1800036db  test    eax, eax
0x1800036dd  jg      short loc_1800036EC
0x1800036df  xor     eax, eax
0x1800036e1  mov     rbx, [rsp+38h+arg_0]
0x1800036e6  add     rsp, 30h
0x1800036ea  pop     rdi
0x1800036eb  retn
0x1800036ec  dec     eax
0x1800036ee  mov     cs:dword_18002D7D0, eax
0x1800036f4  call    __scrt_acquire_startup_lock
0x1800036f9  mov     bl, al
0x1800036fb  mov     [rsp+38h+var_18], al
0x1800036ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180003706  jnz     short loc_18000373E
0x180003708  call    __scrt_dllmain_uninitialize_c
0x18000370d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003712  call    _RTC_Terminate
0x180003717  mov     cs:__scrt_current_native_startup_state, 0
0x180003721  mov     cl, bl
0x180003723  call    __scrt_release_startup_lock
0x180003728  xor     edx, edx
0x18000372a  mov     cl, dil
0x18000372d  call    __scrt_uninitialize_crt
0x180003732  movzx   ebx, al
0x180003735  call    __scrt_dllmain_uninitialize_critical
0x18000373a  mov     eax, ebx
0x18000373c  jmp     short loc_1800036E1
0x18000373e  mov     ecx, 7
0x180003743  call    __scrt_fastfail
0x18001f919  push    rbp
0x18001f91b  sub     rsp, 20h
0x18001f91f  mov     rbp, rdx
0x18001f922  mov     cl, [rbp+20h]
0x18001f925  call    __scrt_release_startup_lock
0x18001f92a  nop
0x18001f92b  add     rsp, 20h
0x18001f92f  pop     rbp
0x18001f930  retn
0x18001f932  push    rbp
0x18001f934  sub     rsp, 20h
0x18001f938  mov     rbp, rdx
0x18001f93b  add     rsp, 20h
0x18001f93f  pop     rbp
0x18001f940  jmp     __scrt_dllmain_uninitialize_critical
```
