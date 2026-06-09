# std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)

- ea: `0x18001496c`
- end: `0x1800149a9`
- name: `??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180014a14`
- `0x180015de4`
- `0x180016da4`
- `0x180018aa0`
- `0x180018fb0`
- `0x1800199e0`
- `0x18001a854`

## callees

- `0x1800101cc`
- `0x18001496c`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<PCLmWriter::IByteStream>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = *a2;
  v4 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *a1 = v2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x18001496c  push    rbx
0x18001496e  sub     rsp, 20h
0x180014972  mov     rax, [rdx]
0x180014975  mov     rbx, rcx
0x180014978  mov     r8, [rdx+8]
0x18001497c  mov     qword ptr [rdx], 0
0x180014983  mov     qword ptr [rdx+8], 0
0x18001498b  mov     [rcx], rax
0x18001498e  mov     rcx, [rcx+8]; this
0x180014992  mov     [rbx+8], r8
0x180014996  test    rcx, rcx
0x180014999  jz      short loc_1800149A0
0x18001499b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800149a0  mov     rax, rbx
0x1800149a3  add     rsp, 20h
0x1800149a7  pop     rbx
0x1800149a8  retn
```
