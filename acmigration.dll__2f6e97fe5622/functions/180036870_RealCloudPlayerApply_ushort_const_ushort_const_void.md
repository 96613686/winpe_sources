# RealCloudPlayerApply(ushort const *,ushort const *,void *)

- ea: `0x180036870`
- end: `0x1800369ed`
- name: `?RealCloudPlayerApply@@YAJPEBG0PEAX@Z`
- size: `381`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180036870`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180036897`
- `KERNEL32!GetLastError` at `0x1800368e2`
- `KERNEL32!GetLastError` at `0x180036967`
- `KERNEL32!GetLastError` at `0x1800369a5`
- `KERNEL32!GetLastError` at `0x180036897`
- `KERNEL32!GetLastError` at `0x1800368e2`
- `KERNEL32!GetLastError` at `0x180036967`
- `KERNEL32!GetLastError` at `0x1800369a5`
- `ADVAPI32!OpenSCManagerW` at `0x180036889`
- `ADVAPI32!OpenSCManagerW` at `0x180036889`
- `ADVAPI32!OpenServiceW` at `0x1800368d4`
- `ADVAPI32!OpenServiceW` at `0x1800368d4`
- `ADVAPI32!CloseServiceHandle` at `0x1800369bf`
- `ADVAPI32!CloseServiceHandle` at `0x1800369c8`
- `ADVAPI32!CloseServiceHandle` at `0x1800369bf`
- `ADVAPI32!CloseServiceHandle` at `0x1800369c8`
- `ADVAPI32!StartServiceW` at `0x18003699b`
- `ADVAPI32!StartServiceW` at `0x18003699b`
- `ADVAPI32!ChangeServiceConfigW` at `0x18003695d`
- `ADVAPI32!ChangeServiceConfigW` at `0x18003695d`

## string_xrefs

- `0x18003689d`: `Failed to open service control manager [%d]`
- `0x1800368ca`: `RealPlayerUpdateSvc`
- `0x1800368e8`: `Failed to open service [%d]`
- `0x18003696d`: `Failed to open change service state [%d]`
- `0x1800369ab`: `Failed to start service [%d]`

## pseudocode

