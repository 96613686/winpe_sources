# AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::Stop(bool)

- ea: `0x18007ae6c`
- end: `0x18007b1af`
- name: `?Stop@SessionManagerBrokerRegisterStagedAIFabricPackagesActivity@AIFabricTraceLogger@@QEAAX_N@Z`
- size: `835`
- prototype: `void __fastcall(AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007a7fc`

## callees

- `0x1800017dc`
- `0x180003b7c`
- `0x180004ca0`
- `0x1800625bc`
- `0x180065380`
- `0x18007ae6c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007aed8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b089`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007aed8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b0a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b13d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b0a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b13d`

## string_xrefs

- `0x18007b15b`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::Stop(
        AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *this,
        char a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // r9
  const struct _tlgProvider_t *v8; // rdi
  __int64 v9; // r8
  char *v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rax
  _BYTE v13[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v16; // [rsp+D0h] [rbp-70h] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  int v20; // [rsp+E4h] [rbp-5Ch] BYREF
  int v21; // [rsp+E8h] [rbp-58h] BYREF
  int v22; // [rsp+ECh] [rbp-54h] BYREF
  const wchar_t *v23; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v24; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v25; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v26; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v27; // [rsp+110h] [rbp-30h] BYREF
  const wchar_t *v28; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v29; // [rsp+120h] [rbp-20h] BYREF
  const wchar_t *v30; // [rsp+128h] [rbp-18h] BYREF
  const wchar_t *v31; // [rsp+130h] [rbp-10h] BYREF
  __int64 v32; // [rsp+138h] [rbp-8h] BYREF
  _BYTE v33[32]; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v34; // [rsp+160h] [rbp+20h]
  __int64 v35; // [rsp+168h] [rbp+28h]
  int *v36; // [rsp+170h] [rbp+30h]
  __int64 v37; // [rsp+178h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+40h]
  __int64 v39; // [rsp+188h] [rbp+48h]
  _BYTE *v40; // [rsp+190h] [rbp+50h]
  __int64 v41; // [rsp+198h] [rbp+58h]
  void *retaddr; // [rsp+1D8h] [rbp+98h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = AIFabricTraceLogger::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v13[0] = a2;
      v23 = (const wchar_t *)*((_QWORD *)v6 + 6);
      v17 = v6[17];
      v18 = v6[4];
      v24 = (const wchar_t *)*((_QWORD *)v6 + 15);
      v25 = (const wchar_t *)*((_QWORD *)v6 + 14);
      v19 = v6[26];
      v26 = (const wchar_t *)*((_QWORD *)v6 + 12);
      v27 = (const wchar_t *)*((_QWORD *)v6 + 11);
      v20 = v6[20];
      v28 = (const wchar_t *)*((_QWORD *)v6 + 9);
      v21 = v6[8];
      v29 = (const wchar_t *)*((_QWORD *)v6 + 3);
      v22 = *v6;
      v30 = (const wchar_t *)*((_QWORD *)v6 + 16);
      v14 = v6[16];
      v31 = (const wchar_t *)*((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v32 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
        (__int64)v7,
        (__int64)byte_18009E6CB,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v7,
        (__int64)&v16,
        (__int64)&v32,
        (__int64)&SRWLock,
        &v31,
        (__int64)&v14,
        &v30,
        (__int64)&v22,
        &v29,
        (__int64)&v21,
        &v28,
        (__int64)&v20,
        &v27,
        &v26,
        (__int64)&v19,
        &v25,
        &v24,
        (__int64)&v18,
        (__int64)&v17,
        &v23,
        (__int64)v13);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v16);
    **((_DWORD **)this + 34) = 2;
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    v8 = AIFabricTraceLogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      v13[0] = a2;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v14 = *(_DWORD *)(v9 + 72);
      v16 = 0;
      v40 = v13;
      v41 = 1;
      p_SRWLock = &SRWLock;
      v39 = 4;
      v36 = &v14;
      v37 = 4;
      v34 = &v16;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v8, &dword_18009E854, v9 + 8, 0, 6, v33);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( *((_DWORD *)v10 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v10 + 6) = 0;
    v11 = *(__int64 **)v10;
    while ( 1 )
    {
      v12 = *v11;
      if ( !*v11 )
        break;
      if ( (char *)v12 == v10 )
      {
        *v11 = *((_QWORD *)v10 + 2);
        break;
      }
      v11 = (__int64 *)(v12 + 16);
      *(_QWORD *)v10 = v12 + 16;
    }
    *(_QWORD *)v10 = 0;
  }
}

```

