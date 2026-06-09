# CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(void)

- ea: `0x140010144`
- end: `0x140010190`
- name: `??1?$ScopeGuardGlobalFuncImpl@V_lambda_2b09a7e4faa30095a7d023915a4f2697_@@@CommonUtil@@QEAA@XZ`
- size: `76`
- prototype: `__int64 (__fastcall *__fastcall(_BYTE *))(int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400125c1`

## callees

- `0x140010144`

## pseudocode

```c
__int64 (__fastcall *__fastcall CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(
        _BYTE *a1))(int, int, int, int, __int64)
{
  __int64 (__fastcall *result)(int, int, int, int, __int64); // rax

  if ( !*a1 )
  {
    off_14001B010 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B020 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B008 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B018 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    result = CommonUtil::GetFileVersionInfoExWDownlevel;
    off_14001B000 = CommonUtil::GetFileVersionInfoExWDownlevel;
  }
  return result;
}

```

## disassembly

```asm
0x140010144  cmp     byte ptr [rcx], 0
0x140010147  jnz     short locret_14001018F
0x140010149  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x140010150  mov     cs:off_14001B010, rax
0x140010157  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x14001015e  mov     cs:off_14001B020, rax
0x140010165  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x14001016c  mov     cs:off_14001B008, rax
0x140010173  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x14001017a  mov     cs:off_14001B018, rax
0x140010181  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x140010188  mov     cs:off_14001B000, rax
0x14001018f  retn
```
