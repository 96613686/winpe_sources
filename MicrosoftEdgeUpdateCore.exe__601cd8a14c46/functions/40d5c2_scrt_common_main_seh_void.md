# __scrt_common_main_seh(void)

- ea: `0x40d5c2`
- end: `0x40d73d`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `379`
- prototype: `char *__usercall@<eax>(char *@<esi>)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40d740`

## callees

- `0x4019cc`
- `0x402330`
- `0x40d2d0`
- `0x40d302`
- `0x40d3c2`
- `0x40d456`
- `0x40d473`
- `0x40d5c2`
- `0x40d86c`
- `0x40d987`
- `0x40d9c3`
- `0x40dc70`
- `0x40ddae`
- `0x40ddb4`
- `0x4104c3`
- `0x4108bf`
- `0x4108ce`
- `0x4108dd`
- `0x4108f3`
- `0x410919`
- `0x4113b7`
- `0x411401`
- `0x411446`

## pseudocode

```c
char *__usercall __scrt_common_main_seh@<eax>(char *a1@<esi>)
{
  char v1; // bl
  _DWORD *v3; // eax
  _DWORD *v4; // esi
  _tls_callback_type *v5; // eax
  _tls_callback_type *v6; // esi
  int show_window_mode; // esi
  CHAR *v8; // eax
  char v9; // [esp+10h] [ebp-24h]
  int Code; // [esp+14h] [ebp-20h]

  if ( !(unsigned __int8)__scrt_initialize_crt(1) || (v1 = 0, v9 = __scrt_acquire_startup_lock(), dword_43DCC4 == 1) )
  {
    __scrt_fastfail(7);
    goto LABEL_19;
  }
  if ( dword_43DCC4 )
  {
    v1 = 1;
  }
  else
  {
    dword_43DCC4 = 1;
    if ( _initterm_e((_PIFV *)&dword_422344, (_PIFV *)&dword_422368) )
      return (char *)255;
    _initterm((_PVFV *)&First, (_PVFV *)&Last);
    dword_43DCC4 = 2;
  }
  __scrt_release_startup_lock(v9);
  v3 = (_DWORD *)sub_40DDAE();
  v4 = v3;
  if ( *v3 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v3) )
    ((void (__thiscall *)(_DWORD, _DWORD, int, _DWORD))*v4)(*v4, 0, 2, 0);
  v5 = (_tls_callback_type *)sub_40DDB4();
  v6 = v5;
  if ( *v5 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v5) )
    _register_thread_local_exe_atexit_callback(*v6);
  show_window_mode = (unsigned __int16)__scrt_get_show_window_mode();
  v8 = (CHAR *)unknown_libname_11();
  a1 = (char *)WinMain(&_ImageBase, 0, v8, show_window_mode);
  if ( !(unsigned __int8)__scrt_is_managed_app() )
  {
LABEL_19:
    _loaddll(a1);
    _exit(Code);
  }
  if ( !v1 )
    _cexit();
  __scrt_uninitialize_crt(1, 0);
  return a1;
}

```

## disassembly

