# UpdateSoftwareInventoryW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180066e80`
- end: `0x180067237`
- name: `?UpdateSoftwareInventoryW@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `951`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180056520`

## callees

- `0x180001200`
- `0x18000243c`
- `0x1800197d4`
- `0x180030038`
- `0x180030fc0`
- `0x1800315c0`
- `0x180031a40`
- `0x180045740`
- `0x18005308c`
- `0x18005318c`
- `0x180059920`
- `0x180059d40`
- `0x18005a8bc`
- `0x180066a50`
- `0x180066e80`
- `0x18010dd68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066ef4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066f2b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066ef4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066f2b`
- `KERNEL32!GetSystemPowerStatus` at `0x180067031`
- `KERNEL32!GetSystemPowerStatus` at `0x180067031`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x180066f13`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1800670c8`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x180066f13`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1800670c8`
- `KERNEL32!GetLastError` at `0x18006703b`
- `KERNEL32!GetLastError` at `0x18006703b`

## string_xrefs

- `0x180066fa7`: `UpdateSoftwareInventoryW`
- `0x180067054`: `UpdateSoftwareInventoryW`
- `0x180067084`: `UpdateSoftwareInventoryW`
- `0x1800671ee`: `UpdateSoftwareInventoryW`
- `0x180067047`: `GetSystemPowerStatus failed [%d]`
- `0x1800671e1`: `UpdateSoftwareInventoryW launched by %s elapsed time: %llu`

## pseudocode

```c
__int64 __fastcall UpdateSoftwareInventoryW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  signed int LastError; // ebx
  BOOL v5; // edi
  wchar_t *v6; // rbx
  __int64 v7; // rcx
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v8; // rcx
  unsigned int AppInventory; // r14d
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  const char *v14; // rax
  void *v15; // [rsp+68h] [rbp-A0h] BYREF
  __int64 (__fastcall **v16)(Windows::Compat::Inventory::SqliteInvCacheItem *__hidden); // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v17; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+80h] [rbp-88h] BYREF
  char *v19; // [rsp+88h] [rbp-80h] BYREF
  const unsigned __int16 *Version; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v21; // [rsp+98h] [rbp-70h] BYREF
  const char *v22; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v23[2]; // [rsp+A8h] [rbp-60h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+B8h] [rbp-50h] BYREF
  int v25; // [rsp+C4h] [rbp-44h]
  __int64 v26; // [rsp+C8h] [rbp-40h]
  char v27[64]; // [rsp+D8h] [rbp-30h] BYREF

  v23[1] = -2;
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  if ( Utility::IsAeInvAlreadyRunning(&v15) )
  {
    LastError = -2147024726;
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    return (unsigned int)LastError;
  }
  v5 = a3 && wcsstr(a3, L"invsvc");
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( v5 )
  {
    v6 = wcsstr(a3, L"-cv:");
    memset_0(v27, 0, sizeof(v27));
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v15,
      0);
    if ( v6 && (int)StringCchPrintfA(v27, 0x40u, "%ls", v6 + 4) >= 0 )
    {
      v7 = 0;
      if ( v27[0] )
      {
        while ( v27[v7] != 32 )
        {
          v7 = (unsigned int)(v7 + 1);
          if ( !v27[v7] )
            goto LABEL_13;
        }
        if ( (unsigned int)v7 >= 0x40uLL )
          _report_rangecheckfailure();
        v27[v7] = 0;
      }
LABEL_13:
      AslLogCallPrintf(3, (unsigned int)"UpdateSoftwareInventoryW", 1163, (unsigned int)"Found correlation vector: %hs");
      Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(v8, v27);
    }
    v16 = off_180131D70;
    SystemPowerStatus.BatteryFullLifeTime = 0;
    v26 = 983170;
    *(_QWORD *)&SystemPowerStatus.ACLineStatus = 24;
    v25 = 1;
    AppInventory = GetAppInventory(
                     (struct Windows::Compat::Inventory::IInventoryDataReceiver *)&v16,
                     (struct Windows::Compat::Inventory::InventoryControlParams *)&SystemPowerStatus,
                     (const char *)((unsigned __int64)v27 & -(__int64)(v27[0] != 0)));
    InventoryApplicationInstalled::SendEvent();
  }
  else
  {
    *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
    SystemPowerStatus.BatteryFullLifeTime = 0;
    if ( !GetSystemPowerStatus(&SystemPowerStatus) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"UpdateSoftwareInventoryW",
        1194,
        (unsigned int)"GetSystemPowerStatus failed [%d]");
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    if ( SystemPowerStatus.ACLineStatus != 1 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"UpdateSoftwareInventoryW",
        1199,
        (unsigned int)"Not running because the system is currently on battery.");
      LastError = 0;
      goto LABEL_22;
    }
    AppInventory = CreateSoftwareInventory(0x1003u, 0, 0);
  }
  v17 = 0;
  QueryUnbiasedInterruptTime(&v17);
  v11 = DWORD2(xmmword_180182350);
  if ( **((_DWORD **)&xmmword_180182350 + 1) > 5u
    && (unsigned __int8)tlgKeywordOn(*((_QWORD *)&xmmword_180182350 + 1), 0x400000000000LL) )
  {
    v19 = &byte_180182368;
    Version = InventoryCoreGetVersion();
    LODWORD(v16) = AppInventory;
    v21 = (v17 - UnbiasedTime) / 0x2710;
    v14 = "InvSvc";
    if ( !v5 )
      v14 = "PCA";
    v22 = v14;
    v23[0] = "AppInv";
    *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v11,
      (unsigned int)&word_180162406,
      v12,
      v13,
      (__int64)&SystemPowerStatus,
      (__int64)v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v16,
      (__int64)&Version,
      (__int64)&v19);
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"UpdateSoftwareInventoryW",
    1208,
    (unsigned int)"UpdateSoftwareInventoryW launched by %s elapsed time: %llu");
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  return AppInventory;
}

```

