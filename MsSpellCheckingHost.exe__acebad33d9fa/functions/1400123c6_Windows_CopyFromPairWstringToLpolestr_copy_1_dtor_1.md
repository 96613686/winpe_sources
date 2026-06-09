# _Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$1

- ea: `0x1400123c6`
- end: `0x1400123ec`
- name: `_Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$1`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400087c4`
- `0x1400123c6`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(a2 + 72);
  }
  return result;
}

```

## disassembly

```asm
0x1400123c6  push    rbp
0x1400123c8  sub     rsp, 20h
0x1400123cc  mov     rbp, rdx
0x1400123cf  mov     eax, [rbp+20h]
0x1400123d2  and     eax, 1
0x1400123d5  test    eax, eax
0x1400123d7  jz      short loc_1400123E6
0x1400123d9  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x1400123dd  lea     rcx, [rbp+48h]
0x1400123e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400123e6  add     rsp, 20h
0x1400123ea  pop     rbp
0x1400123eb  retn
```
