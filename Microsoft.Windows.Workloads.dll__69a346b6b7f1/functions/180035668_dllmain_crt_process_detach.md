# dllmain_crt_process_detach

- ea: `0x180035668`
- end: `0x1800356eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180035500`
- `0x1800356ec`

## callees

- `0x1800350a4`
- `0x1800351cc`
- `0x1800351fc`
- `0x180035370`
- `0x180035394`
- `0x180035668`
- `0x180035e88`
- `0x180036094`
- `0x180036100`

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

  if ( dword_1800595A8 <= 0 )
    return 0;
  --dword_1800595A8;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800356EBLL);
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
0x180035668  mov     [rsp+arg_0], rbx
0x18003566d  push    rdi
0x18003566e  sub     rsp, 30h
0x180035672  mov     dil, cl
0x180035675  mov     eax, cs:dword_1800595A8
0x18003567b  test    eax, eax
0x18003567d  jg      short loc_18003568C
0x18003567f  xor     eax, eax
0x180035681  mov     rbx, [rsp+38h+arg_0]
0x180035686  add     rsp, 30h
0x18003568a  pop     rdi
0x18003568b  retn
0x18003568c  dec     eax
0x18003568e  mov     cs:dword_1800595A8, eax
0x180035694  call    __scrt_acquire_startup_lock
0x180035699  mov     bl, al
0x18003569b  mov     [rsp+38h+var_18], al
0x18003569f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800356a6  jnz     short loc_1800356DE
0x1800356a8  call    __scrt_dllmain_uninitialize_c
0x1800356ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800356b2  call    _RTC_Terminate
0x1800356b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800356c1  mov     cl, bl
0x1800356c3  call    __scrt_release_startup_lock
0x1800356c8  xor     edx, edx
0x1800356ca  mov     cl, dil
0x1800356cd  call    __scrt_uninitialize_crt
0x1800356d2  movzx   ebx, al
0x1800356d5  call    __scrt_dllmain_uninitialize_critical
0x1800356da  mov     eax, ebx
0x1800356dc  jmp     short loc_180035681
0x1800356de  mov     ecx, 7
0x1800356e3  call    __scrt_fastfail
0x1800356e8  nop
0x1800356e9  nop
0x1800356ea  int     3; Trap to Debugger
0x180040b8e  push    rbp
0x180040b90  sub     rsp, 20h
0x180040b94  mov     rbp, rdx
0x180040b97  mov     cl, [rbp+20h]
0x180040b9a  call    __scrt_release_startup_lock
0x180040b9f  nop
0x180040ba0  add     rsp, 20h
0x180040ba4  pop     rbp
0x180040ba5  retn
0x180040ba7  push    rbp
0x180040ba9  sub     rsp, 20h
0x180040bad  mov     rbp, rdx
0x180040bb0  add     rsp, 20h
0x180040bb4  pop     rbp
0x180040bb5  jmp     __scrt_dllmain_uninitialize_critical
```