## disassembly

```asm
0x180066e80  mov     rax, rsp
0x180066e83  push    rbp
0x180066e84  push    rdi
0x180066e85  push    r14
0x180066e87  lea     rbp, [rax-38h]
0x180066e8b  sub     rsp, 120h
0x180066e92  mov     [rbp+30h+var_88], 0FFFFFFFFFFFFFFFEh
0x180066e9a  mov     [rax+8], rbx
0x180066e9e  mov     [rax+10h], rsi
0x180066ea2  mov     rax, cs:__security_cookie
0x180066ea9  xor     rax, rsp
0x180066eac  mov     [rbp+30h+var_20], rax
0x180066eb0  mov     rbx, r8
0x180066eb3  mov     [rsp+130h+var_D0], 0
0x180066ebc  xor     edx, edx
0x180066ebe  lea     rcx, [rsp+130h+var_D0]
0x180066ec3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180066ec8  lea     rcx, [rsp+130h+var_D0]; void **
0x180066ecd  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x180066ed2  test    al, al
0x180066ed4  jz      short loc_180066EE0
0x180066ed6  mov     ebx, 800700AAh
0x180066edb  jmp     loc_180067097
0x180066ee0  mov     esi, 1
0x180066ee5  test    rbx, rbx
0x180066ee8  jz      short loc_180066F03
0x180066eea  lea     rdx, aInvsvc_0; "invsvc"
0x180066ef1  mov     rcx, rbx; Str
0x180066ef4  call    cs:__imp_wcsstr
0x180066efa  test    rax, rax
0x180066efd  jz      short loc_180066F03
0x180066eff  mov     edi, esi
0x180066f01  jmp     short loc_180066F05
0x180066f03  xor     edi, edi
0x180066f05  mov     [rsp+130h+UnbiasedTime], 0
0x180066f0e  lea     rcx, [rsp+130h+UnbiasedTime]; UnbiasedTime
0x180066f13  call    cs:__imp_QueryUnbiasedInterruptTime
0x180066f19  test    edi, edi
0x180066f1b  jz      loc_180067024
0x180066f21  lea     rdx, aCv; "-cv:"
0x180066f28  mov     rcx, rbx; Str
0x180066f2b  call    cs:__imp_wcsstr
0x180066f31  mov     rbx, rax
0x180066f34  mov     r14d, 40h ; '@'
0x180066f3a  mov     r8d, r14d; Size
0x180066f3d  xor     edx, edx; Val
0x180066f3f  lea     rcx, [rbp+30h+var_60]; void *
0x180066f43  call    memset_0
0x180066f48  xor     edx, edx
0x180066f4a  lea     rcx, [rsp+130h+var_D0]
0x180066f4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180066f54  test    rbx, rbx
0x180066f57  jz      short loc_180066FC1
0x180066f59  lea     r9, [rbx+8]
0x180066f5d  lea     r8, aLs; "%ls"
0x180066f64  mov     edx, r14d; unsigned __int64
0x180066f67  lea     rcx, [rbp+30h+var_60]; char *
0x180066f6b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180066f70  test    eax, eax
0x180066f72  js      short loc_180066FC1
0x180066f74  xor     ecx, ecx
0x180066f76  cmp     [rbp+30h+var_60], cl
0x180066f79  jz      short loc_180066F91
0x180066f7b  mov     eax, ecx
0x180066f7d  cmp     [rbp+rcx+30h+var_60], 20h ; ' '
0x180066f82  jz      loc_180067011
0x180066f88  add     ecx, esi
0x180066f8a  cmp     [rbp+rcx+30h+var_60], 0
0x180066f8f  jnz     short loc_180066F7B
0x180066f91  lea     rax, [rbp+30h+var_60]
0x180066f95  mov     [rsp+130h+var_110], rax
0x180066f9a  lea     r9, aFoundCorrelati; "Found correlation vector: %hs"
0x180066fa1  mov     r8d, 48Bh
0x180066fa7  lea     rdx, aUpdatesoftware_2; "UpdateSoftwareInventoryW"
0x180066fae  mov     ecx, 3
0x180066fb3  call    AslLogCallPrintf
0x180066fb8  lea     rdx, [rbp+30h+var_60]; char *
0x180066fbc  call    ?ExtendCv@TelemetryProvider@Telemetry@Shared@Compat@Windows@@QEAAXPEBD@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(char const *)
0x180066fc1  lea     rax, off_180131D70
0x180066fc8  mov     [rsp+130h+var_C8], rax
0x180066fcd  mov     [rbp+30h+SystemPowerStatus.BatteryFullLifeTime], 0
0x180066fd4  mov     [rbp+30h+var_70], 0F0082h
0x180066fdc  mov     qword ptr [rbp+30h+SystemPowerStatus.ACLineStatus], 18h
0x180066fe4  mov     [rbp+30h+var_74], esi
0x180066fe7  mov     al, [rbp+30h+var_60]
0x180066fea  neg     al
0x180066fec  sbb     r8, r8
0x180066fef  lea     rax, [rbp+30h+var_60]
0x180066ff3  and     r8, rax; char *
0x180066ff6  lea     rdx, [rbp+30h+SystemPowerStatus]; struct Windows::Compat::Inventory::InventoryControlParams *
0x180066ffa  lea     rcx, [rsp+130h+var_C8]; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180066fff  call    ?GetAppInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@PEBD@Z; GetAppInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)
0x180067004  mov     r14d, eax
0x180067007  call    ?SendEvent@InventoryApplicationInstalled@@SAXXZ; InventoryApplicationInstalled::SendEvent(void)
0x18006700c  jmp     loc_1800670BA
0x180067011  cmp     rax, r14
0x180067014  jnb     loc_180067231
0x18006701a  mov     [rbp+rcx+30h+var_60], 0
0x18006701f  jmp     loc_180066F91
0x180067024  xor     eax, eax
0x180067026  mov     qword ptr [rbp+30h+SystemPowerStatus.ACLineStatus], rax
0x18006702a  mov     [rbp+30h+SystemPowerStatus.BatteryFullLifeTime], eax
0x18006702d  lea     rcx, [rbp+30h+SystemPowerStatus]; lpSystemPowerStatus
0x180067031  call    cs:__imp_GetSystemPowerStatus
0x180067037  test    eax, eax
0x180067039  jnz     short loc_180067071
0x18006703b  call    cs:__imp_GetLastError
0x180067041  mov     ebx, eax
0x180067043  mov     dword ptr [rsp+130h+var_110], eax
0x180067047  lea     r9, aGetsystempower; "GetSystemPowerStatus failed [%d]"
0x18006704e  mov     r8d, 4AAh
0x180067054  lea     rdx, aUpdatesoftware_2; "UpdateSoftwareInventoryW"
0x18006705b  mov     ecx, esi
0x18006705d  call    AslLogCallPrintf
0x180067062  test    ebx, ebx
0x180067064  jle     short loc_180067097
0x180067066  movzx   ebx, bx
0x180067069  or      ebx, 80070000h
0x18006706f  jmp     short loc_180067097
0x180067071  cmp     [rbp+30h+SystemPowerStatus.ACLineStatus], sil
0x180067075  jz      short loc_1800670A8
0x180067077  lea     r9, aNotRunningBeca; "Not running because the system is curre"...
0x18006707e  mov     r8d, 4AFh
0x180067084  lea     rdx, aUpdatesoftware_2; "UpdateSoftwareInventoryW"
0x18006708b  mov     ecx, 3
0x180067090  call    AslLogCallPrintf
0x180067095  xor     ebx, ebx
0x180067097  lea     rcx, [rsp+130h+var_D0]
0x18006709c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800670a1  mov     eax, ebx
0x1800670a3  jmp     loc_18006720D
0x1800670a8  xor     r8d, r8d; unsigned __int16 **
0x1800670ab  xor     edx, edx; unsigned __int16 **
0x1800670ad  mov     ecx, 1003h; unsigned int
0x1800670b2  call    ?CreateSoftwareInventory@@YAJKPEAPEAG0@Z; CreateSoftwareInventory(ulong,ushort * *,ushort * *)
0x1800670b7  mov     r14d, eax
0x1800670ba  mov     [rsp+130h+var_C0], 0
0x1800670c3  lea     rcx, [rsp+130h+var_C0]; UnbiasedTime
0x1800670c8  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800670ce  mov     rbx, qword ptr cs:xmmword_180182350+8
0x1800670d5  mov     eax, [rbx]
0x1800670d7  lea     rsi, aInvsvc; "InvSvc"
0x1800670de  cmp     eax, 5
0x1800670e1  jbe     loc_1800671AF
0x1800670e7  mov     rdx, 400000000000h
0x1800670f1  mov     rcx, rbx
0x1800670f4  call    _tlgKeywordOn
0x1800670f9  test    al, al
0x1800670fb  jz      loc_1800671AF
0x180067101  lea     rax, byte_180182368
0x180067108  mov     [rbp+30h+var_B0], rax
0x18006710c  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180067111  mov     [rbp+30h+var_A8], rax
0x180067115  mov     dword ptr [rsp+130h+var_C8], r14d
0x18006711a  mov     rcx, [rsp+130h+var_C0]
0x18006711f  sub     rcx, [rsp+130h+UnbiasedTime]
0x180067124  mov     rax, 346DC5D63886594Bh
0x18006712e  mul     rcx
0x180067131  shr     rdx, 0Bh
0x180067135  mov     [rbp+30h+var_A0], rdx
0x180067139  mov     rax, rsi
0x18006713c  test    edi, edi
0x18006713e  lea     rcx, aPca; "PCA"
0x180067145  cmovz   rax, rcx
0x180067149  mov     [rbp+30h+var_98], rax
0x18006714d  lea     rax, aAppinv; "AppInv"
0x180067154  mov     [rbp+30h+var_90], rax
0x180067158  mov     qword ptr [rbp+30h+SystemPowerStatus.ACLineStatus], 1000000h
0x180067160  lea     rax, [rbp+30h+var_B0]
0x180067164  mov     [rsp+130h+var_E0], rax
0x180067169  lea     rax, [rbp+30h+var_A8]
0x18006716d  mov     [rsp+130h+var_E8], rax
0x180067172  lea     rax, [rsp+130h+var_C8]
0x180067177  mov     [rsp+130h+var_F0], rax
0x18006717c  lea     rcx, [rbp+30h+var_A0]
0x180067180  mov     [rsp+130h+var_F8], rcx
0x180067185  lea     rcx, [rbp+30h+var_98]
0x180067189  mov     [rsp+130h+var_100], rcx
0x18006718e  lea     rcx, [rbp+30h+var_90]
0x180067192  mov     [rsp+130h+var_108], rcx
0x180067197  lea     rcx, [rbp+30h+SystemPowerStatus]
0x18006719b  mov     [rsp+130h+var_110], rcx
0x1800671a0  lea     rdx, word_180162406
0x1800671a7  mov     rcx, rbx
0x1800671aa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x1800671af  mov     rcx, [rsp+130h+var_C0]
0x1800671b4  sub     rcx, [rsp+130h+UnbiasedTime]
0x1800671b9  mov     rax, 346DC5D63886594Bh
0x1800671c3  mul     rcx
0x1800671c6  shr     rdx, 0Bh
0x1800671ca  test    edi, edi
0x1800671cc  lea     rax, aPca; "PCA"
0x1800671d3  cmovz   rsi, rax
0x1800671d7  mov     [rsp+130h+var_108], rdx
0x1800671dc  mov     [rsp+130h+var_110], rsi
0x1800671e1  lea     r9, aUpdatesoftware_1; "UpdateSoftwareInventoryW launched by %s"...
0x1800671e8  mov     r8d, 4B8h
0x1800671ee  lea     rdx, aUpdatesoftware_2; "UpdateSoftwareInventoryW"
0x1800671f5  mov     ecx, 3
0x1800671fa  call    AslLogCallPrintf
0x1800671ff  nop
0x180067200  lea     rcx, [rsp+130h+var_D0]
0x180067205  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006720a  mov     eax, r14d
0x18006720d  mov     rcx, [rbp+30h+var_20]
0x180067211  xor     rcx, rsp; StackCookie
0x180067214  call    __security_check_cookie
0x180067219  lea     r11, [rsp+130h+var_10]
0x180067221  mov     rbx, [r11+20h]
0x180067225  mov     rsi, [r11+28h]
0x180067229  mov     rsp, r11
0x18006722c  pop     r14
0x18006722e  pop     rdi
0x18006722f  pop     rbp
0x180067230  retn
0x180067231  call    __report_rangecheckfailure
```
