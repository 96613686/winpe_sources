# CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(void)

- ea: `0x1800088d0`
- end: `0x18000891c`
- name: `??1?$ScopeGuardGlobalFuncImpl@V_lambda_2b09a7e4faa30095a7d023915a4f2697_@@@CommonUtil@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009ba5`

## callees

- `0x1800088d0`

## pseudocode

```c
__int64 (__fastcall *__fastcall CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(
        _BYTE *a1))(int, int, int, int, __int64)
{
  __int64 (__fastcall *result)(int, int, int, int, __int64); // rax

  if ( !*a1 )
  {
    off_180012058[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_180012068 = CommonUtil::VerQueryValueWNotInitialized;
    off_180012050[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_180012060 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    result = CommonUtil::GetFileVersionInfoExWDownlevel;
    off_180012048 = CommonUtil::GetFileVersionInfoExWDownlevel;
  }
  return result;
}

```

## disassembly

```asm
0x1800088d0  cmp     byte ptr [rcx], 0
0x1800088d3  jnz     short locret_18000891B
0x1800088d5  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800088dc  mov     cs:off_180012058, rax
0x1800088e3  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800088ea  mov     cs:off_180012068, rax
0x1800088f1  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800088f8  mov     cs:off_180012050, rax
0x1800088ff  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x180008906  mov     cs:off_180012060, rax
0x18000890d  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x180008914  mov     cs:off_180012048, rax
0x18000891b  retn
```
