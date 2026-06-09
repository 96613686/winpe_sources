# CServiceModule::_SetServiceTypeAutoStart(void)

- ea: `0x18000ea80`
- end: `0x18000ed5c`
- name: `?_SetServiceTypeAutoStart@CServiceModule@@AEAAHXZ`
- size: `732`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000f5d0`
- `0x18000fa00`

## callees

- `0x18000ea80`
- `0x18001bc04`
- `0x18001bffc`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed2a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000eba6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ebea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000eca9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000eba6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ebea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000eca9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000eae6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ec58`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000eae6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ec58`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000eabc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000eabc`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000ec9e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000ec9e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000eb1b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000eb68`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000eb1b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000eb68`

## string_xrefs

- `0x18000eadc`: `TextInputManagementService`
- `0x18000ec4e`: `TextInputManagementService`
- `0x18000ec03`: `PENSERVICE_CServiceModule::_SetServiceTypeAutoStart`
- `0x18000ec2b`: `PENSERVICE_CServiceModule::_SetServiceTypeAutoStart`
- `0x18000ecb8`: `PENSERVICE_CServiceModule::_SetServiceTypeAutoStart`
- `0x18000ecf3`: `PENSERVICE_CServiceModule::_SetServiceTypeAutoStart`
- `0x18000ed37`: `PENSERVICE_CServiceModule::_SetServiceTypeAutoStart`

## pseudocode

```c
__int64 __fastcall CServiceModule::_SetServiceTypeAutoStart(CServiceModule *this)
{
  unsigned int ServiceConfigW; // esi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  int v6; // ebp
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  const struct std::nothrow_t *v8; // rdx
  struct _QUERY_SERVICE_CONFIGW *v9; // r14
  struct _GUID *v10; // rcx
  SC_HANDLE v12; // rax
  SC_HANDLE v13; // rdi
  char LastError; // al
  CServiceModule *pcbBytesNeeded; // [rsp+90h] [rbp+8h] BYREF

  pcbBytesNeeded = this;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      54,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_SetServiceTypeAutoStart");
  ServiceConfigW = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"TextInputManagementService", 1u);
    v5 = v4;
    if ( !v4 )
      goto LABEL_27;
    LODWORD(pcbBytesNeeded) = 0;
    v6 = 0;
    ServiceConfigW = QueryServiceConfigW(v4, 0, 0, (LPDWORD)&pcbBytesNeeded);
    if ( !ServiceConfigW && GetLastError() == 122 )
    {
      v7 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](
                                              (unsigned int)pcbBytesNeeded,
                                              (const struct std::nothrow_t *)&std::nothrow);
      v9 = v7;
      if ( v7 )
      {
        ServiceConfigW = QueryServiceConfigW(v5, v7, (DWORD)pcbBytesNeeded, (LPDWORD)&pcbBytesNeeded);
        if ( ServiceConfigW )
        {
          if ( v9->dwStartType == 2 )
          {
            v6 = 1;
            if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
            {
              WPP_SF_s(
                *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
                55,
                WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
                "PENSERVICE_CServiceModule::_SetServiceTypeAutoStart");
            }
          }
        }
      }
      operator delete(v9, v8);
    }
    CloseServiceHandle(v5);
    if ( !v6 )
    {
LABEL_27:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          56,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_SetServiceTypeAutoStart");
      v12 = OpenServiceW(v3, L"TextInputManagementService", 2u);
      v13 = v12;
      if ( v12 )
      {
        ServiceConfigW = ChangeServiceConfigW(v12, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
        CloseServiceHandle(v13);
      }
    }
    if ( ServiceConfigW )
      goto LABEL_15;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control )
    goto LABEL_17;
  if ( (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      57,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::_SetServiceTypeAutoStart",
      LastError);
LABEL_15:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (struct _GUID *)&WPP_GLOBAL_Control && (v10[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v10[1].Data1,
      58,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_SetServiceTypeAutoStart");
LABEL_17:
  if ( v3 )
    CloseServiceHandle(v3);
  return ServiceConfigW;
}

```

## disassembly

