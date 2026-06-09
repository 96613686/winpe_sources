# dllmain_crt_process_detach

- ea: `0x18004d108`
- end: `0x18004d18b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004cfb0`

## callees

- `0x18004d108`
- `0x18004d414`
- `0x18004d44c`
- `0x18004d574`
- `0x18004d5ac`
- `0x18004d73c`
- `0x18004d768`
- `0x18004d808`
- `0x18004d858`

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

  if ( dword_1800E57D0 <= 0 )
    return 0;
  --dword_1800E57D0;
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
0x18004d108  mov     [rsp+arg_0], rbx
0x18004d10d  push    rdi
0x18004d10e  sub     rsp, 30h
0x18004d112  mov     dil, cl
0x18004d115  mov     eax, cs:dword_1800E57D0
0x18004d11b  test    eax, eax
0x18004d11d  jg      short loc_18004D12C
0x18004d11f  xor     eax, eax
0x18004d121  mov     rbx, [rsp+38h+arg_0]
0x18004d126  add     rsp, 30h
0x18004d12a  pop     rdi
0x18004d12b  retn
0x18004d12c  dec     eax
0x18004d12e  mov     cs:dword_1800E57D0, eax
0x18004d134  call    __scrt_acquire_startup_lock
0x18004d139  mov     bl, al
0x18004d13b  mov     [rsp+38h+var_18], al
0x18004d13f  cmp     cs:__scrt_current_native_startup_state, 2
0x18004d146  jnz     short loc_18004D17E
0x18004d148  call    __scrt_dllmain_uninitialize_c
0x18004d14d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18004d152  call    _RTC_Terminate
0x18004d157  mov     cs:__scrt_current_native_startup_state, 0
0x18004d161  mov     cl, bl
0x18004d163  call    __scrt_release_startup_lock
0x18004d168  xor     edx, edx
0x18004d16a  mov     cl, dil
0x18004d16d  call    __scrt_uninitialize_crt
0x18004d172  movzx   ebx, al
0x18004d175  call    __scrt_dllmain_uninitialize_critical
0x18004d17a  mov     eax, ebx
0x18004d17c  jmp     short loc_18004D121
0x18004d17e  mov     ecx, 7
0x18004d183  call    __scrt_fastfail
0x180096225  push    rbp
0x180096227  sub     rsp, 20h
0x18009622b  mov     rbp, rdx
0x18009622e  mov     cl, [rbp+20h]
0x180096231  call    __scrt_release_startup_lock
0x180096236  nop
0x180096237  add     rsp, 20h
0x18009623b  pop     rbp
0x18009623c  retn
0x18009623e  push    rbp
0x180096240  sub     rsp, 20h
0x180096244  mov     rbp, rdx
0x180096247  add     rsp, 20h
0x18009624b  pop     rbp
0x18009624c  jmp     __scrt_dllmain_uninitialize_critical
```
