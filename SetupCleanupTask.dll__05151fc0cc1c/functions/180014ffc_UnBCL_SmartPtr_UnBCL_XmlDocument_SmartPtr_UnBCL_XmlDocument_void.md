# UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(void)

- ea: `0x180014ffc`
- end: `0x180015049`
- name: `??1?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@UEAA@XZ`
- size: `77`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015180`
- `0x180015278`
- `0x18001577c`
- `0x180016cc4`
- `0x18003490a`
- `0x180034954`
- `0x1800349c4`
- `0x1800349fa`

## callees

- `0x180014ffc`
- `0x180036010`

## import_xrefs

- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180015018`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180015018`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(_QWORD *a1)
{
  void **v2; // rax
  UnBCL::Object *v3; // rcx
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rcx

  v2 = &UnBCL::SmartPtr<UnBCL::XmlDocument>::`vftable';
  *a1 = &UnBCL::SmartPtr<UnBCL::XmlDocument>::`vftable';
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
0x180014ffc  push    rbx
0x180014ffe  sub     rsp, 20h
0x180015002  mov     rbx, rcx
0x180015005  lea     rax, ??_7?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlDocument>::`vftable'
0x18001500c  mov     [rcx], rax
0x18001500f  mov     rcx, [rcx+8]
0x180015013  test    rcx, rcx
0x180015016  jz      short loc_180015043
0x180015018  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x18001501e  test    eax, eax
0x180015020  jz      short loc_18001503B
0x180015022  mov     rcx, [rbx+8]
0x180015026  test    rcx, rcx
0x180015029  jz      short loc_18001503B
0x18001502b  mov     rax, [rcx]
0x18001502e  mov     edx, 1
0x180015033  mov     rax, [rax]
0x180015036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001503b  mov     qword ptr [rbx+8], 0
0x180015043  add     rsp, 20h
0x180015047  pop     rbx
0x180015048  retn
```
