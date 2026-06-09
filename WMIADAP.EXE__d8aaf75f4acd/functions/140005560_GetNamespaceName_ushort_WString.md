# GetNamespaceName(ushort *,WString &)

- ea: `0x140005560`
- end: `0x1400055f6`
- name: `?GetNamespaceName@@YAJPEAGAEAVWString@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct WString *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004e24`

## callees

- `0x140005560`
- `0x1400055fc`

## import_xrefs

- `wbemcomn!??YWString@@QEAAAEAV0@AEBV0@@Z` at `0x1400055c7`
- `wbemcomn!??YWString@@QEAAAEAV0@AEBV0@@Z` at `0x1400055c7`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x1400055b9`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x1400055b9`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x14000558d`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x14000558d`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x14000557c`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x14000557c`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x1400055de`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x1400055de`

## pseudocode

```c
__int64 __fastcall GetNamespaceName(unsigned __int16 *a1, struct WString *a2)
{
  int v4; // ebx
  unsigned __int16 *v6; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  WString::WString((WString *)&v6);
  try
  {
    WString::operator=(a2, L"\\\\.\\root\\cimv2");
    if ( a1 )
    {
      v4 = InitializeLID(a1, (struct WString *)&v6);
      if ( v4 >= 0 )
      {
        WString::operator+=(a2, L"\\");
        WString::operator+=(a2, &v6);
      }
    }
  }
  catch ( CX_MemoryException )
  {
    v4 = -2147217402;
  }
  WString::operator=(a2, L"\\\\.\\root\\cimv2");
  if ( a1 )
  {
    v4 = InitializeLID(a1, (struct WString *)&v6);
    if ( v4 >= 0 )
    {
      WString::operator+=(a2, L"\\");
      WString::operator+=(a2, &v6);
    }
  }
}

```

## disassembly

```asm
0x140005560  mov     [rsp+arg_0], rbx
0x140005565  mov     [rsp+arg_8], rsi
0x14000556a  push    rdi
0x14000556b  sub     rsp, 30h
0x14000556f  mov     rdi, rdx
0x140005572  mov     rsi, rcx
0x140005575  xor     ebx, ebx
0x140005577  lea     rcx, [rsp+38h+arg_10]
0x14000557c  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x140005582  nop
0x140005583  lea     rdx, aRootCimv2; "\\\\.\\root\\cimv2"
0x14000558a  mov     rcx, rdi
0x14000558d  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x140005593  test    rsi, rsi
0x140005596  jz      short loc_1400055CE
0x140005598  lea     rdx, [rsp+38h+arg_10]; struct WString *
0x14000559d  mov     rcx, rsi; unsigned __int16 *
0x1400055a0  call    ?InitializeLID@@YAJPEAGAEAVWString@@@Z; InitializeLID(ushort *,WString &)
0x1400055a5  mov     ebx, eax
0x1400055a7  mov     [rsp+38h+var_18], eax
0x1400055ab  test    eax, eax
0x1400055ad  js      short loc_1400055CE
0x1400055af  lea     rdx, asc_14001A9B8; "\\"
0x1400055b6  mov     rcx, rdi
0x1400055b9  call    cs:__imp_??YWString@@QEAAAEAV0@PEBG@Z; WString::operator+=(ushort const *)
0x1400055bf  lea     rdx, [rsp+38h+arg_10]
0x1400055c4  mov     rcx, rdi
0x1400055c7  call    cs:__imp_??YWString@@QEAAAEAV0@AEBV0@@Z; WString::operator+=(WString const &)
0x1400055cd  nop
0x1400055ce  jmp     short loc_1400055D4
0x1400055d0  mov     ebx, [rsp+38h+var_18]
0x1400055d4  mov     rdx, [rsp+38h+arg_10]
0x1400055d9  lea     rcx, [rsp+38h+arg_10]
0x1400055de  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x1400055e4  mov     eax, ebx
0x1400055e6  mov     rbx, [rsp+38h+arg_0]
0x1400055eb  mov     rsi, [rsp+38h+arg_8]
0x1400055f0  add     rsp, 30h
0x1400055f4  pop     rdi
0x1400055f5  retn
```
