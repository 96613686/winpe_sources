# WPP_SF_sdd

- ea: `0x18008a840`
- end: `0x18008a89a`
- name: `WPP_SF_sdd`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18008a438`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18008a88f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18008a88f`

## string_xrefs

- `0x18008a87c`: `KnowledgeId::CompareTo`

## pseudocode

```c
ULONG WPP_SF_sdd(TRACEHANDLE a1, __int64 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_82d43572357d3e40b8f22864f5a78709_Traceguids,
           0xFu,
           "KnowledgeId::CompareTo",
           23,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18008a840  mov     r11, rsp
0x18008a843  sub     rsp, 68h
0x18008a847  mov     qword ptr [r11-18h], 0
0x18008a84f  lea     rax, [r11+30h]
0x18008a853  mov     r9d, 0Fh; MessageNumber
0x18008a859  lea     r8, WPP_82d43572357d3e40b8f22864f5a78709_Traceguids; MessageGuid
0x18008a860  lea     edx, [r9-0Bh]
0x18008a864  mov     [r11-20h], rdx
0x18008a868  mov     [r11-28h], rax
0x18008a86c  lea     rax, [r11+28h]
0x18008a870  mov     [r11-30h], rdx
0x18008a874  lea     edx, [r9+1Ch]; MessageFlags
0x18008a878  mov     [r11-38h], rax
0x18008a87c  lea     rax, aKnowledgeidCom; "KnowledgeId::CompareTo"
0x18008a883  mov     qword ptr [r11-40h], 17h
0x18008a88b  mov     [r11-48h], rax
0x18008a88f  call    cs:__imp_TraceMessage
0x18008a895  add     rsp, 68h
0x18008a899  retn
```
