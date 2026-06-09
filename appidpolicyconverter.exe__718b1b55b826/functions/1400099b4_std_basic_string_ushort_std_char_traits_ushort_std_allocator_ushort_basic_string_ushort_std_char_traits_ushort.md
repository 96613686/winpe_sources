# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x1400099b4`
- end: `0x1400099dc`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `41`
- callee_count: `1`
- tags: ``

## callers

- `0x140009520`
- `0x140009c34`
- `0x14000a560`
- `0x14000ac40`
- `0x14000af60`
- `0x14000bd68`
- `0x14000bee4`
- `0x14000c138`
- `0x14000c308`
- `0x14000c938`
- `0x14000cba0`
- `0x14000cd80`
- `0x14000cdf0`
- `0x14000cf50`
- `0x14000d930`
- `0x14000da10`
- `0x14000dc30`
- `0x14000dcf0`
- `0x14000dd60`
- `0x14000e340`
- `0x14000e480`
- `0x14000e5e0`
- `0x14000ec60`
- `0x14000ed80`
- `0x14000eea0`
- `0x14000f200`
- `0x14000f3e0`
- `0x14000f44c`
- `0x14000f514`
- `0x14000f610`
- `0x14000ffb8`
- `0x14001036c`
- `0x140010c78`
- `0x140010d90`
- `0x140011020`
- `0x140011240`
- `0x1400114e0`
- `0x1400117c4`
- `0x1400119d4`
- `0x140012d2c`
- `0x140013338`

## callees

- `0x140008498`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1)
{
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign();
  return a1;
}

```

## disassembly

```asm
0x1400099b4  push    rbx
0x1400099b6  sub     rsp, 20h
0x1400099ba  xor     eax, eax
0x1400099bc  mov     qword ptr [rcx+18h], 7
0x1400099c4  mov     [rcx+10h], rax
0x1400099c8  mov     rbx, rcx
0x1400099cb  mov     [rcx], ax
0x1400099ce  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1400099d3  mov     rax, rbx
0x1400099d6  add     rsp, 20h
0x1400099da  pop     rbx
0x1400099db  retn
```
