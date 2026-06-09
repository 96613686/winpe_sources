# std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)

- ea: `0x18000f8d4`
- end: `0x18000f91b`
- name: `??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z`
- size: `71`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fe14`
- `0x180014a14`
- `0x1800152f4`
- `0x180015b6c`
- `0x180016580`
- `0x180018dc0`
- `0x1800199e0`

## callees

- `0x18000e7c8`
- `0x18000f8d4`
- `0x1800101cc`

## pseudocode

```c
__int64 *__fastcall std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r8
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v8, a2);
  v4 = *v3;
  *v3 = *a1;
  *a1 = v4;
  v5 = v3[1];
  v3[1] = a1[1];
  v6 = v8[1];
  a1[1] = v5;
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return a1;
}

```

## disassembly

```asm
0x18000f8d4  push    rbx
0x18000f8d6  sub     rsp, 30h
0x18000f8da  mov     rbx, rcx
0x18000f8dd  lea     rcx, [rsp+38h+var_18]
0x18000f8e2  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18000f8e7  mov     rdx, [rbx]
0x18000f8ea  mov     r8, [rax]
0x18000f8ed  mov     [rax], rdx
0x18000f8f0  mov     [rbx], r8
0x18000f8f3  mov     rdx, [rbx+8]
0x18000f8f7  mov     r8, [rax+8]
0x18000f8fb  mov     [rax+8], rdx
0x18000f8ff  mov     rcx, [rsp+38h+var_10]; this
0x18000f904  mov     [rbx+8], r8
0x18000f908  test    rcx, rcx
0x18000f90b  jz      short loc_18000F912
0x18000f90d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f912  mov     rax, rbx
0x18000f915  add     rsp, 30h
0x18000f919  pop     rbx
0x18000f91a  retn
```
