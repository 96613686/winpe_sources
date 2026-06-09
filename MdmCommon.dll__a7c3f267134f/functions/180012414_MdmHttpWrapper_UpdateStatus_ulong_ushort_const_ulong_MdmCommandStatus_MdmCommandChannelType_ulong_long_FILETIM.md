# MdmHttpWrapper::UpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)

- ea: `0x180012414`
- end: `0x1800128d1`
- name: `?UpdateStatus@MdmHttpWrapper@@SAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z`
- size: `1213`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005a60`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001bdc`
- `0x180002de8`
- `0x180006174`
- `0x1800065c0`
- `0x18000bb9c`
- `0x18000f3b8`
- `0x180012414`
- `0x18001d4f4`
- `0x18001f010`

## string_xrefs

- `0x180012565`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180012768`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x18001262f`: `CHR(CreateUpdateStatusBody( eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, wstrRequestBody))`
- `0x1800126af`: `CHR(MdmSettings::GetUpdateStatusPath(wstrPath))`
- `0x18001272f`: `CHR(StringCchPrintfW(pwszPath, cchPath, wstrPath.c_str(), dwRequestId))`
- `0x1800127f0`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", pwszPath, pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`
- `0x180012657`: `Software\Microsoft\MdmCommon\Internal`
- `0x180012650`: `UpdateStatusPath`
- `0x180012692`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001267e`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszUpdateStatusPathValueName, pszValue))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmHttpWrapper::UpdateStatus(
        _DWORD *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        struct Windows::Data::Json::IJsonValue *a13,
        struct Windows::Data::Json::IJsonValue *a14,
        struct Windows::Data::Json::IJsonValue *a15,
        struct Windows::Data::Json::IJsonValue *a16,
        _DWORD *a17,
        _DWORD *a18,
        _DWORD *a19,
        _DWORD *a20,
        void **a21)
{
  int v22; // esi
  int UpdateStatusBody; // ebx
  unsigned __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  unsigned int v28; // ebx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r15
  const unsigned __int16 *v31; // r8
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // eax
  int v37; // [rsp+90h] [rbp-C8h] BYREF
  void *v38; // [rsp+98h] [rbp-C0h] BYREF
  unsigned int v39; // [rsp+A0h] [rbp-B8h]
  struct IMdmTransport *v40; // [rsp+A8h] [rbp-B0h] BYREF
  _DWORD *v41; // [rsp+B0h] [rbp-A8h]
  _DWORD *v42; // [rsp+B8h] [rbp-A0h]
  _DWORD *v43; // [rsp+C0h] [rbp-98h]
  __int64 v44; // [rsp+C8h] [rbp-90h]
  unsigned __int16 *v45[2]; // [rsp+D0h] [rbp-88h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-78h]
  unsigned __int64 v47; // [rsp+E8h] [rbp-70h]
  __int128 v48; // [rsp+F0h] [rbp-68h] BYREF
  __int64 v49; // [rsp+100h] [rbp-58h]
  __int64 v50; // [rsp+108h] [rbp-50h]

  v39 = a3;
  v44 = a2;
  v43 = a18;
  v42 = a19;
  v41 = a20;
  v48 = 0;
  v22 = 0;
  v49 = 0;
  v50 = 7;
  LOWORD(v48) = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(v45[0]) = 0;
  if ( !a21 )
    goto LABEL_6;
  if ( !*a21 )
  {
    v22 = 1;
LABEL_6:
    if ( a1 )
      *a1 = 0;
    UpdateStatusBody = MdmHttpWrapper::CreateUpdateStatusBody(
                         a4,
                         a5,
                         a6,
                         a7,
                         a8,
                         a9,
                         a10,
                         a11,
                         a12,
                         a13,
                         a14,
                         a15,
                         a16,
                         a17,
                         v43,
                         v42,
                         v41,
                         (__int64)&v48);
    if ( UpdateStatusBody >= 0 )
    {
      UpdateStatusBody = MdmRegistry::GetStringValue(
                           HKEY_LOCAL_MACHINE,
                           L"Software\\Microsoft\\MdmCommon\\Internal",
                           L"UpdateStatusPath",
                           v45);
      if ( UpdateStatusBody >= 0 )
      {
        v28 = v46 + 11;
        v29 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v46 + 11), 2u));
        v30 = v29;
        v31 = (const unsigned __int16 *)v45;
        if ( v47 > 7 )
          v31 = v45[0];
        UpdateStatusBody = StringCchPrintfW(v29, v28, v31, v39);
        if ( UpdateStatusBody >= 0 )
        {
          UpdateStatusBody = CreateHttpRequest(&v40);
          if ( UpdateStatusBody >= 0 )
          {
            UpdateStatusBody = (*(__int64 (__fastcall **)(struct IMdmTransport *, const wchar_t *, unsigned __int16 *, __int64, _QWORD, __int128 *, int *, unsigned __int64))(*(_QWORD *)v40 + 24LL))(
                                 v40,
                                 L"PUT",
                                 v30,
                                 v44,
                                 0,
                                 &v48,
                                 &v37,
                                 (unsigned __int64)&v38 & -(__int64)(v22 != 0));
            if ( UpdateStatusBody >= 0 )
            {
              v35 = v37;
              if ( a1 )
                *a1 = v37;
              if ( (unsigned int)(v35 - 200) <= 0x63 )
              {
                if ( v22 )
                {
                  *a21 = v38;
                  v38 = 0;
                }
              }
              else
              {
                UpdateStatusBody = -2147467259;
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v34,
                    v24,
                    -2147467259,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    76,
                    "CHR(((HRESULT)0x80004005L))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v34,
                v24,
                UpdateStatusBody,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                66,
                "CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", pwszPath, pwszTicket, nullptr, wstrRequestBody"
                ", &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v33,
              v24,
              UpdateStatusBody,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              57,
              "CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v32,
            v24,
            UpdateStatusBody,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            54,
            "CHR(StringCchPrintfW(pwszPath, cchPath, wstrPath.c_str(), dwRequestId))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v26,
          v24,
          UpdateStatusBody,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          65,
          "CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszUpdateStatusPathValueName, pszValue))");
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v27,
            v24,
            UpdateStatusBody,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            49,
            "CHR(MdmSettings::GetUpdateStatusPath(wstrPath))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v25,
        v24,
        UpdateStatusBody,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        46,
        "CHR(CreateUpdateStatusBody( eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, pftWorkSt"
        "arted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pf"
        "MasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, w"
        "strRequestBody))");
    }
    goto LABEL_33;
  }
  UpdateStatusBody = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
    goto LABEL_35;
  McTemplateU0dsqs_EventWriteTransfer(
    (_DWORD)a9,
    a10,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
    18,
    "CBR(*ppwszBuffer == nullptr)");
LABEL_33:
  if ( v38 )
    operator delete(v38, v24);
LABEL_35:
  std::wstring::~wstring(v45);
  if ( v40 )
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v40 + 16LL))(v40);
  std::wstring::~wstring(&v48);
  return (unsigned int)UpdateStatusBody;
}

```

