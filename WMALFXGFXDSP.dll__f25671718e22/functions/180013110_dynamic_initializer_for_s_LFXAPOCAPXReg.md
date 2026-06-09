# _dynamic_initializer_for__s_LFXAPOCAPXReg__

- ea: `0x180013110`
- end: `0x1800131c4`
- name: `_dynamic_initializer_for__s_LFXAPOCAPXReg__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015ea8`

## string_xrefs

- `0x180013137`: `Copyright Microsoft`

## pseudocode

```c
__int64 dynamic_initializer_for__s_LFXAPOCAPXReg__()
{
  __int64 result; // rax

  xmmword_1801B7BA0 = (__int128)CLSID_CWMAudioCAPXLFXAPO;
  memset_0(qword_1801B7BE0, 0, 0x1D4u);
  xmmword_1801B7DB4 = *(_OWORD *)L"Copyright Microsoft";
  qword_1801B7DD4 = *(_QWORD *)L"oft";
  xmmword_1801B7DC4 = *(_OWORD *)L"t Microsoft";
  memset_0(&dword_1801B7DDC, 0, 0x1D8u);
  result = 1;
  dword_1801B7FCC = -1;
  dword_1801B7FB4 = 1;
  xmmword_1801B7FD4 = (__int128)GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10;
  dword_1801B7FB8 = 1;
  dword_1801B7FBC = 1;
  dword_1801B7FC0 = 1;
  dword_1801B7FC4 = 1;
  dword_1801B7FC8 = 1;
  dword_1801B7FD0 = 1;
  return result;
}

```

## disassembly

```asm
0x180013110  sub     rsp, 28h
0x180013114  movups  xmm0, xmmword ptr cs:CLSID_CWMAudioCAPXLFXAPO.Data1
0x18001311b  xor     edx, edx; Val
0x18001311d  lea     rcx, qword_1801B7BE0; void *
0x180013124  mov     r8d, 1D4h; Size
0x18001312a  movdqu  cs:xmmword_1801B7BA0, xmm0
0x180013132  call    memset_0
0x180013137  movups  xmm0, xmmword ptr cs:aCopyrightMicro; "Copyright Microsoft"
0x18001313e  xor     edx, edx; Val
0x180013140  mov     r8d, 1D8h; Size
0x180013146  movups  xmm1, xmmword ptr cs:aCopyrightMicro+10h; "t Microsoft"
0x18001314d  lea     rcx, dword_1801B7DDC; void *
0x180013154  movups  cs:xmmword_1801B7DB4, xmm0
0x18001315b  movsd   xmm0, qword ptr cs:aCopyrightMicro+20h; "oft"
0x180013163  movsd   cs:qword_1801B7DD4, xmm0
0x18001316b  movups  cs:xmmword_1801B7DC4, xmm1
0x180013172  call    memset_0
0x180013177  movups  xmm0, xmmword ptr cs:_GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10.Data1
0x18001317e  mov     eax, 1
0x180013183  mov     cs:dword_1801B7FCC, 0FFFFFFFFh
0x18001318d  mov     cs:dword_1801B7FB4, eax
0x180013193  movdqu  cs:xmmword_1801B7FD4, xmm0
0x18001319b  mov     cs:dword_1801B7FB8, eax
0x1800131a1  mov     cs:dword_1801B7FBC, eax
0x1800131a7  mov     cs:dword_1801B7FC0, eax
0x1800131ad  mov     cs:dword_1801B7FC4, eax
0x1800131b3  mov     cs:dword_1801B7FC8, eax
0x1800131b9  mov     cs:dword_1801B7FD0, eax
0x1800131bf  add     rsp, 28h
0x1800131c3  retn
```
