# CBatchClassifier::Create(bool,CBatchClassifier * *)

- ea: `0x1800e7338`
- end: `0x1800e7649`
- name: `?Create@CBatchClassifier@@SAJ_NPEAPEAV1@@Z`
- size: `785`
- prototype: `static int(bool, struct CBatchClassifier **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e46f0`

## callees

- `0x180001f84`
- `0x18000202c`
- `0x180079724`
- `0x180079770`
- `0x18007f6b0`
- `0x1800e7120`
- `0x1800e7338`
- `0x1800e7ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e7456`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e7456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e74f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e74f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e7417`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e7417`

## string_xrefs

- `0x1800e7409`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Classifier`
- `0x1800e7376`: `Create`
- `0x1800e754e`: `Create`
- `0x1800e75d4`: `Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBatchClassifier::Create(char a1, struct CBatchClassifier **a2, int a3, int a4)
{
  bool v5; // di
  unsigned int v6; // ebx
  const char **v7; // rax
  __int16 *v8; // rdx
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  LSTATUS Value; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CBatchClassifier *v15; // rax
  CBatchClassifier *v16; // rdi
  HKEY *p_hKey; // [rsp+30h] [rbp-40h]
  HKEY *v19; // [rsp+40h] [rbp-30h]
  const char *v20; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+60h] [rbp-10h] BYREF
  CBatchClassifier *Type; // [rsp+A8h] [rbp+38h] BYREF
  unsigned int Data; // [rsp+B0h] [rbp+40h] BYREF
  const char *cbData; // [rsp+B8h] [rbp+48h] BYREF

  v5 = a1;
  if ( a2 )
  {
    v9 = 0;
    if ( a1 )
    {
      hKey = 0;
      v9 = 300;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Classifier",
              0,
              0x20019u,
              &hKey) )
      {
        LODWORD(Type) = 0;
        Data = 0;
        LODWORD(cbData) = 4;
        Value = RegQueryValueExW(hKey, L"FixedBatchSize", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData);
        if ( Value || (_DWORD)Type != 4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_6e18298510fc3efe305f69750689aa3f_Traceguids,
              CurrentThreadActivityIdPrefix,
              Value);
          }
        }
        else
        {
          v9 = Data;
          if ( (unsigned int)CallbackContext > 4 )
          {
            LODWORD(v20) = Data;
            v22[0] = "Use Fixed Batch Size for NN Batch Classification";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v10,
              (unsigned int)&word_1802817CE,
              v11,
              v12,
              (__int64)v22,
              (__int64)&v20);
          }
        }
        RegCloseKey(hKey);
      }
    }
    v15 = (CBatchClassifier *)operator new(0x50u);
    Type = v15;
    if ( v15 )
      v16 = CBatchClassifier::CBatchClassifier(v15, v5, v9);
    else
      v16 = 0;
    if ( !v16 )
    {
      v6 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        return v6;
      cbData = "CBatchClassifier alloc failed";
      v22[0] = "Create";
      LODWORD(Type) = 80;
      hKey = (HKEY)"onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\batchclassifier.cpp";
      v20 = "Error condition failed";
      v19 = (HKEY *)v22;
      p_hKey = &hKey;
      v7 = &v20;
      v8 = (__int16 *)&unk_180281778;
      goto LABEL_4;
    }
    v6 = CBatchClassifier::InitializeInstance(v16);
    if ( (v6 & 0x80000000) == 0 )
    {
      *a2 = v16;
      return v6;
    }
    a1 = (char)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = "pBatchClassifier->InitializeInstance() failed";
      v22[0] = "Create";
      LODWORD(Type) = 83;
      hKey = (HKEY)"onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\batchclassifier.cpp";
      v20 = "Error HResult failed";
      v19 = (HKEY *)v22;
      p_hKey = &hKey;
      v7 = &v20;
      v8 = word_180281722;
      goto LABEL_4;
    }
  }
  else
  {
    v6 = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = "Invalid pObjOut argument";
      hKey = (HKEY)"Create";
      LODWORD(Type) = 38;
      v20 = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\batchclassifier.cpp";
      v22[0] = "Error condition failed";
      v19 = &hKey;
      p_hKey = (HKEY *)&v20;
      v7 = (const char **)v22;
      v8 = (__int16 *)&unk_180281808;
LABEL_4:
      Data = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        a1,
        (_DWORD)v8,
        a3,
        a4,
        (__int64)v7,
        (__int64)&Data,
        (__int64)p_hKey,
        (__int64)&Type,
        (__int64)v19,
        (__int64)&cbData);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800e7338  mov     r11, rsp
