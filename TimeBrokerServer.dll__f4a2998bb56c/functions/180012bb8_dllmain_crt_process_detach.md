# dllmain_crt_process_detach

- ea: `0x180012bb8`
- end: `0x180012c3b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180012a60`

## callees

- `0x180012bb8`
- `0x180012e38`
- `0x180012f60`
- `0x180012f98`
- `0x180013128`
- `0x180013154`
- `0x18001343c`
- `0x180013484`
- `0x1800134d4`

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

  if ( dword_180026550 <= 0 )
    return 0;
  --dword_180026550;
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
0x180012bb8  mov     [rsp+arg_0], rbx
0x180012bbd  push    rdi
0x180012bbe  sub     rsp, 30h
0x180012bc2  mov     dil, cl
0x180012bc5  mov     eax, cs:dword_180026550
0x180012bcb  test    eax, eax
0x180012bcd  jg      short loc_180012BDC
0x180012bcf  xor     eax, eax
0x180012bd1  mov     rbx, [rsp+38h+arg_0]
0x180012bd6  add     rsp, 30h
0x180012bda  pop     rdi
0x180012bdb  retn
0x180012bdc  dec     eax
0x180012bde  mov     cs:dword_180026550, eax
0x180012be4  call    __scrt_acquire_startup_lock
0x180012be9  mov     bl, al
0x180012beb  mov     [rsp+38h+var_18], al
0x180012bef  cmp     cs:__scrt_current_native_startup_state, 2
0x180012bf6  jnz     short loc_180012C2E
0x180012bf8  call    __scrt_dllmain_uninitialize_c
0x180012bfd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180012c02  call    _RTC_Terminate
0x180012c07  mov     cs:__scrt_current_native_startup_state, 0
0x180012c11  mov     cl, bl
0x180012c13  call    __scrt_release_startup_lock
0x180012c18  xor     edx, edx
0x180012c1a  mov     cl, dil
0x180012c1d  call    __scrt_uninitialize_crt
0x180012c22  movzx   ebx, al
0x180012c25  call    __scrt_dllmain_uninitialize_critical
0x180012c2a  mov     eax, ebx
0x180012c2c  jmp     short loc_180012BD1
0x180012c2e  mov     ecx, 7
0x180012c33  call    __scrt_fastfail
0x18001b0ea  push    rbp
0x18001b0ec  sub     rsp, 20h
0x18001b0f0  mov     rbp, rdx
0x18001b0f3  mov     cl, [rbp+20h]
0x18001b0f6  call    __scrt_release_startup_lock
0x18001b0fb  nop
0x18001b0fc  add     rsp, 20h
0x18001b100  pop     rbp
0x18001b101  retn
0x18001b103  push    rbp
0x18001b105  sub     rsp, 20h
0x18001b109  mov     rbp, rdx
0x18001b10c  add     rsp, 20h
0x18001b110  pop     rbp
0x18001b111  jmp     __scrt_dllmain_uninitialize_critical
```
