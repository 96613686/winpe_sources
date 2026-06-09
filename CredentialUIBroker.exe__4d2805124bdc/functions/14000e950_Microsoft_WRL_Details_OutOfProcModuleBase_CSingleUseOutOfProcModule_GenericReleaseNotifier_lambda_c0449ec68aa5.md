# Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_c0449ec68aa58ed5e74c8ca509f85e9a___::Invoke

- ea: `0x14000e950`
- end: `0x14000e964`
- name: `Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_c0449ec68aa58ed5e74c8ca509f85e9a___::Invoke`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14000e95d`

## pseudocode

```c
BOOL __fastcall Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_c0449ec68aa58ed5e74c8ca509f85e9a___::Invoke(
        __int64 a1)
{
  return PostThreadMessageW(*(_DWORD *)(a1 + 16), 0x12u, 0, 0);
}

```

## disassembly

```asm
0x14000e950  mov     ecx, [rcx+10h]
0x14000e953  xor     r9d, r9d
0x14000e956  xor     r8d, r8d
0x14000e959  lea     edx, [r9+12h]
0x14000e95d  jmp     cs:__imp_PostThreadMessageW
```
