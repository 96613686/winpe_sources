# VInitPrintVerifier

- ea: `0x1800359f4`
- end: `0x180035afe`
- name: `VInitPrintVerifier`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800492d0`

## callees

- `0x180033504`
- `0x1800359f4`
- `0x180035b04`
- `0x1800487e0`
- `0x1800491dc`
- `0x180075010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180035a50`
- `KERNEL32!GetSystemDirectoryW` at `0x180035a50`
- `KERNEL32!GetModuleHandleW` at `0x180035aa0`
- `KERNEL32!GetModuleHandleW` at `0x180035aa0`
- `KERNEL32!GetProcAddress` at `0x180035abc`
- `KERNEL32!GetProcAddress` at `0x180035abc`

## string_xrefs

- `0x180035a32`: `vfprint.dll`
- `0x180035a7b`: `vfprint.dll`

## pseudocode

```c
__int64 VInitPrintVerifier()
{
  __int64 SystemDirectoryW; // r9
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  pcchLength[0] = 0;
  if ( StringLengthWorkerW(L"vfprint.dll", 0x103u, pcchLength) < 0
    || (SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u), (unsigned __int64)(SystemDirectoryW - 1) > 0x101)
    || SystemDirectoryW + pcchLength[0] >= 0x103
    || (Buffer[SystemDirectoryW] = 92, StringCchCatW(Buffer, 0x104u, L"vfprint.dll") < 0) )
  {
    ghPrintVerifierModule = 0;
LABEL_9:
    result = 0;
    goto LABEL_10;
  }
  ModuleHandleW = GetModuleHandleW(Buffer);
  ghPrintVerifierModule = ModuleHandleW;
  if ( !ModuleHandleW )
    goto LABEL_9;
  ProcAddress = GetProcAddress(ModuleHandleW, "PrintVerifierIsLayerEnabled");
  if ( !ProcAddress )
    goto LABEL_9;
  result = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
LABEL_10:
  gbPrintVerifierDriverLayerEnabled = result;
  return result;
}

```

## disassembly

```asm
0x1800359f4  sub     rsp, 258h
0x1800359fb  mov     rax, cs:__security_cookie
0x180035a02  xor     rax, rsp
0x180035a05  mov     [rsp+258h+var_18], rax
0x180035a0d  xor     edx, edx; Val
0x180035a0f  lea     rcx, [rsp+258h+Buffer]; void *
0x180035a14  mov     r8d, 208h; Size
0x180035a1a  call    memset_0
0x180035a1f  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x180035a24  mov     [rsp+258h+pcchLength], 0
0x180035a2d  mov     edx, 103h; cchMax
0x180035a32  lea     rcx, aVfprintDll; "vfprint.dll"
0x180035a39  call    StringLengthWorkerW
0x180035a3e  test    eax, eax
0x180035a40  js      loc_180035AD3
0x180035a46  mov     edx, 104h; uSize
0x180035a4b  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180035a50  call    cs:__imp_GetSystemDirectoryW
0x180035a56  mov     r9d, eax
0x180035a59  lea     rax, [r9-1]
0x180035a5d  cmp     rax, 101h
0x180035a63  ja      short loc_180035AD3
0x180035a65  mov     rcx, [rsp+258h+pcchLength]
0x180035a6a  add     rcx, r9
0x180035a6d  cmp     rcx, 103h
0x180035a74  jnb     short loc_180035AD3
0x180035a76  mov     eax, 5Ch ; '\'
0x180035a7b  lea     r8, aVfprintDll; "vfprint.dll"
0x180035a82  mov     edx, 104h; cchDest
0x180035a87  mov     [rsp+r9*2+258h+Buffer], ax
0x180035a8d  lea     rcx, [rsp+258h+Buffer]; pszDest
0x180035a92  call    StringCchCatW
0x180035a97  test    eax, eax
0x180035a99  js      short loc_180035AD3
0x180035a9b  lea     rcx, [rsp+258h+Buffer]; lpModuleName
0x180035aa0  call    cs:__imp_GetModuleHandleW
0x180035aa6  mov     cs:ghPrintVerifierModule, rax
0x180035aad  test    rax, rax
0x180035ab0  jz      short loc_180035ADE
0x180035ab2  lea     rdx, aPrintverifieri; "PrintVerifierIsLayerEnabled"
0x180035ab9  mov     rcx, rax; hModule
0x180035abc  call    cs:__imp_GetProcAddress
0x180035ac2  test    rax, rax
0x180035ac5  jz      short loc_180035ADE
0x180035ac7  mov     ecx, 2
0x180035acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ad1  jmp     short loc_180035AE0
0x180035ad3  mov     cs:ghPrintVerifierModule, 0
0x180035ade  xor     eax, eax
0x180035ae0  mov     cs:gbPrintVerifierDriverLayerEnabled, eax
0x180035ae6  mov     rcx, [rsp+258h+var_18]
0x180035aee  xor     rcx, rsp; StackCookie
0x180035af1  call    __security_check_cookie
0x180035af6  add     rsp, 258h
0x180035afd  retn
```
