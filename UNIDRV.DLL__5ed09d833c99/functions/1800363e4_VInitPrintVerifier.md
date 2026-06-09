# VInitPrintVerifier

- ea: `0x1800363e4`
- end: `0x180036501`
- name: `VInitPrintVerifier`
- size: `285`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004a820`

## callees

- `0x180033e78`
- `0x1800363e4`
- `0x180036508`
- `0x180049d00`
- `0x18004a71c`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180036440`
- `KERNEL32!GetSystemDirectoryW` at `0x180036440`
- `KERNEL32!GetModuleHandleW` at `0x180036496`
- `KERNEL32!GetModuleHandleW` at `0x180036496`
- `KERNEL32!GetProcAddress` at `0x1800364b8`
- `KERNEL32!GetProcAddress` at `0x1800364b8`

## string_xrefs

- `0x180036422`: `vfprint.dll`
- `0x180036471`: `vfprint.dll`

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
0x1800363e4  sub     rsp, 258h
0x1800363eb  mov     rax, cs:__security_cookie
0x1800363f2  xor     rax, rsp
0x1800363f5  mov     [rsp+258h+var_18], rax
0x1800363fd  xor     edx, edx; Val
0x1800363ff  lea     rcx, [rsp+258h+Buffer]; void *
0x180036404  mov     r8d, 208h; Size
0x18003640a  call    memset_0
0x18003640f  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x180036414  mov     [rsp+258h+pcchLength], 0
0x18003641d  mov     edx, 103h; cchMax
0x180036422  lea     rcx, aVfprintDll; "vfprint.dll"
0x180036429  call    StringLengthWorkerW
0x18003642e  test    eax, eax
0x180036430  js      loc_1800364D5
0x180036436  mov     edx, 104h; uSize
0x18003643b  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180036440  call    cs:__imp_GetSystemDirectoryW
0x180036447  nop     dword ptr [rax+rax+00h]
0x18003644c  mov     r9d, eax
0x18003644f  lea     rax, [r9-1]
0x180036453  cmp     rax, 101h
0x180036459  ja      short loc_1800364D5
0x18003645b  mov     rcx, [rsp+258h+pcchLength]
0x180036460  add     rcx, r9
0x180036463  cmp     rcx, 103h
0x18003646a  jnb     short loc_1800364D5
0x18003646c  mov     eax, 5Ch ; '\'
0x180036471  lea     r8, aVfprintDll; "vfprint.dll"
0x180036478  mov     edx, 104h; cchDest
0x18003647d  mov     [rsp+r9*2+258h+Buffer], ax
0x180036483  lea     rcx, [rsp+258h+Buffer]; pszDest
0x180036488  call    StringCchCatW
0x18003648d  test    eax, eax
0x18003648f  js      short loc_1800364D5
0x180036491  lea     rcx, [rsp+258h+Buffer]; lpModuleName
0x180036496  call    cs:__imp_GetModuleHandleW
0x18003649d  nop     dword ptr [rax+rax+00h]
0x1800364a2  mov     cs:ghPrintVerifierModule, rax
0x1800364a9  test    rax, rax
0x1800364ac  jz      short loc_1800364E0
0x1800364ae  lea     rdx, aPrintverifieri; "PrintVerifierIsLayerEnabled"
0x1800364b5  mov     rcx, rax; hModule
0x1800364b8  call    cs:__imp_GetProcAddress
0x1800364bf  nop     dword ptr [rax+rax+00h]
0x1800364c4  test    rax, rax
0x1800364c7  jz      short loc_1800364E0
0x1800364c9  mov     ecx, 2
0x1800364ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d3  jmp     short loc_1800364E2
0x1800364d5  mov     cs:ghPrintVerifierModule, 0
0x1800364e0  xor     eax, eax
0x1800364e2  mov     cs:gbPrintVerifierDriverLayerEnabled, eax
0x1800364e8  mov     rcx, [rsp+258h+var_18]
0x1800364f0  xor     rcx, rsp; StackCookie
0x1800364f3  call    __security_check_cookie
0x1800364f8  add     rsp, 258h
0x1800364ff  retn
```
