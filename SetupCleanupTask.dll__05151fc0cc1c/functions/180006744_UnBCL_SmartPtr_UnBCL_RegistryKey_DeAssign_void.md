# UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)

- ea: `0x180006744`
- end: `0x18000679b`
- name: `?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ`
- size: `87`
- prototype: `void __fastcall(__int64)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800047a8`
- `0x180004c18`
- `0x180004c84`
- `0x180004f20`
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

- `0x180006744`
- `0x180036010`

## import_xrefs

- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180006760`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180006760`

## pseudocode

```c
void __fastcall UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rdx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( UnBCL::Object::DecRef((UnBCL::Object *)(v1 + *(int *)(*(_QWORD *)v1 + 4LL))) )
    {
      v3 = *(_QWORD *)(a1 + 8);
      if ( v3 )
      {
        v4 = (void (__fastcall ***)(_QWORD, __int64))(v3 + *(int *)(*(_QWORD *)v3 + 4LL));
        (**v4)(v4, 1);
      }
    }
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180006744  push    rbx
0x180006746  sub     rsp, 20h
0x18000674a  mov     rdx, [rcx+8]
0x18000674e  mov     rbx, rcx
0x180006751  test    rdx, rdx
0x180006754  jz      short loc_180006795
0x180006756  mov     rax, [rdx]
0x180006759  movsxd  rcx, dword ptr [rax+4]
0x18000675d  add     rcx, rdx
0x180006760  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180006766  test    eax, eax
0x180006768  jz      short loc_18000678D
0x18000676a  mov     rdx, [rbx+8]
0x18000676e  test    rdx, rdx
0x180006771  jz      short loc_18000678D
0x180006773  mov     rax, [rdx]
0x180006776  movsxd  rcx, dword ptr [rax+4]
0x18000677a  add     rcx, rdx
0x18000677d  mov     edx, 1
0x180006782  mov     rax, [rcx]
0x180006785  mov     rax, [rax]
0x180006788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678d  mov     qword ptr [rbx+8], 0
0x180006795  add     rsp, 20h
0x180006799  pop     rbx
0x18000679a  retn
```
