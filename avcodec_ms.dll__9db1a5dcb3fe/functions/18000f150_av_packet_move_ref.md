# av_packet_move_ref

- ea: `0x18000f150`
- end: `0x18000f190`
- name: `av_packet_move_ref`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180006020`
- `0x1800061bc`
- `0x1800097f0`
- `0x180010bec`
- `0x180011534`

## callees

- `0x18000fc2c`

## pseudocode

```c
__int64 __fastcall av_packet_move_ref(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_OWORD *)(a1 + 48) = *(_OWORD *)(a2 + 48);
  *(_OWORD *)(a1 + 64) = *(_OWORD *)(a2 + 64);
  *(_OWORD *)(a1 + 80) = *(_OWORD *)(a2 + 80);
  *(_QWORD *)(a1 + 96) = *(_QWORD *)(a2 + 96);
  return sub_18000FC2C((_QWORD *)a2, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f150  movups  xmm0, xmmword ptr [rdx]
0x18000f153  movups  xmmword ptr [rcx], xmm0
0x18000f156  movups  xmm1, xmmword ptr [rdx+10h]
0x18000f15a  movups  xmmword ptr [rcx+10h], xmm1
0x18000f15e  movups  xmm0, xmmword ptr [rdx+20h]
0x18000f162  movups  xmmword ptr [rcx+20h], xmm0
0x18000f166  movups  xmm1, xmmword ptr [rdx+30h]
0x18000f16a  movups  xmmword ptr [rcx+30h], xmm1
0x18000f16e  movups  xmm0, xmmword ptr [rdx+40h]
0x18000f172  movups  xmmword ptr [rcx+40h], xmm0
0x18000f176  movups  xmm1, xmmword ptr [rdx+50h]
0x18000f17a  movups  xmmword ptr [rcx+50h], xmm1
0x18000f17e  movsd   xmm0, qword ptr [rdx+60h]
0x18000f183  movsd   qword ptr [rcx+60h], xmm0
0x18000f188  mov     rcx, rdx
0x18000f18b  jmp     sub_18000FC2C
```
