# dllmain_crt_process_detach

- ea: `0x180001ea8`
- end: `0x180001f2b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001d50`

## callees

- `0x180001ea8`
- `0x1800020e4`
- `0x18000220c`
- `0x180002244`
- `0x1800023d4`
- `0x180002400`
- `0x1800025e0`
- `0x180002628`
- `0x180002678`

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

  if ( dword_1800242B0 <= 0 )
    return 0;
  --dword_1800242B0;
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
0x180001ea8  mov     [rsp+arg_0], rbx
0x180001ead  push    rdi
0x180001eae  sub     rsp, 30h
0x180001eb2  mov     dil, cl
0x180001eb5  mov     eax, cs:dword_1800242B0
0x180001ebb  test    eax, eax
0x180001ebd  jg      short loc_180001ECC
0x180001ebf  xor     eax, eax
0x180001ec1  mov     rbx, [rsp+38h+arg_0]
0x180001ec6  add     rsp, 30h
0x180001eca  pop     rdi
0x180001ecb  retn
0x180001ecc  dec     eax
0x180001ece  mov     cs:dword_1800242B0, eax
0x180001ed4  call    __scrt_acquire_startup_lock
0x180001ed9  mov     bl, al
0x180001edb  mov     [rsp+38h+var_18], al
0x180001edf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001ee6  jnz     short loc_180001F1E
0x180001ee8  call    __scrt_dllmain_uninitialize_c
0x180001eed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001ef2  call    _RTC_Terminate
0x180001ef7  mov     cs:__scrt_current_native_startup_state, 0
0x180001f01  mov     cl, bl
0x180001f03  call    __scrt_release_startup_lock
0x180001f08  xor     edx, edx
0x180001f0a  mov     cl, dil
0x180001f0d  call    __scrt_uninitialize_crt
0x180001f12  movzx   ebx, al
0x180001f15  call    __scrt_dllmain_uninitialize_critical
0x180001f1a  mov     eax, ebx
0x180001f1c  jmp     short loc_180001EC1
0x180001f1e  mov     ecx, 7
0x180001f23  call    __scrt_fastfail
0x180016599  push    rbp
0x18001659b  sub     rsp, 20h
0x18001659f  mov     rbp, rdx
0x1800165a2  mov     cl, [rbp+20h]
0x1800165a5  call    __scrt_release_startup_lock
0x1800165aa  nop
0x1800165ab  add     rsp, 20h
0x1800165af  pop     rbp
0x1800165b0  retn
0x1800165b2  push    rbp
0x1800165b4  sub     rsp, 20h
0x1800165b8  mov     rbp, rdx
0x1800165bb  add     rsp, 20h
0x1800165bf  pop     rbp
0x1800165c0  jmp     __scrt_dllmain_uninitialize_critical
```
