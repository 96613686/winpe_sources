# dllmain_crt_process_detach

- ea: `0x1800018a8`
- end: `0x18000192b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001750`

## callees

- `0x1800018a8`
- `0x180001ae4`
- `0x180001c0c`
- `0x180001c44`
- `0x180001dd4`
- `0x180001e00`
- `0x180001fec`
- `0x180002034`
- `0x180002084`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002F7D0 <= 0 )
    return 0;
  --dword_18002F7D0;
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
0x1800018a8  mov     [rsp+arg_0], rbx
0x1800018ad  push    rdi
0x1800018ae  sub     rsp, 30h
0x1800018b2  mov     dil, cl
0x1800018b5  mov     eax, cs:dword_18002F7D0
0x1800018bb  test    eax, eax
0x1800018bd  jg      short loc_1800018CC
0x1800018bf  xor     eax, eax
0x1800018c1  mov     rbx, [rsp+38h+arg_0]
0x1800018c6  add     rsp, 30h
0x1800018ca  pop     rdi
0x1800018cb  retn
0x1800018cc  dec     eax
0x1800018ce  mov     cs:dword_18002F7D0, eax
0x1800018d4  call    __scrt_acquire_startup_lock
0x1800018d9  mov     bl, al
0x1800018db  mov     [rsp+38h+var_18], al
0x1800018df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800018e6  jnz     short loc_18000191E
0x1800018e8  call    __scrt_dllmain_uninitialize_c
0x1800018ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800018f2  call    _RTC_Terminate
0x1800018f7  mov     cs:__scrt_current_native_startup_state, 0
0x180001901  mov     cl, bl
0x180001903  call    __scrt_release_startup_lock
0x180001908  xor     edx, edx
0x18000190a  mov     cl, dil
0x18000190d  call    __scrt_uninitialize_crt
0x180001912  movzx   ebx, al
0x180001915  call    __scrt_dllmain_uninitialize_critical
0x18000191a  mov     eax, ebx
0x18000191c  jmp     short loc_1800018C1
0x18000191e  mov     ecx, 7
0x180001923  call    __scrt_fastfail
0x1800229f9  push    rbp
0x1800229fb  sub     rsp, 20h
0x1800229ff  mov     rbp, rdx
0x180022a02  mov     cl, [rbp+20h]
0x180022a05  call    __scrt_release_startup_lock
0x180022a0a  nop
0x180022a0b  add     rsp, 20h
0x180022a0f  pop     rbp
0x180022a10  retn
0x180022a12  push    rbp
0x180022a14  sub     rsp, 20h
0x180022a18  mov     rbp, rdx
0x180022a1b  add     rsp, 20h
0x180022a1f  pop     rbp
0x180022a20  jmp     __scrt_dllmain_uninitialize_critical
```
