# CFirewallManager::GetFirewallServiceState(int &)

- ea: `0x1801b17f8`
- end: `0x1801b19b5`
- name: `?GetFirewallServiceState@CFirewallManager@@AEAAKAEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(CFirewallManager *__hidden this, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801b163c`
- `0x1801b19bc`
- `0x1801b2204`

## callees

- `0x180112380`
- `0x1801123a8`
- `0x1801b17f8`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b186a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b18c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b192c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b186a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b18c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b192c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801b185c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801b185c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801b18ae`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801b18ae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b18bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b191d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1926`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1957`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1960`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b18bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b191d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1926`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1957`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801b1960`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801b1910`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801b1910`

## pseudocode

```c
__int64 __fastcall CFirewallManager::GetFirewallServiceState(CFirewallManager *this, int *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  DWORD LastError; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rdi
  DWORD v11; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_48d1335b11c73b3238db2ecc14edd4d4_Traceguids);
  *a2 = 1;
  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      return LastError;
    v7 = 86;
LABEL_8:
    WPP_SF_d(v6[2], v7, WPP_48d1335b11c73b3238db2ecc14edd4d4_Traceguids, LastError);
    return LastError;
  }
  v9 = OpenServiceW(v3, L"mpssvc", 4u);
  v10 = v9;
  if ( !v9 )
  {
    CloseServiceHandle(v4);
    v11 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_48d1335b11c73b3238db2ecc14edd4d4_Traceguids, v11);
