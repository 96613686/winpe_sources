# dllmain_crt_process_detach

- ea: `0x1800014a8`
- end: `0x18000152b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001350`

## callees

- `0x1800014a8`
- `0x1800017c0`
- `0x1800018e8`
- `0x180001920`
- `0x180001ab0`
- `0x180001adc`
- `0x180001c48`
- `0x180001c90`
- `0x180001ce0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001A210 <= 0 )
    return 0;
  --dword_18001A210;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
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
0x1800014a8  mov     [rsp+arg_0], rbx
0x1800014ad  push    rdi
0x1800014ae  sub     rsp, 30h
0x1800014b2  mov     dil, cl
0x1800014b5  mov     eax, cs:dword_18001A210
0x1800014bb  test    eax, eax
0x1800014bd  jg      short loc_1800014CC
0x1800014bf  xor     eax, eax
0x1800014c1  mov     rbx, [rsp+38h+arg_0]
0x1800014c6  add     rsp, 30h
0x1800014ca  pop     rdi
0x1800014cb  retn
0x1800014cc  dec     eax
0x1800014ce  mov     cs:dword_18001A210, eax
0x1800014d4  call    __scrt_acquire_startup_lock
0x1800014d9  mov     bl, al
0x1800014db  mov     [rsp+38h+var_18], al
0x1800014df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800014e6  jnz     short loc_18000151E
0x1800014e8  call    __scrt_dllmain_uninitialize_c
0x1800014ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800014f2  call    _RTC_Terminate
0x1800014f7  mov     cs:__scrt_current_native_startup_state, 0
0x180001501  mov     cl, bl
0x180001503  call    __scrt_release_startup_lock
0x180001508  xor     edx, edx
0x18000150a  mov     cl, dil
0x18000150d  call    __scrt_uninitialize_crt
0x180001512  movzx   ebx, al
0x180001515  call    __scrt_dllmain_uninitialize_critical
0x18000151a  mov     eax, ebx
0x18000151c  jmp     short loc_1800014C1
0x18000151e  mov     ecx, 7
0x180001523  call    __scrt_fastfail
0x180011539  push    rbp
0x18001153b  sub     rsp, 20h
0x18001153f  mov     rbp, rdx
0x180011542  mov     cl, [rbp+20h]
0x180011545  call    __scrt_release_startup_lock
0x18001154a  nop
0x18001154b  add     rsp, 20h
0x18001154f  pop     rbp
0x180011550  retn
0x180011552  push    rbp
0x180011554  sub     rsp, 20h
0x180011558  mov     rbp, rdx
0x18001155b  add     rsp, 20h
0x18001155f  pop     rbp
0x180011560  jmp     __scrt_dllmain_uninitialize_critical
```
