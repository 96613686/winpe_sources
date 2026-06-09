# _CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$10

- ea: `0x140015fb9`
- end: `0x140015fe2`
- name: `_CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$10`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140015fb9`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(a2 + 136);
  }
  return result;
}

```

## disassembly

```asm
0x140015fb9  push    rbp
0x140015fbb  sub     rsp, 20h
0x140015fbf  mov     rbp, rdx
0x140015fc2  mov     eax, [rbp+40h]
0x140015fc5  and     eax, 1
0x140015fc8  test    eax, eax
0x140015fca  jz      short loc_140015FDC
0x140015fcc  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x140015fd0  lea     rcx, [rbp+88h]
0x140015fd7  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x140015fdc  add     rsp, 20h
0x140015fe0  pop     rbp
0x140015fe1  retn
```
