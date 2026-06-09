# _terminate

- ea: `0x411615`
- end: `0x411651`
- name: `_terminate`
- size: `60`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x40da20`
- `0x40e78e`
- `0x40e831`
- `0x40f497`
- `0x41006c`
- `0x410687`
- `0x4108f3`

## callees

- `0x402330`
- `0x40dc70`
- `0x411615`
- `0x4116b0`
- `0x413a39`

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
0x411615  push    8
0x411617  push    offset stru_43B628
0x41161c  call    __SEH_prolog4
0x411621  call    ___acrt_getptd
0x411626  mov     esi, [eax+0Ch]
0x411629  test    esi, esi
0x41162b  jz      short loc_41164B
0x41162d  and     [ebp+ms_exc.registration.TryLevel], 0
0x411631  mov     ecx, esi
0x411633  call    ds:___guard_check_icall_fptr
0x411639  call    esi
0x41163b  jmp     short loc_411644
0x41163d  xor     eax, eax
0x41163f  inc     eax
0x411640  retn
0x411641  mov     esp, [ebp+ms_exc.old_esp]
0x411644  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x41164b  call    _abort
```
