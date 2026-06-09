# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$17

- ea: `0x18001231d`
- end: `0x180012343`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$17`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b7fc`
- `0x18001231d`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_17(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 0x20;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~0x20u;
    return std::wstring::~wstring(*(char ***)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x18001231d  push    rbp
0x18001231f  sub     rsp, 20h
0x180012323  mov     rbp, rdx
0x180012326  mov     eax, [rbp+20h]
0x180012329  and     eax, 20h
0x18001232c  test    eax, eax
0x18001232e  jz      short loc_18001233D
0x180012330  and     dword ptr [rbp+20h], 0FFFFFFDFh
0x180012334  mov     rcx, [rbp+50h]
0x180012338  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001233d  add     rsp, 20h
0x180012341  pop     rbp
0x180012342  retn
```
