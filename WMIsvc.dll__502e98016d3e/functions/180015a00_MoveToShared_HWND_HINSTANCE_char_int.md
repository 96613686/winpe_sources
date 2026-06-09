# MoveToShared(HWND__ *,HINSTANCE__ *,char *,int)

- ea: `0x180015a00`
- end: `0x180015d93`
- name: `?MoveToShared@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEADH@Z`
- size: `915`
- prototype: `int(HWND, HINSTANCE, char *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003b08`
- `0x18000ca20`
- `0x1800103e0`
- `0x1800150ec`
- `0x180015a00`
- `0x180015d9c`
- `0x18001d3a0`

## import_xrefs

- `msvcrt!atoi` at `0x180015a3a`
- `msvcrt!atoi` at `0x180015a3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015aef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015aef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015be6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015be6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015bd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d58`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015c71`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015c71`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015c03`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015c03`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180015c29`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180015c29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015d3d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015d50`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015d3d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015d50`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015c50`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015c9e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015c50`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015c9e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180015d10`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180015d10`

## string_xrefs

- `0x180015b25`: `CoInitializeSecurityParam`
- `0x180015b90`: `ImpersonationLevel`
- `0x180015bfa`: `ServicesActive`
- `0x180015caf`: `%%systemroot%%\system32\svchost.exe -k %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MoveToShared(HWND a1, HINSTANCE a2, char *a3)
{
  int v3; // r14d
  DWORD LastError; // esi
  HKEY v5; // rbx
  HKEY v6; // rdi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rbx
  _DWORD *v11; // rdi
  struct _QUERY_SERVICE_CONFIGW *v12; // rdx
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v15; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  HKEY v18; // [rsp+80h] [rbp-80h]
  HKEY v19; // [rsp+88h] [rbp-78h]
  WCHAR BinaryPathName[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = 4;
  if ( a3 )
  {
    v3 = atoi(a3);
    if ( !v3 )
      v3 = 4;
  }
  hKey = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost",
                0,
                0xF003Fu,
                &hKey);
  if ( !LastError )
  {
    v5 = hKey;
    v18 = hKey;
    LastError = AddServiceToMultiString(hKey, L"netsvcs");
    if ( !LastError )
    {
      v15 = 0;
      dwDisposition = 0;
      LastError = RegCreateKeyExW(hKey, L"netsvcs", 0, 0, 0, 0xF003Fu, 0, &v15, &dwDisposition);
      if ( !LastError )
      {
        v6 = v15;
        v19 = v15;
        *(_DWORD *)Data = 1;
        LastError = RegSetValueExW(v15, L"CoInitializeSecurityParam", 0, 4u, Data, 4u);
        if ( !LastError )
        {
          *(_DWORD *)Data = v3;
          LastError = RegSetValueExW(v15, L"AuthenticationLevel", 0, 4u, Data, 4u);
          if ( !LastError )
          {
            *(_DWORD *)Data = 2;
            LastError = RegSetValueExW(v15, L"ImpersonationLevel", 0, 4u, Data, 4u);
            if ( !LastError )
            {
              *(_DWORD *)Data = 12320;
              LastError = RegSetValueExW(v15, L"AuthenticationCapabilities", 0, 4u, Data, 4u);
            }
          }
        }
        RegCloseKey(v6);
      }
    }
    RegCloseKey(v5);
    if ( !LastError )
    {
      v7 = OpenSCManagerW(0, L"ServicesActive", 0xF003Fu);
      v8 = v7;
      if ( v7 )
      {
        v19 = (HKEY)v7;
        v9 = OpenServiceW(v7, L"winmgmt", 0xF01FFu);
        v10 = v9;
        if ( v9 )
        {
          v18 = (HKEY)v9;
          *(_DWORD *)Data = 0;
          if ( QueryServiceConfigW(v9, 0, 0, (LPDWORD)Data) || GetLastError() != 122 )
          {
            LastError = 13;
          }
          else
          {
            v11 = CWin32DefaultArena::WbemMemAlloc(*(unsigned int *)Data);
            std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(&hKey, v11);
            if ( v12 )
            {
              if ( !QueryServiceConfigW(v10, v12, *(DWORD *)Data, (LPDWORD)Data)
                || (StringCchPrintfW(BinaryPathName, 0x104u, L"%%systemroot%%\\system32\\svchost.exe -k %s", L"netsvcs"),
                    !ChangeServiceConfigW(
                       v10,
                       *v11,
                       v11[1],
                       v11[2],
                       BinaryPathName,
                       *((LPCWSTR *)v11 + 3),
                       0,
                       *((LPCWSTR *)v11 + 5),
                       *((LPCWSTR *)v11 + 6),
                       0,
                       *((LPCWSTR *)v11 + 7))) )
              {
                LastError = GetLastError();
              }
            }
            else
            {
              LastError = 14;
            }
            CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(&hKey);
          }
          CloseServiceHandle(v10);
        }
        else
        {
          LastError = GetLastError();
        }
        CloseServiceHandle(v8);
      }
      else
      {
        LastError = GetLastError();
      }
      if ( !LastError )
        return (unsigned int)RemoveServiceFromMultiString(L"winmgmt");
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180015a00  push    rbp
0x180015a02  push    rbx
0x180015a03  push    rsi
0x180015a04  push    rdi
0x180015a05  push    r12
0x180015a07  push    r14
0x180015a09  lea     rbp, [rsp-1B8h]
0x180015a11  sub     rsp, 2B8h
0x180015a18  mov     rax, cs:__security_cookie
0x180015a1f  xor     rax, rsp
0x180015a22  mov     [rbp+1E0h+var_40], rax
0x180015a29  mov     r12d, 4
0x180015a2f  mov     r14d, r12d
0x180015a32  test    r8, r8
0x180015a35  jz      short loc_180015A49
0x180015a37  mov     rcx, r8; String
0x180015a3a  call    cs:__imp_atoi
0x180015a40  mov     r14d, eax
0x180015a43  test    eax, eax
0x180015a45  cmovz   r14d, r12d
0x180015a49  mov     [rsp+2E0h+hKey], 0
0x180015a52  lea     rax, [rsp+2E0h+hKey]
0x180015a57  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180015a5c  mov     r9d, 0F003Fh; samDesired
0x180015a62  xor     r8d, r8d; ulOptions
0x180015a65  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015a6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015a73  call    cs:__imp_RegOpenKeyExW
0x180015a79  mov     esi, eax
0x180015a7b  test    eax, eax
0x180015a7d  jnz     loc_180015D72
0x180015a83  mov     rbx, [rsp+2E0h+hKey]
0x180015a88  mov     [rbp+1E0h+var_260], rbx
0x180015a8c  lea     rdx, aNetsvcs_0; "netsvcs"
0x180015a93  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015a98  call    ?AddServiceToMultiString@@YAJPEAUHKEY__@@PEBG@Z; AddServiceToMultiString(HKEY__ *,ushort const *)
0x180015a9d  mov     esi, eax
0x180015a9f  test    eax, eax
0x180015aa1  jnz     loc_180015BE3
0x180015aa7  mov     [rsp+2E0h+var_278], 0
0x180015ab0  mov     [rsp+2E0h+dwDisposition], eax
0x180015ab4  lea     rax, [rsp+2E0h+dwDisposition]
0x180015ab9  mov     [rsp+2E0h+lpdwDisposition], rax; lpdwDisposition
0x180015abe  lea     rax, [rsp+2E0h+var_278]
0x180015ac3  mov     [rsp+2E0h+var_2A8], rax; phkResult
0x180015ac8  mov     [rsp+2E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180015ad1  mov     [rsp+2E0h+samDesired], 0F003Fh; samDesired
0x180015ad9  mov     dword ptr [rsp+2E0h+phkResult], esi; dwOptions
0x180015add  xor     r9d, r9d; lpClass
0x180015ae0  xor     r8d, r8d; Reserved
0x180015ae3  lea     rdx, aNetsvcs_0; "netsvcs"
0x180015aea  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015aef  call    cs:__imp_RegCreateKeyExW
0x180015af5  mov     esi, eax
0x180015af7  test    eax, eax
0x180015af9  jnz     loc_180015BE3
0x180015aff  mov     rdi, [rsp+2E0h+var_278]
0x180015b04  mov     [rbp+1E0h+var_258], rdi
0x180015b08  mov     dword ptr [rsp+2E0h+Data], 1
0x180015b10  mov     [rsp+2E0h+samDesired], r12d; cbData
0x180015b15  lea     rax, [rsp+2E0h+Data]
0x180015b1a  mov     [rsp+2E0h+phkResult], rax; lpData
0x180015b1f  mov     r9d, r12d; dwType
0x180015b22  xor     r8d, r8d; Reserved
0x180015b25  lea     rdx, aCoinitializese; "CoInitializeSecurityParam"
0x180015b2c  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180015b31  call    cs:__imp_RegSetValueExW
0x180015b37  mov     esi, eax
0x180015b39  test    eax, eax
0x180015b3b  jnz     loc_180015BD9
0x180015b41  mov     dword ptr [rsp+2E0h+Data], r14d
0x180015b46  mov     [rsp+2E0h+samDesired], r12d; cbData
0x180015b4b  lea     rax, [rsp+2E0h+Data]
0x180015b50  mov     [rsp+2E0h+phkResult], rax; lpData
0x180015b55  mov     r9d, r12d; dwType
0x180015b58  xor     r8d, r8d; Reserved
0x180015b5b  lea     rdx, aAuthentication; "AuthenticationLevel"
0x180015b62  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180015b67  call    cs:__imp_RegSetValueExW
0x180015b6d  mov     esi, eax
0x180015b6f  test    eax, eax
0x180015b71  jnz     short loc_180015BD9
0x180015b73  mov     dword ptr [rsp+2E0h+Data], 2
0x180015b7b  mov     [rsp+2E0h+samDesired], r12d; cbData
0x180015b80  lea     rax, [rsp+2E0h+Data]
0x180015b85  mov     [rsp+2E0h+phkResult], rax; lpData
0x180015b8a  mov     r9d, r12d; dwType
0x180015b8d  xor     r8d, r8d; Reserved
0x180015b90  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x180015b97  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180015b9c  call    cs:__imp_RegSetValueExW
0x180015ba2  mov     esi, eax
0x180015ba4  test    eax, eax
0x180015ba6  jnz     short loc_180015BD9
0x180015ba8  mov     dword ptr [rsp+2E0h+Data], 3020h
0x180015bb0  mov     [rsp+2E0h+samDesired], r12d; cbData
0x180015bb5  lea     rax, [rsp+2E0h+Data]
0x180015bba  mov     [rsp+2E0h+phkResult], rax; lpData
0x180015bbf  mov     r9d, r12d; dwType
0x180015bc2  xor     r8d, r8d; Reserved
0x180015bc5  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x180015bcc  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180015bd1  call    cs:__imp_RegSetValueExW
0x180015bd7  mov     esi, eax
0x180015bd9  mov     rcx, rdi; hKey
0x180015bdc  call    cs:__imp_RegCloseKey
0x180015be2  nop
0x180015be3  mov     rcx, rbx; hKey
0x180015be6  call    cs:__imp_RegCloseKey
0x180015bec  test    esi, esi
0x180015bee  jnz     loc_180015D72
0x180015bf4  mov     r8d, 0F003Fh; dwDesiredAccess
0x180015bfa  lea     rdx, DatabaseName; "ServicesActive"
0x180015c01  xor     ecx, ecx; lpMachineName
0x180015c03  call    cs:__imp_OpenSCManagerW
0x180015c09  mov     r14, rax
0x180015c0c  test    rax, rax
0x180015c0f  jz      loc_180015D58
0x180015c15  mov     [rbp+1E0h+var_258], rax
0x180015c19  mov     r8d, 0F01FFh; dwDesiredAccess
0x180015c1f  lea     rdx, ServiceName; "winmgmt"
0x180015c26  mov     rcx, rax; hSCManager
0x180015c29  call    cs:__imp_OpenServiceW
0x180015c2f  mov     rbx, rax
0x180015c32  test    rax, rax
0x180015c35  jz      loc_180015D45
0x180015c3b  mov     [rbp+1E0h+var_260], rax
0x180015c3f  mov     dword ptr [rsp+2E0h+Data], esi
0x180015c43  lea     r9, [rsp+2E0h+Data]; pcbBytesNeeded
0x180015c48  xor     r8d, r8d; cbBufSize
0x180015c4b  xor     edx, edx; lpServiceConfig
0x180015c4d  mov     rcx, rax; hService
0x180015c50  call    cs:__imp_QueryServiceConfigW
0x180015c56  test    eax, eax
0x180015c58  jnz     loc_180015D35
0x180015c5e  call    cs:__imp_GetLastError
0x180015c64  cmp     eax, 7Ah ; 'z'
0x180015c67  jnz     loc_180015D35
0x180015c6d  mov     ecx, dword ptr [rsp+2E0h+Data]
0x180015c71  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015c77  mov     rdi, rax
0x180015c7a  mov     rdx, rax
0x180015c7d  lea     rcx, [rsp+2E0h+hKey]
0x180015c82  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x180015c87  nop
0x180015c88  test    rdx, rdx
0x180015c8b  jz      loc_180015D24
0x180015c91  lea     r9, [rsp+2E0h+Data]; pcbBytesNeeded
0x180015c96  mov     r8d, dword ptr [rsp+2E0h+Data]; cbBufSize
0x180015c9b  mov     rcx, rbx; hService
0x180015c9e  call    cs:__imp_QueryServiceConfigW
0x180015ca4  test    eax, eax
0x180015ca6  jz      short loc_180015D1A
0x180015ca8  lea     r9, aNetsvcs_0; "netsvcs"
0x180015caf  lea     r8, aSystemrootSyst; "%%systemroot%%\\system32\\svchost.exe -"...
0x180015cb6  mov     edx, 104h; unsigned __int64
0x180015cbb  lea     rcx, [rbp+1E0h+BinaryPathName]; unsigned __int16 *
0x180015cbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015cc4  mov     rax, [rdi+38h]
0x180015cc8  mov     [rsp+2E0h+lpDisplayName], rax; lpDisplayName
0x180015ccd  mov     [rsp+2E0h+lpPassword], 0; lpPassword
0x180015cd6  mov     rax, [rdi+30h]
0x180015cda  mov     [rsp+2E0h+lpdwDisposition], rax; lpServiceStartName
0x180015cdf  mov     rax, [rdi+28h]
0x180015ce3  mov     [rsp+2E0h+var_2A8], rax; lpDependencies
0x180015ce8  mov     [rsp+2E0h+lpSecurityAttributes], 0; lpdwTagId
0x180015cf1  mov     rax, [rdi+18h]
0x180015cf5  mov     qword ptr [rsp+2E0h+samDesired], rax; lpLoadOrderGroup
0x180015cfa  lea     rax, [rbp+1E0h+BinaryPathName]
0x180015cfe  mov     [rsp+2E0h+phkResult], rax; lpBinaryPathName
0x180015d03  mov     r9d, [rdi+8]; dwErrorControl
0x180015d07  mov     r8d, [rdi+4]; dwStartType
0x180015d0b  mov     edx, [rdi]; dwServiceType
0x180015d0d  mov     rcx, rbx; hService
0x180015d10  call    cs:__imp_ChangeServiceConfigW
0x180015d16  test    eax, eax
0x180015d18  jnz     short loc_180015D29
0x180015d1a  call    cs:__imp_GetLastError
0x180015d20  mov     esi, eax
0x180015d22  jmp     short loc_180015D29
0x180015d24  mov     esi, 0Eh
0x180015d29  lea     rcx, [rsp+2E0h+hKey]
0x180015d2e  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x180015d33  jmp     short loc_180015D3A
0x180015d35  mov     esi, 0Dh
0x180015d3a  mov     rcx, rbx; hSCObject
0x180015d3d  call    cs:__imp_CloseServiceHandle
0x180015d43  jmp     short loc_180015D4D
0x180015d45  call    cs:__imp_GetLastError
0x180015d4b  mov     esi, eax
0x180015d4d  mov     rcx, r14; hSCObject
0x180015d50  call    cs:__imp_CloseServiceHandle
0x180015d56  jmp     short loc_180015D60
0x180015d58  call    cs:__imp_GetLastError
0x180015d5e  mov     esi, eax
0x180015d60  test    esi, esi
0x180015d62  jnz     short loc_180015D72
0x180015d64  lea     rcx, ServiceName; "winmgmt"
0x180015d6b  call    ?RemoveServiceFromMultiString@@YAJPEBG@Z; RemoveServiceFromMultiString(ushort const *)
0x180015d70  mov     esi, eax
0x180015d72  mov     eax, esi
0x180015d74  mov     rcx, [rbp+1E0h+var_40]
0x180015d7b  xor     rcx, rsp; StackCookie
0x180015d7e  call    __security_check_cookie
0x180015d83  add     rsp, 2B8h
0x180015d8a  pop     r14
0x180015d8c  pop     r12
0x180015d8e  pop     rdi
0x180015d8f  pop     rsi
0x180015d90  pop     rbx
0x180015d91  pop     rbp
0x180015d92  retn
```
