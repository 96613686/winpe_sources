# Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey_Old(wistd::function<long (ushort const *)> &&)

- ea: `0x18002aeb8`
- end: `0x18002b208`
- name: `?ForEachActiveMMKey_Old@NetworkUXManager@UX@Networking@Windows@@AEAAX$$QEAV?$function@$$A6AJPEBG@Z@wistd@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180033538`
- `0x180033a88`

## callees

- `0x180002520`
- `0x18001a2d0`
- `0x180028588`
- `0x1800299b4`
- `0x18002aeb8`
- `0x18002d900`
- `0x180037c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b104`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af2b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002b1d0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002b1d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002afcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002afcc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b03a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b0f5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b03a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b0f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey_Old(__int64 a1, __int64 a2)
{
  int v4; // edi
  DWORD v5; // edx
  HKEY i; // rcx
  _DWORD *v7; // rcx
  _DWORD *v8; // r8
  signed int LastError; // eax
  SC_HANDLE v10; // rcx
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  __int64 dwCurrentState; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  SC_HANDLE v16; // rcx
  unsigned int v17; // eax
  LSTATUS result; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE v24[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v4 = 0;
  v5 = 0;
  for ( i = *(HKEY *)(a1 + 144); ; i = *(HKEY *)(a1 + 144) )
  {
    cchName = 128;
    result = RegEnumKeyExW(i, v5, SubKey, &cchName, 0, 0, 0, 0);
    if ( result == 259 )
      break;
    if ( result )
      goto LABEL_41;
    hKey = 0;
    if ( !RegOpenKeyExW(*(HKEY *)(a1 + 144), SubKey, 0, 0x20019u, &hKey) )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      Type = 0;
      if ( !RegQueryValueExW(hKey, L"Active", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data )
      {
        *(_DWORD *)v24 = 0;
        cbData = 4;
        if ( RegQueryValueExW(hKey, L"MediaType", 0, &Type, v24, &cbData) || Type != 4 )
        {
LABEL_39:
          v17 = wistd::function<long (unsigned short const *)>::operator()(a2, SubKey);
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x2C6,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
            (const char *)v17,
            (int)"Callback for %ls failed",
            (const char *)SubKey);
          goto LABEL_40;
        }
        v7 = *(_DWORD **)(a1 + 152);
        v8 = *(_DWORD **)(a1 + 160);
        if ( v8 != v7 )
        {
          while ( *v7 != *(_DWORD *)v24 )
          {
            if ( ++v7 == v8 )
              goto LABEL_40;
          }
        }
        if ( *(_DWORD *)v24 == 1 )
        {
          LastError = -2147467259;
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          v10 = *(SC_HANDLE *)(a1 + 872);
          if ( v10 )
          {
            if ( QueryServiceStatus(v10, &ServiceStatus) )
            {
              LastError = 0;
            }
            else
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
          }
          v11 = retaddr;
          if ( LastError >= 0 )
          {
            dwCurrentState = ServiceStatus.dwCurrentState;
            if ( ServiceStatus.dwCurrentState == 4 )
              goto LABEL_39;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_40;
            v15 = 42;
LABEL_26:
            WPP_SF_d(v14[2], v15, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids, dwCurrentState);
            goto LABEL_40;
          }
          v12 = 679;
        }
        else
        {
          if ( *(_DWORD *)v24 != 2 )
            goto LABEL_39;
          LastError = -2147467259;
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          v16 = *(SC_HANDLE *)(a1 + 1432);
          if ( v16 )
          {
            if ( QueryServiceStatus(v16, &ServiceStatus) )
            {
              LastError = 0;
            }
            else
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
          }
          v11 = retaddr;
          if ( LastError >= 0 )
          {
            dwCurrentState = ServiceStatus.dwCurrentState;
            if ( ServiceStatus.dwCurrentState == 4 )
              goto LABEL_39;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_40;
            v15 = 43;
            goto LABEL_26;
          }
          v12 = 692;
        }
        wil::details::in1diag3::_Log_Hr(
          v11,
          (void *)v12,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
          (const char *)(unsigned int)LastError,
          phkResult);
      }
    }
LABEL_40:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_41:
    v5 = ++v4;
  }
  return result;
}

