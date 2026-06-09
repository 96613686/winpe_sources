# OrchestratorDBManager::SetNotificationStatus(void *,_GUID,DCLifecycleNotificationType,long,ulong)

- ea: `0x18010b390`
- end: `0x18010b697`
- name: `?SetNotificationStatus@OrchestratorDBManager@@QEAAJPEAXU_GUID@@W4DCLifecycleNotificationType@@JK@Z`
- size: `775`
- prototype: `int __high(void *, struct _GUID, enum DCLifecycleNotificationType, int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180110f10`
- `0x18011109c`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x180011fe0`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x18009a2e4`
- `0x1800f5c8c`
- `0x1800f9380`
- `0x1800fdefc`
- `0x18010a054`
- `0x18010a628`
- `0x18010b390`
- `0x18010b6a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010b643`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010b643`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b487`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b4c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b500`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b5cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b62d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b487`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b4c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b500`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b5cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010b62d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18010b517`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18010b517`

## string_xrefs

- `0x18010b400`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OrchestratorDBManager::SetNotificationStatus(
        __int64 a1,
        void *a2,
        struct _SYSTEMTIME *a3,
        int a4,
        int a5)
{
  int v6; // ebx
  OrchestratorDBManager *v8; // rcx
  signed int DMOrchestratorKey; // esi
  CDeclaredConfigurationLogger *Logger; // rax
  HKEY v11; // rbx
  LSTATUS v12; // eax
  bool v13; // cc
  const unsigned __int16 *v14; // r8
  int v15; // eax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  const char *cbData; // [rsp+28h] [rbp-D8h]
  const char *cbDataa; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v22[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v25[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  *(_DWORD *)Data = a4;
  *(_DWORD *)v21 = 0;
  SystemTime = *a3;
  v6 = GUIDToStringWithoutBracket(&SystemTime, v24);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8D2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
      (const char *)(unsigned int)v6,
      (int)"failed to convert GUID to string with no bracket",
      cbData);
    return (unsigned int)v6;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  DMOrchestratorKey = OrchestratorDBManager::GetDMOrchestratorKey(v8, &hKey, v24, 0);
  if ( DMOrchestratorKey >= 0 )
  {
    v11 = hKey;
    v12 = RegSetValueExW(hKey, L"LifecycleNotificationStatus", 0, 4u, Data, 4u);
    v13 = v12 <= 0;
    if ( !v12 )
    {
      v12 = RegSetValueExW(v11, L"LifecycleNotificationHResult", 0, 4u, (const BYTE *)&a5, 4u);
      v13 = v12 <= 0;
      if ( !v12 )
      {
        if ( a5 >= 0 )
          goto LABEL_15;
        v12 = RegSetValueExW(v11, L"State", 0, 4u, (const BYTE *)&a5, 4u);
        v13 = v12 <= 0;
        if ( !v12 )
        {
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          memset_0(v25, 0, 0x208u);
          LODWORD(cbDataa) = SystemTime.wDay;
          LODWORD(lpData) = SystemTime.wMonth;
          if ( StringCchPrintfW(
                 v25,
                 0x104u,
                 L"%d-%02d-%02d %02d:%02d:%02d.%03d",
                 SystemTime.wYear,
                 lpData,
                 cbDataa,
                 SystemTime.wHour,
                 SystemTime.wMinute,
                 SystemTime.wSecond,
                 SystemTime.wMilliseconds) >= 0 )
          {
            *(_QWORD *)v22 = 0;
            if ( (int)StringCbLengthW(v25, 0x208u, (unsigned __int64 *)v22) >= 0 )
              RegSetValueExW(v11, L"Time", 0, 1u, (const BYTE *)v25, v22[0]);
          }
LABEL_15:
          if ( ((*(_DWORD *)Data - 1) & 0xFFFFFFFB) != 0 )
          {
            if ( (*(_DWORD *)Data & 0xFFFFFFFB) != 0 )
            {
              if ( *(_DWORD *)Data != 10 )
              {
LABEL_20:
                v12 = RegSetValueExW(v11, L"LifecycleNotificationProgress", 0, 4u, v21, 4u);
                v13 = v12 <= 0;
                if ( !v12 )
                {
                  if ( a2 )
                    SetEvent(a2);
                  goto LABEL_23;
                }
                goto LABEL_6;
              }
              v15 = OrchestratorDBManager::SetRegistryDWORD((OrchestratorDBManager *)0xA, v11, v14, L"State", 4u);
            }
            else
            {
              v15 = OrchestratorDBManager::SetRegistryDWORD(
                      (OrchestratorDBManager *)*(unsigned int *)Data,
                      v11,
                      v14,
                      L"State",
                      2u);
            }
          }
          else
          {
            v15 = OrchestratorDBManager::SetRegistryDWORD(
                    (OrchestratorDBManager *)*(unsigned int *)Data,
                    v11,
                    v14,
                    L"State",
                    3u);
          }
          DMOrchestratorKey = v15;
          if ( v15 < 0 )
            goto LABEL_23;
          goto LABEL_20;
        }
      }
    }
LABEL_6:
    if ( v13 )
      DMOrchestratorKey = v12;
    else
      DMOrchestratorKey = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_23;
  }
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogFindScenarioIdError(Logger, v24, DMOrchestratorKey);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)DMOrchestratorKey;
}

```

