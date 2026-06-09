# Common::StopService(ushort const *,ulong,int *)

- ea: `0x180072aa8`
- end: `0x180072cae`
- name: `?StopService@Common@@YAJPEBGKPEAH@Z`
- size: `518`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800728f0`

## callees

- `0x18000669c`
- `0x180069eb4`
- `0x180072aa8`
- `0x1800aed10`
- `0x1800e2c4c`
- `0x180188ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bd4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180072c01`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180072c01`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072af9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072af9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180072ad2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180072ad2`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180072bc2`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180072bc2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180072b3d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180072b3d`

## string_xrefs

- `0x180072b81`: `onecore\admin\appmodel\common\serviceutilities.cpp`
- `0x180072c5a`: `onecore\admin\appmodel\common\serviceutilities.cpp`
- `0x180072c77`: `onecore\admin\appmodel\common\serviceutilities.cpp`

## pseudocode

```c
__int64 __fastcall Common::StopService(LPCWSTR lpServiceName, const unsigned __int16 *a2, __int64 a3, int *a4)
{
  SC_HANDLE v5; // rax
  const char *v6; // r9
  const char *v7; // r9
  SC_HANDLE v8; // rbx
  struct SC_HANDLE__ *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // eax
  char v15; // al
  unsigned int v16; // edi
  BOOL v17; // esi
  DWORD v18; // eax
  unsigned int v19; // eax
  unsigned int LastError; // ebx
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-49h]
  DWORD v23; // [rsp+30h] [rbp-39h] BYREF
  SC_HANDLE v24; // [rsp+38h] [rbp-31h] BYREF
  SC_HANDLE v25; // [rsp+40h] [rbp-29h] BYREF
  BYTE Buffer[16]; // [rsp+48h] [rbp-21h] BYREF
  __int128 v27; // [rsp+58h] [rbp-11h]
  int v28; // [rsp+68h] [rbp-1h]
  _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = OpenSCManagerW(0, 0, 1u);
  v24 = v5;
  if ( !v5 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x94,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\serviceutilities.cpp",
                  v6);
    goto LABEL_31;
  }
  v25 = OpenServiceW(v5, lpServiceName, 0x24u);
  v8 = v25;
  if ( !v25 )
  {
    v11 = 159;
    goto LABEL_28;
  }
  v28 = 0;
  v23 = 0;
  *(_OWORD *)Buffer = 0;
  v27 = 0;
  if ( !QueryServiceStatusEx(v25, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v23) )
  {
    v11 = 164;
LABEL_28:
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\admin\\appmodel\\common\\serviceutilities.cpp",
            v7);
    goto LABEL_29;
  }
  switch ( *(_DWORD *)&Buffer[4] )
  {
    case 1:
      goto LABEL_26;
    case 2:
      goto LABEL_12;
    case 3:
      v15 = 1;
      goto LABEL_13;
    case 4:
LABEL_12:
      v15 = 0;
LABEL_13:
      v16 = 0;
      v17 = 0;
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( !v15 )
      {
        while ( !v17 )
        {
          if ( v16 >= 8 )
            goto LABEL_26;
          v17 = ControlService(v8, 1u, &ServiceStatus);
          if ( !v17 )
          {
            v18 = GetLastError();
            if ( v18 == 1062 )
              goto LABEL_26;
            if ( v18 != 1052 && v18 != 1061 && v18 != 1460 )
            {
              if ( !v18 )
                goto LABEL_26;
              v12 = v18;
              v13 = 225;
              goto LABEL_10;
            }
            Sleep(0x9C4u);
            ++v16;
          }
        }
      }
      v19 = Common::ServiceWaitForNotifyStatus(v8, v9, v10);
      if ( v19 )
      {
        v12 = v19;
        v13 = 233;
        goto LABEL_10;
      }
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v24);
      return 0;
  }
  v12 = 1359;
  v13 = 186;
LABEL_10:
  v14 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\admin\\appmodel\\common\\serviceutilities.cpp",
          (const char *)v12,
          pcbBytesNeeded);
LABEL_29:
  LastError = v14;
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v25);
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v24);
  return LastError;
}

