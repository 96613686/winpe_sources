# MDMPushProvider::InternalRenewActivity::Stop(MDMPushProvider::TelemetryData const &)

- ea: `0x140029378`
- end: `0x140029719`
- name: `?Stop@InternalRenewActivity@MDMPushProvider@@QEAAXAEBUTelemetryData@2@@Z`
- size: `929`
- prototype: `void __fastcall(MDMPushProvider::InternalRenewActivity *__hidden this, const struct MDMPushProvider::TelemetryData *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002780c`

## callees

- `0x14000210c`
- `0x140002498`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x140029378`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400293d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400295ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400293d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400295ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002966f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002966f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MDMPushProvider::InternalRenewActivity::Stop(
        MDMPushProvider::InternalRenewActivity *this,
        const struct MDMPushProvider::TelemetryData *a2)
{
  __int64 v4; // rsi
  int v5; // eax
  int *v6; // rsi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  const OLECHAR *v10; // rdx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rax
  const OLECHAR *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+D0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+D4h] [rbp-7Ch] BYREF
  int v19; // [rsp+D8h] [rbp-78h] BYREF
  int v20; // [rsp+DCh] [rbp-74h] BYREF
  int v21; // [rsp+E0h] [rbp-70h] BYREF
  int v22; // [rsp+E4h] [rbp-6Ch] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-68h] BYREF
  const unsigned __int16 *v24; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+100h] [rbp-50h] BYREF
  __int64 v27; // [rsp+108h] [rbp-48h] BYREF
  const OLECHAR *v28; // [rsp+110h] [rbp-40h] BYREF
  const OLECHAR *v29; // [rsp+118h] [rbp-38h] BYREF
  const OLECHAR *v30; // [rsp+120h] [rbp-30h] BYREF
  const unsigned __int16 *v31; // [rsp+128h] [rbp-28h] BYREF
  const OLECHAR *v32; // [rsp+130h] [rbp-20h] BYREF
  const unsigned __int16 *v33; // [rsp+138h] [rbp-18h] BYREF
  const unsigned __int16 *v34; // [rsp+140h] [rbp-10h] BYREF
  const OLECHAR *v35; // [rsp+148h] [rbp-8h] BYREF
  PSRWLOCK SRWLock; // [rsp+170h] [rbp+20h] BYREF
  int v37; // [rsp+180h] [rbp+30h] BYREF
  int v38; // [rsp+188h] [rbp+38h] BYREF

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = MDMPushProvider::Provider();
    v8 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      v9 = *((_QWORD *)v7 + 3);
      if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
      {
        v27 = *((_QWORD *)a2 + 3);
        LODWORD(SRWLock) = *((_DWORD *)a2 + 5);
        v37 = *((_DWORD *)a2 + 3);
        v38 = *((_DWORD *)a2 + 2);
        if ( *((_DWORD *)a2 + 4) >= 9u )
          v10 = 0;
        else
          v10 = `GetPushStatusString'::`2'::pushStatusString[*((unsigned int *)a2 + 4)];
        v28 = v10;
        v29 = *(const OLECHAR **)a2;
        v30 = (const OLECHAR *)*((_QWORD *)v6 + 15);
        v31 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
        v19 = v6[26];
        v32 = (const OLECHAR *)*((_QWORD *)v6 + 12);
        v33 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
        v20 = v6[20];
        v34 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
        v21 = v6[8];
        v35 = (const OLECHAR *)*((_QWORD *)v6 + 3);
        v22 = *v6;
        v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
        v17 = v6[16];
        v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
        CurrentThreadId = v6[2];
        v25 = 0x1000000;
        v26 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v8,
          (__int64)byte_14006E859,
          *((_QWORD *)this + 34) + 8LL,
          v8,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&CurrentThreadId,
          &v24,
          (__int64)&v17,
          &v23,
          (__int64)&v22,
          &v35,
          (__int64)&v21,
          &v34,
          (__int64)&v20,
          &v33,
          &v32,
          (__int64)&v19,
          &v31,
          &v30,
          &v29,
          &v28,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&SRWLock,
          (__int64)&v27);
      }
    }
  }
  else
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v11 = MDMPushProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        v26 = *((_QWORD *)a2 + 3);
        LODWORD(SRWLock) = *((_DWORD *)a2 + 5);
        v37 = *((_DWORD *)a2 + 3);
        v38 = *((_DWORD *)a2 + 2);
        if ( *((_DWORD *)a2 + 4) >= 9u )
          v14 = 0;
        else
          v14 = `GetPushStatusString'::`2'::pushStatusString[*((unsigned int *)a2 + 4)];
        v25 = (__int64)v14;
        v24 = *(const unsigned __int16 **)a2;
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        v17 = *(_DWORD *)(v15 + 72);
        v23 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v12,
          (__int64)&unk_14006E150,
          v15 + 8,
          v16,
          (__int64)&v23,
          (__int64)&v17,
          (__int64)&CurrentThreadId,
          &v24,
          (const OLECHAR **)&v25,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&SRWLock,
          (__int64)&v26);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::InternalRenewActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140029378  mov     [rsp-18h+arg_8], rbx
