# CNonClusterTmInstance::TakeOffline(int)

- ea: `0x180053570`
- end: `0x180053713`
- name: `?TakeOffline@CNonClusterTmInstance@@UEAAJH@Z`
- size: `419`
- prototype: `int(CNonClusterTmInstance *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x18001d178`
- `0x18001d184`
- `0x180053450`
- `0x180053570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005363b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005363b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053648`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800536e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800536eb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800536e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800536eb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800535d9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800535d9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005359d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005359d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18005362d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18005369f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18005362d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18005369f`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::TakeOffline(CNonClusterTmInstance *this, int a2)
{
  const WCHAR *v2; // rcx
  SC_HANDLE v4; // rax
  struct SC_HANDLE__ *v5; // rbp
  signed int LastError; // eax
  unsigned int v7; // ebx
  struct _ENUM_SERVICE_STATUSW *v8; // rdi
  CNonClusterTmInstance *v9; // rcx
  SC_HANDLE v10; // r14
  signed int v11; // eax
  signed int v12; // eax
  struct _ENUM_SERVICE_STATUSW *v13; // rax
  __int64 i; // rsi
  DWORD cbBufSize; // [rsp+50h] [rbp+8h] BYREF
  DWORD ServicesReturned; // [rsp+60h] [rbp+18h] BYREF

  v2 = (const WCHAR *)*((_QWORD *)this + 4);
  cbBufSize = 0;
  ServicesReturned = 0;
  v4 = OpenSCManagerW(v2, 0, 5u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v7;
  }
  v8 = 0;
  v10 = OpenServiceW(v4, L"MSDTC", 8u);
  if ( !v10 )
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_21;
  }
  if ( a2 != 1 || EnumDependentServicesW(v10, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
  {
LABEL_19:
    v7 = CNonClusterTmInstance::StopServiceHelper(v9, v5, L"MSDTC");
    goto LABEL_20;
  }
  if ( GetLastError() != 234 )
    goto LABEL_10;
  v13 = (struct _ENUM_SERVICE_STATUSW *)operator new[](cbBufSize);
  v8 = v13;
  if ( v13 )
  {
    if ( !EnumDependentServicesW(v10, 1u, v13, cbBufSize, &cbBufSize, &ServicesReturned) )
    {
LABEL_10:
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_20;
    }
    for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
    {
      v7 = CNonClusterTmInstance::StopServiceHelper(v9, v5, v8[i].lpServiceName);
      if ( (v7 & 0x80000000) != 0 )
        goto LABEL_20;
    }
    goto LABEL_19;
  }
  v7 = -2147024882;
LABEL_20:
  CloseServiceHandle(v10);
LABEL_21:
  CloseServiceHandle(v5);
  if ( v8 )
    operator delete(v8);
  return v7;
}

```

## disassembly

