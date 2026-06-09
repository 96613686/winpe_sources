# dllmain_crt_process_detach

- ea: `0x180003088`
- end: `0x18000310b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002f30`

## callees

- `0x180003088`
- `0x18000332c`
- `0x180003454`
- `0x18000348c`
- `0x18000361c`
- `0x180003648`
- `0x1800037ec`
- `0x180003834`
- `0x180003884`

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

  if ( dword_18004A3F0 <= 0 )
    return 0;
  --dword_18004A3F0;
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
0x180003088  mov     [rsp+arg_0], rbx
0x18000308d  push    rdi
0x18000308e  sub     rsp, 30h
0x180003092  mov     dil, cl
0x180003095  mov     eax, cs:dword_18004A3F0
0x18000309b  test    eax, eax
0x18000309d  jg      short loc_1800030AC
0x18000309f  xor     eax, eax
0x1800030a1  mov     rbx, [rsp+38h+arg_0]
0x1800030a6  add     rsp, 30h
0x1800030aa  pop     rdi
0x1800030ab  retn
0x1800030ac  dec     eax
0x1800030ae  mov     cs:dword_18004A3F0, eax
0x1800030b4  call    __scrt_acquire_startup_lock
0x1800030b9  mov     bl, al
0x1800030bb  mov     [rsp+38h+var_18], al
0x1800030bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800030c6  jnz     short loc_1800030FE
0x1800030c8  call    __scrt_dllmain_uninitialize_c
0x1800030cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800030d2  call    _RTC_Terminate
0x1800030d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800030e1  mov     cl, bl
0x1800030e3  call    __scrt_release_startup_lock
0x1800030e8  xor     edx, edx
0x1800030ea  mov     cl, dil
0x1800030ed  call    __scrt_uninitialize_crt
0x1800030f2  movzx   ebx, al
0x1800030f5  call    __scrt_dllmain_uninitialize_critical
0x1800030fa  mov     eax, ebx
0x1800030fc  jmp     short loc_1800030A1
0x1800030fe  mov     ecx, 7
0x180003103  call    __scrt_fastfail
0x1800290b9  push    rbp
0x1800290bb  sub     rsp, 20h
0x1800290bf  mov     rbp, rdx
0x1800290c2  mov     cl, [rbp+20h]
0x1800290c5  call    __scrt_release_startup_lock
0x1800290ca  nop
0x1800290cb  add     rsp, 20h
0x1800290cf  pop     rbp
0x1800290d0  retn
0x1800290d2  push    rbp
0x1800290d4  sub     rsp, 20h
0x1800290d8  mov     rbp, rdx
0x1800290db  add     rsp, 20h
0x1800290df  pop     rbp
0x1800290e0  jmp     __scrt_dllmain_uninitialize_critical
```
