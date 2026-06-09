# _PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor$3

- ea: `0x140014279`
- end: `0x1400142a2`
- name: `_PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor$3`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000db9c`
- `0x140014279`

## pseudocode

```c
void __fastcall PolicyModel::CRule::DeserializeConditions_PolicyModel::CFilePathCondition__::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    PolicyModel::CFilePath::~CFilePath((PolicyModel::CFilePath *)(a2 + 136), a2);
  }
}

```

## disassembly

```asm
0x140014279  push    rbp
0x14001427b  sub     rsp, 20h
0x14001427f  mov     rbp, rdx
0x140014282  mov     eax, [rbp+20h]
0x140014285  and     eax, 2
0x140014288  test    eax, eax
0x14001428a  jz      short loc_14001429C
0x14001428c  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x140014290  lea     rcx, [rbp+88h]; this
0x140014297  call    ??1CFilePath@PolicyModel@@UEAA@XZ; PolicyModel::CFilePath::~CFilePath(void)
0x14001429c  add     rsp, 20h
0x1400142a0  pop     rbp
0x1400142a1  retn
```
