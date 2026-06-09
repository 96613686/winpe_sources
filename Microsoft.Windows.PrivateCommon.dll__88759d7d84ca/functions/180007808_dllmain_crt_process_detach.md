# dllmain_crt_process_detach

- ea: `0x180007808`
- end: `0x18000788b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800076a0`
- `0x18000788c`

## callees

- `0x1800072f0`
- `0x180007418`
- `0x180007448`
- `0x1800075bc`
- `0x1800075e0`
- `0x180007808`
- `0x180007ee0`
- `0x1800080fc`
- `0x180008170`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180015BB8 <= 0 )
    return 0;
  --dword_180015BB8;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7u);
    __debugbreak();
    JUMPOUT(0x18000788BLL);
  }
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
0x180007808  mov     [rsp+arg_0], rbx
0x18000780d  push    rdi
0x18000780e  sub     rsp, 30h
0x180007812  mov     dil, cl
0x180007815  mov     eax, cs:dword_180015BB8
0x18000781b  test    eax, eax
0x18000781d  jg      short loc_18000782C
0x18000781f  xor     eax, eax
0x180007821  mov     rbx, [rsp+38h+arg_0]
0x180007826  add     rsp, 30h
0x18000782a  pop     rdi
0x18000782b  retn
0x18000782c  dec     eax
0x18000782e  mov     cs:dword_180015BB8, eax
0x180007834  call    __scrt_acquire_startup_lock
0x180007839  mov     bl, al
0x18000783b  mov     [rsp+38h+var_18], al
0x18000783f  cmp     cs:__scrt_current_native_startup_state, 2
0x180007846  jnz     short loc_18000787E
0x180007848  call    __scrt_dllmain_uninitialize_c
0x18000784d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180007852  call    _RTC_Terminate
0x180007857  mov     cs:__scrt_current_native_startup_state, 0
0x180007861  mov     cl, bl
0x180007863  call    __scrt_release_startup_lock
0x180007868  xor     edx, edx
0x18000786a  mov     cl, dil
0x18000786d  call    __scrt_uninitialize_crt
0x180007872  movzx   ebx, al
0x180007875  call    __scrt_dllmain_uninitialize_critical
0x18000787a  mov     eax, ebx
0x18000787c  jmp     short loc_180007821
0x18000787e  mov     ecx, 7
0x180007883  call    __scrt_fastfail
0x180007888  nop
0x180007889  nop
0x18000788a  int     3; Trap to Debugger
0x18000c9c9  push    rbp
0x18000c9cb  sub     rsp, 20h
0x18000c9cf  mov     rbp, rdx
0x18000c9d2  mov     cl, [rbp+20h]
0x18000c9d5  call    __scrt_release_startup_lock
0x18000c9da  nop
0x18000c9db  add     rsp, 20h
0x18000c9df  pop     rbp
0x18000c9e0  retn
0x18000c9e2  push    rbp
0x18000c9e4  sub     rsp, 20h
0x18000c9e8  mov     rbp, rdx
0x18000c9eb  add     rsp, 20h
0x18000c9ef  pop     rbp
0x18000c9f0  jmp     __scrt_dllmain_uninitialize_critical
```
