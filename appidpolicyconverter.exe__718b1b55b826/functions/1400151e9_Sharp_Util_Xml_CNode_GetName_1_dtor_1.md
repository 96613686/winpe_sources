# _Sharp::Util::Xml::CNode::GetName_::_1_::dtor$1

- ea: `0x1400151e9`
- end: `0x14001520f`
- name: `_Sharp::Util::Xml::CNode::GetName_::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e2c`
- `0x1400151e9`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::GetName_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 48), a2);
  }
  return result;
}

```

## disassembly

```asm
0x1400151e9  push    rbp
0x1400151eb  sub     rsp, 20h
0x1400151ef  mov     rbp, rdx
0x1400151f2  mov     eax, [rbp+20h]
0x1400151f5  and     eax, 1
0x1400151f8  test    eax, eax
0x1400151fa  jz      short loc_140015209
0x1400151fc  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140015200  mov     rcx, [rbp+30h]
0x140015204  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015209  add     rsp, 20h
0x14001520d  pop     rbp
0x14001520e  retn
```
