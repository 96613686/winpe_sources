# _PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor$2

- ea: `0x14001424d`
- end: `0x140014273`
- name: `_PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor$2`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e2c`
- `0x14001424d`

## pseudocode

```c
__int64 __fastcall PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(a2 + 104, a2);
  }
  return result;
}

```

## disassembly

```asm
0x14001424d  push    rbp
0x14001424f  sub     rsp, 20h
0x140014253  mov     rbp, rdx
0x140014256  mov     eax, [rbp+20h]
0x140014259  and     eax, 1
0x14001425c  test    eax, eax
0x14001425e  jz      short loc_14001426D
0x140014260  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140014264  lea     rcx, [rbp+68h]
0x140014268  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001426d  add     rsp, 20h
0x140014271  pop     rbp
0x140014272  retn
```
