# WdsGetTempPath

- ea: `0x180065c50`
- end: `0x180065d5e`
- name: `WdsGetTempPath`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180064da0`

## callees

- `0x180065c50`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180065cea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180065cea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065c75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065c92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065c75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065c92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065d46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065d46`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180065d12`

## string_xrefs

- `0x180065c6e`: `kernelbase.dll`
- `0x180065cde`: `GetTempPath2W`
- `0x180065ca3`: `api-ms-win-core-file-l1-2-4.dll`
- `0x180065c8b`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall WdsGetTempPath(unsigned int a1, __int64 a2)
{
  __int64 (__fastcall *ProcAddress)(_QWORD, __int64); // rax
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // ebx
  unsigned int v7; // edi

  ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))qword_180096ED0;
  if ( qword_180096ED0 )
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
        ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))qword_180096ED0;
        goto LABEL_7;
      }
    }
  }
  LastError = 0;
  ProcAddress = (__int64 (__fastcall *)(_QWORD, __int64))GetProcAddress(ModuleHandleW, "GetTempPath2W");
  qword_180096ED0 = (__int64)ProcAddress;
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
  qword_180096ED0 = (__int64)GetTempPathW;
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
0x180065c50  push    rbx
0x180065c52  push    rbp
0x180065c53  push    rsi
0x180065c54  push    rdi
0x180065c55  sub     rsp, 28h
0x180065c59  mov     rax, cs:qword_180096ED0
0x180065c60  mov     rdi, rdx
0x180065c63  mov     esi, ecx
0x180065c65  test    rax, rax
0x180065c68  jnz     loc_180065D22
0x180065c6e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180065c75  call    cs:__imp_GetModuleHandleW
0x180065c7c  nop     dword ptr [rax+rax+00h]
0x180065c81  mov     ebp, 7Fh
0x180065c86  test    rax, rax
0x180065c89  jnz     short loc_180065CDE
0x180065c8b  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180065c92  call    cs:__imp_GetModuleHandleW
0x180065c99  nop     dword ptr [rax+rax+00h]
0x180065c9e  test    rax, rax
0x180065ca1  jnz     short loc_180065CDE
0x180065ca3  lea     rcx, aApiMsWinCoreFi_3; "api-ms-win-core-file-l1-2-4.dll"
0x180065caa  call    cs:__imp_GetModuleHandleW
0x180065cb1  nop     dword ptr [rax+rax+00h]
0x180065cb6  test    rax, rax
0x180065cb9  jnz     short loc_180065CDE
0x180065cbb  call    cs:__imp_GetLastError
0x180065cc2  nop     dword ptr [rax+rax+00h]
0x180065cc7  mov     ebx, eax
0x180065cc9  mov     rax, cs:qword_180096ED0
0x180065cd0  test    rax, rax
0x180065cd3  jnz     short loc_180065D22
0x180065cd5  xor     edi, edi
0x180065cd7  test    ebx, ebx
0x180065cd9  cmovz   ebx, ebp
0x180065cdc  jmp     short loc_180065D44
0x180065cde  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180065ce5  mov     rcx, rax; hModule
0x180065ce8  xor     ebx, ebx
0x180065cea  call    cs:__imp_GetProcAddress
0x180065cf1  nop     dword ptr [rax+rax+00h]
0x180065cf6  mov     cs:qword_180096ED0, rax
0x180065cfd  test    rax, rax
0x180065d00  jnz     short loc_180065D22
0x180065d02  call    cs:__imp_GetLastError
0x180065d09  nop     dword ptr [rax+rax+00h]
0x180065d0e  cmp     eax, ebp
0x180065d10  jnz     short loc_180065CC9
0x180065d12  mov     rax, cs:__imp_GetTempPathW
0x180065d19  mov     cs:qword_180096ED0, rax
0x180065d20  jmp     short loc_180065CD0
0x180065d22  mov     rdx, rdi
0x180065d25  mov     ecx, esi
0x180065d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d2c  mov     edi, eax
0x180065d2e  test    eax, eax
0x180065d30  jz      short loc_180065D36
0x180065d32  xor     ebx, ebx
0x180065d34  jmp     short loc_180065D44
0x180065d36  call    cs:__imp_GetLastError
0x180065d3d  nop     dword ptr [rax+rax+00h]
0x180065d42  mov     ebx, eax
0x180065d44  mov     ecx, ebx; dwErrCode
0x180065d46  call    cs:__imp_SetLastError
0x180065d4d  nop     dword ptr [rax+rax+00h]
0x180065d52  mov     eax, edi
0x180065d54  add     rsp, 28h
0x180065d58  pop     rdi
0x180065d59  pop     rsi
0x180065d5a  pop     rbp
0x180065d5b  pop     rbx
0x180065d5c  retn
```
