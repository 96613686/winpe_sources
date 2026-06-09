# dllmain_crt_process_detach

- ea: `0x180042db0`
- end: `0x180042e33`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180042c40`

## callees

- `0x1800427f4`
- `0x180042940`
- `0x180042978`
- `0x180042b08`
- `0x180042b34`
- `0x180042db0`
- `0x1800437a4`
- `0x1800439ec`
- `0x180043a78`

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

  if ( dword_180062C84 <= 0 )
    return 0;
  --dword_180062C84;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180042E33LL);
  }
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
0x180042db0  mov     [rsp+arg_0], rbx
0x180042db5  push    rdi
0x180042db6  sub     rsp, 30h
0x180042dba  mov     dil, cl
0x180042dbd  mov     eax, cs:dword_180062C84
0x180042dc3  test    eax, eax
0x180042dc5  jg      short loc_180042DD4
0x180042dc7  xor     eax, eax
0x180042dc9  mov     rbx, [rsp+38h+arg_0]
0x180042dce  add     rsp, 30h
0x180042dd2  pop     rdi
0x180042dd3  retn
0x180042dd4  dec     eax
0x180042dd6  mov     cs:dword_180062C84, eax
0x180042ddc  call    __scrt_acquire_startup_lock
0x180042de1  mov     bl, al
0x180042de3  mov     [rsp+38h+var_18], al
0x180042de7  cmp     cs:__scrt_current_native_startup_state, 2
0x180042dee  jnz     short loc_180042E26
0x180042df0  call    __scrt_dllmain_uninitialize_c
0x180042df5  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180042dfa  call    _RTC_Terminate
0x180042dff  mov     cs:__scrt_current_native_startup_state, 0
0x180042e09  mov     cl, bl
0x180042e0b  call    __scrt_release_startup_lock
0x180042e10  xor     edx, edx
0x180042e12  mov     cl, dil
0x180042e15  call    __scrt_uninitialize_crt
0x180042e1a  movzx   ebx, al
0x180042e1d  call    __scrt_dllmain_uninitialize_critical
0x180042e22  mov     eax, ebx
0x180042e24  jmp     short loc_180042DC9
0x180042e26  mov     ecx, 7
0x180042e2b  call    __scrt_fastfail
0x180042e30  nop
0x180042e31  nop
0x180042e32  int     3; Trap to Debugger
0x18004d332  push    rbp
0x18004d334  sub     rsp, 20h
0x18004d338  mov     rbp, rdx
0x18004d33b  mov     cl, [rbp+20h]
0x18004d33e  call    __scrt_release_startup_lock
0x18004d343  nop
0x18004d344  add     rsp, 20h
0x18004d348  pop     rbp
0x18004d349  retn
0x18004d34b  push    rbp
0x18004d34d  sub     rsp, 20h
0x18004d351  mov     rbp, rdx
0x18004d354  add     rsp, 20h
0x18004d358  pop     rbp
0x18004d359  jmp     __scrt_dllmain_uninitialize_critical
```
