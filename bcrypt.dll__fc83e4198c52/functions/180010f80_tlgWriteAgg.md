# _tlgWriteAgg

- ea: `0x180010f80`
- end: `0x18001100b`
- name: `_tlgWriteAgg`
- size: `139`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d0`
- `0x1800101c0`
- `0x180014510`
- `0x180014740`

## callees

- `0x180011014`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *a5)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  EVENT_DESCRIPTOR v8; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)&v8.Id = *a2 << 24;
  *(_DWORD *)&v8.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  v8.Keyword = v5;
  a5->Ptr = (ULONGLONG)off_180024058;
  a5->Size = *(unsigned __int16 *)off_180024058;
  a5[1].Ptr = (ULONGLONG)v6;
  a5->Reserved = 2;
  a5[1].Size = *v6;
  a5[1].Reserved = 1;
  return TlgAggregateAbsorbEvent((__int64)&TraceLoggingMetadata, &v8, a4, a5);
}

```

## disassembly

```asm
0x180010f80  mov     [rsp+arg_10], r8
0x180010f85  sub     rsp, 38h
0x180010f89  movzx   eax, byte ptr [rdx]
0x180010f8c  mov     r8d, r9d
0x180010f8f  mov     r9, [rsp+38h+arg_20]
0x180010f94  shl     eax, 18h
0x180010f97  mov     [rsp+38h+var_18], eax
0x180010f9b  movzx   eax, word ptr [rdx+1]
0x180010f9f  mov     [rsp+38h+var_14], eax
0x180010fa3  mov     rax, [rdx+3]
0x180010fa7  add     rdx, 0Bh
0x180010fab  mov     [rsp+38h+var_10], rax
0x180010fb0  mov     rax, cs:off_180024058
0x180010fb7  mov     [r9], rax
0x180010fba  mov     rax, cs:off_180024058
0x180010fc1  movzx   ecx, word ptr [rax]
0x180010fc4  mov     [r9+8], ecx
0x180010fc8  lea     rcx, _TraceLoggingMetadata
0x180010fcf  mov     [r9+10h], rdx
0x180010fd3  mov     dword ptr [r9+0Ch], 2
0x180010fdb  movzx   eax, word ptr [rdx]
0x180010fde  lea     rdx, [rsp+38h+var_18]
0x180010fe3  mov     [r9+18h], eax
0x180010fe7  lea     rax, _TraceLoggingMetadataEnd
0x180010fee  sub     eax, ecx
0x180010ff0  mov     dword ptr [r9+1Ch], 1
0x180010ff8  mov     dword ptr [rsp+38h+arg_10], eax
0x180010ffc  mov     eax, dword ptr [rsp+38h+arg_10]
0x180011000  call    TlgAggregateAbsorbEvent
0x180011005  add     rsp, 38h
0x180011009  retn
```