```

## disassembly

```asm
0x18002aeb8  mov     [rsp-8+arg_10], rbx
0x18002aebd  mov     [rsp-8+arg_18], rsi
0x18002aec2  push    rbp
0x18002aec3  push    rdi
0x18002aec4  push    r14
0x18002aec6  lea     rbp, [rsp-90h]
0x18002aece  sub     rsp, 190h
0x18002aed5  mov     rax, cs:__security_cookie
0x18002aedc  xor     rax, rsp
0x18002aedf  mov     [rbp+0A0h+var_20], rax
0x18002aee6  mov     rsi, rdx
0x18002aee9  mov     rbx, rcx
0x18002aeec  xor     r14d, r14d
0x18002aeef  mov     edi, r14d
0x18002aef2  xor     edx, edx
0x18002aef4  mov     rcx, [rcx+90h]
0x18002aefb  jmp     loc_18002B1AB
0x18002af00  test    eax, eax
0x18002af02  jnz     loc_18002B1A0
0x18002af08  mov     [rsp+1A0h+hKey], r14
0x18002af0d  lea     rax, [rsp+1A0h+hKey]
0x18002af12  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18002af17  mov     r9d, 20019h; samDesired
0x18002af1d  xor     r8d, r8d; ulOptions
0x18002af20  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x18002af24  mov     rcx, [rbx+90h]; hKey
0x18002af2b  call    cs:__imp_RegOpenKeyExW
0x18002af31  test    eax, eax
0x18002af33  jnz     loc_18002B196
0x18002af39  mov     dword ptr [rsp+1A0h+Data], r14d
0x18002af3e  mov     [rsp+1A0h+cbData], 4
0x18002af46  mov     [rsp+1A0h+Type], r14d
0x18002af4b  lea     rax, [rsp+1A0h+cbData]
0x18002af50  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18002af55  lea     rax, [rsp+1A0h+Data]
0x18002af5a  mov     [rsp+1A0h+phkResult], rax; lpData
0x18002af5f  lea     r9, [rsp+1A0h+Type]; lpType
0x18002af64  xor     r8d, r8d; lpReserved
0x18002af67  lea     rdx, ValueName; "Active"
0x18002af6e  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18002af73  call    cs:__imp_RegQueryValueExW
0x18002af79  test    eax, eax
0x18002af7b  jnz     loc_18002B196
0x18002af81  cmp     [rsp+1A0h+Type], 4
0x18002af86  jnz     loc_18002B196
0x18002af8c  cmp     dword ptr [rsp+1A0h+Data], r14d
0x18002af91  jz      loc_18002B196
0x18002af97  mov     dword ptr [rsp+1A0h+var_150], r14d
0x18002af9c  mov     [rsp+1A0h+cbData], 4
0x18002afa4  lea     rax, [rsp+1A0h+cbData]
0x18002afa9  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18002afae  lea     rax, [rsp+1A0h+var_150]
0x18002afb3  mov     [rsp+1A0h+phkResult], rax; int
0x18002afb8  lea     r9, [rsp+1A0h+Type]; lpType
0x18002afbd  xor     r8d, r8d; lpReserved
0x18002afc0  lea     rdx, aMediatype; "MediaType"
0x18002afc7  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18002afcc  call    cs:__imp_RegQueryValueExW
0x18002afd2  test    eax, eax
0x18002afd4  jnz     loc_18002B159
0x18002afda  cmp     [rsp+1A0h+Type], 4
0x18002afdf  jnz     loc_18002B159
0x18002afe5  mov     edx, dword ptr [rsp+1A0h+var_150]
0x18002afe9  mov     rcx, [rbx+98h]
0x18002aff0  mov     r8, [rbx+0A0h]
0x18002aff7  cmp     r8, rcx
0x18002affa  jz      short loc_18002B00E
0x18002affc  cmp     [rcx], edx
0x18002affe  jz      short loc_18002B00E
0x18002b000  add     rcx, 4
0x18002b004  cmp     rcx, r8
0x18002b007  jnz     short loc_18002AFFC
0x18002b009  jmp     loc_18002B196
0x18002b00e  cmp     edx, 1
0x18002b011  jnz     loc_18002B0C9
0x18002b017  mov     eax, 80004005h
0x18002b01c  xorps   xmm0, xmm0
0x18002b01f  movups  xmmword ptr [rsp+1A0h+ServiceStatus.dwServiceType], xmm0
0x18002b024  movups  xmmword ptr [rsp+1A0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002b029  mov     rcx, [rbx+368h]; hService
0x18002b030  test    rcx, rcx
0x18002b033  jz      short loc_18002B05B
0x18002b035  lea     rdx, [rsp+1A0h+ServiceStatus]; lpServiceStatus
0x18002b03a  call    cs:__imp_QueryServiceStatus
0x18002b040  test    eax, eax
0x18002b042  jz      short loc_18002B049
0x18002b044  mov     eax, r14d
0x18002b047  jmp     short loc_18002B05B
0x18002b049  call    cs:__imp_GetLastError
0x18002b04f  test    eax, eax
0x18002b051  jle     short loc_18002B05B
0x18002b053  movzx   eax, ax
0x18002b056  or      eax, 80070000h
0x18002b05b  mov     rcx, [rbp+0A8h]; this
0x18002b062  test    eax, eax
0x18002b064  jns     short loc_18002B07F
0x18002b066  mov     edx, 2A7h; void *
0x18002b06b  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b072  mov     r9d, eax; char *
0x18002b075  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b07a  jmp     loc_18002B196
0x18002b07f  mov     r9d, [rsp+1A0h+ServiceStatus.dwCurrentState]
0x18002b084  cmp     r9d, 4
0x18002b088  jz      loc_18002B159
0x18002b08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b095  lea     rax, WPP_GLOBAL_Control
0x18002b09c  cmp     rcx, rax
0x18002b09f  jz      loc_18002B196
0x18002b0a5  test    byte ptr [rcx+1Ch], 8
0x18002b0a9  jz      loc_18002B196
0x18002b0af  mov     edx, 2Ah ; '*'
0x18002b0b4  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18002b0bb  mov     rcx, [rcx+10h]
0x18002b0bf  call    WPP_SF_d
0x18002b0c4  jmp     loc_18002B196
0x18002b0c9  cmp     edx, 2
0x18002b0cc  jnz     loc_18002B159
0x18002b0d2  mov     eax, 80004005h
0x18002b0d7  xorps   xmm0, xmm0
0x18002b0da  movups  xmmword ptr [rsp+1A0h+ServiceStatus.dwServiceType], xmm0
0x18002b0df  movups  xmmword ptr [rsp+1A0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002b0e4  mov     rcx, [rbx+598h]; hService
0x18002b0eb  test    rcx, rcx
0x18002b0ee  jz      short loc_18002B116
0x18002b0f0  lea     rdx, [rsp+1A0h+ServiceStatus]; lpServiceStatus
0x18002b0f5  call    cs:__imp_QueryServiceStatus
0x18002b0fb  test    eax, eax
0x18002b0fd  jz      short loc_18002B104
0x18002b0ff  mov     eax, r14d
0x18002b102  jmp     short loc_18002B116
0x18002b104  call    cs:__imp_GetLastError
0x18002b10a  test    eax, eax
0x18002b10c  jle     short loc_18002B116
0x18002b10e  movzx   eax, ax
0x18002b111  or      eax, 80070000h
0x18002b116  mov     rcx, [rbp+0A8h]
0x18002b11d  test    eax, eax
0x18002b11f  jns     short loc_18002B12B
0x18002b121  mov     edx, 2B4h
0x18002b126  jmp     loc_18002B06B
0x18002b12b  mov     r9d, [rsp+1A0h+ServiceStatus.dwCurrentState]
0x18002b130  cmp     r9d, 4
0x18002b134  jz      short loc_18002B159
0x18002b136  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b13d  lea     rax, WPP_GLOBAL_Control
0x18002b144  cmp     rcx, rax
0x18002b147  jz      short loc_18002B196
0x18002b149  test    byte ptr [rcx+1Ch], 8
0x18002b14d  jz      short loc_18002B196
0x18002b14f  mov     edx, 2Bh ; '+'
0x18002b154  jmp     loc_18002B0B4
0x18002b159  lea     rdx, [rbp+0A0h+SubKey]
0x18002b15d  mov     rcx, rsi
0x18002b160  call    ??R?$function@$$A6AJPEBG@Z@wistd@@QEBAJPEBG@Z; wistd::function<long (ushort const *)>::operator()(ushort const *)
0x18002b165  mov     rcx, [rbp+0A8h]; this
0x18002b16c  lea     rdx, [rbp+0A0h+SubKey]
0x18002b170  mov     [rsp+1A0h+lpcbData], rdx; char *
0x18002b175  lea     rdx, aCallbackForLsF; "Callback for %ls failed"
0x18002b17c  mov     [rsp+1A0h+phkResult], rdx; int
0x18002b181  mov     r9d, eax; char *
0x18002b184  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b18b  mov     edx, 2C6h; void *
0x18002b190  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002b195  nop
0x18002b196  lea     rcx, [rsp+1A0h+hKey]
0x18002b19b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b1a0  inc     edi
0x18002b1a2  mov     edx, edi; dwIndex
0x18002b1a4  mov     rcx, [rbx+90h]; hKey
0x18002b1ab  mov     [rsp+1A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002b1b0  mov     [rsp+1A0h+lpcchClass], r14; lpcchClass
0x18002b1b5  mov     [rsp+1A0h+lpcbData], r14; lpClass
0x18002b1ba  mov     [rsp+1A0h+phkResult], r14; lpReserved
0x18002b1bf  mov     [rsp+1A0h+cchName], 80h
0x18002b1c7  lea     r9, [rsp+1A0h+cchName]; lpcchName
0x18002b1cc  lea     r8, [rbp+0A0h+SubKey]; lpName
0x18002b1d0  call    cs:__imp_RegEnumKeyExW
0x18002b1d6  cmp     eax, 103h
0x18002b1db  jnz     loc_18002AF00
0x18002b1e1  mov     rcx, [rbp+0A0h+var_20]
0x18002b1e8  xor     rcx, rsp; StackCookie
0x18002b1eb  call    __security_check_cookie
0x18002b1f0  lea     r11, [rsp+1A0h+var_10]
0x18002b1f8  mov     rbx, [r11+30h]
0x18002b1fc  mov     rsi, [r11+38h]
0x18002b200  mov     rsp, r11
0x18002b203  pop     r14
0x18002b205  pop     rdi
0x18002b206  pop     rbp
0x18002b207  retn
```
