# Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)

- ea: `0x180006b98`
- end: `0x180006bb6`
- name: `?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b120`
- `0x180011408`
- `0x1800179a0`
- `0x180018ba0`
- `0x1800197e0`
- `0x18001983c`
- `0x180019acc`
- `0x18001a500`
- `0x18001ecb0`
- `0x18001f090`
- `0x18001f350`
- `0x1800200dc`
- `0x1800201ac`
- `0x1800206d0`
- `0x180020730`
- `0x1800207f0`
- `0x180020d50`
- `0x18002214c`

## callees

- `0x180006b98`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180006b98  sub     rsp, 28h
0x180006b9c  mov     rcx, [rcx]
0x180006b9f  test    rcx, rcx
0x180006ba2  jz      short loc_180006BB1
0x180006ba4  mov     rax, [rcx]
0x180006ba7  mov     rax, [rax+8]
0x180006bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb0  nop
0x180006bb1  add     rsp, 28h
0x180006bb5  retn
```
