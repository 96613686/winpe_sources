# CUserStateManager::CUserStateManager(std::shared_ptr<IPartnershipPersister> &,std::shared_ptr<IProtocolClientFactory> &,std::shared_ptr<ILocalChangeWatcherFactory> &,std::shared_ptr<ISyncShareEngineFactory> &,std::shared_ptr<void>,SyncShareManagerConfig &,ISyncShareManagerProgressCallback *)

- ea: `0x1800360ac`
- end: `0x1800365f9`
- name: `??0CUserStateManager@@QEAA@AEAV?$shared_ptr@VIPartnershipPersister@@@std@@AEAV?$shared_ptr@VIProtocolClientFactory@@@2@AEAV?$shared_ptr@VILocalChangeWatcherFactory@@@2@AEAV?$shared_ptr@VISyncShareEngineFactory@@@2@V?$shared_ptr@X@2@AEAVSyncShareManagerConfig@@PEAUISyncShareManagerProgressCallback@@@Z`
- size: `1357`
- prototype: `CUserStateManager *__fastcall(CUserStateManager *this, _QWORD *, _QWORD *, _QWORD *, CUserStateManager *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023e64`

## callees

- `0x180002ab0`
- `0x180002fa4`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180010d58`
- `0x180010f40`
- `0x180011314`
- `0x180023c90`
- `0x1800355ac`
- `0x1800357c4`
- `0x180035cb4`
- `0x180035d40`
- `0x180035da8`
- `0x1800360ac`
- `0x180039bf8`
- `0x180039ec4`
- `0x18003cc04`
- `0x1800421c4`
- `0x18013e010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180036376`
- `ADVAPI32!GetTokenInformation` at `0x180036376`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036223`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036223`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CUserStateManager *__fastcall CUserStateManager::CUserStateManager(
        CUserStateManager *this,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        CUserStateManager *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _QWORD *v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  CUserStatePersister *v19; // rbx
  _BYTE *v20; // rax
  char v21; // cl
  void *v22; // rcx
  __int64 UserDeviceId; // rax
  const WCHAR *v24; // rax
  __int64 v25; // rax
  __int128 v26; // kr00_16
  std::_Ref_count_base *v27; // rcx
  __int64 v28; // rax
  char *v29; // r10
  const WCHAR *v30; // rcx
  char *v31; // rax
  int v32; // eax
  std::_Ref_count_base *v33; // rcx
  int pExceptionObject; // [rsp+40h] [rbp-B1h] BYREF
  CUserStatePersister *v36; // [rsp+48h] [rbp-A9h] BYREF
  int TokenInformation; // [rsp+50h] [rbp-A1h] BYREF
  int LastFailureAsHRESULT; // [rsp+58h] [rbp-99h] BYREF
  int v39; // [rsp+5Ch] [rbp-95h]
  char v40; // [rsp+60h] [rbp-91h]
  const char *v41; // [rsp+68h] [rbp-89h]
  __int64 v42; // [rsp+70h] [rbp-81h]
  CUserStateManager *v43; // [rsp+78h] [rbp-79h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp-71h] BYREF
  __int64 v45; // [rsp+88h] [rbp-69h]
  _QWORD *v46; // [rsp+90h] [rbp-61h] BYREF
  __int64 v47; // [rsp+98h] [rbp-59h]
  __int128 v48; // [rsp+A0h] [rbp-51h]
  __int64 v49[3]; // [rsp+B0h] [rbp-41h] BYREF
  _BYTE v50[8]; // [rsp+C8h] [rbp-29h] BYREF
  std::_Ref_count_base *v51; // [rsp+D0h] [rbp-21h]

  v46 = a2;
  v49[1] = (__int64)this;
  v43 = a5;
  v49[2] = a6;
  v45 = a7;
  v47 = a8;
  *(_QWORD *)this = &IUserCredentialProvider::`vftable';
  *((_QWORD *)this + 1) = &IRemoteTriggerPartnershipProvider::`vftable';
  *((_QWORD *)this + 2) = &IDiscoveryProvider::`vftable';
  *(_QWORD *)this = &CUserStateManager::`vftable'{for `IUserCredentialProvider'};
  *((_QWORD *)this + 1) = &CUserStateManager::`vftable'{for `IRemoteTriggerPartnershipProvider'};
  *((_QWORD *)this + 2) = &CUserStateManager::`vftable'{for `IDiscoveryProvider'};
  v12 = (_QWORD *)((char *)this + 24);
  v36 = (CUserStateManager *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v13 = operator new(0x48u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  *v12 = v13;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v14 = a2[1];
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  *((_QWORD *)this + 5) = *a2;
  *((_QWORD *)this + 6) = a2[1];
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v15 = a4[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *((_QWORD *)this + 11) = *a4;
  *((_QWORD *)this + 12) = a4[1];
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  v16 = a3[1];
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  *((_QWORD *)this + 13) = *a3;
  *((_QWORD *)this + 14) = a3[1];
  v36 = (CUserStateManager *)((char *)this + 120);
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *((_DWORD *)this + 46) = 0;
  v17 = v45;
  *(_OWORD *)((char *)this + 188) = *(_OWORD *)v45;
  *((_DWORD *)this + 51) = *(_DWORD *)(v17 + 16);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  v18 = *(_QWORD *)(a6 + 8);
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
  *((_QWORD *)this + 26) = *(_QWORD *)a6;
  *((_QWORD *)this + 27) = *(_QWORD *)(a6 + 8);
  *((_QWORD *)this + 28) = v47;
  v36 = (CUserStatePersister *)operator new(0x28u);
  *((_QWORD *)this + 30) = CUserStatePersister::CUserStatePersister(v36);
  v19 = (CUserStateManager *)((char *)this + 256);
  *((_OWORD *)this + 16) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 7;
  *((_WORD *)this + 128) = 0;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_15:
      v21 = 0;
      goto LABEL_16;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids);
      v20 = WPP_GLOBAL_Control;
    }
  }
  if ( (v20[68] & 8) == 0 )
    goto LABEL_15;
  v21 = 1;
  if ( v20[65] < 6u )
    goto LABEL_15;
