# WctIsRpcssPid(ulong)

- ea: `0x18005edf0`
- end: `0x18005ef7d`
- name: `?WctIsRpcssPid@@YAHK@Z`
- size: `397`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004e684`

## callees

- `0x180004bb4`
- `0x18001c650`
- `0x18001fe24`
- `0x18005edf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eed0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eeac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eeac`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005eea2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005ef11`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005eea2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005ef11`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005ee7c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005ee7c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef2a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef2a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef33`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005ee5c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005ee5c`

## pseudocode

```c
__int64 __fastcall WctIsRpcssPid(int a1)
{
  wchar_t *v2; // rcx
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  BYTE *v8; // rax
  BYTE *v9; // r14
  DWORD cbBufSize; // [rsp+70h] [rbp+40h] BYREF
  BYTE *v12; // [rsp+78h] [rbp+48h] BYREF
  __int64 v13; // [rsp+80h] [rbp+50h] BYREF

  cbBufSize = 0;
  v12 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( a1 )
  {
    v4 = OpenSCManagerW(0, 0, 1u);
    v5 = v4;
    if ( !v4 )
    {
LABEL_17:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v6 = OpenServiceW(v4, L"RPCSS", 4u);
    if ( !v6 )
    {
LABEL_16:
      CloseServiceHandle(v5);
      goto LABEL_17;
    }
    if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) )
    {
      v7 = 4096;
      cbBufSize = 4096;
    }
    else
    {
      if ( GetLastError() != 122 )
      {
LABEL_15:
        CloseServiceHandle(v6);
        goto LABEL_16;
      }
      v7 = cbBufSize;
    }
    v8 = (BYTE *)HeapAlloc(g_hWerheap, 0, v7);
    v12 = 0;
    v9 = v8;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v12);
    v13 = 0;
    v12 = v9;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v13);
    if ( v9 && QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, v9, cbBufSize, &cbBufSize) && a1 == *((_DWORD *)v9 + 7) )
      v3 = 1;
    goto LABEL_15;
  }
LABEL_18:
  if ( v2 != (wchar_t *)&WPP_GLOBAL_Control && (v2[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 37, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v3);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x18005edf0  push    rbp
0x18005edf2  push    rbx
0x18005edf3  push    rsi
0x18005edf4  push    rdi
0x18005edf5  push    r13
0x18005edf7  push    r14
0x18005edf9  push    r15
0x18005edfb  mov     rbp, rsp
0x18005edfe  sub     rsp, 30h
0x18005ee02  mov     r15d, ecx
0x18005ee05  mov     [rbp+cbBufSize], 0
0x18005ee0c  mov     [rbp+arg_8], 0
0x18005ee14  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee1b  lea     r13, WPP_GLOBAL_Control
0x18005ee22  cmp     rcx, r13
0x18005ee25  jz      short loc_18005EE49
0x18005ee27  test    byte ptr [rcx+1Ch], 4
0x18005ee2b  jz      short loc_18005EE49
0x18005ee2d  mov     rcx, [rcx+10h]
0x18005ee31  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005ee38  mov     edx, 24h ; '$'
0x18005ee3d  call    WPP_SF_
0x18005ee42  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee49  xor     ebx, ebx
0x18005ee4b  test    r15d, r15d
0x18005ee4e  jz      loc_18005EF40
0x18005ee54  xor     edx, edx; lpDatabaseName
0x18005ee56  lea     r8d, [rbx+1]; dwDesiredAccess
0x18005ee5a  xor     ecx, ecx; lpMachineName
0x18005ee5c  call    cs:__imp_OpenSCManagerW
0x18005ee62  mov     rsi, rax
0x18005ee65  test    rax, rax
0x18005ee68  jz      loc_18005EF39
0x18005ee6e  lea     r8d, [rbx+4]; dwDesiredAccess
0x18005ee72  mov     rcx, rax; hSCManager
0x18005ee75  lea     rdx, ServiceName; "RPCSS"
0x18005ee7c  call    cs:__imp_OpenServiceW
0x18005ee82  mov     rdi, rax
0x18005ee85  test    rax, rax
0x18005ee88  jz      loc_18005EF30
0x18005ee8e  lea     rax, [rbp+cbBufSize]
0x18005ee92  xor     r9d, r9d; cbBufSize
0x18005ee95  xor     r8d, r8d; lpBuffer
0x18005ee98  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005ee9d  xor     edx, edx; InfoLevel
0x18005ee9f  mov     rcx, rdi; hService
0x18005eea2  call    cs:__imp_QueryServiceStatusEx
0x18005eea8  test    eax, eax
0x18005eeaa  jnz     short loc_18005EEBC
0x18005eeac  call    cs:__imp_GetLastError
0x18005eeb2  cmp     eax, 7Ah ; 'z'
0x18005eeb5  jnz     short loc_18005EF27
0x18005eeb7  mov     eax, [rbp+cbBufSize]
0x18005eeba  jmp     short loc_18005EEC4
0x18005eebc  mov     eax, 1000h
0x18005eec1  mov     [rbp+cbBufSize], eax
0x18005eec4  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005eecb  xor     edx, edx; dwFlags
0x18005eecd  mov     r8d, eax; dwBytes
0x18005eed0  call    cs:__imp_HeapAlloc
0x18005eed6  lea     rcx, [rbp+arg_8]; void *
0x18005eeda  mov     [rbp+arg_8], rbx
0x18005eede  mov     r14, rax
0x18005eee1  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005eee6  lea     rcx, [rbp+arg_10]; void *
0x18005eeea  mov     [rbp+arg_10], rbx
0x18005eeee  mov     [rbp+arg_8], r14
0x18005eef2  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005eef7  test    r14, r14
0x18005eefa  jz      short loc_18005EF27
0x18005eefc  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18005ef00  lea     rax, [rbp+cbBufSize]
0x18005ef04  mov     r8, r14; lpBuffer
0x18005ef07  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005ef0c  xor     edx, edx; InfoLevel
0x18005ef0e  mov     rcx, rdi; hService
0x18005ef11  call    cs:__imp_QueryServiceStatusEx
0x18005ef17  test    eax, eax
0x18005ef19  jz      short loc_18005EF27
0x18005ef1b  cmp     r15d, [r14+1Ch]
0x18005ef1f  mov     eax, 1
0x18005ef24  cmovz   ebx, eax
0x18005ef27  mov     rcx, rdi; hSCObject
0x18005ef2a  call    cs:__imp_CloseServiceHandle
0x18005ef30  mov     rcx, rsi; hSCObject
0x18005ef33  call    cs:__imp_CloseServiceHandle
0x18005ef39  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef40  cmp     rcx, r13
0x18005ef43  jz      short loc_18005EF63
0x18005ef45  test    byte ptr [rcx+1Ch], 4
0x18005ef49  jz      short loc_18005EF63
0x18005ef4b  mov     rcx, [rcx+10h]
0x18005ef4f  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005ef56  mov     edx, 25h ; '%'
0x18005ef5b  mov     r9d, ebx
0x18005ef5e  call    WPP_SF_d
0x18005ef63  lea     rcx, [rbp+arg_8]; void *
0x18005ef67  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005ef6c  mov     eax, ebx
0x18005ef6e  add     rsp, 30h
0x18005ef72  pop     r15
0x18005ef74  pop     r14
0x18005ef76  pop     r13
0x18005ef78  pop     rdi
0x18005ef79  pop     rsi
0x18005ef7a  pop     rbx
0x18005ef7b  pop     rbp
0x18005ef7c  retn
```
