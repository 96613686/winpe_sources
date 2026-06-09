# SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)

- ea: `0x18002d750`
- end: `0x18002d96e`
- name: `?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z`
- size: `542`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, struct SC_HANDLE__ *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002d690`
- `0x18002d750`

## callees

- `0x180001fb0`
- `0x18002cedc`
- `0x18002d750`
- `0x180033954`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d842`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d7c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d7c3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d93f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d93f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002d7fb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002d838`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002d7fb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002d838`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002d86b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002d86b`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002d8c1`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002d901`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002d8c1`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002d901`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::ResolveDependenciesRecursive(
        SERVICES_MANAGER *this,
        SC_HANDLE a2,
        unsigned __int16 *a3,
        int a4)
{
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  signed int inserted; // ebx
  signed int LastError; // eax
  LPQUERY_SERVICE_CONFIGW v13; // rbx
  DWORD v14; // edi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-39h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-35h] BYREF
  _QWORD v18[4]; // [rsp+38h] [rbp-31h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+58h] [rbp-11h]
  DWORD cbBufSize; // [rsp+60h] [rbp-9h]
  __int16 v21; // [rsp+64h] [rbp-5h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-1h] BYREF

  v18[0] = 0;
  cbBufSize = 32;
  v21 = 256;
  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  lpServiceConfig = (LPQUERY_SERVICE_CONFIGW)v18;
  v8 = OpenServiceW(a2, a3, 0xF01FFu);
  v9 = v8;
  if ( v8 )
  {
    if ( QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
    {
      inserted = -2147418113;
LABEL_23:
      CloseServiceHandle(v9);
      goto LABEL_24;
    }
    if ( !BUFFER::Resize((BUFFER *)v18, pcbBytesNeeded) )
    {
LABEL_7:
      inserted = -2147024888;
      goto LABEL_23;
    }
    if ( QueryServiceConfigW(v9, lpServiceConfig, cbBufSize, &pcbBytesNeeded) )
    {
      v13 = lpServiceConfig;
      if ( QueryServiceStatus(v9, &ServiceStatus) )
      {
        if ( a4 && v13->dwStartType == 3 || v13->dwStartType < 3 || (inserted = 0, ServiceStatus.dwCurrentState != 1) )
        {
          inserted = SERVICES_MANAGER::InsertServiceName(this, a3);
          if ( inserted < 0 )
            goto LABEL_23;
        }
        if ( EnumDependentServicesW(v9, 3u, 0, 0, &pcbBytesNeeded, &ServicesReturned) )
          goto LABEL_23;
        if ( !BUFFER::Resize((BUFFER *)v18, pcbBytesNeeded) )
          goto LABEL_7;
        if ( EnumDependentServicesW(
               v9,
               3u,
               (LPENUM_SERVICE_STATUSW)lpServiceConfig,
               cbBufSize,
               &pcbBytesNeeded,
               &ServicesReturned) )
        {
          v14 = ServicesReturned;
          do
          {
            if ( (--v14 & 0x80000000) != 0 )
              break;
            inserted = SERVICES_MANAGER::ResolveDependenciesRecursive(
                         this,
                         a2,
                         *((unsigned __int16 **)&lpServiceConfig->dwServiceType + 6 * v14),
                         0);
          }
          while ( inserted >= 0 );
          goto LABEL_23;
        }
      }
    }
    LastError = GetLastError();
    inserted = LastError;
    if ( LastError > 0 )
      inserted = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_23;
  }
  v10 = GetLastError();
  inserted = v10;
  if ( v10 > 0 )
    inserted = (unsigned __int16)v10 | 0x80070000;
LABEL_24:
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002d750  push    rbp
0x18002d752  push    rbx
0x18002d753  push    rsi
0x18002d754  push    rdi
0x18002d755  push    r12
0x18002d757  push    r14
0x18002d759  push    r15
0x18002d75b  lea     rbp, [rsp-27h]
0x18002d760  sub     rsp, 90h
0x18002d767  mov     rax, cs:__security_cookie
0x18002d76e  xor     rax, rsp
0x18002d771  mov     [rbp+57h+var_38], rax
0x18002d775  mov     r14, r8
0x18002d778  mov     [rbp+57h+var_88], 0
0x18002d780  mov     r12, rdx
0x18002d783  mov     [rbp+57h+cbBufSize], 20h ; ' '
0x18002d78a  xorps   xmm0, xmm0
0x18002d78d  mov     [rbp+57h+var_5C], 100h
0x18002d793  mov     r15, rcx
0x18002d796  mov     [rbp+57h+pcbBytesNeeded], 0
0x18002d79d  lea     rax, [rbp+57h+var_88]
0x18002d7a1  mov     [rbp+57h+ServicesReturned], 0
0x18002d7a8  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18002d7ac  mov     rdx, r14; lpServiceName
0x18002d7af  mov     [rbp+57h+lpServiceConfig], rax
0x18002d7b3  mov     rcx, r12; hSCManager
0x18002d7b6  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002d7bc  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002d7c0  mov     edi, r9d
0x18002d7c3  call    cs:__imp_OpenServiceW
0x18002d7c9  mov     rsi, rax
0x18002d7cc  test    rax, rax
0x18002d7cf  jnz     short loc_18002D7EF
0x18002d7d1  call    cs:__imp_GetLastError
0x18002d7d7  mov     ebx, eax
0x18002d7d9  test    eax, eax
0x18002d7db  jle     loc_18002D945
0x18002d7e1  movzx   ebx, ax
0x18002d7e4  or      ebx, 80070000h
0x18002d7ea  jmp     loc_18002D945
0x18002d7ef  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18002d7f3  xor     r8d, r8d; cbBufSize
0x18002d7f6  xor     edx, edx; lpServiceConfig
0x18002d7f8  mov     rcx, rsi; hService
0x18002d7fb  call    cs:__imp_QueryServiceConfigW
0x18002d801  test    eax, eax
0x18002d803  jz      short loc_18002D80F
0x18002d805  mov     ebx, 8000FFFFh
0x18002d80a  jmp     loc_18002D93C
0x18002d80f  mov     edx, [rbp+57h+pcbBytesNeeded]; unsigned int
0x18002d812  lea     rcx, [rbp+57h+var_88]; this
0x18002d816  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002d81b  test    al, al
0x18002d81d  jnz     short loc_18002D829
0x18002d81f  mov     ebx, 80070008h
0x18002d824  jmp     loc_18002D93C
0x18002d829  mov     r8d, [rbp+57h+cbBufSize]; cbBufSize
0x18002d82d  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18002d831  mov     rdx, [rbp+57h+lpServiceConfig]; lpServiceConfig
0x18002d835  mov     rcx, rsi; hService
0x18002d838  call    cs:__imp_QueryServiceConfigW
0x18002d83e  test    eax, eax
0x18002d840  jnz     short loc_18002D860
0x18002d842  call    cs:__imp_GetLastError
0x18002d848  mov     ebx, eax
0x18002d84a  test    eax, eax
0x18002d84c  jle     loc_18002D93C
0x18002d852  movzx   ebx, ax
0x18002d855  or      ebx, 80070000h
0x18002d85b  jmp     loc_18002D93C
0x18002d860  mov     rbx, [rbp+57h+lpServiceConfig]
0x18002d864  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18002d868  mov     rcx, rsi; hService
0x18002d86b  call    cs:__imp_QueryServiceStatus
0x18002d871  test    eax, eax
0x18002d873  jz      short loc_18002D842
0x18002d875  test    edi, edi
0x18002d877  jz      short loc_18002D87F
0x18002d879  cmp     dword ptr [rbx+4], 3
0x18002d87d  jz      short loc_18002D88D
0x18002d87f  cmp     dword ptr [rbx+4], 3
0x18002d883  jb      short loc_18002D88D
0x18002d885  xor     ebx, ebx
0x18002d887  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x18002d88b  jz      short loc_18002D8A2
0x18002d88d  mov     rdx, r14; unsigned __int16 *
0x18002d890  mov     rcx, r15; this
0x18002d893  call    ?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z; SERVICES_MANAGER::InsertServiceName(ushort *)
0x18002d898  mov     ebx, eax
0x18002d89a  test    eax, eax
0x18002d89c  js      loc_18002D93C
0x18002d8a2  xor     r9d, r9d; cbBufSize
0x18002d8a5  lea     rax, [rbp+57h+ServicesReturned]
0x18002d8a9  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x18002d8ae  xor     r8d, r8d; lpServices
0x18002d8b1  lea     rax, [rbp+57h+pcbBytesNeeded]
0x18002d8b5  mov     rcx, rsi; hService
0x18002d8b8  mov     [rsp+0C0h+var_A0], rax; pcbBytesNeeded
0x18002d8bd  lea     edx, [r9+3]; dwServiceState
0x18002d8c1  call    cs:__imp_EnumDependentServicesW
0x18002d8c7  test    eax, eax
0x18002d8c9  jnz     short loc_18002D93C
0x18002d8cb  mov     edx, [rbp+57h+pcbBytesNeeded]; unsigned int
0x18002d8ce  lea     rcx, [rbp+57h+var_88]; this
0x18002d8d2  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002d8d7  test    al, al
0x18002d8d9  jz      loc_18002D81F
0x18002d8df  mov     r9d, [rbp+57h+cbBufSize]; cbBufSize
0x18002d8e3  lea     rax, [rbp+57h+ServicesReturned]
0x18002d8e7  mov     r8, [rbp+57h+lpServiceConfig]; lpServices
0x18002d8eb  mov     edx, 3; dwServiceState
0x18002d8f0  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x18002d8f5  mov     rcx, rsi; hService
0x18002d8f8  lea     rax, [rbp+57h+pcbBytesNeeded]
0x18002d8fc  mov     [rsp+0C0h+var_A0], rax; pcbBytesNeeded
0x18002d901  call    cs:__imp_EnumDependentServicesW
0x18002d907  test    eax, eax
0x18002d909  jz      loc_18002D842
0x18002d90f  mov     edi, [rbp+57h+ServicesReturned]
0x18002d912  jmp     short loc_18002D937
0x18002d914  mov     r8, [rbp+57h+lpServiceConfig]
0x18002d918  lea     rcx, [rdi+rdi*2]
0x18002d91c  add     rcx, rcx
0x18002d91f  xor     r9d, r9d; int
0x18002d922  mov     rdx, r12; struct SC_HANDLE__ *
0x18002d925  mov     r8, [r8+rcx*8]; unsigned __int16 *
0x18002d929  mov     rcx, r15; this
0x18002d92c  call    ?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z; SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)
0x18002d931  mov     ebx, eax
0x18002d933  test    eax, eax
0x18002d935  js      short loc_18002D93C
0x18002d937  sub     edi, 1
0x18002d93a  jns     short loc_18002D914
0x18002d93c  mov     rcx, rsi; hSCObject
0x18002d93f  call    cs:__imp_CloseServiceHandle
0x18002d945  lea     rcx, [rbp+57h+var_88]; this
0x18002d949  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002d94e  mov     eax, ebx
0x18002d950  mov     rcx, [rbp+57h+var_38]
0x18002d954  xor     rcx, rsp; StackCookie
0x18002d957  call    __security_check_cookie
0x18002d95c  add     rsp, 90h
0x18002d963  pop     r15
0x18002d965  pop     r14
0x18002d967  pop     r12
0x18002d969  pop     rdi
0x18002d96a  pop     rsi
0x18002d96b  pop     rbx
0x18002d96c  pop     rbp
0x18002d96d  retn
```
