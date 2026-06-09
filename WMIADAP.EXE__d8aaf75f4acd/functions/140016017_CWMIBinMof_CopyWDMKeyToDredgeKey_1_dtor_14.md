# _CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$14

- ea: `0x140016017`
- end: `0x14001603d`
- name: `_CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$14`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140016017`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 0x10;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x10u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(a2 + 112);
  }
  return result;
}

```

## disassembly

```asm
0x140016017  push    rbp
0x140016019  sub     rsp, 20h
0x14001601d  mov     rbp, rdx
0x140016020  mov     eax, [rbp+40h]
0x140016023  and     eax, 10h
0x140016026  test    eax, eax
0x140016028  jz      short loc_140016037
0x14001602a  and     dword ptr [rbp+40h], 0FFFFFFEFh
0x14001602e  lea     rcx, [rbp+70h]
0x140016032  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x140016037  add     rsp, 20h
0x14001603b  pop     rbp
0x14001603c  retn
```
