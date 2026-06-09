# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$9

- ea: `0x18001226d`
- end: `0x180012293`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$9`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b7fc`
- `0x18001226d`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_9(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    return std::wstring::~wstring((char **)(a2 + 88));
  }
  return result;
}

```

## disassembly

```asm
0x18001226d  push    rbp
0x18001226f  sub     rsp, 20h
0x180012273  mov     rbp, rdx
0x180012276  mov     eax, [rbp+20h]
0x180012279  and     eax, 2
0x18001227c  test    eax, eax
0x18001227e  jz      short loc_18001228D
0x180012280  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x180012284  lea     rcx, [rbp+58h]
0x180012288  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001228d  add     rsp, 20h
0x180012291  pop     rbp
0x180012292  retn
```
