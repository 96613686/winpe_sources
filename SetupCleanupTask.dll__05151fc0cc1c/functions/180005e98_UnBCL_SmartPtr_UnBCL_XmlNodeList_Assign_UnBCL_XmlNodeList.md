# UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)

- ea: `0x180005e98`
- end: `0x180005ef1`
- name: `?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z`
- size: `89`
- prototype: `void __fastcall(__int64, UnBCL::Object *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004778`
- `0x18000940c`
- `0x18000f3bc`
- `0x180015278`
- `0x18001577c`
- `0x180016cc4`

## callees

- `0x180005e98`
- `0x180036010`

## import_xrefs

- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180005eb0`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180005eb0`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180005ebf`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180005ebf`

## pseudocode

```c
void __fastcall UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(__int64 a1, UnBCL::Object *a2)
{
  UnBCL::Object *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx

  if ( a2 )
    UnBCL::Object::AddRef(a2);
  v4 = *(UnBCL::Object **)(a1 + 8);
  if ( v4 )
  {
    if ( UnBCL::Object::DecRef(v4) )
    {
      v5 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 8);
      if ( v5 )
        (**v5)(v5, 1);
    }
  }
  *(_QWORD *)(a1 + 8) = a2;
}

```

## disassembly

```asm
0x180005e98  mov     [rsp+arg_0], rbx
0x180005e9d  push    rdi
0x180005e9e  sub     rsp, 20h
0x180005ea2  mov     rdi, rdx
0x180005ea5  mov     rbx, rcx
0x180005ea8  test    rdx, rdx
0x180005eab  jz      short loc_180005EB6
0x180005ead  mov     rcx, rdx
0x180005eb0  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180005eb6  mov     rcx, [rbx+8]
0x180005eba  test    rcx, rcx
0x180005ebd  jz      short loc_180005EE2
0x180005ebf  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180005ec5  test    eax, eax
0x180005ec7  jz      short loc_180005EE2
0x180005ec9  mov     rcx, [rbx+8]
0x180005ecd  test    rcx, rcx
0x180005ed0  jz      short loc_180005EE2
0x180005ed2  mov     rax, [rcx]
0x180005ed5  mov     edx, 1
0x180005eda  mov     rax, [rax]
0x180005edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee2  mov     [rbx+8], rdi
0x180005ee6  mov     rbx, [rsp+28h+arg_0]
0x180005eeb  add     rsp, 20h
0x180005eef  pop     rdi
0x180005ef0  retn
```
