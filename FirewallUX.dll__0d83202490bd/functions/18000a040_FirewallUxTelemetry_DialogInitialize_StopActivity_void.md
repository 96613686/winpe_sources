# FirewallUxTelemetry::DialogInitialize::StopActivity(void)

- ea: `0x18000a040`
- end: `0x18000a2af`
- name: `?StopActivity@DialogInitialize@FirewallUxTelemetry@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(FirewallUxTelemetry::DialogInitialize *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x1800080a4`
- `0x18000812c`
- `0x180008820`
- `0x18000a040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a09a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a23b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a09a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a250`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::DialogInitialize::StopActivity(FirewallUxTelemetry::DialogInitialize *this)
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
        (__int64)&unk_1800329EA,
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
        (__int64)&unk_180032B35,
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
0x18000a040  push    rbp
0x18000a042  push    rbx
0x18000a043  push    rdi
0x18000a044  lea     rbp, [rsp+10h]
0x18000a049  sub     rsp, 130h
0x18000a050  mov     rdi, [rcx+110h]
0x18000a057  mov     rbx, rcx
0x18000a05a  mov     eax, [rdi+48h]
0x18000a05d  test    eax, eax
0x18000a05f  jns     loc_18000A21C
0x18000a065  add     rdi, 50h ; 'P'
0x18000a069  cmp     eax, [rdi+8]
0x18000a06c  jnz     loc_18000A21C
0x18000a072  test    rdi, rdi
0x18000a075  jz      loc_18000A21C
0x18000a07b  lea     rdx, [rbp+SRWLock]
0x18000a07f  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a084  mov     rax, [rbx+110h]
0x18000a08b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000a08f  mov     dword ptr [rax], 2
0x18000a095  test    rcx, rcx
0x18000a098  jz      short loc_18000A0A0
0x18000a09a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a0a0  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18000a0a5  mov     r9, rax
0x18000a0a8  mov     ecx, [rax]
0x18000a0aa  cmp     ecx, 5
0x18000a0ad  jbe     loc_18000A29D
0x18000a0b3  mov     rax, [rdi+70h]
0x18000a0b7  lea     rdx, unk_1800329EA
0x18000a0be  mov     rcx, [rdi+30h]
0x18000a0c2  mov     [rbp+var_60], rax
0x18000a0c6  mov     eax, [rdi+68h]
0x18000a0c9  mov     r8, [rbx+110h]
0x18000a0d0  mov     dword ptr [rbp+arg_10], eax
0x18000a0d3  add     r8, 8
0x18000a0d7  mov     rax, [rdi+60h]
0x18000a0db  mov     [rbp+var_58], rax
0x18000a0df  mov     rax, [rdi+58h]
0x18000a0e3  mov     [rbp+var_50], rax
0x18000a0e7  mov     eax, [rdi+50h]
0x18000a0ea  mov     [rbp+arg_18], eax
0x18000a0ed  mov     rax, [rdi+48h]
0x18000a0f1  mov     [rbp+var_48], rax
0x18000a0f5  mov     eax, [rdi+20h]
0x18000a0f8  mov     [rbp+var_80], eax
0x18000a0fb  mov     rax, [rdi+18h]
0x18000a0ff  mov     [rbp+var_40], rax
0x18000a103  mov     eax, [rdi]
0x18000a105  mov     [rbp+var_7C], eax
0x18000a108  mov     rax, [rdi+80h]
0x18000a10f  mov     [rbp+var_38], rax
0x18000a113  mov     eax, [rdi+40h]
0x18000a116  mov     [rbp+var_78], eax
0x18000a119  mov     rax, [rdi+38h]
0x18000a11d  mov     [rbp+var_30], rax
0x18000a121  mov     eax, [rdi+8]
0x18000a124  mov     [rbp+var_74], eax
0x18000a127  lea     rax, [rbp+var_70]
0x18000a12b  mov     [rsp+140h+var_90], rax
0x18000a133  lea     rax, [rbp+SRWLock]
0x18000a137  mov     [rsp+140h+var_98], rax
0x18000a13f  lea     rax, [rbp+arg_8]
0x18000a143  mov     [rsp+140h+var_A0], rax
0x18000a14b  lea     rax, [rbp+var_68]
0x18000a14f  mov     [rsp+140h+var_A8], rax
0x18000a157  lea     rax, [rbp+var_60]
0x18000a15b  mov     [rsp+140h+var_B0], rax
0x18000a163  lea     rax, [rbp+arg_10]
0x18000a167  mov     [rsp+140h+var_B8], rax
0x18000a16f  lea     rax, [rbp+var_58]
0x18000a173  mov     [rsp+140h+var_C0], rax
0x18000a17b  lea     rax, [rbp+var_50]
0x18000a17f  mov     [rsp+140h+var_C8], rax
0x18000a184  lea     rax, [rbp+arg_18]
0x18000a188  mov     [rsp+140h+var_D0], rax
0x18000a18d  lea     rax, [rbp+var_48]
0x18000a191  mov     [rsp+140h+var_D8], rax
0x18000a196  lea     rax, [rbp+var_80]
0x18000a19a  mov     [rsp+140h+var_E0], rax
0x18000a19f  lea     rax, [rbp+var_40]
0x18000a1a3  mov     [rsp+140h+var_E8], rax
0x18000a1a8  lea     rax, [rbp+var_7C]
0x18000a1ac  mov     [rsp+140h+var_F0], rax
0x18000a1b1  lea     rax, [rbp+var_38]
0x18000a1b5  mov     [rsp+140h+var_F8], rax
0x18000a1ba  lea     rax, [rbp+var_78]
0x18000a1be  mov     [rsp+140h+var_100], rax
0x18000a1c3  lea     rax, [rbp+var_30]
0x18000a1c7  mov     [rsp+140h+var_108], rax
0x18000a1cc  lea     rax, [rbp+var_74]
0x18000a1d0  mov     [rbp+var_70], rcx
0x18000a1d4  mov     ecx, [rdi+44h]
0x18000a1d7  mov     [rsp+140h+var_110], rax
0x18000a1dc  lea     rax, [rbp+var_28]
0x18000a1e0  mov     dword ptr [rbp+SRWLock], ecx
0x18000a1e3  mov     ecx, [rdi+10h]
0x18000a1e6  mov     [rbp+arg_8], ecx
0x18000a1e9  mov     rcx, [rdi+78h]
0x18000a1ed  mov     [rsp+140h+var_118], rax
0x18000a1f2  lea     rax, [rbp+var_20]
0x18000a1f6  mov     [rbp+var_68], rcx
0x18000a1fa  mov     rcx, r9
0x18000a1fd  mov     [rsp+140h+var_120], rax
0x18000a202  mov     [rbp+var_28], 1000000h
0x18000a20a  mov     [rbp+var_20], 0
0x18000a212  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a217  jmp     loc_18000A29D
0x18000a21c  lea     rdx, [rbp+SRWLock]
0x18000a220  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a225  mov     rax, [rbx+110h]
0x18000a22c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000a230  mov     dword ptr [rax], 2
0x18000a236  test    rcx, rcx
0x18000a239  jz      short loc_18000A241
0x18000a23b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a241  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18000a246  mov     rdi, rax
0x18000a249  mov     ecx, [rax]
0x18000a24b  cmp     ecx, 5
0x18000a24e  jbe     short loc_18000A29D
0x18000a250  call    cs:__imp_GetCurrentThreadId
0x18000a256  mov     r8, [rbx+110h]
0x18000a25d  lea     rdx, unk_180032B35
0x18000a264  mov     dword ptr [rbp+SRWLock], eax
0x18000a267  lea     rax, [rbp+SRWLock]
0x18000a26b  mov     [rsp+140h+var_110], rax
0x18000a270  lea     rax, [rbp+arg_8]
0x18000a274  mov     [rsp+140h+var_118], rax
0x18000a279  lea     rax, [rbp+arg_10]
0x18000a27d  mov     ecx, [r8+48h]
0x18000a281  add     r8, 8
0x18000a285  mov     [rbp+arg_8], ecx
0x18000a288  mov     rcx, rdi
0x18000a28b  mov     [rsp+140h+var_120], rax
0x18000a290  mov     [rbp+arg_10], 0
0x18000a298  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a29d  mov     rcx, rbx
0x18000a2a0  add     rsp, 130h
0x18000a2a7  pop     rdi
0x18000a2a8  pop     rbx
0x18000a2a9  pop     rbp
0x18000a2aa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
