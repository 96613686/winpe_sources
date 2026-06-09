# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x1800040a0`
- end: `0x1800040bb`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `132`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ea0`
- `0x180004480`
- `0x180004590`
- `0x180004a50`
- `0x180004aa0`
- `0x180004c70`
- `0x180004e40`
- `0x1800052e0`
- `0x1800058e0`
- `0x180006110`
- `0x180006940`
- `0x180006b70`
- `0x180007150`
- `0x180007820`
- `0x180008c60`
- `0x1800098d0`
- `0x18000a9e0`
- `0x18000ade0`
- `0x18000bd20`
- `0x18000d1f0`
- `0x18000d4e0`
- `0x18000d7a0`
- `0x18000dfb0`
- `0x18000e4a0`
- `0x18000f1a0`
- `0x1800105a0`
- `0x1800107a0`
- `0x1800113a0`
- `0x180013c10`
- `0x180013d70`
- `0x180013ed0`
- `0x180014230`
- `0x180014870`
- `0x180014bb0`
- `0x180014d10`
- `0x180015860`
- `0x180015a80`
- `0x180015b30`
- `0x180015df0`
- `0x180015e40`
- `0x1800166c0`
- `0x180016760`
- `0x1800170d0`
- `0x180017200`
- `0x1800172c0`
- `0x180017340`
- `0x180017910`
- `0x1800182e0`
- `0x180018510`
- `0x180018910`

## callees

- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800040a0  mov     rdx, [rcx]
0x1800040a3  mov     qword ptr [rcx], 0
0x1800040aa  mov     rcx, rdx
0x1800040ad  mov     rax, [rdx]
0x1800040b0  mov     rax, [rax+10h]
0x1800040b4  jmp     cs:__guard_dispatch_icall_fptr
```
