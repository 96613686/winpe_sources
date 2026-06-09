# dllmain_crt_process_detach

- ea: `0x180001338`
- end: `0x1800013bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x180001338`
- `0x1800015a0`
- `0x1800016c8`
- `0x180001700`
- `0x180001890`
- `0x1800018bc`
- `0x180001a4c`
- `0x180001a94`
- `0x180001ae4`

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

  if ( dword_18000F2B0 <= 0 )
    return 0;
  --dword_18000F2B0;
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
0x180001338  mov     [rsp+arg_0], rbx
0x18000133d  push    rdi
0x18000133e  sub     rsp, 30h
0x180001342  mov     dil, cl
0x180001345  mov     eax, cs:dword_18000F2B0
0x18000134b  test    eax, eax
0x18000134d  jg      short loc_18000135C
0x18000134f  xor     eax, eax
0x180001351  mov     rbx, [rsp+38h+arg_0]
0x180001356  add     rsp, 30h
0x18000135a  pop     rdi
0x18000135b  retn
0x18000135c  dec     eax
0x18000135e  mov     cs:dword_18000F2B0, eax
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
0x18000a019  push    rbp
0x18000a01b  sub     rsp, 20h
0x18000a01f  mov     rbp, rdx
0x18000a022  mov     cl, [rbp+20h]
0x18000a025  call    __scrt_release_startup_lock
0x18000a02a  nop
0x18000a02b  add     rsp, 20h
0x18000a02f  pop     rbp
0x18000a030  retn
0x18000a032  push    rbp
0x18000a034  sub     rsp, 20h
0x18000a038  mov     rbp, rdx
0x18000a03b  add     rsp, 20h
0x18000a03f  pop     rbp
0x18000a040  jmp     __scrt_dllmain_uninitialize_critical
```
