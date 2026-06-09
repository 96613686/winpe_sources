# dllmain_crt_process_detach

- ea: `0x180002168`
- end: `0x1800021eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002010`

## callees

- `0x180002168`
- `0x1800023a4`
- `0x1800024cc`
- `0x180002504`
- `0x180002694`
- `0x1800026c0`
- `0x180003024`
- `0x18000306c`
- `0x1800030bc`

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

  if ( dword_1800329F0 <= 0 )
    return 0;
  --dword_1800329F0;
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
0x180002168  mov     [rsp+arg_0], rbx
0x18000216d  push    rdi
0x18000216e  sub     rsp, 30h
0x180002172  mov     dil, cl
0x180002175  mov     eax, cs:dword_1800329F0
0x18000217b  test    eax, eax
0x18000217d  jg      short loc_18000218C
0x18000217f  xor     eax, eax
0x180002181  mov     rbx, [rsp+38h+arg_0]
0x180002186  add     rsp, 30h
0x18000218a  pop     rdi
0x18000218b  retn
0x18000218c  dec     eax
0x18000218e  mov     cs:dword_1800329F0, eax
0x180002194  call    __scrt_acquire_startup_lock
0x180002199  mov     bl, al
0x18000219b  mov     [rsp+38h+var_18], al
0x18000219f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800021a6  jnz     short loc_1800021DE
0x1800021a8  call    __scrt_dllmain_uninitialize_c
0x1800021ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800021b2  call    _RTC_Terminate
0x1800021b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800021c1  mov     cl, bl
0x1800021c3  call    __scrt_release_startup_lock
0x1800021c8  xor     edx, edx
0x1800021ca  mov     cl, dil
0x1800021cd  call    __scrt_uninitialize_crt
0x1800021d2  movzx   ebx, al
0x1800021d5  call    __scrt_dllmain_uninitialize_critical
0x1800021da  mov     eax, ebx
0x1800021dc  jmp     short loc_180002181
0x1800021de  mov     ecx, 7
0x1800021e3  call    __scrt_fastfail
0x18002288d  push    rbp
0x18002288f  sub     rsp, 20h
0x180022893  mov     rbp, rdx
0x180022896  mov     cl, [rbp+20h]
0x180022899  call    __scrt_release_startup_lock
0x18002289e  nop
0x18002289f  add     rsp, 20h
0x1800228a3  pop     rbp
0x1800228a4  retn
0x1800228a6  push    rbp
0x1800228a8  sub     rsp, 20h
0x1800228ac  mov     rbp, rdx
0x1800228af  add     rsp, 20h
0x1800228b3  pop     rbp
0x1800228b4  jmp     __scrt_dllmain_uninitialize_critical
```
