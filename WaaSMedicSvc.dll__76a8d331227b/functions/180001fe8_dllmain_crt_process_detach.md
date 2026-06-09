# dllmain_crt_process_detach

- ea: `0x180001fe8`
- end: `0x18000206b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001e90`

## callees

- `0x180001fe8`
- `0x180002224`
- `0x18000234c`
- `0x180002384`
- `0x180002514`
- `0x180002540`
- `0x180002a7c`
- `0x180002ac4`
- `0x180002b14`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800133B0 <= 0 )
    return 0;
  --dword_1800133B0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180001fe8  mov     [rsp+arg_0], rbx
0x180001fed  push    rdi
0x180001fee  sub     rsp, 30h
0x180001ff2  mov     dil, cl
0x180001ff5  mov     eax, cs:dword_1800133B0
0x180001ffb  test    eax, eax
0x180001ffd  jg      short loc_18000200C
0x180001fff  xor     eax, eax
0x180002001  mov     rbx, [rsp+38h+arg_0]
0x180002006  add     rsp, 30h
0x18000200a  pop     rdi
0x18000200b  retn
0x18000200c  dec     eax
0x18000200e  mov     cs:dword_1800133B0, eax
0x180002014  call    __scrt_acquire_startup_lock
0x180002019  mov     bl, al
0x18000201b  mov     [rsp+38h+var_18], al
0x18000201f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002026  jnz     short loc_18000205E
0x180002028  call    __scrt_dllmain_uninitialize_c
0x18000202d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002032  call    _RTC_Terminate
0x180002037  mov     cs:__scrt_current_native_startup_state, 0
0x180002041  mov     cl, bl
0x180002043  call    __scrt_release_startup_lock
0x180002048  xor     edx, edx
0x18000204a  mov     cl, dil
0x18000204d  call    __scrt_uninitialize_crt
0x180002052  movzx   ebx, al
0x180002055  call    __scrt_dllmain_uninitialize_critical
0x18000205a  mov     eax, ebx
0x18000205c  jmp     short loc_180002001
0x18000205e  mov     ecx, 7
0x180002063  call    __scrt_fastfail
0x18000be39  push    rbp
0x18000be3b  sub     rsp, 20h
0x18000be3f  mov     rbp, rdx
0x18000be42  mov     cl, [rbp+20h]
0x18000be45  call    __scrt_release_startup_lock
0x18000be4a  nop
0x18000be4b  add     rsp, 20h
0x18000be4f  pop     rbp
0x18000be50  retn
0x18000be52  push    rbp
0x18000be54  sub     rsp, 20h
0x18000be58  mov     rbp, rdx
0x18000be5b  add     rsp, 20h
0x18000be5f  pop     rbp
0x18000be60  jmp     __scrt_dllmain_uninitialize_critical
```
