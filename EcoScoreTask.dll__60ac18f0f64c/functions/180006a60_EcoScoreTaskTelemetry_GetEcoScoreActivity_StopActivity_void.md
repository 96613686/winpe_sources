# EcoScoreTaskTelemetry::GetEcoScoreActivity::StopActivity(void)

- ea: `0x180006a60`
- end: `0x180006d9d`
- name: `?StopActivity@GetEcoScoreActivity@EcoScoreTaskTelemetry@@MEAAXXZ`
- size: `829`
- prototype: `void __fastcall(EcoScoreTaskTelemetry::GetEcoScoreActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800018dc`
- `0x180004d4c`
- `0x180005760`
- `0x180006a60`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006acf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006acf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c5f`

## string_xrefs

- `0x180006d40`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall EcoScoreTaskTelemetry::GetEcoScoreActivity::StopActivity(
        EcoScoreTaskTelemetry::GetEcoScoreActivity *this)
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
  char *v16; // rbx
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v21; // [rsp+B0h] [rbp-70h] BYREF
  int v22; // [rsp+B8h] [rbp-68h] BYREF
  int v23; // [rsp+BCh] [rbp-64h] BYREF
  int v24; // [rsp+C0h] [rbp-60h] BYREF
  int v25; // [rsp+C4h] [rbp-5Ch] BYREF
  int *v26; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v27; // [rsp+D0h] [rbp-50h] BYREF
  int *v28; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v29; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-38h] BYREF
  int *v31; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v32; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v33; // [rsp+100h] [rbp-20h] BYREF
  __int64 v34; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v35[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v36; // [rsp+130h] [rbp+10h]
  __int64 v37; // [rsp+138h] [rbp+18h]
  int *v38; // [rsp+140h] [rbp+20h]
  __int64 v39; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v41; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = EcoScoreTaskTelemetry::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v26 = (int *)*((_QWORD *)v4 + 15);
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v22 = v4[26];
        v28 = (int *)*((_QWORD *)v4 + 12);
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v23 = v4[20];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v24 = v4[8];
        v31 = (int *)*((_QWORD *)v4 + 3);
        v25 = *v4;
        v32 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v19 = v4[16];
        v33 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v34 = 0x1000000;
        v21 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)word_18000B38A,
          v9 + 8,
          v7,
          (__int64)&v21,
          (__int64)&v34,
          (__int64)&SRWLock,
          &v33,
          (__int64)&v19,
          &v32,
          (__int64)&v25,
          &v31,
          (__int64)&v24,
          &v30,
          (__int64)&v23,
          &v29,
          &v28,
          (__int64)&v22,
          &v27,
          &v26);
      }
    }
  }
  else
  {
    wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v21);
    v10 = v21;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = EcoScoreTaskTelemetry::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v41 = 4;
        v39 = 4;
        v19 = *(_DWORD *)(v15 + 72);
        v21 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v38 = &v19;
        v36 = &v21;
        v37 = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, &word_18000B336, v15 + 8, 0, 5, v35);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v16 = (char *)this + 288;
    if ( *((_DWORD *)v16 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v17 = *(__int64 **)v16;
    *((_DWORD *)v16 + 6) = 0;
    while ( 1 )
    {
      v18 = *v17;
      if ( !*v17 )
        break;
      if ( (char *)v18 == v16 )
      {
        *v17 = *((_QWORD *)v16 + 2);
        break;
      }
      v17 = (__int64 *)(v18 + 16);
      *(_QWORD *)v16 = v18 + 16;
    }
    *(_QWORD *)v16 = 0;
  }
}

```

## disassembly

