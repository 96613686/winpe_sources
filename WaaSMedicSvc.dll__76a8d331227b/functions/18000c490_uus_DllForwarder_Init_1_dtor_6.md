# _uus::DllForwarder::_Init_::_1_::dtor$6

- ea: `0x18000c490`
- end: `0x18000c4b6`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$6`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008f20`
- `0x18000c490`

## pseudocode

```c
__int64 __fastcall uus::DllForwarder::_Init_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 40) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 40) &= ~2u;
    return std::wstring::~wstring((char **)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x18000c490  push    rbp
0x18000c492  sub     rsp, 20h
0x18000c496  mov     rbp, rdx
0x18000c499  mov     eax, [rbp+28h]
0x18000c49c  and     eax, 2
0x18000c49f  test    eax, eax
0x18000c4a1  jz      short loc_18000C4B0
0x18000c4a3  and     dword ptr [rbp+28h], 0FFFFFFFDh
0x18000c4a7  lea     rcx, [rbp+38h]
0x18000c4ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c4b0  add     rsp, 20h
0x18000c4b4  pop     rbp
0x18000c4b5  retn
```
