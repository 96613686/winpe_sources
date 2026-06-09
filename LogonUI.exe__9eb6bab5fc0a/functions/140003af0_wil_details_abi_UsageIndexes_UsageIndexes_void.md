# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140003af0`
- end: `0x140003b5e`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055a8`
- `0x140005978`
- `0x140005d40`

## callees

- `0x140003a6c`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this)
{
  char v2; // r9
  char v3; // r9
  __int16 v4; // r11

  wil::details_abi::RawUsageIndex::RawUsageIndex((__int64)this, 0, 4, 1, 4, 0);
  wil::details_abi::RawUsageIndex::RawUsageIndex((__int64)this + 64, 0, 4, v2, 4, 2);
  wil::details_abi::RawUsageIndex::RawUsageIndex((__int64)this + 128, 0, 4, v3, v4, v3);
  return this;
}

```

## disassembly

```asm
0x140003af0  mov     [rsp+arg_0], rbx
0x140003af5  push    rdi
0x140003af6  sub     rsp, 30h
0x140003afa  mov     edi, 4
0x140003aff  xor     r11d, r11d
0x140003b02  mov     r8d, edi
0x140003b05  mov     [rsp+38h+var_10], r11b
0x140003b0a  xor     edx, edx
0x140003b0c  mov     [rsp+38h+var_18], di
0x140003b11  mov     r9b, 1
0x140003b14  mov     rbx, rcx
0x140003b17  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140003b1c  mov     r8d, edi
0x140003b1f  mov     [rsp+38h+var_10], 2
0x140003b24  xor     edx, edx
0x140003b26  mov     [rsp+38h+var_18], di
0x140003b2b  lea     rcx, [rbx+40h]
0x140003b2f  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140003b34  mov     r8d, edi
0x140003b37  mov     [rsp+38h+var_10], r9b
0x140003b3c  xor     edx, edx
0x140003b3e  mov     [rsp+38h+var_18], r11w
0x140003b44  lea     rcx, [rbx+80h]
0x140003b4b  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x140003b50  mov     rax, rbx
0x140003b53  mov     rbx, [rsp+38h+arg_0]
0x140003b58  add     rsp, 30h
0x140003b5c  pop     rdi
0x140003b5d  retn
```
