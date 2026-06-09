# _ConvertArrayToPaths_::_1_::dtor$5

- ea: `0x1400114cc`
- end: `0x1400114f5`
- name: `_ConvertArrayToPaths_::_1_::dtor$5`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000a1bc`
- `0x1400114cc`

## pseudocode

```c
__int64 __fastcall ConvertArrayToPaths_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::vector<unsigned short>::~vector<unsigned short>(*(_QWORD *)(a2 + 144));
  }
  return result;
}

```

## disassembly

```asm
0x1400114cc  push    rbp
0x1400114ce  sub     rsp, 20h
0x1400114d2  mov     rbp, rdx
0x1400114d5  mov     eax, [rbp+20h]
0x1400114d8  and     eax, 1
0x1400114db  test    eax, eax
0x1400114dd  jz      short loc_1400114EF
0x1400114df  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x1400114e3  mov     rcx, [rbp+90h]
0x1400114ea  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1400114ef  add     rsp, 20h
0x1400114f3  pop     rbp
0x1400114f4  retn
```
