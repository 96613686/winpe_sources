# dllmain_crt_process_detach

- ea: `0x180001488`
- end: `0x18000150b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
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
- `0x180001be4`
- `0x180001c2c`
- `0x180001c7c`

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

  if ( dword_1800146B0 <= 0 )
    return 0;
  --dword_1800146B0;
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
0x180001488  mov     [rsp+arg_0], rbx
0x18000148d  push    rdi
0x18000148e  sub     rsp, 30h
0x180001492  mov     dil, cl
0x180001495  mov     eax, cs:dword_1800146B0
0x18000149b  test    eax, eax
0x18000149d  jg      short loc_1800014AC
0x18000149f  xor     eax, eax
0x1800014a1  mov     rbx, [rsp+38h+arg_0]
0x1800014a6  add     rsp, 30h
0x1800014aa  pop     rdi
0x1800014ab  retn
0x1800014ac  dec     eax
0x1800014ae  mov     cs:dword_1800146B0, eax
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
0x18000cbf9  push    rbp
0x18000cbfb  sub     rsp, 20h
0x18000cbff  mov     rbp, rdx
0x18000cc02  mov     cl, [rbp+20h]
0x18000cc05  call    __scrt_release_startup_lock
0x18000cc0a  nop
0x18000cc0b  add     rsp, 20h
0x18000cc0f  pop     rbp
0x18000cc10  retn
0x18000cc12  push    rbp
0x18000cc14  sub     rsp, 20h
0x18000cc18  mov     rbp, rdx
0x18000cc1b  add     rsp, 20h
0x18000cc1f  pop     rbp
0x18000cc20  jmp     __scrt_dllmain_uninitialize_critical
```
