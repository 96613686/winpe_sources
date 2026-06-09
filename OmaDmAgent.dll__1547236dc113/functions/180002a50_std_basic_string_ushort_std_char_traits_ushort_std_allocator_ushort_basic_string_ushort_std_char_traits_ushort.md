# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x180002a50`
- end: `0x180002a79`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `41`
- prototype: ``
- caller_count: `49`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015b0`
- `0x180004950`
- `0x180006df0`
- `0x180007110`
- `0x180007a3c`
- `0x180007b5c`
- `0x180007c00`
- `0x180007edc`
- `0x180008cec`
- `0x180009304`
- `0x18000bfd4`
- `0x18000c734`
- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000dcb4`
- `0x18000e0a8`
- `0x18000e524`
- `0x18000e980`
- `0x18000ea88`
- `0x18000fa44`
- `0x1800102b8`
- `0x180010700`
- `0x180011160`
- `0x180011398`
- `0x180011574`
- `0x18001180c`
- `0x180011a44`
- `0x180011bfc`
- `0x180011e54`
- `0x180012050`
- `0x180012338`
- `0x180013330`
- `0x180014110`
- `0x180014680`
- `0x1800155e4`
- `0x180017b58`
- `0x1800182b4`
- `0x1800187f4`
- `0x180018a44`
- `0x180018cf4`
- `0x18001ab3c`
- `0x18001b05c`
- `0x18001bfcc`
- `0x18001c3fc`
- `0x18001cb10`
- `0x18001d000`
- `0x18001d910`
- `0x18001da10`
- `0x18001e24c`

## callees

- `0x1800065f8`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x180002a50  push    rbx
0x180002a52  sub     rsp, 20h
0x180002a56  xor     eax, eax
0x180002a58  mov     qword ptr [rcx+18h], 7
0x180002a60  mov     [rcx+10h], rax
0x180002a64  mov     rbx, rcx
0x180002a67  mov     [rcx], ax
0x180002a6a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180002a6f  mov     rax, rbx
0x180002a72  add     rsp, 20h
0x180002a76  pop     rbx
0x180002a77  retn
```
