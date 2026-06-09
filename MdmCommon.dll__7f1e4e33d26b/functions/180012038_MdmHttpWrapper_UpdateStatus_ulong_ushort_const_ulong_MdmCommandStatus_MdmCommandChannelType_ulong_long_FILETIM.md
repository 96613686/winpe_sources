# MdmHttpWrapper::UpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)

- ea: `0x180012038`
- end: `0x1800124f4`
- name: `?UpdateStatus@MdmHttpWrapper@@SAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z`
- size: `1212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, unsigned int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005a10`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001bdc`
- `0x180002de4`
- `0x18000611c`
- `0x180006548`
- `0x18000b88c`
- `0x18000ef34`
- `0x180012038`
- `0x18001ce60`
- `0x18001f010`

## string_xrefs

- `0x180012189`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18001238c`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180012253`: `CHR(CreateUpdateStatusBody( eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, wstrRequestBody))`
- `0x1800122d3`: `CHR(MdmSettings::GetUpdateStatusPath(wstrPath))`
- `0x180012353`: `CHR(StringCchPrintfW(pwszPath, cchPath, wstrPath.c_str(), dwRequestId))`
- `0x180012414`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", pwszPath, pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`
- `0x18001227b`: `Software\Microsoft\MdmCommon\Internal`
- `0x180012274`: `UpdateStatusPath`
- `0x1800122b6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800122a2`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszUpdateStatusPathValueName, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::UpdateStatus(
        _DWORD *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
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
  __int64 v41; // [rsp+B0h] [rbp-A8h]
  __int64 v42; // [rsp+B8h] [rbp-A0h]
  __int64 v43; // [rsp+C0h] [rbp-98h]
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
                    (__int64)"CHR(((HRESULT)0x80004005L))");
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
                (__int64)"CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", pwszPath, pwszTicket, nullptr, wstrRe"
                         "questBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))");
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
              (__int64)"CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
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
            (__int64)"CHR(StringCchPrintfW(pwszPath, cchPath, wstrPath.c_str(), dwRequestId))");
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
          (__int64)"CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszUpdateStatusPathValueName, pszValue))");
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v27,
            v24,
            UpdateStatusBody,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            49,
            (__int64)"CHR(MdmSettings::GetUpdateStatusPath(wstrPath))");
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
        (__int64)"CHR(CreateUpdateStatusBody( eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, "
                 "pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pC"
                 "onnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLoc"
                 "ationSyncEnabledByClient, wstrRequestBody))");
    }
    goto LABEL_33;
  }
  UpdateStatusBody = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
    goto LABEL_35;
  McTemplateU0dsqs_EventWriteTransfer(
    a9,
    a10,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
    18,
    (__int64)"CBR(*ppwszBuffer == nullptr)");
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
0x180012038  push    rbx
0x18001203a  push    rsi
0x18001203b  push    rdi
0x18001203c  push    r12
0x18001203e  push    r13
0x180012040  push    r14
0x180012042  push    r15
0x180012044  sub     rsp, 120h
0x18001204b  mov     rax, cs:__security_cookie
0x180012052  xor     rax, rsp
0x180012055  mov     [rsp+158h+var_48], rax
0x18001205d  mov     r10d, r9d
0x180012060  mov     [rsp+158h+var_B8], r8d
0x180012068  mov     [rsp+158h+var_90], rdx
0x180012070  mov     rdi, rcx
0x180012073  mov     rcx, [rsp+158h+arg_40]
0x18001207b  mov     rdx, [rsp+158h+arg_48]
0x180012083  mov     r8, [rsp+158h+arg_50]
0x18001208b  mov     r9, [rsp+158h+arg_58]
0x180012093  mov     r11, [rsp+158h+arg_60]
0x18001209b  mov     rbx, [rsp+158h+arg_68]
0x1800120a3  mov     r15, [rsp+158h+arg_70]
0x1800120ab  mov     r12, [rsp+158h+arg_78]
0x1800120b3  mov     r13, [rsp+158h+arg_80]
0x1800120bb  mov     rax, [rsp+158h+arg_88]
0x1800120c3  mov     [rsp+158h+var_98], rax
0x1800120cb  mov     rax, [rsp+158h+arg_90]
0x1800120d3  mov     [rsp+158h+var_A0], rax
0x1800120db  mov     rax, [rsp+158h+arg_98]
0x1800120e3  mov     [rsp+158h+var_A8], rax
0x1800120eb  mov     r14, [rsp+158h+arg_A0]
0x1800120f3  xorps   xmm0, xmm0
0x1800120f6  movups  [rsp+158h+var_68], xmm0
0x1800120fe  xor     esi, esi
0x180012100  mov     [rsp+158h+var_58], rsi
0x180012108  mov     [rsp+158h+var_50], 7
0x180012114  mov     word ptr [rsp+158h+var_68], si
0x18001211c  mov     [rsp+158h+var_B0], rsi
0x180012124  mov     [rsp+158h+var_C8], esi
0x18001212b  mov     [rsp+158h+var_C0], rsi
0x180012133  movups  xmmword ptr [rsp+158h+var_88], xmm0
0x18001213b  mov     [rsp+158h+var_78], rsi
0x180012143  mov     [rsp+158h+var_70], 7
0x18001214f  xor     eax, eax
0x180012151  mov     word ptr [rsp+158h+var_88], ax
0x180012159  test    r14, r14
0x18001215c  jz      short loc_1800121A2
0x18001215e  cmp     [r14], rax
0x180012161  jz      short loc_18001219D
0x180012163  mov     ebx, 80070057h
0x180012168  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001216f  jz      loc_18001249A
0x180012175  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x18001217c  mov     [rsp+158h+var_130], rax
0x180012181  mov     dword ptr [rsp+158h+var_138], 112h
0x180012189  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012190  mov     r8d, ebx
0x180012193  call    McTemplateU0dsqs_EventWriteTransfer
0x180012198  jmp     loc_180012487
0x18001219d  mov     esi, 1
0x1800121a2  test    rdi, rdi
0x1800121a5  jz      short loc_1800121AD
0x1800121a7  mov     dword ptr [rdi], 0
0x1800121ad  lea     rax, [rsp+158h+var_68]
0x1800121b5  mov     [rsp+158h+var_D0], rax
0x1800121bd  mov     rax, [rsp+158h+var_A8]
0x1800121c5  mov     [rsp+158h+var_D8], rax
0x1800121cd  mov     rax, [rsp+158h+var_A0]
0x1800121d5  mov     [rsp+158h+var_E0], rax
0x1800121da  mov     rax, [rsp+158h+var_98]
0x1800121e2  mov     [rsp+158h+var_E8], rax
0x1800121e7  mov     [rsp+158h+var_F0], r13
0x1800121ec  mov     [rsp+158h+var_F8], r12
0x1800121f1  mov     [rsp+158h+var_100], r15
0x1800121f6  mov     [rsp+158h+var_108], rbx
0x1800121fb  mov     [rsp+158h+var_110], r11
0x180012200  mov     [rsp+158h+var_118], r9
0x180012205  mov     [rsp+158h+var_120], r8
0x18001220a  mov     [rsp+158h+var_128], rdx
0x18001220f  mov     [rsp+158h+var_130], rcx
0x180012214  mov     rax, [rsp+158h+arg_38]
0x18001221c  mov     [rsp+158h+var_138], rax
0x180012221  mov     r9d, [rsp+158h+arg_30]
0x180012229  mov     r8d, [rsp+158h+arg_28]
0x180012231  mov     edx, [rsp+158h+arg_20]
0x180012238  mov     ecx, r10d
0x18001223b  call    ?CreateUpdateStatusBody@MdmHttpWrapper@@CAJW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@3PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@5555PEAH666AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::CreateUpdateStatusBody(MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,std::wstring &)
0x180012240  mov     ebx, eax
0x180012242  test    eax, eax
0x180012244  jns     short loc_18001226C
0x180012246  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001224d  jz      loc_180012487
0x180012253  lea     rax, aChrCreateupdat; "CHR(CreateUpdateStatusBody( eCommandSta"...
0x18001225a  mov     [rsp+158h+var_130], rax
0x18001225f  mov     dword ptr [rsp+158h+var_138], 12Eh
0x180012267  jmp     loc_180012189
0x18001226c  lea     r9, [rsp+158h+var_88]
0x180012274  lea     r8, aUpdatestatuspa; "UpdateStatusPath"
0x18001227b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x180012282  mov     rcx, 0FFFFFFFF80000002h
0x180012289  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001228e  mov     ebx, eax
0x180012290  test    eax, eax
0x180012292  jns     short loc_1800122EC
0x180012294  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18001229a  test    al, 1
0x18001229c  jz      loc_180012487
0x1800122a2  lea     rax, aChrMdmregistry_12; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x1800122a9  mov     [rsp+158h+var_130], rax
0x1800122ae  mov     dword ptr [rsp+158h+var_138], 241h
0x1800122b6  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800122bd  mov     r8d, ebx
0x1800122c0  call    McTemplateU0dsqs_EventWriteTransfer
0x1800122c5  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800122cb  test    al, 1
0x1800122cd  jz      loc_180012487
0x1800122d3  lea     rax, aChrMdmsettings_7; "CHR(MdmSettings::GetUpdateStatusPath(ws"...
0x1800122da  mov     [rsp+158h+var_130], rax
0x1800122df  mov     dword ptr [rsp+158h+var_138], 131h
0x1800122e7  jmp     loc_180012189
0x1800122ec  mov     ebx, dword ptr [rsp+158h+var_78]
0x1800122f3  add     ebx, 0Bh
0x1800122f6  mov     eax, 2
0x1800122fb  mul     rbx
0x1800122fe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012305  cmovb   rax, rcx
0x180012309  mov     rcx, rax; unsigned __int64
0x18001230c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012311  mov     r15, rax
0x180012314  lea     r8, [rsp+158h+var_88]
0x18001231c  cmp     [rsp+158h+var_70], 7
0x180012325  cmova   r8, [rsp+158h+var_88]; unsigned __int16 *
0x18001232e  mov     r9d, [rsp+158h+var_B8]
0x180012336  mov     edx, ebx; unsigned __int64
0x180012338  mov     rcx, rax; unsigned __int16 *
0x18001233b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012340  mov     ebx, eax
0x180012342  test    eax, eax
0x180012344  jns     short loc_18001236C
0x180012346  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001234d  jz      loc_180012487
0x180012353  lea     rax, aChrStringcchpr; "CHR(StringCchPrintfW(pwszPath, cchPath,"...
0x18001235a  mov     [rsp+158h+var_130], rax
0x18001235f  mov     dword ptr [rsp+158h+var_138], 136h
0x180012367  jmp     loc_180012189
0x18001236c  lea     rcx, [rsp+158h+var_B0]; struct IMdmTransport **
0x180012374  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180012379  mov     ebx, eax
0x18001237b  test    eax, eax
0x18001237d  jns     short loc_1800123A5
0x18001237f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012386  jz      loc_180012487
0x18001238c  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180012393  mov     [rsp+158h+var_130], rax
0x180012398  mov     dword ptr [rsp+158h+var_138], 139h
0x1800123a0  jmp     loc_180012189
0x1800123a5  mov     rcx, [rsp+158h+var_B0]
0x1800123ad  mov     r8, [rcx]
0x1800123b0  mov     eax, esi
0x1800123b2  neg     eax
0x1800123b4  sbb     rdx, rdx
0x1800123b7  lea     rax, [rsp+158h+var_C0]
0x1800123bf  and     rdx, rax
0x1800123c2  mov     rax, [r8+18h]
0x1800123c6  mov     [rsp+158h+var_120], rdx
0x1800123cb  lea     rdx, [rsp+158h+var_C8]
0x1800123d3  mov     [rsp+158h+var_128], rdx
0x1800123d8  lea     rdx, [rsp+158h+var_68]
0x1800123e0  mov     [rsp+158h+var_130], rdx
0x1800123e5  mov     [rsp+158h+var_138], 0
0x1800123ee  mov     r9, [rsp+158h+var_90]
0x1800123f6  mov     r8, r15
0x1800123f9  lea     rdx, aPut; "PUT"
0x180012400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012405  mov     ebx, eax
0x180012407  test    eax, eax
0x180012409  jns     short loc_18001242D
0x18001240b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012412  jz      short loc_180012487
0x180012414  lea     rax, aChrPmdmtranspo_1; "CHR(pMdmTransport->SendRequestToCommand"...
0x18001241b  mov     [rsp+158h+var_130], rax
0x180012420  mov     dword ptr [rsp+158h+var_138], 142h
0x180012428  jmp     loc_180012189
0x18001242d  mov     eax, [rsp+158h+var_C8]
0x180012434  test    rdi, rdi
0x180012437  jz      short loc_18001243B
0x180012439  mov     [rdi], eax
0x18001243b  add     eax, 0FFFFFF38h
0x180012440  cmp     eax, 63h ; 'c'
0x180012443  jbe     short loc_18001246C
0x180012445  mov     ebx, 80004005h
0x18001244a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012451  jz      short loc_180012487
0x180012453  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x18001245a  mov     [rsp+158h+var_130], rax
0x18001245f  mov     dword ptr [rsp+158h+var_138], 14Ch
0x180012467  jmp     loc_180012189
0x18001246c  test    esi, esi
0x18001246e  jz      short loc_180012487
0x180012470  mov     rax, [rsp+158h+var_C0]
0x180012478  mov     [r14], rax
0x18001247b  mov     [rsp+158h+var_C0], 0
0x180012487  mov     rcx, [rsp+158h+var_C0]; void *
0x18001248f  test    rcx, rcx
0x180012492  jz      short loc_18001249A
0x180012494  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012499  nop
0x18001249a  lea     rcx, [rsp+158h+var_88]
0x1800124a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800124a7  nop
0x1800124a8  mov     rcx, [rsp+158h+var_B0]
0x1800124b0  test    rcx, rcx
0x1800124b3  jz      short loc_1800124C2
0x1800124b5  mov     rax, [rcx]
0x1800124b8  mov     rax, [rax+10h]
0x1800124bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c1  nop
0x1800124c2  lea     rcx, [rsp+158h+var_68]
0x1800124ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800124cf  mov     eax, ebx
0x1800124d1  mov     rcx, [rsp+158h+var_48]
0x1800124d9  xor     rcx, rsp; StackCookie
0x1800124dc  call    __security_check_cookie
0x1800124e1  add     rsp, 120h
0x1800124e8  pop     r15
0x1800124ea  pop     r14
0x1800124ec  pop     r13
0x1800124ee  pop     r12
0x1800124f0  pop     rdi
0x1800124f1  pop     rsi
0x1800124f2  pop     rbx
0x1800124f3  retn
```
