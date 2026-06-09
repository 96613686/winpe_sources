# GetAppIdConfig(ulong *)

- ea: `0x140005534`
- end: `0x14000562c`
- name: `?GetAppIdConfig@@YAKPEAK@Z`
- size: `248`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14000458c`

## callees

- `0x14000157c`
- `0x140001588`
- `0x140005534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000558f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000558f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055bb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140005559`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140005559`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140005581`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140005581`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400055f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400055ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400055f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400055ff`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400055a6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400055e1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400055a6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400055e1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140005605`

## pseudocode

```c
__int64 __fastcall GetAppIdConfig(unsigned int *a1)
{
  struct _QUERY_SERVICE_CONFIGW *v1; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbp
  DWORD LastError; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD pcbBytesNeeded; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  pcbBytesNeeded = 0;
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, L"AppID", 1u);
    v7 = v6;
    if ( v6 )
    {
      if ( (QueryServiceConfigW(v6, 0, 0, &pcbBytesNeeded) || GetLastError() == 122)
        && (v1 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded),
            QueryServiceConfigW(v7, v1, pcbBytesNeeded, &pcbBytesNeeded)) )
      {
        LastError = 0;
        *a1 = v1->dwStartType;
      }
      else
      {
        LastError = GetLastError();
      }
      CloseServiceHandle(v7);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v4);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( &QueryServiceConfigW )
    operator delete(v1);
  return LastError;
}

```

## disassembly

```asm
0x140005534  mov     [rsp+arg_0], rbx
0x140005539  mov     [rsp+arg_10], rbp
0x14000553e  push    rsi
0x14000553f  push    rdi
0x140005540  push    r14
0x140005542  sub     rsp, 20h
0x140005546  xor     esi, esi
0x140005548  mov     r14, rcx
0x14000554b  xor     edx, edx; lpDatabaseName
0x14000554d  mov     [rsp+38h+pcbBytesNeeded], esi
0x140005551  xor     ecx, ecx; lpMachineName
0x140005553  lea     ebx, [rsi+1]
0x140005556  mov     r8d, ebx; dwDesiredAccess
0x140005559  call    cs:__imp_OpenSCManagerW
0x14000555f  mov     rbp, rax
0x140005562  test    rax, rax
0x140005565  jnz     short loc_140005574
0x140005567  call    cs:__imp_GetLastError
0x14000556d  mov     ebx, eax
0x14000556f  jmp     loc_140005605
0x140005574  mov     r8d, ebx; dwDesiredAccess
0x140005577  lea     rdx, ServiceName; "AppID"
0x14000557e  mov     rcx, rbp; hSCManager
0x140005581  call    cs:__imp_OpenServiceW
0x140005587  mov     rdi, rax
0x14000558a  test    rax, rax
0x14000558d  jnz     short loc_140005599
0x14000558f  call    cs:__imp_GetLastError
0x140005595  mov     ebx, eax
0x140005597  jmp     short loc_1400055FC
0x140005599  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x14000559e  xor     r8d, r8d; cbBufSize
0x1400055a1  xor     edx, edx; lpServiceConfig
0x1400055a3  mov     rcx, rdi; hService
0x1400055a6  call    cs:__imp_QueryServiceConfigW
0x1400055ac  test    eax, eax
0x1400055ae  jnz     short loc_1400055C5
0x1400055b0  call    cs:__imp_GetLastError
0x1400055b6  cmp     eax, 7Ah ; 'z'
0x1400055b9  jz      short loc_1400055C5
0x1400055bb  call    cs:__imp_GetLastError
0x1400055c1  mov     ebx, eax
0x1400055c3  jmp     short loc_1400055F3
0x1400055c5  mov     ecx, [rsp+38h+pcbBytesNeeded]; unsigned __int64
0x1400055c9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400055ce  mov     r8d, [rsp+38h+pcbBytesNeeded]; cbBufSize
0x1400055d3  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x1400055d8  mov     rdx, rax; lpServiceConfig
0x1400055db  mov     rcx, rdi; hService
0x1400055de  mov     rsi, rax
0x1400055e1  call    cs:__imp_QueryServiceConfigW
0x1400055e7  test    eax, eax
0x1400055e9  jz      short loc_1400055BB
0x1400055eb  mov     eax, [rsi+4]
0x1400055ee  xor     ebx, ebx
0x1400055f0  mov     [r14], eax
0x1400055f3  mov     rcx, rdi; hSCObject
0x1400055f6  call    cs:__imp_CloseServiceHandle
0x1400055fc  mov     rcx, rbp; hSCObject
0x1400055ff  call    cs:__imp_CloseServiceHandle
0x140005605  cmp     cs:__imp_QueryServiceConfigW, 0
0x14000560d  jz      short loc_140005617
0x14000560f  mov     rcx, rsi; Block
0x140005612  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005617  mov     rbp, [rsp+38h+arg_10]
0x14000561c  mov     eax, ebx
0x14000561e  mov     rbx, [rsp+38h+arg_0]
0x140005623  add     rsp, 20h
0x140005627  pop     r14
0x140005629  pop     rdi
0x14000562a  pop     rsi
0x14000562b  retn
```
