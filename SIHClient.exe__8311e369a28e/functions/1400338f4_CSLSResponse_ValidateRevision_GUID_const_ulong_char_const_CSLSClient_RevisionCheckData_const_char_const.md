# CSLSResponse::ValidateRevision(_GUID const &,ulong,char const *,CSLSClient::RevisionCheckData const &,char const *)

- ea: `0x1400338f4`
- end: `0x140033e2d`
- name: `?ValidateRevision@CSLSResponse@@QEAAJAEBU_GUID@@KPEBDAEBURevisionCheckData@CSLSClient@@1@Z`
- size: `1337`
- prototype: `int(CSLSResponse *__hidden this, const struct _GUID *, unsigned int, const char *, const struct CSLSClient::RevisionCheckData *, const char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400333b4`

## callees

- `0x140003de4`
- `0x1400154b4`
- `0x140017934`
- `0x1400326d0`
- `0x1400338f4`
- `0x140038020`
- `0x140038140`
- `0x14003d4ac`
- `0x14003d4fc`
- `0x14003d87c`
- `0x140045af8`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400339bd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400339bd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033c7d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033c7d`
- `OLEAUT32!__imp_SysFreeString` at `0x140033968`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b52`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140033c27`
- `OLEAUT32!__imp_SysFreeString` at `0x140033df4`
- `OLEAUT32!__imp_SysFreeString` at `0x140033e05`
- `OLEAUT32!__imp_SysFreeString` at `0x140033968`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b52`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140033c27`
- `OLEAUT32!__imp_SysFreeString` at `0x140033df4`
- `OLEAUT32!__imp_SysFreeString` at `0x140033e05`

## string_xrefs

- `0x1400339ff`: `EnvironmentIDConfig`
- `0x140033979`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SLS`
- `0x140033a22`: `EnvironmentIDconfig test override set[%d]. EnforceMatch.`
- `0x140033b1e`: `[service(%08lX)] Local [value = %d]; New [%d] [value = %d]; Buffer [value = %d]; EnvironmentIDconfig [%d], override set.`
- `0x140033ac5`: `EnvironmentIDconfig test override set[%d]. Skip revision check [%s].)`
- `0x140033cf3`: `Validate Revision completes for Environment ID [%ws] (New [%d] Old [%d] Buffer [%d]).`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSLSResponse::ValidateRevision(
        CSLSResponse *this,
        struct _GUID *a2,
        unsigned int a3,
        char *a4,
        const struct CSLSClient::RevisionCheckData *a5)
{
  unsigned int v6; // r12d
  int v7; // esi
  unsigned int v8; // r13d
  unsigned int v9; // r14d
  OLECHAR *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // edi
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // esi
  __int64 v18; // rcx
  unsigned int v19; // ecx
  unsigned int v20; // edi
  const WCHAR *v21; // rax
  bool v22; // r14
  char v23; // r15
  bool v24; // cf
  const char *v25; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  PCNZWCH lpString2a; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  char *v30; // [rsp+30h] [rbp-D0h]
  bool v31; // [rsp+60h] [rbp-A0h]
  char v32; // [rsp+61h] [rbp-9Fh]
  BSTR v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-90h]
  struct _GUID *v35; // [rsp+78h] [rbp-88h]
  CSLSResponse *v36; // [rsp+80h] [rbp-80h]
  char *v37; // [rsp+88h] [rbp-78h]
  BSTR String; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v40; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[64]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = a4;
  v34 = a3;
  v35 = a2;
  v36 = this;
  v6 = *((_DWORD *)a5 + 2);
  v7 = 0;
  v8 = 2;
  v31 = 0;
  v32 = 0;
  v9 = 0;
  v10 = 0;
  v33 = 0;
  bstrString = 0;
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    SysFreeString(0);
    v33 = 0;
    if ( CSusBSTR::Append(
           (CSusBSTR *)&v33,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SLS",
           0x40u) < 0 )
      goto LABEL_19;
    LOWORD(String) = 92;
    if ( CSusBSTR::Append((CSusBSTR *)&v33, (const wchar_t *)&String, 1u) < 0 )
      goto LABEL_19;
    if ( !StringFromGUID2(a2, sz, 64) )
      goto LABEL_19;
    v11 = -1;
    do
      ++v11;
    while ( sz[v11] );
    if ( CSusBSTR::Append((CSusBSTR *)&v33, sz, v11) < 0 )
    {
LABEL_19:
      v10 = v33;
      goto LABEL_20;
    }
    v10 = v33;
    v14 = RegQueryDwordValueWithDefaultAndRangeCheck(v12, v33, L"EnvironmentIDConfig", 0);
    if ( v14 == 1 )
    {
      WUTrace(0, 0, 4, 4, 0, L"EnvironmentIDconfig test override set[%d]. EnforceMatch.");
      v32 = 1;
    }
    else if ( v14 == 2 )
    {
      WUTrace(0, 0, 4, 4, 0, L"EnvironmentIDconfig test override set[%d]. Skip revision check [%s].)");
      goto LABEL_47;
    }
    v15 = RegQueryDwordValueWithDefaultAndRangeCheck(v13, v10, L"RevisionIdLocal", 0);
    v17 = v15;
    if ( v15 )
      v6 = v15;
    v9 = RegQueryDwordValueWithDefaultAndRangeCheck(v16, v10, L"RevisionIdNew", 0);
    v31 = v9 != 0;
    v19 = RegQueryDwordValueWithDefaultAndRangeCheck(v18, v10, L"RevisionBuffer", 2);
    if ( v19 != 2 )
    {
      v8 = v19;
LABEL_18:
      WUTrace(
        0,
        0,
        4,
        4,
        0,
        L"[service(%08lX)] Local [value = %d]; New [%d] [value = %d]; Buffer [value = %d]; EnvironmentIDconfig [%d], override set.");
      goto LABEL_20;
    }
    v8 = 2;
    if ( v17 || v9 )
      goto LABEL_18;
  }