```c
__int64 __fastcall RealCloudPlayerApply(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  signed int LastError; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD v8; // eax
  const char *v9; // r9
  __int64 v10; // r8
  LPCWSTR lpBinaryPathName; // [rsp+20h] [rbp-48h]

  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "RealCloudPlayerApply", 238, "Failed to open service control manager [%d]", LastError);
    goto LABEL_13;
  }
  v6 = OpenServiceW(v3, L"RealPlayerUpdateSvc", 0x12u);
  v7 = v6;
  if ( v6 )
  {
    if ( ChangeServiceConfigW(v6, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      if ( StartServiceW(v7, 0, 0) )
      {
        LastError = 0;
        goto LABEL_11;
      }
      v8 = GetLastError();
      v9 = "Failed to start service [%d]";
      v10 = 278;
    }
    else
    {
      v8 = GetLastError();
      v9 = "Failed to open change service state [%d]";
      v10 = 268;
    }
    LODWORD(lpBinaryPathName) = v8;
    LastError = v8;
    AslLogCallPrintf(1, "RealCloudPlayerApply", v10, v9, lpBinaryPathName);
LABEL_11:
    CloseServiceHandle(v7);
    goto LABEL_12;
  }
  LastError = GetLastError();
  AslLogCallPrintf(1, "RealCloudPlayerApply", 250, "Failed to open service [%d]", LastError);
LABEL_12:
  CloseServiceHandle(v4);
LABEL_13:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180036870  mov     [rsp+arg_0], rbx
0x180036875  mov     [rsp+arg_8], rsi
0x18003687a  push    rdi
0x18003687b  sub     rsp, 60h
0x18003687f  xor     edx, edx; lpDatabaseName
0x180036881  xor     ecx, ecx; lpMachineName
0x180036883  mov     r8d, 0F003Fh; dwDesiredAccess
0x180036889  call    cs:__imp_OpenSCManagerW
0x18003688f  mov     rsi, rax
0x180036892  test    rax, rax
0x180036895  jnz     short loc_1800368C4
0x180036897  call    cs:__imp_GetLastError
0x18003689d  lea     r9, aFailedToOpenSe_0; "Failed to open service control manager "...
0x1800368a4  mov     r8d, 0EEh
0x1800368aa  lea     rdx, aRealcloudplaye_0; "RealCloudPlayerApply"
0x1800368b1  mov     dword ptr [rsp+68h+lpBinaryPathName], eax
0x1800368b5  lea     ecx, [rsi+1]
0x1800368b8  mov     ebx, eax
0x1800368ba  call    AslLogCallPrintf
0x1800368bf  jmp     loc_1800369CE
0x1800368c4  mov     r8d, 12h; dwDesiredAccess
0x1800368ca  lea     rdx, ServiceName; "RealPlayerUpdateSvc"
0x1800368d1  mov     rcx, rsi; hSCManager
0x1800368d4  call    cs:__imp_OpenServiceW
0x1800368da  mov     rdi, rax
0x1800368dd  test    rax, rax
0x1800368e0  jnz     short loc_18003690F
0x1800368e2  call    cs:__imp_GetLastError
0x1800368e8  lea     r9, aFailedToOpenSe; "Failed to open service [%d]"
0x1800368ef  mov     r8d, 0FAh
0x1800368f5  lea     rdx, aRealcloudplaye_0; "RealCloudPlayerApply"
0x1800368fc  mov     dword ptr [rsp+68h+lpBinaryPathName], eax
0x180036900  lea     ecx, [rdi+1]
0x180036903  mov     ebx, eax
0x180036905  call    AslLogCallPrintf
0x18003690a  jmp     loc_1800369C5
0x18003690f  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x180036918  or      edx, 0FFFFFFFFh; dwServiceType
0x18003691b  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180036924  mov     r9d, edx; dwErrorControl
0x180036927  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180036930  mov     r8d, 2; dwStartType
0x180036936  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18003693f  mov     rcx, rdi; hService
0x180036942  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18003694b  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180036954  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18003695d  call    cs:__imp_ChangeServiceConfigW
0x180036963  test    eax, eax
0x180036965  jnz     short loc_180036993
0x180036967  call    cs:__imp_GetLastError
0x18003696d  lea     r9, aFailedToOpenCh; "Failed to open change service state [%d"...
0x180036974  mov     r8d, 10Ch
0x18003697a  lea     rdx, aRealcloudplaye_0; "RealCloudPlayerApply"
0x180036981  mov     dword ptr [rsp+68h+lpBinaryPathName], eax
0x180036985  mov     ecx, 1
0x18003698a  mov     ebx, eax
0x18003698c  call    AslLogCallPrintf
0x180036991  jmp     short loc_1800369BC
0x180036993  xor     r8d, r8d; lpServiceArgVectors
0x180036996  xor     edx, edx; dwNumServiceArgs
0x180036998  mov     rcx, rdi; hService
0x18003699b  call    cs:__imp_StartServiceW
0x1800369a1  test    eax, eax
0x1800369a3  jnz     short loc_1800369BA
0x1800369a5  call    cs:__imp_GetLastError
0x1800369ab  lea     r9, aFailedToStartS; "Failed to start service [%d]"
0x1800369b2  mov     r8d, 116h
0x1800369b8  jmp     short loc_18003697A
0x1800369ba  xor     ebx, ebx
0x1800369bc  mov     rcx, rdi; hSCObject
0x1800369bf  call    cs:__imp_CloseServiceHandle
0x1800369c5  mov     rcx, rsi; hSCObject
0x1800369c8  call    cs:__imp_CloseServiceHandle
0x1800369ce  test    ebx, ebx
0x1800369d0  jle     short loc_1800369DB
0x1800369d2  movzx   ebx, bx
0x1800369d5  or      ebx, 80070000h
0x1800369db  mov     rsi, [rsp+68h+arg_8]
0x1800369e0  mov     eax, ebx
0x1800369e2  mov     rbx, [rsp+68h+arg_0]
0x1800369e7  add     rsp, 60h
0x1800369eb  pop     rdi
0x1800369ec  retn
```