## disassembly

```asm
0x180012414  push    rbx
0x180012416  push    rsi
0x180012417  push    rdi
0x180012418  push    r12
0x18001241a  push    r13
0x18001241c  push    r14
0x18001241e  push    r15
0x180012420  sub     rsp, 120h
0x180012427  mov     rax, cs:__security_cookie
0x18001242e  xor     rax, rsp
0x180012431  mov     [rsp+158h+var_48], rax
0x180012439  mov     r10d, r9d
0x18001243c  mov     [rsp+158h+var_B8], r8d
0x180012444  mov     [rsp+158h+var_90], rdx
0x18001244c  mov     rdi, rcx
0x18001244f  mov     rcx, [rsp+158h+arg_40]
0x180012457  mov     rdx, [rsp+158h+arg_48]
0x18001245f  mov     r8, [rsp+158h+arg_50]
0x180012467  mov     r9, [rsp+158h+arg_58]
0x18001246f  mov     r11, [rsp+158h+arg_60]
0x180012477  mov     rbx, [rsp+158h+arg_68]
0x18001247f  mov     r15, [rsp+158h+arg_70]
0x180012487  mov     r12, [rsp+158h+arg_78]
0x18001248f  mov     r13, [rsp+158h+arg_80]
0x180012497  mov     rax, [rsp+158h+arg_88]
0x18001249f  mov     [rsp+158h+var_98], rax
0x1800124a7  mov     rax, [rsp+158h+arg_90]
0x1800124af  mov     [rsp+158h+var_A0], rax
0x1800124b7  mov     rax, [rsp+158h+arg_98]
0x1800124bf  mov     [rsp+158h+var_A8], rax
0x1800124c7  mov     r14, [rsp+158h+arg_A0]
0x1800124cf  xorps   xmm0, xmm0
0x1800124d2  movups  [rsp+158h+var_68], xmm0
0x1800124da  xor     esi, esi
0x1800124dc  mov     [rsp+158h+var_58], rsi
0x1800124e4  mov     [rsp+158h+var_50], 7
0x1800124f0  mov     word ptr [rsp+158h+var_68], si
0x1800124f8  mov     [rsp+158h+var_B0], rsi
0x180012500  mov     [rsp+158h+var_C8], esi
0x180012507  mov     [rsp+158h+var_C0], rsi
0x18001250f  movups  xmmword ptr [rsp+158h+var_88], xmm0
0x180012517  mov     [rsp+158h+var_78], rsi
0x18001251f  mov     [rsp+158h+var_70], 7
0x18001252b  xor     eax, eax
0x18001252d  mov     word ptr [rsp+158h+var_88], ax
0x180012535  test    r14, r14
0x180012538  jz      short loc_18001257E
0x18001253a  cmp     [r14], rax
0x18001253d  jz      short loc_180012579
0x18001253f  mov     ebx, 80070057h
0x180012544  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001254b  jz      loc_180012876
0x180012551  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x180012558  mov     [rsp+158h+var_130], rax
0x18001255d  mov     dword ptr [rsp+158h+var_138], 112h
0x180012565  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001256c  mov     r8d, ebx
0x18001256f  call    McTemplateU0dsqs_EventWriteTransfer
0x180012574  jmp     loc_180012863
0x180012579  mov     esi, 1
0x18001257e  test    rdi, rdi
0x180012581  jz      short loc_180012589
0x180012583  mov     dword ptr [rdi], 0
0x180012589  lea     rax, [rsp+158h+var_68]
0x180012591  mov     [rsp+158h+var_D0], rax
0x180012599  mov     rax, [rsp+158h+var_A8]
0x1800125a1  mov     [rsp+158h+var_D8], rax
0x1800125a9  mov     rax, [rsp+158h+var_A0]
0x1800125b1  mov     [rsp+158h+var_E0], rax
0x1800125b6  mov     rax, [rsp+158h+var_98]
0x1800125be  mov     [rsp+158h+var_E8], rax
0x1800125c3  mov     [rsp+158h+var_F0], r13
0x1800125c8  mov     [rsp+158h+var_F8], r12
0x1800125cd  mov     [rsp+158h+var_100], r15
0x1800125d2  mov     [rsp+158h+var_108], rbx
0x1800125d7  mov     [rsp+158h+var_110], r11
0x1800125dc  mov     [rsp+158h+var_118], r9
0x1800125e1  mov     [rsp+158h+var_120], r8
0x1800125e6  mov     [rsp+158h+var_128], rdx
0x1800125eb  mov     [rsp+158h+var_130], rcx
0x1800125f0  mov     rax, [rsp+158h+arg_38]
0x1800125f8  mov     [rsp+158h+var_138], rax
0x1800125fd  mov     r9d, [rsp+158h+arg_30]
0x180012605  mov     r8d, [rsp+158h+arg_28]
0x18001260d  mov     edx, [rsp+158h+arg_20]
0x180012614  mov     ecx, r10d
0x180012617  call    ?CreateUpdateStatusBody@MdmHttpWrapper@@CAJW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@3PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@5555PEAH666AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::CreateUpdateStatusBody(MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,std::wstring &)
0x18001261c  mov     ebx, eax
0x18001261e  test    eax, eax
0x180012620  jns     short loc_180012648
0x180012622  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012629  jz      loc_180012863
0x18001262f  lea     rax, aChrCreateupdat; "CHR(CreateUpdateStatusBody( eCommandSta"...
0x180012636  mov     [rsp+158h+var_130], rax
0x18001263b  mov     dword ptr [rsp+158h+var_138], 12Eh
0x180012643  jmp     loc_180012565
0x180012648  lea     r9, [rsp+158h+var_88]
0x180012650  lea     r8, aUpdatestatuspa; "UpdateStatusPath"
0x180012657  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x18001265e  mov     rcx, 0FFFFFFFF80000002h
0x180012665  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001266a  mov     ebx, eax
0x18001266c  test    eax, eax
0x18001266e  jns     short loc_1800126C8
0x180012670  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180012676  test    al, 1
0x180012678  jz      loc_180012863
0x18001267e  lea     rax, aChrMdmregistry_12; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180012685  mov     [rsp+158h+var_130], rax
0x18001268a  mov     dword ptr [rsp+158h+var_138], 241h
0x180012692  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012699  mov     r8d, ebx
0x18001269c  call    McTemplateU0dsqs_EventWriteTransfer
0x1800126a1  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800126a7  test    al, 1
0x1800126a9  jz      loc_180012863
0x1800126af  lea     rax, aChrMdmsettings_7; "CHR(MdmSettings::GetUpdateStatusPath(ws"...
0x1800126b6  mov     [rsp+158h+var_130], rax
0x1800126bb  mov     dword ptr [rsp+158h+var_138], 131h
0x1800126c3  jmp     loc_180012565
0x1800126c8  mov     ebx, dword ptr [rsp+158h+var_78]
0x1800126cf  add     ebx, 0Bh
0x1800126d2  mov     eax, 2
0x1800126d7  mul     rbx
0x1800126da  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800126e1  cmovb   rax, rcx
0x1800126e5  mov     rcx, rax; unsigned __int64
0x1800126e8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800126ed  mov     r15, rax
0x1800126f0  lea     r8, [rsp+158h+var_88]
0x1800126f8  cmp     [rsp+158h+var_70], 7
0x180012701  cmova   r8, [rsp+158h+var_88]; unsigned __int16 *
0x18001270a  mov     r9d, [rsp+158h+var_B8]
0x180012712  mov     edx, ebx; unsigned __int64
0x180012714  mov     rcx, rax; unsigned __int16 *
0x180012717  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001271c  mov     ebx, eax
0x18001271e  test    eax, eax
0x180012720  jns     short loc_180012748
0x180012722  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012729  jz      loc_180012863
0x18001272f  lea     rax, aChrStringcchpr; "CHR(StringCchPrintfW(pwszPath, cchPath,"...
0x180012736  mov     [rsp+158h+var_130], rax
0x18001273b  mov     dword ptr [rsp+158h+var_138], 136h
0x180012743  jmp     loc_180012565
0x180012748  lea     rcx, [rsp+158h+var_B0]; struct IMdmTransport **
0x180012750  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180012755  mov     ebx, eax
0x180012757  test    eax, eax
0x180012759  jns     short loc_180012781
0x18001275b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012762  jz      loc_180012863
0x180012768  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x18001276f  mov     [rsp+158h+var_130], rax
0x180012774  mov     dword ptr [rsp+158h+var_138], 139h
0x18001277c  jmp     loc_180012565
0x180012781  mov     rcx, [rsp+158h+var_B0]
0x180012789  mov     r8, [rcx]
0x18001278c  mov     eax, esi
0x18001278e  neg     eax
0x180012790  sbb     rdx, rdx
0x180012793  lea     rax, [rsp+158h+var_C0]
0x18001279b  and     rdx, rax
0x18001279e  mov     rax, [r8+18h]
0x1800127a2  mov     [rsp+158h+var_120], rdx
0x1800127a7  lea     rdx, [rsp+158h+var_C8]
0x1800127af  mov     [rsp+158h+var_128], rdx
0x1800127b4  lea     rdx, [rsp+158h+var_68]
0x1800127bc  mov     [rsp+158h+var_130], rdx
0x1800127c1  mov     [rsp+158h+var_138], 0
0x1800127ca  mov     r9, [rsp+158h+var_90]
0x1800127d2  mov     r8, r15
0x1800127d5  lea     rdx, aPut; "PUT"
0x1800127dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e1  mov     ebx, eax
0x1800127e3  test    eax, eax
0x1800127e5  jns     short loc_180012809
0x1800127e7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800127ee  jz      short loc_180012863
0x1800127f0  lea     rax, aChrPmdmtranspo_1; "CHR(pMdmTransport->SendRequestToCommand"...
0x1800127f7  mov     [rsp+158h+var_130], rax
0x1800127fc  mov     dword ptr [rsp+158h+var_138], 142h
0x180012804  jmp     loc_180012565
0x180012809  mov     eax, [rsp+158h+var_C8]
0x180012810  test    rdi, rdi
0x180012813  jz      short loc_180012817
0x180012815  mov     [rdi], eax
0x180012817  add     eax, 0FFFFFF38h
0x18001281c  cmp     eax, 63h ; 'c'
0x18001281f  jbe     short loc_180012848
0x180012821  mov     ebx, 80004005h
0x180012826  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001282d  jz      short loc_180012863
0x18001282f  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180012836  mov     [rsp+158h+var_130], rax
0x18001283b  mov     dword ptr [rsp+158h+var_138], 14Ch
0x180012843  jmp     loc_180012565
0x180012848  test    esi, esi
0x18001284a  jz      short loc_180012863
0x18001284c  mov     rax, [rsp+158h+var_C0]
0x180012854  mov     [r14], rax
0x180012857  mov     [rsp+158h+var_C0], 0
0x180012863  mov     rcx, [rsp+158h+var_C0]; void *
0x18001286b  test    rcx, rcx
0x18001286e  jz      short loc_180012876
0x180012870  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012875  nop
0x180012876  lea     rcx, [rsp+158h+var_88]
0x18001287e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012883  nop
0x180012884  mov     rcx, [rsp+158h+var_B0]
0x18001288c  test    rcx, rcx
0x18001288f  jz      short loc_18001289E
0x180012891  mov     rax, [rcx]
0x180012894  mov     rax, [rax+10h]
0x180012898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001289d  nop
0x18001289e  lea     rcx, [rsp+158h+var_68]
0x1800128a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800128ab  mov     eax, ebx
0x1800128ad  mov     rcx, [rsp+158h+var_48]
0x1800128b5  xor     rcx, rsp; StackCookie
0x1800128b8  call    __security_check_cookie
0x1800128bd  add     rsp, 120h
0x1800128c4  pop     r15
0x1800128c6  pop     r14
0x1800128c8  pop     r13
0x1800128ca  pop     r12
0x1800128cc  pop     rdi
0x1800128cd  pop     rsi
0x1800128ce  pop     rbx
0x1800128cf  retn
```
