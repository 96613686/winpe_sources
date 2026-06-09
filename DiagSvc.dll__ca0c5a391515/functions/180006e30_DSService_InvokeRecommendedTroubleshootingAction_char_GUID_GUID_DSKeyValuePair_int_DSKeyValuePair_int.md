# DSService::InvokeRecommendedTroubleshootingAction(char *,_GUID,_GUID,DSKeyValuePair *,int,DSKeyValuePair * *,int *)

- ea: `0x180006e30`
- end: `0x180007377`
- name: `?InvokeRecommendedTroubleshootingAction@DSService@@UEAAJPEADU_GUID@@1PEAUDSKeyValuePair@@HPEAPEAU3@PEAH@Z`
- size: `1351`
- prototype: `__int64 __fastcall(char *pv, char *String, struct _GUID *, struct _GUID *, struct DSKeyValuePair *, int, struct DSKeyValuePair **, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001178`
- `0x180001720`
- `0x1800017f4`
- `0x180006504`
- `0x180006e30`
- `0x180007ec4`
- `0x18001b0dc`
- `0x18001b118`
- `0x18001b3ac`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180006f1b`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180006f1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e6d`

## string_xrefs

- `0x180006e83`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006feb`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x18000708c`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x18000715a`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x18000724c`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x1800070b3`: `Create parameter Xml file`
- `0x180006e8a`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x180006f46`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x180007004`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x1800070a5`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x180007173`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x180007257`: `DSService::InvokeRecommendedTroubleshootingAction`
- `0x18000723d`: `InvokeRecommendedTroubleshootingAction`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DSService::InvokeRecommendedTroubleshootingAction(
        char *pv,
        char *String,
        struct _GUID *a3,
        struct _GUID *a4,
        struct DSKeyValuePair *a5,
        int a6,
        struct DSKeyValuePair **a7,
        int *a8)
{
  const char *v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ecx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  int ParameterXmlFile; // ebx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  char *v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  __int64 *v36; // rcx
  __int128 v37; // xmm1
  __int64 v38; // rax
  __int64 (__fastcall *v39)(__int64 *, __int128 *, __int128 *, struct DSKeyValuePair **, int *); // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v53; // [rsp+C0h] [rbp-80h] BYREF
  const char *v54; // [rsp+C8h] [rbp-78h] BYREF
  const char *v55; // [rsp+D0h] [rbp-70h] BYREF
  const char *v56; // [rsp+D8h] [rbp-68h] BYREF
  const char *v57; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v60; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+100h] [rbp-40h] BYREF
  __int64 v62; // [rsp+108h] [rbp-38h] BYREF
  __int64 v63; // [rsp+110h] [rbp-30h] BYREF
  __int64 v64; // [rsp+118h] [rbp-28h] BYREF
  __int64 v65; // [rsp+120h] [rbp-20h] BYREF
  const char *v66; // [rsp+128h] [rbp-18h] BYREF
  const char *v67; // [rsp+130h] [rbp-10h] BYREF
  const char *v68; // [rsp+138h] [rbp-8h] BYREF
  __int128 v69; // [rsp+140h] [rbp+0h] BYREF
  __int128 v70; // [rsp+150h] [rbp+10h] BYREF
  _BYTE v71[64]; // [rsp+160h] [rbp+20h] BYREF
  int v72; // [rsp+1B0h] [rbp+70h] BYREF
  char *v73; // [rsp+1B8h] [rbp+78h] BYREF

  v73 = String;
  v11 = String;
  TelemetryTimer::TelemetryTimer((TelemetryTimer *)v71);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 16));
  DSService::ToggleShutdownTimer(pv, 0);
  if ( (unsigned int)dword_180039000 > 5
    && (unsigned __int8)tlgKeywordOn(v13, v12, "DSService::InvokeRecommendedTroubleshootingAction") )
  {
    v72 = 328;
    v54 = "acquire lock, stop shutdown timer";
    v56 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v57 = pv + 104;
    v55 = v15;
    v53 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)byte_18002F861,
      (_DWORD)v15,
      v16,
      (__int64)&v57,
      (__int64)&v53,
      (__int64)&v54,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)&v72);
  }
  if ( v11 && strnlen(v11, 0x82u) > 0x81 )
  {
    ParameterXmlFile = -2147024809;
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v18, v17, v19) )
    {
      LODWORD(v73) = 336;
      v56 = "DSService::InvokeRecommendedTroubleshootingAction";
      v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v55 = "Invalid client correlation vector";
      v54 = pv + 104;
      v72 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_18002F7F8,
        v22,
        v23,
        (__int64)&v54,
        (__int64)&v72,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v73);
    }
    v24 = pv + 104;
  }
  else
  {
    v24 = pv + 104;
    ParameterXmlFile = Microsoft::WRL::Details::MakeAndInitialize<RunManager,IRunManager,char (&)[129],char * &>(
                         pv + 80,
                         pv + 104,
                         &v73);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v25, v26) )
    {
      v72 = 350;
      v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v53 = ParameterXmlFile;
      v56 = "DSService::InvokeRecommendedTroubleshootingAction";
      v55 = "RunManager initialize";
      v54 = pv + 104;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)&byte_18002F78F,
        v28,
        v29,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v72);
    }
    if ( ParameterXmlFile >= 0 )
    {
      ParameterXmlFile = HelperClass::CreateParameterXmlFile(a5, a6);
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v31, v30, v32) )
      {
        v72 = 360;
        v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
        v53 = ParameterXmlFile;
        v56 = "DSService::InvokeRecommendedTroubleshootingAction";
        v55 = "Create parameter Xml file";
        v54 = pv + 104;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)&word_18002F726,
          v34,
          v35,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v55,
          (__int64)&v56,
          (__int64)&v57,
          (__int64)&v72);
      }
      if ( ParameterXmlFile >= 0 )
      {
        v36 = (__int64 *)*((_QWORD *)pv + 10);
        v37 = (__int128)*a3;
        v38 = *v36;
        v70 = (__int128)*a4;
        v39 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *, struct DSKeyValuePair **, int *))(v38 + 56);
        v69 = v37;
        ParameterXmlFile = v39(v36, &v69, &v70, a7, a8);
        if ( (unsigned int)dword_180039000 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(v41, v40, v42) )
          {
            v72 = 375;
            v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
            v53 = ParameterXmlFile;
            v56 = "DSService::InvokeRecommendedTroubleshootingAction";
            v55 = "RunManager RunRtpDiagnosticPackage";
            v54 = pv + 104;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v43,
              (unsigned int)byte_18002F6BD,
              v44,
              v45,
              (__int64)&v54,
              (__int64)&v53,
              (__int64)&v55,
              (__int64)&v56,
              (__int64)&v57,
              (__int64)&v72);
          }
        }
      }
    }
    v11 = v73;
  }
  DSService::ToggleShutdownTimer(pv, 1);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v47, v46, v48) )
  {
    v57 = v11;
    v72 = 0;
    LOBYTE(v73) = ParameterXmlFile >= 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v53 = 0;
    LODWORD(v54) = TelemetryTimer::ElapsedTimeMs((TelemetryTimer *)v71);
    v65 = 0;
    v66 = "InvokeRecommendedTroubleshootingAction";
    v67 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v68 = "DSService::InvokeRecommendedTroubleshootingAction";
    *(_QWORD *)&v69 = "Finished executing diagnostic action";
    LODWORD(v55) = 387;
    LODWORD(v56) = ParameterXmlFile;
    *(_QWORD *)&v70 = v24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v49,
      (unsigned int)&word_18002F55E,
      v50,
      v51,
      (__int64)&v70,
      (__int64)&v56,
      (__int64)&v69,
      (__int64)&v68,
      (__int64)&v67,
      (__int64)&v55,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v54,
      (__int64)&v53,
      (__int64)&v73,
      (__int64)&v64,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v60,
      (__int64)&v59,
      (__int64)&v58,
      (__int64)&v72,
      (__int64)&v57);
  }
  if ( pv != (char *)-16LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 16));
  return (unsigned int)ParameterXmlFile;
}