LABEL_16:
  v39 = 24;
  v40 = v21;
  v41 = "CUserStateManager::CUserStateManager";
  v42 = 0;
  LastFailureAsHRESULT = 0;
  v22 = *(void **)a6;
  if ( !*(_QWORD *)a6 )
  {
    LastFailureAsHRESULT = -2147024809;
    HIWORD(v39) = 26;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v39) = 26;
  TokenInformation = 1;
  ReturnLength = 0;
  LastFailureAsHRESULT = 0;
  if ( !GetTokenInformation(v22, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v39) = 34;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 34;
  *((_BYTE *)this + 248) = TokenInformation == 2;
  UserDeviceId = CUserStateManager::GetUserDeviceId(v50);
  std::wstring::operator=((char *)this + 256, UserDeviceId);
  std::wstring::_Tidy_deallocate(v50);
  if ( *((_QWORD *)this + 35) <= 7u )
    v24 = (const WCHAR *)((char *)this + 256);
  else
    v24 = *(const WCHAR **)v19;
  v49[0] = (__int64)v24;
  v36 = this;
  pExceptionObject = *(_DWORD *)v45;
  v25 = std::make_shared<CRemoteTriggerFactory,long,CUserStateManager *,std::shared_ptr<IProtocolClientFactory> &,std::shared_ptr<void> &,unsigned short const *>(
          (__int64)v50,
          &pExceptionObject,
          &v36,
          (int)a3,
          (__int128 *)a6,
          v49);
  v48 = 0;
  v48 = *(_OWORD *)v25;
  v26 = v48;
  *(_QWORD *)v25 = 0;
  *(_QWORD *)(v25 + 8) = 0;
  *(_QWORD *)&v48 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v26;
  *((_QWORD *)&v48 + 1) = *((_QWORD *)this + 10);
  v27 = (std::_Ref_count_base *)*((_QWORD *)&v48 + 1);
  *((_QWORD *)this + 10) = *((_QWORD *)&v26 + 1);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  if ( v51 )
    std::_Ref_count_base::_Decref(v51);
  v28 = std::make_shared<CUniqueSyncEngine,std::shared_ptr<ISyncShareEngineFactory> &>(v50, v43);
  std::shared_ptr<IDataTransferProgressCallback>::operator=<CDataTransferProgressCallback,0>((char *)this + 128, v28);
  if ( v51 )
    std::_Ref_count_base::_Decref(v51);
  v29 = (char *)operator new(0x1C0u);
  v43 = (CUserStateManager *)v29;
  if ( *((_QWORD *)this + 35) <= 7u )
    v30 = (const WCHAR *)((char *)this + 256);
  else
    v30 = *(const WCHAR **)v19;
  v31 = CSyncEngineRunner::CSyncEngineRunner(
          v29,
          (_QWORD *)this + 16,
          v46,
          a3,
          v47,
          *(_DWORD *)(v45 + 4),
          (PTP_TIMER)a6,
          v30);
  std::shared_ptr<CSyncEngineRunner>::reset<CSyncEngineRunner,0>((char *)this + 56, v31);
  v46 = this;
  v43 = this;
  if ( *((_QWORD *)this + 35) > 7u )
    v19 = *(CUserStatePersister **)v19;
  v36 = v19;
  v32 = CEcsUnkImpl_CFileDownloadManager_IFileDownloadManager_IFileDownloadManagerExtension__anonymous_namespace_::CNull_A0xff0eb82f::CNull_A0xff0eb82f::CNull_A0xff0eb82f::CNull_::CreateInstance_unsigned_short_const___std::shared_ptr_IUniqueSyncEngine__std::shared_ptr_IProtocolClientFactory__CUserStateManager___CUserStateManager___(
          (unsigned int)&v36,
          (int)this + 128,
          (_DWORD)a3,
          (unsigned int)&v43,
          (__int64)&v46,
          (__int64)this + 120);
  LastFailureAsHRESULT = v32;
  if ( v32 < 0 )
  {
    HIWORD(v39) = 67;
    pExceptionObject = v32;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v39) = 67;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 272LL))(
    *((_QWORD *)this + 5),
    *((_QWORD *)this + 15));
  CUserStateManager::LoadPartnerships(this);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  v33 = *(std::_Ref_count_base **)(a6 + 8);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  return this;
}

