# wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)

- ea: `0x140003a6c`
- end: `0x140003ae9`
- name: `??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003af0`
- `0x140005da4`

## callees

- `0x140003a6c`
- `0x140004c6c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::RawUsageIndex::RawUsageIndex(
        __int64 a1,
        __int16 a2,
        __int16 a3,
        char a4,
        __int16 a5,
        char a6)
{
  __int64 v6; // r10
  __int64 v7; // r8
  unsigned __int64 Size; // rax
  __int64 result; // rax
  __int16 v10; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+22h] [rbp-26h]
  int v12; // [rsp+24h] [rbp-24h]
  __int16 v13; // [rsp+28h] [rbp-20h]
  __int128 v14; // [rsp+30h] [rbp-18h]

  v6 = a1;
  *(_WORD *)(a1 + 2) = a3;
  v7 = 0;
  *(_WORD *)(a1 + 6) = a5;
  *(_WORD *)a1 = a2;
  *(_BYTE *)(a1 + 4) = a4;
  *(_BYTE *)(a1 + 8) = a6;
  if ( a5 )
  {
    v11 = a6;
    v10 = a5;
    v14 = 0;
    v12 = 0;
    v13 = 0;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v10);
  }
  else
  {
    Size = 0;
  }
  *(_QWORD *)(v6 + 16) = Size;
  result = v6;
  *(_QWORD *)(v6 + 24) = v7;
  *(_QWORD *)(v6 + 32) = v7;
  *(_QWORD *)(v6 + 40) = v7;
  *(_QWORD *)(v6 + 48) = v7;
  *(_WORD *)(v6 + 56) = v7;
  *(_BYTE *)(v6 + 58) = v7;
  return result;
}

```

## disassembly

```asm
0x140003a6c  sub     rsp, 48h
0x140003a70  movzx   eax, [rsp+48h+arg_20]
0x140003a75  mov     r10, rcx
0x140003a78  mov     [rcx+2], r8w
0x140003a7d  xor     r8d, r8d
0x140003a80  mov     [rcx+6], ax
0x140003a84  mov     [rcx], dx
0x140003a87  mov     [rcx+4], r9b
0x140003a8b  mov     cl, [rsp+48h+arg_28]
0x140003a8f  mov     [r10+8], cl
0x140003a93  test    ax, ax
0x140003a96  jz      short loc_140003AC1
0x140003a98  mov     [rsp+48h+var_26], cl
0x140003a9c  xorps   xmm0, xmm0
0x140003a9f  lea     rcx, [rsp+48h+var_28]; this
0x140003aa4  mov     [rsp+48h+var_28], ax
0x140003aa9  movdqu  [rsp+48h+var_18], xmm0
0x140003aaf  mov     [rsp+48h+var_24], r8d
0x140003ab4  mov     [rsp+48h+var_20], r8w
0x140003aba  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140003abf  jmp     short loc_140003AC4
0x140003ac1  mov     rax, r8
0x140003ac4  mov     [r10+10h], rax
0x140003ac8  mov     rax, r10
0x140003acb  mov     [r10+18h], r8
0x140003acf  mov     [r10+20h], r8
0x140003ad3  mov     [r10+28h], r8
0x140003ad7  mov     [r10+30h], r8
0x140003adb  mov     [r10+38h], r8w
0x140003ae0  mov     [r10+3Ah], r8b
0x140003ae4  add     rsp, 48h
0x140003ae8  retn
```
