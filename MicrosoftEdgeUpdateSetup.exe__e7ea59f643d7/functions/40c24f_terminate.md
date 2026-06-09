# _terminate

- ea: `0x40c24f`
- end: `0x40c28b`
- name: `_terminate`
- size: `60`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x408920`
- `0x40900e`
- `0x4090b1`
- `0x40a3ab`
- `0x40af8c`
- `0x40b8ea`
- `0x40bb56`

## callees

- `0x405810`
- `0x4089e0`
- `0x40c24f`
- `0x40c30b`
- `0x40e819`

## pseudocode

```c
void __noreturn terminate()
{
  void (__thiscall *v0)(_DWORD); // esi

  v0 = (void (__thiscall *)(_DWORD))*((_DWORD *)__acrt_getptd() + 3);
  if ( v0 )
    v0(v0);
  abort();
}

```

## disassembly

```asm
0x40c24f  push    8
0x40c251  push    offset stru_424160
0x40c256  call    __SEH_prolog4
0x40c25b  call    ___acrt_getptd
0x40c260  mov     esi, [eax+0Ch]
0x40c263  test    esi, esi
0x40c265  jz      short loc_40C285
0x40c267  and     [ebp+ms_exc.registration.TryLevel], 0
0x40c26b  mov     ecx, esi
0x40c26d  call    ds:___guard_check_icall_fptr
0x40c273  call    esi
0x40c275  jmp     short loc_40C27E
0x40c277  xor     eax, eax
0x40c279  inc     eax
0x40c27a  retn
0x40c27b  mov     esp, [ebp+ms_exc.old_esp]
0x40c27e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40c285  call    _abort
```
