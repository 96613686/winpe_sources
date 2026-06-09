# dllmain_crt_process_detach

- ea: `0x180001408`
- end: `0x18000148b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180001408`
- `0x180001644`
- `0x18000176c`
- `0x1800017a4`
- `0x180001934`
- `0x180001960`
- `0x180001afc`
- `0x180001b44`
- `0x180001b94`

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

  if ( dword_180016270 <= 0 )
    return 0;
  --dword_180016270;
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
0x180001408  mov     [rsp+arg_0], rbx
0x18000140d  push    rdi
0x18000140e  sub     rsp, 30h
0x180001412  mov     dil, cl
0x180001415  mov     eax, cs:dword_180016270
0x18000141b  test    eax, eax
0x18000141d  jg      short loc_18000142C
0x18000141f  xor     eax, eax
0x180001421  mov     rbx, [rsp+38h+arg_0]
0x180001426  add     rsp, 30h
0x18000142a  pop     rdi
0x18000142b  retn
0x18000142c  dec     eax
0x18000142e  mov     cs:dword_180016270, eax
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
0x18000ef69  push    rbp
0x18000ef6b  sub     rsp, 20h
0x18000ef6f  mov     rbp, rdx
0x18000ef72  mov     cl, [rbp+20h]
0x18000ef75  call    __scrt_release_startup_lock
0x18000ef7a  nop
0x18000ef7b  add     rsp, 20h
0x18000ef7f  pop     rbp
0x18000ef80  retn
0x18000ef82  push    rbp
0x18000ef84  sub     rsp, 20h
0x18000ef88  mov     rbp, rdx
0x18000ef8b  add     rsp, 20h
0x18000ef8f  pop     rbp
0x18000ef90  jmp     __scrt_dllmain_uninitialize_critical
```
