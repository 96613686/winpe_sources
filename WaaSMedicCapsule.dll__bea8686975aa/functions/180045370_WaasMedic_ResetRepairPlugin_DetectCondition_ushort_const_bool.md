# WaasMedic::ResetRepairPlugin::DetectCondition(ushort const * *,bool *)

- ea: `0x180045370`
- end: `0x1800455cd`
- name: `?DetectCondition@ResetRepairPlugin@WaasMedic@@UEAAJPEAPEBGPEA_N@Z`
- size: `605`
- prototype: `__int64 __fastcall(WaasMedic::ResetRepairPlugin *__hidden this, const unsigned __int16 **, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000265c`
- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x180016c9c`
- `0x1800179c4`
- `0x18001ced8`
- `0x18002543c`
- `0x180045370`
- `0x180046ecc`
- `0x180047178`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045446`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18004543c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18004543c`

## string_xrefs

- `0x180045407`: `Plugin bypassing detection due to manual remediation.`
- `0x1800453ae`: `onecore\enduser\waasmedic\lib\plugins\resetrepairplugin.cpp`
- `0x18004545e`: `Failed to get host system Windows directory, Err=0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::ResetRepairPlugin::DetectCondition(
        WaasMedic::ResetRepairPlugin *this,
        const unsigned __int16 **a2,
        bool *a3)
{
  unsigned int v5; // ebx
  WaasMedic::ResetRepairPlugin *v7; // rcx
  signed int LastError; // eax
  int v9; // edi
  const struct _tlgProvider_t *v10; // rax
  int v11; // r9d
  int v12; // r8d
  const wchar_t *v13; // rsi
  unsigned __int64 v14; // rcx
  const wchar_t *v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h]
  bool v21; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x706,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\resetrepairplugin.cpp",
      (const char *)0x80004003LL,
      v20);
    return v5;
  }
  if ( a2 )
    *a2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
    || (v21 = 0, (int)WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(this, &v21) < 0)
    || !v21 )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to get host system Windows directory, Err=0x%08x", v5);
      return v5;
    }
    *a3 = 1;
    v9 = WaasMedic::ResetRepairPlugin::NeedRemediation(v7, Buffer, a3);
    if ( v9 >= 0 )
    {
      v10 = WaasMedic::TelemetryProvider::Provider();
      v12 = (int)v10;
      v13 = L"True";
      v14 = *(unsigned int *)v10;
      if ( (unsigned int)v14 > 5 )
      {
        v14 = *((_QWORD *)v10 + 2);
        if ( (v14 & 0x400000000000LL) != 0 && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
        {
          v15 = L"True";
          if ( !*a3 )
            v15 = L"False";
          v22 = v15;
          v23[0] = L"Remediation1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v12,
            (unsigned int)&unk_180089F50,
            v12,
            v11,
            (__int64)v23,
            (__int64)&v22);
        }
      }
      if ( *a3 )
        return 0;
      v9 = WaasMedic::ResetRepairPlugin::NeedRemediation2((WaasMedic::ResetRepairPlugin *)v14, Buffer, a3);
      if ( v9 >= 0 )
      {
        v16 = WaasMedic::TelemetryProvider::Provider();
        if ( *(_DWORD *)v16 > 5u
          && (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v16 + 3) & 0x400000000000LL) == *((_QWORD *)v16 + 3) )
        {
          v19 = !*a3;
          v22 = L"Remediation2";
          if ( v19 )
            v13 = L"False";
          v23[0] = v13;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v16,
            (unsigned int)&byte_180089FA7,
            v17,
            v18,
            (__int64)&v22,
            (__int64)v23);
        }
        return 0;
      }
      LogLevelW(2u, L"NeedRemediation2 failed. Err=0x%08x", (unsigned int)v9);
    }
    else
    {
      LogLevelW(2u, L"NeedRemediation failed. Err=0x%08x", (unsigned int)v9);
    }
    return (unsigned int)v9;
  }
  *a3 = 1;
  LogLevelW(4u, L"Plugin bypassing detection due to manual remediation.");
  return 0;
}

