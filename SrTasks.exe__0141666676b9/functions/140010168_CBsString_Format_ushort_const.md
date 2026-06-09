# CBsString::Format(ushort const *,...)

- ea: `0x140010168`
- end: `0x14001019e`
- name: `?Format@CBsString@@QEAAJPEBGZZ`
- size: `54`
- prototype: `__int64(CBsString *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f24c`
- `0x14000f510`
- `0x14000f7a0`
- `0x14000fa1c`

## callees

- `0x140010168`
- `0x1400101a4`

## pseudocode

```c
__int64 CBsString::Format(CBsString *this, wchar_t *a2, ...)
{
  va_list Args; // [rsp+50h] [rbp+18h] BYREF

  va_start(Args, a2);
  if ( a2 )
    return CBsString::FormatV(this, a2, Args);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x140010168  mov     rax, rsp
0x14001016b  mov     [rax+10h], rdx
0x14001016f  mov     [rax+18h], r8
0x140010173  mov     [rax+20h], r9
0x140010177  sub     rsp, 38h
0x14001017b  mov     qword ptr [rax-18h], 0
0x140010183  test    rdx, rdx
0x140010186  jnz     short loc_14001018F
0x140010188  mov     eax, 80070057h
0x14001018d  jmp     short loc_140010199
0x14001018f  lea     r8, [rsp+38h+Args]; Args
0x140010194  call    ?FormatV@CBsString@@QEAAJPEBGPEAD@Z; CBsString::FormatV(ushort const *,char *)
0x140010199  add     rsp, 38h
0x14001019d  retn
```
