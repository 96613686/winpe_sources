# dllmain_crt_process_detach

- ea: `0x1800033f8`
- end: `0x18000347c`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180003290`
- `0x18000347c`

## callees

- `0x1800033f8`
- `0x180003a38`
- `0x180003a68`
- `0x180003b90`
- `0x180003bc0`
- `0x180003d44`
- `0x180003d68`
- `0x180003df8`
- `0x180003f80`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx
  DWORD v9; // edx
  HINSTANCE v10; // rcx
  LPVOID v11; // r8

  if ( dword_1800071D8 <= 0 )
    return 0;
  --dword_1800071D8;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state == 2 )
  {
    _scrt_dllmain_uninitialize_c(v3);
    __scrt_uninitialize_type_info();
    RTC_Terminate();
    _scrt_current_native_startup_state = 0;
    LOBYTE(v5) = v4;
    _scrt_release_startup_lock(v5);
    LOBYTE(v6) = a1;
    v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
    _scrt_dllmain_uninitialize_critical(v8);
    return v7;
  }
  else
  {
    _scrt_fastfail(7);
    __debugbreak();
    return dllmain_dispatch(v10, v9, v11);
  }
}

```

## disassembly

```asm
0x1800033f8  mov     [rsp+arg_0], rbx
0x1800033fd  push    rdi
0x1800033fe  sub     rsp, 30h
0x180003402  mov     dil, cl
0x180003405  mov     eax, cs:dword_1800071D8
0x18000340b  test    eax, eax
0x18000340d  jg      short loc_18000341C
0x18000340f  xor     eax, eax
0x180003411  mov     rbx, [rsp+38h+arg_0]
0x180003416  add     rsp, 30h
0x18000341a  pop     rdi
0x18000341b  retn
0x18000341c  dec     eax
0x18000341e  mov     cs:dword_1800071D8, eax
0x180003424  call    __scrt_acquire_startup_lock
0x180003429  mov     bl, al
0x18000342b  mov     [rsp+38h+var_18], al
0x18000342f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003436  jnz     short loc_18000346F
0x180003438  call    __scrt_dllmain_uninitialize_c
0x18000343d  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x180003442  call    _RTC_Terminate
0x180003447  and     cs:__scrt_current_native_startup_state, 0
0x18000344e  mov     cl, bl
0x180003450  call    __scrt_release_startup_lock
0x180003455  xor     edx, edx
0x180003457  mov     cl, dil
0x18000345a  call    __scrt_uninitialize_crt
0x18000345f  neg     al
0x180003461  sbb     ebx, ebx
0x180003463  and     ebx, 1
0x180003466  call    __scrt_dllmain_uninitialize_critical
0x18000346b  mov     eax, ebx
0x18000346d  jmp     short loc_180003411
0x18000346f  mov     ecx, 7
0x180003474  call    __scrt_fastfail
0x180003479  nop
0x18000347a  nop
0x18000347b  int     3; Trap to Debugger
0x1800043ed  push    rbp
0x1800043ef  sub     rsp, 20h
0x1800043f3  mov     rbp, rdx
0x1800043f6  mov     cl, [rbp+20h]
0x1800043f9  call    __scrt_release_startup_lock
0x1800043fe  nop
0x1800043ff  add     rsp, 20h
0x180004403  pop     rbp
0x180004404  retn
0x180004406  push    rbp
0x180004408  sub     rsp, 20h
0x18000440c  mov     rbp, rdx
0x18000440f  add     rsp, 20h
0x180004413  pop     rbp
0x180004414  jmp     __scrt_dllmain_uninitialize_critical
```
