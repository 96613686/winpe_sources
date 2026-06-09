# dllmain_crt_process_detach

- ea: `0x180001248`
- end: `0x1800012cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001248`
- `0x180001560`
- `0x180001598`
- `0x1800016c0`
- `0x1800016f8`
- `0x180001888`
- `0x1800018b4`
- `0x1800018f4`
- `0x180001944`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_180007090 <= 0 )
    return 0;
  --dword_180007090;
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
0x180001248  mov     [rsp+arg_0], rbx
0x18000124d  push    rdi
0x18000124e  sub     rsp, 30h
0x180001252  mov     dil, cl
0x180001255  mov     eax, cs:dword_180007090
0x18000125b  test    eax, eax
0x18000125d  jg      short loc_18000126C
0x18000125f  xor     eax, eax
0x180001261  mov     rbx, [rsp+38h+arg_0]
0x180001266  add     rsp, 30h
0x18000126a  pop     rdi
0x18000126b  retn
0x18000126c  dec     eax
0x18000126e  mov     cs:dword_180007090, eax
0x180001274  call    __scrt_acquire_startup_lock
0x180001279  mov     bl, al
0x18000127b  mov     [rsp+38h+var_18], al
0x18000127f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001286  jnz     short loc_1800012BE
0x180001288  call    __scrt_dllmain_uninitialize_c
0x18000128d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001292  call    _RTC_Terminate
0x180001297  mov     cs:__scrt_current_native_startup_state, 0
0x1800012a1  mov     cl, bl
0x1800012a3  call    __scrt_release_startup_lock
0x1800012a8  xor     edx, edx
0x1800012aa  mov     cl, dil
0x1800012ad  call    __scrt_uninitialize_crt
0x1800012b2  movzx   ebx, al
0x1800012b5  call    __scrt_dllmain_uninitialize_critical
0x1800012ba  mov     eax, ebx
0x1800012bc  jmp     short loc_180001261
0x1800012be  mov     ecx, 7
0x1800012c3  call    __scrt_fastfail
0x180003169  push    rbp
0x18000316b  sub     rsp, 20h
0x18000316f  mov     rbp, rdx
0x180003172  mov     cl, [rbp+20h]
0x180003175  call    __scrt_release_startup_lock
0x18000317a  nop
0x18000317b  add     rsp, 20h
0x18000317f  pop     rbp
0x180003180  retn
0x180003182  push    rbp
0x180003184  sub     rsp, 20h
0x180003188  mov     rbp, rdx
0x18000318b  add     rsp, 20h
0x18000318f  pop     rbp
0x180003190  jmp     __scrt_dllmain_uninitialize_critical
```