```asm
0x180006a60  mov     [rsp-8+arg_8], rbx
0x180006a65  mov     [rsp-8+arg_10], rdi
0x180006a6a  push    rbp
0x180006a6b  lea     rbp, [rsp-50h]
0x180006a70  sub     rsp, 170h
0x180006a77  mov     rax, cs:__security_cookie
0x180006a7e  xor     rax, rsp
0x180006a81  mov     [rbp+50h+var_10], rax
0x180006a85  mov     rdi, [rcx+110h]
0x180006a8c  mov     rbx, rcx
0x180006a8f  mov     eax, [rdi+48h]
0x180006a92  test    eax, eax
0x180006a94  jns     loc_180006C40
0x180006a9a  add     rdi, 50h ; 'P'
0x180006a9e  cmp     eax, [rdi+8]
0x180006aa1  jnz     loc_180006C40
0x180006aa7  test    rdi, rdi
0x180006aaa  jz      loc_180006C40
0x180006ab0  lea     rdx, [rbp+50h+SRWLock]
0x180006ab4  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180006ab9  mov     rax, [rbx+110h]
0x180006ac0  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x180006ac4  mov     dword ptr [rax], 2
0x180006aca  test    rcx, rcx
0x180006acd  jz      short loc_180006AD5
0x180006acf  call    cs:__imp_ReleaseSRWLockExclusive
0x180006ad5  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x180006ada  mov     r9, rax
0x180006add  mov     ecx, [rax]
0x180006adf  cmp     ecx, 5
0x180006ae2  jbe     loc_180006D15
0x180006ae8  mov     rax, [rax+18h]
0x180006aec  mov     rdx, 200000000000h
0x180006af6  mov     rcx, [r9+10h]
0x180006afa  test    rdx, rcx
0x180006afd  jz      loc_180006D15
0x180006b03  mov     rcx, rax
0x180006b06  and     rcx, rdx
0x180006b09  cmp     rcx, rax
0x180006b0c  jnz     loc_180006D15
0x180006b12  mov     rax, [rdi+78h]
0x180006b16  lea     rdx, word_18000B38A
0x180006b1d  mov     r8, [rbx+110h]
0x180006b24  mov     rcx, r9
0x180006b27  mov     [rbp+50h+var_A8], rax
0x180006b2b  add     r8, 8
0x180006b2f  mov     rax, [rdi+70h]
0x180006b33  mov     [rbp+50h+var_A0], rax
0x180006b37  mov     eax, [rdi+68h]
0x180006b3a  mov     [rbp+50h+var_B8], eax
0x180006b3d  mov     rax, [rdi+60h]
0x180006b41  mov     [rbp+50h+var_98], rax
0x180006b45  mov     rax, [rdi+58h]
0x180006b49  mov     [rbp+50h+var_90], rax
0x180006b4d  mov     eax, [rdi+50h]
0x180006b50  mov     [rbp+50h+var_B4], eax
0x180006b53  mov     rax, [rdi+48h]
0x180006b57  mov     [rbp+50h+var_88], rax
0x180006b5b  mov     eax, [rdi+20h]
0x180006b5e  mov     [rbp+50h+var_B0], eax
0x180006b61  mov     rax, [rdi+18h]
0x180006b65  mov     [rbp+50h+var_80], rax
0x180006b69  mov     eax, [rdi]
0x180006b6b  mov     [rbp+50h+var_AC], eax
0x180006b6e  mov     rax, [rdi+80h]
0x180006b75  mov     [rbp+50h+var_78], rax
0x180006b79  mov     eax, [rdi+40h]
0x180006b7c  mov     [rbp+50h+var_D0], eax
0x180006b7f  mov     rax, [rdi+38h]
0x180006b83  mov     [rbp+50h+var_70], rax
0x180006b87  mov     eax, [rdi+8]
0x180006b8a  mov     dword ptr [rbp+50h+SRWLock], eax
0x180006b8d  mov     eax, 1000000h
0x180006b92  mov     [rbp+50h+var_68], rax
0x180006b96  mov     [rbp+50h+var_C0], rax
0x180006b9a  lea     rax, [rbp+50h+var_A8]
0x180006b9e  mov     [rsp+170h+var_D8], rax
0x180006ba6  lea     rax, [rbp+50h+var_A0]
0x180006baa  mov     [rsp+170h+var_E0], rax
0x180006bb2  lea     rax, [rbp+50h+var_B8]
0x180006bb6  mov     [rsp+170h+var_E8], rax
0x180006bbe  lea     rax, [rbp+50h+var_98]
0x180006bc2  mov     [rsp+170h+var_F0], rax
0x180006bca  lea     rax, [rbp+50h+var_90]
0x180006bce  mov     [rsp+170h+var_F8], rax
0x180006bd3  lea     rax, [rbp+50h+var_B4]
0x180006bd7  mov     [rsp+170h+var_100], rax
0x180006bdc  lea     rax, [rbp+50h+var_88]
0x180006be0  mov     [rsp+170h+var_108], rax
0x180006be5  lea     rax, [rbp+50h+var_B0]
0x180006be9  mov     [rsp+170h+var_110], rax
0x180006bee  lea     rax, [rbp+50h+var_80]
0x180006bf2  mov     [rsp+170h+var_118], rax
0x180006bf7  lea     rax, [rbp+50h+var_AC]
0x180006bfb  mov     [rsp+170h+var_120], rax
0x180006c00  lea     rax, [rbp+50h+var_78]
0x180006c04  mov     [rsp+170h+var_128], rax
0x180006c09  lea     rax, [rbp+50h+var_D0]
0x180006c0d  mov     [rsp+170h+var_130], rax
0x180006c12  lea     rax, [rbp+50h+var_70]
0x180006c16  mov     [rsp+170h+var_138], rax
0x180006c1b  lea     rax, [rbp+50h+SRWLock]
0x180006c1f  mov     [rsp+170h+var_140], rax
0x180006c24  lea     rax, [rbp+50h+var_68]
0x180006c28  mov     [rsp+170h+var_148], rax
0x180006c2d  lea     rax, [rbp+50h+var_C0]
0x180006c31  mov     [rsp+170h+var_150], rax
0x180006c36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180006c3b  jmp     loc_180006D15
0x180006c40  lea     rdx, [rbp+50h+var_C0]
0x180006c44  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180006c49  mov     rax, [rbx+110h]
0x180006c50  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x180006c54  mov     dword ptr [rax], 2
0x180006c5a  test    rcx, rcx
0x180006c5d  jz      short loc_180006C65
0x180006c5f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c65  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x180006c6a  mov     rdi, rax
0x180006c6d  mov     ecx, [rax]
0x180006c6f  cmp     ecx, 5
0x180006c72  jbe     loc_180006D15
0x180006c78  mov     rax, [rax+18h]
0x180006c7c  mov     rdx, 200000000000h
0x180006c86  mov     rcx, [rdi+10h]
0x180006c8a  test    rdx, rcx
0x180006c8d  jz      loc_180006D15
0x180006c93  mov     rcx, rax
0x180006c96  and     rcx, rdx
0x180006c99  cmp     rcx, rax
0x180006c9c  jnz     short loc_180006D15
0x180006c9e  call    cs:__imp_GetCurrentThreadId
0x180006ca4  mov     r8, [rbx+110h]
0x180006cab  lea     rdx, word_18000B336
0x180006cb2  mov     dword ptr [rbp+50h+SRWLock], eax
0x180006cb5  xor     r9d, r9d
0x180006cb8  mov     rcx, rdi
0x180006cbb  mov     [rbp+50h+var_18], 4
0x180006cc3  mov     [rbp+50h+var_28], 4
0x180006ccb  mov     eax, [r8+48h]
0x180006ccf  add     r8, 8
0x180006cd3  mov     [rbp+50h+var_D0], eax
0x180006cd6  mov     eax, 1000000h
0x180006cdb  mov     [rbp+50h+var_C0], rax
0x180006cdf  lea     rax, [rbp+50h+SRWLock]
0x180006ce3  mov     [rbp+50h+var_20], rax
0x180006ce7  lea     rax, [rbp+50h+var_D0]
0x180006ceb  mov     [rbp+50h+var_30], rax
0x180006cef  lea     rax, [rbp+50h+var_C0]
0x180006cf3  mov     [rbp+50h+var_40], rax
0x180006cf7  lea     rax, [rbp+50h+var_60]
0x180006cfb  mov     [rsp+170h+var_148], rax
0x180006d00  mov     dword ptr [rsp+170h+var_150], 5
0x180006d08  mov     [rbp+50h+var_38], 8
0x180006d10  call    _tlgWriteTransfer_EventWriteTransfer
0x180006d15  cmp     dword ptr [rbx+138h], 0
0x180006d1c  jz      short loc_180006D7C
0x180006d1e  add     rbx, 120h
0x180006d25  call    cs:__imp_GetCurrentThreadId
0x180006d2b  cmp     [rbx+18h], eax
0x180006d2e  jz      short loc_180006D4C
0x180006d30  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180006d37  test    rax, rax
0x180006d3a  jz      short loc_180006D4C
0x180006d3c  mov     rdx, [rbp+58h]
0x180006d40  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180006d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4c  mov     rcx, [rbx]
0x180006d4f  mov     dword ptr [rbx+18h], 0
0x180006d56  jmp     short loc_180006D64
0x180006d58  cmp     rax, rbx
0x180006d5b  jz      short loc_180006D6E
0x180006d5d  lea     rcx, [rax+10h]
0x180006d61  mov     [rbx], rcx
0x180006d64  mov     rax, [rcx]
0x180006d67  test    rax, rax
0x180006d6a  jnz     short loc_180006D58
0x180006d6c  jmp     short loc_180006D75
0x180006d6e  mov     rax, [rbx+10h]
0x180006d72  mov     [rcx], rax
0x180006d75  mov     qword ptr [rbx], 0
0x180006d7c  mov     rcx, [rbp+50h+var_10]
0x180006d80  xor     rcx, rsp; StackCookie
0x180006d83  call    __security_check_cookie
0x180006d88  lea     r11, [rsp+170h+var_s0]
0x180006d90  mov     rbx, [r11+18h]
0x180006d94  mov     rdi, [r11+20h]
0x180006d98  mov     rsp, r11
0x180006d9b  pop     rbp
0x180006d9c  retn
```
