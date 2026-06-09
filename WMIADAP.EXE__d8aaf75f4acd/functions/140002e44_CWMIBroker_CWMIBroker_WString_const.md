# CWMIBroker::CWMIBroker(WString const &)

- ea: `0x140002e44`
- end: `0x140002e76`
- name: `??0CWMIBroker@@QEAA@AEBVWString@@@Z`
- size: `50`
- prototype: `CWMIBroker *__fastcall(CWMIBroker *__hidden this, const struct WString *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003320`
- `0x1400037f0`

## import_xrefs

- `wbemcomn!??4WString@@QEAAAEAV0@AEBV0@@Z` at `0x140002e66`
- `wbemcomn!??4WString@@QEAAAEAV0@AEBV0@@Z` at `0x140002e66`

## pseudocode

```c
CWMIBroker *__fastcall CWMIBroker::CWMIBroker(CWMIBroker *this, const struct WString *a2)
{
  _QWORD *v3; // rcx

  *(_QWORD *)this = &CWMIBroker::`vftable';
  v3 = (_QWORD *)((char *)this + 8);
  *v3 = 0;
  WString::operator=(v3, a2);
  return this;
}

```

## disassembly

```asm
0x140002e44  mov     [rsp+arg_0], rcx
0x140002e49  push    rbx
0x140002e4a  sub     rsp, 20h
0x140002e4e  mov     rbx, rcx
0x140002e51  lea     rax, ??_7CWMIBroker@@6B@; const CWMIBroker::`vftable'
0x140002e58  mov     [rcx], rax
0x140002e5b  add     rcx, 8
0x140002e5f  mov     qword ptr [rcx], 0
0x140002e66  call    cs:__imp_??4WString@@QEAAAEAV0@AEBV0@@Z; WString::operator=(WString const &)
0x140002e6c  nop
0x140002e6d  mov     rax, rbx
0x140002e70  add     rsp, 20h
0x140002e74  pop     rbx
0x140002e75  retn
```
