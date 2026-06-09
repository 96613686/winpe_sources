# WPP_SF_d

- ea: `0x180009aa4`
- end: `0x180009adb`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180005380`
- `0x1800057a0`
- `0x180005d80`
- `0x180006530`
- `0x1800069c0`
- `0x180007d60`
- `0x180008420`
- `0x1800087a0`
- `0x180008c80`
- `0x1800098c0`
- `0x180009c1c`
- `0x180009c84`
- `0x18000a69c`
- `0x18000a88c`
- `0x18000ac38`
- `0x18000b604`
- `0x18000c660`
- `0x18000cab0`
- `0x18000dc98`
- `0x18000e16c`
- `0x18000e440`
- `0x18000e530`
- `0x18000f2f8`
- `0x18000f4dc`
- `0x18001639c`
- `0x1800168c8`
- `0x180016a08`
- `0x180016d30`
- `0x1800175a8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180009ad0`
- `ADVAPI32!TraceMessage` at `0x180009ad0`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180009aa4  mov     r11, rsp
0x180009aa7  mov     [r11+20h], r9d
0x180009aab  sub     rsp, 48h
0x180009aaf  mov     qword ptr [r11-18h], 0
0x180009ab7  lea     rax, [r11+20h]
0x180009abb  movzx   r9d, dx; MessageNumber
0x180009abf  mov     edx, 2Bh ; '+'; MessageFlags
0x180009ac4  mov     qword ptr [r11-20h], 4
0x180009acc  mov     [r11-28h], rax
0x180009ad0  call    cs:__imp_TraceMessage
0x180009ad6  add     rsp, 48h
0x180009ada  retn
```
