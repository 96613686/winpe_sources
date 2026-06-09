# Microsoft::WRL::Details::OutOfProcModuleBase_MultipleUseOutOfProcModule_::GenericReleaseNotifier__lambda_3be76e96985116ee8b2c75684a2c565b___::Invoke

- ea: `0x14000a530`
- end: `0x14000a544`
- name: `Microsoft::WRL::Details::OutOfProcModuleBase_MultipleUseOutOfProcModule_::GenericReleaseNotifier__lambda_3be76e96985116ee8b2c75684a2c565b___::Invoke`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14000a53d`

## pseudocode

```c
BOOL __fastcall Microsoft::WRL::Details::OutOfProcModuleBase_MultipleUseOutOfProcModule_::GenericReleaseNotifier__lambda_3be76e96985116ee8b2c75684a2c565b___::Invoke(
        __int64 a1)
{
  return PostThreadMessageW(*(_DWORD *)(a1 + 16), 0x12u, 0, 0);
}

```

## disassembly

```asm
0x14000a530  mov     ecx, [rcx+10h]
0x14000a533  xor     r9d, r9d
0x14000a536  xor     r8d, r8d
0x14000a539  lea     edx, [r9+12h]
0x14000a53d  jmp     cs:__imp_PostThreadMessageW
```
