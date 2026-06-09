# _CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$15

- ea: `0x140016043`
- end: `0x140016069`
- name: `_CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$15`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140016043`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 0x20;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x20u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(a2 + 112);
  }
  return result;
}

```

## disassembly

```asm
0x140016043  push    rbp
0x140016045  sub     rsp, 20h
0x140016049  mov     rbp, rdx
0x14001604c  mov     eax, [rbp+40h]
0x14001604f  and     eax, 20h
0x140016052  test    eax, eax
0x140016054  jz      short loc_140016063
0x140016056  and     dword ptr [rbp+40h], 0FFFFFFDFh
0x14001605a  lea     rcx, [rbp+70h]
0x14001605e  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x140016063  add     rsp, 20h
0x140016067  pop     rbp
0x140016068  retn
```
