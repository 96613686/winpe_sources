# std::_Construct_in_place<PCLmWriter::ArrayObject,std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>> const &,uint &,uint &>(PCLmWriter::ArrayObject &,std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>> const &,uint &,uint &)

- ea: `0x180010984`
- end: `0x1800109ee`
- name: `??$_Construct_in_place@VArrayObject@PCLmWriter@@AEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAIAEAI@std@@YAXAEAVArrayObject@PCLmWriter@@AEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@0@AEAI2@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012420`

## callees

- `0x1800106c8`
- `0x1800114fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Construct_in_place<PCLmWriter::ArrayObject,std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &,unsigned int &,unsigned int &>(
        __int64 a1,
        __int64 a2,
        int *a3,
        int *a4)
{
  int v5; // edi
  int v6; // ebx
  _BYTE v8[56]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v9; // [rsp+70h] [rbp+18h]

  v5 = *a4;
  v6 = *a3;
  v9 = (_QWORD *)std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v8);
  *(_DWORD *)(a1 + 8) = v6;
  *(_DWORD *)(a1 + 12) = v5;
  *(_DWORD *)(a1 + 16) = 4;
  *(_QWORD *)a1 = &PCLmWriter::ArrayObject::`vftable';
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(a1 + 24);
  return std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(v9);
}

```

## disassembly

```asm
0x180010984  mov     [rsp+arg_8], rbx
0x180010989  push    rsi
0x18001098a  push    rdi
0x18001098b  push    r14
0x18001098d  sub     rsp, 40h
0x180010991  mov     r14, rcx
0x180010994  mov     [rsp+58h+arg_0], rcx
0x180010999  mov     edi, [r9]
0x18001099c  mov     ebx, [r8]
0x18001099f  lea     rcx, [rsp+58h+var_38]
0x1800109a4  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &)
0x1800109a9  mov     rsi, rax
0x1800109ac  mov     [rsp+58h+arg_10], rax
0x1800109b1  mov     [r14+8], ebx
0x1800109b5  mov     [r14+0Ch], edi
0x1800109b9  mov     dword ptr [r14+10h], 4
0x1800109c1  lea     rax, ??_7ArrayObject@PCLmWriter@@6B@; const PCLmWriter::ArrayObject::`vftable'
0x1800109c8  mov     [r14], rax
0x1800109cb  lea     rcx, [r14+18h]
0x1800109cf  mov     rdx, rsi
0x1800109d2  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &)
0x1800109d7  nop
0x1800109d8  mov     rcx, rsi
0x1800109db  call    ?_Tidy@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(void)
0x1800109e0  mov     rbx, [rsp+58h+arg_8]
0x1800109e5  add     rsp, 40h
0x1800109e9  pop     r14
0x1800109eb  pop     rdi
0x1800109ec  pop     rsi
0x1800109ed  retn
```
