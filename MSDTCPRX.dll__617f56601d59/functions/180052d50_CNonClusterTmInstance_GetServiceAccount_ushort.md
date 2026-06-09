# CNonClusterTmInstance::GetServiceAccount(ushort * *)

- ea: `0x180052d50`
- end: `0x180052e68`
- name: `?GetServiceAccount@CNonClusterTmInstance@@UEAAJPEAPEAG@Z`
- size: `280`
- prototype: `int(CNonClusterTmInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006324`
- `0x180052d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dde`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052e3f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052e4d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052e3f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052e4d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052db2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052db2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052d77`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052d77`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052dcd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052e12`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052dcd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052e12`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::GetServiceAccount(CNonClusterTmInstance *this, unsigned __int16 **a2)
{
  const WCHAR *v2; // rcx
  const unsigned __int16 **v3; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  SC_HANDLE v7; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  SC_HANDLE v10; // rax
  DWORD v11; // ebx
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp+8h] BYREF

  v2 = (const WCHAR *)*((_QWORD *)this + 4);
  v3 = 0;
  pcbBytesNeeded = 0;
  v5 = OpenSCManagerW(v2, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v10 = OpenServiceW(v5, L"MSDTC", 1u);
    v7 = v10;
    if ( v10 )
    {
      if ( QueryServiceConfigW(v10, 0, 0, &pcbBytesNeeded) )
      {
        v9 = -2147418113;
        goto LABEL_13;
      }
      if ( GetLastError() == 122 )
      {
        v11 = pcbBytesNeeded;
        v12 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(pcbBytesNeeded);
        v3 = (const unsigned __int16 **)v12;
        if ( !v12 )
        {
          v9 = -2147024882;
          goto LABEL_13;
        }
        if ( QueryServiceConfigW(v7, v12, v11, &pcbBytesNeeded) )
        {
          v9 = DuplicateString(v3[6], a2);
          goto LABEL_13;
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  CoTaskMemFree(v3);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( v6 )
    CloseServiceHandle(v6);
  return v9;
}

```

## disassembly

```asm
0x180052d50  mov     [rsp+arg_8], rbx
0x180052d55  mov     [rsp+arg_10], rbp
0x180052d5a  push    rsi
0x180052d5b  push    rdi
0x180052d5c  push    r14
0x180052d5e  sub     rsp, 20h
0x180052d62  mov     rcx, [rcx+20h]; lpMachineName
0x180052d66  xor     esi, esi
0x180052d68  mov     r14, rdx
0x180052d6b  mov     [rsp+38h+pcbBytesNeeded], esi
0x180052d6f  xor     edx, edx; lpDatabaseName
0x180052d71  lea     ebx, [rsi+1]
0x180052d74  mov     r8d, ebx; dwDesiredAccess
0x180052d77  call    cs:__imp_OpenSCManagerW
0x180052d7d  mov     rbp, rax
0x180052d80  test    rax, rax
0x180052d83  jnz     short loc_180052DA5
0x180052d85  xor     edi, edi
0x180052d87  call    cs:__imp_GetLastError
0x180052d8d  mov     ebx, eax
0x180052d8f  test    eax, eax
0x180052d91  jle     loc_180052E2E
0x180052d97  movzx   ebx, ax
0x180052d9a  or      ebx, 80070000h
0x180052da0  jmp     loc_180052E2E
0x180052da5  mov     r8d, ebx; dwDesiredAccess
0x180052da8  lea     rdx, aMsdtc; "MSDTC"
0x180052daf  mov     rcx, rbp; hSCManager
0x180052db2  call    cs:__imp_OpenServiceW
0x180052db8  mov     rdi, rax
0x180052dbb  test    rax, rax
0x180052dbe  jz      short loc_180052D87
0x180052dc0  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180052dc5  xor     r8d, r8d; cbBufSize
0x180052dc8  xor     edx, edx; lpServiceConfig
0x180052dca  mov     rcx, rax; hService
0x180052dcd  call    cs:__imp_QueryServiceConfigW
0x180052dd3  test    eax, eax
0x180052dd5  jz      short loc_180052DDE
0x180052dd7  mov     ebx, 8000FFFFh
0x180052ddc  jmp     short loc_180052E2E
0x180052dde  call    cs:__imp_GetLastError
0x180052de4  cmp     eax, 7Ah ; 'z'
0x180052de7  jnz     short loc_180052D87
0x180052de9  mov     ebx, [rsp+38h+pcbBytesNeeded]
0x180052ded  mov     ecx, ebx; cb
0x180052def  call    cs:__imp_CoTaskMemAlloc
0x180052df5  mov     rsi, rax
0x180052df8  test    rax, rax
0x180052dfb  jnz     short loc_180052E04
0x180052dfd  mov     ebx, 8007000Eh
0x180052e02  jmp     short loc_180052E2E
0x180052e04  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180052e09  mov     r8d, ebx; cbBufSize
0x180052e0c  mov     rdx, rsi; lpServiceConfig
0x180052e0f  mov     rcx, rdi; hService
0x180052e12  call    cs:__imp_QueryServiceConfigW
0x180052e18  test    eax, eax
0x180052e1a  jz      loc_180052D87
0x180052e20  mov     rcx, [rsi+30h]; unsigned __int16 *
0x180052e24  mov     rdx, r14; unsigned __int16 **
0x180052e27  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180052e2c  mov     ebx, eax
0x180052e2e  mov     rcx, rsi; pv
0x180052e31  call    cs:__imp_CoTaskMemFree
0x180052e37  test    rdi, rdi
0x180052e3a  jz      short loc_180052E45
0x180052e3c  mov     rcx, rdi; hSCObject
0x180052e3f  call    cs:__imp_CloseServiceHandle
0x180052e45  test    rbp, rbp
0x180052e48  jz      short loc_180052E53
0x180052e4a  mov     rcx, rbp; hSCObject
0x180052e4d  call    cs:__imp_CloseServiceHandle
0x180052e53  mov     rbp, [rsp+38h+arg_10]
0x180052e58  mov     eax, ebx
0x180052e5a  mov     rbx, [rsp+38h+arg_8]
0x180052e5f  add     rsp, 20h
0x180052e63  pop     r14
0x180052e65  pop     rdi
0x180052e66  pop     rsi
0x180052e67  retn
```
