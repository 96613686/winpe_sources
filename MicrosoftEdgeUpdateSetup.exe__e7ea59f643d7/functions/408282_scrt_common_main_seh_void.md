# __scrt_common_main_seh(void)

- ea: `0x408282`
- end: `0x4083fd`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `379`
- prototype: `char *__usercall@<eax>(char *@<esi>)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x408400`

## callees

- `0x403116`
- `0x405810`
- `0x408282`
- `0x40844e`
- `0x408480`
- `0x408540`
- `0x4085d4`
- `0x4085f1`
- `0x408773`
- `0x408779`
- `0x40877f`
- `0x40889a`
- `0x4088d0`
- `0x4089e0`
- `0x40b0d0`
- `0x40b7d7`
- `0x40b82a`
- `0x40b86f`
- `0x40bb22`
- `0x40bb31`
- `0x40bb40`
- `0x40bb56`
- `0x40bb7c`

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

  if ( !(unsigned __int8)__scrt_initialize_crt(1) || (v1 = 0, v9 = __scrt_acquire_startup_lock(), dword_426928 == 1) )
  {
    __scrt_fastfail(7);
    goto LABEL_19;
  }
  if ( dword_426928 )
  {
    v1 = 1;
  }
  else
  {
    dword_426928 = 1;
    if ( _initterm_e((_PIFV *)&dword_41C268, (_PIFV *)&dword_41C288) )
      return (char *)255;
    _initterm((_PVFV *)&First, (_PVFV *)&Last);
    dword_426928 = 2;
  }
  __scrt_release_startup_lock(v9);
  v3 = (_DWORD *)sub_408773();
  v4 = v3;
  if ( *v3 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v3) )
    ((void (__thiscall *)(_DWORD, _DWORD, int, _DWORD))*v4)(*v4, 0, 2, 0);
  v5 = (_tls_callback_type *)sub_408779();
  v6 = v5;
  if ( *v5 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v5) )
    _register_thread_local_exe_atexit_callback(*v6);
  show_window_mode = (unsigned __int16)__scrt_get_show_window_mode();
  v8 = (CHAR *)unknown_libname_6();
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
0x408282  push    14h
0x408284  push    offset stru_423F28
0x408289  call    __SEH_prolog4
0x40828e  push    1
0x408290  call    ___scrt_initialize_crt
0x408295  pop     ecx
0x408296  test    al, al
0x408298  jz      loc_4083E8
0x40829e  xor     bl, bl
0x4082a0  mov     [ebp+var_19], bl
0x4082a3  and     [ebp+ms_exc.registration.TryLevel], 0
0x4082a7  call    ___scrt_acquire_startup_lock
0x4082ac  mov     byte ptr [ebp+var_24], al
0x4082af  mov     eax, dword_426928
0x4082b4  xor     ecx, ecx
0x4082b6  inc     ecx
0x4082b7  cmp     eax, ecx
0x4082b9  jz      loc_4083E8
0x4082bf  test    eax, eax
0x4082c1  jnz     short loc_40830C
0x4082c3  mov     dword_426928, ecx
0x4082c9  push    offset dword_41C288; Last
0x4082ce  push    offset dword_41C268; First
0x4082d3  call    __initterm_e
0x4082d8  pop     ecx
0x4082d9  pop     ecx
0x4082da  test    eax, eax
0x4082dc  jz      short loc_4082EF
0x4082de  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x4082e5  mov     eax, 0FFh
0x4082ea  jmp     loc_4083D8
0x4082ef  push    offset Last; Last
0x4082f4  push    offset First; First
0x4082f9  call    __initterm
0x4082fe  pop     ecx
0x4082ff  pop     ecx
0x408300  mov     dword_426928, 2
0x40830a  jmp     short loc_408311
0x40830c  mov     bl, cl
0x40830e  mov     [ebp+var_19], bl
0x408311  push    [ebp+var_24]
0x408314  call    ___scrt_release_startup_lock
0x408319  pop     ecx
0x40831a  call    sub_408773
0x40831f  mov     esi, eax
0x408321  xor     edi, edi
0x408323  cmp     [esi], edi
0x408325  jz      short loc_408342
0x408327  push    esi
0x408328  call    ___scrt_is_nonwritable_in_current_image
0x40832d  pop     ecx
0x40832e  test    al, al
0x408330  jz      short loc_408342
0x408332  mov     esi, [esi]
0x408334  push    edi
0x408335  push    2
0x408337  push    edi
0x408338  mov     ecx, esi
0x40833a  call    ds:___guard_check_icall_fptr
0x408340  call    esi
0x408342  call    sub_408779
0x408347  mov     esi, eax
0x408349  cmp     [esi], edi
0x40834b  jz      short loc_408360
0x40834d  push    esi
0x40834e  call    ___scrt_is_nonwritable_in_current_image
0x408353  pop     ecx
0x408354  test    al, al
0x408356  jz      short loc_408360
0x408358  push    dword ptr [esi]; Callback
0x40835a  call    __register_thread_local_exe_atexit_callback
0x40835f  pop     ecx
0x408360  call    ___scrt_get_show_window_mode
0x408365  movzx   esi, ax
0x408368  call    unknown_libname_6; Microsoft VisualC universal runtime
0x40836d  push    esi; nShowCmd
0x40836e  push    eax; lpCmdLine
0x40836f  push    edi; hPrevInstance
0x408370  push    offset __ImageBase; hInstance
0x408375  call    _WinMain@16
0x40837a  mov     esi, eax
0x40837c  call    ___scrt_is_managed_app
0x408381  test    al, al
0x408383  jz      short loc_4083EF
0x408385  test    bl, bl
0x408387  jnz     short loc_40838E
0x408389  call    __cexit
0x40838e  push    edi; char
0x40838f  push    1; Terminating
0x408391  call    ___scrt_uninitialize_crt
0x408396  pop     ecx
0x408397  pop     ecx
0x408398  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40839f  mov     eax, esi
0x4083a1  jmp     short loc_4083D8
0x4083a3  mov     ecx, [ebp+ms_exc.exc_ptr]
0x4083a6  mov     eax, [ecx]
0x4083a8  mov     eax, [eax]
0x4083aa  mov     [ebp+Code], eax
0x4083ad  push    ecx; ExceptionPtr
0x4083ae  push    eax; ExceptionNum
0x4083af  call    __seh_filter_exe
0x4083b4  pop     ecx
0x4083b5  pop     ecx
0x4083b6  retn
0x4083b7  mov     esp, [ebp+ms_exc.old_esp]
0x4083ba  call    ___scrt_is_managed_app
0x4083bf  test    al, al
0x4083c1  jz      short loc_4083F5
0x4083c3  cmp     [ebp+var_19], 0
0x4083c7  jnz     short loc_4083CE
0x4083c9  call    __c_exit
0x4083ce  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x4083d5  mov     eax, [ebp+Code]
0x4083d8  mov     ecx, [ebp+ms_exc.registration.Next]
0x4083db  mov     large fs:0, ecx
0x4083e2  pop     ecx
0x4083e3  pop     edi
0x4083e4  pop     esi
0x4083e5  pop     ebx
0x4083e6  leave
0x4083e7  retn
0x4083e8  push    7
0x4083ea  call    ___scrt_fastfail
0x4083ef  push    esi; FileName
0x4083f0  call    __loaddll
0x4083f5  push    [ebp+Code]; Code
0x4083f8  call    __exit
```
