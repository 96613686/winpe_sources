# UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(void)

- ea: `0x1800150a4`
- end: `0x1800150f1`
- name: `??1?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@UEAA@XZ`
- size: `77`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015200`
- `0x180015278`
- `0x18001577c`
- `0x180016cc4`
- `0x18003491c`
- `0x180034966`
- `0x1800349b2`
- `0x1800349d6`
- `0x180034a0c`
- `0x180034f5b`
- `0x180034fb7`

## callees

- `0x1800150a4`
- `0x180036010`

## import_xrefs

- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1800150c0`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1800150c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(_QWORD *a1)
{
  void **v2; // rax
  UnBCL::Object *v3; // rcx
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rcx

  v2 = &UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable';
  *a1 = &UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable';
  v3 = (UnBCL::Object *)a1[1];
  if ( v3 )
  {
    LODWORD(v2) = UnBCL::Object::DecRef(v3);
    if ( (_DWORD)v2 )
    {
      v4 = (__int64 (__fastcall ***)(_QWORD, __int64))a1[1];
      if ( v4 )
        LODWORD(v2) = (**v4)(v4, 1);
    }
    a1[1] = 0;
  }
  return (int)v2;
}

```

## disassembly

```asm
0x1800150a4  push    rbx
0x1800150a6  sub     rsp, 20h
0x1800150aa  mov     rbx, rcx
0x1800150ad  lea     rax, ??_7?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable'
0x1800150b4  mov     [rcx], rax
0x1800150b7  mov     rcx, [rcx+8]
0x1800150bb  test    rcx, rcx
0x1800150be  jz      short loc_1800150EB
0x1800150c0  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x1800150c6  test    eax, eax
0x1800150c8  jz      short loc_1800150E3
0x1800150ca  mov     rcx, [rbx+8]
0x1800150ce  test    rcx, rcx
0x1800150d1  jz      short loc_1800150E3
0x1800150d3  mov     rax, [rcx]
0x1800150d6  mov     edx, 1
0x1800150db  mov     rax, [rax]
0x1800150de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150e3  mov     qword ptr [rbx+8], 0
0x1800150eb  add     rsp, 20h
0x1800150ef  pop     rbx
0x1800150f0  retn
```
