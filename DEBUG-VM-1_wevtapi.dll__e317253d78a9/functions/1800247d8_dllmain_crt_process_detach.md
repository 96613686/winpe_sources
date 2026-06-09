# dllmain_crt_process_detach

- ea: `0x1800247d8`
- end: `0x18002485b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180024680`

## callees

- `0x1800247d8`
- `0x180024a4c`
- `0x180024b74`
- `0x180024bac`
- `0x180024d3c`
- `0x180024d68`
- `0x18002500c`
- `0x180025054`
- `0x1800250a4`

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

  if ( dword_18004B290 <= 0 )
    return 0;
  --dword_18004B290;
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
0x1800247d8  mov     [rsp+arg_0], rbx
0x1800247dd  push    rdi
0x1800247de  sub     rsp, 30h
0x1800247e2  mov     dil, cl
0x1800247e5  mov     eax, cs:dword_18004B290
0x1800247eb  test    eax, eax
0x1800247ed  jg      short loc_1800247FC
0x1800247ef  xor     eax, eax
0x1800247f1  mov     rbx, [rsp+38h+arg_0]
0x1800247f6  add     rsp, 30h
0x1800247fa  pop     rdi
0x1800247fb  retn
0x1800247fc  dec     eax
0x1800247fe  mov     cs:dword_18004B290, eax
0x180024804  call    __scrt_acquire_startup_lock
0x180024809  mov     bl, al
0x18002480b  mov     [rsp+38h+var_18], al
0x18002480f  cmp     cs:__scrt_current_native_startup_state, 2
0x180024816  jnz     short loc_18002484E
0x180024818  call    __scrt_dllmain_uninitialize_c
0x18002481d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180024822  call    _RTC_Terminate
0x180024827  mov     cs:__scrt_current_native_startup_state, 0
0x180024831  mov     cl, bl
0x180024833  call    __scrt_release_startup_lock
0x180024838  xor     edx, edx
0x18002483a  mov     cl, dil
0x18002483d  call    __scrt_uninitialize_crt
0x180024842  movzx   ebx, al
0x180024845  call    __scrt_dllmain_uninitialize_critical
0x18002484a  mov     eax, ebx
0x18002484c  jmp     short loc_1800247F1
0x18002484e  mov     ecx, 7
0x180024853  call    __scrt_fastfail
0x18003a834  push    rbp
0x18003a836  sub     rsp, 20h
0x18003a83a  mov     rbp, rdx
0x18003a83d  mov     cl, [rbp+20h]
0x18003a840  call    __scrt_release_startup_lock
0x18003a845  nop
0x18003a846  add     rsp, 20h
0x18003a84a  pop     rbp
0x18003a84b  retn
0x18003a84d  push    rbp
0x18003a84f  sub     rsp, 20h
0x18003a853  mov     rbp, rdx
0x18003a856  add     rsp, 20h
0x18003a85a  pop     rbp
0x18003a85b  jmp     __scrt_dllmain_uninitialize_critical
```
