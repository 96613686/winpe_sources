# WPP_SF_d

- ea: `0x18000be1c`
- end: `0x18000be5a`
- name: `WPP_SF_d`
- size: `62`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180006fd8`
- `0x180007f80`
- `0x1800082c0`
- `0x1800085b0`
- `0x18000a2b0`
- `0x18000b5dc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000be4f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000be4f`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_1d6fff2cd8463d06a7f66ef5d4aaafbc_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000be1c  mov     r11, rsp
0x18000be1f  mov     [r11+20h], r9d
0x18000be23  sub     rsp, 48h
0x18000be27  mov     qword ptr [r11-18h], 0
0x18000be2f  lea     rax, [r11+20h]
0x18000be33  movzx   r9d, dx; MessageNumber
0x18000be37  lea     r8, WPP_1d6fff2cd8463d06a7f66ef5d4aaafbc_Traceguids; MessageGuid
0x18000be3e  mov     qword ptr [r11-20h], 4
0x18000be46  mov     edx, 2Bh ; '+'; MessageFlags
0x18000be4b  mov     [r11-28h], rax
0x18000be4f  call    cs:__imp_TraceMessage
0x18000be55  add     rsp, 48h
0x18000be59  retn
```
