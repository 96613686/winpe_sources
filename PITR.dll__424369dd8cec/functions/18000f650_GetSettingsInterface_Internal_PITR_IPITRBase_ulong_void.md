# GetSettingsInterface_Internal(PITR::IPITRBase *,ulong,void * *)

- ea: `0x18000f650`
- end: `0x18000f975`
- name: `?GetSettingsInterface_Internal@@YAJPEAUIPITRBase@PITR@@KPEAPEAX@Z`
- size: `805`
- prototype: `__int64 __fastcall(struct PITR::IPITRBase *, int, struct CPITRSettings **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009e04`
- `0x18000f5f4`
- `0x18000f650`
- `0x18001def0`
- `0x1800502a7`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8be`
- `WDSCORE!CurrentIP` at `0x18000f69b`
- `WDSCORE!CurrentIP` at `0x18000f780`
- `WDSCORE!CurrentIP` at `0x18000f801`
- `WDSCORE!CurrentIP` at `0x18000f8c6`
- `WDSCORE!CurrentIP` at `0x18000f69b`
- `WDSCORE!CurrentIP` at `0x18000f780`
- `WDSCORE!CurrentIP` at `0x18000f801`
- `WDSCORE!CurrentIP` at `0x18000f8c6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f707`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f7e3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f864`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f707`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f7e3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f864`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000f886`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000f886`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f86f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f86f`

## string_xrefs

- `0x18000f6e4`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f7c0`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f841`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f90f`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`

## pseudocode

```c
__int64 __fastcall GetSettingsInterface_Internal(struct PITR::IPITRBase *a1, int a2, struct CPITRSettings **a3)
{
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int SettingsInterface; // esi
  CPITRBase *v10; // rax
  int v11; // ebp
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  _QWORD *v18; // rax
  struct CPITRSettings *v19; // rdi
  DWORD LastError; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  CPITRBase *v23; // rax
  struct CPITRSettings *v25; // [rsp+A8h] [rbp+20h] BYREF

  v25 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    if ( a2 != 1 )
    {
      LastError = GetLastError();
      v21 = CurrentIP();
      v22 = ConstructPartialMsgW(
              0x2000000u,
              "GetSettingsInterface: Found version mismatch: %d (internal) vs %d (caller).",
              1,
              a2);
      WdsSetupLogMessageW(
        v22,
        0,
        L"D",
        0,
        1473,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"GetSettingsInterface_Internal",
        v21,
        LastError,
        0,
        0);
      return (unsigned int)-2147023590;
    }
    v23 = (CPITRBase *)_RTDynamicCast_0(
                         a1,
                         0,
                         &PITR::IPITRBase `RTTI Type Descriptor',
                         &CPITRBase `RTTI Type Descriptor',
                         0);
    if ( v23 )
      return (unsigned int)CPITRBase::GetSettingsInterface(v23, a3);
    return (unsigned int)-2147024809;
  }
  if ( (unsigned int)(a2 - 1) > 1 )
  {
    v6 = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000u,
           "GetSettingsInterface: Found version mismatch: %d (internal) vs %d (caller).",
           2,
           a2);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      1429,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"GetSettingsInterface_Internal",
      v7,
      v6,
      0,
      0);
    return (unsigned int)-2147023590;
  }
  v10 = (CPITRBase *)_RTDynamicCast_0(
                       a1,
                       0,
                       &PITR::IPITRBase `RTTI Type Descriptor',
                       &CPITRBase `RTTI Type Descriptor',
                       0);
  if ( !v10 )
    return (unsigned int)-2147024809;
  SettingsInterface = CPITRBase::GetSettingsInterface(v10, &v25);
  if ( SettingsInterface >= 0 )
  {
    v11 = a2 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v12 = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(0x4000000u, "VERSIONTRACK: Will return settings interface version 2");
        WdsSetupLogMessageW(
          v14,
          0,
          L"D",
          0,
          1452,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"GetSettingsInterface_Internal",
          v13,
          v12,
          0,
          0);
        *a3 = v25;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
    else
    {
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(0x4000000u, "VERSIONTRACK: Will return settings interface version 1");
      WdsSetupLogMessageW(
        v17,
        0,
        L"D",
        0,
        1446,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"GetSettingsInterface_Internal",
        v16,
        v15,
        0,
        0);
      v18 = UnBCL::Object::operator new(0x20u);
      v19 = (struct CPITRSettings *)v18;
      if ( v18 )
      {
        UnBCL::Object::Object((UnBCL::Object *)(v18 + 1));
        *(_QWORD *)v19 = &CPITRSettings_V1::`vftable'{for `IPITRSettings_V1'};
        *((_QWORD *)v19 + 1) = &CPITRSettings_V1::`vftable'{for `UnBCL::Object'};
        *((_QWORD *)v19 + 3) = v25;
      }
      else
      {
        v19 = 0;
      }
      *a3 = v19;
    }
  }
  return (unsigned int)SettingsInterface;
}

