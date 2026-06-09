# AipFreeFileSignature

- ea: `0x180009fa8`
- end: `0x18000a03e`
- name: `AipFreeFileSignature`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c28`
- `0x180008c14`
- `0x18000a0f8`
- `0x18000a708`

## callees

- `0x180009fa8`
- `0x18000c0a2`
- `0x18000c0e0`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x18000a01b`
- `WINTRUST!WinVerifyTrust` at `0x18000a01b`

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
0x180009fa8  test    rcx, rcx
0x180009fab  jz      locret_18000A03D
0x180009fb1  mov     [rsp-8+arg_8], rbx
0x180009fb6  push    rbp
0x180009fb7  lea     rbp, [rsp-57h]
0x180009fbc  sub     rsp, 0A0h
0x180009fc3  mov     rax, cs:__security_cookie
0x180009fca  xor     rax, rsp
0x180009fcd  mov     [rbp+57h+var_10], rax
0x180009fd1  xor     edx, edx; Val
0x180009fd3  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x180009fda  mov     rbx, rcx
0x180009fdd  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x180009fe4  lea     rcx, [rbp+57h+pWVTData]; void *
0x180009fe8  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x180009fef  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x180009ff6  lea     r8d, [rdx+58h]; Size
0x180009ffa  call    memset_0
0x180009fff  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x18000a003  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x18000a00a  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x18000a00e  mov     [rbp+57h+var_50], 2
0x18000a015  xor     ecx, ecx; hwnd
0x18000a017  mov     [rbp+57h+var_48], rbx
0x18000a01b  call    cs:__imp_WinVerifyTrust
0x18000a021  mov     rcx, [rbp+57h+var_10]
0x18000a025  xor     rcx, rsp; StackCookie
0x18000a028  call    __security_check_cookie
0x18000a02d  mov     rbx, [rsp+0A0h+arg_8]
0x18000a035  add     rsp, 0A0h
0x18000a03c  pop     rbp
0x18000a03d  retn
```
