# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$13

- ea: `0x1800122c5`
- end: `0x1800122eb`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$13`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b7fc`
- `0x1800122c5`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_13(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 8;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~8u;
    return std::wstring::~wstring((char **)(a2 + 88));
  }
  return result;
}

```

## disassembly

```asm
0x1800122c5  push    rbp
0x1800122c7  sub     rsp, 20h
0x1800122cb  mov     rbp, rdx
0x1800122ce  mov     eax, [rbp+20h]
0x1800122d1  and     eax, 8
0x1800122d4  test    eax, eax
0x1800122d6  jz      short loc_1800122E5
0x1800122d8  and     dword ptr [rbp+20h], 0FFFFFFF7h
0x1800122dc  lea     rcx, [rbp+58h]
0x1800122e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122e5  add     rsp, 20h
0x1800122e9  pop     rbp
0x1800122ea  retn
```
