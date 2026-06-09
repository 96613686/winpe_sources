# _PolicyModel::CRule::FromXml_::_1_::dtor$3

- ea: `0x140014551`
- end: `0x140014577`
- name: `_PolicyModel::CRule::FromXml_::_1_::dtor$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e1c`
- `0x140014551`

## pseudocode

```c
__int64 __fastcall PolicyModel::CRule::FromXml_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return Sharp::Util::CSharedPtr<PolicyModel::CFileHash>::~CSharedPtr<PolicyModel::CFileHash>(*(Sharp::Util::CRefCount ***)(a2 + 104));
  }
  return result;
}

```

## disassembly

```asm
0x140014551  push    rbp
0x140014553  sub     rsp, 20h
0x140014557  mov     rbp, rdx
0x14001455a  mov     eax, [rbp+30h]
0x14001455d  and     eax, 1
0x140014560  test    eax, eax
0x140014562  jz      short loc_140014571
0x140014564  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140014568  mov     rcx, [rbp+68h]
0x14001456c  call    ??1?$CSharedPtr@VCFileHash@PolicyModel@@@Util@Sharp@@QEAA@XZ; Sharp::Util::CSharedPtr<PolicyModel::CFileHash>::~CSharedPtr<PolicyModel::CFileHash>(void)
0x140014571  add     rsp, 20h
0x140014575  pop     rbp
0x140014576  retn
```
