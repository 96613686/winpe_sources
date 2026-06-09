# dllmain_crt_process_detach

- ea: `0x180001488`
- end: `0x18000150b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x180001488`
- `0x1800016c4`
- `0x1800017ec`
- `0x180001824`
- `0x1800019b4`
- `0x1800019e0`
- `0x180001b7c`
- `0x180001bc4`
- `0x180001c14`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180015230 <= 0 )
    return 0;
  --dword_180015230;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180001488  mov     [rsp+arg_0], rbx
0x18000148d  push    rdi
0x18000148e  sub     rsp, 30h
0x180001492  mov     dil, cl
0x180001495  mov     eax, cs:dword_180015230
0x18000149b  test    eax, eax
0x18000149d  jg      short loc_1800014AC
0x18000149f  xor     eax, eax
0x1800014a1  mov     rbx, [rsp+38h+arg_0]
0x1800014a6  add     rsp, 30h
0x1800014aa  pop     rdi
0x1800014ab  retn
0x1800014ac  dec     eax
0x1800014ae  mov     cs:dword_180015230, eax
0x1800014b4  call    __scrt_acquire_startup_lock
0x1800014b9  mov     bl, al
0x1800014bb  mov     [rsp+38h+var_18], al
0x1800014bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800014c6  jnz     short loc_1800014FE
0x1800014c8  call    __scrt_dllmain_uninitialize_c
0x1800014cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800014d2  call    _RTC_Terminate
0x1800014d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800014e1  mov     cl, bl
0x1800014e3  call    __scrt_release_startup_lock
0x1800014e8  xor     edx, edx
0x1800014ea  mov     cl, dil
0x1800014ed  call    __scrt_uninitialize_crt
0x1800014f2  movzx   ebx, al
0x1800014f5  call    __scrt_dllmain_uninitialize_critical
0x1800014fa  mov     eax, ebx
0x1800014fc  jmp     short loc_1800014A1
0x1800014fe  mov     ecx, 7
0x180001503  call    __scrt_fastfail
0x18000a019  push    rbp
0x18000a01b  sub     rsp, 20h
0x18000a01f  mov     rbp, rdx
0x18000a022  mov     cl, [rbp+20h]
0x18000a025  call    __scrt_release_startup_lock
0x18000a02a  nop
0x18000a02b  add     rsp, 20h
0x18000a02f  pop     rbp
0x18000a030  retn
0x18000a032  push    rbp
0x18000a034  sub     rsp, 20h
0x18000a038  mov     rbp, rdx
0x18000a03b  add     rsp, 20h
0x18000a03f  pop     rbp
0x18000a040  jmp     __scrt_dllmain_uninitialize_critical
```
