# Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_f0f2ad5f90657ad8d9071b6e9a8e4fbb___::Invoke

- ea: `0x140002df0`
- end: `0x140002e04`
- name: `Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_f0f2ad5f90657ad8d9071b6e9a8e4fbb___::Invoke`
- size: `20`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x140002dfd`

## pseudocode

```c
BOOL __fastcall Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_f0f2ad5f90657ad8d9071b6e9a8e4fbb___::Invoke(
        __int64 a1)
{
  return PostThreadMessageW(*(_DWORD *)(a1 + 16), 0x12u, 0, 0);
}

```

## disassembly

```asm
0x140002df0  mov     ecx, [rcx+10h]
0x140002df3  xor     r9d, r9d
0x140002df6  xor     r8d, r8d
0x140002df9  lea     edx, [r9+12h]
0x140002dfd  jmp     cs:__imp_PostThreadMessageW
```
