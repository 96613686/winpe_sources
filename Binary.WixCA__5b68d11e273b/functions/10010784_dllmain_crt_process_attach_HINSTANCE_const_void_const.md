# dllmain_crt_process_attach(HINSTANCE__ * const,void * const)

- ea: `0x10010784`
- end: `0x1001088e`
- name: `?dllmain_crt_process_attach@@YAHQAUHINSTANCE__@@QAX@Z`
- size: `266`
- prototype: `int __cdecl(HINSTANCE, void *const)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x10010731`

## callees

- `0x1000b035`
- `0x10010784`
- `0x10010cc6`
- `0x10010cde`
- `0x10010d3f`
- `0x10010d71`
- `0x10010d9c`
- `0x10010e3a`
- `0x10010f18`
- `0x10010fac`
- `0x10010ff1`
- `0x10010ff7`
- `0x10011119`
- `0x10011180`
- `0x10015f40`
- `0x10015f87`

## pseudocode

```c
int __cdecl dllmain_crt_process_attach(HINSTANCE a1, void *const a2)
{
  char v3; // bl
  _DWORD *v4; // eax
  _DWORD *v5; // esi
  char v6; // [esp+13h] [ebp-1Dh]

  if ( !(unsigned __int8)__scrt_initialize_crt(0) )
    return 0;
  v6 = __scrt_acquire_startup_lock();
  v3 = 1;
  if ( dword_10034CF0 )
  {
    __scrt_fastfail(7);
    __debugbreak();
  }
  dword_10034CF0 = 1;
  if ( (unsigned __int8)__scrt_dllmain_before_initialize_c() )
  {
    sub_10011119();
    sub_10010CC6();
    __scrt_initialize_default_local_stdio_options();
    if ( !_initterm_e((_PIFV *)&dword_1002235C, (_PIFV *)&dword_10022370) )
    {
      if ( (unsigned __int8)__scrt_dllmain_after_initialize_c() )
      {
        _initterm((_PVFV *)&First, (_PVFV *)&Last);
        dword_10034CF0 = 2;
        v3 = 0;
      }
    }
  }
  __scrt_release_startup_lock(v6);
  if ( v3 )
    return 0;
  v4 = (_DWORD *)sub_10010FF1();
  v5 = v4;
  if ( *v4 )
  {
    if ( (unsigned __int8)__scrt_is_nonwritable_in_current_image(v4) )
      ((void (__thiscall *)(_DWORD, HINSTANCE, int, void *const))*v5)(*v5, a1, 2, a2);
  }
  ++dword_100349C0;
  return 1;
}

```

## disassembly

```asm
0x10010784  push    10h
0x10010786  push    offset stru_10030F40
0x1001078b  call    __SEH_prolog4
0x10010790  push    0
0x10010792  call    ___scrt_initialize_crt
0x10010797  pop     ecx
0x10010798  test    al, al
0x1001079a  jnz     short loc_100107A3
0x1001079c  xor     eax, eax
0x1001079e  jmp     loc_10010869
0x100107a3  call    ___scrt_acquire_startup_lock
0x100107a8  mov     byte ptr [ebp+var_1D], al
0x100107ab  mov     bl, 1
0x100107ad  mov     [ebp+var_19], bl
0x100107b0  and     [ebp+ms_exc.registration.TryLevel], 0
0x100107b4  cmp     dword_10034CF0, 0
0x100107bb  jnz     loc_10010886
0x100107c1  mov     dword_10034CF0, 1
0x100107cb  call    ___scrt_dllmain_before_initialize_c
0x100107d0  test    al, al
0x100107d2  jz      short loc_10010821
0x100107d4  call    sub_10011119
0x100107d9  call    sub_10010CC6
0x100107de  call    ___scrt_initialize_default_local_stdio_options
0x100107e3  push    offset dword_10022370; Last
0x100107e8  push    offset dword_1002235C; First
0x100107ed  call    __initterm_e
0x100107f2  pop     ecx
0x100107f3  pop     ecx
0x100107f4  test    eax, eax
0x100107f6  jnz     short loc_10010821
0x100107f8  call    ___scrt_dllmain_after_initialize_c
0x100107fd  test    al, al
0x100107ff  jz      short loc_10010821
0x10010801  push    offset Last; Last
0x10010806  push    offset First; First
0x1001080b  call    __initterm
0x10010810  pop     ecx
0x10010811  pop     ecx
0x10010812  mov     dword_10034CF0, 2
0x1001081c  xor     bl, bl
0x1001081e  mov     [ebp+var_19], bl
0x10010821  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10010828  call    loc_1001087C
0x1001082d  test    bl, bl
0x1001082f  jnz     loc_1001079C
0x10010835  call    sub_10010FF1
0x1001083a  mov     esi, eax
0x1001083c  cmp     dword ptr [esi], 0
0x1001083f  jz      short loc_10010860
0x10010841  push    esi
0x10010842  call    ___scrt_is_nonwritable_in_current_image
0x10010847  pop     ecx
0x10010848  test    al, al
0x1001084a  jz      short loc_10010860
0x1001084c  push    [ebp+arg_4]
0x1001084f  push    2
0x10010851  push    [ebp+arg_0]
0x10010854  mov     esi, [esi]
0x10010856  mov     ecx, esi
0x10010858  call    ds:___guard_check_icall_fptr
0x1001085e  call    esi
0x10010860  inc     dword_100349C0
0x10010866  xor     eax, eax
0x10010868  inc     eax
0x10010869  mov     ecx, [ebp+ms_exc.registration.Next]
0x1001086c  mov     large fs:0, ecx
0x10010873  pop     ecx
0x10010874  pop     edi
0x10010875  pop     esi
0x10010876  pop     ebx
0x10010877  leave
0x10010878  retn
0x10010879  mov     bl, [ebp+var_19]
0x1001087c  push    [ebp+var_1D]
0x1001087f  call    ___scrt_release_startup_lock
0x10010884  pop     ecx
0x10010885  retn
0x10010886  push    7
0x10010888  call    ___scrt_fastfail
0x1001088d  int     3; Trap to Debugger
```
