# DdcProtectionStateHelper::GetProtectionState(Windows::Data::Json::IJsonValue * *)

- ea: `0x180020068`
- end: `0x180020454`
- name: `?GetProtectionState@DdcProtectionStateHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013b38`
- `0x18001ce80`
- `0x18001d588`
- `0x18001e8a0`
- `0x18001f23c`
- `0x18001f2e0`
- `0x18001fd74`
- `0x180020068`
- `0x1800204a4`
- `0x18002a010`

## string_xrefs

- `0x180020127`: `Windows.Data.Json.JsonObject`
- `0x1800200be`: `CPR(ppJsonValue)`
- `0x1800200ff`: `CBR(*ppJsonValue == nullptr)`
- `0x1800200d2`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x180020158`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pProtectionState.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcProtectionStateHelper::GetProtectionState(struct Windows::Data::Json::IJsonValue **a1, int a2)
{
  int v3; // r8d
  int ProtectionPillarStatus; // edi
  int v5; // edx
  int v6; // ecx
  struct Windows::Data::Json::IJsonValue *v7; // rax
  struct Windows::Data::Json::IJsonObject *v8; // rcx
  char v10; // [rsp+20h] [rbp-50h]
  const char *v11; // [rsp+28h] [rbp-48h]
  struct Windows::Data::Json::IJsonObject *v12; // [rsp+30h] [rbp-40h] BYREF
  IUnknown *v13; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Data::Json::IJsonValue *v14; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h]

  v12 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    ProtectionPillarStatus = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_47;
    v11 = "CPR(ppJsonValue)";
    v10 = -1;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      v10,
      v11);
    goto LABEL_47;
  }
  if ( !*a1 )
  {
    v16 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ProtectionPillarStatus = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v16, &v12);
    if ( ProtectionPillarStatus >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      CreateInstanceWithCloak<IDashboard>(v6, v5, &v13);
      ProtectionPillarStatus = DdcProtectionStateHelper::GetProtectionPillarStatus((__int64)v13, 1u, (__int64)v12);
      if ( ProtectionPillarStatus >= 0 )
      {
        ProtectionPillarStatus = DdcProtectionStateHelper::GetProtectionPillarStatus((__int64)v13, 2u, (__int64)v12);
        if ( ProtectionPillarStatus >= 0 )
        {
          ProtectionPillarStatus = DdcProtectionStateHelper::GetProtectionPillarStatus((__int64)v13, 4u, (__int64)v12);
          if ( ProtectionPillarStatus >= 0 )
          {
            ProtectionPillarStatus = DdcProtectionStateHelper::GetProtectionPillarStatus(
                                       (__int64)v13,
                                       0x10u,
                                       (__int64)v12);
            if ( ProtectionPillarStatus >= 0 )
            {
              ProtectionPillarStatus = DdcProtectionStateHelper::GetProtectionPillarStatus(
                                         (__int64)v13,
                                         8u,
                                         (__int64)v12);
              if ( ProtectionPillarStatus >= 0 )
              {
                ProtectionPillarStatus = DdcProtectionStateHelper::GetThreatProtectionValues(v12);
                if ( ProtectionPillarStatus >= 0 )
                {
                  ProtectionPillarStatus = DdcProtectionStateHelper::GetDefenderValues(v12, a2);
                  if ( ProtectionPillarStatus >= 0 )
                  {
                    ProtectionPillarStatus = DdcProtectionStateHelper::GetNetworkProtectionValues(v12, a2);
                    if ( ProtectionPillarStatus >= 0 )
                    {
                      ProtectionPillarStatus = DdcProtectionStateHelper::GetAppAndBrowserValues(v12, a2);
                      if ( ProtectionPillarStatus >= 0 )
                      {
                        ProtectionPillarStatus = DdcProtectionStateHelper::GetHealthAdvisorValues(v12);
                        if ( ProtectionPillarStatus >= 0 )
                        {
                          ProtectionPillarStatus = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                                     (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v12,
                                                     (__int64)&v14);
                          if ( ProtectionPillarStatus >= 0 )
                          {
                            v7 = v14;
                            v14 = 0;
                            *a1 = v7;
                            goto LABEL_47;
                          }
                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                            goto LABEL_47;
                          v11 = "CHR(pProtectionState.As(&pProtectionStateAsValue))";
                          v10 = 80;
                        }
                        else
                        {
                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                            goto LABEL_47;
                          v11 = "CHR(GetHealthAdvisorValues(pProtectionState.Get()))";
                          v10 = 77;
                        }
                      }
                      else
                      {
                        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                          goto LABEL_47;
                        v11 = "CHR(GetAppAndBrowserValues(pProtectionState.Get()))";
                        v10 = 68;
                      }
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                        goto LABEL_47;
                      v11 = "CHR(GetNetworkProtectionValues(pProtectionState.Get()))";
                      v10 = 59;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_47;
                    v11 = "CHR(GetDefenderValues(pProtectionState.Get()))";
                    v10 = 53;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_47;
                  v11 = "CHR(GetThreatProtectionValues(pProtectionState.Get()))";
                  v10 = 41;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_47;
                v11 = "CHR(GetProtectionPillarStatus(pDashboard.Get(), Pillars_HealthAdvisor, pProtectionState.Get()))";
                v10 = 31;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_47;
              v11 = "CHR(GetProtectionPillarStatus(pDashboard.Get(), Pillars_AppAndBrowserProtection, pProtectionState.Get()))";
              v10 = 26;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_47;
            v11 = "CHR(GetProtectionPillarStatus(pDashboard.Get(), Pillars_NetworkProtection, pProtectionState.Get()))";
            v10 = 21;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_47;
          v11 = "CHR(GetProtectionPillarStatus(pDashboard.Get(), Pillars_Defender, pProtectionState.Get()))";
          v10 = 16;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_47;
        v11 = "CHR(GetProtectionPillarStatus(pDashboard.Get(), Pillars_ThreatProtection, pProtectionState.Get()))";
        v10 = 11;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_47;
      v11 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pProtectionState.GetAddressOf()))";
      v10 = 3;
    }
    v3 = ProtectionPillarStatus;
    goto LABEL_4;
  }
  ProtectionPillarStatus = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      0,
      "CBR(*ppJsonValue == nullptr)");
LABEL_47:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)ProtectionPillarStatus;
}

```

