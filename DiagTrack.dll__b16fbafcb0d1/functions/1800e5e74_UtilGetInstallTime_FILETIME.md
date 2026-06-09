# UtilGetInstallTime(_FILETIME *)

- ea: `0x1800e5e74`
- end: `0x1800e615e`
- name: `?UtilGetInstallTime@@YAJPEAU_FILETIME@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18019c878`

## callees

- `0x1800e5e74`
- `0x1800e6240`
- `0x1801e19ac`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6088`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5fad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5fad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5f40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e600e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6065`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5f40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e600e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6065`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5f1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5fe9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e6149`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5f1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5fe9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e6149`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800e607a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800e607a`

## string_xrefs

- `0x1800e5ed4`: `Software\Microsoft\WindowsUpdate\Orchestrator\Installation\Target`
- `0x1800e5efa`: `UpdateTimestamp`
- `0x1800e5fc8`: `OobeCompleteTime`

## pseudocode

```c
__int64 __fastcall UtilGetInstallTime(LPFILETIME lpFileTime)
{
  LSTATUS ValueW; // eax
  char v3; // di
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned int v6; // ebx
  LSTATUS v8; // eax
  char v9; // di
  LSTATUS v10; // eax
  signed int LastError; // eax
  HKEY hkey; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 pvData; // [rsp+48h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-20h] BYREF
  DWORD v15; // [rsp+54h] [rbp-1Ch] BYREF
  SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  v15 = 16;
  pvData = 0;
  pcbData = 8;
  hkey = 0;
  SystemTime = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Installation\\Target",
             0,
             0x101u,
             &hkey);
  if ( !ValueW )
  {
    ValueW = RegGetValueW(hkey, 0, L"UpdateTimestamp", 0x40u, 0, &pvData, &pcbData);
    if ( !ValueW )
    {
      v3 = 0;
LABEL_4:
      v4 = pvData;
      goto LABEL_5;
    }
  }
  v3 = 0;
  if ( (int)ERROR_HR_FROM_WIN32(ValueW) >= 0 )
    goto LABEL_4;
  v4 = 0;
  v3 = 1;
  pvData = 0;
LABEL_5:
  v5 = HIDWORD(v4);
  if ( hkey )
    RegCloseKey(hkey);
  if ( !v3 )
    goto LABEL_8;
  pvData = 0;
  pcbData = 8;
  hkey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Shell\\OOBE", 0, 0x101u, &hkey);
  if ( !v8 )
  {
    v8 = RegGetValueW(hkey, 0, L"OobeCompleteTime", 0x40u, 0, &pvData, &pcbData);
    if ( !v8 )
    {
      v9 = 0;
LABEL_14:
      v4 = pvData;
      goto LABEL_15;
    }
  }
  v9 = 0;
  if ( (int)ERROR_HR_FROM_WIN32(v8) >= 0 )
    goto LABEL_14;
  v4 = 0;
  v9 = 1;
  pvData = 0;
LABEL_15:
  v5 = HIDWORD(v4);
  if ( hkey )
    RegCloseKey(hkey);
  if ( !v9 )
  {
LABEL_8:
    lpFileTime->dwLowDateTime = v4;
    lpFileTime->dwHighDateTime = v5;
    return 0;
  }
  hkey = 0;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
          0,
          0x101u,
          &hkey);
  if ( v10 || (v10 = RegGetValueW(hkey, 0, L"EndTimeStamp", 8u, 0, &SystemTime, &v15)) != 0 )
    v6 = ERROR_HR_FROM_WIN32(v10);
  else
    v6 = 0;
  if ( hkey )
    RegCloseKey(hkey);
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( SystemTimeToFileTime(&SystemTime, lpFileTime) )
      return 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800e5e74  mov     [rsp-18h+arg_8], rbx
0x1800e5e79  mov     [rsp-18h+arg_10], rsi
0x1800e5e7e  push    rbp
0x1800e5e7f  push    rdi
0x1800e5e80  push    r14
0x1800e5e82  mov     rbp, rsp
0x1800e5e85  sub     rsp, 70h
0x1800e5e89  mov     rax, cs:__security_cookie
0x1800e5e90  xor     rax, rsp
0x1800e5e93  mov     [rbp+var_8], rax
0x1800e5e97  mov     rsi, rcx
0x1800e5e9a  mov     [rbp+var_1C], 10h
0x1800e5ea1  xorps   xmm0, xmm0
0x1800e5ea4  mov     [rbp+var_28], 0
0x1800e5eac  lea     rax, [rbp+hkey]
0x1800e5eb0  mov     [rbp+var_20], 8
0x1800e5eb7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e5ebe  mov     [rsp+70h+phkResult], rax; phkResult
0x1800e5ec3  mov     r9d, 101h; samDesired
0x1800e5ec9  mov     [rbp+hkey], 0
0x1800e5ed1  xor     r8d, r8d; ulOptions
0x1800e5ed4  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x1800e5edb  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800e5edf  call    cs:__imp_RegOpenKeyExW
0x1800e5ee5  test    eax, eax
0x1800e5ee7  jnz     loc_1800E60DB
0x1800e5eed  mov     rcx, [rbp+hkey]; hkey
0x1800e5ef1  lea     rax, [rbp+var_20]
0x1800e5ef5  mov     [rsp+70h+pcbData], rax; pcbData
0x1800e5efa  lea     r8, aUpdatetimestam; "UpdateTimestamp"
0x1800e5f01  lea     rax, [rbp+var_28]
0x1800e5f05  mov     r9d, 40h ; '@'; dwFlags
0x1800e5f0b  mov     [rsp+70h+pvData], rax; pvData
0x1800e5f10  xor     edx, edx; lpSubKey
0x1800e5f12  mov     [rsp+70h+phkResult], 0; pdwType
0x1800e5f1b  call    cs:__imp_RegGetValueW
0x1800e5f21  test    eax, eax
0x1800e5f23  jnz     loc_1800E60DB
0x1800e5f29  xor     dil, dil
0x1800e5f2c  mov     rbx, [rbp+var_28]
0x1800e5f30  mov     rcx, [rbp+hkey]; hKey
0x1800e5f34  mov     r14, rbx
0x1800e5f37  shr     r14, 20h
0x1800e5f3b  test    rcx, rcx
0x1800e5f3e  jz      short loc_1800E5F46
0x1800e5f40  call    cs:__imp_RegCloseKey
0x1800e5f46  test    dil, dil
0x1800e5f49  jnz     short loc_1800E5F76
0x1800e5f4b  mov     [rsi], ebx
0x1800e5f4d  mov     [rsi+4], r14d
0x1800e5f51  xor     ebx, ebx
0x1800e5f53  mov     eax, ebx
0x1800e5f55  mov     rcx, [rbp+var_8]
0x1800e5f59  xor     rcx, rsp; StackCookie
0x1800e5f5c  call    __security_check_cookie
0x1800e5f61  lea     r11, [rsp+70h+var_s0]
0x1800e5f66  mov     rbx, [r11+28h]
0x1800e5f6a  mov     rsi, [r11+30h]
0x1800e5f6e  mov     rsp, r11
0x1800e5f71  pop     r14
0x1800e5f73  pop     rdi
0x1800e5f74  pop     rbp
0x1800e5f75  retn
0x1800e5f76  lea     rax, [rbp+hkey]
0x1800e5f7a  mov     [rbp+var_28], 0
0x1800e5f82  mov     r9d, 101h; samDesired
0x1800e5f88  mov     [rsp+70h+phkResult], rax; phkResult
0x1800e5f8d  xor     r8d, r8d; ulOptions
0x1800e5f90  mov     [rbp+var_20], 8
0x1800e5f97  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Shell\\OOBE"
0x1800e5f9e  mov     [rbp+hkey], 0
0x1800e5fa6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e5fad  call    cs:__imp_RegOpenKeyExW
0x1800e5fb3  test    eax, eax
0x1800e5fb5  jnz     loc_1800E60FB
0x1800e5fbb  mov     rcx, [rbp+hkey]; hkey
0x1800e5fbf  lea     rax, [rbp+var_20]
0x1800e5fc3  mov     [rsp+70h+pcbData], rax; pcbData
0x1800e5fc8  lea     r8, aOobecompleteti; "OobeCompleteTime"
0x1800e5fcf  lea     rax, [rbp+var_28]
0x1800e5fd3  mov     r9d, 40h ; '@'; dwFlags
0x1800e5fd9  mov     [rsp+70h+pvData], rax; pvData
0x1800e5fde  xor     edx, edx; lpSubKey
0x1800e5fe0  mov     [rsp+70h+phkResult], 0; pdwType
0x1800e5fe9  call    cs:__imp_RegGetValueW
0x1800e5fef  test    eax, eax
0x1800e5ff1  jnz     loc_1800E60FB
0x1800e5ff7  xor     dil, dil
0x1800e5ffa  mov     rbx, [rbp+var_28]
0x1800e5ffe  mov     rcx, [rbp+hkey]; hKey
0x1800e6002  mov     r14, rbx
0x1800e6005  shr     r14, 20h
0x1800e6009  test    rcx, rcx
0x1800e600c  jz      short loc_1800E6014
0x1800e600e  call    cs:__imp_RegCloseKey
0x1800e6014  test    dil, dil
0x1800e6017  jz      loc_1800E5F4B
0x1800e601d  lea     rax, [rbp+hkey]
0x1800e6021  mov     [rbp+hkey], 0
0x1800e6029  mov     r9d, 101h; samDesired
0x1800e602f  mov     [rsp+70h+phkResult], rax; phkResult
0x1800e6034  xor     r8d, r8d; ulOptions
0x1800e6037  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800e603e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e6045  call    cs:__imp_RegOpenKeyExW
0x1800e604b  test    eax, eax
0x1800e604d  jz      loc_1800E611B
0x1800e6053  mov     ecx, eax; unsigned int
0x1800e6055  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800e605a  mov     ebx, eax
0x1800e605c  mov     rcx, [rbp+hkey]; hKey
0x1800e6060  test    rcx, rcx
0x1800e6063  jz      short loc_1800E606B
0x1800e6065  call    cs:__imp_RegCloseKey
0x1800e606b  test    ebx, ebx
0x1800e606d  js      loc_1800E5F53
0x1800e6073  mov     rdx, rsi; lpFileTime
0x1800e6076  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800e607a  call    cs:__imp_SystemTimeToFileTime
0x1800e6080  test    eax, eax
0x1800e6082  jnz     loc_1800E5F51
0x1800e6088  call    cs:__imp_GetLastError
0x1800e608e  mov     ebx, eax
0x1800e6090  test    eax, eax
0x1800e6092  jle     short loc_1800E609D
0x1800e6094  movzx   ebx, ax
0x1800e6097  or      ebx, 80070000h
0x1800e609d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60a4  lea     rax, WPP_GLOBAL_Control
0x1800e60ab  cmp     rcx, rax
0x1800e60ae  jz      loc_1800E5F53
0x1800e60b4  test    byte ptr [rcx+1Ch], 1
0x1800e60b8  jz      loc_1800E5F53
0x1800e60be  mov     rcx, [rcx+10h]
0x1800e60c2  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e60c9  mov     edx, 0A5h
0x1800e60ce  mov     r9d, ebx
0x1800e60d1  call    WPP_SF_d
0x1800e60d6  jmp     loc_1800E5F53
0x1800e60db  mov     ecx, eax; unsigned int
0x1800e60dd  xor     dil, dil
0x1800e60e0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800e60e5  test    eax, eax
0x1800e60e7  jns     loc_1800E5F2C
0x1800e60ed  xor     ebx, ebx
0x1800e60ef  mov     dil, 1
0x1800e60f2  mov     [rbp+var_28], rbx
0x1800e60f6  jmp     loc_1800E5F30
0x1800e60fb  mov     ecx, eax; unsigned int
0x1800e60fd  xor     dil, dil
0x1800e6100  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800e6105  test    eax, eax
0x1800e6107  jns     loc_1800E5FFA
0x1800e610d  xor     ebx, ebx
0x1800e610f  mov     dil, 1
0x1800e6112  mov     [rbp+var_28], rbx
0x1800e6116  jmp     loc_1800E5FFE
0x1800e611b  mov     rcx, [rbp+hkey]; hkey
0x1800e611f  lea     rax, [rbp+var_1C]
0x1800e6123  mov     [rsp+70h+pcbData], rax; pcbData
0x1800e6128  lea     r8, aEndtimestamp; "EndTimeStamp"
0x1800e612f  lea     rax, [rbp+SystemTime]
0x1800e6133  mov     r9d, 8; dwFlags
0x1800e6139  mov     [rsp+70h+pvData], rax; pvData
0x1800e613e  xor     edx, edx; lpSubKey
0x1800e6140  mov     [rsp+70h+phkResult], 0; pdwType
0x1800e6149  call    cs:__imp_RegGetValueW
0x1800e614f  test    eax, eax
0x1800e6151  jnz     loc_1800E6053
0x1800e6157  xor     ebx, ebx
0x1800e6159  jmp     loc_1800E605C
```
