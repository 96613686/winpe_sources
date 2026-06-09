# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140004790`
- end: `0x1400048a8`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `280`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400046c8`
- `0x1400087cc`
- `0x14000c104`

## callees

- `0x1400048b0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexes::UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  unsigned __int64 Size; // rax
  __int64 v2; // r8
  __int64 v3; // r10
  __int16 v4; // r9
  unsigned __int64 v5; // rax
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // r10
  __int16 v9; // [rsp+20h] [rbp-20h] BYREF
  char v10; // [rsp+22h] [rbp-1Eh]
  int v11; // [rsp+24h] [rbp-1Ch]
  __int16 v12; // [rsp+28h] [rbp-18h]
  __int128 v13; // [rsp+30h] [rbp-10h]

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  *((_BYTE *)this + 8) = 0;
  v10 = 0;
  v11 = 0;
  *((_WORD *)this + 3) = 4;
  v9 = 4;
  v12 = 0;
  v13 = 0;
  Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v9);
  *(_QWORD *)(v2 + 16) = Size;
  *(_QWORD *)(v2 + 24) = v3;
  *(_QWORD *)(v2 + 32) = v3;
  *(_QWORD *)(v2 + 40) = v3;
  *(_QWORD *)(v2 + 48) = v3;
  *(_WORD *)(v2 + 56) = v3;
  *(_BYTE *)(v2 + 58) = v3;
  *(_DWORD *)(v2 + 64) = 0x40000;
  *(_BYTE *)(v2 + 68) = 1;
  *(_WORD *)(v2 + 70) = v4;
  *(_BYTE *)(v2 + 72) = 2;
  v9 = v4;
  v10 = 2;
  v11 = v3;
  v12 = v3;
  v13 = 0;
  v5 = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v9);
  *(_QWORD *)(v6 + 80) = v5;
  result = v6;
  *(_QWORD *)(v6 + 88) = v8;
  *(_QWORD *)(v6 + 96) = v8;
  *(_QWORD *)(v6 + 104) = v8;
  *(_QWORD *)(v6 + 112) = v8;
  *(_WORD *)(v6 + 120) = v8;
  *(_BYTE *)(v6 + 122) = v8;
  *(_DWORD *)(v6 + 128) = 0x40000;
  *(_BYTE *)(v6 + 132) = 1;
  *(_WORD *)(v6 + 134) = v8;
  *(_BYTE *)(v6 + 136) = 1;
  *(_QWORD *)(v6 + 144) = v8;
  *(_QWORD *)(v6 + 152) = v8;
  *(_QWORD *)(v6 + 160) = v8;
  *(_QWORD *)(v6 + 168) = v8;
  *(_QWORD *)(v6 + 176) = v8;
  *(_WORD *)(v6 + 184) = v8;
  *(_BYTE *)(v6 + 186) = v8;
  return result;
}

```

## disassembly

```asm
0x140004790  push    rbp
0x140004792  mov     rbp, rsp
0x140004795  sub     rsp, 40h
0x140004799  xor     r10d, r10d
0x14000479c  mov     dword ptr [rcx], 40000h
0x1400047a2  mov     r8, rcx
0x1400047a5  mov     byte ptr [rcx+4], 1
0x1400047a9  mov     [rcx+8], r10b
0x1400047ad  xorps   xmm0, xmm0
0x1400047b0  mov     [rbp+var_1E], r10b
0x1400047b4  lea     r9d, [r10+4]
0x1400047b8  mov     [rbp+var_1C], r10d
0x1400047bc  mov     [rcx+6], r9w
0x1400047c1  lea     rcx, [rbp+var_20]; this
0x1400047c5  mov     [rbp+var_20], r9w
0x1400047ca  mov     [rbp+var_18], r10w
0x1400047cf  movdqu  [rbp+var_10], xmm0
0x1400047d4  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1400047d9  mov     [r8+10h], rax
0x1400047dd  lea     rcx, [rbp+var_20]; this
0x1400047e1  mov     [r8+18h], r10
0x1400047e5  mov     [r8+20h], r10
0x1400047e9  mov     [r8+28h], r10
0x1400047ed  mov     [r8+30h], r10
0x1400047f1  mov     [r8+38h], r10w
0x1400047f6  mov     [r8+3Ah], r10b
0x1400047fa  mov     dword ptr [r8+40h], 40000h
0x140004802  mov     byte ptr [r8+44h], 1
0x140004807  mov     [r8+46h], r9w
0x14000480c  mov     byte ptr [r8+48h], 2
0x140004811  mov     [rbp+var_20], r9w
0x140004816  mov     [rbp+var_1E], 2
0x14000481a  mov     [rbp+var_1C], r10d
0x14000481e  mov     [rbp+var_18], r10w
0x140004823  movdqu  [rbp+var_10], xmm0
0x140004828  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000482d  mov     [r8+50h], rax
0x140004831  mov     rax, r8
0x140004834  mov     [r8+58h], r10
0x140004838  mov     [r8+60h], r10
0x14000483c  mov     [r8+68h], r10
0x140004840  mov     [r8+70h], r10
0x140004844  mov     [r8+78h], r10w
0x140004849  mov     [r8+7Ah], r10b
0x14000484d  mov     dword ptr [r8+80h], 40000h
0x140004858  mov     byte ptr [r8+84h], 1
0x140004860  mov     [r8+86h], r10w
0x140004868  mov     byte ptr [r8+88h], 1
0x140004870  mov     [r8+90h], r10
0x140004877  mov     [r8+98h], r10
0x14000487e  mov     [r8+0A0h], r10
0x140004885  mov     [r8+0A8h], r10
0x14000488c  mov     [r8+0B0h], r10
0x140004893  mov     [r8+0B8h], r10w
0x14000489b  mov     [r8+0BAh], r10b
0x1400048a2  add     rsp, 40h
0x1400048a6  pop     rbp
0x1400048a7  retn
```
