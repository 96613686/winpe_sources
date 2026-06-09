# FirewallUxTelemetry::AllowApplication::StopActivity(void)

- ea: `0x1800203d0`
- end: `0x18002063f`
- name: `?StopActivity@AllowApplication@FirewallUxTelemetry@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(FirewallUxTelemetry::AllowApplication *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x1800080a4`
- `0x18000812c`
- `0x180008820`
- `0x1800203d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002042a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800205cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002042a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800205cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205e0`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::AllowApplication::StopActivity(FirewallUxTelemetry::AllowApplication *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const wchar_t *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const wchar_t *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v7;
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)&unk_1800335D3,
        v8 + 8,
        (__int64)v6,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&unk_18003371E,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800203d0  push    rbp
0x1800203d2  push    rbx
0x1800203d3  push    rdi
0x1800203d4  lea     rbp, [rsp+10h]
0x1800203d9  sub     rsp, 130h
0x1800203e0  mov     rdi, [rcx+110h]
0x1800203e7  mov     rbx, rcx
0x1800203ea  mov     eax, [rdi+48h]
0x1800203ed  test    eax, eax
0x1800203ef  jns     loc_1800205AC
0x1800203f5  add     rdi, 50h ; 'P'
0x1800203f9  cmp     eax, [rdi+8]
0x1800203fc  jnz     loc_1800205AC
0x180020402  test    rdi, rdi
0x180020405  jz      loc_1800205AC
0x18002040b  lea     rdx, [rbp+SRWLock]
0x18002040f  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020414  mov     rax, [rbx+110h]
0x18002041b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002041f  mov     dword ptr [rax], 2
0x180020425  test    rcx, rcx
0x180020428  jz      short loc_180020430
0x18002042a  call    cs:__imp_ReleaseSRWLockExclusive
0x180020430  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180020435  mov     r9, rax
0x180020438  mov     ecx, [rax]
0x18002043a  cmp     ecx, 5
0x18002043d  jbe     loc_18002062D
0x180020443  mov     rax, [rdi+70h]
0x180020447  lea     rdx, unk_1800335D3
0x18002044e  mov     rcx, [rdi+30h]
0x180020452  mov     [rbp+var_60], rax
0x180020456  mov     eax, [rdi+68h]
0x180020459  mov     r8, [rbx+110h]
0x180020460  mov     dword ptr [rbp+arg_10], eax
0x180020463  add     r8, 8
0x180020467  mov     rax, [rdi+60h]
0x18002046b  mov     [rbp+var_58], rax
0x18002046f  mov     rax, [rdi+58h]
0x180020473  mov     [rbp+var_50], rax
0x180020477  mov     eax, [rdi+50h]
0x18002047a  mov     [rbp+arg_18], eax
0x18002047d  mov     rax, [rdi+48h]
0x180020481  mov     [rbp+var_48], rax
0x180020485  mov     eax, [rdi+20h]
0x180020488  mov     [rbp+var_80], eax
0x18002048b  mov     rax, [rdi+18h]
0x18002048f  mov     [rbp+var_40], rax
0x180020493  mov     eax, [rdi]
0x180020495  mov     [rbp+var_7C], eax
0x180020498  mov     rax, [rdi+80h]
0x18002049f  mov     [rbp+var_38], rax
0x1800204a3  mov     eax, [rdi+40h]
0x1800204a6  mov     [rbp+var_78], eax
0x1800204a9  mov     rax, [rdi+38h]
0x1800204ad  mov     [rbp+var_30], rax
0x1800204b1  mov     eax, [rdi+8]
0x1800204b4  mov     [rbp+var_74], eax
0x1800204b7  lea     rax, [rbp+var_70]
0x1800204bb  mov     [rsp+140h+var_90], rax
0x1800204c3  lea     rax, [rbp+SRWLock]
0x1800204c7  mov     [rsp+140h+var_98], rax
0x1800204cf  lea     rax, [rbp+arg_8]
0x1800204d3  mov     [rsp+140h+var_A0], rax
0x1800204db  lea     rax, [rbp+var_68]
0x1800204df  mov     [rsp+140h+var_A8], rax
0x1800204e7  lea     rax, [rbp+var_60]
0x1800204eb  mov     [rsp+140h+var_B0], rax
0x1800204f3  lea     rax, [rbp+arg_10]
0x1800204f7  mov     [rsp+140h+var_B8], rax
0x1800204ff  lea     rax, [rbp+var_58]
0x180020503  mov     [rsp+140h+var_C0], rax
0x18002050b  lea     rax, [rbp+var_50]
0x18002050f  mov     [rsp+140h+var_C8], rax
0x180020514  lea     rax, [rbp+arg_18]
0x180020518  mov     [rsp+140h+var_D0], rax
0x18002051d  lea     rax, [rbp+var_48]
0x180020521  mov     [rsp+140h+var_D8], rax
0x180020526  lea     rax, [rbp+var_80]
0x18002052a  mov     [rsp+140h+var_E0], rax
0x18002052f  lea     rax, [rbp+var_40]
0x180020533  mov     [rsp+140h+var_E8], rax
0x180020538  lea     rax, [rbp+var_7C]
0x18002053c  mov     [rsp+140h+var_F0], rax
0x180020541  lea     rax, [rbp+var_38]
0x180020545  mov     [rsp+140h+var_F8], rax
0x18002054a  lea     rax, [rbp+var_78]
0x18002054e  mov     [rsp+140h+var_100], rax
0x180020553  lea     rax, [rbp+var_30]
0x180020557  mov     [rsp+140h+var_108], rax
0x18002055c  lea     rax, [rbp+var_74]
0x180020560  mov     [rbp+var_70], rcx
0x180020564  mov     ecx, [rdi+44h]
0x180020567  mov     [rsp+140h+var_110], rax
0x18002056c  lea     rax, [rbp+var_28]
0x180020570  mov     dword ptr [rbp+SRWLock], ecx
0x180020573  mov     ecx, [rdi+10h]
0x180020576  mov     [rbp+arg_8], ecx
0x180020579  mov     rcx, [rdi+78h]
0x18002057d  mov     [rsp+140h+var_118], rax
0x180020582  lea     rax, [rbp+var_20]
0x180020586  mov     [rbp+var_68], rcx
0x18002058a  mov     rcx, r9
0x18002058d  mov     [rsp+140h+var_120], rax
0x180020592  mov     [rbp+var_28], 1000000h
0x18002059a  mov     [rbp+var_20], 0
0x1800205a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800205a7  jmp     loc_18002062D
0x1800205ac  lea     rdx, [rbp+SRWLock]
0x1800205b0  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800205b5  mov     rax, [rbx+110h]
0x1800205bc  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800205c0  mov     dword ptr [rax], 2
0x1800205c6  test    rcx, rcx
0x1800205c9  jz      short loc_1800205D1
0x1800205cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800205d1  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800205d6  mov     rdi, rax
0x1800205d9  mov     ecx, [rax]
0x1800205db  cmp     ecx, 5
0x1800205de  jbe     short loc_18002062D
0x1800205e0  call    cs:__imp_GetCurrentThreadId
0x1800205e6  mov     r8, [rbx+110h]
0x1800205ed  lea     rdx, unk_18003371E
0x1800205f4  mov     dword ptr [rbp+SRWLock], eax
0x1800205f7  lea     rax, [rbp+SRWLock]
0x1800205fb  mov     [rsp+140h+var_110], rax
0x180020600  lea     rax, [rbp+arg_8]
0x180020604  mov     [rsp+140h+var_118], rax
0x180020609  lea     rax, [rbp+arg_10]
0x18002060d  mov     ecx, [r8+48h]
0x180020611  add     r8, 8
0x180020615  mov     [rbp+arg_8], ecx
0x180020618  mov     rcx, rdi
0x18002061b  mov     [rsp+140h+var_120], rax
0x180020620  mov     [rbp+arg_10], 0
0x180020628  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002062d  mov     rcx, rbx
0x180020630  add     rsp, 130h
0x180020637  pop     rdi
0x180020638  pop     rbx
0x180020639  pop     rbp
0x18002063a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
