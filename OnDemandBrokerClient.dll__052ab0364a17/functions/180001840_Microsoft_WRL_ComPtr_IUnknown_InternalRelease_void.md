# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180001840`
- end: `0x180001861`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001270`
- `0x1800015a0`
- `0x180001920`
- `0x180001b70`
- `0x180001c20`

## callees

- `0x180001840`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x180001840  mov     rax, rcx
0x180001843  xor     edx, edx
0x180001845  mov     rcx, [rcx]
0x180001848  test    rcx, rcx
0x18000184b  jz      short loc_18000185D
0x18000184d  mov     [rax], rdx
0x180001850  mov     rax, [rcx]
0x180001853  mov     rax, [rax+10h]
0x180001857  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000185c  retn
0x18000185d  mov     eax, edx
0x18000185f  jmp     short locret_18000185C
```
