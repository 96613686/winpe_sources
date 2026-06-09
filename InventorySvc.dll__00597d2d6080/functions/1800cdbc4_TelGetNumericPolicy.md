# TelGetNumericPolicy

- ea: `0x1800cdbc4`
- end: `0x1800cdf0f`
- name: `TelGetNumericPolicy`
- size: `843`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cda24`
- `0x1800ce224`

## callees

- `0x18000ec54`
- `0x1800cd9e8`
- `0x1800cdbc4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdcec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd24`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd47`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddb3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdde1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddf8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cde0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cde26`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdcec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd24`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd47`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdd98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddb3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdde1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cddf8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cde0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cde26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdc35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdc48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdc35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdc48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cdc1d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cdc1d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cdec6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cdec6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cde65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cde65`

## string_xrefs

- `0x1800cdc08`: `policymanager.dll`
- `0x1800cdd1a`: `ConfigureTelemetryOptInSettingsUx`
- `0x1800cdcfa`: `ConfigureTelemetryOptInChangeNotification`
- `0x1800cdd70`: `AllowCommercialDataPipeline`
- `0x1800cdd3a`: `DisableDeviceDelete`

## pseudocode

```c
__int64 __fastcall TelGetNumericPolicy(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  HMODULE Library; // rax
  HMODULE v7; // r14
  FARPROC ProcAddress; // rbx
  __int64 (*v9)(void); // r12
  signed int v10; // ebx
  _DWORD *v11; // rcx
  const WCHAR *v12; // rbx
  LSTATUS ValueW; // eax
  int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rdx
  int pdwType; // [rsp+20h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  _DWORD *v23; // [rsp+98h] [rbp+48h] BYREF

  if ( !a1 || !a2 || !a3 )
  {
    v10 = -2147024809;
    v17 = 454;
    goto LABEL_47;
  }
  *a3 = 0;
  *a2 = 0;
  Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PolicyManager_GetPolicy");
    v9 = GetProcAddress(v7, "PolicyManager_FreeGetPolicyData");
  }
  else
  {
    ProcAddress = 0;
    v9 = 0;
  }
  v23 = 0;
  v20 = 0;
  if ( !ProcAddress || !v9 )
  {
    v12 = L"LimitEnhancedDiagnosticDataWindowsAnalytics";
    if ( (unsigned int)_o__wcsicmp(a1, L"LimitEnhancedDiagnosticDataWindowsAnalytics") )
    {
      if ( (unsigned int)_o__wcsicmp(a1, L"ConfigureTelemetryOptInChangeNotification") )
      {
        if ( (unsigned int)_o__wcsicmp(a1, L"ConfigureTelemetryOptInSettingsUx") )
        {
          v12 = L"DisableDeviceDelete";
          if ( (unsigned int)_o__wcsicmp(a1, L"DisableDeviceDelete") )
          {
            v12 = L"DisableDiagnosticDataViewer";
            if ( (unsigned int)_o__wcsicmp(a1, L"DisableDiagnosticDataViewer") )
            {
              v12 = L"AllowCommercialDataPipeline";
              if ( (unsigned int)_o__wcsicmp(a1, L"AllowCommercialDataPipeline") )
              {
                v12 = L"AllowTelemetry";
                if ( (unsigned int)_o__wcsicmp(a1, L"AllowTelemetry") )
                {
                  v12 = L"LimitDumpCollection";
                  if ( (unsigned int)_o__wcsicmp(a1, L"LimitDumpCollection") )
                  {
                    v12 = L"LimitDiagnosticLogCollection";
                    if ( (unsigned int)_o__wcsicmp(a1, L"LimitDiagnosticLogCollection") )
                    {
                      v12 = L"DisableEnterpriseAuthProxy";
                      if ( (unsigned int)_o__wcsicmp(a1, L"DisableEnterpriseAuthProxy") )
                      {
                        v12 = L"AllowDeviceNameInDiagnosticData";
                        if ( (unsigned int)_o__wcsicmp(a1, L"AllowDeviceNameInDiagnosticData") )
                        {
                          v12 = L"DisableOneSettingsDownloads";
                          if ( (unsigned int)_o__wcsicmp(a1, L"DisableOneSettingsDownloads") )
                          {
                            v12 = L"EnableOneSettingsAuditing";
                            if ( (unsigned int)_o__wcsicmp(a1, L"EnableOneSettingsAuditing") )
                            {
                              v10 = -2147024809;
                              goto LABEL_38;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          v12 = L"DisableTelemetryOptInSettingsUx";
        }
      }
      else
      {
        v12 = L"DisableTelemetryOptInChangeNotification";
      }
    }
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Policies\\Microsoft\\Windows\\DataCollection",
               v12,
               0x18u,
               0,
               a3,
               &pcbData);
    v10 = ValueW;
    if ( ValueW > 0 )
      v10 = (unsigned __int16)ValueW | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_35;
    *a2 = 1;
LABEL_38:
    v11 = v23;
    goto LABEL_39;
  }
  v20 = 0x200000001LL;
  v10 = ((__int64 (__fastcall *)(const wchar_t *, __int64, __int64 *, _DWORD **))ProcAddress)(L"System", a1, &v20, &v23);
  if ( v10 >= 0 )
  {
    v11 = v23;
    if ( v23 )
    {
      if ( !v23[1] )
      {
        *a2 = 0;
        goto LABEL_39;
      }
      if ( v23[2] == 1 )
      {
        *a3 = v23[4];
        *a2 = 1;
        goto LABEL_39;
      }
    }
    v10 = -2147024883;
    goto LABEL_39;
  }
LABEL_35:
  v11 = v23;
  if ( v10 == -2147024894 )
  {
    v10 = 0;
    *a2 = 0;
  }
LABEL_39:
  if ( v11 )
  {
    v14 = v9();
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v15, v16, (const char *)(unsigned int)v14, pdwType);
  }
  if ( v7 )
    FreeLibrary(v7);
  if ( v10 < 0 )
  {
    v17 = 596;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\telemetry\\permission\\lib\\telemetrypermission.cpp",
      (const char *)(unsigned int)v10,
      pdwType);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800cdbc4  mov     [rsp-28h+arg_8], rbx
0x1800cdbc9  mov     [rsp-28h+arg_10], rsi
0x1800cdbce  push    rbp
0x1800cdbcf  push    rdi
0x1800cdbd0  push    r12
0x1800cdbd2  push    r14
0x1800cdbd4  push    r15
0x1800cdbd6  mov     rbp, rsp
0x1800cdbd9  sub     rsp, 50h
0x1800cdbdd  mov     r15, r8
0x1800cdbe0  mov     rsi, rdx
0x1800cdbe3  mov     rdi, rcx
0x1800cdbe6  test    rcx, rcx
0x1800cdbe9  jz      loc_1800CDED7
0x1800cdbef  test    rdx, rdx
0x1800cdbf2  jz      loc_1800CDED7
0x1800cdbf8  test    r8, r8
0x1800cdbfb  jz      loc_1800CDED7
0x1800cdc01  mov     dword ptr [r8], 0
0x1800cdc08  lea     rcx, aPolicymanagerD; "policymanager.dll"
0x1800cdc0f  mov     dword ptr [rdx], 0
0x1800cdc15  mov     r8d, 800h; dwFlags
0x1800cdc1b  xor     edx, edx; hFile
0x1800cdc1d  call    cs:__imp_LoadLibraryExW
0x1800cdc23  mov     r14, rax
0x1800cdc26  test    rax, rax
0x1800cdc29  jz      short loc_1800CDC53
0x1800cdc2b  lea     rdx, aPolicymanagerG; "PolicyManager_GetPolicy"
0x1800cdc32  mov     rcx, rax; hModule
0x1800cdc35  call    cs:__imp_GetProcAddress
0x1800cdc3b  lea     rdx, aPolicymanagerF; "PolicyManager_FreeGetPolicyData"
0x1800cdc42  mov     rcx, r14; hModule
0x1800cdc45  mov     rbx, rax
0x1800cdc48  call    cs:__imp_GetProcAddress
0x1800cdc4e  mov     r12, rax
0x1800cdc51  jmp     short loc_1800CDC58
0x1800cdc53  xor     ebx, ebx
0x1800cdc55  xor     r12d, r12d
0x1800cdc58  mov     [rbp+arg_18], 0
0x1800cdc60  mov     [rbp+var_10], 0
0x1800cdc68  test    rbx, rbx
0x1800cdc6b  jz      short loc_1800CDCDF
0x1800cdc6d  test    r12, r12
0x1800cdc70  jz      short loc_1800CDCDF
0x1800cdc72  lea     r9, [rbp+arg_18]
0x1800cdc76  mov     dword ptr [rbp+var_10], 1
0x1800cdc7d  lea     r8, [rbp+var_10]
0x1800cdc81  mov     dword ptr [rbp+var_10+4], 2
0x1800cdc88  mov     rdx, rdi
0x1800cdc8b  lea     rcx, aSystem; "System"
0x1800cdc92  mov     rax, rbx
0x1800cdc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdc9a  mov     ebx, eax
0x1800cdc9c  test    eax, eax
0x1800cdc9e  js      loc_1800CDE86
0x1800cdca4  mov     rcx, [rbp+arg_18]
0x1800cdca8  test    rcx, rcx
0x1800cdcab  jz      short loc_1800CDCD5
0x1800cdcad  cmp     dword ptr [rcx+4], 0
0x1800cdcb1  jnz     short loc_1800CDCBE
0x1800cdcb3  mov     dword ptr [rsi], 0
0x1800cdcb9  jmp     loc_1800CDEA1
0x1800cdcbe  cmp     dword ptr [rcx+8], 1
0x1800cdcc2  jnz     short loc_1800CDCD5
0x1800cdcc4  mov     eax, [rcx+10h]
0x1800cdcc7  mov     [r15], eax
0x1800cdcca  mov     dword ptr [rsi], 1
0x1800cdcd0  jmp     loc_1800CDEA1
0x1800cdcd5  mov     ebx, 8007000Dh
0x1800cdcda  jmp     loc_1800CDEA1
0x1800cdcdf  lea     rbx, aLimitenhancedd; "LimitEnhancedDiagnosticDataWindowsAnaly"...
0x1800cdce6  mov     rcx, rdi
0x1800cdce9  mov     rdx, rbx
0x1800cdcec  call    cs:__imp__o__wcsicmp
0x1800cdcf2  test    eax, eax
0x1800cdcf4  jz      loc_1800CDE30
0x1800cdcfa  lea     rdx, aConfiguretelem_0; "ConfigureTelemetryOptInChangeNotificati"...
0x1800cdd01  mov     rcx, rdi
0x1800cdd04  call    cs:__imp__o__wcsicmp
0x1800cdd0a  test    eax, eax
0x1800cdd0c  jnz     short loc_1800CDD1A
0x1800cdd0e  lea     rbx, aDisabletelemet; "DisableTelemetryOptInChangeNotification"
0x1800cdd15  jmp     loc_1800CDE30
0x1800cdd1a  lea     rdx, aConfiguretelem; "ConfigureTelemetryOptInSettingsUx"
0x1800cdd21  mov     rcx, rdi
0x1800cdd24  call    cs:__imp__o__wcsicmp
0x1800cdd2a  test    eax, eax
0x1800cdd2c  jnz     short loc_1800CDD3A
0x1800cdd2e  lea     rbx, aDisabletelemet_0; "DisableTelemetryOptInSettingsUx"
0x1800cdd35  jmp     loc_1800CDE30
0x1800cdd3a  lea     rbx, aDisabledeviced; "DisableDeviceDelete"
0x1800cdd41  mov     rcx, rdi
0x1800cdd44  mov     rdx, rbx
0x1800cdd47  call    cs:__imp__o__wcsicmp
0x1800cdd4d  test    eax, eax
0x1800cdd4f  jz      loc_1800CDE30
0x1800cdd55  lea     rbx, aDisablediagnos; "DisableDiagnosticDataViewer"
0x1800cdd5c  mov     rcx, rdi
0x1800cdd5f  mov     rdx, rbx
0x1800cdd62  call    cs:__imp__o__wcsicmp
0x1800cdd68  test    eax, eax
0x1800cdd6a  jz      loc_1800CDE30
0x1800cdd70  lea     rbx, aAllowcommercia; "AllowCommercialDataPipeline"
0x1800cdd77  mov     rcx, rdi
0x1800cdd7a  mov     rdx, rbx
0x1800cdd7d  call    cs:__imp__o__wcsicmp
0x1800cdd83  test    eax, eax
0x1800cdd85  jz      loc_1800CDE30
0x1800cdd8b  lea     rbx, aAllowtelemetry_0; "AllowTelemetry"
0x1800cdd92  mov     rcx, rdi
0x1800cdd95  mov     rdx, rbx
0x1800cdd98  call    cs:__imp__o__wcsicmp
0x1800cdd9e  test    eax, eax
0x1800cdda0  jz      loc_1800CDE30
0x1800cdda6  lea     rbx, aLimitdumpcolle; "LimitDumpCollection"
0x1800cddad  mov     rcx, rdi
0x1800cddb0  mov     rdx, rbx
0x1800cddb3  call    cs:__imp__o__wcsicmp
0x1800cddb9  test    eax, eax
0x1800cddbb  jz      short loc_1800CDE30
0x1800cddbd  lea     rbx, aLimitdiagnosti; "LimitDiagnosticLogCollection"
0x1800cddc4  mov     rcx, rdi
0x1800cddc7  mov     rdx, rbx
0x1800cddca  call    cs:__imp__o__wcsicmp
0x1800cddd0  test    eax, eax
0x1800cddd2  jz      short loc_1800CDE30
0x1800cddd4  lea     rbx, aDisableenterpr; "DisableEnterpriseAuthProxy"
0x1800cdddb  mov     rcx, rdi
0x1800cddde  mov     rdx, rbx
0x1800cdde1  call    cs:__imp__o__wcsicmp
0x1800cdde7  test    eax, eax
0x1800cdde9  jz      short loc_1800CDE30
0x1800cddeb  lea     rbx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800cddf2  mov     rcx, rdi
0x1800cddf5  mov     rdx, rbx
0x1800cddf8  call    cs:__imp__o__wcsicmp
0x1800cddfe  test    eax, eax
0x1800cde00  jz      short loc_1800CDE30
0x1800cde02  lea     rbx, aDisableonesett; "DisableOneSettingsDownloads"
0x1800cde09  mov     rcx, rdi
0x1800cde0c  mov     rdx, rbx
0x1800cde0f  call    cs:__imp__o__wcsicmp
0x1800cde15  test    eax, eax
0x1800cde17  jz      short loc_1800CDE30
0x1800cde19  lea     rbx, aEnableonesetti; "EnableOneSettingsAuditing"
0x1800cde20  mov     rcx, rdi
0x1800cde23  mov     rdx, rbx
0x1800cde26  call    cs:__imp__o__wcsicmp
0x1800cde2c  test    eax, eax
0x1800cde2e  jnz     short loc_1800CDE98
0x1800cde30  lea     rax, [rbp+arg_0]
0x1800cde34  mov     [rbp+arg_0], 4
0x1800cde3b  mov     [rsp+50h+pcbData], rax; pcbData
0x1800cde40  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800cde47  mov     [rsp+50h+pvData], r15; pvData
0x1800cde4c  mov     r9d, 18h; dwFlags
0x1800cde52  mov     r8, rbx; lpValue
0x1800cde55  mov     [rsp+50h+pdwType], 0; pdwType
0x1800cde5e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800cde65  call    cs:__imp_RegGetValueW
0x1800cde6b  mov     ebx, eax
0x1800cde6d  test    eax, eax
0x1800cde6f  jle     short loc_1800CDE7A
0x1800cde71  movzx   ebx, ax
0x1800cde74  or      ebx, 80070000h
0x1800cde7a  test    ebx, ebx
0x1800cde7c  js      short loc_1800CDE86
0x1800cde7e  mov     dword ptr [rsi], 1
0x1800cde84  jmp     short loc_1800CDE9D
0x1800cde86  mov     rcx, [rbp+arg_18]
0x1800cde8a  cmp     ebx, 80070002h
0x1800cde90  jnz     short loc_1800CDEA1
0x1800cde92  xor     ebx, ebx
0x1800cde94  mov     [rsi], ebx
0x1800cde96  jmp     short loc_1800CDEA1
0x1800cde98  mov     ebx, 80070057h
0x1800cde9d  mov     rcx, [rbp+arg_18]
0x1800cdea1  test    rcx, rcx
0x1800cdea4  jz      short loc_1800CDEBE
0x1800cdea6  mov     rax, r12
0x1800cdea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdeae  test    eax, eax
0x1800cdeb0  jns     short loc_1800CDEBE
0x1800cdeb2  mov     rcx, [rbp+28h]; this
0x1800cdeb6  mov     r9d, eax; char *
0x1800cdeb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cdebe  test    r14, r14
0x1800cdec1  jz      short loc_1800CDECC
0x1800cdec3  mov     rcx, r14; hLibModule
0x1800cdec6  call    cs:__imp_FreeLibrary
0x1800cdecc  test    ebx, ebx
0x1800cdece  jns     short loc_1800CDEF4
0x1800cded0  mov     edx, 254h
0x1800cded5  jmp     short loc_1800CDEE1
0x1800cded7  mov     ebx, 80070057h
0x1800cdedc  mov     edx, 1C6h; void *
0x1800cdee1  mov     rcx, [rbp+28h]; this
0x1800cdee5  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\permission\\l"...
0x1800cdeec  mov     r9d, ebx; char *
0x1800cdeef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdef4  lea     r11, [rsp+50h+var_s0]
0x1800cdef9  mov     eax, ebx
0x1800cdefb  mov     rbx, [r11+38h]
0x1800cdeff  mov     rsi, [r11+40h]
0x1800cdf03  mov     rsp, r11
0x1800cdf06  pop     r15
0x1800cdf08  pop     r14
0x1800cdf0a  pop     r12
0x1800cdf0c  pop     rdi
0x1800cdf0d  pop     rbp
0x1800cdf0e  retn
```