## disassembly

```asm
0x180020068  mov     [rsp-8+arg_8], rsi
0x18002006d  mov     [rsp-8+arg_10], rdi
0x180020072  push    rbp
0x180020073  mov     rbp, rsp
0x180020076  sub     rsp, 70h
0x18002007a  mov     rax, cs:__security_cookie
0x180020081  xor     rax, rsp
0x180020084  mov     [rbp+var_8], rax
0x180020088  mov     rsi, rcx
0x18002008b  mov     [rbp+var_40], 0
0x180020093  mov     [rbp+var_30], 0
0x18002009b  mov     [rbp+var_38], 0
0x1800200a3  test    rcx, rcx
0x1800200a6  jnz     short loc_1800200E3
0x1800200a8  mov     r8d, 80070057h
0x1800200ae  mov     edi, r8d
0x1800200b1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800200b8  jz      loc_180020402
0x1800200be  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x1800200c5  mov     [rsp+70h+var_48], rax
0x1800200ca  mov     dword ptr [rsp+70h+var_50], 1FFh
0x1800200d2  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800200d9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800200de  jmp     loc_180020402
0x1800200e3  cmp     qword ptr [rcx], 0
0x1800200e7  jz      short loc_180020115
0x1800200e9  mov     r8d, 80070057h
0x1800200ef  mov     edi, r8d
0x1800200f2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800200f9  jz      loc_180020402
0x1800200ff  lea     rax, aCbrPpjsonvalue_0; "CBR(*ppJsonValue == nullptr)"
0x180020106  mov     [rsp+70h+var_48], rax
0x18002010b  mov     dword ptr [rsp+70h+var_50], 200h
0x180020113  jmp     short loc_1800200D2
0x180020115  mov     [rbp+var_10], 0
0x18002011d  mov     r9d, 1Ch; unsigned int
0x180020123  lea     r8d, [r9+1]; unsigned int
0x180020127  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18002012e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180020132  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020137  nop
0x180020138  lea     rdx, [rbp+var_40]
0x18002013c  mov     rcx, [rbp+var_10]
0x180020140  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180020145  mov     edi, eax
0x180020147  test    eax, eax
0x180020149  jns     short loc_180020174
0x18002014b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020152  jz      loc_180020402
0x180020158  lea     rax, aChrActivateins_10; "CHR(ActivateInstance(HStringReference(R"...
0x18002015f  mov     [rsp+70h+var_48], rax
0x180020164  mov     dword ptr [rsp+70h+var_50], 203h
0x18002016c  mov     r8d, edi
0x18002016f  jmp     loc_1800200D2
0x180020174  lea     rcx, [rbp+var_38]
0x180020178  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002017d  lea     r8, [rbp+var_38]
0x180020181  call    ??$CreateInstanceWithCloak@UIDashboard@@@@YAJAEBU_GUID@@0PEAPEAUIDashboard@@@Z; CreateInstanceWithCloak<IDashboard>(_GUID const &,_GUID const &,IDashboard * *)
0x180020186  mov     r8, [rbp+var_40]
0x18002018a  mov     edx, 1
0x18002018f  mov     rcx, [rbp+var_38]
0x180020193  call    ?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)
0x180020198  mov     edi, eax
0x18002019a  test    eax, eax
0x18002019c  jns     short loc_1800201C1
0x18002019e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800201a5  jz      loc_180020402
0x1800201ab  lea     rax, aChrGetprotecti_0; "CHR(GetProtectionPillarStatus(pDashboar"...
0x1800201b2  mov     [rsp+70h+var_48], rax
0x1800201b7  mov     dword ptr [rsp+70h+var_50], 20Bh
0x1800201bf  jmp     short loc_18002016C
0x1800201c1  mov     r8, [rbp+var_40]
0x1800201c5  mov     edx, 2
0x1800201ca  mov     rcx, [rbp+var_38]
0x1800201ce  call    ?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)
0x1800201d3  mov     edi, eax
0x1800201d5  test    eax, eax
0x1800201d7  jns     short loc_1800201FF
0x1800201d9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800201e0  jz      loc_180020402
0x1800201e6  lea     rax, aChrGetprotecti_1; "CHR(GetProtectionPillarStatus(pDashboar"...
0x1800201ed  mov     [rsp+70h+var_48], rax
0x1800201f2  mov     dword ptr [rsp+70h+var_50], 210h
0x1800201fa  jmp     loc_18002016C
0x1800201ff  mov     r8, [rbp+var_40]
0x180020203  mov     edx, 4
0x180020208  mov     rcx, [rbp+var_38]
0x18002020c  call    ?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)
0x180020211  mov     edi, eax
0x180020213  test    eax, eax
0x180020215  jns     short loc_18002023D
0x180020217  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002021e  jz      loc_180020402
0x180020224  lea     rax, aChrGetprotecti_3; "CHR(GetProtectionPillarStatus(pDashboar"...
0x18002022b  mov     [rsp+70h+var_48], rax
0x180020230  mov     dword ptr [rsp+70h+var_50], 215h
0x180020238  jmp     loc_18002016C
0x18002023d  mov     r8, [rbp+var_40]
0x180020241  mov     edx, 10h
0x180020246  mov     rcx, [rbp+var_38]
0x18002024a  call    ?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)
0x18002024f  mov     edi, eax
0x180020251  test    eax, eax
0x180020253  jns     short loc_18002027B
0x180020255  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002025c  jz      loc_180020402
0x180020262  lea     rax, aChrGetprotecti; "CHR(GetProtectionPillarStatus(pDashboar"...
0x180020269  mov     [rsp+70h+var_48], rax
0x18002026e  mov     dword ptr [rsp+70h+var_50], 21Ah
0x180020276  jmp     loc_18002016C
0x18002027b  mov     r8, [rbp+var_40]
0x18002027f  mov     edx, 8
0x180020284  mov     rcx, [rbp+var_38]
0x180020288  call    ?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)
0x18002028d  mov     edi, eax
0x18002028f  test    eax, eax
0x180020291  jns     short loc_1800202B9
0x180020293  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002029a  jz      loc_180020402
0x1800202a0  lea     rax, aChrGetprotecti_2; "CHR(GetProtectionPillarStatus(pDashboar"...
0x1800202a7  mov     [rsp+70h+var_48], rax
0x1800202ac  mov     dword ptr [rsp+70h+var_50], 21Fh
0x1800202b4  jmp     loc_18002016C
0x1800202b9  mov     rcx, [rbp+var_40]; struct Windows::Data::Json::IJsonObject *
0x1800202bd  call    ?GetThreatProtectionValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetThreatProtectionValues(Windows::Data::Json::IJsonObject *)
0x1800202c2  mov     edi, eax
0x1800202c4  test    eax, eax
0x1800202c6  jns     short loc_1800202EE
0x1800202c8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800202cf  jz      loc_180020402
0x1800202d5  lea     rax, aChrGetthreatpr; "CHR(GetThreatProtectionValues(pProtecti"...
0x1800202dc  mov     [rsp+70h+var_48], rax
0x1800202e1  mov     dword ptr [rsp+70h+var_50], 229h
0x1800202e9  jmp     loc_18002016C
0x1800202ee  mov     rcx, [rbp+var_40]; struct Windows::Data::Json::IJsonObject *
0x1800202f2  call    ?GetDefenderValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetDefenderValues(Windows::Data::Json::IJsonObject *)
0x1800202f7  mov     edi, eax
0x1800202f9  test    eax, eax
0x1800202fb  jns     short loc_180020323
0x1800202fd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020304  jz      loc_180020402
0x18002030a  lea     rax, aChrGetdefender; "CHR(GetDefenderValues(pProtectionState."...
0x180020311  mov     [rsp+70h+var_48], rax
0x180020316  mov     dword ptr [rsp+70h+var_50], 235h
0x18002031e  jmp     loc_18002016C
0x180020323  mov     rcx, [rbp+var_40]; struct Windows::Data::Json::IJsonObject *
0x180020327  call    ?GetNetworkProtectionValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetNetworkProtectionValues(Windows::Data::Json::IJsonObject *)
0x18002032c  mov     edi, eax
0x18002032e  test    eax, eax
0x180020330  jns     short loc_180020358
0x180020332  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020339  jz      loc_180020402
0x18002033f  lea     rax, aChrGetnetworkp; "CHR(GetNetworkProtectionValues(pProtect"...
0x180020346  mov     [rsp+70h+var_48], rax
0x18002034b  mov     dword ptr [rsp+70h+var_50], 23Bh
0x180020353  jmp     loc_18002016C
0x180020358  mov     rcx, [rbp+var_40]; struct Windows::Data::Json::IJsonObject *
0x18002035c  call    ?GetAppAndBrowserValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetAppAndBrowserValues(Windows::Data::Json::IJsonObject *)
0x180020361  mov     edi, eax
0x180020363  test    eax, eax
0x180020365  jns     short loc_18002038D
0x180020367  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002036e  jz      loc_180020402
0x180020374  lea     rax, aChrGetappandbr; "CHR(GetAppAndBrowserValues(pProtectionS"...
0x18002037b  mov     [rsp+70h+var_48], rax
0x180020380  mov     dword ptr [rsp+70h+var_50], 244h
0x180020388  jmp     loc_18002016C
0x18002038d  mov     rcx, [rbp+var_40]; struct Windows::Data::Json::IJsonObject *
0x180020391  call    ?GetHealthAdvisorValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetHealthAdvisorValues(Windows::Data::Json::IJsonObject *)
0x180020396  mov     edi, eax
0x180020398  test    eax, eax
0x18002039a  jns     short loc_1800203BE
0x18002039c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800203a3  jz      short loc_180020402
0x1800203a5  lea     rax, aChrGethealthad; "CHR(GetHealthAdvisorValues(pProtectionS"...
0x1800203ac  mov     [rsp+70h+var_48], rax
0x1800203b1  mov     dword ptr [rsp+70h+var_50], 24Dh
0x1800203b9  jmp     loc_18002016C
0x1800203be  lea     rdx, [rbp+var_30]
0x1800203c2  lea     rcx, [rbp+var_40]
0x1800203c6  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800203cb  mov     edi, eax
0x1800203cd  test    eax, eax
0x1800203cf  jns     short loc_1800203F3
0x1800203d1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800203d8  jz      short loc_180020402
0x1800203da  lea     rax, aChrPprotection_12; "CHR(pProtectionState.As(&pProtectionSta"...
0x1800203e1  mov     [rsp+70h+var_48], rax
0x1800203e6  mov     dword ptr [rsp+70h+var_50], 250h
0x1800203ee  jmp     loc_18002016C
0x1800203f3  mov     rax, [rbp+var_30]
0x1800203f7  mov     [rbp+var_30], 0
0x1800203ff  mov     [rsi], rax
0x180020402  lea     rcx, [rbp+var_38]
0x180020406  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002040b  nop
0x18002040c  lea     rcx, [rbp+var_30]
0x180020410  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020415  nop
0x180020416  mov     rcx, [rbp+var_40]
0x18002041a  test    rcx, rcx
0x18002041d  jz      short loc_180020434
0x18002041f  mov     [rbp+var_40], 0
0x180020427  mov     rax, [rcx]
0x18002042a  mov     rax, [rax+10h]
0x18002042e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020433  nop
0x180020434  mov     eax, edi
0x180020436  mov     rcx, [rbp+var_8]
0x18002043a  xor     rcx, rsp; StackCookie
0x18002043d  call    __security_check_cookie
0x180020442  lea     r11, [rsp+70h+var_s0]
0x180020447  mov     rsi, [r11+18h]
0x18002044b  mov     rdi, [r11+20h]
0x18002044f  mov     rsp, r11
0x180020452  pop     rbp
0x180020453  retn
```
