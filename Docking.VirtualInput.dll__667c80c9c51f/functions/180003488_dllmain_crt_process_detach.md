# dllmain_crt_process_detach

- ea: `0x180003488`
- end: `0x18000350b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003330`

## callees

- `0x180003488`
- `0x1800036c4`
- `0x1800037ec`
- `0x180003824`
- `0x1800039b4`
- `0x1800039e0`
- `0x180003b7c`
- `0x180003bc4`
- `0x180003c14`

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

  if ( dword_1800253F0 <= 0 )
    return 0;
  --dword_1800253F0;
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
0x180003488  mov     [rsp+arg_0], rbx
0x18000348d  push    rdi
0x18000348e  sub     rsp, 30h
0x180003492  mov     dil, cl
0x180003495  mov     eax, cs:dword_1800253F0
0x18000349b  test    eax, eax
0x18000349d  jg      short loc_1800034AC
0x18000349f  xor     eax, eax
0x1800034a1  mov     rbx, [rsp+38h+arg_0]
0x1800034a6  add     rsp, 30h
0x1800034aa  pop     rdi
0x1800034ab  retn
0x1800034ac  dec     eax
0x1800034ae  mov     cs:dword_1800253F0, eax
0x1800034b4  call    __scrt_acquire_startup_lock
0x1800034b9  mov     bl, al
0x1800034bb  mov     [rsp+38h+var_18], al
0x1800034bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800034c6  jnz     short loc_1800034FE
0x1800034c8  call    __scrt_dllmain_uninitialize_c
0x1800034cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800034d2  call    _RTC_Terminate
0x1800034d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800034e1  mov     cl, bl
0x1800034e3  call    __scrt_release_startup_lock
0x1800034e8  xor     edx, edx
0x1800034ea  mov     cl, dil
0x1800034ed  call    __scrt_uninitialize_crt
0x1800034f2  movzx   ebx, al
0x1800034f5  call    __scrt_dllmain_uninitialize_critical
0x1800034fa  mov     eax, ebx
0x1800034fc  jmp     short loc_1800034A1
0x1800034fe  mov     ecx, 7
0x180003503  call    __scrt_fastfail
0x18001b4ed  push    rbp
0x18001b4ef  sub     rsp, 20h
0x18001b4f3  mov     rbp, rdx
0x18001b4f6  mov     cl, [rbp+20h]
0x18001b4f9  call    __scrt_release_startup_lock
0x18001b4fe  nop
0x18001b4ff  add     rsp, 20h
0x18001b503  pop     rbp
0x18001b504  retn
0x18001b506  push    rbp
0x18001b508  sub     rsp, 20h
0x18001b50c  mov     rbp, rdx
0x18001b50f  add     rsp, 20h
0x18001b513  pop     rbp
0x18001b514  jmp     __scrt_dllmain_uninitialize_critical
```
