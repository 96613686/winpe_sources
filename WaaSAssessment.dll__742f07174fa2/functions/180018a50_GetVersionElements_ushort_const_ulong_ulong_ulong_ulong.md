# GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)

- ea: `0x180018a50`
- end: `0x180018abb`
- name: `?GetVersionElements@@YAHPEBGAEAK111@Z`
- size: `107`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c990`
- `0x18000d9e0`
- `0x18000dd50`
- `0x18000df40`
- `0x18000e0f0`
- `0x18000e300`
- `0x180019068`

## callees

- `0x180018a50`
- `0x180019760`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180018aa3`
- `msvcrt!swscanf_s` at `0x180018aa3`

## pseudocode

```c
int __fastcall GetVersionElements(
        const unsigned __int16 *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  wchar_t Format[12]; // [rsp+30h] [rbp-28h] BYREF

  wcscpy(Format, (const wchar_t *)"%\x00d\x00.\x00%\x00d\x00.\x00%\x00d\x00.\x00%\x00d");
  if ( a1 )
    return swscanf_s(a1, Format, a2, a3, a4, a5);
  else
    return 0;
}

```

## disassembly

```asm
0x180018a50  sub     rsp, 58h
0x180018a54  mov     rax, cs:__security_cookie
0x180018a5b  xor     rax, rsp
0x180018a5e  mov     [rsp+58h+var_10], rax
0x180018a63  movsd   xmm1, qword ptr cs:?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+50h; ".\x00%\x00d"
0x180018a6b  mov     rax, [rsp+58h+arg_20]
0x180018a73  movsd   [rsp+58h+var_18], xmm1
0x180018a79  movups  xmm0, xmmword ptr cs:?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "%\x00d\x00.\x00%\x00d\x00.\x00%\x00d"...
0x180018a80  movups  xmmword ptr [rsp+58h+Format], xmm0
0x180018a85  test    rcx, rcx
0x180018a88  jnz     short loc_180018A8E
0x180018a8a  xor     eax, eax
0x180018a8c  jmp     short loc_180018AA9
0x180018a8e  mov     [rsp+58h+var_30], rax
0x180018a93  mov     [rsp+58h+var_38], r9
0x180018a98  mov     r9, r8
0x180018a9b  mov     r8, rdx
0x180018a9e  lea     rdx, [rsp+58h+Format]; Format
0x180018aa3  call    cs:__imp_swscanf_s
0x180018aa9  mov     rcx, [rsp+58h+var_10]
0x180018aae  xor     rcx, rsp; StackCookie
0x180018ab1  call    __security_check_cookie
0x180018ab6  add     rsp, 58h
0x180018aba  retn
```
