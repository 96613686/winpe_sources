# dllmain_crt_process_detach

- ea: `0x180001338`
- end: `0x1800013bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x180001338`
- `0x180001584`
- `0x1800016ac`
- `0x1800016e4`
- `0x180001874`
- `0x1800018a0`
- `0x180001a3c`
- `0x180001a84`
- `0x180001ad4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000E290 <= 0 )
    return 0;
  --dword_18000E290;
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
0x180001338  mov     [rsp+arg_0], rbx
0x18000133d  push    rdi
0x18000133e  sub     rsp, 30h
0x180001342  mov     dil, cl
0x180001345  mov     eax, cs:dword_18000E290
0x18000134b  test    eax, eax
0x18000134d  jg      short loc_18000135C
0x18000134f  xor     eax, eax
0x180001351  mov     rbx, [rsp+38h+arg_0]
0x180001356  add     rsp, 30h
0x18000135a  pop     rdi
0x18000135b  retn
0x18000135c  dec     eax
0x18000135e  mov     cs:dword_18000E290, eax
0x180001364  call    __scrt_acquire_startup_lock
0x180001369  mov     bl, al
0x18000136b  mov     [rsp+38h+var_18], al
0x18000136f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001376  jnz     short loc_1800013AE
0x180001378  call    __scrt_dllmain_uninitialize_c
0x18000137d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001382  call    _RTC_Terminate
0x180001387  mov     cs:__scrt_current_native_startup_state, 0
0x180001391  mov     cl, bl
0x180001393  call    __scrt_release_startup_lock
0x180001398  xor     edx, edx
0x18000139a  mov     cl, dil
0x18000139d  call    __scrt_uninitialize_crt
0x1800013a2  movzx   ebx, al
0x1800013a5  call    __scrt_dllmain_uninitialize_critical
0x1800013aa  mov     eax, ebx
0x1800013ac  jmp     short loc_180001351
0x1800013ae  mov     ecx, 7
0x1800013b3  call    __scrt_fastfail
0x180008009  push    rbp
0x18000800b  sub     rsp, 20h
0x18000800f  mov     rbp, rdx
0x180008012  mov     cl, [rbp+20h]
0x180008015  call    __scrt_release_startup_lock
0x18000801a  nop
0x18000801b  add     rsp, 20h
0x18000801f  pop     rbp
0x180008020  retn
0x180008022  push    rbp
0x180008024  sub     rsp, 20h
0x180008028  mov     rbp, rdx
0x18000802b  add     rsp, 20h
0x18000802f  pop     rbp
0x180008030  jmp     __scrt_dllmain_uninitialize_critical
```
