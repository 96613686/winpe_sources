# ForceCryptServiceToStart

- ea: `0x18013a898`
- end: `0x18013aa35`
- name: `ForceCryptServiceToStart`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwStartType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000e340`

## callees

- `0x18004500c`
- `0x18013a898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18013aa13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18013aa13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a94e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a94e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a98a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a98a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013aa02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013aa0b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013aa02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013aa0b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18013a9e2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18013a9e2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18013a8cd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18013a8cd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18013a8ff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18013a8ff`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18013a9c3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18013a9c3`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18013a935`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18013a972`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18013a935`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18013a972`

## pseudocode

```c
__int64 __fastcall ForceCryptServiceToStart(LPCWSTR lpServiceName, DWORD dwStartType)
{
  unsigned int v4; // r14d
  SC_HANDLE v5; // rax
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // r9d
  SC_HANDLE v9; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r9d
  SC_HANDLE v15; // rdi
  struct _QUERY_SERVICE_CONFIGW *v16; // rax
  struct _QUERY_SERVICE_CONFIGW *v17; // rbp
  BOOL v18; // ebx
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  int lpBinaryPathName; // [rsp+20h] [rbp-68h]
  int lpLoadOrderGroup; // [rsp+28h] [rbp-60h]
  DWORD pcbBytesNeeded; // [rsp+A0h] [rbp+18h] BYREF

  pcbBytesNeeded = 0;
  v4 = 0;
  v5 = OpenSCManagerW(0, 0, 0xE0000000);
  v9 = v5;
  if ( v5 )
  {
    v11 = OpenServiceW(v5, lpServiceName, 0x13u);
    v15 = v11;
    if ( !v11 )
    {
      ErrLog_LogError(v13, v12, 0xC0u, v14, lpBinaryPathName, lpLoadOrderGroup);
      LastError = GetLastError();
LABEL_17:
      CloseServiceHandle(v9);
      goto LABEL_18;
    }
    if ( QueryServiceConfigW(v11, 0, 0, &pcbBytesNeeded) )
    {
      v16 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
      v17 = v16;
      if ( v16 )
      {
        v18 = !QueryServiceConfigW(v15, v16, pcbBytesNeeded, &pcbBytesNeeded);
        if ( v17->dwStartType == 4 )
          v18 = 1;
        LocalFree(v17);
        if ( !v18 )
          goto LABEL_21;
      }
    }
    if ( ChangeServiceConfigW(v15, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
LABEL_21:
      if ( StartServiceW(v15, 0, 0) )
      {
        v4 = 1;
        goto LABEL_16;
      }
      v22 = 259;
    }
    else
    {
      v22 = 250;
    }
    ErrLog_LogError(v20, v19, v22, v21, lpBinaryPathName, lpLoadOrderGroup);
LABEL_16:
    LastError = GetLastError();
    CloseServiceHandle(v15);
    goto LABEL_17;
  }
  ErrLog_LogError(v7, v6, 0xB6u, v8, lpBinaryPathName, lpLoadOrderGroup);
  LastError = GetLastError();
LABEL_18:
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x18013a898  mov     rax, rsp
0x18013a89b  mov     [rax+8], rbx
0x18013a89f  mov     [rax+10h], rbp
0x18013a8a3  mov     [rax+18h], r8d
0x18013a8a7  push    rsi
0x18013a8a8  push    rdi
0x18013a8a9  push    r13
0x18013a8ab  push    r14
0x18013a8ad  push    r15
0x18013a8af  sub     rsp, 60h
0x18013a8b3  mov     r15d, edx
0x18013a8b6  mov     dword ptr [rax+18h], 0
0x18013a8bd  mov     rbx, rcx
0x18013a8c0  xor     edx, edx; lpDatabaseName
0x18013a8c2  xor     ecx, ecx; lpMachineName
0x18013a8c4  mov     r8d, 0E0000000h; dwDesiredAccess
0x18013a8ca  xor     r14d, r14d
0x18013a8cd  call    cs:__imp_OpenSCManagerW
0x18013a8d3  mov     rsi, rax
0x18013a8d6  test    rax, rax
0x18013a8d9  jnz     short loc_18013A8F3
0x18013a8db  mov     r8d, 0B6h; unsigned int
0x18013a8e1  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18013a8e6  call    cs:__imp_GetLastError
0x18013a8ec  mov     ebx, eax
0x18013a8ee  jmp     loc_18013AA11
0x18013a8f3  mov     r8d, 13h; dwDesiredAccess
0x18013a8f9  mov     rdx, rbx; lpServiceName
0x18013a8fc  mov     rcx, rsi; hSCManager
0x18013a8ff  call    cs:__imp_OpenServiceW
0x18013a905  mov     rdi, rax
0x18013a908  test    rax, rax
0x18013a90b  jnz     short loc_18013A925
0x18013a90d  mov     r8d, 0C0h; unsigned int
0x18013a913  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18013a918  call    cs:__imp_GetLastError
0x18013a91e  mov     ebx, eax
0x18013a920  jmp     loc_18013AA08
0x18013a925  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18013a92d  xor     r8d, r8d; cbBufSize
0x18013a930  xor     edx, edx; lpServiceConfig
0x18013a932  mov     rcx, rdi; hService
0x18013a935  call    cs:__imp_QueryServiceConfigW
0x18013a93b  mov     r13d, 1
0x18013a941  test    eax, eax
0x18013a943  jz      short loc_18013A994
0x18013a945  mov     edx, [rsp+88h+pcbBytesNeeded]; uBytes
0x18013a94c  xor     ecx, ecx; uFlags
0x18013a94e  call    cs:__imp_LocalAlloc
0x18013a954  mov     rbp, rax
0x18013a957  test    rax, rax
0x18013a95a  jz      short loc_18013A994
0x18013a95c  mov     r8d, [rsp+88h+pcbBytesNeeded]; cbBufSize
0x18013a964  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18013a96c  mov     rdx, rax; lpServiceConfig
0x18013a96f  mov     rcx, rdi; hService
0x18013a972  call    cs:__imp_QueryServiceConfigW
0x18013a978  xor     ebx, ebx
0x18013a97a  mov     rcx, rbp; hMem
0x18013a97d  test    eax, eax
0x18013a97f  setz    bl
0x18013a982  cmp     dword ptr [rbp+4], 4
0x18013a986  cmovz   ebx, r13d
0x18013a98a  call    cs:__imp_LocalFree
0x18013a990  test    ebx, ebx
0x18013a992  jz      short loc_18013A9DA
0x18013a994  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x18013a999  or      edx, 0FFFFFFFFh; dwServiceType
0x18013a99c  mov     [rsp+88h+lpPassword], r14; lpPassword
0x18013a9a1  mov     r9d, edx; dwErrorControl
0x18013a9a4  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x18013a9a9  mov     r8d, r15d; dwStartType
0x18013a9ac  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x18013a9b1  mov     rcx, rdi; hService
0x18013a9b4  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x18013a9b9  mov     [rsp+88h+lpLoadOrderGroup], r14; int
0x18013a9be  mov     [rsp+88h+lpBinaryPathName], r14; int
0x18013a9c3  call    cs:__imp_ChangeServiceConfigW
0x18013a9c9  test    eax, eax
0x18013a9cb  jnz     short loc_18013A9DA
0x18013a9cd  mov     r8d, 0FAh; unsigned int
0x18013a9d3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18013a9d8  jmp     short loc_18013A9F7
0x18013a9da  xor     r8d, r8d; lpServiceArgVectors
0x18013a9dd  xor     edx, edx; dwNumServiceArgs
0x18013a9df  mov     rcx, rdi; hService
0x18013a9e2  call    cs:__imp_StartServiceW
0x18013a9e8  test    eax, eax
0x18013a9ea  jnz     short loc_18013A9F4
0x18013a9ec  mov     r8d, 103h
0x18013a9f2  jmp     short loc_18013A9D3
0x18013a9f4  mov     r14d, r13d
0x18013a9f7  call    cs:__imp_GetLastError
0x18013a9fd  mov     rcx, rdi; hSCObject
0x18013aa00  mov     ebx, eax
0x18013aa02  call    cs:__imp_CloseServiceHandle
0x18013aa08  mov     rcx, rsi; hSCObject
0x18013aa0b  call    cs:__imp_CloseServiceHandle
0x18013aa11  mov     ecx, ebx; dwErrCode
0x18013aa13  call    cs:__imp_SetLastError
0x18013aa19  lea     r11, [rsp+88h+var_28]
0x18013aa1e  mov     eax, r14d
0x18013aa21  mov     rbx, [r11+30h]
0x18013aa25  mov     rbp, [r11+38h]
0x18013aa29  mov     rsp, r11
0x18013aa2c  pop     r15
0x18013aa2e  pop     r14
0x18013aa30  pop     r13
0x18013aa32  pop     rdi
0x18013aa33  pop     rsi
0x18013aa34  retn
```
