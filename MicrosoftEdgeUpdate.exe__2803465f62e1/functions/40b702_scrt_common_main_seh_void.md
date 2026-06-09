# __scrt_common_main_seh(void)

- ea: `0x40b702`
- end: `0x40b87d`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `379`
- prototype: `char *__usercall@<eax>(char *@<esi>)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40b880`

## callees

- `0x407eb0`
- `0x40aca2`
- `0x40b702`
- `0x40ba26`
- `0x40ba58`
- `0x40bb18`
- `0x40bbac`
- `0x40bbc9`
- `0x40bd49`
- `0x40bd4f`
- `0x40bd55`
- `0x40be70`
- `0x40bea6`
- `0x40bfc0`
- `0x40e29f`
- `0x40e9f7`
- `0x40ea41`
- `0x40ea86`
- `0x40ed39`
- `0x40ed48`
- `0x40ed57`
- `0x40ed6d`
- `0x40ed93`

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

  if ( !(unsigned __int8)__scrt_initialize_crt(1) || (v1 = 0, v9 = __scrt_acquire_startup_lock(), dword_417CCC == 1) )
  {
    __scrt_fastfail(7);
    goto LABEL_19;
  }
  if ( dword_417CCC )
  {
    v1 = 1;
  }
  else
  {
    dword_417CCC = 1;
    if ( _initterm_e((_PIFV *)&dword_40100C, (_PIFV *)&dword_401028) )
      return (char *)255;
    _initterm((_PVFV *)&First, (_PVFV *)&Last);
    dword_417CCC = 2;
  }
  __scrt_release_startup_lock(v9);
  v3 = (_DWORD *)sub_40BD49();
  v4 = v3;
  if ( *v3 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v3) )
    ((void (__thiscall *)(_DWORD, _DWORD, int, _DWORD))*v4)(*v4, 0, 2, 0);
  v5 = (_tls_callback_type *)sub_40BD4F();
  v6 = v5;
  if ( *v5 && (unsigned __int8)__scrt_is_nonwritable_in_current_image(v5) )
    _register_thread_local_exe_atexit_callback(*v6);
  show_window_mode = (unsigned __int16)__scrt_get_show_window_mode();
  v8 = (CHAR *)unknown_libname_7();
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
0x40b702  push    14h
0x40b704  push    offset stru_4167E8
0x40b709  call    __SEH_prolog4
0x40b70e  push    1
0x40b710  call    ___scrt_initialize_crt
0x40b715  pop     ecx
0x40b716  test    al, al
0x40b718  jz      loc_40B868
0x40b71e  xor     bl, bl
0x40b720  mov     [ebp+var_19], bl
0x40b723  and     [ebp+ms_exc.registration.TryLevel], 0
0x40b727  call    ___scrt_acquire_startup_lock
0x40b72c  mov     byte ptr [ebp+var_24], al
0x40b72f  mov     eax, dword_417CCC
0x40b734  xor     ecx, ecx
0x40b736  inc     ecx
0x40b737  cmp     eax, ecx
0x40b739  jz      loc_40B868
0x40b73f  test    eax, eax
0x40b741  jnz     short loc_40B78C
0x40b743  mov     dword_417CCC, ecx
0x40b749  push    offset dword_401028; Last
0x40b74e  push    offset dword_40100C; First
0x40b753  call    __initterm_e
0x40b758  pop     ecx
0x40b759  pop     ecx
0x40b75a  test    eax, eax
0x40b75c  jz      short loc_40B76F
0x40b75e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40b765  mov     eax, 0FFh
0x40b76a  jmp     loc_40B858
0x40b76f  push    offset Last; Last
0x40b774  push    offset First; First
0x40b779  call    __initterm
0x40b77e  pop     ecx
0x40b77f  pop     ecx
0x40b780  mov     dword_417CCC, 2
0x40b78a  jmp     short loc_40B791
0x40b78c  mov     bl, cl
0x40b78e  mov     [ebp+var_19], bl
0x40b791  push    [ebp+var_24]
0x40b794  call    ___scrt_release_startup_lock
0x40b799  pop     ecx
0x40b79a  call    sub_40BD49
0x40b79f  mov     esi, eax
0x40b7a1  xor     edi, edi
0x40b7a3  cmp     [esi], edi
0x40b7a5  jz      short loc_40B7C2
0x40b7a7  push    esi
0x40b7a8  call    ___scrt_is_nonwritable_in_current_image
0x40b7ad  pop     ecx
0x40b7ae  test    al, al
0x40b7b0  jz      short loc_40B7C2
0x40b7b2  mov     esi, [esi]
0x40b7b4  push    edi
0x40b7b5  push    2
0x40b7b7  push    edi
0x40b7b8  mov     ecx, esi
0x40b7ba  call    ds:___guard_check_icall_fptr
0x40b7c0  call    esi
0x40b7c2  call    sub_40BD4F
0x40b7c7  mov     esi, eax
0x40b7c9  cmp     [esi], edi
0x40b7cb  jz      short loc_40B7E0
0x40b7cd  push    esi
0x40b7ce  call    ___scrt_is_nonwritable_in_current_image
0x40b7d3  pop     ecx
0x40b7d4  test    al, al
0x40b7d6  jz      short loc_40B7E0
0x40b7d8  push    dword ptr [esi]; Callback
0x40b7da  call    __register_thread_local_exe_atexit_callback
0x40b7df  pop     ecx
0x40b7e0  call    ___scrt_get_show_window_mode
0x40b7e5  movzx   esi, ax
0x40b7e8  call    unknown_libname_7; Microsoft VisualC universal runtime
0x40b7ed  push    esi; nShowCmd
0x40b7ee  push    eax; lpCmdLine
0x40b7ef  push    edi; hPrevInstance
0x40b7f0  push    offset __ImageBase; hInstance
0x40b7f5  call    _WinMain@16
0x40b7fa  mov     esi, eax
0x40b7fc  call    ___scrt_is_managed_app
0x40b801  test    al, al
0x40b803  jz      short loc_40B86F
0x40b805  test    bl, bl
0x40b807  jnz     short loc_40B80E
0x40b809  call    __cexit
0x40b80e  push    edi; char
0x40b80f  push    1; Terminating
0x40b811  call    ___scrt_uninitialize_crt
0x40b816  pop     ecx
0x40b817  pop     ecx
0x40b818  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40b81f  mov     eax, esi
0x40b821  jmp     short loc_40B858
0x40b823  mov     ecx, [ebp+ms_exc.exc_ptr]
0x40b826  mov     eax, [ecx]
0x40b828  mov     eax, [eax]
0x40b82a  mov     [ebp+Code], eax
0x40b82d  push    ecx; ExceptionPtr
0x40b82e  push    eax; ExceptionNum
0x40b82f  call    __seh_filter_exe
0x40b834  pop     ecx
0x40b835  pop     ecx
0x40b836  retn
0x40b837  mov     esp, [ebp+ms_exc.old_esp]
0x40b83a  call    ___scrt_is_managed_app
0x40b83f  test    al, al
0x40b841  jz      short loc_40B875
0x40b843  cmp     [ebp+var_19], 0
0x40b847  jnz     short loc_40B84E
0x40b849  call    __c_exit
0x40b84e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40b855  mov     eax, [ebp+Code]
0x40b858  mov     ecx, [ebp+ms_exc.registration.Next]
0x40b85b  mov     large fs:0, ecx
0x40b862  pop     ecx
0x40b863  pop     edi
0x40b864  pop     esi
0x40b865  pop     ebx
0x40b866  leave
0x40b867  retn
0x40b868  push    7
0x40b86a  call    ___scrt_fastfail
0x40b86f  push    esi; FileName
0x40b870  call    __loaddll
0x40b875  push    [ebp+Code]; Code
0x40b878  call    __exit
```
