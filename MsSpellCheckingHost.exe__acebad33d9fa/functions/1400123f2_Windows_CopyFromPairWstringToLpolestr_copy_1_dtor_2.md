# _Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$2

- ea: `0x1400123f2`
- end: `0x140012418`
- name: `_Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400087c4`
- `0x1400123f2`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    return std::wstring::~wstring(a2 + 104);
  }
  return result;
}

```

## disassembly

```asm
0x1400123f2  push    rbp
0x1400123f4  sub     rsp, 20h
0x1400123f8  mov     rbp, rdx
0x1400123fb  mov     eax, [rbp+20h]
0x1400123fe  and     eax, 2
0x140012401  test    eax, eax
0x140012403  jz      short loc_140012412
0x140012405  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x140012409  lea     rcx, [rbp+68h]
0x14001240d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012412  add     rsp, 20h
0x140012416  pop     rbp
0x140012417  retn
```
