# CImageClassifier::Initialize(void)

- ea: `0x1800e46f0`
- end: `0x1800e4b5d`
- name: `?Initialize@CImageClassifier@@QEAAJXZ`
- size: `1133`
- prototype: `__int64 __fastcall(CImageClassifier *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4420`

## callees

- `0x180001f84`
- `0x18000202c`
- `0x180004378`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007cf90`
- `0x18007f6b0`
- `0x1800e46a4`
- `0x1800e46f0`
- `0x1800e4ebc`
- `0x1800e7338`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e48d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e48d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e49b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e49b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e4897`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e4897`

## string_xrefs

- `0x1800e4889`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Classifier`
- `0x1800e4727`: `Fail to create forced reencode BA`
- `0x1800e47a9`: `m_openedBands.Initialize failed`
- `0x1800e4a6f`: `CBatchClassifier::Create failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImageClassifier::Initialize(CImageClassifier *this)
{
  int Instance; // edi
  int v3; // r8d
  int v4; // r9d
  int v5; // ecx
  HKEY *v6; // rax
  char *v7; // rdx
  HKEY *p_hKey; // rax
  LSTATUS Value; // esi
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  const char *v13; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CBlockTypeClassifier *v15; // rax
  CBlockTypeClassifier *v16; // rax
  unsigned int v17; // eax
  const char *v18; // rax
  unsigned int v19; // eax
  const char **v21; // [rsp+30h] [rbp-48h]
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  const char *v23; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+60h] [rbp-18h] BYREF
  CBlockTypeClassifier *Type; // [rsp+B0h] [rbp+38h] BYREF
  const char *Data; // [rsp+B8h] [rbp+40h] BYREF
  const char *cbData; // [rsp+C0h] [rbp+48h] BYREF
  const char *v28; // [rsp+C8h] [rbp+50h] BYREF

  Instance = RgnlibBA_CreateInstance((char *)this + 24376);
  if ( Instance >= 0 )
  {
    if ( (unsigned __int8)FixedList<HBand>::Initialize((char *)this + 344) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(Type) = *((_DWORD *)this + 6);
        Data = "Image classification method";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)byte_180280B5D,
          v3,
          v4,
          (__int64)&Data,
          (__int64)&Type);
      }
      if ( (unsigned int)(*((_DWORD *)this + 6) - 6) <= 1 )
      {
        hKey = 0;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Classifier",
                0,
                0x20019u,
                &hKey) )
        {
          LODWORD(Type) = 0;
          LODWORD(Data) = 0;
          LODWORD(cbData) = 4;
          Value = RegQueryValueExW(hKey, L"ClassifierBatchClassify", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData);
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
                &WPP_db16d46b7da534bb368dbfabc71a6145_Traceguids,
                CurrentThreadActivityIdPrefix,
                Value);
            }
          }
          else
          {
            v12 = (int)Data;
            *((_DWORD *)this + 84) = (_DWORD)Data != 0;
            *((_DWORD *)this + 85) = v12;
            if ( (unsigned int)CallbackContext > 4 )
            {
              v13 = "Fixed";
              if ( *((_DWORD *)this + 85) != 1 )
                v13 = "Variable";
              v23 = v13;
              LODWORD(v28) = *((_DWORD *)this + 84);
              v24[0] = "Use Batch Classification on NN/CNN";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (unsigned int)"Variable",
                (unsigned int)byte_180280B0D,
                v10,
                v11,
                (__int64)v24,
                (__int64)&v28,
                (__int64)&v23);
            }
          }
          RegCloseKey(hKey);
        }
      }
      else
      {
        *((_DWORD *)this + 84) = 0;
      }
      v15 = (CBlockTypeClassifier *)operator new(0xC28u);
      Type = v15;
      if ( v15 )
        v16 = CBlockTypeClassifier::CBlockTypeClassifier(v15, (CImageClassifier *)((char *)this + 44));
      else
        v16 = 0;
      *((_QWORD *)this + 10) = v16;
      if ( !v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            (unsigned int)&WPP_db16d46b7da534bb368dbfabc71a6145_Traceguids,
            v17,
            (__int64)"CBlockTypeClassifier");
        }
        return (unsigned int)-2147024882;
      }
      if ( *((_DWORD *)this + 84)
        && (Instance = CBatchClassifier::Create(
                         *((_DWORD *)this + 85) == 1,
                         (struct CBatchClassifier **)this + 11,
                         v3,
                         v4),
            Instance < 0) )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          return (unsigned int)Instance;
        cbData = "CBatchClassifier::Create failed!";
        v28 = "Initialize";
        LODWORD(Type) = 169;
        v24[0] = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\imgclassifier.cpp";
        v18 = "Error HResult failed";
        v7 = &byte_180280AB7;
      }
      else
      {
        v19 = *((_DWORD *)this + 7);
        if ( v19 > 0x32 )
        {
          *((_DWORD *)this + 7) = 0;
          LOWORD(v19) = 0;
        }
        *((_WORD *)this + 166) = v19;
        if ( (_WORD)v19 )
          return (unsigned int)Instance;
        Instance = -2147467259;
        if ( (unsigned int)CallbackContext <= 2 )
          return (unsigned int)Instance;
        cbData = "Feature vector size is not valid.";
        v28 = "Initialize";
        LODWORD(Type) = 175;
        v24[0] = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\imgclassifier.cpp";
        v18 = "Error condition failed";
        v7 = byte_180280A61;
      }
      v23 = v18;
      v6 = (HKEY *)v24;
      goto LABEL_42;
    }
    Instance = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = "m_openedBands.Initialize failed";
      v28 = "Initialize";
      LODWORD(Type) = 113;
      v23 = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\imgclassifier.cpp";
      hKey = (HKEY)"Error condition failed";
      v21 = &v23;
      p_hKey = &hKey;
      v7 = byte_180280B9D;
LABEL_43:
      LODWORD(Data) = Instance;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (_DWORD)v7,
        v3,
        v4,
        (__int64)p_hKey,
        (__int64)&Data,
        (__int64)v21,
        (__int64)&Type,
        (__int64)&v28,
        (__int64)&cbData);
    }
  }
  else
  {
    v5 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = "Fail to create forced reencode BA";
      v28 = "Initialize";
      LODWORD(Type) = 110;
      hKey = (HKEY)"onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\imgclassifier.cpp";
      v23 = "Error HResult failed";
      v6 = &hKey;
      v7 = byte_180280BF3;
LABEL_42:
      v21 = (const char **)v6;
      p_hKey = (HKEY *)&v23;
      goto LABEL_43;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e46f0  push    rbp
0x1800e46f2  push    rbx
0x1800e46f3  push    rsi
0x1800e46f4  push    rdi
0x1800e46f5  push    r12
0x1800e46f7  push    r14
0x1800e46f9  mov     rbp, rsp
0x1800e46fc  sub     rsp, 78h
0x1800e4700  mov     rbx, rcx
0x1800e4703  add     rcx, 5F38h
0x1800e470a  call    RgnlibBA_CreateInstance
0x1800e470f  mov     edi, eax
0x1800e4711  xor     r14d, r14d
0x1800e4714  test    eax, eax
0x1800e4716  jns     short loc_1800E4785
0x1800e4718  mov     ecx, cs:CallbackContext
0x1800e471e  cmp     ecx, 2
0x1800e4721  jbe     loc_1800E4B4E
0x1800e4727  lea     rax, aFailToCreateFo; "Fail to create forced reencode BA"
0x1800e472e  mov     [rbp+cbData], rax
0x1800e4732  lea     rax, aInitialize; "Initialize"
0x1800e4739  mov     [rbp+arg_18], rax
0x1800e473d  mov     dword ptr [rbp+Type], 6Eh ; 'n'
0x1800e4744  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e474b  mov     [rbp+hKey], rax
0x1800e474f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e4756  mov     [rbp+var_20], rax
0x1800e475a  lea     rax, [rbp+cbData]
0x1800e475e  mov     [rsp+78h+var_30], rax
0x1800e4763  lea     rax, [rbp+arg_18]
0x1800e4767  mov     [rsp+78h+var_38], rax
0x1800e476c  lea     rax, [rbp+Type]
0x1800e4770  mov     [rsp+78h+var_40], rax
0x1800e4775  lea     rax, [rbp+hKey]
0x1800e4779  lea     rdx, byte_180280BF3
0x1800e4780  jmp     loc_1800E4B2F
0x1800e4785  lea     rcx, [rbx+158h]
0x1800e478c  call    ?Initialize@?$FixedList@UHBand@@@@QEAA_NH@Z; FixedList<HBand>::Initialize(int)
0x1800e4791  test    al, al
0x1800e4793  mov     eax, cs:CallbackContext
0x1800e4799  jnz     short loc_1800E4819
0x1800e479b  mov     edi, 8007000Eh
0x1800e47a0  cmp     eax, 2
0x1800e47a3  jbe     loc_1800E4B4E
0x1800e47a9  lea     rax, aMOpenedbandsIn; "m_openedBands.Initialize failed"
0x1800e47b0  mov     [rbp+cbData], rax
0x1800e47b4  lea     rax, aInitialize; "Initialize"
0x1800e47bb  mov     [rbp+arg_18], rax
0x1800e47bf  mov     dword ptr [rbp+Type], 71h ; 'q'
0x1800e47c6  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e47cd  mov     [rbp+var_20], rax
0x1800e47d1  lea     rax, aErrorCondition; "Error condition failed"
0x1800e47d8  mov     [rbp+hKey], rax
0x1800e47dc  lea     rax, [rbp+cbData]
0x1800e47e0  mov     [rsp+78h+var_30], rax
0x1800e47e5  lea     rax, [rbp+arg_18]
0x1800e47e9  mov     [rsp+78h+var_38], rax
0x1800e47ee  lea     rax, [rbp+Type]
0x1800e47f2  mov     [rsp+78h+var_40], rax
0x1800e47f7  lea     rax, [rbp+var_20]
0x1800e47fb  mov     [rsp+78h+var_48], rax
0x1800e4800  lea     rax, [rbp+Data]
0x1800e4804  mov     [rsp+78h+lpcbData], rax
0x1800e4809  lea     rax, [rbp+hKey]
0x1800e480d  lea     rdx, byte_180280B9D
0x1800e4814  jmp     loc_1800E4B41
0x1800e4819  cmp     eax, 4
0x1800e481c  jbe     short loc_1800E4852
0x1800e481e  lea     rsi, [rbx+18h]
0x1800e4822  mov     eax, [rsi]
0x1800e4824  mov     dword ptr [rbp+Type], eax
0x1800e4827  lea     rax, aImageClassific; "Image classification method"
0x1800e482e  mov     [rbp+Data], rax
0x1800e4832  lea     rax, [rbp+Type]
0x1800e4836  mov     [rsp+78h+lpcbData], rax
0x1800e483b  lea     rax, [rbp+Data]
0x1800e483f  mov     [rsp+78h+phkResult], rax
0x1800e4844  lea     rdx, byte_180280B5D
0x1800e484b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800e4850  jmp     short loc_1800E4856
0x1800e4852  lea     rsi, [rbx+18h]
0x1800e4856  mov     eax, [rsi]
0x1800e4858  sub     eax, 6
0x1800e485b  lea     r12, WPP_GLOBAL_Control
0x1800e4862  cmp     eax, 1
0x1800e4865  jbe     short loc_1800E4873
0x1800e4867  mov     [rbx+150h], r14d
0x1800e486e  jmp     loc_1800E49BF
0x1800e4873  mov     [rbp+hKey], r14
0x1800e4877  lea     rax, [rbp+hKey]
0x1800e487b  mov     [rsp+78h+phkResult], rax; phkResult
0x1800e4880  mov     r9d, 20019h; samDesired
0x1800e4886  xor     r8d, r8d; ulOptions
0x1800e4889  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x1800e4890  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e4897  call    cs:__imp_RegOpenKeyExW
0x1800e489d  test    eax, eax
0x1800e489f  jnz     loc_1800E49BF
0x1800e48a5  mov     dword ptr [rbp+Type], r14d
0x1800e48a9  mov     dword ptr [rbp+Data], r14d
0x1800e48ad  mov     dword ptr [rbp+cbData], 4
0x1800e48b4  lea     rax, [rbp+cbData]
0x1800e48b8  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800e48bd  lea     rax, [rbp+Data]
0x1800e48c1  mov     [rsp+78h+phkResult], rax; lpData
0x1800e48c6  lea     r9, [rbp+Type]; lpType
0x1800e48ca  xor     r8d, r8d; lpReserved
0x1800e48cd  lea     rdx, aClassifierbatc; "ClassifierBatchClassify"
0x1800e48d4  mov     rcx, [rbp+hKey]; hKey
0x1800e48d8  call    cs:__imp_RegQueryValueExW
0x1800e48de  mov     esi, eax
0x1800e48e0  test    eax, eax
0x1800e48e2  jnz     loc_1800E4972
0x1800e48e8  cmp     dword ptr [rbp+Type], 4
0x1800e48ec  jnz     loc_1800E4972
0x1800e48f2  mov     eax, r14d
0x1800e48f5  mov     ecx, dword ptr [rbp+Data]
0x1800e48f8  test    ecx, ecx
0x1800e48fa  setnz   al
0x1800e48fd  mov     [rbx+150h], eax
0x1800e4903  mov     [rbx+154h], ecx
0x1800e4909  mov     eax, cs:CallbackContext
0x1800e490f  cmp     eax, 4
0x1800e4912  jbe     loc_1800E49B5
0x1800e4918  lea     rcx, aVariable; "Variable"
0x1800e491f  lea     rax, aFixed; "Fixed"
0x1800e4926  cmp     dword ptr [rbx+154h], 1
0x1800e492d  cmovnz  rax, rcx
0x1800e4931  mov     [rbp+var_20], rax
0x1800e4935  mov     eax, [rbx+150h]
0x1800e493b  mov     dword ptr [rbp+arg_18], eax
0x1800e493e  lea     rax, aUseBatchClassi; "Use Batch Classification on NN/CNN"
0x1800e4945  mov     [rbp+var_18], rax
0x1800e4949  lea     rax, [rbp+var_20]
0x1800e494d  mov     [rsp+78h+var_48], rax
0x1800e4952  lea     rax, [rbp+arg_18]
0x1800e4956  mov     [rsp+78h+lpcbData], rax
0x1800e495b  lea     rax, [rbp+var_18]
0x1800e495f  mov     [rsp+78h+phkResult], rax
0x1800e4964  lea     rdx, byte_180280B0D
0x1800e496b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800e4970  jmp     short loc_1800E49B5
0x1800e4972  mov     rax, cs:WPP_GLOBAL_Control
0x1800e4979  cmp     rax, r12
0x1800e497c  jz      short loc_1800E49B5
0x1800e497e  test    dword ptr [rax+1Ch], 100h
0x1800e4985  jz      short loc_1800E49B5
0x1800e4987  cmp     byte ptr [rax+19h], 3
0x1800e498b  jb      short loc_1800E49B5
0x1800e498d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e4992  mov     edx, 0Ah
0x1800e4997  mov     dword ptr [rsp+78h+phkResult], esi
0x1800e499b  mov     r9d, eax
0x1800e499e  lea     r8, WPP_db16d46b7da534bb368dbfabc71a6145_Traceguids
0x1800e49a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e49ac  mov     rcx, [rcx+10h]
0x1800e49b0  call    WPP_SF_Dd
0x1800e49b5  mov     rcx, [rbp+hKey]; hKey
0x1800e49b9  call    cs:__imp_RegCloseKey
0x1800e49bf  mov     ecx, 0C28h; Size
0x1800e49c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e49c9  mov     [rbp+Type], rax
0x1800e49cd  test    rax, rax
0x1800e49d0  jz      short loc_1800E49E0
0x1800e49d2  lea     rdx, [rbx+2Ch]; struct BlockClassificationSettings *
0x1800e49d6  mov     rcx, rax; this
0x1800e49d9  call    ??0CBlockTypeClassifier@@QEAA@AEAUBlockClassificationSettings@@@Z; CBlockTypeClassifier::CBlockTypeClassifier(BlockClassificationSettings &)
0x1800e49de  jmp     short loc_1800E49E3
0x1800e49e0  mov     rax, r14
0x1800e49e3  mov     [rbx+50h], rax
0x1800e49e7  test    rax, rax
0x1800e49ea  jnz     short loc_1800E4A3E
0x1800e49ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800e49f3  cmp     rax, r12
0x1800e49f6  jz      short loc_1800E4A34
0x1800e49f8  test    byte ptr [rax+1Ch], 8
0x1800e49fc  jz      short loc_1800E4A34
0x1800e49fe  cmp     byte ptr [rax+19h], 2
0x1800e4a02  jb      short loc_1800E4A34
0x1800e4a04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e4a09  mov     edx, 0Bh
0x1800e4a0e  lea     rcx, aCblocktypeclas_1; "CBlockTypeClassifier"
0x1800e4a15  mov     [rsp+78h+phkResult], rcx
0x1800e4a1a  mov     r9d, eax
0x1800e4a1d  lea     r8, WPP_db16d46b7da534bb368dbfabc71a6145_Traceguids
0x1800e4a24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4a2b  mov     rcx, [rcx+10h]
0x1800e4a2f  call    WPP_SF_Ds
0x1800e4a34  mov     edi, 8007000Eh
0x1800e4a39  jmp     loc_1800E4B4E
0x1800e4a3e  cmp     [rbx+150h], r14d
0x1800e4a45  jz      short loc_1800E4AA7
0x1800e4a47  lea     rdx, [rbx+58h]; struct CBatchClassifier **
0x1800e4a4b  cmp     dword ptr [rbx+154h], 1
0x1800e4a52  setz    cl; bool
0x1800e4a55  call    ?Create@CBatchClassifier@@SAJ_NPEAPEAV1@@Z; CBatchClassifier::Create(bool,CBatchClassifier * *)
0x1800e4a5a  mov     edi, eax
0x1800e4a5c  test    eax, eax
0x1800e4a5e  jns     short loc_1800E4AA7
0x1800e4a60  mov     eax, cs:CallbackContext
0x1800e4a66  cmp     eax, 2
0x1800e4a69  jbe     loc_1800E4B4E
0x1800e4a6f  lea     rax, aCbatchclassifi_0; "CBatchClassifier::Create failed!"
0x1800e4a76  mov     [rbp+cbData], rax
0x1800e4a7a  lea     rax, aInitialize; "Initialize"
0x1800e4a81  mov     [rbp+arg_18], rax
0x1800e4a85  mov     dword ptr [rbp+Type], 0A9h
0x1800e4a8c  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e4a93  mov     [rbp+var_18], rax
0x1800e4a97  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e4a9e  lea     rdx, byte_180280AB7
0x1800e4aa5  jmp     short loc_1800E4B0C
0x1800e4aa7  mov     eax, [rbx+1Ch]
0x1800e4aaa  cmp     eax, 32h ; '2'
0x1800e4aad  jbe     short loc_1800E4AB6
0x1800e4aaf  mov     [rbx+1Ch], r14d
0x1800e4ab3  mov     eax, r14d
0x1800e4ab6  mov     [rbx+14Ch], ax
0x1800e4abd  test    ax, ax
0x1800e4ac0  jnz     loc_1800E4B4E
0x1800e4ac6  mov     edi, 80004005h
0x1800e4acb  mov     eax, cs:CallbackContext
0x1800e4ad1  cmp     eax, 2
0x1800e4ad4  jbe     short loc_1800E4B4E
0x1800e4ad6  lea     rax, aFeatureVectorS; "Feature vector size is not valid."
0x1800e4add  mov     [rbp+cbData], rax
0x1800e4ae1  lea     rax, aInitialize; "Initialize"
0x1800e4ae8  mov     [rbp+arg_18], rax
0x1800e4aec  mov     dword ptr [rbp+Type], 0AFh
0x1800e4af3  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800e4afa  mov     [rbp+var_18], rax
0x1800e4afe  lea     rax, aErrorCondition; "Error condition failed"
0x1800e4b05  lea     rdx, byte_180280A61
0x1800e4b0c  mov     [rbp+var_20], rax
0x1800e4b10  lea     rax, [rbp+cbData]
0x1800e4b14  mov     [rsp+78h+var_30], rax
0x1800e4b19  lea     rax, [rbp+arg_18]
0x1800e4b1d  mov     [rsp+78h+var_38], rax
0x1800e4b22  lea     rax, [rbp+Type]
0x1800e4b26  mov     [rsp+78h+var_40], rax
0x1800e4b2b  lea     rax, [rbp+var_18]
0x1800e4b2f  mov     [rsp+78h+var_48], rax
0x1800e4b34  lea     rax, [rbp+Data]
0x1800e4b38  mov     [rsp+78h+lpcbData], rax
0x1800e4b3d  lea     rax, [rbp+var_20]
0x1800e4b41  mov     [rsp+78h+phkResult], rax
0x1800e4b46  mov     dword ptr [rbp+Data], edi
0x1800e4b49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e4b4e  mov     eax, edi
0x1800e4b50  add     rsp, 78h
0x1800e4b54  pop     r14
0x1800e4b56  pop     r12
0x1800e4b58  pop     rdi
0x1800e4b59  pop     rsi
0x1800e4b5a  pop     rbx
0x1800e4b5b  pop     rbp
0x1800e4b5c  retn
```
