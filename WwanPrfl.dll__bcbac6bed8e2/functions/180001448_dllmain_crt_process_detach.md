# dllmain_crt_process_detach

- ea: `0x180001448`
- end: `0x1800014cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012f0`

## callees

- `0x180001448`
- `0x1800016cc`
- `0x1800017f4`
- `0x18000182c`
- `0x1800019bc`
- `0x1800019e8`
- `0x180001b8c`
- `0x180001bd4`
- `0x180001c24`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001F590 <= 0 )
    return 0;
  --dword_18001F590;
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
0x180001448  mov     [rsp+arg_0], rbx
0x18000144d  push    rdi
0x18000144e  sub     rsp, 30h
0x180001452  mov     dil, cl
0x180001455  mov     eax, cs:dword_18001F590
0x18000145b  test    eax, eax
0x18000145d  jg      short loc_18000146C
0x18000145f  xor     eax, eax
0x180001461  mov     rbx, [rsp+38h+arg_0]
0x180001466  add     rsp, 30h
0x18000146a  pop     rdi
0x18000146b  retn
0x18000146c  dec     eax
0x18000146e  mov     cs:dword_18001F590, eax
0x180001474  call    __scrt_acquire_startup_lock
0x180001479  mov     bl, al
0x18000147b  mov     [rsp+38h+var_18], al
0x18000147f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001486  jnz     short loc_1800014BE
0x180001488  call    __scrt_dllmain_uninitialize_c
0x18000148d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001492  call    _RTC_Terminate
0x180001497  mov     cs:__scrt_current_native_startup_state, 0
0x1800014a1  mov     cl, bl
0x1800014a3  call    __scrt_release_startup_lock
0x1800014a8  xor     edx, edx
0x1800014aa  mov     cl, dil
0x1800014ad  call    __scrt_uninitialize_crt
0x1800014b2  movzx   ebx, al
0x1800014b5  call    __scrt_dllmain_uninitialize_critical
0x1800014ba  mov     eax, ebx
0x1800014bc  jmp     short loc_180001461
0x1800014be  mov     ecx, 7
0x1800014c3  call    __scrt_fastfail
0x1800137a9  push    rbp
0x1800137ab  sub     rsp, 20h
0x1800137af  mov     rbp, rdx
0x1800137b2  mov     cl, [rbp+20h]
0x1800137b5  call    __scrt_release_startup_lock
0x1800137ba  nop
0x1800137bb  add     rsp, 20h
0x1800137bf  pop     rbp
0x1800137c0  retn
0x1800137c2  push    rbp
0x1800137c4  sub     rsp, 20h
0x1800137c8  mov     rbp, rdx
0x1800137cb  add     rsp, 20h
0x1800137cf  pop     rbp
0x1800137d0  jmp     __scrt_dllmain_uninitialize_critical
```
