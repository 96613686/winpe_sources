# UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)

- ea: `0x1800047a8`
- end: `0x1800047f9`
- name: `??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z`
- size: `81`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000541c`
- `0x180006838`
- `0x18000940c`
- `0x180009838`
- `0x18000a090`
- `0x18000ae40`
- `0x18000c23c`
- `0x18000cbc4`
- `0x18000f3bc`
- `0x18000f800`
- `0x18000f930`
- `0x18000ffc8`
- `0x1800131d0`
- `0x180013590`
- `0x1800177bc`

## callees

- `0x1800047a8`
- `0x180006744`

## import_xrefs

- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800047d9`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800047d9`

## pseudocode

```c
_QWORD *__fastcall UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(_QWORD *a1, __int64 a2)
{
  _QWORD *result; // rax

  a1[1] = 0;
  *a1 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  if ( a2 )
    UnBCL::Object::AddRef((UnBCL::Object *)(a2 + *(int *)(*(_QWORD *)a2 + 4LL)));
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(a1);
  result = a1;
  a1[1] = a2;
  return result;
}

```

## disassembly

```asm
0x1800047a8  mov     [rsp+arg_0], rbx
0x1800047ad  push    rdi
0x1800047ae  sub     rsp, 20h
0x1800047b2  mov     qword ptr [rcx+8], 0
0x1800047ba  lea     rax, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x1800047c1  mov     [rcx], rax
0x1800047c4  mov     rdi, rdx
0x1800047c7  mov     rbx, rcx
0x1800047ca  test    rdx, rdx
0x1800047cd  jz      short loc_1800047DF
0x1800047cf  mov     rax, [rdx]
0x1800047d2  movsxd  rcx, dword ptr [rax+4]
0x1800047d6  add     rcx, rdx
0x1800047d9  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x1800047df  mov     rcx, rbx
0x1800047e2  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x1800047e7  mov     rax, rbx
0x1800047ea  mov     [rbx+8], rdi
0x1800047ee  mov     rbx, [rsp+28h+arg_0]
0x1800047f3  add     rsp, 20h
0x1800047f7  pop     rdi
0x1800047f8  retn
```