```

## disassembly

```asm
0x180006e30  mov     [rsp-8+arg_10], rbx
0x180006e35  mov     [rsp-8+arg_8], rdx
0x180006e3a  push    rbp
0x180006e3b  push    rsi
0x180006e3c  push    rdi
0x180006e3d  push    r12
0x180006e3f  push    r13
0x180006e41  push    r14
0x180006e43  push    r15
0x180006e45  lea     rbp, [rsp-30h]
0x180006e4a  sub     rsp, 170h
0x180006e51  mov     rdi, rcx
0x180006e54  mov     r12, r9
0x180006e57  lea     rcx, [rbp+60h+var_40]; this
0x180006e5b  mov     r13, r8
0x180006e5e  mov     r14, rdx
0x180006e61  call    ??0TelemetryTimer@@QEAA@XZ; TelemetryTimer::TelemetryTimer(void)
0x180006e66  lea     r15, [rdi+10h]
0x180006e6a  mov     rcx, r15; lpCriticalSection
0x180006e6d  call    cs:__imp_EnterCriticalSection
0x180006e73  xor     edx, edx; int
0x180006e75  mov     rcx, rdi; pv
0x180006e78  call    ?ToggleShutdownTimer@DSService@@IEAAXH@Z; DSService::ToggleShutdownTimer(int)
0x180006e7d  mov     eax, cs:dword_180039000
0x180006e83  lea     rsi, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006e8a  lea     r8, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x180006e91  cmp     eax, 5
0x180006e94  jbe     short loc_180006F0A
0x180006e96  call    _tlgKeywordOn
0x180006e9b  test    al, al
0x180006e9d  jz      short loc_180006F0A
0x180006e9f  lea     rax, aAcquireLockSto; "acquire lock, stop shutdown timer"
0x180006ea6  mov     [rbp+60h+arg_0], 148h
0x180006ead  mov     [rbp+60h+var_D8], rax
0x180006eb1  lea     rdx, byte_18002F861
0x180006eb8  lea     rax, [rdi+68h]
0x180006ebc  mov     [rbp+60h+var_C8], rsi
0x180006ec0  mov     [rbp+60h+var_C0], rax
0x180006ec4  lea     rax, [rbp+60h+arg_0]
0x180006ec8  mov     [rsp+1A0h+var_158], rax
0x180006ecd  lea     rax, [rbp+60h+var_C8]
0x180006ed1  mov     [rsp+1A0h+var_160], rax
0x180006ed6  lea     rax, [rbp+60h+var_D0]
0x180006eda  mov     [rsp+1A0h+var_168], rax
0x180006edf  lea     rax, [rbp+60h+var_D8]
0x180006ee3  mov     [rsp+1A0h+var_170], rax
0x180006ee8  lea     rax, [rbp+60h+var_E0]
0x180006eec  mov     [rsp+1A0h+var_178], rax
0x180006ef1  lea     rax, [rbp+60h+var_C0]
0x180006ef5  mov     [rsp+1A0h+var_180], rax
0x180006efa  mov     [rbp+60h+var_D0], r8
0x180006efe  mov     [rbp+60h+var_E0], 0
0x180006f05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006f0a  test    r14, r14
0x180006f0d  jz      loc_180006FC1
0x180006f13  mov     edx, 82h; MaxCount
0x180006f18  mov     rcx, r14; String
0x180006f1b  call    cs:__imp_strnlen
0x180006f21  cmp     rax, 81h
0x180006f27  jbe     loc_180006FC1
0x180006f2d  mov     eax, cs:dword_180039000
0x180006f33  mov     ebx, 80070057h
0x180006f38  cmp     eax, 5
0x180006f3b  jbe     short loc_180006FB8
0x180006f3d  call    _tlgKeywordOn
0x180006f42  test    al, al
0x180006f44  jz      short loc_180006FB8
0x180006f46  lea     rax, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x180006f4d  mov     dword ptr [rbp+60h+arg_8], 150h
0x180006f54  mov     [rbp+60h+var_C8], rax
0x180006f58  lea     rdx, unk_18002F7F8
0x180006f5f  lea     rax, aInvalidClientC; "Invalid client correlation vector"
0x180006f66  mov     [rbp+60h+var_C0], rsi
0x180006f6a  mov     [rbp+60h+var_D0], rax
0x180006f6e  lea     rax, [rdi+68h]
0x180006f72  mov     [rbp+60h+var_D8], rax
0x180006f76  lea     rax, [rbp+60h+arg_8]
0x180006f7a  mov     [rsp+1A0h+var_158], rax
0x180006f7f  lea     rax, [rbp+60h+var_C0]
0x180006f83  mov     [rsp+1A0h+var_160], rax
0x180006f88  lea     rax, [rbp+60h+var_C8]
0x180006f8c  mov     [rsp+1A0h+var_168], rax
0x180006f91  lea     rax, [rbp+60h+var_D0]
0x180006f95  mov     [rsp+1A0h+var_170], rax
0x180006f9a  lea     rax, [rbp+60h+arg_0]
0x180006f9e  mov     [rsp+1A0h+var_178], rax
0x180006fa3  lea     rax, [rbp+60h+var_D8]
0x180006fa7  mov     [rsp+1A0h+var_180], rax
0x180006fac  mov     [rbp+60h+arg_0], 80070057h
0x180006fb3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006fb8  lea     rsi, [rdi+68h]
0x180006fbc  jmp     loc_1800071CF
0x180006fc1  lea     rsi, [rdi+68h]
0x180006fc5  mov     rdx, rsi
0x180006fc8  lea     r8, [rbp+60h+arg_8]
0x180006fcc  lea     rcx, [rdi+50h]
0x180006fd0  call    ??$MakeAndInitialize@VRunManager@@UIRunManager@@AEAY0IB@DAEAPEAD@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIRunManager@@@WRL@Microsoft@@@012@AEAY0IB@DAEAPEAD@Z; Microsoft::WRL::Details::MakeAndInitialize<RunManager,IRunManager,char (&)[129],char * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IRunManager>>,char (&)[129],char * &)
0x180006fd5  mov     ecx, cs:dword_180039000
0x180006fdb  mov     ebx, eax
0x180006fdd  cmp     ecx, 5
0x180006fe0  jbe     short loc_18000705C
0x180006fe2  call    _tlgKeywordOn
0x180006fe7  test    al, al
0x180006fe9  jz      short loc_18000705C
0x180006feb  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006ff2  mov     [rbp+60h+arg_0], 15Eh
0x180006ff9  mov     [rbp+60h+var_C0], rax
0x180006ffd  lea     rdx, byte_18002F78F
0x180007004  lea     rax, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x18000700b  mov     [rbp+60h+var_E0], ebx
0x18000700e  mov     [rbp+60h+var_C8], rax
0x180007012  lea     rax, aRunmanagerInit; "RunManager initialize"
0x180007019  mov     [rbp+60h+var_D0], rax
0x18000701d  lea     rax, [rbp+60h+arg_0]
0x180007021  mov     [rsp+1A0h+var_158], rax
0x180007026  lea     rax, [rbp+60h+var_C0]
0x18000702a  mov     [rsp+1A0h+var_160], rax
0x18000702f  lea     rax, [rbp+60h+var_C8]
0x180007033  mov     [rsp+1A0h+var_168], rax
0x180007038  lea     rax, [rbp+60h+var_D0]
0x18000703c  mov     [rsp+1A0h+var_170], rax
0x180007041  lea     rax, [rbp+60h+var_E0]
0x180007045  mov     [rsp+1A0h+var_178], rax
0x18000704a  lea     rax, [rbp+60h+var_D8]
0x18000704e  mov     [rsp+1A0h+var_180], rax
0x180007053  mov     [rbp+60h+var_D8], rsi
0x180007057  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000705c  test    ebx, ebx
0x18000705e  js      loc_1800071CB
0x180007064  mov     edx, [rbp+60h+arg_28]; int
0x18000706a  mov     rcx, [rbp+60h+arg_20]; struct DSKeyValuePair *
0x180007071  call    ?CreateParameterXmlFile@HelperClass@@SAJPEAUDSKeyValuePair@@H@Z; HelperClass::CreateParameterXmlFile(DSKeyValuePair *,int)
0x180007076  mov     ebx, eax
0x180007078  mov     eax, cs:dword_180039000
0x18000707e  cmp     eax, 5
0x180007081  jbe     short loc_1800070FD
0x180007083  call    _tlgKeywordOn
0x180007088  test    al, al
0x18000708a  jz      short loc_1800070FD
0x18000708c  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180007093  mov     [rbp+60h+arg_0], 168h
0x18000709a  mov     [rbp+60h+var_C0], rax
0x18000709e  lea     rdx, word_18002F726
0x1800070a5  lea     rax, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x1800070ac  mov     [rbp+60h+var_E0], ebx
0x1800070af  mov     [rbp+60h+var_C8], rax
0x1800070b3  lea     rax, aCreateParamete; "Create parameter Xml file"
0x1800070ba  mov     [rbp+60h+var_D0], rax
0x1800070be  lea     rax, [rbp+60h+arg_0]
0x1800070c2  mov     [rsp+1A0h+var_158], rax
0x1800070c7  lea     rax, [rbp+60h+var_C0]
0x1800070cb  mov     [rsp+1A0h+var_160], rax
0x1800070d0  lea     rax, [rbp+60h+var_C8]
0x1800070d4  mov     [rsp+1A0h+var_168], rax
0x1800070d9  lea     rax, [rbp+60h+var_D0]
0x1800070dd  mov     [rsp+1A0h+var_170], rax
0x1800070e2  lea     rax, [rbp+60h+var_E0]
0x1800070e6  mov     [rsp+1A0h+var_178], rax
0x1800070eb  lea     rax, [rbp+60h+var_D8]
0x1800070ef  mov     [rsp+1A0h+var_180], rax
0x1800070f4  mov     [rbp+60h+var_D8], rsi
0x1800070f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800070fd  test    ebx, ebx
0x1800070ff  js      loc_1800071CB
0x180007105  mov     rcx, [rdi+50h]
0x180007109  lea     r8, [rbp+60h+var_50]
0x18000710d  movups  xmm0, xmmword ptr [r12]
0x180007112  mov     rdx, [rbp+60h+arg_38]
0x180007119  movups  xmm1, xmmword ptr [r13+0]
0x18000711e  mov     rax, [rcx]
0x180007121  mov     r9, [rbp+60h+arg_30]
0x180007128  mov     [rsp+1A0h+var_180], rdx
0x18000712d  lea     rdx, [rbp+60h+var_60]
0x180007131  movdqu  [rbp+60h+var_50], xmm0
0x180007136  mov     rax, [rax+38h]
0x18000713a  movdqu  [rbp+60h+var_60], xmm1
0x18000713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007144  mov     ebx, eax
0x180007146  mov     eax, cs:dword_180039000
0x18000714c  cmp     eax, 5
0x18000714f  jbe     short loc_1800071CB
0x180007151  call    _tlgKeywordOn
0x180007156  test    al, al
0x180007158  jz      short loc_1800071CB
0x18000715a  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180007161  mov     [rbp+60h+arg_0], 177h
0x180007168  mov     [rbp+60h+var_C0], rax
0x18000716c  lea     rdx, byte_18002F6BD
0x180007173  lea     rax, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x18000717a  mov     [rbp+60h+var_E0], ebx
0x18000717d  mov     [rbp+60h+var_C8], rax
0x180007181  lea     rax, aRunmanagerRunr_0; "RunManager RunRtpDiagnosticPackage"
0x180007188  mov     [rbp+60h+var_D0], rax
0x18000718c  lea     rax, [rbp+60h+arg_0]
0x180007190  mov     [rsp+1A0h+var_158], rax
0x180007195  lea     rax, [rbp+60h+var_C0]
0x180007199  mov     [rsp+1A0h+var_160], rax
0x18000719e  lea     rax, [rbp+60h+var_C8]
0x1800071a2  mov     [rsp+1A0h+var_168], rax
0x1800071a7  lea     rax, [rbp+60h+var_D0]
0x1800071ab  mov     [rsp+1A0h+var_170], rax
0x1800071b0  lea     rax, [rbp+60h+var_E0]
0x1800071b4  mov     [rsp+1A0h+var_178], rax
0x1800071b9  lea     rax, [rbp+60h+var_D8]
0x1800071bd  mov     [rsp+1A0h+var_180], rax
0x1800071c2  mov     [rbp+60h+var_D8], rsi
0x1800071c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800071cb  mov     r14, [rbp+60h+arg_8]
0x1800071cf  mov     edx, 1; int
0x1800071d4  mov     rcx, rdi; pv
0x1800071d7  call    ?ToggleShutdownTimer@DSService@@IEAAXH@Z; DSService::ToggleShutdownTimer(int)
0x1800071dc  mov     eax, cs:dword_180039000
0x1800071e2  cmp     eax, 5
0x1800071e5  jbe     loc_18000734C
0x1800071eb  call    _tlgKeywordOn
0x1800071f0  xor     edi, edi
0x1800071f2  test    al, al
0x1800071f4  jz      loc_18000734C
0x1800071fa  mov     eax, ebx
0x1800071fc  mov     [rbp+60h+var_C0], r14
0x180007200  shr     eax, 1Fh
0x180007203  lea     rcx, [rbp+60h+var_40]; this
0x180007207  xor     al, 1
0x180007209  mov     [rbp+60h+arg_0], edi
0x18000720c  mov     byte ptr [rbp+60h+arg_8], al
0x18000720f  mov     [rbp+60h+var_B8], rdi
0x180007213  mov     [rbp+60h+var_B0], rdi
0x180007217  mov     [rbp+60h+var_A8], rdi
0x18000721b  mov     [rbp+60h+var_A0], rdi
0x18000721f  mov     [rbp+60h+var_98], rdi
0x180007223  mov     [rbp+60h+var_90], rdi
0x180007227  mov     [rbp+60h+var_88], rdi
0x18000722b  mov     [rbp+60h+var_E0], edi
0x18000722e  call    ?ElapsedTimeMs@TelemetryTimer@@QEBA_KXZ; TelemetryTimer::ElapsedTimeMs(void)
0x180007233  mov     dword ptr [rbp+60h+var_D8], eax
0x180007236  lea     rdx, word_18002F55E
0x18000723d  lea     rax, aInvokerecommen; "InvokeRecommendedTroubleshootingAction"
0x180007244  mov     [rbp+60h+var_80], rdi
0x180007248  mov     [rbp+60h+var_78], rax
0x18000724c  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180007253  mov     [rbp+60h+var_70], rax
0x180007257  lea     rax, aDsserviceInvok; "DSService::InvokeRecommendedTroubleshoo"...
0x18000725e  mov     [rbp+60h+var_68], rax
0x180007262  lea     rax, aFinishedExecut; "Finished executing diagnostic action"
0x180007269  mov     qword ptr [rbp+60h+var_60], rax
0x18000726d  lea     rax, [rbp+60h+var_C0]
0x180007271  mov     [rsp+1A0h+var_E8], rax
0x180007279  lea     rax, [rbp+60h+arg_0]
0x18000727d  mov     [rsp+1A0h+var_F0], rax
0x180007285  lea     rax, [rbp+60h+var_B8]
0x180007289  mov     [rsp+1A0h+var_F8], rax
0x180007291  lea     rax, [rbp+60h+var_B0]
0x180007295  mov     [rsp+1A0h+var_100], rax
0x18000729d  lea     rax, [rbp+60h+var_A8]
0x1800072a1  mov     [rsp+1A0h+var_108], rax
0x1800072a9  lea     rax, [rbp+60h+var_A0]
0x1800072ad  mov     [rsp+1A0h+var_110], rax
0x1800072b5  lea     rax, [rbp+60h+var_98]
0x1800072b9  mov     [rsp+1A0h+var_118], rax
0x1800072c1  lea     rax, [rbp+60h+var_90]
0x1800072c5  mov     [rsp+1A0h+var_120], rax
0x1800072cd  lea     rax, [rbp+60h+var_88]
0x1800072d1  mov     [rsp+1A0h+var_128], rax
0x1800072d6  lea     rax, [rbp+60h+arg_8]
0x1800072da  mov     [rsp+1A0h+var_130], rax
0x1800072df  lea     rax, [rbp+60h+var_E0]
0x1800072e3  mov     [rsp+1A0h+var_138], rax
0x1800072e8  lea     rax, [rbp+60h+var_D8]
0x1800072ec  mov     [rsp+1A0h+var_140], rax
0x1800072f1  lea     rax, [rbp+60h+var_80]
0x1800072f5  mov     [rsp+1A0h+var_148], rax
0x1800072fa  lea     rax, [rbp+60h+var_78]
0x1800072fe  mov     [rsp+1A0h+var_150], rax
0x180007303  lea     rax, [rbp+60h+var_D0]
0x180007307  mov     [rsp+1A0h+var_158], rax
0x18000730c  lea     rax, [rbp+60h+var_70]
0x180007310  mov     [rsp+1A0h+var_160], rax
0x180007315  lea     rax, [rbp+60h+var_68]
0x180007319  mov     [rsp+1A0h+var_168], rax
0x18000731e  lea     rax, [rbp+60h+var_60]
0x180007322  mov     [rsp+1A0h+var_170], rax
0x180007327  lea     rax, [rbp+60h+var_C8]
0x18000732b  mov     [rsp+1A0h+var_178], rax
0x180007330  lea     rax, [rbp+60h+var_50]
0x180007334  mov     [rsp+1A0h+var_180], rax
0x180007339  mov     dword ptr [rbp+60h+var_D0], 183h
0x180007340  mov     dword ptr [rbp+60h+var_C8], ebx
0x180007343  mov     qword ptr [rbp+60h+var_50], rsi
0x180007347  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U1@U2@U2@U?$_tlgWrapperByVal@$00@@U1@U1@U1@U1@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343344AEBU?$_tlgWrapperByVal@$00@@333333343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000734c  test    r15, r15
0x18000734f  jz      short loc_18000735A
0x180007351  mov     rcx, r15; lpCriticalSection
0x180007354  call    cs:__imp_LeaveCriticalSection
0x18000735a  mov     eax, ebx
0x18000735c  mov     rbx, [rsp+1A0h+arg_10]
0x180007364  add     rsp, 170h
0x18000736b  pop     r15
0x18000736d  pop     r14
0x18000736f  pop     r13
0x180007371  pop     r12
  ... truncated ...
```
