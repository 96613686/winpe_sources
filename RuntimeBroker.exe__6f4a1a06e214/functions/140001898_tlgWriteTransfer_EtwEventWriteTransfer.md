# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x140001898`
- end: `0x14000192f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400010b8`
- `0x140001210`
- `0x1400014c4`
- `0x14000e884`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x140001924`
- `ntdll!EtwEventWriteTransfer` at `0x140001924`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
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
0x140001898  sub     rsp, 48h
0x14000189c  movzx   eax, byte ptr [rdx]
0x14000189f  mov     r11, rcx
0x1400018a2  shl     eax, 18h
0x1400018a5  mov     r10, r8
0x1400018a8  mov     r8, [rsp+48h+arg_28]
0x1400018ad  mov     [rsp+48h+var_18], eax
0x1400018b1  movzx   eax, word ptr [rdx+1]
0x1400018b5  mov     [rsp+48h+var_14], eax
0x1400018b9  mov     rax, [rdx+3]
0x1400018bd  add     rdx, 0Bh
0x1400018c1  mov     [rsp+48h+var_10], rax
0x1400018c6  mov     rax, [rcx+8]
0x1400018ca  mov     [r8], rax
0x1400018cd  mov     rax, [rcx+8]
0x1400018d1  mov     [rsp+48h+var_20], r8
0x1400018d6  movzx   ecx, word ptr [rax]
0x1400018d9  mov     [r8+8], ecx
0x1400018dd  lea     rcx, _TraceLoggingMetadata
0x1400018e4  mov     [r8+10h], rdx
0x1400018e8  mov     dword ptr [r8+0Ch], 2
0x1400018f0  movzx   eax, word ptr [rdx]
0x1400018f3  lea     rdx, [rsp+48h+var_18]
0x1400018f8  mov     [r8+18h], eax
0x1400018fc  lea     rax, _TraceLoggingMetadataEnd
0x140001903  sub     eax, ecx
0x140001905  mov     dword ptr [r8+1Ch], 1
0x14000190d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001911  mov     r8, r10
0x140001914  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001918  mov     eax, [rsp+48h+arg_20]
0x14000191c  mov     rcx, [r11+20h]
0x140001920  mov     [rsp+48h+var_28], eax
0x140001924  call    cs:__imp_EtwEventWriteTransfer
0x14000192a  add     rsp, 48h
0x14000192e  retn
```
