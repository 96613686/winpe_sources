# DriverPackageSupportsNativeArchitecture

- ea: `0x140013140`
- end: `0x1400131e2`
- name: `DriverPackageSupportsNativeArchitecture`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013220`

## callees

- `0x140013140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131ab`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14001316d`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14001316d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400131c6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400131c6`
- `drvstore!DriverPackageEnumOsVersionsW` at `0x14001319f`
- `drvstore!DriverPackageEnumOsVersionsW` at `0x14001319f`

## pseudocode

```c
__int64 __fastcall DriverPackageSupportsNativeArchitecture(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  struct _SYSTEM_INFO v7; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  memset(&v7, 0, sizeof(v7));
  GetNativeSystemInfo(&v7);
  WORD2(v8) = v7.wProcessorArchitecture;
  LODWORD(v8) = 0;
  if ( (unsigned int)DriverPackageEnumOsVersionsW(a1, 0, DriverPackageSupportsNativeArchitectureCallback, &v8) )
  {
    return (unsigned int)v8;
  }
  else
  {
    v4 = 0;
    LastError = GetLastError();
    DevRtlWriteTextLog(
      a2,
      1,
      2,
      "Unable to determine if driver package supports the native architecture. Error = 0x%08X",
      LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x140013140  mov     rax, rsp
0x140013143  mov     [rax+8], rbx
0x140013147  push    rdi
0x140013148  sub     rsp, 60h
0x14001314c  xorps   xmm0, xmm0
0x14001314f  mov     qword ptr [rax+18h], 0
0x140013157  mov     rbx, rcx
0x14001315a  mov     rdi, rdx
0x14001315d  lea     rcx, [rax-38h]; lpSystemInfo
0x140013161  movups  xmmword ptr [rax-38h], xmm0
0x140013165  movups  xmmword ptr [rax-28h], xmm0
0x140013169  movups  xmmword ptr [rax-18h], xmm0
0x14001316d  call    cs:__imp_GetNativeSystemInfo
0x140013173  movzx   eax, word ptr [rsp+68h+var_38]
0x140013178  lea     r9, [rsp+68h+arg_10]
0x140013180  lea     r8, DriverPackageSupportsNativeArchitectureCallback
0x140013187  mov     [rsp+68h+arg_14], ax
0x14001318f  xor     edx, edx
0x140013191  mov     [rsp+68h+arg_10], 0
0x14001319c  mov     rcx, rbx
0x14001319f  call    cs:__imp_DriverPackageEnumOsVersionsW
0x1400131a5  test    eax, eax
0x1400131a7  jnz     short loc_1400131CE
0x1400131a9  xor     ebx, ebx
0x1400131ab  call    cs:__imp_GetLastError
0x1400131b1  lea     r9, aUnableToDeterm_2; "Unable to determine if driver package s"...
0x1400131b8  mov     rcx, rdi
0x1400131bb  lea     edx, [rbx+1]
0x1400131be  mov     [rsp+68h+var_48], eax
0x1400131c2  lea     r8d, [rbx+2]
0x1400131c6  call    cs:__imp_DevRtlWriteTextLog
0x1400131cc  jmp     short loc_1400131D5
0x1400131ce  mov     ebx, [rsp+68h+arg_10]
0x1400131d5  mov     eax, ebx
0x1400131d7  mov     rbx, [rsp+68h+arg_0]
0x1400131dc  add     rsp, 60h
0x1400131e0  pop     rdi
0x1400131e1  retn
```
