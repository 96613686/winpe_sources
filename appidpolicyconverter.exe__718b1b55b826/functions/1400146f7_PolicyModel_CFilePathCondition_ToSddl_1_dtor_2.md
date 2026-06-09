# _PolicyModel::CFilePathCondition::ToSddl_::_1_::dtor$2

- ea: `0x1400146f7`
- end: `0x14001471d`
- name: `_PolicyModel::CFilePathCondition::ToSddl_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e2c`
- `0x1400146f7`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePathCondition::ToSddl_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 56), a2);
  }
  return result;
}

```

## disassembly

```asm
0x1400146f7  push    rbp
0x1400146f9  sub     rsp, 20h
0x1400146fd  mov     rbp, rdx
0x140014700  mov     eax, [rbp+30h]
0x140014703  and     eax, 1
0x140014706  test    eax, eax
0x140014708  jz      short loc_140014717
0x14001470a  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14001470e  mov     rcx, [rbp+38h]
0x140014712  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014717  add     rsp, 20h
0x14001471b  pop     rbp
0x14001471c  retn
```
