# UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(UnBCL::SmartPtr<UnBCL::RegistryKey> const &)

- ea: `0x180004c84`
- end: `0x180004cc4`
- name: `??4?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z`
- size: `64`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000541c`
- `0x18000ae40`
- `0x1800131d0`
- `0x180013590`

## callees

- `0x180004c84`
- `0x180006744`

## import_xrefs

- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180004ca4`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180004ca4`

## pseudocode

```c
__int64 __fastcall UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 8);
  if ( v2 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v2 + *(int *)(*(_QWORD *)v2 + 4LL)));
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(a1);
  *(_QWORD *)(a1 + 8) = v2;
  return a1;
}

```

## disassembly

```asm
0x180004c84  mov     [rsp+arg_0], rbx
0x180004c89  push    rdi
0x180004c8a  sub     rsp, 20h
0x180004c8e  mov     rbx, [rdx+8]
0x180004c92  mov     rdi, rcx
0x180004c95  test    rbx, rbx
0x180004c98  jz      short loc_180004CAA
0x180004c9a  mov     rax, [rbx]
0x180004c9d  movsxd  rcx, dword ptr [rax+4]
0x180004ca1  add     rcx, rbx
0x180004ca4  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180004caa  mov     rcx, rdi
0x180004cad  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180004cb2  mov     [rdi+8], rbx
0x180004cb6  mov     rax, rdi
0x180004cb9  mov     rbx, [rsp+28h+arg_0]
0x180004cbe  add     rsp, 20h
0x180004cc2  pop     rdi
0x180004cc3  retn
```
