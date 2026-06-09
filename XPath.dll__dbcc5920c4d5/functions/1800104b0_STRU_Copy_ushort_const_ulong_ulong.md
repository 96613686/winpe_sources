# STRU::Copy(ushort const *,ulong,ulong)

- ea: `0x1800104b0`
- end: `0x1800104f8`
- name: `?Copy@STRU@@QEAAJPEBGKK@Z`
- size: `72`
- prototype: `__int64 __fastcall(STRU *this, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001082c`
- `0x180010bc8`

## callees

- `0x18000a750`
- `0x18000ae3c`
- `0x1800104b0`

## pseudocode

```c
__int64 __fastcall STRU::Copy(STRU *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 result; // rax
  STRU *v4; // r11
  unsigned __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  result = STRU::GetStringCbLengthW(L"{", 0, a3, &v5);
  if ( (int)result >= 0 )
    return STRU::AuxAppend(v4, L"{", v5, 0);
  return result;
}

```

## disassembly

```asm
0x1800104b0  mov     [rsp+arg_8], rdx
0x1800104b5  sub     rsp, 28h
0x1800104b9  mov     r11, rcx
0x1800104bc  mov     [rsp+28h+arg_8], 0
0x1800104c5  lea     rcx, asc_180017268; "{"
0x1800104cc  xor     edx, edx; unsigned int
0x1800104ce  lea     r9, [rsp+28h+arg_8]; unsigned __int64 *
0x1800104d3  call    ?GetStringCbLengthW@STRU@@CAJPEBGKKPEA_K@Z; STRU::GetStringCbLengthW(ushort const *,ulong,ulong,unsigned __int64 *)
0x1800104d8  test    eax, eax
0x1800104da  js      short loc_1800104F3
0x1800104dc  mov     r8d, dword ptr [rsp+28h+arg_8]; unsigned int
0x1800104e1  lea     rdx, asc_180017268; "{"
0x1800104e8  xor     r9d, r9d; unsigned int
0x1800104eb  mov     rcx, r11; this
0x1800104ee  call    ?AuxAppend@STRU@@AEAAJPEBGKK@Z; STRU::AuxAppend(ushort const *,ulong,ulong)
0x1800104f3  add     rsp, 28h
0x1800104f7  retn
```