LABEL_20:
  SysFreeString(bstrString);
  v40 = 0;
  String = 0;
  bstrString = 0;
  v20 = 0;
  v7 = CWUSLSParse::Init((CWUSLSParse *)&v40, v34, v37);
  if ( v7 < 0
    || (SysFreeString(String),
        String = 0,
        v7 = CWUSLSParse::ExtractEnvIDRevisionID((__int64 **)&v40, &bstrString, &String),
        v7 < 0) )
  {
    LODWORD(lpString2) = v7;
    WUTrace("ExtractEnvIDRevisionID", 134, 4, 1, lpString2, L"Method failed");
  }
  else
  {
    v20 = o_wcstoul_0(String, 0, 10);
    WUTrace(0, 0, 4, 5, 0, L"Environment ID [%ws] Revision [%d]...");
  }
  SysFreeString(String);
  String = 0;
  CWUSLSParse::~CWUSLSParse((CWUSLSParse *)&v40);
  if ( v7 < 0 )
    goto LABEL_46;
  if ( v31 )
    v20 = v9;
  v21 = *(const WCHAR **)a5;
  if ( bstrString == *(BSTR *)a5 || bstrString && v21 && CompareStringW(0x7Fu, 1u, bstrString, -1, v21, -1) == 2 || v32 )
  {
    v22 = 0;
    v23 = 0;
    if ( v6 < v8 )
    {
      if ( v20 + v8 < v6 )
      {
        v23 = 1;
LABEL_42:
        v30 = (char *)bstrString;
        WUTrace(0, 0, 4, 4, 0, L"Validate Revision completes for Environment ID [%ws] (New [%d] Old [%d] Buffer [%d]).");
        if ( v22 )
        {
          WUTrace(0, 0, 4, 4, 0, L"Send SLS Discovery Revision Check[Old] Event.");
          v40 = *v35;
          sls::telemetry::DiscoveryEvent::SendOldButValidRevisionDetectedEvent(
            &v40,
            *((const wchar_t **)v36 + 2),
            v7,
            v25);
          goto LABEL_47;
        }
        if ( !v23 )
          goto LABEL_47;
        WUTrace(0, 0, 4, 4, 0, L"Send SLS Discovery Revision Check[Invalid] Event.");
        v7 = -2145078783;
        v40 = *v35;
        sls::telemetry::DiscoveryEvent::SendInvalidRevisionDetectedEvent(
          &v40,
          *((const wchar_t **)v36 + 2),
          bstrString,
          v20,
          v6,
          cchCount2,
          v30);
LABEL_46:
        LODWORD(lpString2a) = v7;
        WUTrace("CSLSResponse::ValidateRevision", 481, 32, 1, lpString2a, L"Method failed");
        goto LABEL_47;
      }
      v22 = v20 < v6;
    }
    else
    {
      v24 = v20 < v6 - v8;
      if ( v20 >= v6 - v8 )
      {
        v22 = v20 < v6;
        v24 = v20 < v6 - v8;
      }
      v23 = v24;
    }
    if ( v22 || v23 )
      goto LABEL_42;
  }
