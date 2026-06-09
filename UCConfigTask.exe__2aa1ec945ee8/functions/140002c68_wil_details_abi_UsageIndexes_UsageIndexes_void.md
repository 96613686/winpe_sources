# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140002c68`
- end: `0x140002cd6`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a38`
- `0x1400052f4`
- `0x140005898`

## callees

- `0x140002aa4`

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
0x140002c68  mov     [rsp+arg_0], rbx
0x140002c6d  push    rdi
0x140002c6e  sub     rsp, 30h
0x140002c72  mov     edi, 4
0x140002c77  xor     r11d, r11d
0x140002c7a  mov     r8d, edi
0x140002c7d  mov     byte ptr [rsp+38h+var_10], r11b
0x140002c82  xor     edx, edx
0x140002c84  mov     [rsp+38h+var_18], di
0x140002c89  mov     r9b, 1
0x140002c8c  mov     rbx, rcx
0x140002c8f  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140002c94  mov     r8d, edi
0x140002c97  mov     byte ptr [rsp+38h+var_10], 2
0x140002c9c  xor     edx, edx
0x140002c9e  mov     [rsp+38h+var_18], di
0x140002ca3  lea     rcx, [rbx+40h]
0x140002ca7  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140002cac  mov     r8d, edi
0x140002caf  mov     byte ptr [rsp+38h+var_10], r9b
0x140002cb4  xor     edx, edx
0x140002cb6  mov     [rsp+38h+var_18], r11w
0x140002cbc  lea     rcx, [rbx+80h]
0x140002cc3  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140002cc8  mov     rax, rbx
0x140002ccb  mov     rbx, [rsp+38h+arg_0]
0x140002cd0  add     rsp, 30h
0x140002cd4  pop     rdi
0x140002cd5  retn
```
