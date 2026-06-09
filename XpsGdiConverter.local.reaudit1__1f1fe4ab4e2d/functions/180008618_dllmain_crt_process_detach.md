# dllmain_crt_process_detach

- ea: `0x180008618`
- end: `0x18000869b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800084c0`

## callees

- `0x180008618`
- `0x180008898`
- `0x1800089c0`
- `0x1800089f8`
- `0x180008b88`
- `0x180008bb4`
- `0x180009098`
- `0x1800090e0`
- `0x180009130`

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

  if ( dword_180057410 <= 0 )
    return 0;
  --dword_180057410;
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
0x180008618  mov     [rsp+arg_0], rbx
0x18000861d  push    rdi
0x18000861e  sub     rsp, 30h
0x180008622  mov     dil, cl
0x180008625  mov     eax, cs:dword_180057410
0x18000862b  test    eax, eax
0x18000862d  jg      short loc_18000863C
0x18000862f  xor     eax, eax
0x180008631  mov     rbx, [rsp+38h+arg_0]
0x180008636  add     rsp, 30h
0x18000863a  pop     rdi
0x18000863b  retn
0x18000863c  dec     eax
0x18000863e  mov     cs:dword_180057410, eax
0x180008644  call    __scrt_acquire_startup_lock
0x180008649  mov     bl, al
0x18000864b  mov     [rsp+38h+var_18], al
0x18000864f  cmp     cs:__scrt_current_native_startup_state, 2
0x180008656  jnz     short loc_18000868E
0x180008658  call    __scrt_dllmain_uninitialize_c
0x18000865d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180008662  call    _RTC_Terminate
0x180008667  mov     cs:__scrt_current_native_startup_state, 0
0x180008671  mov     cl, bl
0x180008673  call    __scrt_release_startup_lock
0x180008678  xor     edx, edx
0x18000867a  mov     cl, dil
0x18000867d  call    __scrt_uninitialize_crt
0x180008682  movzx   ebx, al
0x180008685  call    __scrt_dllmain_uninitialize_critical
0x18000868a  mov     eax, ebx
0x18000868c  jmp     short loc_180008631
0x18000868e  mov     ecx, 7
0x180008693  call    __scrt_fastfail
0x180047249  push    rbp
0x18004724b  sub     rsp, 20h
0x18004724f  mov     rbp, rdx
0x180047252  mov     cl, [rbp+20h]
0x180047255  call    __scrt_release_startup_lock
0x18004725a  nop
0x18004725b  add     rsp, 20h
0x18004725f  pop     rbp
0x180047260  retn
0x180047262  push    rbp
0x180047264  sub     rsp, 20h
0x180047268  mov     rbp, rdx
0x18004726b  add     rsp, 20h
0x18004726f  pop     rbp
0x180047270  jmp     __scrt_dllmain_uninitialize_critical
```
