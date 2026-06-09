# NS_AdminProtectionGeneral::DsLaunchPCAUI

- ea: `0x180055eb0`
- end: `0x180055f4d`
- name: `NS_AdminProtectionGeneral::DsLaunchPCAUI`
- size: `157`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055f54`

## callees

- `0x180055eb0`
- `0x180059235`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f3e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180055f24`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180055f24`

## pseudocode

```c
BOOL __fastcall NS_AdminProtectionGeneral::DsLaunchPCAUI(LPWSTR lpCommandLine)
{
  BOOL result; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  result = CreateProcessW(0, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation);
  if ( result )
  {
    CloseHandle(ProcessInformation.hProcess);
    return CloseHandle(ProcessInformation.hThread);
  }
  return result;
}

```

## disassembly

```asm
0x180055eb0  push    rbx
0x180055eb2  sub     rsp, 0E0h
0x180055eb9  xor     edx, edx; Val
0x180055ebb  mov     rbx, rcx
0x180055ebe  lea     rcx, [rsp+0E8h+StartupInfo+4]; void *
0x180055ec3  lea     r8d, [rdx+64h]; Size
0x180055ec7  call    memset_0
0x180055ecc  xor     eax, eax
0x180055ece  mov     [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x180055ed6  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x180055edb  xorps   xmm0, xmm0
0x180055ede  lea     rax, [rsp+0E8h+ProcessInformation]
0x180055ee3  xor     r9d, r9d; lpThreadAttributes
0x180055ee6  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x180055eeb  xor     r8d, r8d; lpProcessAttributes
0x180055eee  lea     rax, [rsp+0E8h+StartupInfo]
0x180055ef3  mov     rdx, rbx; lpCommandLine
0x180055ef6  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x180055efb  xor     ecx, ecx; lpApplicationName
0x180055efd  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180055f06  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x180055f0f  mov     [rsp+0E8h+dwCreationFlags], 0; dwCreationFlags
0x180055f17  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x180055f1f  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x180055f24  call    cs:__imp_CreateProcessW
0x180055f2a  test    eax, eax
0x180055f2c  jz      short loc_180055F44
0x180055f2e  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x180055f33  call    cs:__imp_CloseHandle
0x180055f39  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x180055f3e  call    cs:__imp_CloseHandle
0x180055f44  add     rsp, 0E0h
0x180055f4b  pop     rbx
0x180055f4c  retn
```