## disassembly

```asm
0x18010b390  mov     [rsp-8+arg_0], rbx
0x18010b395  push    rbp
0x18010b396  push    rsi
0x18010b397  push    rdi
0x18010b398  push    r12
0x18010b39a  push    r14
0x18010b39c  lea     rbp, [rsp-1F0h]
0x18010b3a4  sub     rsp, 2F0h
0x18010b3ab  mov     rax, cs:__security_cookie
0x18010b3b2  xor     rax, rsp
0x18010b3b5  mov     [rbp+210h+var_30], rax
0x18010b3bc  mov     r14, rdx
0x18010b3bf  mov     dword ptr [rsp+310h+Data], r9d
0x18010b3c4  mov     dword ptr [rsp+310h+var_2B0], 0
0x18010b3cc  movaps  xmm0, xmmword ptr [r8]
0x18010b3d0  movdqa  xmmword ptr [rsp+310h+SystemTime.wYear], xmm0
0x18010b3d6  lea     rdx, [rbp+210h+var_290]
0x18010b3da  lea     rcx, [rsp+310h+SystemTime]
0x18010b3df  call    GUIDToStringWithoutBracket
0x18010b3e4  mov     ebx, eax
0x18010b3e6  test    eax, eax
0x18010b3e8  jns     short loc_18010B418
0x18010b3ea  mov     rcx, [rbp+218h]; this
0x18010b3f1  lea     rax, aFailedToConver_1; "failed to convert GUID to string with n"...
0x18010b3f8  mov     [rsp+310h+lpData], rax; int
0x18010b3fd  mov     r9d, ebx; char *
0x18010b400  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010b407  mov     edx, 8D2h; void *
0x18010b40c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010b411  mov     eax, ebx
0x18010b413  jmp     loc_18010B656
0x18010b418  mov     [rsp+310h+hKey], 0
0x18010b421  xor     edx, edx
0x18010b423  lea     rcx, [rsp+310h+hKey]
0x18010b428  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18010b42d  xor     r9d, r9d; int
0x18010b430  lea     r8, [rbp+210h+var_290]; unsigned __int16 *
0x18010b434  lea     rdx, [rsp+310h+hKey]; HKEY *
0x18010b439  call    ?GetDMOrchestratorKey@OrchestratorDBManager@@QEAAJPEAPEAUHKEY__@@PEBGH@Z; OrchestratorDBManager::GetDMOrchestratorKey(HKEY__ * *,ushort const *,int)
0x18010b43e  mov     esi, eax
0x18010b440  test    eax, eax
0x18010b442  jns     short loc_18010B45D
0x18010b444  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18010b449  mov     r8d, esi; int
0x18010b44c  lea     rdx, [rbp+210h+var_290]; unsigned __int16 *
0x18010b450  mov     rcx, rax; this
0x18010b453  call    ?LogFindScenarioIdError@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogFindScenarioIdError(ushort const *,long)
0x18010b458  jmp     loc_18010B64A
0x18010b45d  mov     r12d, 4
0x18010b463  mov     dword ptr [rsp+310h+cbData], r12d; cbData
0x18010b468  lea     rax, [rsp+310h+Data]
0x18010b46d  mov     [rsp+310h+lpData], rax; lpData
0x18010b472  mov     r9d, r12d; dwType
0x18010b475  xor     r8d, r8d; Reserved
0x18010b478  lea     rdx, aLifecyclenotif_1; "LifecycleNotificationStatus"
0x18010b47f  mov     rbx, [rsp+310h+hKey]
0x18010b484  mov     rcx, rbx; hKey
0x18010b487  call    cs:__imp_RegSetValueExW
0x18010b48d  test    eax, eax
0x18010b48f  jz      short loc_18010B4A8
0x18010b491  jg      short loc_18010B49A
0x18010b493  mov     esi, eax
0x18010b495  jmp     loc_18010B64A
0x18010b49a  movzx   esi, ax
0x18010b49d  or      esi, 80070000h
0x18010b4a3  jmp     loc_18010B64A
0x18010b4a8  mov     dword ptr [rsp+310h+cbData], r12d; cbData
0x18010b4ad  lea     rax, [rbp+210h+arg_20]
0x18010b4b4  mov     [rsp+310h+lpData], rax; lpData
0x18010b4b9  mov     r9d, r12d; dwType
0x18010b4bc  xor     r8d, r8d; Reserved
0x18010b4bf  lea     rdx, aLifecyclenotif; "LifecycleNotificationHResult"
0x18010b4c6  mov     rcx, rbx; hKey
0x18010b4c9  call    cs:__imp_RegSetValueExW
0x18010b4cf  test    eax, eax
0x18010b4d1  jnz     short loc_18010B491
0x18010b4d3  cmp     [rbp+210h+arg_20], eax
0x18010b4d9  jge     loc_18010B5D3
0x18010b4df  mov     dword ptr [rsp+310h+cbData], r12d; cbData
0x18010b4e4  lea     rax, [rbp+210h+arg_20]
0x18010b4eb  mov     [rsp+310h+lpData], rax; lpData
0x18010b4f0  mov     r9d, r12d; dwType
0x18010b4f3  xor     r8d, r8d; Reserved
0x18010b4f6  lea     rdx, aState; "State"
0x18010b4fd  mov     rcx, rbx; hKey
0x18010b500  call    cs:__imp_RegSetValueExW
0x18010b506  test    eax, eax
0x18010b508  jnz     short loc_18010B491
0x18010b50a  xorps   xmm0, xmm0
0x18010b50d  movups  xmmword ptr [rsp+310h+SystemTime.wYear], xmm0
0x18010b512  lea     rcx, [rsp+310h+SystemTime]; lpSystemTime
0x18010b517  call    cs:__imp_GetSystemTime
0x18010b51d  xor     edx, edx; Val
0x18010b51f  mov     r8d, 208h; Size
0x18010b525  lea     rcx, [rbp+210h+var_240]; void *
0x18010b529  call    memset_0
0x18010b52e  movzx   eax, [rsp+310h+SystemTime.wMilliseconds]
0x18010b533  movzx   ecx, [rsp+310h+SystemTime.wSecond]
0x18010b538  movzx   r8d, [rsp+310h+SystemTime.wMinute]
0x18010b53e  movzx   r10d, [rsp+310h+SystemTime.wHour]
0x18010b544  movzx   r11d, [rsp+310h+SystemTime.wDay]
0x18010b54a  movzx   edi, [rsp+310h+SystemTime.wMonth]
0x18010b54f  movzx   r9d, [rsp+310h+SystemTime.wYear]
0x18010b555  mov     [rsp+310h+var_2C8], eax
0x18010b559  mov     [rsp+310h+var_2D0], ecx
0x18010b55d  mov     [rsp+310h+var_2D8], r8d
0x18010b562  mov     [rsp+310h+var_2E0], r10d
0x18010b567  mov     dword ptr [rsp+310h+cbData], r11d
0x18010b56c  mov     dword ptr [rsp+310h+lpData], edi
0x18010b570  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x18010b577  mov     edx, 104h; unsigned __int64
0x18010b57c  lea     rcx, [rbp+210h+var_240]; unsigned __int16 *
0x18010b580  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010b585  test    eax, eax
0x18010b587  js      short loc_18010B5D3
0x18010b589  mov     qword ptr [rsp+310h+var_2A8], 0
0x18010b592  lea     r8, [rsp+310h+var_2A8]; unsigned __int64 *
0x18010b597  mov     edx, 208h; unsigned __int64
0x18010b59c  lea     rcx, [rbp+210h+var_240]; unsigned __int16 *
0x18010b5a0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18010b5a5  test    eax, eax
0x18010b5a7  js      short loc_18010B5D3
0x18010b5a9  mov     eax, [rsp+310h+var_2A8]
0x18010b5ad  mov     dword ptr [rsp+310h+cbData], eax; cbData
0x18010b5b1  lea     rax, [rbp+210h+var_240]
0x18010b5b5  mov     [rsp+310h+lpData], rax; lpData
0x18010b5ba  mov     r9d, 1; dwType
0x18010b5c0  xor     r8d, r8d; Reserved
0x18010b5c3  lea     rdx, aTime; "Time"
0x18010b5ca  mov     rcx, rbx; hKey
0x18010b5cd  call    cs:__imp_RegSetValueExW
0x18010b5d3  mov     ecx, dword ptr [rsp+310h+Data]; this
0x18010b5d7  lea     eax, [rcx-1]
0x18010b5da  mov     edx, 0FFFFFFFBh
0x18010b5df  test    edx, eax
0x18010b5e1  jz      loc_18010B689
0x18010b5e7  test    edx, ecx
0x18010b5e9  jz      loc_18010B67C
0x18010b5ef  cmp     ecx, 0Ah
0x18010b5f2  jnz     short loc_18010B60E
0x18010b5f4  mov     dword ptr [rsp+310h+lpData], r12d; unsigned int
0x18010b5f9  lea     r9, aState; "State"
0x18010b600  mov     rdx, rbx; HKEY
0x18010b603  call    ?SetRegistryDWORD@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG1K@Z; OrchestratorDBManager::SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18010b608  mov     esi, eax
0x18010b60a  test    eax, eax
0x18010b60c  js      short loc_18010B64A
0x18010b60e  mov     dword ptr [rsp+310h+cbData], r12d; cbData
0x18010b613  lea     rax, [rsp+310h+var_2B0]
0x18010b618  mov     [rsp+310h+lpData], rax; lpData
0x18010b61d  mov     r9d, r12d; dwType
0x18010b620  xor     r8d, r8d; Reserved
0x18010b623  lea     rdx, aLifecyclenotif_0; "LifecycleNotificationProgress"
0x18010b62a  mov     rcx, rbx; hKey
0x18010b62d  call    cs:__imp_RegSetValueExW
0x18010b633  test    eax, eax
0x18010b635  jnz     loc_18010B491
0x18010b63b  test    r14, r14
0x18010b63e  jz      short loc_18010B64A
0x18010b640  mov     rcx, r14; hEvent
0x18010b643  call    cs:__imp_SetEvent
0x18010b649  nop
0x18010b64a  lea     rcx, [rsp+310h+hKey]
0x18010b64f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010b654  mov     eax, esi
0x18010b656  mov     rcx, [rbp+210h+var_30]
0x18010b65d  xor     rcx, rsp; StackCookie
0x18010b660  call    __security_check_cookie
0x18010b665  mov     rbx, [rsp+310h+arg_0]
0x18010b66d  add     rsp, 2F0h
0x18010b674  pop     r14
0x18010b676  pop     r12
0x18010b678  pop     rdi
0x18010b679  pop     rsi
0x18010b67a  pop     rbp
0x18010b67b  retn
0x18010b67c  mov     dword ptr [rsp+310h+lpData], 2
0x18010b684  jmp     loc_18010B5F9
0x18010b689  mov     dword ptr [rsp+310h+lpData], 3
0x18010b691  jmp     loc_18010B5F9
```
