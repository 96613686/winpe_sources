# dllmain_crt_process_detach

- ea: `0x180001358`
- end: `0x1800013db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001200`

## callees

- `0x180001358`
- `0x180001594`
- `0x1800016bc`
- `0x1800016f4`
- `0x180001884`
- `0x1800018b0`
- `0x180001ae0`
- `0x180001b28`
- `0x180001b78`

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

  if ( dword_180013570 <= 0 )
    return 0;
  --dword_180013570;
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
0x180001358  mov     [rsp+arg_0], rbx
0x18000135d  push    rdi
0x18000135e  sub     rsp, 30h
0x180001362  mov     dil, cl
0x180001365  mov     eax, cs:dword_180013570
0x18000136b  test    eax, eax
0x18000136d  jg      short loc_18000137C
0x18000136f  xor     eax, eax
0x180001371  mov     rbx, [rsp+38h+arg_0]
0x180001376  add     rsp, 30h
0x18000137a  pop     rdi
0x18000137b  retn
0x18000137c  dec     eax
0x18000137e  mov     cs:dword_180013570, eax
0x180001384  call    __scrt_acquire_startup_lock
0x180001389  mov     bl, al
0x18000138b  mov     [rsp+38h+var_18], al
0x18000138f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001396  jnz     short loc_1800013CE
0x180001398  call    __scrt_dllmain_uninitialize_c
0x18000139d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013a2  call    _RTC_Terminate
0x1800013a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800013b1  mov     cl, bl
0x1800013b3  call    __scrt_release_startup_lock
0x1800013b8  xor     edx, edx
0x1800013ba  mov     cl, dil
0x1800013bd  call    __scrt_uninitialize_crt
0x1800013c2  movzx   ebx, al
0x1800013c5  call    __scrt_dllmain_uninitialize_critical
0x1800013ca  mov     eax, ebx
0x1800013cc  jmp     short loc_180001371
0x1800013ce  mov     ecx, 7
0x1800013d3  call    __scrt_fastfail
0x18000b649  push    rbp
0x18000b64b  sub     rsp, 20h
0x18000b64f  mov     rbp, rdx
0x18000b652  mov     cl, [rbp+20h]
0x18000b655  call    __scrt_release_startup_lock
0x18000b65a  nop
0x18000b65b  add     rsp, 20h
0x18000b65f  pop     rbp
0x18000b660  retn
0x18000b662  push    rbp
0x18000b664  sub     rsp, 20h
0x18000b668  mov     rbp, rdx
0x18000b66b  add     rsp, 20h
0x18000b66f  pop     rbp
0x18000b670  jmp     __scrt_dllmain_uninitialize_critical
```
