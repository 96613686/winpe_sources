# AipFreeFileSignature

- ea: `0x180007ccc`
- end: `0x180007d62`
- name: `AipFreeFileSignature`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800074a0`
- `0x180007d68`
- `0x1800082ec`

## callees

- `0x180007ccc`
- `0x18000957a`
- `0x1800095c0`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x180007d3f`
- `WINTRUST!WinVerifyTrust` at `0x180007d3f`

## pseudocode

```c
LONG __fastcall AipFreeFileSignature(__int64 a1)
{
  LONG result; // eax
  _DWORD pWVTData[14]; // [rsp+20h] [rbp-29h] BYREF
  __int64 v4; // [rsp+58h] [rbp+Fh]
  GUID pgActionID; // [rsp+80h] [rbp+37h] BYREF

  if ( a1 )
  {
    pgActionID.Data1 = 11191659;
    *(_DWORD *)&pgActionID.Data2 = 298896708;
    *(_DWORD *)pgActionID.Data4 = -1073692020;
    *(_DWORD *)&pgActionID.Data4[4] = -292175281;
    memset_0(pWVTData, 0, 0x58u);
    pWVTData[0] = 88;
    pWVTData[12] = 2;
    v4 = a1;
    return WinVerifyTrust(0, &pgActionID, pWVTData);
  }
  return result;
}

```

## disassembly

```asm
0x180007ccc  test    rcx, rcx
0x180007ccf  jz      locret_180007D61
0x180007cd5  mov     [rsp-8+arg_8], rbx
0x180007cda  push    rbp
0x180007cdb  lea     rbp, [rsp-57h]
0x180007ce0  sub     rsp, 0A0h
0x180007ce7  mov     rax, cs:__security_cookie
0x180007cee  xor     rax, rsp
0x180007cf1  mov     [rbp+57h+var_10], rax
0x180007cf5  xor     edx, edx; Val
0x180007cf7  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x180007cfe  mov     rbx, rcx
0x180007d01  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x180007d08  lea     rcx, [rbp+57h+pWVTData]; void *
0x180007d0c  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x180007d13  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x180007d1a  lea     r8d, [rdx+58h]; Size
0x180007d1e  call    memset_0
0x180007d23  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180007d27  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x180007d2e  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180007d32  mov     [rbp+57h+var_50], 2
0x180007d39  xor     ecx, ecx; hwnd
0x180007d3b  mov     [rbp+57h+var_48], rbx
0x180007d3f  call    cs:__imp_WinVerifyTrust
0x180007d45  mov     rcx, [rbp+57h+var_10]
0x180007d49  xor     rcx, rsp; StackCookie
0x180007d4c  call    __security_check_cookie
0x180007d51  mov     rbx, [rsp+0A0h+arg_8]
0x180007d59  add     rsp, 0A0h
0x180007d60  pop     rbp
0x180007d61  retn
```
