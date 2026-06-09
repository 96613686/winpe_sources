# _MakeObjGuard_CRegistry_void_(__cdecl_CRegistry::_)(void)__::_1_::dtor$0

- ea: `0x140015ed1`
- end: `0x140015ef7`
- name: `_MakeObjGuard_CRegistry_void_(__cdecl_CRegistry::_)(void)__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140015ed1`

## pseudocode

```c
__int64 __fastcall MakeObjGuard_CRegistry_void____cdecl_CRegistry::___void___::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)a2 & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)a2 &= ~1u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(*(_QWORD *)(a2 + 32));
  }
  return result;
}

```

## disassembly

```asm
0x140015ed1  push    rbp
0x140015ed3  sub     rsp, 20h
0x140015ed7  mov     rbp, rdx
0x140015eda  mov     eax, [rbp+0]
0x140015edd  and     eax, 1
0x140015ee0  test    eax, eax
0x140015ee2  jz      short loc_140015EF1
0x140015ee4  and     dword ptr [rbp+0], 0FFFFFFFEh
0x140015ee8  mov     rcx, [rbp+20h]
0x140015eec  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x140015ef1  add     rsp, 20h
0x140015ef5  pop     rbp
0x140015ef6  retn
```
