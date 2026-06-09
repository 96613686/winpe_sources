# PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StopActivity(void)

- ea: `0x18002e980`
- end: `0x18002ecbe`
- name: `?StopActivity@GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@MEAAXXZ`
- size: `830`
- prototype: `void __fastcall(PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800013a4`
- `0x180001c7c`
- `0x18002b340`
- `0x18002befc`
- `0x18002e980`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ebbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ec46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ebbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ec46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e9ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eb7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e9ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eb7f`

## string_xrefs

- `0x18002ec61`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StopActivity(
        PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B8h] [rbp-68h] BYREF
  int v19; // [rsp+BCh] [rbp-64h] BYREF
  int v20; // [rsp+C0h] [rbp-60h] BYREF
  int v21; // [rsp+C4h] [rbp-5Ch] BYREF
  int *v22; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-50h] BYREF
  int *v24; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-38h] BYREF
  int *v27; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = PowerGridForecastTaskTelemetry::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        v22 = (int *)*((_QWORD *)v4 + 15);
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = (int *)*((_QWORD *)v4 + 12);
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = (int *)*((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&byte_18003E937,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          &v29,
          (__int64)&v15,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          (__int64)&v19,
          &v25,
          &v24,
          (__int64)&v18,
          &v23,
          &v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = PowerGridForecastTaskTelemetry::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, byte_18003E8D5, v11 + 8, 0, 5, v31);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x18002e980  mov     [rsp-8+arg_8], rbx
0x18002e985  mov     [rsp-8+arg_10], rdi
0x18002e98a  push    rbp
0x18002e98b  lea     rbp, [rsp-50h]
0x18002e990  sub     rsp, 170h
0x18002e997  mov     rax, cs:__security_cookie
0x18002e99e  xor     rax, rsp
0x18002e9a1  mov     [rbp+50h+var_10], rax
0x18002e9a5  mov     rbx, rcx
0x18002e9a8  mov     rdi, [rcx+110h]
0x18002e9af  mov     eax, [rdi+48h]
0x18002e9b2  test    eax, eax
0x18002e9b4  jns     loc_18002EB60
0x18002e9ba  add     rdi, 50h ; 'P'
0x18002e9be  cmp     eax, [rdi+8]
0x18002e9c1  jnz     loc_18002EB60
0x18002e9c7  test    rdi, rdi
0x18002e9ca  jz      loc_18002EB60
0x18002e9d0  lea     rdx, [rbp+50h+SRWLock]
0x18002e9d4  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e9d9  mov     rax, [rbx+110h]
0x18002e9e0  mov     dword ptr [rax], 2
0x18002e9e6  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18002e9ea  test    rcx, rcx
0x18002e9ed  jz      short loc_18002E9F5
0x18002e9ef  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e9f5  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002e9fa  mov     r9, rax
0x18002e9fd  mov     ecx, [rax]
0x18002e9ff  cmp     ecx, 5
0x18002ea02  jbe     loc_18002EC36
0x18002ea08  mov     rax, [rax+18h]
0x18002ea0c  mov     rcx, [r9+10h]
0x18002ea10  mov     rdx, 200000000000h
0x18002ea1a  test    rdx, rcx
0x18002ea1d  jz      loc_18002EC36
0x18002ea23  mov     rcx, rax
0x18002ea26  and     rcx, rdx
0x18002ea29  cmp     rcx, rax
0x18002ea2c  jnz     loc_18002EC36
0x18002ea32  mov     rax, [rdi+78h]
0x18002ea36  mov     [rbp+50h+var_A8], rax
0x18002ea3a  mov     rax, [rdi+70h]
0x18002ea3e  mov     [rbp+50h+var_A0], rax
0x18002ea42  mov     eax, [rdi+68h]
0x18002ea45  mov     [rbp+50h+var_B8], eax
0x18002ea48  mov     rax, [rdi+60h]
0x18002ea4c  mov     [rbp+50h+var_98], rax
0x18002ea50  mov     rax, [rdi+58h]
0x18002ea54  mov     [rbp+50h+var_90], rax
0x18002ea58  mov     eax, [rdi+50h]
0x18002ea5b  mov     [rbp+50h+var_B4], eax
0x18002ea5e  mov     rax, [rdi+48h]
0x18002ea62  mov     [rbp+50h+var_88], rax
0x18002ea66  mov     eax, [rdi+20h]
0x18002ea69  mov     [rbp+50h+var_B0], eax
0x18002ea6c  mov     rax, [rdi+18h]
0x18002ea70  mov     [rbp+50h+var_80], rax
0x18002ea74  mov     eax, [rdi]
0x18002ea76  mov     [rbp+50h+var_AC], eax
0x18002ea79  mov     rax, [rdi+80h]
0x18002ea80  mov     [rbp+50h+var_78], rax
0x18002ea84  mov     eax, [rdi+40h]
0x18002ea87  mov     [rbp+50h+var_D0], eax
0x18002ea8a  mov     rax, [rdi+38h]
0x18002ea8e  mov     [rbp+50h+var_70], rax
0x18002ea92  mov     eax, [rdi+8]
0x18002ea95  mov     dword ptr [rbp+50h+SRWLock], eax
0x18002ea98  mov     eax, 1000000h
0x18002ea9d  mov     [rbp+50h+var_68], rax
0x18002eaa1  mov     [rbp+50h+var_C0], rax
0x18002eaa5  mov     r8, [rbx+110h]
0x18002eaac  add     r8, 8
0x18002eab0  lea     rax, [rbp+50h+var_A8]
0x18002eab4  mov     [rsp+170h+var_D8], rax
0x18002eabc  lea     rax, [rbp+50h+var_A0]
0x18002eac0  mov     [rsp+170h+var_E0], rax
0x18002eac8  lea     rax, [rbp+50h+var_B8]
0x18002eacc  mov     [rsp+170h+var_E8], rax
0x18002ead4  lea     rax, [rbp+50h+var_98]
0x18002ead8  mov     [rsp+170h+var_F0], rax
0x18002eae0  lea     rax, [rbp+50h+var_90]
0x18002eae4  mov     [rsp+170h+var_F8], rax
0x18002eae9  lea     rax, [rbp+50h+var_B4]
0x18002eaed  mov     [rsp+170h+var_100], rax
0x18002eaf2  lea     rax, [rbp+50h+var_88]
0x18002eaf6  mov     [rsp+170h+var_108], rax
0x18002eafb  lea     rax, [rbp+50h+var_B0]
0x18002eaff  mov     [rsp+170h+var_110], rax
0x18002eb04  lea     rax, [rbp+50h+var_80]
0x18002eb08  mov     [rsp+170h+var_118], rax
0x18002eb0d  lea     rax, [rbp+50h+var_AC]
0x18002eb11  mov     [rsp+170h+var_120], rax
0x18002eb16  lea     rax, [rbp+50h+var_78]
0x18002eb1a  mov     [rsp+170h+var_128], rax
0x18002eb1f  lea     rax, [rbp+50h+var_D0]
0x18002eb23  mov     [rsp+170h+var_130], rax
0x18002eb28  lea     rax, [rbp+50h+var_70]
0x18002eb2c  mov     [rsp+170h+var_138], rax
0x18002eb31  lea     rax, [rbp+50h+SRWLock]
0x18002eb35  mov     [rsp+170h+var_140], rax
0x18002eb3a  lea     rax, [rbp+50h+var_68]
0x18002eb3e  mov     [rsp+170h+var_148], rax
0x18002eb43  lea     rax, [rbp+50h+var_C0]
0x18002eb47  mov     [rsp+170h+var_150], rax
0x18002eb4c  lea     rdx, byte_18003E937
0x18002eb53  mov     rcx, r9
0x18002eb56  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002eb5b  jmp     loc_18002EC36
0x18002eb60  lea     rdx, [rbp+50h+var_C0]
0x18002eb64  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002eb69  mov     rax, [rbx+110h]
0x18002eb70  mov     dword ptr [rax], 2
0x18002eb76  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18002eb7a  test    rcx, rcx
0x18002eb7d  jz      short loc_18002EB85
0x18002eb7f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002eb85  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002eb8a  mov     rdi, rax
0x18002eb8d  mov     ecx, [rax]
0x18002eb8f  cmp     ecx, 5
0x18002eb92  jbe     loc_18002EC36
0x18002eb98  mov     rax, [rax+18h]
0x18002eb9c  mov     rcx, [rdi+10h]
0x18002eba0  mov     rdx, 200000000000h
0x18002ebaa  test    rdx, rcx
0x18002ebad  jz      loc_18002EC36
0x18002ebb3  mov     rcx, rax
0x18002ebb6  and     rcx, rdx
0x18002ebb9  cmp     rcx, rax
0x18002ebbc  jnz     short loc_18002EC36
0x18002ebbe  call    cs:__imp_GetCurrentThreadId
0x18002ebc4  mov     dword ptr [rbp+50h+SRWLock], eax
0x18002ebc7  mov     r8, [rbx+110h]
0x18002ebce  mov     eax, [r8+48h]
0x18002ebd2  mov     [rbp+50h+var_D0], eax
0x18002ebd5  mov     eax, 1000000h
0x18002ebda  mov     [rbp+50h+var_C0], rax
0x18002ebde  lea     rax, [rbp+50h+SRWLock]
0x18002ebe2  mov     [rbp+50h+var_20], rax
0x18002ebe6  mov     [rbp+50h+var_18], 4
0x18002ebee  lea     rax, [rbp+50h+var_D0]
0x18002ebf2  mov     [rbp+50h+var_30], rax
0x18002ebf6  mov     [rbp+50h+var_28], 4
0x18002ebfe  lea     rax, [rbp+50h+var_C0]
0x18002ec02  mov     [rbp+50h+var_40], rax
0x18002ec06  mov     [rbp+50h+var_38], 8
0x18002ec0e  add     r8, 8
0x18002ec12  lea     rax, [rbp+50h+var_60]
0x18002ec16  mov     [rsp+170h+var_148], rax
0x18002ec1b  mov     dword ptr [rsp+170h+var_150], 5
0x18002ec23  xor     r9d, r9d
0x18002ec26  lea     rdx, byte_18003E8D5
0x18002ec2d  mov     rcx, rdi
0x18002ec30  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ec35  nop
0x18002ec36  cmp     dword ptr [rbx+138h], 0
0x18002ec3d  jz      short loc_18002EC9D
0x18002ec3f  add     rbx, 120h
0x18002ec46  call    cs:__imp_GetCurrentThreadId
0x18002ec4c  cmp     [rbx+18h], eax
0x18002ec4f  jz      short loc_18002EC6D
0x18002ec51  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002ec58  test    rax, rax
0x18002ec5b  jz      short loc_18002EC6D
0x18002ec5d  mov     rdx, [rbp+58h]
0x18002ec61  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002ec68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec6d  mov     dword ptr [rbx+18h], 0
0x18002ec74  mov     rcx, [rbx]
0x18002ec77  jmp     short loc_18002EC85
0x18002ec79  cmp     rax, rbx
0x18002ec7c  jz      short loc_18002EC8F
0x18002ec7e  lea     rcx, [rax+10h]
0x18002ec82  mov     [rbx], rcx
0x18002ec85  mov     rax, [rcx]
0x18002ec88  test    rax, rax
0x18002ec8b  jnz     short loc_18002EC79
0x18002ec8d  jmp     short loc_18002EC96
0x18002ec8f  mov     rax, [rbx+10h]
0x18002ec93  mov     [rcx], rax
0x18002ec96  mov     qword ptr [rbx], 0
0x18002ec9d  mov     rcx, [rbp+50h+var_10]
0x18002eca1  xor     rcx, rsp; StackCookie
0x18002eca4  call    __security_check_cookie
0x18002eca9  lea     r11, [rsp+170h+var_s0]
0x18002ecb1  mov     rbx, [r11+18h]
0x18002ecb5  mov     rdi, [r11+20h]
0x18002ecb9  mov     rsp, r11
0x18002ecbc  pop     rbp
0x18002ecbd  retn
```
