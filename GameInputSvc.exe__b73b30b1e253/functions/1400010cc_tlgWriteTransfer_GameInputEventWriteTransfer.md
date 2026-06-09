# _tlgWriteTransfer_GameInputEventWriteTransfer

- ea: `0x1400010cc`
- end: `0x140001163`
- name: `_tlgWriteTransfer_GameInputEventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001008`
- `0x14000116c`
- `0x14000125c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x140001158`
- `ntdll!EtwEventWriteTransfer` at `0x140001158`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_GameInputEventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  _DWORD v9[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+38h] [rbp-10h]

  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v10 = v6;
  *(_QWORD *)a6 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a6 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3);
}

```

## disassembly

```asm
0x1400010cc  sub     rsp, 48h
0x1400010d0  movzx   eax, byte ptr [rdx]
0x1400010d3  mov     r11, rcx
0x1400010d6  shl     eax, 18h
0x1400010d9  mov     r10, r8
0x1400010dc  mov     r8, [rsp+48h+arg_28]
0x1400010e1  mov     [rsp+48h+var_18], eax
0x1400010e5  movzx   eax, word ptr [rdx+1]
0x1400010e9  mov     [rsp+48h+var_14], eax
0x1400010ed  mov     rax, [rdx+3]
0x1400010f1  add     rdx, 0Bh
0x1400010f5  mov     [rsp+48h+var_10], rax
0x1400010fa  mov     rax, [rcx+8]
0x1400010fe  mov     [r8], rax
0x140001101  mov     rax, [rcx+8]
0x140001105  mov     [rsp+48h+var_20], r8
0x14000110a  movzx   ecx, word ptr [rax]
0x14000110d  mov     [r8+8], ecx
0x140001111  lea     rcx, _TraceLoggingMetadata
0x140001118  mov     [r8+10h], rdx
0x14000111c  mov     dword ptr [r8+0Ch], 2
0x140001124  movzx   eax, word ptr [rdx]
0x140001127  lea     rdx, [rsp+48h+var_18]
0x14000112c  mov     [r8+18h], eax
0x140001130  lea     rax, _TraceLoggingMetadataEnd
0x140001137  sub     eax, ecx
0x140001139  mov     dword ptr [r8+1Ch], 1
0x140001141  mov     dword ptr [rsp+48h+arg_28], eax
0x140001145  mov     r8, r10
0x140001148  mov     eax, dword ptr [rsp+48h+arg_28]
0x14000114c  mov     eax, [rsp+48h+arg_20]
0x140001150  mov     rcx, [r11+20h]
0x140001154  mov     [rsp+48h+var_28], eax
0x140001158  call    cs:__imp_EtwEventWriteTransfer
0x14000115e  add     rsp, 48h
0x140001162  retn
```
