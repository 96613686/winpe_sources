# dllmain_crt_process_detach

- ea: `0x1800016c8`
- end: `0x18000174b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001570`

## callees

- `0x1800016c8`
- `0x180001904`
- `0x180001a2c`
- `0x180001a64`
- `0x180001bf4`
- `0x180001c20`
- `0x180001e0c`
- `0x180001e54`
- `0x180001ea4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002F5D0 <= 0 )
    return 0;
  --dword_18002F5D0;
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
0x1800016c8  mov     [rsp+arg_0], rbx
0x1800016cd  push    rdi
0x1800016ce  sub     rsp, 30h
0x1800016d2  mov     dil, cl
0x1800016d5  mov     eax, cs:dword_18002F5D0
0x1800016db  test    eax, eax
0x1800016dd  jg      short loc_1800016EC
0x1800016df  xor     eax, eax
0x1800016e1  mov     rbx, [rsp+38h+arg_0]
0x1800016e6  add     rsp, 30h
0x1800016ea  pop     rdi
0x1800016eb  retn
0x1800016ec  dec     eax
0x1800016ee  mov     cs:dword_18002F5D0, eax
0x1800016f4  call    __scrt_acquire_startup_lock
0x1800016f9  mov     bl, al
0x1800016fb  mov     [rsp+38h+var_18], al
0x1800016ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001706  jnz     short loc_18000173E
0x180001708  call    __scrt_dllmain_uninitialize_c
0x18000170d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001712  call    _RTC_Terminate
0x180001717  mov     cs:__scrt_current_native_startup_state, 0
0x180001721  mov     cl, bl
0x180001723  call    __scrt_release_startup_lock
0x180001728  xor     edx, edx
0x18000172a  mov     cl, dil
0x18000172d  call    __scrt_uninitialize_crt
0x180001732  movzx   ebx, al
0x180001735  call    __scrt_dllmain_uninitialize_critical
0x18000173a  mov     eax, ebx
0x18000173c  jmp     short loc_1800016E1
0x18000173e  mov     ecx, 7
0x180001743  call    __scrt_fastfail
0x1800266e9  push    rbp
0x1800266eb  sub     rsp, 20h
0x1800266ef  mov     rbp, rdx
0x1800266f2  mov     cl, [rbp+20h]
0x1800266f5  call    __scrt_release_startup_lock
0x1800266fa  nop
0x1800266fb  add     rsp, 20h
0x1800266ff  pop     rbp
0x180026700  retn
0x180026702  push    rbp
0x180026704  sub     rsp, 20h
0x180026708  mov     rbp, rdx
0x18002670b  add     rsp, 20h
0x18002670f  pop     rbp
0x180026710  jmp     __scrt_dllmain_uninitialize_critical
```
