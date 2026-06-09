# _Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$3

- ea: `0x14001241e`
- end: `0x140012447`
- name: `_Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$3`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400087c4`
- `0x14001241e`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 4;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~4u;
    return std::wstring::~wstring(a2 + 136);
  }
  return result;
}

```

## disassembly

```asm
0x14001241e  push    rbp
0x140012420  sub     rsp, 20h
0x140012424  mov     rbp, rdx
0x140012427  mov     eax, [rbp+20h]
0x14001242a  and     eax, 4
0x14001242d  test    eax, eax
0x14001242f  jz      short loc_140012441
0x140012431  and     dword ptr [rbp+20h], 0FFFFFFFBh
0x140012435  lea     rcx, [rbp+88h]
0x14001243c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012441  add     rsp, 20h
0x140012445  pop     rbp
0x140012446  retn
```
