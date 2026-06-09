# HydrateAllEnrollments(ushort const *)

- ea: `0x180004168`
- end: `0x180004706`
- name: `?HydrateAllEnrollments@@YAJPEBG@Z`
- size: `1438`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180003480`

## callees

- `0x180001c60`
- `0x18000383c`
- `0x180003874`
- `0x1800038c0`
- `0x1800038ec`
- `0x180003990`
- `0x180004168`
- `0x18000470c`
- `0x180004df4`
- `0x18000533c`
- `0x180005bfc`
- `0x180005fbc`
- `0x1800060d8`
- `0x180006340`
- `0x18000649c`
- `0x18000fc24`
- `0x180010340`
- `0x180010804`
- `0x180012b80`
- `0x180017ce4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000444c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000444c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000442c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000442c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000439a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000439a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004226`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004321`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004496`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800044e1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000453a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004628`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004680`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800046be`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004226`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004321`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004496`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800044e1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000453a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004628`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180004680`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800046be`

## string_xrefs

- `0x18000441e`: `Global\SC_AutoStartComplete`
- `0x18000436d`: `get_SID 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HydrateAllEnrollments(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rbx
  int IsSystemOrAdmin; // eax
  __int64 v3; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  int v11; // ebx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // r12
  __int64 (__fastcall *v16)(__int64 *, BSTR *); // r13
  OLECHAR *v17; // rbx
  int v18; // eax
  unsigned int v19; // r12d
  int v20; // eax
  char *v21; // rax
  __int64 v22; // r8
  int RenewPeriodInSeconds; // eax
  struct _FILETIME v24; // rbx
  unsigned int v25; // r13d
  unsigned int v26; // ecx
  unsigned __int16 *v27; // rax
  unsigned int Data; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-55h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v33; // [rsp+60h] [rbp-39h] BYREF
  struct _CRYPTOAPI_BLOB v34; // [rsp+68h] [rbp-31h] BYREF
  const unsigned __int16 *v35; // [rsp+78h] [rbp-21h]
  WINBOOL IsMember; // [rsp+80h] [rbp-19h] BYREF
  __int64 v37; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v38[8]; // [rsp+90h] [rbp-9h] BYREF
  __int128 v39; // [rsp+98h] [rbp-1h] BYREF

  v1 = a1;
  v35 = a1;
  IsMember = 1;
  WdsSetupLogMessageW(0x4000000u, L"HydrateAllEnrollments");
  IsSystemOrAdmin = DmIsSystemOrAdmin(&IsMember);
  Data = IsSystemOrAdmin;
  if ( IsSystemOrAdmin >= 0 )
  {
    v37 = 0;
    v33 = 0;
    v39 = 0;
    Data = GetEnrollmentsOfTypes(v3, &v37);
    if ( (Data & 0x80000000) == 0 )
    {
      while ( 1 )
      {
        Data = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v37 + 24LL))(v37, &v33);
        if ( Data )
          break;
        v6 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v33 + 24))(v33, &v39);
        Data = v6;
        if ( v6 >= 0 )
        {
          v34 = 0;
          v7 = LoadFile(v1, &v34);
          v11 = v7;
          if ( v7 >= 0 )
          {
            v12 = ImportCert(&v34, v8, v9, v10);
            v11 = v12;
            if ( v12 < 0 )
              WdsSetupLogMessageW(0x2000000u, L"ImportCert client 0x%x", (unsigned int)v12);
          }
          else
          {
            WdsSetupLogMessageW(0x2000000u, L"LoadFile 0x%x", (unsigned int)v7);
          }
          SafeHeapFree(v34.pbData);
          Data = v11;
          if ( v11 < 0 )
          {
            RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", L"3RestoreCerts", 4u, &Data, 4u);
            WdsSetupLogMessageW(0x2000000u, L"RestoreCerts 0x%x", Data);
          }
          v31 = 0;
          bstrString = 0;
          v32 = 0;
          v13 = *v33;
          v31 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **))(v13 + 112))(v33, &v31);
          Data = v14;
          if ( v14 >= 0 )
          {
            v15 = v33;
            v16 = *(__int64 (__fastcall **)(__int64 *, BSTR *))(*v33 + 32);
            v17 = bstrString;
            if ( bstrString )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v38);
              SysFreeString(v17);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v38);
            }
            bstrString = 0;
            v18 = v16(v15, &bstrString);
            Data = v18;
            v19 = 0;
            if ( v18 >= 0 )
            {
              WdsSetupLogMessageW(0x4000000u, L"Found Enrollment:%s", bstrString);
              v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v33 + 48))(v33, &v32);
              Data = v20;
              if ( v20 >= 0 )
              {
                v21 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
                *(_QWORD *)&v34.cbData = v21;
                if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  WaitForSingleObject(v21, 0xFFFFFFFF);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
                Data = SyncPollingOptions(bstrString, v31, v22, v32);
                if ( (Data & 0x80000000) != 0 )
                {
                  RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Enrollments",
                    L"4SyncPollingOptions",
                    4u,
                    &Data,
                    4u);
                  WdsSetupLogMessageW(0x2000000u, L"SyncPollingOptions 0x%x", Data);
                }
                RenewPeriodInSeconds = SyncPollingOptionsForMultipleSession(bstrString);
                Data = RenewPeriodInSeconds;
                if ( RenewPeriodInSeconds < 0 )
                {
                  RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Enrollments",
                    L"4SyncPollingOptionsForMultipleSession",
                    4u,
                    &Data,
                    4u);
                  WdsSetupLogMessageW(0x2000000u, L"SyncPollingOptionsForMultipleSession 0x%x", Data);
                  RenewPeriodInSeconds = Data;
                }
                v24 = 0;
                *(_QWORD *)&v34.cbData = 0;
                if ( RenewPeriodInSeconds >= 0 )
                {
                  Data = GetDeviceCertExpiryTime(bstrString, (struct _FILETIME *)&v34);
                  RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Enrollments",
                    L"5GetDeviceCertExpiryTime",
                    4u,
                    &Data,
                    4u);
                  WdsSetupLogMessageW(0x2000000u, L"GetDeviceCertExpiryTime 0x%x", Data);
                  RenewPeriodInSeconds = Data;
                  v24 = *(struct _FILETIME *)&v34.cbData;
                }
                v25 = 0;
                v29 = 0;
                if ( RenewPeriodInSeconds >= 0 )
                {
                  RenewPeriodInSeconds = GetRenewPeriodInSeconds(bstrString, &v29);
                  Data = RenewPeriodInSeconds;
                  v25 = v29;
                }
                v34.cbData = 0;
                if ( RenewPeriodInSeconds >= 0 )
                {
                  RenewPeriodInSeconds = GetRenewRetryIntervalInSeconds(bstrString, 1, &v34.cbData);
                  Data = RenewPeriodInSeconds;
                }
                v29 = 0;
                if ( RenewPeriodInSeconds >= 0 )
                {
                  RenewPeriodInSeconds = GetRenewRetryIntervalInSeconds(bstrString, 0, &v29);
                  Data = RenewPeriodInSeconds;
                  v19 = v29;
                }
                v26 = 0;
                v29 = 0;
                if ( RenewPeriodInSeconds >= 0 )
                {
                  Data = IsROBOMode(bstrString, (int *)&v29);
                  v26 = v29;
                }
                v27 = 0;
                if ( v32 == 5 )
                  v27 = v31;
                Data = SetupAllEnrollmentSchedules(bstrString, v24, v25, v34.cbData, v19, v26, v27);
                if ( (Data & 0x80000000) != 0 )
                {
                  RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Enrollments",
                    L"6SetupAllEnrollmentSchedules",
                    4u,
                    &Data,
                    4u);
                  WdsSetupLogMessageW(0x2000000u, L"SetupAllEnrollmentSchedules 0x%x", Data);
                }
              }
              else
              {
                WdsSetupLogMessageW(0x2000000u, L"get_EnrollmentType 0x%x", (unsigned int)v20);
              }
            }
            else
            {
              WdsSetupLogMessageW(0x2000000u, L"get_KeyAsString 0x%x", (unsigned int)v18);
            }
          }
          else
          {
            WdsSetupLogMessageW(0x2000000u, L"get_SID 0x%x", (unsigned int)v14);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
          v1 = v35;
        }
        else
        {
          WdsSetupLogMessageW(0x3000000u, L"get_Key 0x%x", (unsigned int)v6);
        }
      }
      RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", L"2get_Next", 4u, &Data, 4u);
      WdsSetupLogMessageW(0x4000000u, L"get_Next 0x%x", Data);
      RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", L"7Done", 4u, &Data, 4u);
      v5 = 0;
      Data = 0;
    }
    else
    {
      RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", L"1GetEnrollmentsOfTypes", 4u, &Data, 4u);
      WdsSetupLogMessageW(0x2000000u, L"GetEnrollmentsOfTypes 0x%x", Data);
      v5 = Data;
    }
    ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(&v33);
    ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(&v37);
    return v5;
  }
  else
  {
    WdsSetupLogMessageW(0x2000000u, L"DmIsSystemOrAdmin 0x%x", (unsigned int)IsSystemOrAdmin);
    return Data;
  }
}

```

