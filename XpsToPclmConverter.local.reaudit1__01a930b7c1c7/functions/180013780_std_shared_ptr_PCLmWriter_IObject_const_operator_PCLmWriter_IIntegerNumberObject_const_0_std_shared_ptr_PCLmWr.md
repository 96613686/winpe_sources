# std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)

- ea: `0x180013780`
- end: `0x1800137bb`
- name: `??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z`
- size: `59`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180014a14`
- `0x1800152f4`
- `0x1800159d0`
- `0x180015bf0`
- `0x180016da4`

## callees

- `0x1800101cc`
- `0x180013780`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v4 = a2[1];
  *a1 = *a2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x180013780  push    rbx
0x180013782  sub     rsp, 20h
0x180013786  mov     rax, [rdx+8]
0x18001378a  mov     rbx, rcx
0x18001378d  test    rax, rax
0x180013790  jz      short loc_180013796
0x180013792  lock inc dword ptr [rax+8]
0x180013796  mov     rax, [rdx]
0x180013799  mov     r8, [rdx+8]
0x18001379d  mov     [rcx], rax
0x1800137a0  mov     rcx, [rcx+8]; this
0x1800137a4  mov     [rbx+8], r8
0x1800137a8  test    rcx, rcx
0x1800137ab  jz      short loc_1800137B2
0x1800137ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800137b2  mov     rax, rbx
0x1800137b5  add     rsp, 20h
0x1800137b9  pop     rbx
0x1800137ba  retn
```
