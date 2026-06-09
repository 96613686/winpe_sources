# dllmain_crt_process_detach

- ea: `0x180001698`
- end: `0x18000171b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001540`

## callees

- `0x180001698`
- `0x1800019a4`
- `0x1800019dc`
- `0x180001b04`
- `0x180001b3c`
- `0x180001ccc`
- `0x180001cf8`
- `0x180001d38`
- `0x180001d88`

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

  if ( dword_180039650 <= 0 )
    return 0;
  --dword_180039650;
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
0x180001698  mov     [rsp+arg_0], rbx
0x18000169d  push    rdi
0x18000169e  sub     rsp, 30h
0x1800016a2  mov     dil, cl
0x1800016a5  mov     eax, cs:dword_180039650
0x1800016ab  test    eax, eax
0x1800016ad  jg      short loc_1800016BC
0x1800016af  xor     eax, eax
0x1800016b1  mov     rbx, [rsp+38h+arg_0]
0x1800016b6  add     rsp, 30h
0x1800016ba  pop     rdi
0x1800016bb  retn
0x1800016bc  dec     eax
0x1800016be  mov     cs:dword_180039650, eax
0x1800016c4  call    __scrt_acquire_startup_lock
0x1800016c9  mov     bl, al
0x1800016cb  mov     [rsp+38h+var_18], al
0x1800016cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800016d6  jnz     short loc_18000170E
0x1800016d8  call    __scrt_dllmain_uninitialize_c
0x1800016dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800016e2  call    _RTC_Terminate
0x1800016e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800016f1  mov     cl, bl
0x1800016f3  call    __scrt_release_startup_lock
0x1800016f8  xor     edx, edx
0x1800016fa  mov     cl, dil
0x1800016fd  call    __scrt_uninitialize_crt
0x180001702  movzx   ebx, al
0x180001705  call    __scrt_dllmain_uninitialize_critical
0x18000170a  mov     eax, ebx
0x18000170c  jmp     short loc_1800016B1
0x18000170e  mov     ecx, 7
0x180001713  call    __scrt_fastfail
0x180021099  push    rbp
0x18002109b  sub     rsp, 20h
0x18002109f  mov     rbp, rdx
0x1800210a2  mov     cl, [rbp+20h]
0x1800210a5  call    __scrt_release_startup_lock
0x1800210aa  nop
0x1800210ab  add     rsp, 20h
0x1800210af  pop     rbp
0x1800210b0  retn
0x1800210b2  push    rbp
0x1800210b4  sub     rsp, 20h
0x1800210b8  mov     rbp, rdx
0x1800210bb  add     rsp, 20h
0x1800210bf  pop     rbp
0x1800210c0  jmp     __scrt_dllmain_uninitialize_critical
```
