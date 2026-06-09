# MoveToAlone(HWND__ *,HINSTANCE__ *,char *,int)

- ea: `0x180015560`
- end: `0x1800159ef`
- name: `?MoveToAlone@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEADH@Z`
- size: `1167`
- prototype: `int(HWND, HINSTANCE, char *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003b08`
- `0x18000ca20`
- `0x1800103e0`
- `0x1800150ec`
- `0x180015560`
- `0x180015d9c`
- `0x18001d3a0`

## import_xrefs

- `msvcrt!atoi` at `0x1800155a3`
- `msvcrt!atoi` at `0x1800155a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800155dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001594a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800155dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001594a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015658`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015658`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001577e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015788`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800159bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001577e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015788`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800159bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001597a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001597a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001569e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800156d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001570c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001573e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015773`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800159af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001569e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800156d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001570c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001573e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015773`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800159af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015813`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015813`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800157a5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800157a5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800157cb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800157cb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800158df`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800158f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800158df`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800158f2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800157f2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015840`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800157f2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015840`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800158b2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800158b2`

## string_xrefs

- `0x180015692`: `CoInitializeSecurityParam`
- `0x1800156ca`: `CoInitializeSecurityAppID`
- `0x180015732`: `ImpersonationLevel`
- `0x18001579c`: `ServicesActive`
- `0x180015851`: `%%systemroot%%\system32\svchost.exe -k %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MoveToAlone(HWND a1, HINSTANCE a2, char *a3)
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
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v16; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  HKEY v18; // [rsp+80h] [rbp-80h]
  HKEY v19; // [rsp+88h] [rbp-78h]
  WCHAR BinaryPathName[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = 2;
  if ( a3 )
  {
    v3 = atoi(a3);
    if ( !v3 )
      v3 = 2;
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
    LastError = AddServiceToMultiString(hKey, L"winmgmt");
    if ( !LastError )
    {
      v16 = 0;
      dwDisposition = 0;
      LastError = RegCreateKeyExW(hKey, L"winmgmt", 0, 0, 0, 0xF003Fu, 0, &v16, &dwDisposition);
      if ( !LastError )
      {
        v6 = v16;
        v19 = v16;
        *(_DWORD *)Data = 1;
        LastError = RegSetValueExW(v16, L"CoInitializeSecurityParam", 0, 4u, Data, 4u);
        if ( !LastError )
        {
          LastError = RegSetValueExW(
                        v16,
                        L"CoInitializeSecurityAppID",
                        0,
                        1u,
                        L"{8BC3F05E-D86B-11D0-A075-00C04FB68820}",
                        0x4Eu);
          if ( !LastError )
          {
            *(_DWORD *)Data = v3;
            LastError = RegSetValueExW(v16, L"AuthenticationLevel", 0, 4u, Data, 4u);
            if ( !LastError )
            {
              *(_DWORD *)Data = 2;
              LastError = RegSetValueExW(v16, L"ImpersonationLevel", 0, 4u, Data, 4u);
              if ( !LastError )
              {
                *(_DWORD *)Data = 12320;
                LastError = RegSetValueExW(v16, L"AuthenticationCapabilities", 0, 4u, Data, 4u);
              }
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
                || (StringCchPrintfW(BinaryPathName, 0x104u, L"%%systemroot%%\\system32\\svchost.exe -k %s", L"winmgmt"),
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
      {
        LastError = RemoveServiceFromMultiString(L"netsvcs");
        if ( !LastError )
        {
          hKey = 0;
          LastError = RegOpenKeyExW(
                        HKEY_LOCAL_MACHINE,
                        L"Software\\classes\\AppID\\{8BC3F05E-D86B-11D0-A075-00C04FB68820}",
                        0,
                        0xF003Fu,
                        &hKey);
          if ( !LastError )
          {
            LastError = RegQueryValueExW(hKey, L"EndPoints", 0, 0, 0, 0);
            if ( LastError )
              LastError = RegSetValueExW(hKey, L"EndPoints", 0, 7u, L"ncacn_ip_tcp,0,24158", 0x2Au);
            RegCloseKey(hKey);
          }
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180015560  mov     [rsp-8+arg_0], rbx
0x180015565  mov     [rsp-8+arg_8], rsi
0x18001556a  push    rbp
0x18001556b  push    rdi
0x18001556c  push    r12
0x18001556e  push    r13
0x180015570  push    r14
0x180015572  lea     rbp, [rsp-1B0h]
0x18001557a  sub     rsp, 2B0h
0x180015581  mov     rax, cs:__security_cookie
0x180015588  xor     rax, rsp
0x18001558b  mov     [rbp+1D0h+var_30], rax
0x180015592  mov     r13d, 2
0x180015598  mov     r14d, r13d
0x18001559b  test    r8, r8
0x18001559e  jz      short loc_1800155B2
0x1800155a0  mov     rcx, r8; String
0x1800155a3  call    cs:__imp_atoi
0x1800155a9  mov     r14d, eax
0x1800155ac  test    eax, eax
0x1800155ae  cmovz   r14d, r13d
0x1800155b2  mov     [rsp+2D0h+hKey], 0
0x1800155bb  lea     rax, [rsp+2D0h+hKey]
0x1800155c0  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800155c5  mov     r9d, 0F003Fh; samDesired
0x1800155cb  xor     r8d, r8d; ulOptions
0x1800155ce  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800155d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800155dc  call    cs:__imp_RegOpenKeyExW
0x1800155e2  mov     esi, eax
0x1800155e4  test    eax, eax
0x1800155e6  jnz     loc_1800159C2
0x1800155ec  mov     rbx, [rsp+2D0h+hKey]
0x1800155f1  mov     [rbp+1D0h+var_250], rbx
0x1800155f5  lea     rdx, ServiceName; "winmgmt"
0x1800155fc  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180015601  call    ?AddServiceToMultiString@@YAJPEAUHKEY__@@PEBG@Z; AddServiceToMultiString(HKEY__ *,ushort const *)
0x180015606  mov     esi, eax
0x180015608  test    eax, eax
0x18001560a  jnz     loc_180015785
0x180015610  mov     [rsp+2D0h+var_260], 0
0x180015619  mov     [rsp+2D0h+dwDisposition], eax
0x18001561d  lea     rax, [rsp+2D0h+dwDisposition]
0x180015622  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x180015627  lea     rax, [rsp+2D0h+var_260]
0x18001562c  mov     [rsp+2D0h+var_298], rax; phkResult
0x180015631  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001563a  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180015642  mov     dword ptr [rsp+2D0h+phkResult], esi; dwOptions
0x180015646  xor     r9d, r9d; lpClass
0x180015649  xor     r8d, r8d; Reserved
0x18001564c  lea     rdx, ServiceName; "winmgmt"
0x180015653  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180015658  call    cs:__imp_RegCreateKeyExW
0x18001565e  mov     esi, eax
0x180015660  test    eax, eax
0x180015662  jnz     loc_180015785
0x180015668  mov     rdi, [rsp+2D0h+var_260]
0x18001566d  mov     [rbp+1D0h+var_248], rdi
0x180015671  mov     dword ptr [rsp+2D0h+Data], 1
0x180015679  lea     r12d, [rax+4]
0x18001567d  mov     [rsp+2D0h+samDesired], r12d; cbData
0x180015682  lea     rax, [rsp+2D0h+Data]
0x180015687  mov     [rsp+2D0h+phkResult], rax; lpData
0x18001568c  mov     r9d, r12d; dwType
0x18001568f  xor     r8d, r8d; Reserved
0x180015692  lea     rdx, aCoinitializese; "CoInitializeSecurityParam"
0x180015699  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18001569e  call    cs:__imp_RegSetValueExW
0x1800156a4  mov     esi, eax
0x1800156a6  test    eax, eax
0x1800156a8  jnz     loc_18001577B
0x1800156ae  mov     [rsp+2D0h+samDesired], 4Eh ; 'N'; cbData
0x1800156b6  lea     rax, a8bc3f05eD86b11; "{8BC3F05E-D86B-11D0-A075-00C04FB68820}"
0x1800156bd  mov     [rsp+2D0h+phkResult], rax; lpData
0x1800156c2  lea     r9d, [r12-3]; dwType
0x1800156c7  xor     r8d, r8d; Reserved
0x1800156ca  lea     rdx, aCoinitializese_0; "CoInitializeSecurityAppID"
0x1800156d1  mov     rcx, [rsp+2D0h+var_260]; hKey
0x1800156d6  call    cs:__imp_RegSetValueExW
0x1800156dc  mov     esi, eax
0x1800156de  test    eax, eax
0x1800156e0  jnz     loc_18001577B
0x1800156e6  mov     dword ptr [rsp+2D0h+Data], r14d
0x1800156eb  mov     [rsp+2D0h+samDesired], r12d; cbData
0x1800156f0  lea     rax, [rsp+2D0h+Data]
0x1800156f5  mov     [rsp+2D0h+phkResult], rax; lpData
0x1800156fa  mov     r9d, r12d; dwType
0x1800156fd  xor     r8d, r8d; Reserved
0x180015700  lea     rdx, aAuthentication; "AuthenticationLevel"
0x180015707  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18001570c  call    cs:__imp_RegSetValueExW
0x180015712  mov     esi, eax
0x180015714  test    eax, eax
0x180015716  jnz     short loc_18001577B
0x180015718  mov     dword ptr [rsp+2D0h+Data], r13d
0x18001571d  mov     [rsp+2D0h+samDesired], r12d; cbData
0x180015722  lea     rax, [rsp+2D0h+Data]
0x180015727  mov     [rsp+2D0h+phkResult], rax; lpData
0x18001572c  mov     r9d, r12d; dwType
0x18001572f  xor     r8d, r8d; Reserved
0x180015732  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x180015739  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18001573e  call    cs:__imp_RegSetValueExW
0x180015744  mov     esi, eax
0x180015746  test    eax, eax
0x180015748  jnz     short loc_18001577B
0x18001574a  mov     dword ptr [rsp+2D0h+Data], 3020h
0x180015752  mov     [rsp+2D0h+samDesired], r12d; cbData
0x180015757  lea     rax, [rsp+2D0h+Data]
0x18001575c  mov     [rsp+2D0h+phkResult], rax; lpData
0x180015761  mov     r9d, r12d; dwType
0x180015764  xor     r8d, r8d; Reserved
0x180015767  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x18001576e  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180015773  call    cs:__imp_RegSetValueExW
0x180015779  mov     esi, eax
0x18001577b  mov     rcx, rdi; hKey
0x18001577e  call    cs:__imp_RegCloseKey
0x180015784  nop
0x180015785  mov     rcx, rbx; hKey
0x180015788  call    cs:__imp_RegCloseKey
0x18001578e  test    esi, esi
0x180015790  jnz     loc_1800159C2
0x180015796  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001579c  lea     rdx, DatabaseName; "ServicesActive"
0x1800157a3  xor     ecx, ecx; lpMachineName
0x1800157a5  call    cs:__imp_OpenSCManagerW
0x1800157ab  mov     r14, rax
0x1800157ae  test    rax, rax
0x1800157b1  jz      loc_1800158FA
0x1800157b7  mov     [rbp+1D0h+var_248], rax
0x1800157bb  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800157c1  lea     rdx, ServiceName; "winmgmt"
0x1800157c8  mov     rcx, rax; hSCManager
0x1800157cb  call    cs:__imp_OpenServiceW
0x1800157d1  mov     rbx, rax
0x1800157d4  test    rax, rax
0x1800157d7  jz      loc_1800158E7
0x1800157dd  mov     [rbp+1D0h+var_250], rax
0x1800157e1  mov     dword ptr [rsp+2D0h+Data], esi
0x1800157e5  lea     r9, [rsp+2D0h+Data]; pcbBytesNeeded
0x1800157ea  xor     r8d, r8d; cbBufSize
0x1800157ed  xor     edx, edx; lpServiceConfig
0x1800157ef  mov     rcx, rax; hService
0x1800157f2  call    cs:__imp_QueryServiceConfigW
0x1800157f8  test    eax, eax
0x1800157fa  jnz     loc_1800158D7
0x180015800  call    cs:__imp_GetLastError
0x180015806  cmp     eax, 7Ah ; 'z'
0x180015809  jnz     loc_1800158D7
0x18001580f  mov     ecx, dword ptr [rsp+2D0h+Data]
0x180015813  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015819  mov     rdi, rax
0x18001581c  mov     rdx, rax
0x18001581f  lea     rcx, [rsp+2D0h+hKey]
0x180015824  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x180015829  nop
0x18001582a  test    rdx, rdx
0x18001582d  jz      loc_1800158C6
0x180015833  lea     r9, [rsp+2D0h+Data]; pcbBytesNeeded
0x180015838  mov     r8d, dword ptr [rsp+2D0h+Data]; cbBufSize
0x18001583d  mov     rcx, rbx; hService
0x180015840  call    cs:__imp_QueryServiceConfigW
0x180015846  test    eax, eax
0x180015848  jz      short loc_1800158BC
0x18001584a  lea     r9, ServiceName; "winmgmt"
0x180015851  lea     r8, aSystemrootSyst; "%%systemroot%%\\system32\\svchost.exe -"...
0x180015858  mov     edx, 104h; unsigned __int64
0x18001585d  lea     rcx, [rbp+1D0h+BinaryPathName]; unsigned __int16 *
0x180015861  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015866  mov     rax, [rdi+38h]
0x18001586a  mov     [rsp+2D0h+lpDisplayName], rax; lpDisplayName
0x18001586f  mov     [rsp+2D0h+lpPassword], 0; lpPassword
0x180015878  mov     rax, [rdi+30h]
0x18001587c  mov     [rsp+2D0h+lpdwDisposition], rax; lpServiceStartName
0x180015881  mov     rax, [rdi+28h]
0x180015885  mov     [rsp+2D0h+var_298], rax; lpDependencies
0x18001588a  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpdwTagId
0x180015893  mov     rax, [rdi+18h]
0x180015897  mov     qword ptr [rsp+2D0h+samDesired], rax; lpLoadOrderGroup
0x18001589c  lea     rax, [rbp+1D0h+BinaryPathName]
0x1800158a0  mov     [rsp+2D0h+phkResult], rax; lpBinaryPathName
0x1800158a5  mov     r9d, [rdi+8]; dwErrorControl
0x1800158a9  mov     r8d, [rdi+4]; dwStartType
0x1800158ad  mov     edx, [rdi]; dwServiceType
0x1800158af  mov     rcx, rbx; hService
0x1800158b2  call    cs:__imp_ChangeServiceConfigW
0x1800158b8  test    eax, eax
0x1800158ba  jnz     short loc_1800158CB
0x1800158bc  call    cs:__imp_GetLastError
0x1800158c2  mov     esi, eax
0x1800158c4  jmp     short loc_1800158CB
0x1800158c6  mov     esi, 0Eh
0x1800158cb  lea     rcx, [rsp+2D0h+hKey]
0x1800158d0  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x1800158d5  jmp     short loc_1800158DC
0x1800158d7  mov     esi, 0Dh
0x1800158dc  mov     rcx, rbx; hSCObject
0x1800158df  call    cs:__imp_CloseServiceHandle
0x1800158e5  jmp     short loc_1800158EF
0x1800158e7  call    cs:__imp_GetLastError
0x1800158ed  mov     esi, eax
0x1800158ef  mov     rcx, r14; hSCObject
0x1800158f2  call    cs:__imp_CloseServiceHandle
0x1800158f8  jmp     short loc_180015902
0x1800158fa  call    cs:__imp_GetLastError
0x180015900  mov     esi, eax
0x180015902  test    esi, esi
0x180015904  jnz     loc_1800159C2
0x18001590a  lea     rcx, aNetsvcs_0; "netsvcs"
0x180015911  call    ?RemoveServiceFromMultiString@@YAJPEBG@Z; RemoveServiceFromMultiString(ushort const *)
0x180015916  mov     esi, eax
0x180015918  test    eax, eax
0x18001591a  jnz     loc_1800159C2
0x180015920  mov     [rsp+2D0h+hKey], 0
0x180015929  lea     rax, [rsp+2D0h+hKey]
0x18001592e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180015933  mov     r9d, 0F003Fh; samDesired
0x180015939  xor     r8d, r8d; ulOptions
0x18001593c  lea     rdx, aSoftwareClasse_2; "Software\\classes\\AppID\\{8BC3F05E-D86"...
0x180015943  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001594a  call    cs:__imp_RegOpenKeyExW
0x180015950  mov     esi, eax
0x180015952  test    eax, eax
0x180015954  jnz     short loc_1800159C2
0x180015956  mov     qword ptr [rsp+2D0h+samDesired], 0; lpcbData
0x18001595f  mov     [rsp+2D0h+phkResult], 0; lpData
0x180015968  xor     r9d, r9d; lpType
0x18001596b  xor     r8d, r8d; lpReserved
0x18001596e  lea     rdx, aEndpoints; "EndPoints"
0x180015975  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001597a  call    cs:__imp_RegQueryValueExW
0x180015980  mov     esi, eax
0x180015982  test    eax, eax
0x180015984  jz      short loc_1800159B7
0x180015986  mov     [rsp+2D0h+samDesired], 2Ah ; '*'; cbData
0x18001598e  lea     rax, aNcacnIpTcp0241; "ncacn_ip_tcp,0,24158"
0x180015995  mov     [rsp+2D0h+phkResult], rax; lpData
0x18001599a  mov     r9d, 7; dwType
0x1800159a0  xor     r8d, r8d; Reserved
0x1800159a3  lea     rdx, aEndpoints; "EndPoints"
0x1800159aa  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800159af  call    cs:__imp_RegSetValueExW
0x1800159b5  mov     esi, eax
0x1800159b7  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800159bc  call    cs:__imp_RegCloseKey
0x1800159c2  mov     eax, esi
0x1800159c4  mov     rcx, [rbp+1D0h+var_30]
0x1800159cb  xor     rcx, rsp; StackCookie
0x1800159ce  call    __security_check_cookie
0x1800159d3  lea     r11, [rsp+2D0h+var_20]
0x1800159db  mov     rbx, [r11+30h]
0x1800159df  mov     rsi, [r11+38h]
0x1800159e3  mov     rsp, r11
0x1800159e6  pop     r14
0x1800159e8  pop     r13
0x1800159ea  pop     r12
0x1800159ec  pop     rdi
0x1800159ed  pop     rbp
0x1800159ee  retn
```
