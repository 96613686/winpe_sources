# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000702c`
- end: `0x18000705c`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `48`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a8c8`
- `0x18000a970`
- `0x18000b51c`
- `0x18000b5dc`
- `0x18000b6f4`
- `0x18000b7d8`
- `0x18000be18`
- `0x18000bfd4`
- `0x18000c354`
- `0x18000c734`
- `0x18000cb4c`
- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000da10`
- `0x18000dcb4`
- `0x18000e524`
- `0x18000ea88`
- `0x18000fe4c`
- `0x1800100a4`
- `0x1800102b8`
- `0x180010700`
- `0x180010eac`
- `0x1800110c0`
- `0x180011160`
- `0x180011398`
- `0x180011574`
- `0x18001180c`
- `0x180011a44`
- `0x180011bfc`
- `0x180011e54`
- `0x180012050`
- `0x180012338`
- `0x180013234`
- `0x180013330`
- `0x180013ce4`
- `0x180013e10`
- `0x180014680`
- `0x180017b58`
- `0x1800182b4`
- `0x1800187f4`
- `0x180018a44`
- `0x180019d2c`
- `0x18001a040`
- `0x18001a380`
- `0x18001a3d8`
- `0x18001a4f8`
- `0x18001b6bc`
- `0x18001b9d4`
- `0x18001bcd4`
- `0x18001bfcc`

## callees

- `0x180006530`

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
0x18000702c  push    rbx
0x18000702e  sub     rsp, 20h
0x180007032  xor     eax, eax
0x180007034  mov     qword ptr [rcx+18h], 7
0x18000703c  mov     [rcx+10h], rax
0x180007040  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007044  xor     r8d, r8d
0x180007047  mov     [rcx], ax
0x18000704a  mov     rbx, rcx
0x18000704d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007052  mov     rax, rbx
0x180007055  add     rsp, 20h
0x180007059  pop     rbx
0x18000705a  retn
```
