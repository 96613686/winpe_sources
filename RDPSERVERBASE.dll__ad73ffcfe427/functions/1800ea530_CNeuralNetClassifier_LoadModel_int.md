# CNeuralNetClassifier::LoadModel(int)

- ea: `0x1800ea530`
- end: `0x1800ea907`
- name: `?LoadModel@CNeuralNetClassifier@@EEAAJH@Z`
- size: `983`
- prototype: `__int64 __fastcall(CNeuralNetClassifier *__hidden this, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001764`
- `0x180001f84`
- `0x18000202c`
- `0x180077994`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f6b0`
- `0x1800e9fa0`
- `0x1800ea530`
- `0x1800eacd4`

## import_xrefs

- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x1800ea6ad`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x1800ea7ff`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x1800ea6ad`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x1800ea7ff`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x1800ea6b6`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x1800ea808`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x1800ea6b6`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x1800ea808`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ea5ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ea5ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ea6a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ea6a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ea588`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ea588`

## string_xrefs

- `0x1800ea57b`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Classifier`
- `0x1800ea5be`: `ClassifierModelPath`

## pseudocode

```c
__int64 __fastcall CNeuralNetClassifier::LoadModel(CNeuralNetClassifier *this)
{
  unsigned __int64 v2; // rdi
  LSTATUS v3; // eax
  char v4; // si
  char v5; // bl
  unsigned int v6; // eax
  int v7; // edx
  int v8; // r8d
  const wchar_t *v9; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  int v12; // r8d
  PipelineClock *Instance; // rax
  unsigned int MillisecondCount; // esi
  _QWORD *v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  DWORD v19; // ebx
  __int16 *v20; // rdx
  const char **v21; // rax
  const char *v22; // rax
  PipelineClock *v23; // rax
  unsigned int v24; // eax
  int v25; // r8d
  int v26; // r9d
  const char **v28; // [rsp+30h] [rbp-D0h]
  const char **v29; // [rsp+40h] [rbp-C0h]
  const char **v30; // [rsp+48h] [rbp-B8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  const char *v33; // [rsp+58h] [rbp-A8h] BYREF
  const char *v34; // [rsp+60h] [rbp-A0h] BYREF
  const char *v35; // [rsp+68h] [rbp-98h] BYREF
  const char *v36; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 Data[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Classifier",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 520;
    Type = 0;
    v3 = RegQueryValueExW(hKey, L"ClassifierModelPath", 0, &Type, (LPBYTE)Data, &cbData);
    v4 = v3;
    if ( v3 || Type != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = L"REG_SZ";
        if ( Type != 1 )
          v9 = L"not sz";
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DdS(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, CurrentThreadActivityIdPrefix, v4, (__int64)v9);
      }
    }
    else
    {
      v2 = -1;
      do
        ++v2;
      while ( Data[v2] );
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v5 = cbData;
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v6, (__int64)Data, v5);
      }
    }
    RegCloseKey(hKey);
  }
  Instance = (PipelineClock *)PipelineClock::GetInstance();
  MillisecondCount = PipelineClock::GetMillisecondCount(Instance);
  v15 = operator new(8u);
  if ( v15 )
    *v15 = 0;
  else
    v15 = 0;
  *((_QWORD *)this + 7) = v15;
  if ( v15 )
  {
    if ( v2 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        cbData = v2;
        v33 = (const char *)Data;
        v34 = "Loading model file";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&dword_18028201C,
          v17,
          v18,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&cbData);
      }
      v19 = RDP::AI::MachineLearning::Details::WinMLLearningModel::Initialize(
              *((RDP::AI::MachineLearning::Details::WinMLLearningModel **)this + 7),
              Data,
              v2);
      if ( (v19 & 0x80000000) == 0 )
      {
        v23 = (PipelineClock *)PipelineClock::GetInstance();
        v24 = PipelineClock::GetMillisecondCount(v23);
        if ( (unsigned int)CallbackContext > 4 )
        {
          cbData = v24 - MillisecondCount;
          v33 = "NN model loaded";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)CallbackContext,
            (unsigned int)&dword_180281FDC,
            v25,
            v26,
            (__int64)&v33,
            (__int64)&cbData);
        }
        return v19;
      }
      v16 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        return v19;
      v22 = "m_pModel->Initialize() failed!";
      cbData = 123;
      v20 = (__int16 *)&unk_180282060;
    }
    else
    {
      v19 = -2147467263;
      if ( (unsigned int)CallbackContext <= 2 )
        return v19;
      v22 = "Loading NN Model from resource blob disabled!";
      cbData = 129;
      v20 = &word_180281F86;
    }
    v33 = v22;
    v34 = "LoadModel";
    v36 = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\nnclassifier.cpp";
    v35 = "Error HResult failed";
    v30 = &v33;
    v29 = &v34;
    v28 = &v36;
    v21 = &v35;
    goto LABEL_34;
  }
  v19 = -2147024882;
  if ( (unsigned int)CallbackContext > 2 )
  {
    cbData = 112;
    v35 = "Failed to allocate memory for m_pModel";
    v20 = (__int16 *)&dword_18028210C;
    v36 = "LoadModel";
    v34 = "onecore\\termsrv\\rdpplatform\\imganalyzers\\imgclassifier\\nnclassifier.cpp";
    v33 = "Error condition failed";
    v30 = &v35;
    v29 = &v36;
    v28 = &v34;
    v21 = &v33;
LABEL_34:
    Type = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v16,
      (_DWORD)v20,
      v17,
      v18,
      (__int64)v21,
      (__int64)&Type,
      (__int64)v28,
      (__int64)&cbData,
      (__int64)v29,
      (__int64)v30);
  }
  return v19;
}

```

