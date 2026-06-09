# UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(void)

- ea: `0x180015050`
- end: `0x18001509d`
- name: `??1?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@UEAA@XZ`
- size: `77`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800151c0`
- `0x180015278`
- `0x18001577c`
- `0x180016cc4`
- `0x18003492e`
- `0x180034978`
- `0x1800349e8`
- `0x180034a1e`
- `0x180034fa5`

## callees

- `0x180015050`
- `0x180036010`

## import_xrefs

- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x18001506c`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x18001506c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(_QWORD *a1)
{
  void **v2; // rax
  UnBCL::Object *v3; // rcx
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rcx

  v2 = &UnBCL::SmartPtr<UnBCL::XmlNode>::`vftable';
  *a1 = &UnBCL::SmartPtr<UnBCL::XmlNode>::`vftable';
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
0x180015050  push    rbx
0x180015052  sub     rsp, 20h
0x180015056  mov     rbx, rcx
0x180015059  lea     rax, ??_7?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlNode>::`vftable'
0x180015060  mov     [rcx], rax
0x180015063  mov     rcx, [rcx+8]
0x180015067  test    rcx, rcx
0x18001506a  jz      short loc_180015097
0x18001506c  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180015072  test    eax, eax
0x180015074  jz      short loc_18001508F
0x180015076  mov     rcx, [rbx+8]
0x18001507a  test    rcx, rcx
0x18001507d  jz      short loc_18001508F
0x18001507f  mov     rax, [rcx]
0x180015082  mov     edx, 1
0x180015087  mov     rax, [rax]
0x18001508a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001508f  mov     qword ptr [rbx+8], 0
0x180015097  add     rsp, 20h
0x18001509b  pop     rbx
0x18001509c  retn
```