```asm
0x18000ea80  mov     [rsp+pcbBytesNeeded], rcx
0x18000ea85  push    rbx
0x18000ea86  push    rsi
0x18000ea87  sub     rsp, 78h
0x18000ea8b  mov     [rsp+88h+var_18], r12
0x18000ea90  mov     [rsp+88h+var_28], r15
0x18000ea95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea9c  lea     r15, WPP_GLOBAL_Control
0x18000eaa3  cmp     rcx, r15
0x18000eaa6  jnz     loc_18000EC1D
0x18000eaac  xor     r12d, r12d
0x18000eaaf  xor     edx, edx; lpDatabaseName
0x18000eab1  xor     ecx, ecx; lpMachineName
0x18000eab3  mov     r8d, 1; dwDesiredAccess
0x18000eab9  mov     esi, r12d
0x18000eabc  call    cs:__imp_OpenSCManagerW
0x18000eac2  mov     rbx, rax
0x18000eac5  test    rax, rax
0x18000eac8  jz      loc_18000ED10
0x18000eace  mov     r8d, 1; dwDesiredAccess
0x18000ead4  mov     [rsp+88h+arg_10], rdi
0x18000eadc  lea     rdx, ServiceName; "TextInputManagementService"
0x18000eae3  mov     rcx, rax; hSCManager
0x18000eae6  call    cs:__imp_OpenServiceW
0x18000eaec  mov     rdi, rax
0x18000eaef  test    rax, rax
0x18000eaf2  jz      loc_18000ECD5
0x18000eaf8  mov     [rsp+88h+arg_8], rbp
0x18000eb00  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18000eb08  xor     r8d, r8d; cbBufSize
0x18000eb0b  mov     dword ptr [rsp+88h+pcbBytesNeeded], r12d
0x18000eb13  xor     edx, edx; lpServiceConfig
0x18000eb15  mov     rcx, rax; hService
0x18000eb18  mov     ebp, r12d
0x18000eb1b  call    cs:__imp_QueryServiceConfigW
0x18000eb21  mov     esi, eax
0x18000eb23  test    eax, eax
0x18000eb25  jnz     short loc_18000EBA3
0x18000eb27  call    cs:__imp_GetLastError
0x18000eb2d  cmp     eax, 7Ah ; 'z'
0x18000eb30  jnz     short loc_18000EBA3
0x18000eb32  mov     ecx, dword ptr [rsp+88h+pcbBytesNeeded]; unsigned __int64
0x18000eb39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb40  mov     [rsp+88h+var_20], r14
0x18000eb45  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000eb4a  mov     r14, rax
0x18000eb4d  test    rax, rax
0x18000eb50  jz      short loc_18000EB96
0x18000eb52  mov     r8d, dword ptr [rsp+88h+pcbBytesNeeded]; cbBufSize
0x18000eb5a  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18000eb62  mov     rdx, rax; lpServiceConfig
0x18000eb65  mov     rcx, rdi; hService
0x18000eb68  call    cs:__imp_QueryServiceConfigW
0x18000eb6e  mov     esi, eax
0x18000eb70  test    eax, eax
0x18000eb72  jz      short loc_18000EB96
0x18000eb74  cmp     dword ptr [r14+4], 2
0x18000eb79  jnz     short loc_18000EB96
0x18000eb7b  mov     ebp, 1
0x18000eb80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb87  cmp     rcx, r15
0x18000eb8a  jz      short loc_18000EB96
0x18000eb8c  test    byte ptr [rcx+1Ch], 10h
0x18000eb90  jnz     loc_18000ECB4
0x18000eb96  mov     rcx, r14; void *
0x18000eb99  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000eb9e  mov     r14, [rsp+88h+var_20]
0x18000eba3  mov     rcx, rdi; hSCObject
0x18000eba6  call    cs:__imp_CloseServiceHandle
0x18000ebac  test    ebp, ebp
0x18000ebae  mov     rbp, [rsp+88h+arg_8]
0x18000ebb6  jz      loc_18000ECD5
0x18000ebbc  mov     rdi, [rsp+88h+arg_10]
0x18000ebc4  test    esi, esi
0x18000ebc6  jz      loc_18000ED10
0x18000ebcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebd3  cmp     rcx, r15
0x18000ebd6  jnz     short loc_18000EBF9
0x18000ebd8  mov     r15, [rsp+88h+var_28]
0x18000ebdd  mov     r12, [rsp+88h+var_18]
0x18000ebe2  test    rbx, rbx
0x18000ebe5  jz      short loc_18000EBF0
0x18000ebe7  mov     rcx, rbx; hSCObject
0x18000ebea  call    cs:__imp_CloseServiceHandle
0x18000ebf0  mov     eax, esi
0x18000ebf2  add     rsp, 78h
0x18000ebf6  pop     rsi
0x18000ebf7  pop     rbx
0x18000ebf8  retn
0x18000ebf9  test    byte ptr [rcx+1Ch], 10h
0x18000ebfd  jz      short loc_18000EBD8
0x18000ebff  mov     rcx, [rcx+10h]
0x18000ec03  lea     r9, aPenserviceCser_3; "PENSERVICE_CServiceModule::_SetServiceT"...
0x18000ec0a  mov     edx, 3Ah ; ':'
0x18000ec0f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000ec16  call    WPP_SF_s
0x18000ec1b  jmp     short loc_18000EBD8
0x18000ec1d  test    byte ptr [rcx+1Ch], 10h
0x18000ec21  jz      loc_18000EAAC
0x18000ec27  mov     rcx, [rcx+10h]
0x18000ec2b  lea     r9, aPenserviceCser_3; "PENSERVICE_CServiceModule::_SetServiceT"...
0x18000ec32  mov     edx, 36h ; '6'
0x18000ec37  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000ec3e  call    WPP_SF_s
0x18000ec43  jmp     loc_18000EAAC
0x18000ec48  mov     r8d, 2; dwDesiredAccess
0x18000ec4e  lea     rdx, ServiceName; "TextInputManagementService"
0x18000ec55  mov     rcx, rbx; hSCManager
0x18000ec58  call    cs:__imp_OpenServiceW
0x18000ec5e  mov     rdi, rax
0x18000ec61  test    rax, rax
0x18000ec64  jz      loc_18000EBBC
0x18000ec6a  mov     [rsp+88h+lpDisplayName], r12; lpDisplayName
0x18000ec6f  mov     edx, 0FFFFFFFFh; dwServiceType
0x18000ec74  mov     [rsp+88h+lpPassword], r12; lpPassword
0x18000ec79  mov     r9d, edx; dwErrorControl
0x18000ec7c  mov     [rsp+88h+lpServiceStartName], r12; lpServiceStartName
0x18000ec81  mov     r8d, 2; dwStartType
0x18000ec87  mov     [rsp+88h+lpDependencies], r12; lpDependencies
0x18000ec8c  mov     rcx, rax; hService
0x18000ec8f  mov     [rsp+88h+lpdwTagId], r12; lpdwTagId
0x18000ec94  mov     [rsp+88h+lpLoadOrderGroup], r12; lpLoadOrderGroup
0x18000ec99  mov     [rsp+88h+lpBinaryPathName], r12; lpBinaryPathName
0x18000ec9e  call    cs:__imp_ChangeServiceConfigW
0x18000eca4  mov     rcx, rdi; hSCObject
0x18000eca7  mov     esi, eax
0x18000eca9  call    cs:__imp_CloseServiceHandle
0x18000ecaf  jmp     loc_18000EBBC
0x18000ecb4  mov     rcx, [rcx+10h]
0x18000ecb8  lea     r9, aPenserviceCser_3; "PENSERVICE_CServiceModule::_SetServiceT"...
0x18000ecbf  mov     edx, 37h ; '7'
0x18000ecc4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000eccb  call    WPP_SF_s
0x18000ecd0  jmp     loc_18000EB96
0x18000ecd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecdc  cmp     rcx, r15
0x18000ecdf  jz      loc_18000EC48
0x18000ece5  test    byte ptr [rcx+1Ch], 10h
0x18000ece9  jz      loc_18000EC48
0x18000ecef  mov     rcx, [rcx+10h]
0x18000ecf3  lea     r9, aPenserviceCser_3; "PENSERVICE_CServiceModule::_SetServiceT"...
0x18000ecfa  mov     edx, 38h ; '8'
0x18000ecff  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000ed06  call    WPP_SF_s
0x18000ed0b  jmp     loc_18000EC48
0x18000ed10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed17  cmp     rcx, r15
0x18000ed1a  jz      loc_18000EBD8
0x18000ed20  test    byte ptr [rcx+1Ch], 4
0x18000ed24  jz      loc_18000EBD3
0x18000ed2a  call    cs:__imp_GetLastError
0x18000ed30  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed37  lea     r9, aPenserviceCser_3; "PENSERVICE_CServiceModule::_SetServiceT"...
0x18000ed3e  mov     edx, 39h ; '9'
0x18000ed43  mov     dword ptr [rsp+88h+lpBinaryPathName], eax
0x18000ed47  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000ed4e  mov     rcx, [rcx+10h]
0x18000ed52  call    WPP_SF_sd
0x18000ed57  jmp     loc_18000EBCC
```
