# DSService::InvokeDiagnosticAction(char *,_GUID,_GUID,DSKeyValuePair *,int,DSKeyValuePair * *,int *)

- ea: `0x1800068e0`
- end: `0x180006e27`
- name: `?InvokeDiagnosticAction@DSService@@UEAAJPEADU_GUID@@1PEAUDSKeyValuePair@@HPEAPEAU3@PEAH@Z`
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
- `0x1800068e0`
- `0x180007ec4`
- `0x18001b0dc`
- `0x18001b118`
- `0x18001b3ac`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800069cb`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800069cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000691d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000691d`

## string_xrefs

- `0x180006933`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006a9b`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006b3c`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006c0a`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006cfc`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x18000693a`: `DSService::InvokeDiagnosticAction`
- `0x1800069f6`: `DSService::InvokeDiagnosticAction`
- `0x180006ab4`: `DSService::InvokeDiagnosticAction`
- `0x180006b55`: `DSService::InvokeDiagnosticAction`
- `0x180006c23`: `DSService::InvokeDiagnosticAction`
- `0x180006d07`: `DSService::InvokeDiagnosticAction`
- `0x180006b63`: `Create parameter Xml file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DSService::InvokeDiagnosticAction(
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
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v13, v12, "DSService::InvokeDiagnosticAction") )
  {
    v72 = 245;
    v54 = "acquire lock, stop shutdown timer";
    v56 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v57 = pv + 104;
    v55 = v15;
    v53 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)byte_18002FBCD,
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
      LODWORD(v73) = 253;
      v56 = "DSService::InvokeDiagnosticAction";
      v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v55 = "Invalid client correlation vector";
      v54 = pv + 104;
      v72 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&dword_18002FB64,
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
      v72 = 267;
      v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v53 = ParameterXmlFile;
      v56 = "DSService::InvokeDiagnosticAction";
      v55 = "RunManager initialize";
      v54 = pv + 104;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)byte_18002FAFB,
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
        v72 = 277;
        v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
        v53 = ParameterXmlFile;
        v56 = "DSService::InvokeDiagnosticAction";
        v55 = "Create parameter Xml file";
        v54 = pv + 104;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)word_18002FA92,
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
        v39 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *, struct DSKeyValuePair **, int *))(v38 + 48);
        v69 = v37;
        ParameterXmlFile = v39(v36, &v69, &v70, a7, a8);
        if ( (unsigned int)dword_180039000 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(v41, v40, v42) )
          {
            v72 = 292;
            v57 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
            v53 = ParameterXmlFile;
            v56 = "DSService::InvokeDiagnosticAction";
            v55 = "RunManager RunDiagnosticPackage";
            v54 = pv + 104;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v43,
              (unsigned int)byte_18002FA29,
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
    v66 = "InvokeDiagnosticAction";
    v67 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v68 = "DSService::InvokeDiagnosticAction";
    *(_QWORD *)&v69 = "Finished executing diagnostic action";
    LODWORD(v55) = 304;
    LODWORD(v56) = ParameterXmlFile;
    *(_QWORD *)&v70 = v24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v49,
      (unsigned int)word_18002F8CA,
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
0x1800068e0  mov     [rsp-8+arg_10], rbx
0x1800068e5  mov     [rsp-8+arg_8], rdx
0x1800068ea  push    rbp
0x1800068eb  push    rsi
0x1800068ec  push    rdi
0x1800068ed  push    r12
0x1800068ef  push    r13
0x1800068f1  push    r14
0x1800068f3  push    r15
0x1800068f5  lea     rbp, [rsp-30h]
0x1800068fa  sub     rsp, 170h
0x180006901  mov     rdi, rcx
0x180006904  mov     r12, r9
0x180006907  lea     rcx, [rbp+60h+var_40]; this
0x18000690b  mov     r13, r8
0x18000690e  mov     r14, rdx
0x180006911  call    ??0TelemetryTimer@@QEAA@XZ; TelemetryTimer::TelemetryTimer(void)
0x180006916  lea     r15, [rdi+10h]
0x18000691a  mov     rcx, r15; lpCriticalSection
0x18000691d  call    cs:__imp_EnterCriticalSection
0x180006923  xor     edx, edx; int
0x180006925  mov     rcx, rdi; pv
0x180006928  call    ?ToggleShutdownTimer@DSService@@IEAAXH@Z; DSService::ToggleShutdownTimer(int)
0x18000692d  mov     eax, cs:dword_180039000
0x180006933  lea     rsi, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000693a  lea     r8, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x180006941  cmp     eax, 5
0x180006944  jbe     short loc_1800069BA
0x180006946  call    _tlgKeywordOn
0x18000694b  test    al, al
0x18000694d  jz      short loc_1800069BA
0x18000694f  lea     rax, aAcquireLockSto; "acquire lock, stop shutdown timer"
0x180006956  mov     [rbp+60h+arg_0], 0F5h
0x18000695d  mov     [rbp+60h+var_D8], rax
0x180006961  lea     rdx, byte_18002FBCD
0x180006968  lea     rax, [rdi+68h]
0x18000696c  mov     [rbp+60h+var_C8], rsi
0x180006970  mov     [rbp+60h+var_C0], rax
0x180006974  lea     rax, [rbp+60h+arg_0]
0x180006978  mov     [rsp+1A0h+var_158], rax
0x18000697d  lea     rax, [rbp+60h+var_C8]
0x180006981  mov     [rsp+1A0h+var_160], rax
0x180006986  lea     rax, [rbp+60h+var_D0]
0x18000698a  mov     [rsp+1A0h+var_168], rax
0x18000698f  lea     rax, [rbp+60h+var_D8]
0x180006993  mov     [rsp+1A0h+var_170], rax
0x180006998  lea     rax, [rbp+60h+var_E0]
0x18000699c  mov     [rsp+1A0h+var_178], rax
0x1800069a1  lea     rax, [rbp+60h+var_C0]
0x1800069a5  mov     [rsp+1A0h+var_180], rax
0x1800069aa  mov     [rbp+60h+var_D0], r8
0x1800069ae  mov     [rbp+60h+var_E0], 0
0x1800069b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800069ba  test    r14, r14
0x1800069bd  jz      loc_180006A71
0x1800069c3  mov     edx, 82h; MaxCount
0x1800069c8  mov     rcx, r14; String
0x1800069cb  call    cs:__imp_strnlen
0x1800069d1  cmp     rax, 81h
0x1800069d7  jbe     loc_180006A71
0x1800069dd  mov     eax, cs:dword_180039000
0x1800069e3  mov     ebx, 80070057h
0x1800069e8  cmp     eax, 5
0x1800069eb  jbe     short loc_180006A68
0x1800069ed  call    _tlgKeywordOn
0x1800069f2  test    al, al
0x1800069f4  jz      short loc_180006A68
0x1800069f6  lea     rax, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x1800069fd  mov     dword ptr [rbp+60h+arg_8], 0FDh
0x180006a04  mov     [rbp+60h+var_C8], rax
0x180006a08  lea     rdx, dword_18002FB64
0x180006a0f  lea     rax, aInvalidClientC; "Invalid client correlation vector"
0x180006a16  mov     [rbp+60h+var_C0], rsi
0x180006a1a  mov     [rbp+60h+var_D0], rax
0x180006a1e  lea     rax, [rdi+68h]
0x180006a22  mov     [rbp+60h+var_D8], rax
0x180006a26  lea     rax, [rbp+60h+arg_8]
0x180006a2a  mov     [rsp+1A0h+var_158], rax
0x180006a2f  lea     rax, [rbp+60h+var_C0]
0x180006a33  mov     [rsp+1A0h+var_160], rax
0x180006a38  lea     rax, [rbp+60h+var_C8]
0x180006a3c  mov     [rsp+1A0h+var_168], rax
0x180006a41  lea     rax, [rbp+60h+var_D0]
0x180006a45  mov     [rsp+1A0h+var_170], rax
0x180006a4a  lea     rax, [rbp+60h+arg_0]
0x180006a4e  mov     [rsp+1A0h+var_178], rax
0x180006a53  lea     rax, [rbp+60h+var_D8]
0x180006a57  mov     [rsp+1A0h+var_180], rax
0x180006a5c  mov     [rbp+60h+arg_0], 80070057h
0x180006a63  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006a68  lea     rsi, [rdi+68h]
0x180006a6c  jmp     loc_180006C7F
0x180006a71  lea     rsi, [rdi+68h]
0x180006a75  mov     rdx, rsi
0x180006a78  lea     r8, [rbp+60h+arg_8]
0x180006a7c  lea     rcx, [rdi+50h]
0x180006a80  call    ??$MakeAndInitialize@VRunManager@@UIRunManager@@AEAY0IB@DAEAPEAD@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIRunManager@@@WRL@Microsoft@@@012@AEAY0IB@DAEAPEAD@Z; Microsoft::WRL::Details::MakeAndInitialize<RunManager,IRunManager,char (&)[129],char * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IRunManager>>,char (&)[129],char * &)
0x180006a85  mov     ecx, cs:dword_180039000
0x180006a8b  mov     ebx, eax
0x180006a8d  cmp     ecx, 5
0x180006a90  jbe     short loc_180006B0C
0x180006a92  call    _tlgKeywordOn
0x180006a97  test    al, al
0x180006a99  jz      short loc_180006B0C
0x180006a9b  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006aa2  mov     [rbp+60h+arg_0], 10Bh
0x180006aa9  mov     [rbp+60h+var_C0], rax
0x180006aad  lea     rdx, byte_18002FAFB
0x180006ab4  lea     rax, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x180006abb  mov     [rbp+60h+var_E0], ebx
0x180006abe  mov     [rbp+60h+var_C8], rax
0x180006ac2  lea     rax, aRunmanagerInit; "RunManager initialize"
0x180006ac9  mov     [rbp+60h+var_D0], rax
0x180006acd  lea     rax, [rbp+60h+arg_0]
0x180006ad1  mov     [rsp+1A0h+var_158], rax
0x180006ad6  lea     rax, [rbp+60h+var_C0]
0x180006ada  mov     [rsp+1A0h+var_160], rax
0x180006adf  lea     rax, [rbp+60h+var_C8]
0x180006ae3  mov     [rsp+1A0h+var_168], rax
0x180006ae8  lea     rax, [rbp+60h+var_D0]
0x180006aec  mov     [rsp+1A0h+var_170], rax
0x180006af1  lea     rax, [rbp+60h+var_E0]
0x180006af5  mov     [rsp+1A0h+var_178], rax
0x180006afa  lea     rax, [rbp+60h+var_D8]
0x180006afe  mov     [rsp+1A0h+var_180], rax
0x180006b03  mov     [rbp+60h+var_D8], rsi
0x180006b07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006b0c  test    ebx, ebx
0x180006b0e  js      loc_180006C7B
0x180006b14  mov     edx, [rbp+60h+arg_28]; int
0x180006b1a  mov     rcx, [rbp+60h+arg_20]; struct DSKeyValuePair *
0x180006b21  call    ?CreateParameterXmlFile@HelperClass@@SAJPEAUDSKeyValuePair@@H@Z; HelperClass::CreateParameterXmlFile(DSKeyValuePair *,int)
0x180006b26  mov     ebx, eax
0x180006b28  mov     eax, cs:dword_180039000
0x180006b2e  cmp     eax, 5
0x180006b31  jbe     short loc_180006BAD
0x180006b33  call    _tlgKeywordOn
0x180006b38  test    al, al
0x180006b3a  jz      short loc_180006BAD
0x180006b3c  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006b43  mov     [rbp+60h+arg_0], 115h
0x180006b4a  mov     [rbp+60h+var_C0], rax
0x180006b4e  lea     rdx, word_18002FA92
0x180006b55  lea     rax, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x180006b5c  mov     [rbp+60h+var_E0], ebx
0x180006b5f  mov     [rbp+60h+var_C8], rax
0x180006b63  lea     rax, aCreateParamete; "Create parameter Xml file"
0x180006b6a  mov     [rbp+60h+var_D0], rax
0x180006b6e  lea     rax, [rbp+60h+arg_0]
0x180006b72  mov     [rsp+1A0h+var_158], rax
0x180006b77  lea     rax, [rbp+60h+var_C0]
0x180006b7b  mov     [rsp+1A0h+var_160], rax
0x180006b80  lea     rax, [rbp+60h+var_C8]
0x180006b84  mov     [rsp+1A0h+var_168], rax
0x180006b89  lea     rax, [rbp+60h+var_D0]
0x180006b8d  mov     [rsp+1A0h+var_170], rax
0x180006b92  lea     rax, [rbp+60h+var_E0]
0x180006b96  mov     [rsp+1A0h+var_178], rax
0x180006b9b  lea     rax, [rbp+60h+var_D8]
0x180006b9f  mov     [rsp+1A0h+var_180], rax
0x180006ba4  mov     [rbp+60h+var_D8], rsi
0x180006ba8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006bad  test    ebx, ebx
0x180006baf  js      loc_180006C7B
0x180006bb5  mov     rcx, [rdi+50h]
0x180006bb9  lea     r8, [rbp+60h+var_50]
0x180006bbd  movups  xmm0, xmmword ptr [r12]
0x180006bc2  mov     rdx, [rbp+60h+arg_38]
0x180006bc9  movups  xmm1, xmmword ptr [r13+0]
0x180006bce  mov     rax, [rcx]
0x180006bd1  mov     r9, [rbp+60h+arg_30]
0x180006bd8  mov     [rsp+1A0h+var_180], rdx
0x180006bdd  lea     rdx, [rbp+60h+var_60]
0x180006be1  movdqu  [rbp+60h+var_50], xmm0
0x180006be6  mov     rax, [rax+30h]
0x180006bea  movdqu  [rbp+60h+var_60], xmm1
0x180006bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf4  mov     ebx, eax
0x180006bf6  mov     eax, cs:dword_180039000
0x180006bfc  cmp     eax, 5
0x180006bff  jbe     short loc_180006C7B
0x180006c01  call    _tlgKeywordOn
0x180006c06  test    al, al
0x180006c08  jz      short loc_180006C7B
0x180006c0a  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006c11  mov     [rbp+60h+arg_0], 124h
0x180006c18  mov     [rbp+60h+var_C0], rax
0x180006c1c  lea     rdx, byte_18002FA29
0x180006c23  lea     rax, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x180006c2a  mov     [rbp+60h+var_E0], ebx
0x180006c2d  mov     [rbp+60h+var_C8], rax
0x180006c31  lea     rax, aRunmanagerRund; "RunManager RunDiagnosticPackage"
0x180006c38  mov     [rbp+60h+var_D0], rax
0x180006c3c  lea     rax, [rbp+60h+arg_0]
0x180006c40  mov     [rsp+1A0h+var_158], rax
0x180006c45  lea     rax, [rbp+60h+var_C0]
0x180006c49  mov     [rsp+1A0h+var_160], rax
0x180006c4e  lea     rax, [rbp+60h+var_C8]
0x180006c52  mov     [rsp+1A0h+var_168], rax
0x180006c57  lea     rax, [rbp+60h+var_D0]
0x180006c5b  mov     [rsp+1A0h+var_170], rax
0x180006c60  lea     rax, [rbp+60h+var_E0]
0x180006c64  mov     [rsp+1A0h+var_178], rax
0x180006c69  lea     rax, [rbp+60h+var_D8]
0x180006c6d  mov     [rsp+1A0h+var_180], rax
0x180006c72  mov     [rbp+60h+var_D8], rsi
0x180006c76  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006c7b  mov     r14, [rbp+60h+arg_8]
0x180006c7f  mov     edx, 1; int
0x180006c84  mov     rcx, rdi; pv
0x180006c87  call    ?ToggleShutdownTimer@DSService@@IEAAXH@Z; DSService::ToggleShutdownTimer(int)
0x180006c8c  mov     eax, cs:dword_180039000
0x180006c92  cmp     eax, 5
0x180006c95  jbe     loc_180006DFC
0x180006c9b  call    _tlgKeywordOn
0x180006ca0  xor     edi, edi
0x180006ca2  test    al, al
0x180006ca4  jz      loc_180006DFC
0x180006caa  mov     eax, ebx
0x180006cac  mov     [rbp+60h+var_C0], r14
0x180006cb0  shr     eax, 1Fh
0x180006cb3  lea     rcx, [rbp+60h+var_40]; this
0x180006cb7  xor     al, 1
0x180006cb9  mov     [rbp+60h+arg_0], edi
0x180006cbc  mov     byte ptr [rbp+60h+arg_8], al
0x180006cbf  mov     [rbp+60h+var_B8], rdi
0x180006cc3  mov     [rbp+60h+var_B0], rdi
0x180006cc7  mov     [rbp+60h+var_A8], rdi
0x180006ccb  mov     [rbp+60h+var_A0], rdi
0x180006ccf  mov     [rbp+60h+var_98], rdi
0x180006cd3  mov     [rbp+60h+var_90], rdi
0x180006cd7  mov     [rbp+60h+var_88], rdi
0x180006cdb  mov     [rbp+60h+var_E0], edi
0x180006cde  call    ?ElapsedTimeMs@TelemetryTimer@@QEBA_KXZ; TelemetryTimer::ElapsedTimeMs(void)
0x180006ce3  mov     dword ptr [rbp+60h+var_D8], eax
0x180006ce6  lea     rdx, word_18002F8CA
0x180006ced  lea     rax, aInvokediagnost; "InvokeDiagnosticAction"
0x180006cf4  mov     [rbp+60h+var_80], rdi
0x180006cf8  mov     [rbp+60h+var_78], rax
0x180006cfc  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006d03  mov     [rbp+60h+var_70], rax
0x180006d07  lea     rax, aDsserviceInvok_0; "DSService::InvokeDiagnosticAction"
0x180006d0e  mov     [rbp+60h+var_68], rax
0x180006d12  lea     rax, aFinishedExecut; "Finished executing diagnostic action"
0x180006d19  mov     qword ptr [rbp+60h+var_60], rax
0x180006d1d  lea     rax, [rbp+60h+var_C0]
0x180006d21  mov     [rsp+1A0h+var_E8], rax
0x180006d29  lea     rax, [rbp+60h+arg_0]
0x180006d2d  mov     [rsp+1A0h+var_F0], rax
0x180006d35  lea     rax, [rbp+60h+var_B8]
0x180006d39  mov     [rsp+1A0h+var_F8], rax
0x180006d41  lea     rax, [rbp+60h+var_B0]
0x180006d45  mov     [rsp+1A0h+var_100], rax
0x180006d4d  lea     rax, [rbp+60h+var_A8]
0x180006d51  mov     [rsp+1A0h+var_108], rax
0x180006d59  lea     rax, [rbp+60h+var_A0]
0x180006d5d  mov     [rsp+1A0h+var_110], rax
0x180006d65  lea     rax, [rbp+60h+var_98]
0x180006d69  mov     [rsp+1A0h+var_118], rax
0x180006d71  lea     rax, [rbp+60h+var_90]
0x180006d75  mov     [rsp+1A0h+var_120], rax
0x180006d7d  lea     rax, [rbp+60h+var_88]
0x180006d81  mov     [rsp+1A0h+var_128], rax
0x180006d86  lea     rax, [rbp+60h+arg_8]
0x180006d8a  mov     [rsp+1A0h+var_130], rax
0x180006d8f  lea     rax, [rbp+60h+var_E0]
0x180006d93  mov     [rsp+1A0h+var_138], rax
0x180006d98  lea     rax, [rbp+60h+var_D8]
0x180006d9c  mov     [rsp+1A0h+var_140], rax
0x180006da1  lea     rax, [rbp+60h+var_80]
0x180006da5  mov     [rsp+1A0h+var_148], rax
0x180006daa  lea     rax, [rbp+60h+var_78]
0x180006dae  mov     [rsp+1A0h+var_150], rax
0x180006db3  lea     rax, [rbp+60h+var_D0]
0x180006db7  mov     [rsp+1A0h+var_158], rax
0x180006dbc  lea     rax, [rbp+60h+var_70]
0x180006dc0  mov     [rsp+1A0h+var_160], rax
0x180006dc5  lea     rax, [rbp+60h+var_68]
0x180006dc9  mov     [rsp+1A0h+var_168], rax
0x180006dce  lea     rax, [rbp+60h+var_60]
0x180006dd2  mov     [rsp+1A0h+var_170], rax
0x180006dd7  lea     rax, [rbp+60h+var_C8]
0x180006ddb  mov     [rsp+1A0h+var_178], rax
0x180006de0  lea     rax, [rbp+60h+var_50]
0x180006de4  mov     [rsp+1A0h+var_180], rax
0x180006de9  mov     dword ptr [rbp+60h+var_D0], 130h
0x180006df0  mov     dword ptr [rbp+60h+var_C8], ebx
0x180006df3  mov     qword ptr [rbp+60h+var_50], rsi
0x180006df7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U1@U2@U2@U?$_tlgWrapperByVal@$00@@U1@U1@U1@U1@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343344AEBU?$_tlgWrapperByVal@$00@@333333343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180006dfc  test    r15, r15
0x180006dff  jz      short loc_180006E0A
0x180006e01  mov     rcx, r15; lpCriticalSection
0x180006e04  call    cs:__imp_LeaveCriticalSection
0x180006e0a  mov     eax, ebx
0x180006e0c  mov     rbx, [rsp+1A0h+arg_10]
0x180006e14  add     rsp, 170h
0x180006e1b  pop     r15
0x180006e1d  pop     r14
0x180006e1f  pop     r13
0x180006e21  pop     r12
  ... truncated ...
```
