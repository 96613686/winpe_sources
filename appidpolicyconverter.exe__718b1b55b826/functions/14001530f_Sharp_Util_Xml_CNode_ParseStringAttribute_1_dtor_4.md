# _Sharp::Util::Xml::CNode::ParseStringAttribute_::_1_::dtor$4

- ea: `0x14001530f`
- end: `0x140015335`
- name: `_Sharp::Util::Xml::CNode::ParseStringAttribute_::_1_::dtor$4`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e2c`
- `0x14001530f`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::ParseStringAttribute_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 72), a2);
  }
  return result;
}

```

## disassembly

```asm
0x14001530f  push    rbp
0x140015311  sub     rsp, 20h
0x140015315  mov     rbp, rdx
0x140015318  mov     eax, [rbp+30h]
0x14001531b  and     eax, 1
0x14001531e  test    eax, eax
0x140015320  jz      short loc_14001532F
0x140015322  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140015326  mov     rcx, [rbp+48h]
0x14001532a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001532f  add     rsp, 20h
0x140015333  pop     rbp
0x140015334  retn
```
