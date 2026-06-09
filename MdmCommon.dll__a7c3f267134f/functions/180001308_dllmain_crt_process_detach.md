# dllmain_crt_process_detach

- ea: `0x180001308`
- end: `0x18000138b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x180001308`
- `0x1800016dc`
- `0x180001714`
- `0x18000183c`
- `0x180001874`
- `0x180001a04`
- `0x180001a30`
- `0x180001ad0`
- `0x180001b20`

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

  if ( dword_180030250 <= 0 )
    return 0;
  --dword_180030250;
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
0x180001308  mov     [rsp+arg_0], rbx
0x18000130d  push    rdi
0x18000130e  sub     rsp, 30h
0x180001312  mov     dil, cl
0x180001315  mov     eax, cs:dword_180030250
0x18000131b  test    eax, eax
0x18000131d  jg      short loc_18000132C
0x18000131f  xor     eax, eax
0x180001321  mov     rbx, [rsp+38h+arg_0]
0x180001326  add     rsp, 30h
0x18000132a  pop     rdi
0x18000132b  retn
0x18000132c  dec     eax
0x18000132e  mov     cs:dword_180030250, eax
0x180001334  call    __scrt_acquire_startup_lock
0x180001339  mov     bl, al
0x18000133b  mov     [rsp+38h+var_18], al
0x18000133f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001346  jnz     short loc_18000137E
0x180001348  call    __scrt_dllmain_uninitialize_c
0x18000134d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001352  call    _RTC_Terminate
0x180001357  mov     cs:__scrt_current_native_startup_state, 0
0x180001361  mov     cl, bl
0x180001363  call    __scrt_release_startup_lock
0x180001368  xor     edx, edx
0x18000136a  mov     cl, dil
0x18000136d  call    __scrt_uninitialize_crt
0x180001372  movzx   ebx, al
0x180001375  call    __scrt_dllmain_uninitialize_critical
0x18000137a  mov     eax, ebx
0x18000137c  jmp     short loc_180001321
0x18000137e  mov     ecx, 7
0x180001383  call    __scrt_fastfail
0x18001dc99  push    rbp
0x18001dc9b  sub     rsp, 20h
0x18001dc9f  mov     rbp, rdx
0x18001dca2  mov     cl, [rbp+20h]
0x18001dca5  call    __scrt_release_startup_lock
0x18001dcaa  nop
0x18001dcab  add     rsp, 20h
0x18001dcaf  pop     rbp
0x18001dcb0  retn
0x18001dcb2  push    rbp
0x18001dcb4  sub     rsp, 20h
0x18001dcb8  mov     rbp, rdx
0x18001dcbb  add     rsp, 20h
0x18001dcbf  pop     rbp
0x18001dcc0  jmp     __scrt_dllmain_uninitialize_critical
```
