# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000f744`
- end: `0x18000f773`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f270`
- `0x18000f3f4`
- `0x18000f454`
- `0x18000fe1c`
- `0x180011d98`
- `0x18001211c`
- `0x180012e20`
- `0x180014170`

## callees

- `0x180012644`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, a2, 0, -1);
  return a1;
}

```

## disassembly

```asm
0x18000f744  push    rbx
0x18000f746  sub     rsp, 20h
0x18000f74a  xor     eax, eax
0x18000f74c  mov     qword ptr [rcx+18h], 7
0x18000f754  mov     [rcx+10h], rax
0x18000f758  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f75c  xor     r8d, r8d
0x18000f75f  mov     [rcx], ax
0x18000f762  mov     rbx, rcx
0x18000f765  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f76a  mov     rax, rbx
0x18000f76d  add     rsp, 20h
0x18000f771  pop     rbx
0x18000f772  retn
```