```asm
0x180053570  mov     rax, rsp
0x180053573  mov     [rax+10h], rbx
0x180053577  mov     [rax+20h], rbp
0x18005357b  push    rsi
0x18005357c  push    rdi
0x18005357d  push    r14
0x18005357f  sub     rsp, 30h
0x180053583  mov     rcx, [rcx+20h]; lpMachineName
0x180053587  mov     ebx, edx
0x180053589  xor     edx, edx; lpDatabaseName
0x18005358b  mov     dword ptr [rax+8], 0
0x180053592  mov     dword ptr [rax+18h], 0
0x180053599  lea     r8d, [rdx+5]; dwDesiredAccess
0x18005359d  call    cs:__imp_OpenSCManagerW
0x1800535a3  mov     rbp, rax
0x1800535a6  test    rax, rax
0x1800535a9  jnz     short loc_1800535C9
0x1800535ab  call    cs:__imp_GetLastError
0x1800535b1  mov     ebx, eax
0x1800535b3  test    eax, eax
0x1800535b5  jle     loc_1800536FE
0x1800535bb  movzx   ebx, ax
0x1800535be  or      ebx, 80070000h
0x1800535c4  jmp     loc_1800536FE
0x1800535c9  xor     edi, edi
0x1800535cb  lea     rdx, aMsdtc; "MSDTC"
0x1800535d2  mov     rcx, rbp; hSCManager
0x1800535d5  lea     r8d, [rdi+8]; dwDesiredAccess
0x1800535d9  call    cs:__imp_OpenServiceW
0x1800535df  mov     r14, rax
0x1800535e2  test    rax, rax
0x1800535e5  jnz     short loc_180053605
0x1800535e7  call    cs:__imp_GetLastError
0x1800535ed  mov     ebx, eax
0x1800535ef  test    eax, eax
0x1800535f1  jle     loc_1800536E8
0x1800535f7  movzx   ebx, ax
0x1800535fa  or      ebx, 80070000h
0x180053600  jmp     loc_1800536E8
0x180053605  cmp     ebx, 1
0x180053608  jnz     loc_1800536CE
0x18005360e  lea     rax, [rsp+48h+ServicesReturned]
0x180053613  xor     r9d, r9d; cbBufSize
0x180053616  mov     [rsp+48h+lpServicesReturned], rax; lpServicesReturned
0x18005361b  xor     r8d, r8d; lpServices
0x18005361e  lea     rax, [rsp+48h+cbBufSize]
0x180053623  mov     edx, ebx; dwServiceState
0x180053625  mov     rcx, r14; hService
0x180053628  mov     [rsp+48h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005362d  call    cs:__imp_EnumDependentServicesW
0x180053633  test    eax, eax
0x180053635  jnz     loc_1800536CE
0x18005363b  call    cs:__imp_GetLastError
0x180053641  cmp     eax, 0EAh
0x180053646  jz      short loc_180053663
0x180053648  call    cs:__imp_GetLastError
0x18005364e  mov     ebx, eax
0x180053650  test    eax, eax
0x180053652  jle     loc_1800536DF
0x180053658  movzx   ebx, ax
0x18005365b  or      ebx, 80070000h
0x180053661  jmp     short loc_1800536DF
0x180053663  mov     ecx, [rsp+48h+cbBufSize]; unsigned __int64
0x180053667  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005366c  mov     rdi, rax
0x18005366f  test    rax, rax
0x180053672  jnz     short loc_18005367B
0x180053674  mov     ebx, 8007000Eh
0x180053679  jmp     short loc_1800536DF
0x18005367b  mov     r9d, [rsp+48h+cbBufSize]; cbBufSize
0x180053680  lea     rax, [rsp+48h+ServicesReturned]
0x180053685  mov     [rsp+48h+lpServicesReturned], rax; lpServicesReturned
0x18005368a  mov     r8, rdi; lpServices
0x18005368d  lea     rax, [rsp+48h+cbBufSize]
0x180053692  mov     edx, 1; dwServiceState
0x180053697  mov     rcx, r14; hService
0x18005369a  mov     [rsp+48h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005369f  call    cs:__imp_EnumDependentServicesW
0x1800536a5  test    eax, eax
0x1800536a7  jz      short loc_180053648
0x1800536a9  xor     esi, esi
0x1800536ab  cmp     esi, [rsp+48h+ServicesReturned]
0x1800536af  jnb     short loc_1800536CE
0x1800536b1  lea     r8, [rsi+rsi*2]
0x1800536b5  mov     rdx, rbp; struct SC_HANDLE__ *
0x1800536b8  add     r8, r8
0x1800536bb  mov     r8, [rdi+r8*8]; unsigned __int16 *
0x1800536bf  call    ?StopServiceHelper@CNonClusterTmInstance@@AEAAJPEAUSC_HANDLE__@@PEBG@Z; CNonClusterTmInstance::StopServiceHelper(SC_HANDLE__ *,ushort const *)
0x1800536c4  mov     ebx, eax
0x1800536c6  test    eax, eax
0x1800536c8  js      short loc_1800536DF
0x1800536ca  inc     esi
0x1800536cc  jmp     short loc_1800536AB
0x1800536ce  lea     r8, aMsdtc; "MSDTC"
0x1800536d5  mov     rdx, rbp; struct SC_HANDLE__ *
0x1800536d8  call    ?StopServiceHelper@CNonClusterTmInstance@@AEAAJPEAUSC_HANDLE__@@PEBG@Z; CNonClusterTmInstance::StopServiceHelper(SC_HANDLE__ *,ushort const *)
0x1800536dd  mov     ebx, eax
0x1800536df  mov     rcx, r14; hSCObject
0x1800536e2  call    cs:__imp_CloseServiceHandle
0x1800536e8  mov     rcx, rbp; hSCObject
0x1800536eb  call    cs:__imp_CloseServiceHandle
0x1800536f1  test    rdi, rdi
0x1800536f4  jz      short loc_1800536FE
0x1800536f6  mov     rcx, rdi; Block
0x1800536f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800536fe  mov     rbp, [rsp+48h+arg_18]
0x180053703  mov     eax, ebx
0x180053705  mov     rbx, [rsp+48h+arg_8]
0x18005370a  add     rsp, 30h
0x18005370e  pop     r14
0x180053710  pop     rdi
0x180053711  pop     rsi
0x180053712  retn
```
