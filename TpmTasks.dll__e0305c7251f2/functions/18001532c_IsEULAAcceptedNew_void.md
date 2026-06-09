# IsEULAAcceptedNew(void)

- ea: `0x18001532c`
- end: `0x180015498`
- name: `?IsEULAAcceptedNew@@YA_NXZ`
- size: `364`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x180009f44`
- `0x180009fcc`
- `0x18000a054`
- `0x18000a0dc`
- `0x18000a164`
- `0x18000d170`
- `0x18000e430`
- `0x18001532c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001542f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001542f`
- `SHLWAPI!PathFileExistsW` at `0x18001546e`
- `SHLWAPI!PathFileExistsW` at `0x18001546e`
- `WINBRAND!GetInstalledEULAPath` at `0x18001545d`
- `WINBRAND!GetInstalledEULAPath` at `0x18001545d`

## pseudocode

```c
char IsEULAAcceptedNew(void)
{
  int v0; // edi
  char v1; // bl
  __int64 v2; // rdx
  __int64 v3; // rdx
  LSTATUS ValueW; // eax
  __int64 v5; // rdx
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp-8h] BYREF
  LSTATUS v9; // [rsp+70h] [rbp+20h] BYREF
  int pvData; // [rsp+78h] [rbp+28h] BYREF
  int InstalledEULAPath; // [rsp+80h] [rbp+30h] BYREF
  char v12; // [rsp+88h] [rbp+38h] BYREF

  pvData = 0;
  LOBYTE(v9) = 0;
  InstalledEULAPath = wil::wnf_query_nothrow<unsigned long>(&WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED, &v9, &pvData, &v12);
  v0 = InstalledEULAPath;
  v1 = 1;
  if ( InstalledEULAPath < 0 )
  {
    ProvisionTelemetryProvider::EULACheckWnfFailure<long &,unsigned short const (&)[35]>(&InstalledEULAPath);
  }
  else if ( (_BYTE)v9 && pvData == 1 )
  {
    return v1;
  }
  if ( (int)wil::wnf_query_nothrow<unsigned long>(&WNF_SHEL_OOBE_USER_LOGON_COMPLETE, &v9, &pvData, &v12) < 0
    || !(_BYTE)v9
    || pvData != 1 )
  {
    if ( v0 < 0 )
      ProvisionTelemetryProvider::EULACheckWnfFailure<long &,unsigned short const (&)[34]>(&InstalledEULAPath, v2);
    if ( (int)wil::wnf_query_nothrow<unsigned long>(&WNF_CSHL_PRODUCT_READY, &v9, &pvData, &v12) < 0
      || !(_BYTE)v9
      || pvData != 1 )
    {
      if ( v0 < 0 )
        ProvisionTelemetryProvider::EULACheckWnfFailure<long &,unsigned short const (&)[23]>(&InstalledEULAPath, v3);
      pcbData = 4;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
                 L"SetupDisplayedEula",
                 0x10u,
                 0,
                 &pvData,
                 &pcbData);
      v9 = ValueW;
      if ( ValueW )
      {
        if ( ValueW != 2 )
          ProvisionTelemetryProvider::EULACheckRegistryFailure<long &,unsigned short const (&)[19]>(&v9, v5);
      }
      else if ( pvData == 1 )
      {
        return v1;
      }
      pszPath = 0;
      InstalledEULAPath = GetInstalledEULAPath(&pszPath);
      if ( InstalledEULAPath < 0 )
      {
        ProvisionTelemetryProvider::GetInstalledEULAPathFailure<long &>(&InstalledEULAPath);
      }
      else if ( PathFileExistsW(pszPath) )
      {
        goto LABEL_26;
      }
      v1 = 0;
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void EulaFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void EulaFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001532c  push    rbp
0x18001532e  push    rbx
0x18001532f  push    rdi
0x180015330  mov     rbp, rsp
0x180015333  sub     rsp, 50h
0x180015337  lea     r9, [rbp+arg_18]
0x18001533b  mov     [rbp+arg_8], 0
0x180015342  lea     r8, [rbp+arg_8]
0x180015346  mov     byte ptr [rbp+arg_0], 0
0x18001534a  lea     rdx, [rbp+arg_0]
0x18001534e  lea     rcx, WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED
0x180015355  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18001535a  mov     [rbp+arg_10], eax
0x18001535d  mov     edi, eax
0x18001535f  mov     ebx, 1
0x180015364  test    eax, eax
0x180015366  js      short loc_180015379
0x180015368  cmp     byte ptr [rbp+arg_0], 0
0x18001536c  jz      short loc_180015382
0x18001536e  cmp     [rbp+arg_8], ebx
0x180015371  jz      loc_18001548E
0x180015377  jmp     short loc_180015382
0x180015379  lea     rcx, [rbp+arg_10]
0x18001537d  call    ??$EULACheckWnfFailure@AEAJAEAY0CD@$$CBG@ProvisionTelemetryProvider@@SAXAEAJAEAY0CD@$$CBG@Z; ProvisionTelemetryProvider::EULACheckWnfFailure<long &,ushort const (&)[35]>(long &,ushort const (&)[35])
0x180015382  lea     r9, [rbp+arg_18]
0x180015386  lea     r8, [rbp+arg_8]
0x18001538a  lea     rdx, [rbp+arg_0]
0x18001538e  lea     rcx, WNF_SHEL_OOBE_USER_LOGON_COMPLETE
0x180015395  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18001539a  test    eax, eax
0x18001539c  js      short loc_1800153AD
0x18001539e  cmp     byte ptr [rbp+arg_0], 0
0x1800153a2  jz      short loc_1800153AD
0x1800153a4  cmp     [rbp+arg_8], ebx
0x1800153a7  jz      loc_18001548E
0x1800153ad  test    edi, edi
0x1800153af  jns     short loc_1800153BA
0x1800153b1  lea     rcx, [rbp+arg_10]
0x1800153b5  call    ??$EULACheckWnfFailure@AEAJAEAY0CC@$$CBG@ProvisionTelemetryProvider@@SAXAEAJAEAY0CC@$$CBG@Z; ProvisionTelemetryProvider::EULACheckWnfFailure<long &,ushort const (&)[34]>(long &,ushort const (&)[34])
0x1800153ba  lea     r9, [rbp+arg_18]
0x1800153be  lea     r8, [rbp+arg_8]
0x1800153c2  lea     rdx, [rbp+arg_0]
0x1800153c6  lea     rcx, WNF_CSHL_PRODUCT_READY
0x1800153cd  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800153d2  test    eax, eax
0x1800153d4  js      short loc_1800153E5
0x1800153d6  cmp     byte ptr [rbp+arg_0], 0
0x1800153da  jz      short loc_1800153E5
0x1800153dc  cmp     [rbp+arg_8], ebx
0x1800153df  jz      loc_18001548E
0x1800153e5  test    edi, edi
0x1800153e7  jns     short loc_1800153F2
0x1800153e9  lea     rcx, [rbp+arg_10]
0x1800153ed  call    ??$EULACheckWnfFailure@AEAJAEAY0BH@$$CBG@ProvisionTelemetryProvider@@SAXAEAJAEAY0BH@$$CBG@Z; ProvisionTelemetryProvider::EULACheckWnfFailure<long &,ushort const (&)[23]>(long &,ushort const (&)[23])
0x1800153f2  lea     rax, [rbp+var_10]
0x1800153f6  mov     [rbp+var_10], 4
0x1800153fd  mov     [rsp+50h+pcbData], rax; pcbData
0x180015402  lea     r8, aSetupdisplayed; "SetupDisplayedEula"
0x180015409  lea     rax, [rbp+arg_8]
0x18001540d  mov     r9d, 10h; dwFlags
0x180015413  mov     [rsp+50h+pvData], rax; pvData
0x180015418  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001541f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015426  mov     [rsp+50h+pdwType], 0; pdwType
0x18001542f  call    cs:__imp_RegGetValueW
0x180015435  mov     [rbp+arg_0], eax
0x180015438  test    eax, eax
0x18001543a  jnz     short loc_180015443
0x18001543c  cmp     [rbp+arg_8], ebx
0x18001543f  jnz     short loc_180015451
0x180015441  jmp     short loc_18001548E
0x180015443  cmp     eax, 2
0x180015446  jz      short loc_180015451
0x180015448  lea     rcx, [rbp+arg_0]
0x18001544c  call    ??$EULACheckRegistryFailure@AEAJAEAY0BD@$$CBG@ProvisionTelemetryProvider@@SAXAEAJAEAY0BD@$$CBG@Z; ProvisionTelemetryProvider::EULACheckRegistryFailure<long &,ushort const (&)[19]>(long &,ushort const (&)[19])
0x180015451  lea     rcx, [rbp+pszPath]
0x180015455  mov     [rbp+pszPath], 0
0x18001545d  call    cs:__imp_GetInstalledEULAPath
0x180015463  mov     [rbp+arg_10], eax
0x180015466  test    eax, eax
0x180015468  js      short loc_18001547A
0x18001546a  mov     rcx, [rbp+pszPath]; pszPath
0x18001546e  call    cs:__imp_PathFileExistsW
0x180015474  test    eax, eax
0x180015476  jz      short loc_180015483
0x180015478  jmp     short loc_180015485
0x18001547a  lea     rcx, [rbp+arg_10]
0x18001547e  call    ??$GetInstalledEULAPathFailure@AEAJ@ProvisionTelemetryProvider@@SAXAEAJ@Z; ProvisionTelemetryProvider::GetInstalledEULAPathFailure<long &>(long &)
0x180015483  xor     bl, bl
0x180015485  lea     rcx, [rbp+pszPath]
0x180015489  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?EulaFreeBuffer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&EulaFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&EulaFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001548e  mov     al, bl
0x180015490  add     rsp, 50h
0x180015494  pop     rdi
0x180015495  pop     rbx
0x180015496  pop     rbp
0x180015497  retn
```
