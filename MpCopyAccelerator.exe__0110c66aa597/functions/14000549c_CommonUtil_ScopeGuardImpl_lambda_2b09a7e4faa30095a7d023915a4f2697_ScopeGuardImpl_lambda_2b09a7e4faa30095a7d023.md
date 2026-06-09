# CommonUtil::ScopeGuardImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(void)

- ea: `0x14000549c`
- end: `0x1400054e8`
- name: `??1?$ScopeGuardImpl@V_lambda_2b09a7e4faa30095a7d023915a4f2697_@@@CommonUtil@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140025a4f`

## callees

- `0x14000549c`

## pseudocode

```c
__int64 (__fastcall *__fastcall CommonUtil::ScopeGuardImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(
        _BYTE *a1))(int, int, int, int, __int64)
{
  __int64 (__fastcall *result)(int, int, int, int, __int64); // rax

  if ( !*a1 )
  {
    off_14003B110[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_14003B118[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_14003B120[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_14003B128 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    result = CommonUtil::GetFileVersionInfoExWDownlevel;
    off_14003B130 = CommonUtil::GetFileVersionInfoExWDownlevel;
  }
  return result;
}

```

## disassembly

```asm
0x14000549c  cmp     byte ptr [rcx], 0
0x14000549f  jnz     short locret_1400054E7
0x1400054a1  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1400054a8  mov     cs:off_14003B110, rax
0x1400054af  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1400054b6  mov     cs:off_14003B118, rax
0x1400054bd  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1400054c4  mov     cs:off_14003B120, rax
0x1400054cb  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x1400054d2  mov     cs:off_14003B128, rax
0x1400054d9  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x1400054e0  mov     cs:off_14003B130, rax
0x1400054e7  retn
```
