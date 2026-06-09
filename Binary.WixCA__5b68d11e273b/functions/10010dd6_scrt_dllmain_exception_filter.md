# ___scrt_dllmain_exception_filter

- ea: `0x10010dd6`
- end: `0x10010e0a`
- name: `___scrt_dllmain_exception_filter`
- size: `52`
- prototype: `int __cdecl(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10010920`

## callees

- `0x1000b035`
- `0x10010dd6`
- `0x10011376`
- `0x10015fb5`

## pseudocode

```c
int __cdecl __scrt_dllmain_exception_filter(
        int a1,
        int a2,
        int a3,
        void (__thiscall *a4)(_DWORD, int, _DWORD, int),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !__scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a4, a1, 0, a3);
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x10010dd6  push    ebp
0x10010dd7  mov     ebp, esp
0x10010dd9  call    ___scrt_is_ucrt_dll_in_use
0x10010dde  test    eax, eax
0x10010de0  jnz     short loc_10010DFB
0x10010de2  cmp     [ebp+arg_4], 1
0x10010de6  jnz     short loc_10010DFB
0x10010de8  push    [ebp+arg_8]
0x10010deb  mov     ecx, [ebp+arg_C]
0x10010dee  push    eax
0x10010def  push    [ebp+arg_0]
0x10010df2  call    ds:___guard_check_icall_fptr
0x10010df8  call    [ebp+arg_C]
0x10010dfb  push    [ebp+ExceptionPtr]; ExceptionPtr
0x10010dfe  push    [ebp+ExceptionNum]; ExceptionNum
0x10010e01  call    __seh_filter_dll
0x10010e06  pop     ecx
0x10010e07  pop     ecx
0x10010e08  pop     ebp
0x10010e09  retn
```