LABEL_22:
    *a2 = 0;
    return 0;
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !QueryServiceStatus(v9, &ServiceStatus) )
  {
    CloseServiceHandle(v10);
    CloseServiceHandle(v4);
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      return LastError;
    v7 = 88;
    goto LABEL_8;
  }
  CloseServiceHandle(v10);
  CloseServiceHandle(v4);
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_48d1335b11c73b3238db2ecc14edd4d4_Traceguids);
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x1801b17f8  push    rbx
0x1801b17fa  push    rbp
0x1801b17fb  push    rsi
0x1801b17fc  push    rdi
0x1801b17fd  push    r14
0x1801b17ff  push    r15
0x1801b1801  sub     rsp, 58h
0x1801b1805  mov     rax, cs:__security_cookie
0x1801b180c  xor     rax, rsp
0x1801b180f  mov     [rsp+88h+var_48], rax
0x1801b1814  mov     rsi, rdx
0x1801b1817  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b181e  lea     r14, WPP_GLOBAL_Control
0x1801b1825  lea     r15, WPP_48d1335b11c73b3238db2ecc14edd4d4_Traceguids
0x1801b182c  mov     ebp, 400000h
0x1801b1831  cmp     rcx, r14
0x1801b1834  jz      short loc_1801B184C
0x1801b1836  test    [rcx+1Ch], ebp
0x1801b1839  jz      short loc_1801B184C
0x1801b183b  mov     rcx, [rcx+10h]
0x1801b183f  mov     edx, 55h ; 'U'
0x1801b1844  mov     r8, r15
0x1801b1847  call    WPP_SF_
0x1801b184c  xor     edx, edx; lpDatabaseName
0x1801b184e  mov     dword ptr [rsi], 1
0x1801b1854  xor     ecx, ecx; lpMachineName
0x1801b1856  mov     r8d, 0F003Fh; dwDesiredAccess
0x1801b185c  call    cs:__imp_OpenSCManagerW
0x1801b1862  mov     rbx, rax
0x1801b1865  test    rax, rax
0x1801b1868  jnz     short loc_1801B189E
0x1801b186a  call    cs:__imp_GetLastError
0x1801b1870  mov     ebx, eax
0x1801b1872  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b1879  cmp     rcx, r14
0x1801b187c  jz      short loc_1801B1897
0x1801b187e  test    [rcx+1Ch], ebp
0x1801b1881  jz      short loc_1801B1897
0x1801b1883  mov     edx, 56h ; 'V'
0x1801b1888  mov     rcx, [rcx+10h]
0x1801b188c  mov     r9d, ebx
0x1801b188f  mov     r8, r15
0x1801b1892  call    WPP_SF_d
0x1801b1897  mov     eax, ebx
0x1801b1899  jmp     loc_1801B199B
0x1801b189e  mov     r8d, 4; dwDesiredAccess
0x1801b18a4  lea     rdx, ServiceName; "mpssvc"
0x1801b18ab  mov     rcx, rbx; hSCManager
0x1801b18ae  call    cs:__imp_OpenServiceW
0x1801b18b4  mov     rdi, rax
0x1801b18b7  test    rax, rax
0x1801b18ba  jnz     short loc_1801B18FB
0x1801b18bc  mov     rcx, rbx; hSCObject
0x1801b18bf  call    cs:__imp_CloseServiceHandle
0x1801b18c5  call    cs:__imp_GetLastError
0x1801b18cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b18d2  cmp     rcx, r14
0x1801b18d5  jz      loc_1801B1993
0x1801b18db  test    [rcx+1Ch], ebp
0x1801b18de  jz      loc_1801B1993
0x1801b18e4  mov     rcx, [rcx+10h]
0x1801b18e8  lea     edx, [rdi+57h]
0x1801b18eb  mov     r9d, eax
0x1801b18ee  mov     r8, r15
0x1801b18f1  call    WPP_SF_d
0x1801b18f6  jmp     loc_1801B1993
0x1801b18fb  xorps   xmm0, xmm0
0x1801b18fe  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1801b1903  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x1801b1908  mov     rcx, rdi; hService
0x1801b190b  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x1801b1910  call    cs:__imp_QueryServiceStatus
0x1801b1916  mov     rcx, rdi; hSCObject
0x1801b1919  test    eax, eax
0x1801b191b  jnz     short loc_1801B1957
0x1801b191d  call    cs:__imp_CloseServiceHandle
0x1801b1923  mov     rcx, rbx; hSCObject
0x1801b1926  call    cs:__imp_CloseServiceHandle
0x1801b192c  call    cs:__imp_GetLastError
0x1801b1932  mov     ebx, eax
0x1801b1934  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b193b  cmp     rcx, r14
0x1801b193e  jz      loc_1801B1897
0x1801b1944  test    [rcx+1Ch], ebp
0x1801b1947  jz      loc_1801B1897
0x1801b194d  mov     edx, 58h ; 'X'
0x1801b1952  jmp     loc_1801B1888
0x1801b1957  call    cs:__imp_CloseServiceHandle
0x1801b195d  mov     rcx, rbx; hSCObject
0x1801b1960  call    cs:__imp_CloseServiceHandle
0x1801b1966  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 1
0x1801b196b  jnz     short loc_1801B1999
0x1801b196d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b1974  cmp     rcx, r14
0x1801b1977  jz      short loc_1801B1993
0x1801b1979  test    dword ptr [rcx+1Ch], 200000h
0x1801b1980  jz      short loc_1801B1993
0x1801b1982  mov     rcx, [rcx+10h]
0x1801b1986  mov     edx, 59h ; 'Y'
0x1801b198b  mov     r8, r15
0x1801b198e  call    WPP_SF_
0x1801b1993  mov     dword ptr [rsi], 0
0x1801b1999  xor     eax, eax
0x1801b199b  mov     rcx, [rsp+88h+var_48]
0x1801b19a0  xor     rcx, rsp; StackCookie
0x1801b19a3  call    __security_check_cookie
0x1801b19a8  add     rsp, 58h
0x1801b19ac  pop     r15
0x1801b19ae  pop     r14
0x1801b19b0  pop     rdi
0x1801b19b1  pop     rsi
0x1801b19b2  pop     rbp
0x1801b19b3  pop     rbx
0x1801b19b4  retn
```