```

## disassembly

```asm
0x18000f650  mov     rax, rsp
0x18000f653  mov     [rax+8], rbx
0x18000f657  mov     [rax+10h], rbp
0x18000f65b  push    rsi
0x18000f65c  push    rdi
0x18000f65d  push    r14
0x18000f65f  sub     rsp, 70h
0x18000f663  mov     r14, r8
0x18000f666  mov     ebp, edx
0x18000f668  mov     rbx, rcx
0x18000f66b  mov     qword ptr [rax+20h], 0
0x18000f673  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000f67a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000f67f  test    al, al
0x18000f681  jz      loc_18000F8B9
0x18000f687  lea     eax, [rbp-1]
0x18000f68a  cmp     eax, 1
0x18000f68d  jbe     loc_18000F717
0x18000f693  call    cs:__imp_GetLastError
0x18000f699  mov     edi, eax
0x18000f69b  call    cs:__imp_CurrentIP
0x18000f6a1  mov     rbx, rax
0x18000f6a4  mov     r9d, ebp
0x18000f6a7  mov     r8d, 2
0x18000f6ad  lea     rdx, aGetsettingsint_1; "GetSettingsInterface: Found version mis"...
0x18000f6b4  mov     ecx, 2000000h; unsigned int
0x18000f6b9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f6be  mov     [rsp+88h+var_38], 0
0x18000f6c6  mov     [rsp+88h+var_40], 0
0x18000f6cf  mov     [rsp+88h+var_48], edi
0x18000f6d3  mov     [rsp+88h+var_50], rbx
0x18000f6d8  lea     rcx, aGetsettingsint_0; "GetSettingsInterface_Internal"
0x18000f6df  mov     [rsp+88h+var_58], rcx
0x18000f6e4  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f6eb  mov     [rsp+88h+var_60], rcx
0x18000f6f0  mov     [rsp+88h+var_68], 595h
0x18000f6f8  xor     r9d, r9d
0x18000f6fb  lea     r8, aD; "D"
0x18000f702  xor     edx, edx
0x18000f704  mov     rcx, rax
0x18000f707  call    cs:__imp_WdsSetupLogMessageW
0x18000f70d  mov     esi, 8007051Ah
0x18000f712  jmp     loc_18000F95E
0x18000f717  mov     [rsp+88h+var_68], 0
0x18000f71f  lea     r9, ??_R0?AVCPITRBase@@@8; CPITRBase `RTTI Type Descriptor'
0x18000f726  lea     r8, ??_R0?AUIPITRBase@PITR@@@8; PITR::IPITRBase `RTTI Type Descriptor'
0x18000f72d  xor     edx, edx
0x18000f72f  mov     rcx, rbx
0x18000f732  call    __RTDynamicCast_0
0x18000f737  test    rax, rax
0x18000f73a  jnz     short loc_18000F746
0x18000f73c  mov     esi, 80070057h
0x18000f741  jmp     loc_18000F95E
0x18000f746  lea     rdx, [rsp+88h+arg_18]; struct CPITRSettings **
0x18000f74e  mov     rcx, rax; this
0x18000f751  call    ?GetSettingsInterface@CPITRBase@@QEAAJPEAPEAVCPITRSettings@@@Z; CPITRBase::GetSettingsInterface(CPITRSettings * *)
0x18000f756  mov     esi, eax
0x18000f758  test    eax, eax
0x18000f75a  js      loc_18000F95E
0x18000f760  sub     ebp, 1
0x18000f763  jz      loc_18000F7F9
0x18000f769  cmp     ebp, 1
0x18000f76c  jz      short loc_18000F778
0x18000f76e  mov     esi, 80004005h
0x18000f773  jmp     loc_18000F95E
0x18000f778  call    cs:__imp_GetLastError
0x18000f77e  mov     edi, eax
0x18000f780  call    cs:__imp_CurrentIP
0x18000f786  mov     rbx, rax
0x18000f789  lea     rdx, aVersiontrackWi_0; "VERSIONTRACK: Will return settings inte"...
0x18000f790  mov     ecx, 4000000h; unsigned int
0x18000f795  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f79a  mov     [rsp+88h+var_38], 0
0x18000f7a2  mov     [rsp+88h+var_40], 0
0x18000f7ab  mov     [rsp+88h+var_48], edi
0x18000f7af  mov     [rsp+88h+var_50], rbx
0x18000f7b4  lea     rcx, aGetsettingsint_0; "GetSettingsInterface_Internal"
0x18000f7bb  mov     [rsp+88h+var_58], rcx
0x18000f7c0  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f7c7  mov     [rsp+88h+var_60], rcx
0x18000f7cc  mov     [rsp+88h+var_68], 5ACh
0x18000f7d4  xor     r9d, r9d
0x18000f7d7  lea     r8, aD; "D"
0x18000f7de  xor     edx, edx
0x18000f7e0  mov     rcx, rax
0x18000f7e3  call    cs:__imp_WdsSetupLogMessageW
0x18000f7e9  mov     rax, [rsp+88h+arg_18]
0x18000f7f1  mov     [r14], rax
0x18000f7f4  jmp     loc_18000F95E
0x18000f7f9  call    cs:__imp_GetLastError
0x18000f7ff  mov     edi, eax
0x18000f801  call    cs:__imp_CurrentIP
0x18000f807  mov     rbx, rax
0x18000f80a  lea     rdx, aVersiontrackWi; "VERSIONTRACK: Will return settings inte"...
0x18000f811  mov     ecx, 4000000h; unsigned int
0x18000f816  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f81b  mov     [rsp+88h+var_38], 0
0x18000f823  mov     [rsp+88h+var_40], 0
0x18000f82c  mov     [rsp+88h+var_48], edi
0x18000f830  mov     [rsp+88h+var_50], rbx
0x18000f835  lea     rcx, aGetsettingsint_0; "GetSettingsInterface_Internal"
0x18000f83c  mov     [rsp+88h+var_58], rcx
0x18000f841  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f848  mov     [rsp+88h+var_60], rcx
0x18000f84d  mov     [rsp+88h+var_68], 5A6h
0x18000f855  xor     r9d, r9d
0x18000f858  lea     r8, aD; "D"
0x18000f85f  xor     edx, edx
0x18000f861  mov     rcx, rax
0x18000f864  call    cs:__imp_WdsSetupLogMessageW
0x18000f86a  mov     ecx, 20h ; ' '
0x18000f86f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f875  mov     rdi, rax
0x18000f878  mov     [rsp+88h+var_28], rax
0x18000f87d  test    rax, rax
0x18000f880  jz      short loc_18000F8AF
0x18000f882  lea     rcx, [rax+8]
0x18000f886  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x18000f88c  lea     rax, ??_7CPITRSettings_V1@@6BIPITRSettings_V1@@@; const CPITRSettings_V1::`vftable'{for `IPITRSettings_V1'}
0x18000f893  mov     [rdi], rax
0x18000f896  lea     rax, ??_7CPITRSettings_V1@@6BObject@UnBCL@@@; const CPITRSettings_V1::`vftable'{for `UnBCL::Object'}
0x18000f89d  mov     [rdi+8], rax
0x18000f8a1  mov     rcx, [rsp+88h+arg_18]
0x18000f8a9  mov     [rdi+18h], rcx
0x18000f8ad  jmp     short loc_18000F8B1
0x18000f8af  xor     edi, edi
0x18000f8b1  mov     [r14], rdi
0x18000f8b4  jmp     loc_18000F95E
0x18000f8b9  cmp     ebp, 1
0x18000f8bc  jz      short loc_18000F928
0x18000f8be  call    cs:__imp_GetLastError
0x18000f8c4  mov     edi, eax
0x18000f8c6  call    cs:__imp_CurrentIP
0x18000f8cc  mov     rbx, rax
0x18000f8cf  mov     r9d, ebp
0x18000f8d2  mov     r8d, 1
0x18000f8d8  lea     rdx, aGetsettingsint_1; "GetSettingsInterface: Found version mis"...
0x18000f8df  mov     ecx, 2000000h; unsigned int
0x18000f8e4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f8e9  mov     [rsp+88h+var_38], 0
0x18000f8f1  mov     [rsp+88h+var_40], 0
0x18000f8fa  mov     [rsp+88h+var_48], edi
0x18000f8fe  mov     [rsp+88h+var_50], rbx
0x18000f903  lea     rcx, aGetsettingsint_0; "GetSettingsInterface_Internal"
0x18000f90a  mov     [rsp+88h+var_58], rcx
0x18000f90f  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f916  mov     [rsp+88h+var_60], rcx
0x18000f91b  mov     [rsp+88h+var_68], 5C1h
0x18000f923  jmp     loc_18000F6F8
0x18000f928  mov     [rsp+88h+var_68], 0
0x18000f930  lea     r9, ??_R0?AVCPITRBase@@@8; CPITRBase `RTTI Type Descriptor'
0x18000f937  lea     r8, ??_R0?AUIPITRBase@PITR@@@8; PITR::IPITRBase `RTTI Type Descriptor'
0x18000f93e  xor     edx, edx
0x18000f940  mov     rcx, rbx
0x18000f943  call    __RTDynamicCast_0
0x18000f948  test    rax, rax
0x18000f94b  jz      loc_18000F73C
0x18000f951  mov     rdx, r14; struct CPITRSettings **
0x18000f954  mov     rcx, rax; this
0x18000f957  call    ?GetSettingsInterface@CPITRBase@@QEAAJPEAPEAVCPITRSettings@@@Z; CPITRBase::GetSettingsInterface(CPITRSettings * *)
0x18000f95c  mov     esi, eax
0x18000f95e  mov     eax, esi
0x18000f960  lea     r11, [rsp+88h+var_18]
0x18000f965  mov     rbx, [r11+20h]
0x18000f969  mov     rbp, [r11+28h]
0x18000f96d  mov     rsp, r11
0x18000f970  pop     r14
0x18000f972  pop     rdi
0x18000f973  pop     rsi
0x18000f974  retn
```
