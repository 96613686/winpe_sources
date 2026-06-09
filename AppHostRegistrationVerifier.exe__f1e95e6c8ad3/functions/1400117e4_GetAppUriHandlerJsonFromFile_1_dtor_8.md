# _GetAppUriHandlerJsonFromFile_::_1_::dtor$8

- ea: `0x1400117e4`
- end: `0x14001180d`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$8`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b64`
- `0x1400117e4`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 4;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~4u;
    return std::wstring::~wstring(a2 + 624);
  }
  return result;
}

```

## disassembly

```asm
0x1400117e4  push    rbp
0x1400117e6  sub     rsp, 20h
0x1400117ea  mov     rbp, rdx
0x1400117ed  mov     eax, [rbp+30h]
0x1400117f0  and     eax, 4
0x1400117f3  test    eax, eax
0x1400117f5  jz      short loc_140011807
0x1400117f7  and     dword ptr [rbp+30h], 0FFFFFFFBh
0x1400117fb  lea     rcx, [rbp+270h]
0x140011802  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011807  add     rsp, 20h
0x14001180b  pop     rbp
0x14001180c  retn
```
