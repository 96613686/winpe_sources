# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x140002dc0`
- end: `0x140002de9`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `41`
- prototype: `__int64(__int64, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14000384c`

## callees

- `0x1400022f0`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  return Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeHelper<_lambda_fe718337787c493ce2d833414db25eba_>(
           a1,
           a2,
           va);
}

```

## disassembly

```asm
0x140002dc0  mov     rax, rsp
0x140002dc3  mov     [rax+10h], rdx
0x140002dc7  mov     [rax+18h], r8
0x140002dcb  mov     [rax+20h], r9
0x140002dcf  sub     rsp, 38h
0x140002dd3  lea     r8, [rax+18h]
0x140002dd7  mov     qword ptr [rax-18h], 0
0x140002ddf  call    ??$_InitializeHelper@V_lambda_fe718337787c493ce2d833414db25eba_@@@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBGPEADAEBV_lambda_fe718337787c493ce2d833414db25eba_@@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeHelper<_lambda_fe718337787c493ce2d833414db25eba_>(ushort const *,char *,_lambda_fe718337787c493ce2d833414db25eba_ const &)
0x140002de4  add     rsp, 38h
0x140002de8  retn
```
