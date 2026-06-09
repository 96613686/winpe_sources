# dllmain_crt_process_detach

- ea: `0x180002328`
- end: `0x1800023ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800021d0`

## callees

- `0x180002328`
- `0x180002574`
- `0x18000269c`
- `0x1800026d4`
- `0x180002864`
- `0x180002890`
- `0x180002a90`
- `0x180002ad8`
- `0x180002b28`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C530 <= 0 )
    return 0;
  --dword_18001C530;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
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
0x180002328  mov     [rsp+arg_0], rbx
0x18000232d  push    rdi
0x18000232e  sub     rsp, 30h
0x180002332  mov     dil, cl
0x180002335  mov     eax, cs:dword_18001C530
0x18000233b  test    eax, eax
0x18000233d  jg      short loc_18000234C
0x18000233f  xor     eax, eax
0x180002341  mov     rbx, [rsp+38h+arg_0]
0x180002346  add     rsp, 30h
0x18000234a  pop     rdi
0x18000234b  retn
0x18000234c  dec     eax
0x18000234e  mov     cs:dword_18001C530, eax
0x180002354  call    __scrt_acquire_startup_lock
0x180002359  mov     bl, al
0x18000235b  mov     [rsp+38h+var_18], al
0x18000235f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002366  jnz     short loc_18000239E
0x180002368  call    __scrt_dllmain_uninitialize_c
0x18000236d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002372  call    _RTC_Terminate
0x180002377  mov     cs:__scrt_current_native_startup_state, 0
0x180002381  mov     cl, bl
0x180002383  call    __scrt_release_startup_lock
0x180002388  xor     edx, edx
0x18000238a  mov     cl, dil
0x18000238d  call    __scrt_uninitialize_crt
0x180002392  movzx   ebx, al
0x180002395  call    __scrt_dllmain_uninitialize_critical
0x18000239a  mov     eax, ebx
0x18000239c  jmp     short loc_180002341
0x18000239e  mov     ecx, 7
0x1800023a3  call    __scrt_fastfail
0x180011139  push    rbp
0x18001113b  sub     rsp, 20h
0x18001113f  mov     rbp, rdx
0x180011142  mov     cl, [rbp+20h]
0x180011145  call    __scrt_release_startup_lock
0x18001114a  nop
0x18001114b  add     rsp, 20h
0x18001114f  pop     rbp
0x180011150  retn
0x180011152  push    rbp
0x180011154  sub     rsp, 20h
0x180011158  mov     rbp, rdx
0x18001115b  add     rsp, 20h
0x18001115f  pop     rbp
0x180011160  jmp     __scrt_dllmain_uninitialize_critical
```
