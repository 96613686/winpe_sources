# dllmain_crt_process_detach

- ea: `0x1800016d8`
- end: `0x18000175b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x1800016d8`
- `0x180001940`
- `0x180001a68`
- `0x180001aa0`
- `0x180001c30`
- `0x180001c5c`
- `0x180001dec`
- `0x180001e34`
- `0x180001e84`

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

  if ( dword_1800352F8 <= 0 )
    return 0;
  --dword_1800352F8;
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
0x1800016d8  mov     [rsp+arg_0], rbx
0x1800016dd  push    rdi
0x1800016de  sub     rsp, 30h
0x1800016e2  mov     dil, cl
0x1800016e5  mov     eax, cs:dword_1800352F8
0x1800016eb  test    eax, eax
0x1800016ed  jg      short loc_1800016FC
0x1800016ef  xor     eax, eax
0x1800016f1  mov     rbx, [rsp+38h+arg_0]
0x1800016f6  add     rsp, 30h
0x1800016fa  pop     rdi
0x1800016fb  retn
0x1800016fc  dec     eax
0x1800016fe  mov     cs:dword_1800352F8, eax
0x180001704  call    __scrt_acquire_startup_lock
0x180001709  mov     bl, al
0x18000170b  mov     [rsp+38h+var_18], al
0x18000170f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001716  jnz     short loc_18000174E
0x180001718  call    __scrt_dllmain_uninitialize_c
0x18000171d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001722  call    _RTC_Terminate
0x180001727  mov     cs:__scrt_current_native_startup_state, 0
0x180001731  mov     cl, bl
0x180001733  call    __scrt_release_startup_lock
0x180001738  xor     edx, edx
0x18000173a  mov     cl, dil
0x18000173d  call    __scrt_uninitialize_crt
0x180001742  movzx   ebx, al
0x180001745  call    __scrt_dllmain_uninitialize_critical
0x18000174a  mov     eax, ebx
0x18000174c  jmp     short loc_1800016F1
0x18000174e  mov     ecx, 7
0x180001753  call    __scrt_fastfail
0x180022ee9  push    rbp
0x180022eeb  sub     rsp, 20h
0x180022eef  mov     rbp, rdx
0x180022ef2  mov     cl, [rbp+20h]
0x180022ef5  call    __scrt_release_startup_lock
0x180022efa  nop
0x180022efb  add     rsp, 20h
0x180022eff  pop     rbp
0x180022f00  retn
0x180022f02  push    rbp
0x180022f04  sub     rsp, 20h
0x180022f08  mov     rbp, rdx
0x180022f0b  add     rsp, 20h
0x180022f0f  pop     rbp
0x180022f10  jmp     __scrt_dllmain_uninitialize_critical
```
