# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180003284`
- end: `0x1800032f2`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e74`
- `0x180006368`
- `0x180006a18`

## callees

- `0x1800030c0`

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
0x180003284  mov     [rsp+arg_0], rbx
0x180003289  push    rdi
0x18000328a  sub     rsp, 30h
0x18000328e  mov     edi, 4
0x180003293  xor     r11d, r11d
0x180003296  mov     r8d, edi
0x180003299  mov     byte ptr [rsp+38h+var_10], r11b
0x18000329e  xor     edx, edx
0x1800032a0  mov     [rsp+38h+var_18], di
0x1800032a5  mov     r9b, 1
0x1800032a8  mov     rbx, rcx
0x1800032ab  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800032b0  mov     r8d, edi
0x1800032b3  mov     byte ptr [rsp+38h+var_10], 2
0x1800032b8  xor     edx, edx
0x1800032ba  mov     [rsp+38h+var_18], di
0x1800032bf  lea     rcx, [rbx+40h]
0x1800032c3  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800032c8  mov     r8d, edi
0x1800032cb  mov     byte ptr [rsp+38h+var_10], r9b
0x1800032d0  xor     edx, edx
0x1800032d2  mov     [rsp+38h+var_18], r11w
0x1800032d8  lea     rcx, [rbx+80h]
0x1800032df  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800032e4  mov     rax, rbx
0x1800032e7  mov     rbx, [rsp+38h+arg_0]
0x1800032ec  add     rsp, 30h
0x1800032f0  pop     rdi
0x1800032f1  retn
```
