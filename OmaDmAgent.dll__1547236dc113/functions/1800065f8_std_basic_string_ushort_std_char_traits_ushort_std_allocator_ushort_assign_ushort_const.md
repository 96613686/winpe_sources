# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x1800065f8`
- end: `0x180006619`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `33`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a50`
- `0x1800075b0`
- `0x1800078f4`
- `0x180007b5c`
- `0x180007edc`
- `0x1800083fc`
- `0x18000e524`
- `0x18000e980`
- `0x18000ea88`
- `0x18000f704`
- `0x18000f7d4`
- `0x18000f924`
- `0x18000fe4c`
- `0x1800100a4`
- `0x180010eac`
- `0x180013330`
- `0x180013e10`
- `0x1800155e4`
- `0x180015a2c`
- `0x180015c2c`
- `0x1800184e4`
- `0x180018cf4`
- `0x180019a88`
- `0x180019f78`
- `0x18001a2c8`
- `0x18001a4f8`
- `0x18001d2a0`
- `0x18001da10`
- `0x18001e24c`

## callees

- `0x180006620`
- `0x180006998`

## pseudocode

```c
__int64 __fastcall std::wstring::assign(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r10

  v2 = std::char_traits<unsigned short>::length(a2);
  return std::wstring::assign(v4, v3, v2);
}

```

## disassembly

```asm
0x1800065f8  sub     rsp, 28h
0x1800065fc  mov     r10, rcx
0x1800065ff  mov     rcx, rdx
0x180006602  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180006607  mov     rdx, rcx
0x18000660a  mov     r8, rax
0x18000660d  mov     rcx, r10
0x180006610  add     rsp, 28h
0x180006614  jmp     ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
```
