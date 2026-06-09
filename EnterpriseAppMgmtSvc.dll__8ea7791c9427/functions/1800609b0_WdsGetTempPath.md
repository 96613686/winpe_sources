# WdsGetTempPath

- ea: `0x1800609b0`
- end: `0x180060a8d`
- name: `WdsGetTempPath`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005fc68`

## callees

- `0x1800609b0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060a32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060a32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800609fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060a7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060a7c`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180060a4e`

## string_xrefs

- `0x1800609ce`: `kernelbase.dll`
- `0x180060a26`: `GetTempPath2W`
- `0x1800609f7`: `api-ms-win-core-file-l1-2-4.dll`
- `0x1800609e5`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall WdsGetTempPath(unsigned int a1, __int64 a2)
{
  __int64 (__fastcall *ProcAddress)(_QWORD, __int64); // rax
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // ebx
  unsigned int v7; // edi

  ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))qword_180090ED0;
  if ( qword_180090ED0 )
    goto LABEL_14;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
    {
      ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-file-l1-2-4.dll");
      if ( !ModuleHandleW )
      {
        LastError = GetLastError();
LABEL_6:
        ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))qword_180090ED0;
        goto LABEL_7;
      }
    }
  }
  LastError = 0;
  ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))GetProcAddress(ModuleHandleW, "GetTempPath2W");
  qword_180090ED0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_14:
    v7 = ProcAddress(a1, a2);
    if ( v7 )
      LastError = 0;
    else
      LastError = GetLastError();
    goto LABEL_17;
  }
  if ( GetLastError() != 127 )
    goto LABEL_6;
  ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))GetTempPathW;
  qword_180090ED0 = (__int64)GetTempPathW;
LABEL_7:
  if ( ProcAddress )
    goto LABEL_14;
  v7 = 0;
  if ( !LastError )
    LastError = 127;
LABEL_17:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x1800609b0  push    rbx
0x1800609b2  push    rbp
0x1800609b3  push    rsi
0x1800609b4  push    rdi
0x1800609b5  sub     rsp, 28h
0x1800609b9  mov     rax, cs:qword_180090ED0
0x1800609c0  mov     rdi, rdx
0x1800609c3  mov     esi, ecx
0x1800609c5  test    rax, rax
0x1800609c8  jnz     loc_180060A5E
0x1800609ce  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800609d5  call    cs:__imp_GetModuleHandleW
0x1800609db  mov     ebp, 7Fh
0x1800609e0  test    rax, rax
0x1800609e3  jnz     short loc_180060A26
0x1800609e5  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800609ec  call    cs:__imp_GetModuleHandleW
0x1800609f2  test    rax, rax
0x1800609f5  jnz     short loc_180060A26
0x1800609f7  lea     rcx, aApiMsWinCoreFi_3; "api-ms-win-core-file-l1-2-4.dll"
0x1800609fe  call    cs:__imp_GetModuleHandleW
0x180060a04  test    rax, rax
0x180060a07  jnz     short loc_180060A26
0x180060a09  call    cs:__imp_GetLastError
0x180060a0f  mov     ebx, eax
0x180060a11  mov     rax, cs:qword_180090ED0
0x180060a18  test    rax, rax
0x180060a1b  jnz     short loc_180060A5E
0x180060a1d  xor     edi, edi
0x180060a1f  test    ebx, ebx
0x180060a21  cmovz   ebx, ebp
0x180060a24  jmp     short loc_180060A7A
0x180060a26  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180060a2d  mov     rcx, rax; hModule
0x180060a30  xor     ebx, ebx
0x180060a32  call    cs:__imp_GetProcAddress
0x180060a38  mov     cs:qword_180090ED0, rax
0x180060a3f  test    rax, rax
0x180060a42  jnz     short loc_180060A5E
0x180060a44  call    cs:__imp_GetLastError
0x180060a4a  cmp     eax, ebp
0x180060a4c  jnz     short loc_180060A11
0x180060a4e  mov     rax, cs:__imp_GetTempPathW
0x180060a55  mov     cs:qword_180090ED0, rax
0x180060a5c  jmp     short loc_180060A18
0x180060a5e  mov     rdx, rdi
0x180060a61  mov     ecx, esi
0x180060a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a68  mov     edi, eax
0x180060a6a  test    eax, eax
0x180060a6c  jz      short loc_180060A72
0x180060a6e  xor     ebx, ebx
0x180060a70  jmp     short loc_180060A7A
0x180060a72  call    cs:__imp_GetLastError
0x180060a78  mov     ebx, eax
0x180060a7a  mov     ecx, ebx; dwErrCode
0x180060a7c  call    cs:__imp_SetLastError
0x180060a82  mov     eax, edi
0x180060a84  add     rsp, 28h
0x180060a88  pop     rdi
0x180060a89  pop     rsi
0x180060a8a  pop     rbp
0x180060a8b  pop     rbx
0x180060a8c  retn
```
