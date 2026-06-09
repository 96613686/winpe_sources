# _OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$1

- ea: `0x14000eda0`
- end: `0x14000edac`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400083b4`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::lambda_call__lambda_b307d734c6599441bc136d573e025edc___::_lambda_call__lambda_b307d734c6599441bc136d573e025edc___(a2 + 48);
}

```

## disassembly

```asm
0x14000eda0  lea     rcx, [rdx+30h]
0x14000eda7  jmp     wil__details__lambda_call__lambda_b307d734c6599441bc136d573e025edc______lambda_call__lambda_b307d734c6599441bc136d573e025edc___
```
