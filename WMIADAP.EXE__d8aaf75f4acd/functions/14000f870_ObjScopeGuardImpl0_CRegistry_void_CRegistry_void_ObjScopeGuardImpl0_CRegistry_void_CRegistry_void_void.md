# ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)

- ea: `0x14000f870`
- end: `0x14000f88f`
- name: `??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f91c`
- `0x140015ed1`
- `0x140015efd`
- `0x140015f4d`
- `0x140015fb9`
- `0x140015fe8`
- `0x140016017`
- `0x140016043`

## callees

- `0x14000f870`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(
        __int64 a1)
{
  __int64 result; // rax

  result = a1;
  if ( !*(_BYTE *)a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 8));
  return result;
}

```

## disassembly

```asm
0x14000f870  sub     rsp, 28h
0x14000f874  mov     rax, rcx
0x14000f877  cmp     byte ptr [rcx], 0
0x14000f87a  jnz     short loc_14000F88A
0x14000f87c  mov     rcx, [rcx+8]
0x14000f880  mov     rax, [rax+10h]
0x14000f884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f889  nop
0x14000f88a  add     rsp, 28h
0x14000f88e  retn
```
