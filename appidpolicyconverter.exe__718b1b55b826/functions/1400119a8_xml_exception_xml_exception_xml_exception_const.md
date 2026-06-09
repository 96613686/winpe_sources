# xml_exception::xml_exception(xml_exception const &)

- ea: `0x1400119a8`
- end: `0x1400119ce`
- name: `??0xml_exception@@QEAA@AEBV0@@Z`
- size: `38`
- prototype: `xml_exception *__fastcall(xml_exception *__hidden this, const struct xml_exception *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140009cb4`

## pseudocode

```c
xml_exception *__fastcall xml_exception::xml_exception(xml_exception *this, const struct xml_exception *a2)
{
  Sharp::Util::standard_exception::standard_exception(this, a2);
  *(_QWORD *)this = &xml_exception::`vftable';
  return this;
}

```

## disassembly

```asm
0x1400119a8  mov     [rsp+arg_0], rcx
0x1400119ad  push    rbx
0x1400119ae  sub     rsp, 20h
0x1400119b2  mov     rbx, rcx
0x1400119b5  call    ??0standard_exception@Util@Sharp@@QEAA@AEBV012@@Z; Sharp::Util::standard_exception::standard_exception(Sharp::Util::standard_exception const &)
0x1400119ba  nop
0x1400119bb  lea     rax, ??_7xml_exception@@6B@; const xml_exception::`vftable'
0x1400119c2  mov     [rbx], rax
0x1400119c5  mov     rax, rbx
0x1400119c8  add     rsp, 20h
0x1400119cc  pop     rbx
0x1400119cd  retn
```
