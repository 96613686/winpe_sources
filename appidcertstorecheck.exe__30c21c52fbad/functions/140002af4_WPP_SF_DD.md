# WPP_SF_DD

- ea: `0x140002af4`
- end: `0x140002b3f`
- name: `WPP_SF_DD`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400024e8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x140002b34`
- `ntdll!EtwTraceMessage` at `0x140002b34`

## pseudocode

```c
__int64 __fastcall WPP_SF_DD(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_94ebf5b9b7c531a9fa2e37c94bc8856a_Traceguids, 12, &v5);
}

```

## disassembly

```asm
0x140002af4  mov     r11, rsp
0x140002af7  mov     [r11+20h], r9d
0x140002afb  sub     rsp, 58h
0x140002aff  mov     qword ptr [r11-18h], 0
0x140002b07  lea     rax, [r11+28h]
0x140002b0b  mov     r9d, 0Ch
0x140002b11  lea     r8, WPP_94ebf5b9b7c531a9fa2e37c94bc8856a_Traceguids
0x140002b18  lea     edx, [r9-8]
0x140002b1c  mov     [r11-20h], rdx
0x140002b20  mov     [r11-28h], rax
0x140002b24  lea     rax, [r11+20h]
0x140002b28  mov     [r11-30h], rdx
0x140002b2c  lea     edx, [r9+1Fh]
0x140002b30  mov     [r11-38h], rax
0x140002b34  call    cs:__imp_EtwTraceMessage
0x140002b3a  add     rsp, 58h
0x140002b3e  retn
```
