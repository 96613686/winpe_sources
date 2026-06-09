# dllmain_crt_process_detach

- ea: `0x180002438`
- end: `0x1800024bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800022e0`

## callees

- `0x180002438`
- `0x180002744`
- `0x18000286c`
- `0x1800028a4`
- `0x180002a34`
- `0x180002a60`
- `0x180003000`
- `0x180003048`
- `0x180003098`

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

  if ( dword_180014290 <= 0 )
    return 0;
  --dword_180014290;
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
0x180002438  mov     [rsp+arg_0], rbx
0x18000243d  push    rdi
0x18000243e  sub     rsp, 30h
0x180002442  mov     dil, cl
0x180002445  mov     eax, cs:dword_180014290
0x18000244b  test    eax, eax
0x18000244d  jg      short loc_18000245C
0x18000244f  xor     eax, eax
0x180002451  mov     rbx, [rsp+38h+arg_0]
0x180002456  add     rsp, 30h
0x18000245a  pop     rdi
0x18000245b  retn
0x18000245c  dec     eax
0x18000245e  mov     cs:dword_180014290, eax
0x180002464  call    __scrt_acquire_startup_lock
0x180002469  mov     bl, al
0x18000246b  mov     [rsp+38h+var_18], al
0x18000246f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002476  jnz     short loc_1800024AE
0x180002478  call    __scrt_dllmain_uninitialize_c
0x18000247d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002482  call    _RTC_Terminate
0x180002487  mov     cs:__scrt_current_native_startup_state, 0
0x180002491  mov     cl, bl
0x180002493  call    __scrt_release_startup_lock
0x180002498  xor     edx, edx
0x18000249a  mov     cl, dil
0x18000249d  call    __scrt_uninitialize_crt
0x1800024a2  movzx   ebx, al
0x1800024a5  call    __scrt_dllmain_uninitialize_critical
0x1800024aa  mov     eax, ebx
0x1800024ac  jmp     short loc_180002451
0x1800024ae  mov     ecx, 7
0x1800024b3  call    __scrt_fastfail
0x18000bf99  push    rbp
0x18000bf9b  sub     rsp, 20h
0x18000bf9f  mov     rbp, rdx
0x18000bfa2  mov     cl, [rbp+20h]
0x18000bfa5  call    __scrt_release_startup_lock
0x18000bfaa  nop
0x18000bfab  add     rsp, 20h
0x18000bfaf  pop     rbp
0x18000bfb0  retn
0x18000bfb2  push    rbp
0x18000bfb4  sub     rsp, 20h
0x18000bfb8  mov     rbp, rdx
0x18000bfbb  add     rsp, 20h
0x18000bfbf  pop     rbp
0x18000bfc0  jmp     __scrt_dllmain_uninitialize_critical
```
