# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180016e0c`
- end: `0x180016e4c`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `64`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fa30`
- `0x18001d1fc`
- `0x18001fadc`
- `0x180021928`
- `0x180021ddc`
- `0x18002217c`
- `0x180022c80`
- `0x180023ed8`
- `0x180024ec4`

## callees

- `0x180016e0c`
- `0x180016fd8`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 >> 1 )
  {
    if ( a2 >> 1 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2 >> 1, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180016e0c  sub     rsp, 38h
0x180016e10  mov     rax, rdx
0x180016e13  shr     rax, 1
0x180016e16  jz      short loc_180016E36
0x180016e18  cmp     rax, 7FFFFFFFh
0x180016e1e  jbe     short loc_180016E27
0x180016e20  mov     edx, 80070057h
0x180016e25  jmp     short loc_180016E40
0x180016e27  mov     r9, r8; pszSrc
0x180016e2a  mov     rdx, rax; cchDest
0x180016e2d  call    StringCopyWorkerW
0x180016e32  mov     edx, eax
0x180016e34  jmp     short loc_180016E45
0x180016e36  mov     edx, 80070057h
0x180016e3b  test    rax, rax
0x180016e3e  jz      short loc_180016E45
0x180016e40  xor     eax, eax
0x180016e42  mov     [rcx], ax
0x180016e45  mov     eax, edx
0x180016e47  add     rsp, 38h
0x180016e4b  retn
```
