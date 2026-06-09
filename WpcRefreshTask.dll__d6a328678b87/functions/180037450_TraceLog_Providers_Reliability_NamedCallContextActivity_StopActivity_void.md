# TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(void)

- ea: `0x180037450`
- end: `0x1800376ca`
- name: `?StopActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(TraceLog::Providers::Reliability::NamedCallContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180036d18`
- `0x180037450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003765d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003765d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800374aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037648`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800374aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037648`

## pseudocode

```c
void __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(
        TraceLog::Providers::Reliability::NamedCallContextActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v5 > 4u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&byte_1800D565F,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&word_1800D5606,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((TraceLog::Providers::Reliability::NamedCallContextActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180037450  push    rbp
0x180037452  push    rbx
0x180037453  push    rdi
0x180037454  lea     rbp, [rsp+10h]
0x180037459  sub     rsp, 130h
0x180037460  mov     rbx, rcx
0x180037463  mov     rdi, [rcx+110h]
0x18003746a  mov     eax, [rdi+48h]
0x18003746d  test    eax, eax
0x18003746f  jns     loc_180037629
0x180037475  add     rdi, 50h ; 'P'
0x180037479  cmp     eax, [rdi+8]
0x18003747c  jnz     loc_180037629
0x180037482  test    rdi, rdi
0x180037485  jz      loc_180037629
0x18003748b  lea     rdx, [rbp+SRWLock]
0x18003748f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180037494  mov     rax, [rbx+110h]
0x18003749b  mov     dword ptr [rax], 2
0x1800374a1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800374a5  test    rcx, rcx
0x1800374a8  jz      short loc_1800374B0
0x1800374aa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800374b0  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x1800374b5  mov     r9, rax
0x1800374b8  mov     ecx, [rax]
0x1800374ba  cmp     ecx, 4
0x1800374bd  jbe     loc_1800376AC
0x1800374c3  mov     rcx, [rdi+30h]
0x1800374c7  mov     [rbp+var_70], rcx
0x1800374cb  mov     ecx, [rdi+44h]
0x1800374ce  mov     dword ptr [rbp+SRWLock], ecx
0x1800374d1  mov     ecx, [rdi+10h]
0x1800374d4  mov     [rbp+arg_8], ecx
0x1800374d7  mov     rcx, [rdi+78h]
0x1800374db  mov     [rbp+var_68], rcx
0x1800374df  mov     rax, [rdi+70h]
0x1800374e3  mov     [rbp+var_60], rax
0x1800374e7  mov     eax, [rdi+68h]
0x1800374ea  mov     dword ptr [rbp+arg_10], eax
0x1800374ed  mov     rax, [rdi+60h]
0x1800374f1  mov     [rbp+var_58], rax
0x1800374f5  mov     rax, [rdi+58h]
0x1800374f9  mov     [rbp+var_50], rax
0x1800374fd  mov     eax, [rdi+50h]
0x180037500  mov     [rbp+arg_18], eax
0x180037503  mov     rax, [rdi+48h]
0x180037507  mov     [rbp+var_48], rax
0x18003750b  mov     eax, [rdi+20h]
0x18003750e  mov     [rbp+var_80], eax
0x180037511  mov     rax, [rdi+18h]
0x180037515  mov     [rbp+var_40], rax
0x180037519  mov     eax, [rdi]
0x18003751b  mov     [rbp+var_7C], eax
0x18003751e  mov     rax, [rdi+80h]
0x180037525  mov     [rbp+var_38], rax
0x180037529  mov     eax, [rdi+40h]
0x18003752c  mov     [rbp+var_78], eax
0x18003752f  mov     rax, [rdi+38h]
0x180037533  mov     [rbp+var_30], rax
0x180037537  mov     eax, [rdi+8]
0x18003753a  mov     [rbp+var_74], eax
0x18003753d  mov     eax, 1000000h
0x180037542  mov     [rbp+var_28], rax
0x180037546  mov     [rbp+var_20], rax
0x18003754a  mov     r8, [rbx+110h]
0x180037551  add     r8, 8
0x180037555  lea     rax, [rbp+var_70]
0x180037559  mov     [rsp+140h+var_90], rax
0x180037561  lea     rax, [rbp+SRWLock]
0x180037565  mov     [rsp+140h+var_98], rax
0x18003756d  lea     rax, [rbp+arg_8]
0x180037571  mov     [rsp+140h+var_A0], rax
0x180037579  lea     rax, [rbp+var_68]
0x18003757d  mov     [rsp+140h+var_A8], rax
0x180037585  lea     rax, [rbp+var_60]
0x180037589  mov     [rsp+140h+var_B0], rax
0x180037591  lea     rax, [rbp+arg_10]
0x180037595  mov     [rsp+140h+var_B8], rax
0x18003759d  lea     rax, [rbp+var_58]
0x1800375a1  mov     [rsp+140h+var_C0], rax
0x1800375a9  lea     rax, [rbp+var_50]
0x1800375ad  mov     [rsp+140h+var_C8], rax
0x1800375b2  lea     rax, [rbp+arg_18]
0x1800375b6  mov     [rsp+140h+var_D0], rax
0x1800375bb  lea     rax, [rbp+var_48]
0x1800375bf  mov     [rsp+140h+var_D8], rax
0x1800375c4  lea     rax, [rbp+var_80]
0x1800375c8  mov     [rsp+140h+var_E0], rax
0x1800375cd  lea     rax, [rbp+var_40]
0x1800375d1  mov     [rsp+140h+var_E8], rax
0x1800375d6  lea     rax, [rbp+var_7C]
0x1800375da  mov     [rsp+140h+var_F0], rax
0x1800375df  lea     rax, [rbp+var_38]
0x1800375e3  mov     [rsp+140h+var_F8], rax
0x1800375e8  lea     rax, [rbp+var_78]
0x1800375ec  mov     [rsp+140h+var_100], rax
0x1800375f1  lea     rax, [rbp+var_30]
0x1800375f5  mov     [rsp+140h+var_108], rax
0x1800375fa  lea     rax, [rbp+var_74]
0x1800375fe  mov     [rsp+140h+var_110], rax
0x180037603  lea     rax, [rbp+var_28]
0x180037607  mov     [rsp+140h+var_118], rax
0x18003760c  lea     rax, [rbp+var_20]
0x180037610  mov     [rsp+140h+var_120], rax
0x180037615  lea     rdx, byte_1800D565F
0x18003761c  mov     rcx, r9
0x18003761f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180037624  jmp     loc_1800376AC
0x180037629  lea     rdx, [rbp+SRWLock]
0x18003762d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180037632  mov     rax, [rbx+110h]
0x180037639  mov     dword ptr [rax], 2
0x18003763f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180037643  test    rcx, rcx
0x180037646  jz      short loc_18003764E
0x180037648  call    cs:__imp_ReleaseSRWLockExclusive
0x18003764e  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180037653  mov     rdi, rax
0x180037656  mov     ecx, [rax]
0x180037658  cmp     ecx, 4
0x18003765b  jbe     short loc_1800376AC
0x18003765d  call    cs:__imp_GetCurrentThreadId
0x180037663  mov     dword ptr [rbp+SRWLock], eax
0x180037666  mov     r8, [rbx+110h]
0x18003766d  mov     ecx, [r8+48h]
0x180037671  mov     [rbp+arg_8], ecx
0x180037674  mov     eax, 1000000h
0x180037679  mov     [rbp+arg_10], rax
0x18003767d  add     r8, 8
0x180037681  lea     rax, [rbp+SRWLock]
0x180037685  mov     [rsp+140h+var_110], rax
0x18003768a  lea     rax, [rbp+arg_8]
0x18003768e  mov     [rsp+140h+var_118], rax
0x180037693  lea     rax, [rbp+arg_10]
0x180037697  mov     [rsp+140h+var_120], rax
0x18003769c  lea     rdx, word_1800D5606
0x1800376a3  mov     rcx, rdi
0x1800376a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800376ab  nop
0x1800376ac  lea     rcx, [rbx+120h]; this
0x1800376b3  cmp     dword ptr [rcx+18h], 0
0x1800376b7  jz      short loc_1800376BF
0x1800376b9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800376be  nop
0x1800376bf  add     rsp, 130h
0x1800376c6  pop     rdi
0x1800376c7  pop     rbx
0x1800376c8  pop     rbp
0x1800376c9  retn
```
