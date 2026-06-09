# _terminate

- ea: `0x40f45f`
- end: `0x40f49b`
- name: `_terminate`
- size: `60`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x40bf00`
- `0x40c4a8`
- `0x40c6fd`
- `0x40d59e`
- `0x40eb01`
- `0x40ed6d`

## callees

- `0x407eb0`
- `0x40bfc0`
- `0x40f45f`
- `0x40f51a`
- `0x40f9a9`

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
0x40f45f  push    8
0x40f461  push    offset stru_416A28
0x40f466  call    __SEH_prolog4
0x40f46b  call    ___acrt_getptd
0x40f470  mov     esi, [eax+0Ch]
0x40f473  test    esi, esi
0x40f475  jz      short loc_40F495
0x40f477  and     [ebp+ms_exc.registration.TryLevel], 0
0x40f47b  mov     ecx, esi
0x40f47d  call    ds:___guard_check_icall_fptr
0x40f483  call    esi
0x40f485  jmp     short loc_40F48E
0x40f487  xor     eax, eax
0x40f489  inc     eax
0x40f48a  retn
0x40f48b  mov     esp, [ebp+ms_exc.old_esp]
0x40f48e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40f495  call    _abort
```
