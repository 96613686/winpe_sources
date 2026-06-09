# dllmain_crt_process_detach

- ea: `0x180001378`
- end: `0x1800013fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001378`
- `0x1800015b4`
- `0x1800016dc`
- `0x180001714`
- `0x1800018a4`
- `0x1800018d0`
- `0x180001a98`
- `0x180001ae0`
- `0x180001b30`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000B1B0 <= 0 )
    return 0;
  --dword_18000B1B0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180001378  mov     [rsp+arg_0], rbx
0x18000137d  push    rdi
0x18000137e  sub     rsp, 30h
0x180001382  mov     dil, cl
0x180001385  mov     eax, cs:dword_18000B1B0
0x18000138b  test    eax, eax
0x18000138d  jg      short loc_18000139C
0x18000138f  xor     eax, eax
0x180001391  mov     rbx, [rsp+38h+arg_0]
0x180001396  add     rsp, 30h
0x18000139a  pop     rdi
0x18000139b  retn
0x18000139c  dec     eax
0x18000139e  mov     cs:dword_18000B1B0, eax
0x1800013a4  call    __scrt_acquire_startup_lock
0x1800013a9  mov     bl, al
0x1800013ab  mov     [rsp+38h+var_18], al
0x1800013af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013b6  jnz     short loc_1800013EE
0x1800013b8  call    __scrt_dllmain_uninitialize_c
0x1800013bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013c2  call    _RTC_Terminate
0x1800013c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800013d1  mov     cl, bl
0x1800013d3  call    __scrt_release_startup_lock
0x1800013d8  xor     edx, edx
0x1800013da  mov     cl, dil
0x1800013dd  call    __scrt_uninitialize_crt
0x1800013e2  movzx   ebx, al
0x1800013e5  call    __scrt_dllmain_uninitialize_critical
0x1800013ea  mov     eax, ebx
0x1800013ec  jmp     short loc_180001391
0x1800013ee  mov     ecx, 7
0x1800013f3  call    __scrt_fastfail
0x180006269  push    rbp
0x18000626b  sub     rsp, 20h
0x18000626f  mov     rbp, rdx
0x180006272  mov     cl, [rbp+20h]
0x180006275  call    __scrt_release_startup_lock
0x18000627a  nop
0x18000627b  add     rsp, 20h
0x18000627f  pop     rbp
0x180006280  retn
0x180006282  push    rbp
0x180006284  sub     rsp, 20h
0x180006288  mov     rbp, rdx
0x18000628b  add     rsp, 20h
0x18000628f  pop     rbp
0x180006290  jmp     __scrt_dllmain_uninitialize_critical
```