```asm
0x40d5c2  push    14h
0x40d5c4  push    offset stru_43B410
0x40d5c9  call    __SEH_prolog4
0x40d5ce  push    1
0x40d5d0  call    ___scrt_initialize_crt
0x40d5d5  pop     ecx
0x40d5d6  test    al, al
0x40d5d8  jz      loc_40D728
0x40d5de  xor     bl, bl
0x40d5e0  mov     [ebp+var_19], bl
0x40d5e3  and     [ebp+ms_exc.registration.TryLevel], 0
0x40d5e7  call    ___scrt_acquire_startup_lock
0x40d5ec  mov     byte ptr [ebp+var_24], al
0x40d5ef  mov     eax, dword_43DCC4
0x40d5f4  xor     ecx, ecx
0x40d5f6  inc     ecx
0x40d5f7  cmp     eax, ecx
0x40d5f9  jz      loc_40D728
0x40d5ff  test    eax, eax
0x40d601  jnz     short loc_40D64C
0x40d603  mov     dword_43DCC4, ecx
0x40d609  push    offset dword_422368; Last
0x40d60e  push    offset dword_422344; First
0x40d613  call    __initterm_e
0x40d618  pop     ecx
0x40d619  pop     ecx
0x40d61a  test    eax, eax
0x40d61c  jz      short loc_40D62F
0x40d61e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40d625  mov     eax, 0FFh
0x40d62a  jmp     loc_40D718
0x40d62f  push    offset Last; Last
0x40d634  push    offset First; First
0x40d639  call    __initterm
0x40d63e  pop     ecx
0x40d63f  pop     ecx
0x40d640  mov     dword_43DCC4, 2
0x40d64a  jmp     short loc_40D651
0x40d64c  mov     bl, cl
0x40d64e  mov     [ebp+var_19], bl
0x40d651  push    [ebp+var_24]
0x40d654  call    ___scrt_release_startup_lock
0x40d659  pop     ecx
0x40d65a  call    sub_40DDAE
0x40d65f  mov     esi, eax
0x40d661  xor     edi, edi
0x40d663  cmp     [esi], edi
0x40d665  jz      short loc_40D682
0x40d667  push    esi
0x40d668  call    ___scrt_is_nonwritable_in_current_image
0x40d66d  pop     ecx
0x40d66e  test    al, al
0x40d670  jz      short loc_40D682
0x40d672  mov     esi, [esi]
0x40d674  push    edi
0x40d675  push    2
0x40d677  push    edi
0x40d678  mov     ecx, esi
0x40d67a  call    ds:___guard_check_icall_fptr
0x40d680  call    esi
0x40d682  call    sub_40DDB4
0x40d687  mov     esi, eax
0x40d689  cmp     [esi], edi
0x40d68b  jz      short loc_40D6A0
0x40d68d  push    esi
0x40d68e  call    ___scrt_is_nonwritable_in_current_image
0x40d693  pop     ecx
0x40d694  test    al, al
0x40d696  jz      short loc_40D6A0
0x40d698  push    dword ptr [esi]; Callback
0x40d69a  call    __register_thread_local_exe_atexit_callback
0x40d69f  pop     ecx
0x40d6a0  call    ___scrt_get_show_window_mode
0x40d6a5  movzx   esi, ax
0x40d6a8  call    unknown_libname_11; Microsoft VisualC universal runtime
0x40d6ad  push    esi; nShowCmd
0x40d6ae  push    eax; lpCmdLine
0x40d6af  push    edi; hPrevInstance
0x40d6b0  push    offset __ImageBase; hInstance
0x40d6b5  call    _WinMain@16
0x40d6ba  mov     esi, eax
0x40d6bc  call    ___scrt_is_managed_app
0x40d6c1  test    al, al
0x40d6c3  jz      short loc_40D72F
0x40d6c5  test    bl, bl
0x40d6c7  jnz     short loc_40D6CE
0x40d6c9  call    __cexit
0x40d6ce  push    edi; char
0x40d6cf  push    1; Terminating
0x40d6d1  call    ___scrt_uninitialize_crt
0x40d6d6  pop     ecx
0x40d6d7  pop     ecx
0x40d6d8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40d6df  mov     eax, esi
0x40d6e1  jmp     short loc_40D718
0x40d6e3  mov     ecx, [ebp+ms_exc.exc_ptr]
0x40d6e6  mov     eax, [ecx]
0x40d6e8  mov     eax, [eax]
0x40d6ea  mov     [ebp+Code], eax
0x40d6ed  push    ecx; ExceptionPtr
0x40d6ee  push    eax; ExceptionNum
0x40d6ef  call    __seh_filter_exe
0x40d6f4  pop     ecx
0x40d6f5  pop     ecx
0x40d6f6  retn
0x40d6f7  mov     esp, [ebp+ms_exc.old_esp]
0x40d6fa  call    ___scrt_is_managed_app
0x40d6ff  test    al, al
0x40d701  jz      short loc_40D735
0x40d703  cmp     [ebp+var_19], 0
0x40d707  jnz     short loc_40D70E
0x40d709  call    __c_exit
0x40d70e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40d715  mov     eax, [ebp+Code]
0x40d718  mov     ecx, [ebp+ms_exc.registration.Next]
0x40d71b  mov     large fs:0, ecx
0x40d722  pop     ecx
0x40d723  pop     edi
0x40d724  pop     esi
0x40d725  pop     ebx
0x40d726  leave
0x40d727  retn
0x40d728  push    7
0x40d72a  call    ___scrt_fastfail
0x40d72f  push    esi; FileName
0x40d730  call    __loaddll
0x40d735  push    [ebp+Code]; Code
0x40d738  call    __exit
```
