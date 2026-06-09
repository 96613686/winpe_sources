# _RegistryKeyIterator::operator__::_1_::dtor$0

- ea: `0x18001427a`
- end: `0x1800142a0`
- name: `_RegistryKeyIterator::operator__::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000732c`
- `0x18001427a`

## pseudocode

```c
__int64 __fastcall RegistryKeyIterator::operator__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x18001427a  push    rbp
0x18001427c  sub     rsp, 20h
0x180014280  mov     rbp, rdx
0x180014283  mov     eax, [rbp+20h]
0x180014286  and     eax, 1
0x180014289  test    eax, eax
0x18001428b  jz      short loc_18001429A
0x18001428d  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180014291  mov     rcx, [rbp+48h]
0x180014295  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18001429a  add     rsp, 20h
0x18001429e  pop     rbp
0x18001429f  retn
```
