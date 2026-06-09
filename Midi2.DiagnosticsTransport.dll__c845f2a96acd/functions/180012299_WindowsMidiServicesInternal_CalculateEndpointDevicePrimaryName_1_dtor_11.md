# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$11

- ea: `0x180012299`
- end: `0x1800122bf`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$11`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b7fc`
- `0x180012299`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_11(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 4;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~4u;
    return std::wstring::~wstring(*(char ***)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x180012299  push    rbp
0x18001229b  sub     rsp, 20h
0x18001229f  mov     rbp, rdx
0x1800122a2  mov     eax, [rbp+20h]
0x1800122a5  and     eax, 4
0x1800122a8  test    eax, eax
0x1800122aa  jz      short loc_1800122B9
0x1800122ac  and     dword ptr [rbp+20h], 0FFFFFFFBh
0x1800122b0  mov     rcx, [rbp+50h]
0x1800122b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122b9  add     rsp, 20h
0x1800122bd  pop     rbp
0x1800122be  retn
```
