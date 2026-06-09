# dllmain_crt_process_detach

- ea: `0x1800027f0`
- end: `0x180002873`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002680`

## callees

- `0x1800027f0`
- `0x180002a48`
- `0x180002b94`
- `0x180002bcc`
- `0x180002d5c`
- `0x180002d88`
- `0x180002f10`
- `0x180002f60`
- `0x180002fb0`

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

  if ( dword_180126240 <= 0 )
    return 0;
  --dword_180126240;
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
0x1800027f0  mov     [rsp+arg_0], rbx
0x1800027f5  push    rdi
0x1800027f6  sub     rsp, 30h
0x1800027fa  mov     dil, cl
0x1800027fd  mov     eax, cs:dword_180126240
0x180002803  test    eax, eax
0x180002805  jg      short loc_180002814
0x180002807  xor     eax, eax
0x180002809  mov     rbx, [rsp+38h+arg_0]
0x18000280e  add     rsp, 30h
0x180002812  pop     rdi
0x180002813  retn
0x180002814  dec     eax
0x180002816  mov     cs:dword_180126240, eax
0x18000281c  call    __scrt_acquire_startup_lock
0x180002821  mov     bl, al
0x180002823  mov     [rsp+38h+var_18], al
0x180002827  cmp     cs:__scrt_current_native_startup_state, 2
0x18000282e  jnz     short loc_180002866
0x180002830  call    __scrt_dllmain_uninitialize_c
0x180002835  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000283a  call    _RTC_Terminate
0x18000283f  mov     cs:__scrt_current_native_startup_state, 0
0x180002849  mov     cl, bl
0x18000284b  call    __scrt_release_startup_lock
0x180002850  xor     edx, edx
0x180002852  mov     cl, dil
0x180002855  call    __scrt_uninitialize_crt
0x18000285a  movzx   ebx, al
0x18000285d  call    __scrt_dllmain_uninitialize_critical
0x180002862  mov     eax, ebx
0x180002864  jmp     short loc_180002809
0x180002866  mov     ecx, 7
0x18000286b  call    __scrt_fastfail
0x1800b10af  push    rbp
0x1800b10b1  sub     rsp, 20h
0x1800b10b5  mov     rbp, rdx
0x1800b10b8  mov     cl, [rbp+20h]
0x1800b10bb  call    __scrt_release_startup_lock
0x1800b10c0  nop
0x1800b10c1  add     rsp, 20h
0x1800b10c5  pop     rbp
0x1800b10c6  retn
0x1800b10c8  push    rbp
0x1800b10ca  sub     rsp, 20h
0x1800b10ce  mov     rbp, rdx
0x1800b10d1  add     rsp, 20h
0x1800b10d5  pop     rbp
0x1800b10d6  jmp     __scrt_dllmain_uninitialize_critical
```
