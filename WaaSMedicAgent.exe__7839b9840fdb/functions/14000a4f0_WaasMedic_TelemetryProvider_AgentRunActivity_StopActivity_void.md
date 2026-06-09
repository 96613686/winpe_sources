# WaasMedic::TelemetryProvider::AgentRunActivity::StopActivity(void)

- ea: `0x14000a4f0`
- end: `0x14000a7ce`
- name: `?StopActivity@AgentRunActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `734`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AgentRunActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x140001008`
- `0x14000198c`
- `0x140002a30`
- `0x14000827c`
- `0x14000830c`
- `0x14000885c`
- `0x14000a4f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a55f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a6ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a55f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a6ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a72e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a72e`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AgentRunActivity::StopActivity(
        WaasMedic::TelemetryProvider::AgentRunActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B8h] [rbp-68h] BYREF
  int v20; // [rsp+BCh] [rbp-64h] BYREF
  int v21; // [rsp+C0h] [rbp-60h] BYREF
  int v22; // [rsp+C4h] [rbp-5Ch] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WaasMedic::TelemetryProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_140019D1D,
          v9 + 8,
          v7,
          (__int64)&v18,
          (__int64)&v31,
          (__int64)&SRWLock,
          &v30,
          (__int64)&v16,
          &v29,
          (__int64)&v22,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          &v25,
          (__int64)&v19,
          &v24,
          &v23);
      }
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WaasMedic::TelemetryProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        v18 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, byte_140019E45, v15 + 8, 0, 5, v32);
      }
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000a4f0  mov     [rsp-8+arg_8], rbx
0x14000a4f5  mov     [rsp-8+arg_10], rdi
0x14000a4fa  push    rbp
0x14000a4fb  lea     rbp, [rsp-50h]
0x14000a500  sub     rsp, 170h
0x14000a507  mov     rax, cs:__security_cookie
0x14000a50e  xor     rax, rsp
0x14000a511  mov     [rbp+50h+var_10], rax
0x14000a515  mov     rdi, [rcx+110h]
0x14000a51c  mov     rbx, rcx
0x14000a51f  mov     eax, [rdi+48h]
0x14000a522  test    eax, eax
0x14000a524  jns     loc_14000A6D0
0x14000a52a  add     rdi, 50h ; 'P'
0x14000a52e  cmp     eax, [rdi+8]
0x14000a531  jnz     loc_14000A6D0
0x14000a537  test    rdi, rdi
0x14000a53a  jz      loc_14000A6D0
0x14000a540  lea     rdx, [rbp+50h+SRWLock]
0x14000a544  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000a549  mov     rax, [rbx+110h]
0x14000a550  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x14000a554  mov     dword ptr [rax], 2
0x14000a55a  test    rcx, rcx
0x14000a55d  jz      short loc_14000A565
0x14000a55f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a565  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000a56a  mov     r9, rax
0x14000a56d  mov     ecx, [rax]
0x14000a56f  cmp     ecx, 5
0x14000a572  jbe     loc_14000A7A5
0x14000a578  mov     rax, [rax+18h]
0x14000a57c  mov     rdx, 400000000000h
0x14000a586  mov     rcx, [r9+10h]
0x14000a58a  test    rdx, rcx
0x14000a58d  jz      loc_14000A7A5
0x14000a593  mov     rcx, rax
0x14000a596  and     rcx, rdx
0x14000a599  cmp     rcx, rax
0x14000a59c  jnz     loc_14000A7A5
0x14000a5a2  mov     rax, [rdi+78h]
0x14000a5a6  lea     rdx, byte_140019D1D
0x14000a5ad  mov     r8, [rbx+110h]
0x14000a5b4  mov     rcx, r9
0x14000a5b7  mov     [rbp+50h+var_A8], rax
0x14000a5bb  add     r8, 8
0x14000a5bf  mov     rax, [rdi+70h]
0x14000a5c3  mov     [rbp+50h+var_A0], rax
0x14000a5c7  mov     eax, [rdi+68h]
0x14000a5ca  mov     [rbp+50h+var_B8], eax
0x14000a5cd  mov     rax, [rdi+60h]
0x14000a5d1  mov     [rbp+50h+var_98], rax
0x14000a5d5  mov     rax, [rdi+58h]
0x14000a5d9  mov     [rbp+50h+var_90], rax
0x14000a5dd  mov     eax, [rdi+50h]
0x14000a5e0  mov     [rbp+50h+var_B4], eax
0x14000a5e3  mov     rax, [rdi+48h]
0x14000a5e7  mov     [rbp+50h+var_88], rax
0x14000a5eb  mov     eax, [rdi+20h]
0x14000a5ee  mov     [rbp+50h+var_B0], eax
0x14000a5f1  mov     rax, [rdi+18h]
0x14000a5f5  mov     [rbp+50h+var_80], rax
0x14000a5f9  mov     eax, [rdi]
0x14000a5fb  mov     [rbp+50h+var_AC], eax
0x14000a5fe  mov     rax, [rdi+80h]
0x14000a605  mov     [rbp+50h+var_78], rax
0x14000a609  mov     eax, [rdi+40h]
0x14000a60c  mov     [rbp+50h+var_D0], eax
0x14000a60f  mov     rax, [rdi+38h]
0x14000a613  mov     [rbp+50h+var_70], rax
0x14000a617  mov     eax, [rdi+8]
0x14000a61a  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000a61d  mov     eax, 1000000h
0x14000a622  mov     [rbp+50h+var_68], rax
0x14000a626  mov     [rbp+50h+var_C0], rax
0x14000a62a  lea     rax, [rbp+50h+var_A8]
0x14000a62e  mov     [rsp+170h+var_D8], rax
0x14000a636  lea     rax, [rbp+50h+var_A0]
0x14000a63a  mov     [rsp+170h+var_E0], rax
0x14000a642  lea     rax, [rbp+50h+var_B8]
0x14000a646  mov     [rsp+170h+var_E8], rax
0x14000a64e  lea     rax, [rbp+50h+var_98]
0x14000a652  mov     [rsp+170h+var_F0], rax
0x14000a65a  lea     rax, [rbp+50h+var_90]
0x14000a65e  mov     [rsp+170h+var_F8], rax
0x14000a663  lea     rax, [rbp+50h+var_B4]
0x14000a667  mov     [rsp+170h+var_100], rax
0x14000a66c  lea     rax, [rbp+50h+var_88]
0x14000a670  mov     [rsp+170h+var_108], rax
0x14000a675  lea     rax, [rbp+50h+var_B0]
0x14000a679  mov     [rsp+170h+var_110], rax
0x14000a67e  lea     rax, [rbp+50h+var_80]
0x14000a682  mov     [rsp+170h+var_118], rax
0x14000a687  lea     rax, [rbp+50h+var_AC]
0x14000a68b  mov     [rsp+170h+var_120], rax
0x14000a690  lea     rax, [rbp+50h+var_78]
0x14000a694  mov     [rsp+170h+var_128], rax
0x14000a699  lea     rax, [rbp+50h+var_D0]
0x14000a69d  mov     [rsp+170h+var_130], rax
0x14000a6a2  lea     rax, [rbp+50h+var_70]
0x14000a6a6  mov     [rsp+170h+var_138], rax
0x14000a6ab  lea     rax, [rbp+50h+SRWLock]
0x14000a6af  mov     [rsp+170h+var_140], rax
0x14000a6b4  lea     rax, [rbp+50h+var_68]
0x14000a6b8  mov     [rsp+170h+var_148], rax
0x14000a6bd  lea     rax, [rbp+50h+var_C0]
0x14000a6c1  mov     [rsp+170h+var_150], rax
0x14000a6c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000a6cb  jmp     loc_14000A7A5
0x14000a6d0  lea     rdx, [rbp+50h+var_C0]
0x14000a6d4  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000a6d9  mov     rax, [rbx+110h]
0x14000a6e0  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x14000a6e4  mov     dword ptr [rax], 2
0x14000a6ea  test    rcx, rcx
0x14000a6ed  jz      short loc_14000A6F5
0x14000a6ef  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a6f5  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000a6fa  mov     rdi, rax
0x14000a6fd  mov     ecx, [rax]
0x14000a6ff  cmp     ecx, 5
0x14000a702  jbe     loc_14000A7A5
0x14000a708  mov     rax, [rax+18h]
0x14000a70c  mov     rdx, 400000000000h
0x14000a716  mov     rcx, [rdi+10h]
0x14000a71a  test    rdx, rcx
0x14000a71d  jz      loc_14000A7A5
0x14000a723  mov     rcx, rax
0x14000a726  and     rcx, rdx
0x14000a729  cmp     rcx, rax
0x14000a72c  jnz     short loc_14000A7A5
0x14000a72e  call    cs:__imp_GetCurrentThreadId
0x14000a734  mov     r8, [rbx+110h]
0x14000a73b  lea     rdx, byte_140019E45
0x14000a742  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000a745  xor     r9d, r9d
0x14000a748  mov     rcx, rdi
0x14000a74b  mov     [rbp+50h+var_18], 4
0x14000a753  mov     [rbp+50h+var_28], 4
0x14000a75b  mov     eax, [r8+48h]
0x14000a75f  add     r8, 8
0x14000a763  mov     [rbp+50h+var_D0], eax
0x14000a766  mov     eax, 1000000h
0x14000a76b  mov     [rbp+50h+var_C0], rax
0x14000a76f  lea     rax, [rbp+50h+SRWLock]
0x14000a773  mov     [rbp+50h+var_20], rax
0x14000a777  lea     rax, [rbp+50h+var_D0]
0x14000a77b  mov     [rbp+50h+var_30], rax
0x14000a77f  lea     rax, [rbp+50h+var_C0]
0x14000a783  mov     [rbp+50h+var_40], rax
0x14000a787  lea     rax, [rbp+50h+var_60]
0x14000a78b  mov     [rsp+170h+var_148], rax
0x14000a790  mov     dword ptr [rsp+170h+var_150], 5
0x14000a798  mov     [rbp+50h+var_38], 8
0x14000a7a0  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a7a5  mov     rcx, rbx
0x14000a7a8  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000a7ad  mov     rcx, [rbp+50h+var_10]
0x14000a7b1  xor     rcx, rsp; StackCookie
0x14000a7b4  call    __security_check_cookie
0x14000a7b9  lea     r11, [rsp+170h+var_s0]
0x14000a7c1  mov     rbx, [r11+18h]
0x14000a7c5  mov     rdi, [r11+20h]
0x14000a7c9  mov     rsp, r11
0x14000a7cc  pop     rbp
0x14000a7cd  retn
```