## disassembly

```asm
0x180004168  push    rbp
0x18000416a  push    rbx
0x18000416b  push    rsi
0x18000416c  push    rdi
0x18000416d  push    r12
0x18000416f  push    r13
0x180004171  push    r14
0x180004173  push    r15
0x180004175  lea     rbp, [rsp-1Fh]
0x18000417a  sub     rsp, 0B8h
0x180004181  mov     rax, cs:__security_cookie
0x180004188  xor     rax, rsp
0x18000418b  mov     [rbp+57h+var_48], rax
0x18000418f  mov     rbx, rcx
0x180004192  mov     [rbp+57h+var_78], rcx
0x180004196  mov     [rbp+57h+IsMember], 1
0x18000419d  lea     rdx, aHydrateallenro; "HydrateAllEnrollments"
0x1800041a4  mov     ecx, 4000000h; unsigned int
0x1800041a9  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800041ae  lea     rcx, [rbp+57h+IsMember]; IsMember
0x1800041b2  call    ?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x1800041b7  mov     [rbp+57h+Data], eax
0x1800041ba  xor     r12d, r12d
0x1800041bd  test    eax, eax
0x1800041bf  jns     short loc_1800041DD
0x1800041c1  mov     r8d, eax
0x1800041c4  lea     rdx, aDmissystemorad_0; "DmIsSystemOrAdmin 0x%x"
0x1800041cb  mov     ecx, 2000000h; unsigned int
0x1800041d0  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800041d5  mov     eax, [rbp+57h+Data]
0x1800041d8  jmp     loc_1800046E5
0x1800041dd  mov     [rbp+57h+var_68], r12
0x1800041e1  mov     [rbp+57h+var_90], r12
0x1800041e5  xorps   xmm0, xmm0
0x1800041e8  movups  [rbp+57h+var_58], xmm0
0x1800041ec  lea     rdx, [rbp+57h+var_68]
0x1800041f0  call    GetEnrollmentsOfTypes
0x1800041f5  mov     [rbp+57h+Data], eax
0x1800041f8  mov     esi, 4
0x1800041fd  test    eax, eax
0x1800041ff  jns     short loc_18000424F
0x180004201  mov     [rsp+0F0h+cbData], esi; cbData
0x180004205  lea     rax, [rbp+57h+Data]
0x180004209  mov     [rsp+0F0h+lpData], rax; lpData
0x18000420e  mov     r9d, esi; dwType
0x180004211  lea     r8, ValueName; "1GetEnrollmentsOfTypes"
0x180004218  lea     rdx, SubKey; "Software\\Microsoft\\Enrollments"
0x18000421f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004226  call    cs:__imp_RegSetKeyValueW
0x18000422d  nop     dword ptr [rax+rax+00h]
0x180004232  mov     r8d, [rbp+57h+Data]
0x180004236  lea     rdx, aGetenrollments; "GetEnrollmentsOfTypes 0x%x"
0x18000423d  mov     ecx, 2000000h; unsigned int
0x180004242  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x180004247  mov     ebx, [rbp+57h+Data]
0x18000424a  jmp     loc_1800046D0
0x18000424f  mov     edi, 2000000h
0x180004254  lea     r14, SubKey; "Software\\Microsoft\\Enrollments"
0x18000425b  mov     r15, 0FFFFFFFF80000002h
0x180004262  mov     rcx, [rbp+57h+var_68]
0x180004266  mov     rax, [rcx]
0x180004269  lea     rdx, [rbp+57h+var_90]
0x18000426d  mov     rax, [rax+18h]
0x180004271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004276  mov     [rbp+57h+Data], eax
0x180004279  test    eax, eax
0x18000427b  jnz     loc_180004663
0x180004281  mov     rcx, [rbp+57h+var_90]
0x180004285  mov     rax, [rcx]
0x180004288  lea     rdx, [rbp+57h+var_58]
0x18000428c  mov     rax, [rax+18h]
0x180004290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004295  mov     [rbp+57h+Data], eax
0x180004298  test    eax, eax
0x18000429a  jns     short loc_1800042B2
0x18000429c  mov     r8d, eax
0x18000429f  lea     rdx, aGetKey0xX; "get_Key 0x%x"
0x1800042a6  mov     ecx, 3000000h; unsigned int
0x1800042ab  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800042b0  jmp     short loc_180004262
0x1800042b2  xorps   xmm0, xmm0
0x1800042b5  movups  xmmword ptr [rbp+57h+var_88.cbData], xmm0
0x1800042b9  lea     rdx, [rbp+57h+var_88]; struct _CRYPTOAPI_BLOB *
0x1800042bd  mov     rcx, rbx; unsigned __int16 *
0x1800042c0  call    ?LoadFile@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; LoadFile(ushort const *,_CRYPTOAPI_BLOB *)
0x1800042c5  mov     ebx, eax
0x1800042c7  test    eax, eax
0x1800042c9  jns     short loc_1800042D4
0x1800042cb  lea     rdx, aLoadfile0xX; "LoadFile 0x%x"
0x1800042d2  jmp     short loc_1800042EA
0x1800042d4  lea     rcx, [rbp+57h+var_88]; struct _CRYPTOAPI_BLOB *
0x1800042d8  call    ?ImportCert@@YAJPEAU_CRYPTOAPI_BLOB@@PEBGK1@Z; ImportCert(_CRYPTOAPI_BLOB *,ushort const *,ulong,ushort const *)
0x1800042dd  mov     ebx, eax
0x1800042df  test    eax, eax
0x1800042e1  jns     short loc_1800042F4
0x1800042e3  lea     rdx, aImportcertClie; "ImportCert client 0x%x"
0x1800042ea  mov     r8d, eax
0x1800042ed  mov     ecx, edi; unsigned int
0x1800042ef  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800042f4  mov     rcx, [rbp+57h+var_88.pbData]; void *
0x1800042f8  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x1800042fd  mov     [rbp+57h+Data], ebx
0x180004300  test    ebx, ebx
0x180004302  jns     short loc_18000433F
0x180004304  mov     [rsp+0F0h+cbData], esi; cbData
0x180004308  lea     rax, [rbp+57h+Data]
0x18000430c  mov     [rsp+0F0h+lpData], rax; lpData
0x180004311  mov     r9d, esi; dwType
0x180004314  lea     r8, a3restorecerts; "3RestoreCerts"
0x18000431b  mov     rdx, r14; lpSubKey
0x18000431e  mov     rcx, r15; hKey
0x180004321  call    cs:__imp_RegSetKeyValueW
0x180004328  nop     dword ptr [rax+rax+00h]
0x18000432d  mov     r8d, [rbp+57h+Data]
0x180004331  lea     rdx, aRestorecerts0x; "RestoreCerts 0x%x"
0x180004338  mov     ecx, edi; unsigned int
0x18000433a  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x18000433f  mov     [rbp+57h+var_A0], r12
0x180004343  mov     [rbp+57h+bstrString], r12
0x180004347  mov     [rbp+57h+var_98], r12d
0x18000434b  mov     rcx, [rbp+57h+var_90]
0x18000434f  mov     rax, [rcx]
0x180004352  mov     [rbp+57h+var_A0], r12
0x180004356  lea     rdx, [rbp+57h+var_A0]
0x18000435a  mov     rax, [rax+70h]
0x18000435e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004363  mov     [rbp+57h+Data], eax
0x180004366  test    eax, eax
0x180004368  jns     short loc_180004379
0x18000436a  mov     r8d, eax
0x18000436d  lea     rdx, aGetSid0xX; "get_SID 0x%x"
0x180004374  jmp     loc_18000463F
0x180004379  mov     r12, [rbp+57h+var_90]
0x18000437d  mov     rax, [r12]
0x180004381  mov     r13, [rax+20h]
0x180004385  mov     rbx, [rbp+57h+bstrString]
0x180004389  test    rbx, rbx
0x18000438c  jz      short loc_1800043AF
0x18000438e  lea     rcx, [rbp+57h+var_60]; this
0x180004392  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004397  mov     rcx, rbx; bstrString
0x18000439a  call    cs:__imp_SysFreeString
0x1800043a1  nop     dword ptr [rax+rax+00h]
0x1800043a6  lea     rcx, [rbp+57h+var_60]; this
0x1800043aa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800043af  mov     [rbp+57h+bstrString], 0
0x1800043b7  lea     rdx, [rbp+57h+bstrString]
0x1800043bb  mov     rcx, r12
0x1800043be  mov     rax, r13
0x1800043c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c6  mov     [rbp+57h+Data], eax
0x1800043c9  xor     r12d, r12d
0x1800043cc  test    eax, eax
0x1800043ce  jns     short loc_1800043DF
0x1800043d0  mov     r8d, eax
0x1800043d3  lea     rdx, aGetKeyasstring; "get_KeyAsString 0x%x"
0x1800043da  jmp     loc_18000463F
0x1800043df  mov     r8, [rbp+57h+bstrString]
0x1800043e3  lea     rdx, aFoundEnrollmen; "Found Enrollment:%s"
0x1800043ea  mov     ecx, 4000000h; unsigned int
0x1800043ef  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800043f4  mov     rcx, [rbp+57h+var_90]
0x1800043f8  mov     rax, [rcx]
0x1800043fb  lea     rdx, [rbp+57h+var_98]
0x1800043ff  mov     rax, [rax+30h]
0x180004403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004408  mov     [rbp+57h+Data], eax
0x18000440b  test    eax, eax
0x18000440d  jns     short loc_18000441E
0x18000440f  mov     r8d, eax
0x180004412  lea     rdx, aGetEnrollmentt; "get_EnrollmentType 0x%x"
0x180004419  jmp     loc_18000463F
0x18000441e  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x180004425  xor     edx, edx; bInheritHandle
0x180004427  mov     ecx, 100000h; dwDesiredAccess
0x18000442c  call    cs:__imp_OpenEventW
0x180004433  nop     dword ptr [rax+rax+00h]
0x180004438  mov     qword ptr [rbp+57h+var_88.cbData], rax
0x18000443c  lea     rcx, [rax-1]
0x180004440  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180004444  ja      short loc_180004458
0x180004446  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004449  mov     rcx, rax; hHandle
0x18000444c  call    cs:__imp_WaitForSingleObject
0x180004453  nop     dword ptr [rax+rax+00h]
0x180004458  lea     rcx, [rbp+57h+var_88]
0x18000445c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004461  mov     r9d, [rbp+57h+var_98]
0x180004465  mov     rdx, [rbp+57h+var_A0]
0x180004469  mov     rcx, [rbp+57h+bstrString]
0x18000446d  call    ?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z; SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)
0x180004472  mov     [rbp+57h+Data], eax
0x180004475  test    eax, eax
0x180004477  jns     short loc_1800044B4
0x180004479  mov     [rsp+0F0h+cbData], esi; cbData
0x18000447d  lea     rax, [rbp+57h+Data]
0x180004481  mov     [rsp+0F0h+lpData], rax; lpData
0x180004486  mov     r9d, esi; dwType
0x180004489  lea     r8, a4syncpollingop; "4SyncPollingOptions"
0x180004490  mov     rdx, r14; lpSubKey
0x180004493  mov     rcx, r15; hKey
0x180004496  call    cs:__imp_RegSetKeyValueW
0x18000449d  nop     dword ptr [rax+rax+00h]
0x1800044a2  mov     r8d, [rbp+57h+Data]
0x1800044a6  lea     rdx, aSyncpollingopt; "SyncPollingOptions 0x%x"
0x1800044ad  mov     ecx, edi; unsigned int
0x1800044af  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800044b4  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800044b8  call    ?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z; SyncPollingOptionsForMultipleSession(ushort const *)
0x1800044bd  mov     [rbp+57h+Data], eax
0x1800044c0  test    eax, eax
0x1800044c2  jns     short loc_180004502
0x1800044c4  mov     [rsp+0F0h+cbData], esi; cbData
0x1800044c8  lea     rax, [rbp+57h+Data]
0x1800044cc  mov     [rsp+0F0h+lpData], rax; lpData
0x1800044d1  mov     r9d, esi; dwType
0x1800044d4  lea     r8, a4syncpollingop_0; "4SyncPollingOptionsForMultipleSession"
0x1800044db  mov     rdx, r14; lpSubKey
0x1800044de  mov     rcx, r15; hKey
0x1800044e1  call    cs:__imp_RegSetKeyValueW
0x1800044e8  nop     dword ptr [rax+rax+00h]
0x1800044ed  mov     r8d, [rbp+57h+Data]
0x1800044f1  lea     rdx, aSyncpollingopt_1; "SyncPollingOptionsForMultipleSession 0x"...
0x1800044f8  mov     ecx, edi; unsigned int
0x1800044fa  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x1800044ff  mov     eax, [rbp+57h+Data]
0x180004502  mov     rbx, r12
0x180004505  mov     qword ptr [rbp+57h+var_88.cbData], rbx
0x180004509  test    eax, eax
0x18000450b  js      short loc_18000455F
0x18000450d  lea     rdx, [rbp+57h+var_88]; struct _FILETIME *
0x180004511  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180004515  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x18000451a  mov     [rbp+57h+Data], eax
0x18000451d  mov     [rsp+0F0h+cbData], esi; cbData
0x180004521  lea     rax, [rbp+57h+Data]
0x180004525  mov     [rsp+0F0h+lpData], rax; lpData
0x18000452a  mov     r9d, esi; dwType
0x18000452d  lea     r8, a5getdevicecert; "5GetDeviceCertExpiryTime"
0x180004534  mov     rdx, r14; lpSubKey
0x180004537  mov     rcx, r15; hKey
0x18000453a  call    cs:__imp_RegSetKeyValueW
0x180004541  nop     dword ptr [rax+rax+00h]
0x180004546  mov     r8d, [rbp+57h+Data]
0x18000454a  lea     rdx, aGetdevicecerte; "GetDeviceCertExpiryTime 0x%x"
0x180004551  mov     ecx, edi; unsigned int
0x180004553  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x180004558  mov     eax, [rbp+57h+Data]
0x18000455b  mov     rbx, qword ptr [rbp+57h+var_88.cbData]
0x18000455f  mov     r13d, r12d
0x180004562  mov     [rbp+57h+var_AC], r12d
0x180004566  test    eax, eax
0x180004568  js      short loc_18000457E
0x18000456a  lea     rdx, [rbp+57h+var_AC]; unsigned int *
0x18000456e  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180004572  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x180004577  mov     [rbp+57h+Data], eax
0x18000457a  mov     r13d, [rbp+57h+var_AC]
0x18000457e  mov     [rbp+57h+var_88.cbData], r12d
0x180004582  test    eax, eax
0x180004584  js      short loc_18000459B
0x180004586  lea     r8, [rbp+57h+var_88]; unsigned int *
0x18000458a  mov     edx, 1; int
0x18000458f  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180004593  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180004598  mov     [rbp+57h+Data], eax
0x18000459b  mov     [rbp+57h+var_AC], r12d
0x18000459f  test    eax, eax
0x1800045a1  js      short loc_1800045B9
0x1800045a3  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x1800045a7  xor     edx, edx; int
0x1800045a9  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800045ad  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x1800045b2  mov     [rbp+57h+Data], eax
0x1800045b5  mov     r12d, [rbp+57h+var_AC]
0x1800045b9  xor     ecx, ecx
0x1800045bb  mov     [rbp+57h+var_AC], ecx
0x1800045be  test    eax, eax
0x1800045c0  js      short loc_1800045D5
0x1800045c2  lea     rdx, [rbp+57h+var_AC]; int *
0x1800045c6  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800045ca  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x1800045cf  mov     [rbp+57h+Data], eax
0x1800045d2  mov     ecx, [rbp+57h+var_AC]
0x1800045d5  xor     eax, eax
0x1800045d7  cmp     [rbp+57h+var_98], 5
0x1800045db  cmovz   rax, [rbp+57h+var_A0]
0x1800045e0  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x1800045e5  mov     [rsp+0F0h+cbData], ecx; int
0x1800045e9  mov     dword ptr [rsp+0F0h+lpData], r12d; unsigned int
0x1800045ee  mov     r9d, [rbp+57h+var_88.cbData]; unsigned int
0x1800045f2  mov     r8d, r13d; unsigned int
0x1800045f5  mov     rdx, rbx; struct _FILETIME
0x1800045f8  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800045fc  call    ?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z; SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180004601  mov     [rbp+57h+Data], eax
0x180004604  xor     r12d, r12d
0x180004607  test    eax, eax
0x180004609  jns     short loc_180004647
0x18000460b  mov     [rsp+0F0h+cbData], esi; cbData
  ... truncated ...
```
