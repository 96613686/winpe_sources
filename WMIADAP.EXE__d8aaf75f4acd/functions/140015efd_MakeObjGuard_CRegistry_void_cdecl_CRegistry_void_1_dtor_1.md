# _MakeObjGuard_CRegistry_void_(__cdecl_CRegistry::_)(void)__::_1_::dtor$1

- ea: `0x140015efd`
- end: `0x140015f23`
- name: `_MakeObjGuard_CRegistry_void_(__cdecl_CRegistry::_)(void)__::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f870`
- `0x140015efd`

## pseudocode

```c
__int64 __fastcall MakeObjGuard_CRegistry_void____cdecl_CRegistry::___void___::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)a2 & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)a2 &= ~2u;
    return ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(*(_QWORD *)(a2 + 32));
  }
  return result;
}

```

## disassembly

```asm
0x140015efd  push    rbp
0x140015eff  sub     rsp, 20h
0x140015f03  mov     rbp, rdx
0x140015f06  mov     eax, [rbp+0]
0x140015f09  and     eax, 2
0x140015f0c  test    eax, eax
0x140015f0e  jz      short loc_140015F1D
0x140015f10  and     dword ptr [rbp+0], 0FFFFFFFDh
0x140015f14  mov     rcx, [rbp+20h]
0x140015f18  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x140015f1d  add     rsp, 20h
0x140015f21  pop     rbp
0x140015f22  retn
```