```

## disassembly

```asm
0x180045370  mov     [rsp-8+arg_18], rbx
0x180045375  push    rbp
0x180045376  push    rsi
0x180045377  push    rdi
0x180045378  push    r12
0x18004537a  push    r15
0x18004537c  lea     rbp, [rsp-170h]
0x180045384  sub     rsp, 270h
0x18004538b  mov     rax, cs:__security_cookie
0x180045392  xor     rax, rsp
0x180045395  mov     [rbp+190h+var_30], rax
0x18004539c  mov     rbx, r8
0x18004539f  mov     rdi, rcx
0x1800453a2  test    r8, r8
0x1800453a5  jnz     short loc_1800453CE
0x1800453a7  mov     rcx, [rbp+198h]; this
0x1800453ae  lea     r8, aOnecoreEnduser_39; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800453b5  mov     ebx, 80004003h
0x1800453ba  mov     edx, 706h; void *
0x1800453bf  mov     r9d, ebx; char *
0x1800453c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800453c7  mov     eax, ebx
0x1800453c9  jmp     loc_1800455A7
0x1800453ce  test    rdx, rdx
0x1800453d1  jz      short loc_1800453DA
0x1800453d3  mov     qword ptr [rdx], 0
0x1800453da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x1800453e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x1800453e6  test    al, al
0x1800453e8  jz      short loc_180045420
0x1800453ea  lea     rdx, [rsp+290h+var_260]; bool *
0x1800453ef  mov     [rsp+290h+var_260], 0
0x1800453f4  mov     rcx, rdi; this
0x1800453f7  call    ?IsManualRemediationApplicable@CRemediationPluginBase@WaasMedic@@IEAAJAEA_N@Z; WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(bool &)
0x1800453fc  test    eax, eax
0x1800453fe  js      short loc_180045420
0x180045400  cmp     [rsp+290h+var_260], 0
0x180045405  jz      short loc_180045420
0x180045407  lea     rdx, aPluginBypassin; "Plugin bypassing detection due to manua"...
0x18004540e  mov     byte ptr [rbx], 1
0x180045411  mov     ecx, 4; unsigned __int8
0x180045416  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004541b  jmp     loc_1800455A5
0x180045420  xor     edx, edx; Val
0x180045422  lea     rcx, [rsp+290h+Buffer]; void *
0x180045427  mov     r8d, 20Ah; Size
0x18004542d  call    memset_0
0x180045432  mov     edx, 104h; uSize
0x180045437  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x18004543c  call    cs:__imp_GetWindowsDirectoryW
0x180045442  test    eax, eax
0x180045444  jnz     short loc_180045474
0x180045446  call    cs:__imp_GetLastError
0x18004544c  mov     ebx, eax
0x18004544e  test    eax, eax
0x180045450  jle     short loc_18004545B
0x180045452  movzx   ebx, ax
0x180045455  or      ebx, 80070000h
0x18004545b  mov     r8d, ebx
0x18004545e  lea     rdx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180045465  mov     ecx, 2; unsigned __int8
0x18004546a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004546f  jmp     loc_1800453C7
0x180045474  mov     r8, rbx; bool *
0x180045477  mov     byte ptr [rbx], 1
0x18004547a  lea     rdx, [rsp+290h+Buffer]; unsigned __int16 *
0x18004547f  call    ?NeedRemediation@ResetRepairPlugin@WaasMedic@@AEAAJPEBGPEA_N@Z; WaasMedic::ResetRepairPlugin::NeedRemediation(ushort const *,bool *)
0x180045484  mov     edi, eax
0x180045486  test    eax, eax
0x180045488  jns     short loc_1800454A5
0x18004548a  lea     rdx, aNeedremediatio; "NeedRemediation failed. Err=0x%08x"
0x180045491  mov     r8d, edi
0x180045494  mov     ecx, 2; unsigned __int8
0x180045499  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004549e  mov     eax, edi
0x1800454a0  jmp     loc_1800455A7
0x1800454a5  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800454aa  mov     r8, rax
0x1800454ad  lea     r12, aFalse_2; "False"
0x1800454b4  mov     r15, 400000000000h
0x1800454be  lea     rsi, aTrue_0; "True"
0x1800454c5  mov     ecx, [rax]
0x1800454c7  cmp     ecx, 5
0x1800454ca  jbe     short loc_180045522
0x1800454cc  mov     rdx, [rax+18h]
0x1800454d0  mov     rcx, [rax+10h]
0x1800454d4  test    r15, rcx
0x1800454d7  jz      short loc_180045522
0x1800454d9  mov     rax, rdx
0x1800454dc  and     rax, r15
0x1800454df  cmp     rax, rdx
0x1800454e2  jnz     short loc_180045522
0x1800454e4  cmp     byte ptr [rbx], 0
0x1800454e7  lea     rdx, unk_180089F50
0x1800454ee  mov     rax, rsi
0x1800454f1  mov     rcx, r8
0x1800454f4  cmovz   rax, r12
0x1800454f8  mov     [rsp+290h+var_258], rax
0x1800454fd  lea     rax, aRemediation1; "Remediation1"
0x180045504  mov     [rsp+290h+var_250], rax
0x180045509  lea     rax, [rsp+290h+var_258]
0x18004550e  mov     [rsp+290h+var_268], rax
0x180045513  lea     rax, [rsp+290h+var_250]
0x180045518  mov     [rsp+290h+var_270], rax
0x18004551d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180045522  cmp     byte ptr [rbx], 0
0x180045525  jnz     short loc_1800455A5
0x180045527  mov     r8, rbx; bool *
0x18004552a  lea     rdx, [rsp+290h+Buffer]; unsigned __int16 *
0x18004552f  call    ?NeedRemediation2@ResetRepairPlugin@WaasMedic@@AEAAJPEBGPEA_N@Z; WaasMedic::ResetRepairPlugin::NeedRemediation2(ushort const *,bool *)
0x180045534  mov     edi, eax
0x180045536  test    eax, eax
0x180045538  jns     short loc_180045546
0x18004553a  lea     rdx, aNeedremediatio_0; "NeedRemediation2 failed. Err=0x%08x"
0x180045541  jmp     loc_180045491
0x180045546  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004554b  mov     ecx, [rax]
0x18004554d  cmp     ecx, 5
0x180045550  jbe     short loc_1800455A5
0x180045552  mov     rdx, [rax+18h]
0x180045556  mov     rcx, [rax+10h]
0x18004555a  test    r15, rcx
0x18004555d  jz      short loc_1800455A5
0x18004555f  mov     rcx, rdx
0x180045562  and     rcx, r15
0x180045565  cmp     rcx, rdx
0x180045568  jnz     short loc_1800455A5
0x18004556a  cmp     byte ptr [rbx], 0
0x18004556d  lea     rcx, aRemediation2; "Remediation2"
0x180045574  mov     [rsp+290h+var_258], rcx
0x180045579  lea     rdx, byte_180089FA7
0x180045580  lea     rcx, [rsp+290h+var_250]
0x180045585  cmovz   rsi, r12
0x180045589  mov     [rsp+290h+var_268], rcx
0x18004558e  lea     rcx, [rsp+290h+var_258]
0x180045593  mov     [rsp+290h+var_270], rcx
0x180045598  mov     rcx, rax
0x18004559b  mov     [rsp+290h+var_250], rsi
0x1800455a0  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800455a5  xor     eax, eax
0x1800455a7  mov     rcx, [rbp+190h+var_30]
0x1800455ae  xor     rcx, rsp; StackCookie
0x1800455b1  call    __security_check_cookie
0x1800455b6  mov     rbx, [rsp+290h+arg_18]
0x1800455be  add     rsp, 270h
0x1800455c5  pop     r15
0x1800455c7  pop     r12
0x1800455c9  pop     rdi
0x1800455ca  pop     rsi
0x1800455cb  pop     rbp
0x1800455cc  retn
```