```

## disassembly

```asm
0x1800360ac  push    rbp
0x1800360ae  push    rbx
0x1800360af  push    rsi
0x1800360b0  push    rdi
0x1800360b1  push    r12
0x1800360b3  push    r13
0x1800360b5  push    r14
0x1800360b7  push    r15
0x1800360b9  lea     rbp, [rsp-7]
0x1800360be  sub     rsp, 0F8h
0x1800360c5  mov     rax, cs:__security_cookie
0x1800360cc  xor     rax, rsp
0x1800360cf  mov     [rbp+3Fh+var_48], rax
0x1800360d3  mov     rsi, r9
0x1800360d6  mov     r15, r8
0x1800360d9  mov     r12, rdx
0x1800360dc  mov     [rbp+3Fh+var_A0], rdx
0x1800360e0  mov     rdi, rcx
0x1800360e3  mov     [rbp+3Fh+var_78], rcx
0x1800360e7  mov     rax, [rbp+3Fh+arg_20]
0x1800360eb  mov     [rbp+3Fh+var_B8], rax
0x1800360ef  mov     r14, [rbp+3Fh+arg_28]
0x1800360f3  mov     [rbp+3Fh+var_70], r14
0x1800360f7  mov     rax, [rbp+3Fh+arg_30]
0x1800360fb  mov     [rbp+3Fh+var_A8], rax
0x1800360ff  mov     rax, [rbp+3Fh+arg_38]
0x180036106  mov     [rbp+3Fh+var_98], rax
0x18003610a  lea     rax, ??_7IUserCredentialProvider@@6B@; const IUserCredentialProvider::`vftable'
0x180036111  mov     [rcx], rax
0x180036114  lea     rax, ??_7IRemoteTriggerPartnershipProvider@@6B@; const IRemoteTriggerPartnershipProvider::`vftable'
0x18003611b  mov     [rcx+8], rax
0x18003611f  lea     rax, ??_7IDiscoveryProvider@@6B@; const IDiscoveryProvider::`vftable'
0x180036126  mov     [rcx+10h], rax
0x18003612a  lea     rax, ??_7CUserStateManager@@6BIUserCredentialProvider@@@; const CUserStateManager::`vftable'{for `IUserCredentialProvider'}
0x180036131  mov     [rcx], rax
0x180036134  lea     rax, ??_7CUserStateManager@@6BIRemoteTriggerPartnershipProvider@@@; const CUserStateManager::`vftable'{for `IRemoteTriggerPartnershipProvider'}
0x18003613b  mov     [rcx+8], rax
0x18003613f  lea     rax, ??_7CUserStateManager@@6BIDiscoveryProvider@@@; const CUserStateManager::`vftable'{for `IDiscoveryProvider'}
0x180036146  mov     [rcx+10h], rax
0x18003614a  lea     rbx, [rcx+18h]
0x18003614e  mov     [rsp+130h+var_E8], rbx
0x180036153  mov     qword ptr [rbx], 0
0x18003615a  mov     qword ptr [rbx+8], 0
0x180036162  mov     ecx, 48h ; 'H'; Size
0x180036167  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003616c  mov     [rax], rax
0x18003616f  mov     [rax+8], rax
0x180036173  mov     [rax+10h], rax
0x180036177  mov     word ptr [rax+18h], 101h
0x18003617d  mov     [rbx], rax
0x180036180  xor     ebx, ebx
0x180036182  mov     [rdi+28h], rbx
0x180036186  mov     [rdi+30h], rbx
0x18003618a  mov     rax, [r12+8]
0x18003618f  test    rax, rax
0x180036192  jz      short loc_180036198
0x180036194  lock inc dword ptr [rax+8]
0x180036198  mov     rax, [r12]
0x18003619c  mov     [rdi+28h], rax
0x1800361a0  mov     rax, [r12+8]
0x1800361a5  mov     [rdi+30h], rax
0x1800361a9  mov     [rdi+38h], rbx
0x1800361ad  mov     [rdi+40h], rbx
0x1800361b1  mov     [rdi+48h], rbx
0x1800361b5  mov     [rdi+50h], rbx
0x1800361b9  mov     [rdi+58h], rbx
0x1800361bd  mov     [rdi+60h], rbx
0x1800361c1  mov     rax, [rsi+8]
0x1800361c5  test    rax, rax
0x1800361c8  jz      short loc_1800361CE
0x1800361ca  lock inc dword ptr [rax+8]
0x1800361ce  mov     rax, [rsi]
0x1800361d1  mov     [rdi+58h], rax
0x1800361d5  mov     rax, [rsi+8]
0x1800361d9  mov     [rdi+60h], rax
0x1800361dd  mov     [rdi+68h], rbx
0x1800361e1  mov     [rdi+70h], rbx
0x1800361e5  mov     rax, [r15+8]
0x1800361e9  test    rax, rax
0x1800361ec  jz      short loc_1800361F2
0x1800361ee  lock inc dword ptr [rax+8]
0x1800361f2  mov     rax, [r15]
0x1800361f5  mov     [rdi+68h], rax
0x1800361f9  mov     rax, [r15+8]
0x1800361fd  mov     [rdi+70h], rax
0x180036201  lea     r12, [rdi+78h]
0x180036205  mov     [rsp+130h+var_E8], r12
0x18003620a  mov     [r12], rbx
0x18003620e  lea     rsi, [rdi+80h]
0x180036215  mov     [rsi], rbx
0x180036218  mov     [rsi+8], rbx
0x18003621c  lea     rcx, [rdi+90h]; lpCriticalSection
0x180036223  call    cs:__imp_InitializeCriticalSection
0x180036229  nop
0x18003622a  mov     [rdi+0B8h], ebx
0x180036230  mov     rax, [rbp+3Fh+var_A8]
0x180036234  movups  xmm0, xmmword ptr [rax]
0x180036237  movups  xmmword ptr [rdi+0BCh], xmm0
0x18003623e  mov     eax, [rax+10h]
0x180036241  mov     [rdi+0CCh], eax
0x180036247  mov     [rdi+0D0h], rbx
0x18003624e  mov     [rdi+0D8h], rbx
0x180036255  mov     rax, [r14+8]
0x180036259  test    rax, rax
0x18003625c  jz      short loc_180036262
0x18003625e  lock inc dword ptr [rax+8]
0x180036262  mov     rax, [r14]
0x180036265  mov     [rdi+0D0h], rax
0x18003626c  mov     rax, [r14+8]
0x180036270  mov     [rdi+0D8h], rax
0x180036277  mov     rax, [rbp+3Fh+var_98]
0x18003627b  mov     [rdi+0E0h], rax
0x180036282  mov     ecx, 28h ; '('; Size
0x180036287  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003628c  mov     [rsp+130h+var_E8], rax
0x180036291  mov     rcx, rax; this
0x180036294  call    ??0CUserStatePersister@@QEAA@XZ; CUserStatePersister::CUserStatePersister(void)
0x180036299  nop
0x18003629a  mov     [rdi+0F0h], rax
0x1800362a1  lea     rbx, [rdi+100h]
0x1800362a8  xorps   xmm0, xmm0
0x1800362ab  movups  xmmword ptr [rbx], xmm0
0x1800362ae  xor     edx, edx
0x1800362b0  mov     [rbx+10h], rdx
0x1800362b4  mov     qword ptr [rbx+18h], 7
0x1800362bc  mov     [rbx], dx
0x1800362bf  lea     rcx, WPP_GLOBAL_Control
0x1800362c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800362cd  cmp     rax, rcx
0x1800362d0  jz      short loc_1800362FC
0x1800362d2  test    byte ptr [rax+44h], 8
0x1800362d6  jz      short loc_18003630A
0x1800362d8  cmp     byte ptr [rax+41h], 6
0x1800362dc  jb      short loc_1800362FC
0x1800362de  mov     edx, 0Ah
0x1800362e3  lea     r8, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids
0x1800362ea  mov     rcx, [rax+38h]
0x1800362ee  call    WPP_SF_
0x1800362f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800362fa  xor     edx, edx
0x1800362fc  test    byte ptr [rax+44h], 8
0x180036300  jz      short loc_18003630A
0x180036302  cmp     byte ptr [rax+41h], 6
0x180036306  mov     cl, 1
0x180036308  jnb     short loc_18003630C
0x18003630a  mov     cl, dl
0x18003630c  mov     [rsp+130h+var_D8], edx
0x180036310  mov     [rsp+130h+var_D4], 18h
0x180036318  mov     [rsp+130h+var_D0], cl
0x18003631c  lea     rax, aCuserstatemana_19; "CUserStateManager::CUserStateManager"
0x180036323  mov     [rsp+130h+var_C8], rax
0x180036328  mov     [rsp+130h+var_C0], rdx
0x18003632d  mov     eax, [rsp+130h+var_D8]
0x180036331  mov     [rsp+130h+var_D8], eax
0x180036335  mov     rcx, [r14]; TokenHandle
0x180036338  mov     eax, 1Ah
0x18003633d  test    rcx, rcx
0x180036340  jz      loc_1800365AC
0x180036346  mov     [rsp+130h+var_D8], edx
0x18003634a  mov     word ptr [rsp+130h+var_D4], ax
0x18003634f  mov     [rsp+130h+TokenInformation], 1
0x180036357  mov     [rbp+3Fh+var_B0], edx
0x18003635a  mov     [rsp+130h+var_D8], edx
0x18003635e  lea     rax, [rbp+3Fh+var_B0]
0x180036362  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180036367  mov     r9d, 4; TokenInformationLength
0x18003636d  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x180036372  lea     edx, [r9+0Eh]; TokenInformationClass
0x180036376  call    cs:__imp_GetTokenInformation
0x18003637c  test    eax, eax
0x18003637e  jz      loc_1800365D0
0x180036384  mov     [rsp+130h+var_D8], 0
0x18003638c  mov     ecx, 22h ; '"'
0x180036391  mov     word ptr [rsp+130h+var_D4], cx
0x180036396  cmp     [rsp+130h+TokenInformation], 2
0x18003639b  setz    al
0x18003639e  mov     [rdi+0F8h], al
0x1800363a4  lea     rcx, [rbp+3Fh+var_68]
0x1800363a8  call    ?GetUserDeviceId@CUserStateManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CUserStateManager::GetUserDeviceId(void)
0x1800363ad  nop
0x1800363ae  mov     rdx, rax
0x1800363b1  mov     rcx, rbx
0x1800363b4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800363b9  nop
0x1800363ba  lea     rcx, [rbp+3Fh+var_68]
0x1800363be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800363c3  cmp     qword ptr [rbx+18h], 7
0x1800363c8  jbe     short loc_1800363CF
0x1800363ca  mov     rax, [rbx]
0x1800363cd  jmp     short loc_1800363D2
0x1800363cf  mov     rax, rbx
0x1800363d2  mov     [rbp+3Fh+var_80], rax
0x1800363d6  mov     [rsp+130h+var_E8], rdi
0x1800363db  mov     rax, [rbp+3Fh+var_A8]
0x1800363df  mov     eax, [rax]
0x1800363e1  mov     [rsp+130h+pExceptionObject], eax
0x1800363e5  lea     rax, [rbp+3Fh+var_80]
0x1800363e9  mov     qword ptr [rsp+130h+var_108], rax
0x1800363ee  mov     [rsp+130h+ReturnLength], r14
0x1800363f3  mov     r9, r15
0x1800363f6  lea     r8, [rsp+130h+var_E8]
0x1800363fb  lea     rdx, [rsp+130h+pExceptionObject]
0x180036400  lea     rcx, [rbp+3Fh+var_68]
0x180036404  call    ??$make_shared@VCRemoteTriggerFactory@@JPEAVCUserStateManager@@AEAV?$shared_ptr@VIProtocolClientFactory@@@std@@AEAV?$shared_ptr@X@4@PEBG@std@@YA?AV?$shared_ptr@VCRemoteTriggerFactory@@@0@$$QEAJ$$QEAPEAVCUserStateManager@@AEAV?$shared_ptr@VIProtocolClientFactory@@@0@AEAV?$shared_ptr@X@0@$$QEAPEBG@Z; std::make_shared<CRemoteTriggerFactory,long,CUserStateManager *,std::shared_ptr<IProtocolClientFactory> &,std::shared_ptr<void> &,ushort const *>(long &&,CUserStateManager * &&,std::shared_ptr<IProtocolClientFactory> &,std::shared_ptr<void> &,ushort const * &&)
0x180036409  nop
0x18003640a  xorps   xmm0, xmm0
0x18003640d  movdqu  [rbp+3Fh+var_90], xmm0
0x180036412  mov     rcx, [rax]
0x180036415  mov     qword ptr [rbp+3Fh+var_90], rcx
0x180036419  mov     rdx, [rax+8]
0x18003641d  mov     qword ptr [rbp+3Fh+var_90+8], rdx
0x180036421  mov     qword ptr [rax], 0
0x180036428  mov     qword ptr [rax+8], 0
0x180036430  mov     rax, [rdi+48h]
0x180036434  mov     qword ptr [rbp+3Fh+var_90], rax
0x180036438  mov     [rdi+48h], rcx
0x18003643c  mov     rcx, [rdi+50h]; this
0x180036440  mov     qword ptr [rbp+3Fh+var_90+8], rcx
0x180036444  mov     [rdi+50h], rdx
0x180036448  test    rcx, rcx
0x18003644b  jz      short loc_180036453
0x18003644d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036452  nop
0x180036453  mov     rcx, [rbp+3Fh+var_60]; this
0x180036457  test    rcx, rcx
0x18003645a  jz      short loc_180036461
0x18003645c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036461  mov     rdx, [rbp+3Fh+var_B8]
0x180036465  lea     rcx, [rbp+3Fh+var_68]
0x180036469  call    ??$make_shared@VCUniqueSyncEngine@@AEAV?$shared_ptr@VISyncShareEngineFactory@@@std@@@std@@YA?AV?$shared_ptr@VCUniqueSyncEngine@@@0@AEAV?$shared_ptr@VISyncShareEngineFactory@@@0@@Z; std::make_shared<CUniqueSyncEngine,std::shared_ptr<ISyncShareEngineFactory> &>(std::shared_ptr<ISyncShareEngineFactory> &)
0x18003646e  nop
0x18003646f  mov     rdx, rax
0x180036472  mov     rcx, rsi
0x180036475  call    ??$?4VCDataTransferProgressCallback@@$0A@@?$shared_ptr@UIDataTransferProgressCallback@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@VCDataTransferProgressCallback@@@1@@Z; std::shared_ptr<IDataTransferProgressCallback>::operator=<CDataTransferProgressCallback,0>(std::shared_ptr<CDataTransferProgressCallback> &&)
0x18003647a  nop
0x18003647b  mov     rcx, [rbp+3Fh+var_60]; this
0x18003647f  test    rcx, rcx
0x180036482  jz      short loc_180036489
0x180036484  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036489  mov     ecx, 1C0h; Size
0x18003648e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036493  mov     r10, rax
0x180036496  mov     [rbp+3Fh+var_B8], rax
0x18003649a  cmp     qword ptr [rbx+18h], 7
0x18003649f  jbe     short loc_1800364A6
0x1800364a1  mov     rcx, [rbx]
0x1800364a4  jmp     short loc_1800364A9
0x1800364a6  mov     rcx, rbx
0x1800364a9  mov     [rsp+130h+var_F8], rcx; __int64
0x1800364ae  mov     [rsp+130h+var_100], r14; pExceptionObject
0x1800364b3  mov     rax, [rbp+3Fh+var_A8]
0x1800364b7  mov     eax, [rax+4]
0x1800364ba  mov     [rsp+130h+var_108], eax; int
0x1800364be  mov     rax, [rbp+3Fh+var_98]
0x1800364c2  mov     [rsp+130h+ReturnLength], rax; __int64
0x1800364c7  mov     r9, r15
0x1800364ca  mov     r8, [rbp+3Fh+var_A0]
0x1800364ce  mov     rdx, rsi
0x1800364d1  mov     rcx, r10; void *
0x1800364d4  call    ??0CSyncEngineRunner@@QEAA@AEAV?$shared_ptr@VIUniqueSyncEngine@@@std@@AEAV?$shared_ptr@VIPartnershipPersister@@@2@AEAV?$shared_ptr@VIProtocolClientFactory@@@2@PEAUISyncShareManagerProgressCallback@@JAEAV?$shared_ptr@X@2@PEBG@Z; CSyncEngineRunner::CSyncEngineRunner(std::shared_ptr<IUniqueSyncEngine> &,std::shared_ptr<IPartnershipPersister> &,std::shared_ptr<IProtocolClientFactory> &,ISyncShareManagerProgressCallback *,long,std::shared_ptr<void> &,ushort const *)
0x1800364d9  nop
0x1800364da  mov     rdx, rax
0x1800364dd  lea     rcx, [rdi+38h]
0x1800364e1  call    ??$reset@VCSyncEngineRunner@@$0A@@?$shared_ptr@VCSyncEngineRunner@@@std@@QEAAXPEAVCSyncEngineRunner@@@Z; std::shared_ptr<CSyncEngineRunner>::reset<CSyncEngineRunner,0>(CSyncEngineRunner *)
0x1800364e6  mov     [rbp+3Fh+var_A0], rdi
0x1800364ea  mov     [rbp+3Fh+var_B8], rdi
0x1800364ee  cmp     qword ptr [rbx+18h], 7
0x1800364f3  jbe     short loc_1800364F8
0x1800364f5  mov     rbx, [rbx]
0x1800364f8  mov     [rsp+130h+var_E8], rbx
0x1800364fd  mov     qword ptr [rsp+130h+var_108], r12
0x180036502  lea     rax, [rbp+3Fh+var_A0]
0x180036506  mov     [rsp+130h+ReturnLength], rax
0x18003650b  lea     r9, [rbp+3Fh+var_B8]
0x18003650f  mov     r8, r15
0x180036512  mov     rdx, rsi
0x180036515  lea     rcx, [rsp+130h+var_E8]
0x18003651a  call    CEcsUnkImpl_CFileDownloadManager_IFileDownloadManager_IFileDownloadManagerExtension__anonymous_namespace___CNull_A0xff0eb82f__CNull_A0xff0eb82f__CNull_A0xff0eb82f__CNull___CreateInstance_unsigned_short_const___std__shared_ptr_IUniqueSyncEngine__std__shared_ptr_IProtocolClientFactory__CUserStateManager___CUserStateManager___
0x18003651f  mov     [rsp+130h+var_D8], eax
0x180036523  mov     [rsp+130h+var_D8], eax
0x180036527  mov     ecx, 43h ; 'C'
0x18003652c  test    eax, eax
0x18003652e  js      short loc_180036591
0x180036530  mov     word ptr [rsp+130h+var_D4], cx
0x180036535  mov     rcx, [rdi+28h]
0x180036539  mov     rax, [rcx]
0x18003653c  mov     rdx, [r12]
0x180036540  mov     rax, [rax+110h]
0x180036547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003654c  mov     rcx, rdi; this
0x18003654f  call    ?LoadPartnerships@CUserStateManager@@AEAAXXZ; CUserStateManager::LoadPartnerships(void)
0x180036554  nop
0x180036555  lea     rcx, [rsp+130h+var_D8]; this
0x18003655a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003655f  nop
0x180036560  mov     rcx, [r14+8]; this
0x180036564  test    rcx, rcx
0x180036567  jz      short loc_18003656E
0x180036569  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003656e  mov     rax, rdi
  ... truncated ...
```