## disassembly

```asm
0x1800ea530  push    rbp
0x1800ea532  push    rbx
0x1800ea533  push    rsi
0x1800ea534  push    rdi
0x1800ea535  push    r14
0x1800ea537  push    r15
0x1800ea539  lea     rbp, [rsp-1A8h]
0x1800ea541  sub     rsp, 2A8h
0x1800ea548  mov     rax, cs:__security_cookie
0x1800ea54f  xor     rax, rsp
0x1800ea552  mov     [rbp+1D0h+var_40], rax
0x1800ea559  mov     r14, rcx
0x1800ea55c  lea     rax, [rsp+2D0h+hKey]
0x1800ea561  xor     r15d, r15d
0x1800ea564  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800ea569  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ea570  mov     [rsp+2D0h+hKey], r15
0x1800ea575  mov     r9d, 20019h; samDesired
0x1800ea57b  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x1800ea582  xor     r8d, r8d; ulOptions
0x1800ea585  mov     edi, r15d
0x1800ea588  call    cs:__imp_RegOpenKeyExW
0x1800ea58e  test    eax, eax
0x1800ea590  jnz     loc_1800EA6AD
0x1800ea596  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ea59b  lea     rax, [rsp+2D0h+cbData]
0x1800ea5a0  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1800ea5a5  lea     r9, [rsp+2D0h+Type]; lpType
0x1800ea5aa  lea     rax, [rbp+1D0h+Data]
0x1800ea5ae  mov     [rsp+2D0h+cbData], 208h
0x1800ea5b6  xor     r8d, r8d; lpReserved
0x1800ea5b9  mov     [rsp+2D0h+phkResult], rax; lpData
0x1800ea5be  lea     rdx, aClassifiermode; "ClassifierModelPath"
0x1800ea5c5  mov     [rsp+2D0h+Type], r15d
0x1800ea5ca  call    cs:__imp_RegQueryValueExW
0x1800ea5d0  mov     esi, eax
0x1800ea5d2  test    eax, eax
0x1800ea5d4  jnz     short loc_1800EA648
0x1800ea5d6  cmp     [rsp+2D0h+Type], 1
0x1800ea5db  jnz     short loc_1800EA648
0x1800ea5dd  lea     rax, [rbp+1D0h+Data]
0x1800ea5e1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ea5e5  inc     rdi
0x1800ea5e8  cmp     [rax+rdi*2], r15w
0x1800ea5ed  jnz     short loc_1800EA5E5
0x1800ea5ef  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea5f6  lea     rcx, WPP_GLOBAL_Control
0x1800ea5fd  cmp     rax, rcx
0x1800ea600  jz      loc_1800EA6A2
0x1800ea606  test    dword ptr [rax+1Ch], 100h
0x1800ea60d  jz      loc_1800EA6A2
0x1800ea613  cmp     byte ptr [rax+19h], 4
0x1800ea617  jb      loc_1800EA6A2
0x1800ea61d  mov     ebx, [rsp+2D0h+cbData]
0x1800ea621  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea626  lea     rcx, [rbp+1D0h+Data]
0x1800ea62a  mov     dword ptr [rsp+2D0h+lpcbData], ebx
0x1800ea62e  mov     [rsp+2D0h+phkResult], rcx
0x1800ea633  mov     r9d, eax
0x1800ea636  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea63d  mov     rcx, [rcx+10h]
0x1800ea641  call    WPP_SF_DSd
0x1800ea646  jmp     short loc_1800EA6A2
0x1800ea648  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea64f  lea     rcx, WPP_GLOBAL_Control
0x1800ea656  cmp     rax, rcx
0x1800ea659  jz      short loc_1800EA6A2
0x1800ea65b  test    dword ptr [rax+1Ch], 100h
0x1800ea662  jz      short loc_1800EA6A2
0x1800ea664  cmp     byte ptr [rax+19h], 3
0x1800ea668  jb      short loc_1800EA6A2
0x1800ea66a  cmp     [rsp+2D0h+Type], 1
0x1800ea66f  lea     rax, aNotSz; "not sz"
0x1800ea676  lea     rbx, aRegSz; "REG_SZ"
0x1800ea67d  cmovnz  rbx, rax
0x1800ea681  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea686  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea68d  mov     r9d, eax
0x1800ea690  mov     [rsp+2D0h+lpcbData], rbx
0x1800ea695  mov     dword ptr [rsp+2D0h+phkResult], esi
0x1800ea699  mov     rcx, [rcx+10h]
0x1800ea69d  call    WPP_SF_DdS
0x1800ea6a2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ea6a7  call    cs:__imp_RegCloseKey
0x1800ea6ad  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x1800ea6b3  mov     rcx, rax
0x1800ea6b6  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x1800ea6bc  mov     ecx, 8; Size
0x1800ea6c1  mov     esi, eax
0x1800ea6c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ea6c8  test    rax, rax
0x1800ea6cb  jz      short loc_1800EA6D2
0x1800ea6cd  mov     [rax], r15
0x1800ea6d0  jmp     short loc_1800EA6D5
0x1800ea6d2  mov     rax, r15
0x1800ea6d5  mov     [r14+38h], rax
0x1800ea6d9  test    rax, rax
0x1800ea6dc  mov     eax, cs:CallbackContext
0x1800ea6e2  jnz     loc_1800EA771
0x1800ea6e8  mov     ebx, 8007000Eh
0x1800ea6ed  cmp     eax, 2
0x1800ea6f0  jbe     loc_1800EA8E6
0x1800ea6f6  lea     rax, aFailedToAlloca_25; "Failed to allocate memory for m_pModel"
0x1800ea6fd  mov     [rsp+2D0h+cbData], 70h ; 'p'
0x1800ea705  mov     [rsp+2D0h+var_268], rax
0x1800ea70a  lea     rdx, dword_18028210C
0x1800ea711  lea     rax, aLoadmodel; "LoadModel"
0x1800ea718  mov     [rsp+2D0h+var_260], rax
0x1800ea71d  lea     rax, aOnecoreTermsrv_56; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800ea724  mov     [rsp+2D0h+var_270], rax
0x1800ea729  lea     rax, aErrorCondition; "Error condition failed"
0x1800ea730  mov     [rsp+2D0h+var_278], rax
0x1800ea735  lea     rax, [rsp+2D0h+var_268]
0x1800ea73a  mov     [rsp+2D0h+var_288], rax
0x1800ea73f  lea     rax, [rsp+2D0h+var_260]
0x1800ea744  mov     [rsp+2D0h+var_290], rax
0x1800ea749  lea     rax, [rsp+2D0h+cbData]
0x1800ea74e  mov     [rsp+2D0h+var_298], rax
0x1800ea753  lea     rax, [rsp+2D0h+var_270]
0x1800ea758  mov     [rsp+2D0h+var_2A0], rax
0x1800ea75d  lea     rax, [rsp+2D0h+Type]
0x1800ea762  mov     [rsp+2D0h+lpcbData], rax
0x1800ea767  lea     rax, [rsp+2D0h+var_278]
0x1800ea76c  jmp     loc_1800EA8D8
0x1800ea771  test    rdi, rdi
0x1800ea774  jz      loc_1800EA854
0x1800ea77a  cmp     eax, 4
0x1800ea77d  jbe     short loc_1800EA7C2
0x1800ea77f  lea     rax, [rbp+1D0h+Data]
0x1800ea783  mov     [rsp+2D0h+cbData], edi
0x1800ea787  mov     [rsp+2D0h+var_278], rax
0x1800ea78c  lea     rdx, dword_18028201C
0x1800ea793  lea     rax, aLoadingModelFi; "Loading model file"
0x1800ea79a  mov     [rsp+2D0h+var_270], rax
0x1800ea79f  lea     rax, [rsp+2D0h+cbData]
0x1800ea7a4  mov     [rsp+2D0h+var_2A0], rax
0x1800ea7a9  lea     rax, [rsp+2D0h+var_278]
0x1800ea7ae  mov     [rsp+2D0h+lpcbData], rax
0x1800ea7b3  lea     rax, [rsp+2D0h+var_270]
0x1800ea7b8  mov     [rsp+2D0h+phkResult], rax
0x1800ea7bd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800ea7c2  mov     rcx, [r14+38h]; this
0x1800ea7c6  lea     rdx, [rbp+1D0h+Data]; unsigned __int16 *
0x1800ea7ca  mov     r8, rdi; unsigned __int64
0x1800ea7cd  call    ?Initialize@WinMLLearningModel@Details@MachineLearning@AI@RDP@@QEAAJPEBG_K@Z; RDP::AI::MachineLearning::Details::WinMLLearningModel::Initialize(ushort const *,unsigned __int64)
0x1800ea7d2  mov     ebx, eax
0x1800ea7d4  test    eax, eax
0x1800ea7d6  jns     short loc_1800EA7FF
0x1800ea7d8  mov     ecx, cs:CallbackContext
0x1800ea7de  cmp     ecx, 2
0x1800ea7e1  jbe     loc_1800EA8E6
0x1800ea7e7  lea     rax, aMPmodelInitial; "m_pModel->Initialize() failed!"
0x1800ea7ee  mov     [rsp+2D0h+cbData], 7Bh ; '{'
0x1800ea7f6  lea     rdx, unk_180282060
0x1800ea7fd  jmp     short loc_1800EA878
0x1800ea7ff  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x1800ea805  mov     rcx, rax
0x1800ea808  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x1800ea80e  mov     ecx, cs:CallbackContext
0x1800ea814  cmp     ecx, 4
0x1800ea817  jbe     loc_1800EA8E6
0x1800ea81d  sub     eax, esi
0x1800ea81f  lea     rdx, dword_180281FDC
0x1800ea826  mov     [rsp+2D0h+cbData], eax
0x1800ea82a  lea     rax, aNnModelLoaded; "NN model loaded"
0x1800ea831  mov     [rsp+2D0h+var_278], rax
0x1800ea836  lea     rax, [rsp+2D0h+cbData]
0x1800ea83b  mov     [rsp+2D0h+lpcbData], rax
0x1800ea840  lea     rax, [rsp+2D0h+var_278]
0x1800ea845  mov     [rsp+2D0h+phkResult], rax
0x1800ea84a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ea84f  jmp     loc_1800EA8E6
0x1800ea854  mov     ebx, 80004001h
0x1800ea859  cmp     eax, 2
0x1800ea85c  jbe     loc_1800EA8E6
0x1800ea862  lea     rax, aLoadingNnModel; "Loading NN Model from resource blob dis"...
0x1800ea869  mov     [rsp+2D0h+cbData], 81h
0x1800ea871  lea     rdx, word_180281F86
0x1800ea878  mov     [rsp+2D0h+var_278], rax
0x1800ea87d  lea     rax, aLoadmodel; "LoadModel"
0x1800ea884  mov     [rsp+2D0h+var_270], rax
0x1800ea889  lea     rax, aOnecoreTermsrv_56; "onecore\\termsrv\\rdpplatform\\imganaly"...
0x1800ea890  mov     [rsp+2D0h+var_260], rax
0x1800ea895  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800ea89c  mov     [rsp+2D0h+var_268], rax
0x1800ea8a1  lea     rax, [rsp+2D0h+var_278]
0x1800ea8a6  mov     [rsp+2D0h+var_288], rax
0x1800ea8ab  lea     rax, [rsp+2D0h+var_270]
0x1800ea8b0  mov     [rsp+2D0h+var_290], rax
0x1800ea8b5  lea     rax, [rsp+2D0h+cbData]
0x1800ea8ba  mov     [rsp+2D0h+var_298], rax
0x1800ea8bf  lea     rax, [rsp+2D0h+var_260]
0x1800ea8c4  mov     [rsp+2D0h+var_2A0], rax
0x1800ea8c9  lea     rax, [rsp+2D0h+Type]
0x1800ea8ce  mov     [rsp+2D0h+lpcbData], rax
0x1800ea8d3  lea     rax, [rsp+2D0h+var_268]
0x1800ea8d8  mov     [rsp+2D0h+phkResult], rax
0x1800ea8dd  mov     [rsp+2D0h+Type], ebx
0x1800ea8e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800ea8e6  mov     eax, ebx
0x1800ea8e8  mov     rcx, [rbp+1D0h+var_40]
0x1800ea8ef  xor     rcx, rsp; StackCookie
0x1800ea8f2  call    __security_check_cookie
0x1800ea8f7  add     rsp, 2A8h
0x1800ea8fe  pop     r15
0x1800ea900  pop     r14
0x1800ea902  pop     rdi
0x1800ea903  pop     rsi
0x1800ea904  pop     rbx
0x1800ea905  pop     rbp
0x1800ea906  retn
```
