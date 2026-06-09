# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001bd8`
- end: `0x180001c6f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800010f8`
- `0x180001148`
- `0x180001420`
- `0x1800016d4`
- `0x180001778`
- `0x180001820`
- `0x180001b18`
- `0x180001c78`
- `0x180001d08`
- `0x180001dcc`
- `0x180001ec0`
- `0x180001f24`
- `0x180001f9c`
- `0x180002070`
- `0x180002134`
- `0x1800022d4`
- `0x1800023cc`
- `0x1800024c0`
- `0x18000256c`
- `0x18001506c`
- `0x180023f54`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001c64`
- `ntdll!EtwEventWriteTransfer` at `0x180001c64`

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
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180001bd8  sub     rsp, 48h
0x180001bdc  movzx   eax, byte ptr [rdx]
0x180001bdf  mov     r11, rcx
0x180001be2  shl     eax, 18h
0x180001be5  mov     r10, r8
0x180001be8  mov     r8, [rsp+48h+arg_28]
0x180001bed  mov     [rsp+48h+var_18], eax
0x180001bf1  movzx   eax, word ptr [rdx+1]
0x180001bf5  mov     [rsp+48h+var_14], eax
0x180001bf9  mov     rax, [rdx+3]
0x180001bfd  add     rdx, 0Bh
0x180001c01  mov     [rsp+48h+var_10], rax
0x180001c06  mov     rax, [rcx+8]
0x180001c0a  mov     [r8], rax
0x180001c0d  mov     rax, [rcx+8]
0x180001c11  mov     [rsp+48h+var_20], r8
0x180001c16  movzx   ecx, word ptr [rax]
0x180001c19  mov     [r8+8], ecx
0x180001c1d  lea     rcx, _TraceLoggingMetadata
0x180001c24  mov     [r8+10h], rdx
0x180001c28  mov     dword ptr [r8+0Ch], 2
0x180001c30  movzx   eax, word ptr [rdx]
0x180001c33  lea     rdx, [rsp+48h+var_18]
0x180001c38  mov     [r8+18h], eax
0x180001c3c  lea     rax, _TraceLoggingMetadataEnd
0x180001c43  sub     eax, ecx
0x180001c45  mov     dword ptr [r8+1Ch], 1
0x180001c4d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001c51  mov     r8, r10
0x180001c54  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001c58  mov     eax, [rsp+48h+arg_20]
0x180001c5c  mov     rcx, [r11+20h]
0x180001c60  mov     [rsp+48h+var_28], eax
0x180001c64  call    cs:__imp_EtwEventWriteTransfer
0x180001c6a  add     rsp, 48h
0x180001c6e  retn
```
