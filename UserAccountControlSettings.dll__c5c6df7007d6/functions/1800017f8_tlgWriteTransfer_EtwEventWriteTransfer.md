# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x1800017f8`
- end: `0x18000188f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180009d30`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001884`
- `ntdll!EtwEventWriteTransfer` at `0x180001884`

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
0x1800017f8  sub     rsp, 48h
0x1800017fc  movzx   eax, byte ptr [rdx]
0x1800017ff  mov     r11, rcx
0x180001802  shl     eax, 18h
0x180001805  mov     r10, r8
0x180001808  mov     r8, [rsp+48h+arg_28]
0x18000180d  mov     [rsp+48h+var_18], eax
0x180001811  movzx   eax, word ptr [rdx+1]
0x180001815  mov     [rsp+48h+var_14], eax
0x180001819  mov     rax, [rdx+3]
0x18000181d  add     rdx, 0Bh
0x180001821  mov     [rsp+48h+var_10], rax
0x180001826  mov     rax, [rcx+8]
0x18000182a  mov     [r8], rax
0x18000182d  mov     rax, [rcx+8]
0x180001831  mov     [rsp+48h+var_20], r8
0x180001836  movzx   ecx, word ptr [rax]
0x180001839  mov     [r8+8], ecx
0x18000183d  lea     rcx, _TraceLoggingMetadata
0x180001844  mov     [r8+10h], rdx
0x180001848  mov     dword ptr [r8+0Ch], 2
0x180001850  movzx   eax, word ptr [rdx]
0x180001853  lea     rdx, [rsp+48h+var_18]
0x180001858  mov     [r8+18h], eax
0x18000185c  lea     rax, _TraceLoggingMetadataEnd
0x180001863  sub     eax, ecx
0x180001865  mov     dword ptr [r8+1Ch], 1
0x18000186d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001871  mov     r8, r10
0x180001874  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001878  mov     eax, [rsp+48h+arg_20]
0x18000187c  mov     rcx, [r11+20h]
0x180001880  mov     [rsp+48h+var_28], eax
0x180001884  call    cs:__imp_EtwEventWriteTransfer
0x18000188a  add     rsp, 48h
0x18000188e  retn
```
