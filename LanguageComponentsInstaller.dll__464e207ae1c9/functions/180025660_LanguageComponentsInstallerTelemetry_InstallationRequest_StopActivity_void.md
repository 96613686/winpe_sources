# LanguageComponentsInstallerTelemetry::InstallationRequest::StopActivity(void)

- ea: `0x180025660`
- end: `0x1800258cf`
- name: `?StopActivity@InstallationRequest@LanguageComponentsInstallerTelemetry@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::InstallationRequest *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001658`
- `0x18000196c`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x180025660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800256ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002585b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800256ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002585b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025870`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationRequest::StopActivity(
        LanguageComponentsInstallerTelemetry::InstallationRequest *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  __int64 v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  __int64 v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = LanguageComponentsInstallerTelemetryProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      LODWORD(v33) = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v7;
      LODWORD(SRWLock) = v4[17];
      LODWORD(v31) = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v6,
        (int)&dword_18002FAA4,
        v8 + 8,
        (__int64)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (const unsigned __int16 **)&v27,
        (__int64)&v17,
        (const unsigned __int16 **)&v26,
        (__int64)&v16,
        (__int64 **)&v25,
        (__int64)&v15,
        (const unsigned __int16 **)&v24,
        (__int64)&v33,
        (const unsigned __int16 **)&v23,
        (__int64 **)&v22,
        (__int64)&v32,
        (const unsigned __int16 **)&v21,
        (__int64 **)&v20,
        (__int64)&v31,
        (__int64)&SRWLock,
        (const unsigned __int16 **)&v19);
    }
  }
  else
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v31) = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)&word_18002FE1E,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180025660  push    rbp
0x180025662  push    rbx
0x180025663  push    rdi
0x180025664  lea     rbp, [rsp+10h]
0x180025669  sub     rsp, 130h
0x180025670  mov     rdi, [rcx+110h]
0x180025677  mov     rbx, rcx
0x18002567a  mov     eax, [rdi+48h]
0x18002567d  test    eax, eax
0x18002567f  jns     loc_18002583C
0x180025685  add     rdi, 50h ; 'P'
0x180025689  cmp     eax, [rdi+8]
0x18002568c  jnz     loc_18002583C
0x180025692  test    rdi, rdi
0x180025695  jz      loc_18002583C
0x18002569b  lea     rdx, [rbp+SRWLock]
0x18002569f  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800256a4  mov     rax, [rbx+110h]
0x1800256ab  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800256af  mov     dword ptr [rax], 2
0x1800256b5  test    rcx, rcx
0x1800256b8  jz      short loc_1800256C0
0x1800256ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800256c0  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x1800256c5  mov     r9, rax
0x1800256c8  mov     ecx, [rax]
0x1800256ca  cmp     ecx, 5
0x1800256cd  jbe     loc_1800258BD
0x1800256d3  mov     rax, [rdi+70h]
0x1800256d7  lea     rdx, dword_18002FAA4; int
0x1800256de  mov     rcx, [rdi+30h]
0x1800256e2  mov     [rbp+var_60], rax
0x1800256e6  mov     eax, [rdi+68h]
0x1800256e9  mov     r8, [rbx+110h]
0x1800256f0  mov     dword ptr [rbp+arg_10], eax
0x1800256f3  add     r8, 8; int
0x1800256f7  mov     rax, [rdi+60h]
0x1800256fb  mov     [rbp+var_58], rax
0x1800256ff  mov     rax, [rdi+58h]
0x180025703  mov     [rbp+var_50], rax
0x180025707  mov     eax, [rdi+50h]
0x18002570a  mov     dword ptr [rbp+arg_18], eax
0x18002570d  mov     rax, [rdi+48h]
0x180025711  mov     [rbp+var_48], rax
0x180025715  mov     eax, [rdi+20h]
0x180025718  mov     dword ptr [rbp+var_80], eax
0x18002571b  mov     rax, [rdi+18h]
0x18002571f  mov     [rbp+var_40], rax
0x180025723  mov     eax, [rdi]
0x180025725  mov     dword ptr [rbp+var_80+4], eax
0x180025728  mov     rax, [rdi+80h]
0x18002572f  mov     [rbp+var_38], rax
0x180025733  mov     eax, [rdi+40h]
0x180025736  mov     dword ptr [rbp+var_78], eax
0x180025739  mov     rax, [rdi+38h]
0x18002573d  mov     [rbp+var_30], rax
0x180025741  mov     eax, [rdi+8]
0x180025744  mov     dword ptr [rbp+var_78+4], eax
0x180025747  lea     rax, [rbp+var_70]
0x18002574b  mov     [rsp+140h+var_90], rax; __int64
0x180025753  lea     rax, [rbp+SRWLock]
0x180025757  mov     [rsp+140h+var_98], rax; __int64
0x18002575f  lea     rax, [rbp+arg_8]
0x180025763  mov     [rsp+140h+var_A0], rax; __int64
0x18002576b  lea     rax, [rbp+var_68]
0x18002576f  mov     [rsp+140h+var_A8], rax; __int64
0x180025777  lea     rax, [rbp+var_60]
0x18002577b  mov     [rsp+140h+var_B0], rax; __int64
0x180025783  lea     rax, [rbp+arg_10]
0x180025787  mov     [rsp+140h+var_B8], rax; __int64
0x18002578f  lea     rax, [rbp+var_58]
0x180025793  mov     [rsp+140h+var_C0], rax; __int64
0x18002579b  lea     rax, [rbp+var_50]
0x18002579f  mov     [rsp+140h+var_C8], rax; __int64
0x1800257a4  lea     rax, [rbp+arg_18]
0x1800257a8  mov     [rsp+140h+var_D0], rax; __int64
0x1800257ad  lea     rax, [rbp+var_48]
0x1800257b1  mov     [rsp+140h+var_D8], rax; __int64
0x1800257b6  lea     rax, [rbp+var_80]
0x1800257ba  mov     [rsp+140h+var_E0], rax; __int64
0x1800257bf  lea     rax, [rbp+var_40]
0x1800257c3  mov     [rsp+140h+var_E8], rax; __int64
0x1800257c8  lea     rax, [rbp+var_80+4]
0x1800257cc  mov     [rsp+140h+var_F0], rax; __int64
0x1800257d1  lea     rax, [rbp+var_38]
0x1800257d5  mov     [rsp+140h+var_F8], rax; __int64
0x1800257da  lea     rax, [rbp+var_78]
0x1800257de  mov     [rsp+140h+var_100], rax; __int64
0x1800257e3  lea     rax, [rbp+var_30]
0x1800257e7  mov     [rsp+140h+var_108], rax; __int64
0x1800257ec  lea     rax, [rbp+var_78+4]
0x1800257f0  mov     [rbp+var_70], rcx
0x1800257f4  mov     ecx, [rdi+44h]
0x1800257f7  mov     [rsp+140h+var_110], rax; __int64
0x1800257fc  lea     rax, [rbp+var_28]
0x180025800  mov     dword ptr [rbp+SRWLock], ecx
0x180025803  mov     ecx, [rdi+10h]
0x180025806  mov     dword ptr [rbp+arg_8], ecx
0x180025809  mov     rcx, [rdi+78h]
0x18002580d  mov     [rsp+140h+var_118], rax; __int64
0x180025812  lea     rax, [rbp+var_20]
0x180025816  mov     [rbp+var_68], rcx
0x18002581a  mov     rcx, r9; int
0x18002581d  mov     [rsp+140h+var_120], rax; __int64
0x180025822  mov     [rbp+var_28], 1000000h
0x18002582a  mov     [rbp+var_20], 0
0x180025832  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180025837  jmp     loc_1800258BD
0x18002583c  lea     rdx, [rbp+SRWLock]
0x180025840  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025845  mov     rax, [rbx+110h]
0x18002584c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180025850  mov     dword ptr [rax], 2
0x180025856  test    rcx, rcx
0x180025859  jz      short loc_180025861
0x18002585b  call    cs:__imp_ReleaseSRWLockExclusive
0x180025861  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025866  mov     rdi, rax
0x180025869  mov     ecx, [rax]
0x18002586b  cmp     ecx, 5
0x18002586e  jbe     short loc_1800258BD
0x180025870  call    cs:__imp_GetCurrentThreadId
0x180025876  mov     r8, [rbx+110h]
0x18002587d  lea     rdx, word_18002FE1E
0x180025884  mov     dword ptr [rbp+SRWLock], eax
0x180025887  lea     rax, [rbp+SRWLock]
0x18002588b  mov     [rsp+140h+var_110], rax
0x180025890  lea     rax, [rbp+arg_8]
0x180025894  mov     [rsp+140h+var_118], rax
0x180025899  lea     rax, [rbp+arg_10]
0x18002589d  mov     ecx, [r8+48h]
0x1800258a1  add     r8, 8
0x1800258a5  mov     dword ptr [rbp+arg_8], ecx
0x1800258a8  mov     rcx, rdi
0x1800258ab  mov     [rsp+140h+var_120], rax
0x1800258b0  mov     [rbp+arg_10], 0
0x1800258b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800258bd  mov     rcx, rbx
0x1800258c0  add     rsp, 130h
0x1800258c7  pop     rdi
0x1800258c8  pop     rbx
0x1800258c9  pop     rbp
0x1800258ca  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