0x1800e733b  push    rbp
0x1800e733c  push    rbx
0x1800e733d  push    rsi
0x1800e733e  push    rdi
0x1800e733f  push    r14
0x1800e7341  mov     rbp, rsp
0x1800e7344  sub     rsp, 70h
0x1800e7348  mov     rsi, rdx
0x1800e734b  mov     dil, cl
0x1800e734e  test    rdx, rdx
0x1800e7351  jnz     loc_1800E73E3
0x1800e7357  mov     ebx, 80070057h
0x1800e735c  mov     eax, cs:CallbackContext
0x1800e7362  cmp     eax, 2
0x1800e7365  jbe     loc_1800E763C
0x1800e736b  lea     rax, aInvalidPobjout; "Invalid pObjOut argument"
0x1800e7372  mov     [rbp+cbData], rax
0x1800e7376  lea     rax, aCreate; "Create"
0x1800e737d  mov     [rbp+hKey], rax
0x1800e7381  mov     dword ptr [rbp+Type], 26h ; '&'
0x1800e7388  lea     rax, aOnecoreTermsrv_25; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e738f  mov     [rbp+var_20], rax
0x1800e7393  lea     rax, aErrorCondition; "Error condition failed"
0x1800e739a  mov     [rbp+var_10], rax
0x1800e739e  lea     rax, [rbp+cbData]
0x1800e73a2  mov     [r11-50h], rax
0x1800e73a6  lea     rax, [rbp+hKey]
0x1800e73aa  mov     [r11-58h], rax
0x1800e73ae  lea     rax, [rbp+Type]
0x1800e73b2  mov     [r11-60h], rax
0x1800e73b6  lea     rax, [rbp+var_20]
0x1800e73ba  mov     [r11-68h], rax
0x1800e73be  lea     rax, [rbp+Data]
0x1800e73c2  mov     [r11-70h], rax
0x1800e73c6  lea     rax, [rbp+var_10]
0x1800e73ca  lea     rdx, unk_180281808
0x1800e73d1  mov     [rbp+Data], ebx
0x1800e73d4  mov     [rsp+70h+phkResult], rax
0x1800e73d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e73de  jmp     loc_1800E763C
0x1800e73e3  xor     ebx, ebx
0x1800e73e5  test    dil, dil
0x1800e73e8  jz      loc_1800E74FA
0x1800e73ee  mov     [rbp+hKey], rbx
0x1800e73f2  mov     ebx, 12Ch
0x1800e73f7  lea     rax, [rbp+hKey]
0x1800e73fb  mov     [rsp+70h+phkResult], rax; phkResult
0x1800e7400  mov     r9d, 20019h; samDesired
0x1800e7406  xor     r8d, r8d; ulOptions
0x1800e7409  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x1800e7410  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e7417  call    cs:__imp_RegOpenKeyExW
0x1800e741d  test    eax, eax
0x1800e741f  jnz     loc_1800E74FA
0x1800e7425  mov     dword ptr [rbp+Type], eax
0x1800e7428  mov     [rbp+Data], eax
0x1800e742b  mov     dword ptr [rbp+cbData], 4
0x1800e7432  lea     rax, [rbp+cbData]
0x1800e7436  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800e743b  lea     rax, [rbp+Data]
0x1800e743f  mov     [rsp+70h+phkResult], rax; lpData
0x1800e7444  lea     r9, [rbp+Type]; lpType
0x1800e7448  xor     r8d, r8d; lpReserved
0x1800e744b  lea     rdx, aFixedbatchsize; "FixedBatchSize"
0x1800e7452  mov     rcx, [rbp+hKey]; hKey
0x1800e7456  call    cs:__imp_RegQueryValueExW
0x1800e745c  mov     r14d, eax
0x1800e745f  test    eax, eax
0x1800e7461  jnz     short loc_1800E74A5
0x1800e7463  cmp     dword ptr [rbp+Type], 4
0x1800e7467  jnz     short loc_1800E74A5
0x1800e7469  mov     ebx, [rbp+Data]
0x1800e746c  mov     eax, cs:CallbackContext
0x1800e7472  cmp     eax, 4
0x1800e7475  jbe     short loc_1800E74F0
0x1800e7477  mov     dword ptr [rbp+var_20], ebx
0x1800e747a  lea     rax, aUseFixedBatchS; "Use Fixed Batch Size for NN Batch Class"...
0x1800e7481  mov     [rbp+var_10], rax
0x1800e7485  lea     rax, [rbp+var_20]
0x1800e7489  mov     [rsp+70h+lpcbData], rax
0x1800e748e  lea     rax, [rbp+var_10]
0x1800e7492  mov     [rsp+70h+phkResult], rax
0x1800e7497  lea     rdx, word_1802817CE
0x1800e749e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800e74a3  jmp     short loc_1800E74F0
0x1800e74a5  lea     rcx, WPP_GLOBAL_Control
0x1800e74ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800e74b3  cmp     rax, rcx
0x1800e74b6  jz      short loc_1800E74F0
0x1800e74b8  test    dword ptr [rax+1Ch], 100h
0x1800e74bf  jz      short loc_1800E74F0
0x1800e74c1  cmp     byte ptr [rax+19h], 3
0x1800e74c5  jb      short loc_1800E74F0
0x1800e74c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e74cc  mov     edx, 0Ah
0x1800e74d1  mov     dword ptr [rsp+70h+phkResult], r14d
0x1800e74d6  mov     r9d, eax
0x1800e74d9  lea     r8, WPP_6e18298510fc3efe305f69750689aa3f_Traceguids
0x1800e74e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e74e7  mov     rcx, [rcx+10h]
0x1800e74eb  call    WPP_SF_Dd
0x1800e74f0  mov     rcx, [rbp+hKey]; hKey
0x1800e74f4  call    cs:__imp_RegCloseKey
0x1800e74fa  mov     r14d, 50h ; 'P'
0x1800e7500  mov     ecx, r14d; Size
0x1800e7503  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e7508  mov     [rbp+Type], rax
0x1800e750c  test    rax, rax
0x1800e750f  jz      short loc_1800E7524
0x1800e7511  mov     r8d, ebx; unsigned int
0x1800e7514  mov     dl, dil; bool
0x1800e7517  mov     rcx, rax; this
0x1800e751a  call    ??0CBatchClassifier@@QEAA@_NI@Z; CBatchClassifier::CBatchClassifier(bool,uint)
0x1800e751f  mov     rdi, rax
0x1800e7522  jmp     short loc_1800E7526
0x1800e7524  xor     edi, edi
0x1800e7526  test    rdi, rdi
0x1800e7529  jnz     loc_1800E75B0
0x1800e752f  mov     ebx, 8007000Eh
0x1800e7534  mov     eax, cs:CallbackContext
0x1800e753a  cmp     eax, 2
0x1800e753d  jbe     loc_1800E763C
0x1800e7543  lea     rax, aCbatchclassifi; "CBatchClassifier alloc failed"
0x1800e754a  mov     [rbp+cbData], rax
0x1800e754e  lea     rax, aCreate; "Create"
0x1800e7555  mov     [rbp+var_10], rax
0x1800e7559  mov     dword ptr [rbp+Type], r14d
0x1800e755d  lea     rax, aOnecoreTermsrv_25; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e7564  mov     [rbp+hKey], rax
0x1800e7568  lea     rax, aErrorCondition; "Error condition failed"
0x1800e756f  mov     [rbp+var_20], rax
0x1800e7573  lea     rax, [rbp+cbData]
0x1800e7577  mov     [rsp+70h+var_28], rax
0x1800e757c  lea     rax, [rbp+var_10]
0x1800e7580  mov     [rsp+70h+var_30], rax
0x1800e7585  lea     rax, [rbp+Type]
0x1800e7589  mov     [rsp+70h+var_38], rax
0x1800e758e  lea     rax, [rbp+hKey]
0x1800e7592  mov     [rsp+70h+var_40], rax
0x1800e7597  lea     rax, [rbp+Data]
0x1800e759b  mov     [rsp+70h+lpcbData], rax
0x1800e75a0  lea     rax, [rbp+var_20]
0x1800e75a4  lea     rdx, unk_180281778
0x1800e75ab  jmp     loc_1800E73D1
0x1800e75b0  mov     rcx, rdi; this
0x1800e75b3  call    ?InitializeInstance@CBatchClassifier@@AEAAJXZ; CBatchClassifier::InitializeInstance(void)
0x1800e75b8  mov     ebx, eax
0x1800e75ba  test    eax, eax
0x1800e75bc  jns     short loc_1800E7639
0x1800e75be  mov     ecx, cs:CallbackContext
0x1800e75c4  cmp     ecx, 2
0x1800e75c7  jbe     short loc_1800E763C
0x1800e75c9  lea     rax, aPbatchclassifi; "pBatchClassifier->InitializeInstance() "...
0x1800e75d0  mov     [rbp+cbData], rax
0x1800e75d4  lea     rax, aCreate; "Create"
0x1800e75db  mov     [rbp+var_10], rax
0x1800e75df  mov     dword ptr [rbp+Type], 53h ; 'S'
0x1800e75e6  lea     rax, aOnecoreTermsrv_25; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e75ed  mov     [rbp+hKey], rax
0x1800e75f1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e75f8  mov     [rbp+var_20], rax
0x1800e75fc  lea     rax, [rbp+cbData]
0x1800e7600  mov     [rsp+70h+var_28], rax
0x1800e7605  lea     rax, [rbp+var_10]
0x1800e7609  mov     [rsp+70h+var_30], rax
0x1800e760e  lea     rax, [rbp+Type]
0x1800e7612  mov     [rsp+70h+var_38], rax
0x1800e7617  lea     rax, [rbp+hKey]
0x1800e761b  mov     [rsp+70h+var_40], rax
0x1800e7620  lea     rax, [rbp+Data]
0x1800e7624  mov     [rsp+70h+lpcbData], rax
0x1800e7629  lea     rax, [rbp+var_20]
0x1800e762d  lea     rdx, word_180281722
0x1800e7634  jmp     loc_1800E73D1
0x1800e7639  mov     [rsi], rdi
0x1800e763c  mov     eax, ebx
0x1800e763e  add     rsp, 70h
0x1800e7642  pop     r14
0x1800e7644  pop     rdi
0x1800e7645  pop     rsi
0x1800e7646  pop     rbx
0x1800e7647  pop     rbp
0x1800e7648  retn
```
