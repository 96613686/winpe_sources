# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140004c40`
- end: `0x140004cae`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f70`
- `0x14000740c`
- `0x140007924`

## callees

- `0x140004ab4`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r9
  __int64 v6; // r9
  __int16 v7; // r11
  __int16 v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  char v12; // [rsp+28h] [rbp-10h]
  int v13; // [rsp+28h] [rbp-10h]
  int v14; // [rsp+28h] [rbp-10h]

  v12 = 0;
  v9 = 4;
  LOBYTE(a4) = 1;
  wil::details_abi::RawUsageIndex::RawUsageIndex(this, 0, 4, a4, v9, v12);
  LOBYTE(v13) = 2;
  LOWORD(v10) = 4;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 64, 0, 4, v5, v10, v13);
  LOBYTE(v14) = v6;
  LOWORD(v11) = v7;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 128, 0, 4, v6, v11, v14);
  return this;
}

```

## disassembly

```asm
0x140004c40  mov     [rsp+arg_0], rbx
0x140004c45  push    rdi
0x140004c46  sub     rsp, 30h
0x140004c4a  mov     edi, 4
0x140004c4f  xor     r11d, r11d
0x140004c52  mov     r8d, edi
0x140004c55  mov     byte ptr [rsp+38h+var_10], r11b
0x140004c5a  xor     edx, edx
0x140004c5c  mov     [rsp+38h+var_18], di
0x140004c61  mov     r9b, 1
0x140004c64  mov     rbx, rcx
0x140004c67  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140004c6c  mov     r8d, edi
0x140004c6f  mov     byte ptr [rsp+38h+var_10], 2
0x140004c74  xor     edx, edx
0x140004c76  mov     [rsp+38h+var_18], di
0x140004c7b  lea     rcx, [rbx+40h]
0x140004c7f  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140004c84  mov     r8d, edi
0x140004c87  mov     byte ptr [rsp+38h+var_10], r9b
0x140004c8c  xor     edx, edx
0x140004c8e  mov     [rsp+38h+var_18], r11w
0x140004c94  lea     rcx, [rbx+80h]
0x140004c9b  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140004ca0  mov     rax, rbx
0x140004ca3  mov     rbx, [rsp+38h+arg_0]
0x140004ca8  add     rsp, 30h
0x140004cac  pop     rdi
0x140004cad  retn
```