LABEL_47:
  SysFreeString(bstrString);
  bstrString = 0;
  SysFreeString(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400338f4  push    rbp
0x1400338f6  push    rbx
0x1400338f7  push    rsi
0x1400338f8  push    rdi
0x1400338f9  push    r12
0x1400338fb  push    r13
0x1400338fd  push    r14
0x1400338ff  push    r15
0x140033901  lea     rbp, [rsp-48h]
0x140033906  sub     rsp, 148h
0x14003390d  mov     rax, cs:__security_cookie
0x140033914  xor     rax, rsp
0x140033917  mov     [rbp+80h+var_50], rax
0x14003391b  mov     [rbp+80h+var_F8], r9
0x14003391f  mov     [rsp+180h+var_110], r8d
0x140033924  mov     rdi, rdx
0x140033927  mov     [rsp+180h+var_108], rdx
0x14003392c  mov     [rbp+80h+var_100], rcx
0x140033930  mov     r15, [rbp+80h+arg_20]
0x140033937  mov     r12d, [r15+8]
0x14003393b  xor     esi, esi
0x14003393d  lea     r13d, [rsi+2]
0x140033941  mov     [rsp+180h+var_120], sil
0x140033946  mov     [rsp+180h+var_11F], sil
0x14003394b  mov     r14d, esi
0x14003394e  mov     ebx, esi
0x140033950  mov     [rsp+180h+var_118], rbx
0x140033955  mov     [rbp+80h+bstrString], rsi
0x140033959  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14003395e  test    eax, eax
0x140033960  jz      loc_140033B4E
0x140033966  xor     ecx, ecx; bstrString
0x140033968  call    cs:__imp_SysFreeString
0x14003396e  mov     [rsp+180h+var_118], rsi
0x140033973  lea     ebx, [rsi+40h]
0x140033976  mov     r8d, ebx; unsigned int
0x140033979  lea     rdx, ?c_szWUTestSLSKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033980  lea     rcx, [rsp+180h+var_118]; this
0x140033985  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x14003398a  test    eax, eax
0x14003398c  js      loc_140033B45
0x140033992  lea     eax, [rsi+5Ch]
0x140033995  mov     word ptr [rbp+80h+String], ax
0x140033999  lea     r8d, [rsi+1]; unsigned int
0x14003399d  lea     rdx, [rbp+80h+String]; wchar_t *
0x1400339a1  lea     rcx, [rsp+180h+var_118]; this
0x1400339a6  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x1400339ab  test    eax, eax
0x1400339ad  js      loc_140033B45
0x1400339b3  mov     r8d, ebx; cchMax
0x1400339b6  lea     rdx, [rbp+80h+sz]; lpsz
0x1400339ba  mov     rcx, rdi; rguid
0x1400339bd  call    cs:__imp_StringFromGUID2
0x1400339c3  test    eax, eax
0x1400339c5  jz      loc_140033B45
0x1400339cb  lea     rax, [rbp+80h+sz]
0x1400339cf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400339d3  inc     r8; unsigned int
0x1400339d6  cmp     [rax+r8*2], si
0x1400339db  jnz     short loc_1400339D3
0x1400339dd  lea     rdx, [rbp+80h+sz]; wchar_t *
0x1400339e1  lea     rcx, [rsp+180h+var_118]; this
0x1400339e6  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x1400339eb  test    eax, eax
0x1400339ed  js      loc_140033B45
0x1400339f3  or      r13d, 0FFFFFFFFh
0x1400339f7  mov     [rsp+180h+cchCount2], r13d
0x1400339fc  xor     r9d, r9d
0x1400339ff  lea     r8, ?c_szRegSLSEnvironmentIDConfig@@3QB_WB; "EnvironmentIDConfig"
0x140033a06  mov     rbx, [rsp+180h+var_118]
0x140033a0b  mov     rdx, rbx
0x140033a0e  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140033a13  mov     edi, eax
0x140033a15  cmp     eax, 1
0x140033a18  jnz     loc_140033AB4
0x140033a1e  mov     dword ptr [rsp+180h+var_150], eax
0x140033a22  lea     rax, aEnvironmentidc_0; "EnvironmentIDconfig test override set[%"...
0x140033a29  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033a2e  mov     [rsp+180h+lpString2], rsi
0x140033a33  lea     eax, [rdi+3]
0x140033a36  mov     r9d, eax
0x140033a39  mov     r8d, eax
0x140033a3c  xor     edx, edx
0x140033a3e  xor     ecx, ecx
0x140033a40  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033a45  mov     [rsp+180h+var_11F], dil
0x140033a4a  mov     [rsp+180h+cchCount2], r13d
0x140033a4f  xor     r9d, r9d
0x140033a52  lea     r8, ?c_szRegSLSRevisionCheckIdLocal@@3QB_WB; "RevisionIdLocal"
0x140033a59  mov     rdx, rbx
0x140033a5c  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140033a61  mov     esi, eax
0x140033a63  test    eax, eax
0x140033a65  cmovnz  r12d, eax
0x140033a69  mov     [rsp+180h+cchCount2], r13d
0x140033a6e  xor     r9d, r9d
0x140033a71  lea     r8, ?c_szRegSLSRevisionCheckIdNew@@3QB_WB; "RevisionIdNew"
0x140033a78  mov     rdx, rbx
0x140033a7b  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140033a80  mov     r14d, eax
0x140033a83  test    eax, eax
0x140033a85  setnz   [rsp+180h+var_120]
0x140033a8a  mov     [rsp+180h+cchCount2], r13d
0x140033a8f  mov     r9d, 2
0x140033a95  lea     r8, ?c_szRegSLSRevisionBuffer@@3QB_WB; "RevisionBuffer"
0x140033a9c  mov     rdx, rbx
0x140033a9f  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140033aa4  mov     ecx, eax
0x140033aa6  mov     eax, 2
0x140033aab  cmp     ecx, eax
0x140033aad  jz      short loc_140033AED
0x140033aaf  mov     r13d, ecx
0x140033ab2  jmp     short loc_140033AF9
0x140033ab4  cmp     edi, 2
0x140033ab7  jnz     short loc_140033A4A
0x140033ab9  mov     rax, [r15]
0x140033abc  mov     [rsp+180h+var_148], rax
0x140033ac1  mov     dword ptr [rsp+180h+var_150], edi
0x140033ac5  lea     rax, aEnvironmentidc; "EnvironmentIDconfig test override set[%"...
0x140033acc  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033ad1  mov     [rsp+180h+lpString2], rsi
0x140033ad6  lea     eax, [rdi+2]
0x140033ad9  mov     r9d, eax
0x140033adc  mov     r8d, eax
0x140033adf  xor     edx, edx
0x140033ae1  xor     ecx, ecx
0x140033ae3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033ae8  jmp     loc_140033DF0
0x140033aed  mov     r13d, eax
0x140033af0  test    esi, esi
0x140033af2  jnz     short loc_140033AF9
0x140033af4  test    r14d, r14d
0x140033af7  jz      short loc_140033B4C
0x140033af9  movzx   eax, [rsp+180h+var_120]
0x140033afe  mov     [rsp+180h+var_128], edi
0x140033b02  mov     [rsp+180h+var_130], ecx
0x140033b06  mov     [rsp+180h+var_138], r14d
0x140033b0b  mov     [rsp+180h+var_140], eax
0x140033b0f  mov     dword ptr [rsp+180h+var_148], esi
0x140033b13  mov     rax, [rsp+180h+var_108]
0x140033b18  mov     eax, [rax]
0x140033b1a  mov     dword ptr [rsp+180h+var_150], eax
0x140033b1e  lea     rax, aService08lxLoc; "[service(%08lX)] Local [value = %d]; Ne"...
0x140033b25  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033b2a  xor     esi, esi
0x140033b2c  mov     [rsp+180h+lpString2], rsi
0x140033b31  lea     eax, [rsi+4]
0x140033b34  mov     r9d, eax
0x140033b37  mov     r8d, eax
0x140033b3a  xor     edx, edx
0x140033b3c  xor     ecx, ecx
0x140033b3e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033b43  jmp     short loc_140033B4E
0x140033b45  mov     rbx, [rsp+180h+var_118]
0x140033b4a  jmp     short loc_140033B4E
0x140033b4c  xor     esi, esi
0x140033b4e  mov     rcx, [rbp+80h+bstrString]; bstrString
0x140033b52  call    cs:__imp_SysFreeString
0x140033b58  xorps   xmm1, xmm1
0x140033b5b  movdqu  xmmword ptr [rbp+80h+var_E0.Data1], xmm1
0x140033b60  mov     [rbp+80h+String], rsi
0x140033b64  mov     [rbp+80h+bstrString], rsi
0x140033b68  mov     edi, esi
0x140033b6a  mov     r8, [rbp+80h+var_F8]; char *
0x140033b6e  mov     edx, [rsp+180h+var_110]; unsigned int
0x140033b72  lea     rcx, [rbp+80h+var_E0]; this
0x140033b76  call    ?Init@CWUSLSParse@@QEAAJKPEBD@Z; CWUSLSParse::Init(ulong,char const *)
0x140033b7b  mov     esi, eax
0x140033b7d  lea     rax, aMethodFailed; "Method failed"
0x140033b84  test    esi, esi
0x140033b86  js      short loc_140033BFE
0x140033b88  mov     rcx, [rbp+80h+String]; bstrString
0x140033b8c  call    cs:__imp_SysFreeString
0x140033b92  mov     [rbp+80h+String], 0
0x140033b9a  lea     r8, [rbp+80h+String]; wchar_t **
0x140033b9e  lea     rdx, [rbp+80h+bstrString]; wchar_t **
0x140033ba2  lea     rcx, [rbp+80h+var_E0]; this
0x140033ba6  call    ?ExtractEnvIDRevisionID@CWUSLSParse@@QEAAJPEAPEA_W0@Z; CWUSLSParse::ExtractEnvIDRevisionID(wchar_t * *,wchar_t * *)
0x140033bab  mov     esi, eax
0x140033bad  test    eax, eax
0x140033baf  js      short loc_140033BF7
0x140033bb1  xor     edx, edx; EndPtr
0x140033bb3  lea     r8d, [rdx+0Ah]; Radix
0x140033bb7  mov     rcx, [rbp+80h+String]; String
0x140033bbb  call    _o_wcstoul_0
0x140033bc0  mov     edi, eax
0x140033bc2  mov     dword ptr [rsp+180h+var_148], eax
0x140033bc6  mov     rax, [rbp+80h+bstrString]
0x140033bca  mov     [rsp+180h+var_150], rax
0x140033bcf  lea     rax, aEnvironmentIdW; "Environment ID [%ws] Revision [%d]..."
0x140033bd6  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033bdb  mov     [rsp+180h+lpString2], 0
0x140033be4  xor     edx, edx
0x140033be6  xor     ecx, ecx
0x140033be8  lea     r9d, [rdx+5]
0x140033bec  lea     r8d, [rdx+4]
0x140033bf0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033bf5  jmp     short loc_140033C23
0x140033bf7  lea     rax, aMethodFailed; "Method failed"
0x140033bfe  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033c03  mov     dword ptr [rsp+180h+lpString2], esi
0x140033c07  mov     edx, 86h
0x140033c0c  mov     r9d, 1
0x140033c12  lea     r8d, [r9+3]
0x140033c16  lea     rcx, aExtractenvidre; "ExtractEnvIDRevisionID"
0x140033c1d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033c22  nop
0x140033c23  mov     rcx, [rbp+80h+String]; bstrString
0x140033c27  call    cs:__imp_SysFreeString
0x140033c2d  mov     [rbp+80h+String], 0
0x140033c35  lea     rcx, [rbp+80h+var_E0]; this
0x140033c39  call    ??1CWUSLSParse@@QEAA@XZ; CWUSLSParse::~CWUSLSParse(void)
0x140033c3e  test    esi, esi
0x140033c40  js      loc_140033DC4
0x140033c46  cmp     [rsp+180h+var_120], 0
0x140033c4b  cmovnz  edi, r14d
0x140033c4f  mov     rax, [r15]
0x140033c52  mov     r8, [rbp+80h+bstrString]; lpString1
0x140033c56  cmp     r8, rax
0x140033c59  jz      short loc_140033C93
0x140033c5b  test    r8, r8
0x140033c5e  jz      short loc_140033C88
0x140033c60  test    rax, rax
0x140033c63  jz      short loc_140033C88
0x140033c65  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x140033c6d  mov     [rsp+180h+lpString2], rax; lpString2
0x140033c72  or      r9d, 0FFFFFFFFh; cchCount1
0x140033c76  lea     edx, [r9+2]; dwCmpFlags
0x140033c7a  lea     ecx, [rdx+7Eh]; Locale
0x140033c7d  call    cs:__imp_CompareStringW
0x140033c83  cmp     eax, 2
0x140033c86  jz      short loc_140033C93
0x140033c88  cmp     [rsp+180h+var_11F], 0
0x140033c8d  jz      loc_140033DF0
0x140033c93  xor     r14b, r14b
0x140033c96  xor     r15b, r15b
0x140033c99  cmp     r12d, r13d
0x140033c9c  jb      short loc_140033CB7
0x140033c9e  mov     eax, r12d
0x140033ca1  sub     eax, r13d
0x140033ca4  cmp     edi, eax
0x140033ca6  jb      short loc_140033CB1
0x140033ca8  cmp     edi, r12d
0x140033cab  setb    r14b
0x140033caf  cmp     edi, eax
0x140033cb1  setb    r15b
0x140033cb5  jmp     short loc_140033CC7
0x140033cb7  lea     eax, [rdi+r13]
0x140033cbb  cmp     eax, r12d
0x140033cbe  jb      short loc_140033CD9
0x140033cc0  cmp     edi, r12d
0x140033cc3  setb    r14b
0x140033cc7  mov     al, r15b
0x140033cca  test    r14b, r14b
0x140033ccd  jnz     short loc_140033CDC
0x140033ccf  test    al, al
0x140033cd1  jz      loc_140033DF0
0x140033cd7  jmp     short loc_140033CDC
0x140033cd9  mov     r15b, 1
0x140033cdc  mov     [rsp+180h+var_138], r13d
0x140033ce1  mov     [rsp+180h+var_140], r12d
0x140033ce6  mov     dword ptr [rsp+180h+var_148], edi
0x140033cea  mov     rax, [rbp+80h+bstrString]
0x140033cee  mov     [rsp+180h+var_150], rax; char *
0x140033cf3  lea     rax, aValidateRevisi; "Validate Revision completes for Environ"...
0x140033cfa  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033cff  mov     [rsp+180h+lpString2], 0
0x140033d08  mov     r13d, 4
0x140033d0e  mov     r9d, r13d
0x140033d11  mov     r8d, r13d
0x140033d14  xor     edx, edx
0x140033d16  xor     ecx, ecx
0x140033d18  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033d1d  test    r14b, r14b
0x140033d20  jz      short loc_140033D6C
0x140033d22  lea     rax, aSendSlsDiscove; "Send SLS Discovery Revision Check[Old] "...
0x140033d29  mov     qword ptr [rsp+180h+cchCount2], rax
0x140033d2e  mov     [rsp+180h+lpString2], 0
0x140033d37  mov     r9d, r13d
0x140033d3a  mov     r8d, r13d
0x140033d3d  xor     edx, edx
0x140033d3f  xor     ecx, ecx
0x140033d41  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033d46  mov     rax, [rsp+180h+var_108]
0x140033d4b  movaps  xmm0, xmmword ptr [rax]
0x140033d4e  movdqa  xmmword ptr [rbp+80h+var_E0.Data1], xmm0
0x140033d53  mov     r8d, esi; int
0x140033d56  mov     rdx, [rbp+80h+var_100]
0x140033d5a  mov     rdx, [rdx+10h]; wchar_t *
0x140033d5e  lea     rcx, [rbp+80h+var_E0]; struct _GUID
0x140033d62  call    ?SendOldButValidRevisionDetectedEvent@DiscoveryEvent@telemetry@sls@@SAXU_GUID@@PEB_WJPEBD@Z; sls::telemetry::DiscoveryEvent::SendOldButValidRevisionDetectedEvent(_GUID,wchar_t const *,long,char const *)
0x140033d67  jmp     loc_140033DF0
0x140033d6c  test    r15b, r15b
0x140033d6f  jz      short loc_140033DF0
0x140033d71  lea     rax, aSendSlsDiscove_1; "Send SLS Discovery Revision Check[Inval"...
0x140033d78  mov     qword ptr [rsp+180h+cchCount2], rax; int
0x140033d7d  mov     [rsp+180h+lpString2], 0
0x140033d86  mov     r9d, r13d
0x140033d89  mov     r8d, r13d
0x140033d8c  xor     edx, edx
  ... truncated ...
```
