# PCLmWriter::Exception::Exception(PCLmWriter::Exception const &)

- ea: `0x1800115a4`
- end: `0x1800115f7`
- name: `??0Exception@PCLmWriter@@QEAA@AEBV01@@Z`
- size: `83`
- prototype: `__int64 __fastcall(PCLmWriter::Exception *__hidden this, const struct PCLmWriter::Exception *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180014738`
- `0x1800183b0`
- `0x180018928`

## callees

- `0x1800083e0`
- `0x18000f398`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter::Exception *__fastcall PCLmWriter::Exception::Exception(
        PCLmWriter::Exception *this,
        const struct PCLmWriter::Exception *a2)
{
  std::exception::exception(this, a2);
  *(_QWORD *)this = &PCLmWriter::Exception::`vftable';
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  *((_BYTE *)this + 28) = *((_BYTE *)a2 + 28);
  *((_BYTE *)this + 29) = *((_BYTE *)a2 + 29);
  std::string::string((char *)this + 32);
  return this;
}

```

## disassembly

```asm
0x1800115a4  mov     [rsp+arg_8], rbx
0x1800115a9  mov     [rsp+arg_0], rcx
0x1800115ae  push    rdi
0x1800115af  sub     rsp, 20h
0x1800115b3  mov     rbx, rdx
0x1800115b6  mov     rdi, rcx
0x1800115b9  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800115be  nop
0x1800115bf  lea     rax, ??_7Exception@PCLmWriter@@6B@; const PCLmWriter::Exception::`vftable'
0x1800115c6  mov     [rdi], rax
0x1800115c9  mov     eax, [rbx+18h]
0x1800115cc  mov     [rdi+18h], eax
0x1800115cf  mov     al, [rbx+1Ch]
0x1800115d2  mov     [rdi+1Ch], al
0x1800115d5  mov     al, [rbx+1Dh]
0x1800115d8  mov     [rdi+1Dh], al
0x1800115db  lea     rdx, [rbx+20h]
0x1800115df  lea     rcx, [rdi+20h]
0x1800115e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800115e8  nop
0x1800115e9  mov     rax, rdi
0x1800115ec  mov     rbx, [rsp+28h+arg_8]
0x1800115f1  add     rsp, 20h
0x1800115f5  pop     rdi
0x1800115f6  retn
```
