# dllmain_crt_process_detach

- ea: `0x180002248`
- end: `0x1800022cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800020f0`

## callees

- `0x180002248`
- `0x180002504`
- `0x18000262c`
- `0x180002664`
- `0x1800027f4`
- `0x180002820`
- `0x1800029e0`
- `0x180002a28`
- `0x180002a78`

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

  if ( dword_18001E470 <= 0 )
    return 0;
  --dword_18001E470;
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
0x180002248  mov     [rsp+arg_0], rbx
0x18000224d  push    rdi
0x18000224e  sub     rsp, 30h
0x180002252  mov     dil, cl
0x180002255  mov     eax, cs:dword_18001E470
0x18000225b  test    eax, eax
0x18000225d  jg      short loc_18000226C
0x18000225f  xor     eax, eax
0x180002261  mov     rbx, [rsp+38h+arg_0]
0x180002266  add     rsp, 30h
0x18000226a  pop     rdi
0x18000226b  retn
0x18000226c  dec     eax
0x18000226e  mov     cs:dword_18001E470, eax
0x180002274  call    __scrt_acquire_startup_lock
0x180002279  mov     bl, al
0x18000227b  mov     [rsp+38h+var_18], al
0x18000227f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002286  jnz     short loc_1800022BE
0x180002288  call    __scrt_dllmain_uninitialize_c
0x18000228d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002292  call    _RTC_Terminate
0x180002297  mov     cs:__scrt_current_native_startup_state, 0
0x1800022a1  mov     cl, bl
0x1800022a3  call    __scrt_release_startup_lock
0x1800022a8  xor     edx, edx
0x1800022aa  mov     cl, dil
0x1800022ad  call    __scrt_uninitialize_crt
0x1800022b2  movzx   ebx, al
0x1800022b5  call    __scrt_dllmain_uninitialize_critical
0x1800022ba  mov     eax, ebx
0x1800022bc  jmp     short loc_180002261
0x1800022be  mov     ecx, 7
0x1800022c3  call    __scrt_fastfail
0x180014119  push    rbp
0x18001411b  sub     rsp, 20h
0x18001411f  mov     rbp, rdx
0x180014122  mov     cl, [rbp+20h]
0x180014125  call    __scrt_release_startup_lock
0x18001412a  nop
0x18001412b  add     rsp, 20h
0x18001412f  pop     rbp
0x180014130  retn
0x180014132  push    rbp
0x180014134  sub     rsp, 20h
0x180014138  mov     rbp, rdx
0x18001413b  add     rsp, 20h
0x18001413f  pop     rbp
0x180014140  jmp     __scrt_dllmain_uninitialize_critical
```
