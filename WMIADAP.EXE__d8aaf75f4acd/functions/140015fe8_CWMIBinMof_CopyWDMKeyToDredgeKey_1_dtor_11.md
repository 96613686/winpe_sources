# _CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$11

- ea: `0x140015fe8`
- end: `0x140016011`
- name: `_CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$11`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140015fe8`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~2u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(a2 + 136);
  }
  return result;
}

```

## disassembly

```asm
0x140015fe8  push    rbp
0x140015fea  sub     rsp, 20h
0x140015fee  mov     rbp, rdx
0x140015ff1  mov     eax, [rbp+40h]
0x140015ff4  and     eax, 2
0x140015ff7  test    eax, eax
0x140015ff9  jz      short loc_14001600B
0x140015ffb  and     dword ptr [rbp+40h], 0FFFFFFFDh
0x140015fff  lea     rcx, [rbp+88h]
0x140016006  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x14001600b  add     rsp, 20h
0x14001600f  pop     rbp
0x140016010  retn
```