0x14002937d  push    rbp
0x14002937e  push    rsi
0x14002937f  push    rdi
0x140029380  mov     rbp, rsp
0x140029383  sub     rsp, 150h
0x14002938a  mov     rbx, rdx
0x14002938d  mov     rdi, rcx
0x140029390  mov     rsi, [rcx+110h]
0x140029397  mov     eax, [rsi+48h]
0x14002939a  test    eax, eax
0x14002939c  jns     loc_1400295D0
0x1400293a2  add     rsi, 50h ; 'P'
0x1400293a6  cmp     eax, [rsi+8]
0x1400293a9  jnz     loc_1400295D0
0x1400293af  test    rsi, rsi
0x1400293b2  jz      loc_1400295D0
0x1400293b8  lea     rdx, [rbp+SRWLock]
0x1400293bc  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400293c1  mov     rax, [rdi+110h]
0x1400293c8  mov     dword ptr [rax], 2
0x1400293ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400293d2  test    rcx, rcx
0x1400293d5  jz      short loc_1400293DD
0x1400293d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400293dd  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400293e2  mov     r9, rax
0x1400293e5  mov     ecx, [rax]
0x1400293e7  cmp     ecx, 5
0x1400293ea  jbe     loc_1400296F3
0x1400293f0  mov     rax, [rax+18h]
0x1400293f4  mov     rcx, [r9+10h]
0x1400293f8  mov     rdx, 400000000000h
0x140029402  test    rdx, rcx
0x140029405  jz      loc_1400296F3
0x14002940b  mov     rcx, rax
0x14002940e  and     rcx, rdx
0x140029411  cmp     rcx, rax
0x140029414  jnz     loc_1400296F3
0x14002941a  mov     rax, [rbx+18h]
0x14002941e  mov     [rbp+var_48], rax
0x140029422  mov     eax, [rbx+14h]
0x140029425  mov     dword ptr [rbp+SRWLock], eax
0x140029428  mov     eax, [rbx+0Ch]
0x14002942b  mov     [rbp+arg_10], eax
0x14002942e  mov     eax, [rbx+8]
0x140029431  mov     [rbp+arg_18], eax
0x140029434  cmp     dword ptr [rbx+10h], 9
0x140029438  jnb     short loc_14002944A
0x14002943a  mov     eax, [rbx+10h]
0x14002943d  lea     rcx, ?pushStatusString@?1??GetPushStatusString@@YAPEBGK@Z@4PAPEBGA; ushort const * near * `GetPushStatusString(ulong)'::`2'::pushStatusString
0x140029444  mov     rdx, [rcx+rax*8]
0x140029448  jmp     short loc_14002944C
0x14002944a  xor     edx, edx
0x14002944c  mov     [rbp+var_40], rdx
0x140029450  mov     rax, [rbx]
0x140029453  mov     [rbp+var_38], rax
0x140029457  mov     rax, [rsi+78h]
0x14002945b  mov     [rbp+var_30], rax
0x14002945f  mov     rax, [rsi+70h]
0x140029463  mov     [rbp+var_28], rax
0x140029467  mov     eax, [rsi+68h]
0x14002946a  mov     [rbp+var_78], eax
0x14002946d  mov     rax, [rsi+60h]
0x140029471  mov     [rbp+var_20], rax
0x140029475  mov     rax, [rsi+58h]
0x140029479  mov     [rbp+var_18], rax
0x14002947d  mov     eax, [rsi+50h]
0x140029480  mov     [rbp+var_74], eax
0x140029483  mov     rax, [rsi+48h]
0x140029487  mov     [rbp+var_10], rax
0x14002948b  mov     eax, [rsi+20h]
0x14002948e  mov     [rbp+var_70], eax
0x140029491  mov     rax, [rsi+18h]
0x140029495  mov     [rbp+var_8], rax
0x140029499  mov     eax, [rsi]
0x14002949b  mov     [rbp+var_6C], eax
0x14002949e  mov     rax, [rsi+80h]
0x1400294a5  mov     [rbp+var_68], rax
0x1400294a9  mov     eax, [rsi+40h]
0x1400294ac  mov     [rbp+var_80], eax
0x1400294af  mov     rax, [rsi+38h]
0x1400294b3  mov     [rbp+var_60], rax
0x1400294b7  mov     eax, [rsi+8]
0x1400294ba  mov     [rbp+var_7C], eax
0x1400294bd  mov     [rbp+var_58], 1000000h
0x1400294c5  mov     [rbp+var_50], 0
0x1400294cd  mov     r8, [rdi+110h]
0x1400294d4  add     r8, 8
0x1400294d8  lea     rax, [rbp+var_48]
0x1400294dc  mov     [rsp+150h+var_88], rax
0x1400294e4  lea     rax, [rbp+SRWLock]
0x1400294e8  mov     [rsp+150h+var_90], rax
0x1400294f0  lea     rax, [rbp+arg_10]
0x1400294f4  mov     [rsp+150h+var_98], rax
0x1400294fc  lea     rax, [rbp+arg_18]
0x140029500  mov     [rsp+150h+var_A0], rax
0x140029508  lea     rax, [rbp+var_40]
0x14002950c  mov     [rsp+150h+var_A8], rax
0x140029514  lea     rax, [rbp+var_38]
0x140029518  mov     [rsp+150h+var_B0], rax
0x140029520  lea     rax, [rbp+var_30]
0x140029524  mov     [rsp+150h+var_B8], rax
0x14002952c  lea     rax, [rbp+var_28]
0x140029530  mov     [rsp+150h+var_C0], rax
0x140029538  lea     rax, [rbp+var_78]
0x14002953c  mov     [rsp+150h+var_C8], rax
0x140029544  lea     rax, [rbp+var_20]
0x140029548  mov     [rsp+150h+var_D0], rax
0x140029550  lea     rax, [rbp+var_18]
0x140029554  mov     [rsp+150h+var_D8], rax
0x140029559  lea     rax, [rbp+var_74]
0x14002955d  mov     [rsp+150h+var_E0], rax
0x140029562  lea     rax, [rbp+var_10]
0x140029566  mov     [rsp+150h+var_E8], rax
0x14002956b  lea     rax, [rbp+var_70]
0x14002956f  mov     [rsp+150h+var_F0], rax
0x140029574  lea     rax, [rbp+var_8]
0x140029578  mov     [rsp+150h+var_F8], rax
0x14002957d  lea     rax, [rbp+var_6C]
0x140029581  mov     [rsp+150h+var_100], rax
0x140029586  lea     rax, [rbp+var_68]
0x14002958a  mov     [rsp+150h+var_108], rax
0x14002958f  lea     rax, [rbp+var_80]
0x140029593  mov     [rsp+150h+var_110], rax
0x140029598  lea     rax, [rbp+var_60]
0x14002959c  mov     [rsp+150h+var_118], rax
0x1400295a1  lea     rax, [rbp+var_7C]
0x1400295a5  mov     [rsp+150h+var_120], rax
0x1400295aa  lea     rax, [rbp+var_58]
0x1400295ae  mov     [rsp+150h+var_128], rax
0x1400295b3  lea     rax, [rbp+var_50]
0x1400295b7  mov     [rsp+150h+var_130], rax
0x1400295bc  lea     rdx, byte_14006E859
0x1400295c3  mov     rcx, r9
0x1400295c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U2@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456664443@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400295cb  jmp     loc_1400296F3
0x1400295d0  lea     rdx, [rbp+SRWLock]
0x1400295d4  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400295d9  mov     rax, [rdi+110h]
0x1400295e0  mov     dword ptr [rax], 2
0x1400295e6  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400295ea  test    rcx, rcx
0x1400295ed  jz      short loc_1400295F5
0x1400295ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1400295f5  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400295fa  mov     rsi, rax
0x1400295fd  mov     ecx, [rax]
0x1400295ff  cmp     ecx, 5
0x140029602  jbe     loc_1400296F3
0x140029608  mov     rax, [rax+18h]
0x14002960c  mov     rcx, [rsi+10h]
0x140029610  mov     rdx, 400000000000h
0x14002961a  test    rdx, rcx
0x14002961d  jz      loc_1400296F3
0x140029623  mov     rcx, rax
0x140029626  and     rcx, rdx
0x140029629  cmp     rcx, rax
0x14002962c  jnz     loc_1400296F3
0x140029632  mov     rax, [rbx+18h]
0x140029636  mov     [rbp+var_50], rax
0x14002963a  mov     eax, [rbx+14h]
0x14002963d  mov     dword ptr [rbp+SRWLock], eax
0x140029640  mov     eax, [rbx+0Ch]
0x140029643  mov     [rbp+arg_10], eax
0x140029646  mov     eax, [rbx+8]
0x140029649  mov     [rbp+arg_18], eax
0x14002964c  cmp     dword ptr [rbx+10h], 9
0x140029650  jnb     short loc_140029662
0x140029652  mov     eax, [rbx+10h]
0x140029655  lea     rcx, ?pushStatusString@?1??GetPushStatusString@@YAPEBGK@Z@4PAPEBGA; ushort const * near * `GetPushStatusString(ulong)'::`2'::pushStatusString
0x14002965c  mov     rdx, [rcx+rax*8]
0x140029660  jmp     short loc_140029664
0x140029662  xor     edx, edx
0x140029664  mov     [rbp+var_58], rdx
0x140029668  mov     rax, [rbx]
0x14002966b  mov     [rbp+var_60], rax
0x14002966f  call    cs:__imp_GetCurrentThreadId
0x140029675  mov     [rbp+var_7C], eax
0x140029678  mov     r8, [rdi+110h]
0x14002967f  mov     eax, [r8+48h]
0x140029683  mov     [rbp+var_80], eax
0x140029686  mov     [rbp+var_68], 0
0x14002968e  add     r8, 8
0x140029692  lea     rax, [rbp+var_50]
0x140029696  mov     [rsp+150h+var_F0], rax
0x14002969b  lea     rax, [rbp+SRWLock]
0x14002969f  mov     [rsp+150h+var_F8], rax
0x1400296a4  lea     rax, [rbp+arg_10]
0x1400296a8  mov     [rsp+150h+var_100], rax
0x1400296ad  lea     rax, [rbp+arg_18]
0x1400296b1  mov     [rsp+150h+var_108], rax
0x1400296b6  lea     rax, [rbp+var_58]
0x1400296ba  mov     [rsp+150h+var_110], rax
0x1400296bf  lea     rax, [rbp+var_60]
0x1400296c3  mov     [rsp+150h+var_118], rax
0x1400296c8  lea     rax, [rbp+var_7C]
0x1400296cc  mov     [rsp+150h+var_120], rax
0x1400296d1  lea     rax, [rbp+var_80]
0x1400296d5  mov     [rsp+150h+var_128], rax
0x1400296da  lea     rax, [rbp+var_68]
0x1400296de  mov     [rsp+150h+var_130], rax
0x1400296e3  lea     rdx, unk_14006E150
0x1400296ea  mov     rcx, rsi
0x1400296ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U2@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@54443@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400296f2  nop
0x1400296f3  lea     rcx, [rdi+120h]; this
0x1400296fa  cmp     dword ptr [rcx+18h], 0
0x1400296fe  jz      short loc_140029706
0x140029700  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140029705  nop
0x140029706  mov     rbx, [rsp+150h+arg_8]
0x14002970e  add     rsp, 150h
0x140029715  pop     rdi
0x140029716  pop     rsi
0x140029717  pop     rbp
0x140029718  retn
```