```

## disassembly

```asm
0x180072aa8  push    rbp
0x180072aaa  push    rbx
0x180072aab  push    rsi
0x180072aac  push    rdi
0x180072aad  lea     rbp, [rsp-3Fh]
0x180072ab2  sub     rsp, 0A8h
0x180072ab9  mov     rax, cs:__security_cookie
0x180072ac0  xor     rax, rsp
0x180072ac3  mov     [rbp+57h+var_30], rax
0x180072ac7  xor     edx, edx; lpDatabaseName
0x180072ac9  mov     rbx, rcx
0x180072acc  xor     ecx, ecx; lpMachineName
0x180072ace  lea     r8d, [rdx+1]; dwDesiredAccess
0x180072ad2  call    cs:__imp_OpenSCManagerW
0x180072ad9  nop     dword ptr [rax+rax+00h]
0x180072ade  mov     [rbp+57h+var_88], rax
0x180072ae2  test    rax, rax
0x180072ae5  jz      loc_180072C73
0x180072aeb  mov     edi, 24h ; '$'
0x180072af0  mov     rdx, rbx; lpServiceName
0x180072af3  mov     r8d, edi; dwDesiredAccess
0x180072af6  mov     rcx, rax; hSCManager
0x180072af9  call    cs:__imp_OpenServiceW
0x180072b00  nop     dword ptr [rax+rax+00h]
0x180072b05  mov     [rbp+57h+var_80], rax
0x180072b09  mov     rbx, rax
0x180072b0c  test    rax, rax
0x180072b0f  jz      loc_180072C51
0x180072b15  xor     eax, eax
0x180072b17  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180072b1b  xorps   xmm0, xmm0
0x180072b1e  mov     [rbp+57h+var_58], eax
0x180072b21  mov     [rbp+57h+var_90], eax
0x180072b24  mov     r9d, edi; cbBufSize
0x180072b27  lea     rax, [rbp+57h+var_90]
0x180072b2b  xor     edx, edx; InfoLevel
0x180072b2d  mov     rcx, rbx; hService
0x180072b30  mov     qword ptr [rsp+0C0h+pcbBytesNeeded], rax; unsigned int
0x180072b35  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180072b39  movups  [rbp+57h+var_68], xmm0
0x180072b3d  call    cs:__imp_QueryServiceStatusEx
0x180072b44  nop     dword ptr [rax+rax+00h]
0x180072b49  test    eax, eax
0x180072b4b  jnz     short loc_180072B57
0x180072b4d  mov     edx, 0A4h
0x180072b52  jmp     loc_180072C56
0x180072b57  mov     eax, dword ptr [rbp+57h+Buffer+4]
0x180072b5a  sub     eax, 1
0x180072b5d  jz      loc_180072C3B
0x180072b63  sub     eax, 1
0x180072b66  jz      short loc_180072B96
0x180072b68  sub     eax, 1
0x180072b6b  jz      short loc_180072B92
0x180072b6d  cmp     eax, 1
0x180072b70  jz      short loc_180072B96
0x180072b72  mov     r9d, 54Fh; char *
0x180072b78  mov     edx, 0BAh; void *
0x180072b7d  mov     rcx, [rbp+5Fh]; this
0x180072b81  lea     r8, aOnecoreAdminAp_62; "onecore\\admin\\appmodel\\common\\servi"...
0x180072b88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072b8d  jmp     loc_180072C66
0x180072b92  mov     al, 1
0x180072b94  jmp     short loc_180072B98
0x180072b96  xor     al, al
0x180072b98  xorps   xmm0, xmm0
0x180072b9b  xor     edi, edi
0x180072b9d  xor     esi, esi
0x180072b9f  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180072ba3  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180072ba7  test    al, al
0x180072ba9  jnz     short loc_180072C22
0x180072bab  test    esi, esi
0x180072bad  jnz     short loc_180072C22
0x180072baf  cmp     edi, 8
0x180072bb2  jnb     loc_180072C3B
0x180072bb8  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180072bbc  mov     rcx, rbx; hService
0x180072bbf  lea     edx, [rsi+1]; dwControl
0x180072bc2  call    cs:__imp_ControlService
0x180072bc9  nop     dword ptr [rax+rax+00h]
0x180072bce  mov     esi, eax
0x180072bd0  test    eax, eax
0x180072bd2  jnz     short loc_180072BAB
0x180072bd4  call    cs:__imp_GetLastError
0x180072bdb  nop     dword ptr [rax+rax+00h]
0x180072be0  cmp     eax, 426h
0x180072be5  jz      short loc_180072C3B
0x180072be7  cmp     eax, 41Ch
0x180072bec  jz      short loc_180072BFC
0x180072bee  cmp     eax, 425h
0x180072bf3  jz      short loc_180072BFC
0x180072bf5  cmp     eax, 5B4h
0x180072bfa  jnz     short loc_180072C11
0x180072bfc  mov     ecx, 9C4h; dwMilliseconds
0x180072c01  call    cs:__imp_Sleep
0x180072c08  nop     dword ptr [rax+rax+00h]
0x180072c0d  inc     edi
0x180072c0f  jmp     short loc_180072BAB
0x180072c11  test    eax, eax
0x180072c13  jz      short loc_180072C3B
0x180072c15  mov     r9d, eax
0x180072c18  mov     edx, 0E1h
0x180072c1d  jmp     loc_180072B7D
0x180072c22  mov     rcx, rbx; hService
0x180072c25  call    ?ServiceWaitForNotifyStatus@Common@@YAKPEAUSC_HANDLE__@@K@Z; Common::ServiceWaitForNotifyStatus(SC_HANDLE__ *,ulong)
0x180072c2a  test    eax, eax
0x180072c2c  jz      short loc_180072C3B
0x180072c2e  mov     r9d, eax
0x180072c31  mov     edx, 0E9h
0x180072c36  jmp     loc_180072B7D
0x180072c3b  lea     rcx, [rbp+57h+var_80]
0x180072c3f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072c44  lea     rcx, [rbp+57h+var_88]
0x180072c48  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072c4d  xor     eax, eax
0x180072c4f  jmp     short loc_180072C95
0x180072c51  mov     edx, 9Fh; void *
0x180072c56  mov     rcx, [rbp+5Fh]; this
0x180072c5a  lea     r8, aOnecoreAdminAp_62; "onecore\\admin\\appmodel\\common\\servi"...
0x180072c61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072c66  lea     rcx, [rbp+57h+var_80]
0x180072c6a  mov     ebx, eax
0x180072c6c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072c71  jmp     short loc_180072C8A
0x180072c73  mov     rcx, [rbp+5Fh]; this
0x180072c77  lea     r8, aOnecoreAdminAp_62; "onecore\\admin\\appmodel\\common\\servi"...
0x180072c7e  mov     edx, 94h; void *
0x180072c83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072c88  mov     ebx, eax
0x180072c8a  lea     rcx, [rbp+57h+var_88]
0x180072c8e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072c93  mov     eax, ebx
0x180072c95  mov     rcx, [rbp+57h+var_30]
0x180072c99  xor     rcx, rsp; StackCookie
0x180072c9c  call    __security_check_cookie
0x180072ca1  add     rsp, 0A8h
0x180072ca8  pop     rdi
0x180072ca9  pop     rsi
0x180072caa  pop     rbx
0x180072cab  pop     rbp
0x180072cac  retn
```