## disassembly

```asm
0x18007ae6c  push    rbp
0x18007ae6e  push    rbx
0x18007ae6f  push    rsi
0x18007ae70  push    rdi
0x18007ae71  lea     rbp, [rsp-78h]
0x18007ae76  sub     rsp, 1B8h
0x18007ae7d  mov     rax, cs:__security_cookie
0x18007ae84  xor     rax, rsp
0x18007ae87  mov     [rbp+90h+var_30], rax
0x18007ae8b  mov     sil, dl
0x18007ae8e  mov     rbx, rcx
0x18007ae91  mov     rdi, [rcx+110h]
0x18007ae98  mov     eax, [rdi+48h]
0x18007ae9b  test    eax, eax
0x18007ae9d  jns     loc_18007B06A
0x18007aea3  add     rdi, 50h ; 'P'
0x18007aea7  cmp     eax, [rdi+8]
0x18007aeaa  jnz     loc_18007B06A
0x18007aeb0  test    rdi, rdi
0x18007aeb3  jz      loc_18007B06A
0x18007aeb9  lea     rdx, [rbp+90h+SRWLock]
0x18007aebd  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007aec2  mov     rax, [rbx+110h]
0x18007aec9  mov     dword ptr [rax], 2
0x18007aecf  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x18007aed3  test    rcx, rcx
0x18007aed6  jz      short loc_18007AEDE
0x18007aed8  call    cs:__imp_ReleaseSRWLockExclusive
0x18007aede  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007aee3  mov     r9, rax
0x18007aee6  mov     ecx, [rax]
0x18007aee8  cmp     ecx, 5
0x18007aeeb  jbe     loc_18007B12D
0x18007aef1  mov     [rbp+90h+var_110], sil
0x18007aef5  mov     rcx, [rdi+30h]
0x18007aef9  mov     [rbp+90h+var_E0], rcx
0x18007aefd  mov     ecx, [rdi+44h]
0x18007af00  mov     [rbp+90h+var_F8], ecx
0x18007af03  mov     ecx, [rdi+10h]
0x18007af06  mov     [rbp+90h+var_F4], ecx
0x18007af09  mov     rcx, [rdi+78h]
0x18007af0d  mov     [rbp+90h+var_D8], rcx
0x18007af11  mov     rax, [rdi+70h]
0x18007af15  mov     [rbp+90h+var_D0], rax
0x18007af19  mov     eax, [rdi+68h]
0x18007af1c  mov     [rbp+90h+var_F0], eax
0x18007af1f  mov     rax, [rdi+60h]
0x18007af23  mov     [rbp+90h+var_C8], rax
0x18007af27  mov     rax, [rdi+58h]
0x18007af2b  mov     [rbp+90h+var_C0], rax
0x18007af2f  mov     eax, [rdi+50h]
0x18007af32  mov     [rbp+90h+var_EC], eax
0x18007af35  mov     rax, [rdi+48h]
0x18007af39  mov     [rbp+90h+var_B8], rax
0x18007af3d  mov     eax, [rdi+20h]
0x18007af40  mov     [rbp+90h+var_E8], eax
0x18007af43  mov     rax, [rdi+18h]
0x18007af47  mov     [rbp+90h+var_B0], rax
0x18007af4b  mov     eax, [rdi]
0x18007af4d  mov     [rbp+90h+var_E4], eax
0x18007af50  mov     rax, [rdi+80h]
0x18007af57  mov     [rbp+90h+var_A8], rax
0x18007af5b  mov     eax, [rdi+40h]
0x18007af5e  mov     [rbp+90h+var_10C], eax
0x18007af61  mov     rax, [rdi+38h]
0x18007af65  mov     [rbp+90h+var_A0], rax
0x18007af69  mov     eax, [rdi+8]
0x18007af6c  mov     dword ptr [rbp+90h+SRWLock], eax
0x18007af6f  mov     [rbp+90h+var_98], 1000000h
0x18007af77  mov     [rbp+90h+var_100], 0
0x18007af7f  mov     r8, [rbx+110h]
0x18007af86  add     r8, 8
0x18007af8a  lea     rax, [rbp+90h+var_110]
0x18007af8e  mov     [rsp+1D0h+var_118], rax
0x18007af96  lea     rax, [rbp+90h+var_E0]
0x18007af9a  mov     [rsp+1D0h+var_120], rax
0x18007afa2  lea     rax, [rbp+90h+var_F8]
0x18007afa6  mov     [rsp+1D0h+var_128], rax
0x18007afae  lea     rax, [rbp+90h+var_F4]
0x18007afb2  mov     [rsp+1D0h+var_130], rax
0x18007afba  lea     rax, [rbp+90h+var_D8]
0x18007afbe  mov     [rsp+1D0h+var_138], rax
0x18007afc6  lea     rax, [rbp+90h+var_D0]
0x18007afca  mov     [rsp+1D0h+var_140], rax
0x18007afd2  lea     rax, [rbp+90h+var_F0]
0x18007afd6  mov     [rsp+1D0h+var_148], rax
0x18007afde  lea     rax, [rbp+90h+var_C8]
0x18007afe2  mov     [rsp+1D0h+var_150], rax
0x18007afea  lea     rax, [rbp+90h+var_C0]
0x18007afee  mov     [rsp+1D0h+var_158], rax
0x18007aff3  lea     rax, [rbp+90h+var_EC]
0x18007aff7  mov     [rsp+1D0h+var_160], rax
0x18007affc  lea     rax, [rbp+90h+var_B8]
0x18007b000  mov     [rsp+1D0h+var_168], rax
0x18007b005  lea     rax, [rbp+90h+var_E8]
0x18007b009  mov     [rsp+1D0h+var_170], rax
0x18007b00e  lea     rax, [rbp+90h+var_B0]
0x18007b012  mov     [rsp+1D0h+var_178], rax
0x18007b017  lea     rax, [rbp+90h+var_E4]
0x18007b01b  mov     [rsp+1D0h+var_180], rax
0x18007b020  lea     rax, [rbp+90h+var_A8]
0x18007b024  mov     [rsp+1D0h+var_188], rax
0x18007b029  lea     rax, [rbp+90h+var_10C]
0x18007b02d  mov     [rsp+1D0h+var_190], rax
0x18007b032  lea     rax, [rbp+90h+var_A0]
0x18007b036  mov     [rsp+1D0h+var_198], rax
0x18007b03b  lea     rax, [rbp+90h+SRWLock]
0x18007b03f  mov     [rsp+1D0h+var_1A0], rax
0x18007b044  lea     rax, [rbp+90h+var_98]
0x18007b048  mov     [rsp+1D0h+var_1A8], rax
0x18007b04d  lea     rax, [rbp+90h+var_100]
0x18007b051  mov     [rsp+1D0h+var_1B0], rax
0x18007b056  lea     rdx, byte_18009E6CB
0x18007b05d  mov     rcx, r9
0x18007b060  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x18007b065  jmp     loc_18007B12D
0x18007b06a  lea     rdx, [rbp+90h+var_100]
0x18007b06e  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007b073  mov     rax, [rbx+110h]
0x18007b07a  mov     dword ptr [rax], 2
0x18007b080  mov     rcx, [rbp+90h+var_100]; SRWLock
0x18007b084  test    rcx, rcx
0x18007b087  jz      short loc_18007B08F
0x18007b089  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b08f  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007b094  mov     rdi, rax
0x18007b097  mov     ecx, [rax]
0x18007b099  cmp     ecx, 5
0x18007b09c  jbe     loc_18007B12D
0x18007b0a2  mov     [rbp+90h+var_110], sil
0x18007b0a6  call    cs:__imp_GetCurrentThreadId
0x18007b0ac  mov     dword ptr [rbp+90h+SRWLock], eax
0x18007b0af  mov     r8, [rbx+110h]
0x18007b0b6  mov     ecx, [r8+48h]
0x18007b0ba  mov     [rbp+90h+var_10C], ecx
0x18007b0bd  mov     [rbp+90h+var_100], 0
0x18007b0c5  lea     rax, [rbp+90h+var_110]
0x18007b0c9  mov     [rbp+90h+var_40], rax
0x18007b0cd  mov     [rbp+90h+var_38], 1
0x18007b0d5  lea     rax, [rbp+90h+SRWLock]
0x18007b0d9  mov     [rbp+90h+var_50], rax
0x18007b0dd  mov     [rbp+90h+var_48], 4
0x18007b0e5  lea     rax, [rbp+90h+var_10C]
0x18007b0e9  mov     [rbp+90h+var_60], rax
0x18007b0ed  mov     [rbp+90h+var_58], 4
0x18007b0f5  lea     rax, [rbp+90h+var_100]
0x18007b0f9  mov     [rbp+90h+var_70], rax
0x18007b0fd  mov     [rbp+90h+var_68], 8
0x18007b105  add     r8, 8
0x18007b109  lea     rax, [rbp+90h+var_90]
0x18007b10d  mov     [rsp+1D0h+var_1A8], rax
0x18007b112  mov     dword ptr [rsp+1D0h+var_1B0], 6
0x18007b11a  xor     r9d, r9d
0x18007b11d  lea     rdx, dword_18009E854
0x18007b124  mov     rcx, rdi
0x18007b127  call    _tlgWriteTransfer_EventWriteTransfer
0x18007b12c  nop
0x18007b12d  cmp     dword ptr [rbx+138h], 0
0x18007b134  jz      short loc_18007B197
0x18007b136  add     rbx, 120h
0x18007b13d  call    cs:__imp_GetCurrentThreadId
0x18007b143  cmp     [rbx+18h], eax
0x18007b146  jz      short loc_18007B167
0x18007b148  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18007b14f  test    rax, rax
0x18007b152  jz      short loc_18007B167
0x18007b154  mov     rdx, [rbp+98h]
0x18007b15b  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18007b162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b167  mov     dword ptr [rbx+18h], 0
0x18007b16e  mov     rcx, [rbx]
0x18007b171  jmp     short loc_18007B17F
0x18007b173  cmp     rax, rbx
0x18007b176  jz      short loc_18007B189
0x18007b178  lea     rcx, [rax+10h]
0x18007b17c  mov     [rbx], rcx
0x18007b17f  mov     rax, [rcx]
0x18007b182  test    rax, rax
0x18007b185  jnz     short loc_18007B173
0x18007b187  jmp     short loc_18007B190
0x18007b189  mov     rax, [rbx+10h]
0x18007b18d  mov     [rcx], rax
0x18007b190  mov     qword ptr [rbx], 0
0x18007b197  mov     rcx, [rbp+90h+var_30]
0x18007b19b  xor     rcx, rsp; StackCookie
0x18007b19e  call    __security_check_cookie
0x18007b1a3  add     rsp, 1B8h
0x18007b1aa  pop     rdi
0x18007b1ab  pop     rsi
0x18007b1ac  pop     rbx
0x18007b1ad  pop     rbp
0x18007b1ae  retn
```
