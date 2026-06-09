# MDMPushProvider::CreatePushRenewalScheduleActivity::StopActivity(void)

- ea: `0x140029720`
- end: `0x14002999c`
- name: `?StopActivity@CreatePushRenewalScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(MDMPushProvider::CreatePushRenewalScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x140029720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002977a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002991b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002977a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002991b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029930`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029930`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MDMPushProvider::CreatePushRenewalScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushRenewalScheduleActivity *this)
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
  const OLECHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const OLECHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const OLECHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const OLECHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const OLECHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const OLECHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)byte_14006DC55,
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
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)word_14006E222,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::CreatePushRenewalScheduleActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140029720  push    rbp
0x140029722  push    rbx
0x140029723  push    rdi
0x140029724  lea     rbp, [rsp+10h]
0x140029729  sub     rsp, 130h
0x140029730  mov     rbx, rcx
0x140029733  mov     rdi, [rcx+110h]
0x14002973a  mov     eax, [rdi+48h]
0x14002973d  test    eax, eax
0x14002973f  jns     loc_1400298FC
0x140029745  add     rdi, 50h ; 'P'
0x140029749  cmp     eax, [rdi+8]
0x14002974c  jnz     loc_1400298FC
0x140029752  test    rdi, rdi
0x140029755  jz      loc_1400298FC
0x14002975b  lea     rdx, [rbp+SRWLock]
0x14002975f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029764  mov     rax, [rbx+110h]
0x14002976b  mov     dword ptr [rax], 2
0x140029771  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029775  test    rcx, rcx
0x140029778  jz      short loc_140029780
0x14002977a  call    cs:__imp_ReleaseSRWLockExclusive
0x140029780  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029785  mov     r9, rax
0x140029788  mov     ecx, [rax]
0x14002978a  cmp     ecx, 5
0x14002978d  jbe     loc_14002997E
0x140029793  mov     rcx, [rdi+30h]
0x140029797  mov     [rbp+var_70], rcx
0x14002979b  mov     ecx, [rdi+44h]
0x14002979e  mov     dword ptr [rbp+SRWLock], ecx
0x1400297a1  mov     ecx, [rdi+10h]
0x1400297a4  mov     [rbp+arg_8], ecx
0x1400297a7  mov     rcx, [rdi+78h]
0x1400297ab  mov     [rbp+var_68], rcx
0x1400297af  mov     rax, [rdi+70h]
0x1400297b3  mov     [rbp+var_60], rax
0x1400297b7  mov     eax, [rdi+68h]
0x1400297ba  mov     dword ptr [rbp+arg_10], eax
0x1400297bd  mov     rax, [rdi+60h]
0x1400297c1  mov     [rbp+var_58], rax
0x1400297c5  mov     rax, [rdi+58h]
0x1400297c9  mov     [rbp+var_50], rax
0x1400297cd  mov     eax, [rdi+50h]
0x1400297d0  mov     [rbp+arg_18], eax
0x1400297d3  mov     rax, [rdi+48h]
0x1400297d7  mov     [rbp+var_48], rax
0x1400297db  mov     eax, [rdi+20h]
0x1400297de  mov     [rbp+var_80], eax
0x1400297e1  mov     rax, [rdi+18h]
0x1400297e5  mov     [rbp+var_40], rax
0x1400297e9  mov     eax, [rdi]
0x1400297eb  mov     [rbp+var_7C], eax
0x1400297ee  mov     rax, [rdi+80h]
0x1400297f5  mov     [rbp+var_38], rax
0x1400297f9  mov     eax, [rdi+40h]
0x1400297fc  mov     [rbp+var_78], eax
0x1400297ff  mov     rax, [rdi+38h]
0x140029803  mov     [rbp+var_30], rax
0x140029807  mov     eax, [rdi+8]
0x14002980a  mov     [rbp+var_74], eax
0x14002980d  mov     [rbp+var_28], 1000000h
0x140029815  mov     [rbp+var_20], 0
0x14002981d  mov     r8, [rbx+110h]
0x140029824  add     r8, 8
0x140029828  lea     rax, [rbp+var_70]
0x14002982c  mov     [rsp+140h+var_90], rax
0x140029834  lea     rax, [rbp+SRWLock]
0x140029838  mov     [rsp+140h+var_98], rax
0x140029840  lea     rax, [rbp+arg_8]
0x140029844  mov     [rsp+140h+var_A0], rax
0x14002984c  lea     rax, [rbp+var_68]
0x140029850  mov     [rsp+140h+var_A8], rax
0x140029858  lea     rax, [rbp+var_60]
0x14002985c  mov     [rsp+140h+var_B0], rax
0x140029864  lea     rax, [rbp+arg_10]
0x140029868  mov     [rsp+140h+var_B8], rax
0x140029870  lea     rax, [rbp+var_58]
0x140029874  mov     [rsp+140h+var_C0], rax
0x14002987c  lea     rax, [rbp+var_50]
0x140029880  mov     [rsp+140h+var_C8], rax
0x140029885  lea     rax, [rbp+arg_18]
0x140029889  mov     [rsp+140h+var_D0], rax
0x14002988e  lea     rax, [rbp+var_48]
0x140029892  mov     [rsp+140h+var_D8], rax
0x140029897  lea     rax, [rbp+var_80]
0x14002989b  mov     [rsp+140h+var_E0], rax
0x1400298a0  lea     rax, [rbp+var_40]
0x1400298a4  mov     [rsp+140h+var_E8], rax
0x1400298a9  lea     rax, [rbp+var_7C]
0x1400298ad  mov     [rsp+140h+var_F0], rax
0x1400298b2  lea     rax, [rbp+var_38]
0x1400298b6  mov     [rsp+140h+var_F8], rax
0x1400298bb  lea     rax, [rbp+var_78]
0x1400298bf  mov     [rsp+140h+var_100], rax
0x1400298c4  lea     rax, [rbp+var_30]
0x1400298c8  mov     [rsp+140h+var_108], rax
0x1400298cd  lea     rax, [rbp+var_74]
0x1400298d1  mov     [rsp+140h+var_110], rax
0x1400298d6  lea     rax, [rbp+var_28]
0x1400298da  mov     [rsp+140h+var_118], rax
0x1400298df  lea     rax, [rbp+var_20]
0x1400298e3  mov     [rsp+140h+var_120], rax
0x1400298e8  lea     rdx, byte_14006DC55
0x1400298ef  mov     rcx, r9
0x1400298f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400298f7  jmp     loc_14002997E
0x1400298fc  lea     rdx, [rbp+SRWLock]
0x140029900  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029905  mov     rax, [rbx+110h]
0x14002990c  mov     dword ptr [rax], 2
0x140029912  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029916  test    rcx, rcx
0x140029919  jz      short loc_140029921
0x14002991b  call    cs:__imp_ReleaseSRWLockExclusive
0x140029921  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029926  mov     rdi, rax
0x140029929  mov     ecx, [rax]
0x14002992b  cmp     ecx, 5
0x14002992e  jbe     short loc_14002997E
0x140029930  call    cs:__imp_GetCurrentThreadId
0x140029936  mov     dword ptr [rbp+SRWLock], eax
0x140029939  mov     r8, [rbx+110h]
0x140029940  mov     ecx, [r8+48h]
0x140029944  mov     [rbp+arg_8], ecx
0x140029947  mov     [rbp+arg_10], 0
0x14002994f  add     r8, 8
0x140029953  lea     rax, [rbp+SRWLock]
0x140029957  mov     [rsp+140h+var_110], rax
0x14002995c  lea     rax, [rbp+arg_8]
0x140029960  mov     [rsp+140h+var_118], rax
0x140029965  lea     rax, [rbp+arg_10]
0x140029969  mov     [rsp+140h+var_120], rax
0x14002996e  lea     rdx, word_14006E222
0x140029975  mov     rcx, rdi
0x140029978  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002997d  nop
0x14002997e  lea     rcx, [rbx+120h]; this
0x140029985  cmp     dword ptr [rcx+18h], 0
0x140029989  jz      short loc_140029991
0x14002998b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140029990  nop
0x140029991  add     rsp, 130h
0x140029998  pop     rdi
0x140029999  pop     rbx
0x14002999a  pop     rbp
0x14002999b  retn
```
