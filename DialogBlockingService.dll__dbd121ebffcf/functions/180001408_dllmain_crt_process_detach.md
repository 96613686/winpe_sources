# dllmain_crt_process_detach

- ea: `0x180001408`
- end: `0x18000148b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180001408`
- `0x180001694`
- `0x1800017bc`
- `0x1800017f4`
- `0x180001984`
- `0x1800019b0`
- `0x180001b98`
- `0x180001be0`
- `0x180001c30`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180014270 <= 0 )
    return 0;
  --dword_180014270;
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
0x180001408  mov     [rsp+arg_0], rbx
0x18000140d  push    rdi
0x18000140e  sub     rsp, 30h
0x180001412  mov     dil, cl
0x180001415  mov     eax, cs:dword_180014270
0x18000141b  test    eax, eax
0x18000141d  jg      short loc_18000142C
0x18000141f  xor     eax, eax
0x180001421  mov     rbx, [rsp+38h+arg_0]
0x180001426  add     rsp, 30h
0x18000142a  pop     rdi
0x18000142b  retn
0x18000142c  dec     eax
0x18000142e  mov     cs:dword_180014270, eax
0x180001434  call    __scrt_acquire_startup_lock
0x180001439  mov     bl, al
0x18000143b  mov     [rsp+38h+var_18], al
0x18000143f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001446  jnz     short loc_18000147E
0x180001448  call    __scrt_dllmain_uninitialize_c
0x18000144d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001452  call    _RTC_Terminate
0x180001457  mov     cs:__scrt_current_native_startup_state, 0
0x180001461  mov     cl, bl
0x180001463  call    __scrt_release_startup_lock
0x180001468  xor     edx, edx
0x18000146a  mov     cl, dil
0x18000146d  call    __scrt_uninitialize_crt
0x180001472  movzx   ebx, al
0x180001475  call    __scrt_dllmain_uninitialize_critical
0x18000147a  mov     eax, ebx
0x18000147c  jmp     short loc_180001421
0x18000147e  mov     ecx, 7
0x180001483  call    __scrt_fastfail
0x18000c889  push    rbp
0x18000c88b  sub     rsp, 20h
0x18000c88f  mov     rbp, rdx
0x18000c892  mov     cl, [rbp+20h]
0x18000c895  call    __scrt_release_startup_lock
0x18000c89a  nop
0x18000c89b  add     rsp, 20h
0x18000c89f  pop     rbp
0x18000c8a0  retn
0x18000c8a2  push    rbp
0x18000c8a4  sub     rsp, 20h
0x18000c8a8  mov     rbp, rdx
0x18000c8ab  add     rsp, 20h
0x18000c8af  pop     rbp
0x18000c8b0  jmp     __scrt_dllmain_uninitialize_critical
```
