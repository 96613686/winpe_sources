# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$15

- ea: `0x1800122f1`
- end: `0x180012317`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$15`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b7fc`
- `0x1800122f1`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_15(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 0x10;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~0x10u;
    return std::wstring::~wstring(*(char ***)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x1800122f1  push    rbp
0x1800122f3  sub     rsp, 20h
0x1800122f7  mov     rbp, rdx
0x1800122fa  mov     eax, [rbp+20h]
0x1800122fd  and     eax, 10h
0x180012300  test    eax, eax
0x180012302  jz      short loc_180012311
0x180012304  and     dword ptr [rbp+20h], 0FFFFFFEFh
0x180012308  mov     rcx, [rbp+50h]
0x18001230c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012311  add     rsp, 20h
0x180012315  pop     rbp
0x180012316  retn
```
