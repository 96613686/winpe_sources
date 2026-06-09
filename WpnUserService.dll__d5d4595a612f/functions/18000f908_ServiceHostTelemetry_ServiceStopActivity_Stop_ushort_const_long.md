# ServiceHostTelemetry::ServiceStopActivity::Stop(ushort const *,long)

- ea: `0x18000f908`
- end: `0x18000fbe1`
- name: `?Stop@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z`
- size: `729`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000edbc`

## callees

- `0x180001e50`
- `0x18000214c`
- `0x18000a648`
- `0x18000e400`
- `0x18000e47c`
- `0x18000f908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f96e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f96e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb67`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::Stop(
        ServiceHostTelemetry::ServiceStopActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v3; // rdi
  int v6; // eax
  int *v7; // rdi
  RTL_SRWLOCK *v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+B0h] [rbp-80h] BYREF
  int v21; // [rsp+B4h] [rbp-7Ch] BYREF
  int v22; // [rsp+B8h] [rbp-78h] BYREF
  int v23; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v24; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  __int64 *v26; // [rsp+D0h] [rbp-60h] BYREF
  __int64 *v27; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp-50h] BYREF
  __int64 *v29; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v31; // [rsp+F8h] [rbp-38h] BYREF
  __int64 *v32; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v34; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v36; // [rsp+150h] [rbp+20h] BYREF
  int v37; // [rsp+158h] [rbp+28h] BYREF

  v36 = a3;
  v3 = *((_QWORD *)this + 34);
  v6 = *(_DWORD *)(v3 + 72);
  if ( v6 < 0 && (v7 = (int *)(v3 + 80), v6 == v7[2]) && v7 )
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = ServiceHostLogging::Provider();
    v10 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u )
    {
      v11 = *((_QWORD *)v9 + 3);
      if ( (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0 && (v11 & 0x400000000000LL) == v11 )
      {
        v27 = (__int64 *)*((_QWORD *)v7 + 15);
        v28 = (const unsigned __int16 *)*((_QWORD *)v7 + 14);
        v12 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = v7[26];
        v29 = (__int64 *)*((_QWORD *)v7 + 12);
        v30 = (const unsigned __int16 *)*((_QWORD *)v7 + 11);
        v37 = v7[20];
        v31 = (const unsigned __int16 *)*((_QWORD *)v7 + 9);
        v20 = v7[8];
        v32 = (__int64 *)*((_QWORD *)v7 + 3);
        v21 = *v7;
        v33 = (const unsigned __int16 *)*((_QWORD *)v7 + 16);
        v22 = v7[16];
        v34 = (const unsigned __int16 *)*((_QWORD *)v7 + 7);
        v23 = v7[2];
        v24 = 0x1000000;
        v25 = 0x1000000;
        v36 = 0;
        v26 = (__int64 *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v10,
          (__int64)word_180015582,
          v12 + 8,
          v10,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23,
          &v34,
          (__int64)&v22,
          &v33,
          (__int64)&v21,
          &v32,
          (__int64)&v20,
          &v31,
          (__int64)&v37,
          &v30,
          &v29,
          (__int64)&SRWLock,
          &v28,
          &v27,
          &v26,
          (__int64)&v36);
      }
    }
  }
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v13 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v14 = ServiceHostLogging::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u )
    {
      v16 = *((_QWORD *)v14 + 3);
      if ( (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0 && (v16 & 0x400000000000LL) == v16 )
      {
        v36 = 0;
        v25 = (__int64)a2;
        CurrentThreadId = GetCurrentThreadId();
        v18 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v37 = *(_DWORD *)(v18 + 72);
        v24 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v15,
          (__int64)byte_18001551D,
          v18 + 8,
          v19,
          (__int64)&v24,
          (__int64)&v37,
          (__int64)&SRWLock,
          (__int64 **)&v25,
          (__int64)&v36);
      }
    }
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000f908  mov     [rsp-8+arg_8], rbx
0x18000f90d  mov     [rsp-8+arg_10], r8d
0x18000f912  push    rbp
0x18000f913  push    rsi
0x18000f914  push    rdi
0x18000f915  lea     rbp, [rsp+10h]
0x18000f91a  sub     rsp, 120h
0x18000f921  mov     rdi, [rcx+110h]
0x18000f928  mov     rsi, rdx
0x18000f92b  mov     rbx, rcx
0x18000f92e  mov     eax, [rdi+48h]
0x18000f931  test    eax, eax
0x18000f933  jns     loc_18000FB02
0x18000f939  add     rdi, 50h ; 'P'
0x18000f93d  cmp     eax, [rdi+8]
0x18000f940  jnz     loc_18000FB02
0x18000f946  test    rdi, rdi
0x18000f949  jz      loc_18000FB02
0x18000f94f  lea     rdx, [rbp+SRWLock]
0x18000f953  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f958  mov     rax, [rbx+110h]
0x18000f95f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000f963  mov     dword ptr [rax], 2
0x18000f969  test    rcx, rcx
0x18000f96c  jz      short loc_18000F974
0x18000f96e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f974  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f979  mov     r9, rax
0x18000f97c  mov     ecx, [rax]
0x18000f97e  cmp     ecx, 5
0x18000f981  jbe     loc_18000FBC7
0x18000f987  mov     rax, [rax+18h]
0x18000f98b  mov     rdx, 400000000000h
0x18000f995  mov     rcx, [r9+10h]
0x18000f999  test    rdx, rcx
0x18000f99c  jz      loc_18000FBC7
0x18000f9a2  mov     rcx, rax
0x18000f9a5  and     rcx, rdx
0x18000f9a8  cmp     rcx, rax
0x18000f9ab  jnz     loc_18000FBC7
0x18000f9b1  mov     rax, [rdi+78h]
0x18000f9b5  lea     rdx, word_180015582
0x18000f9bc  mov     [rbp+var_58], rax
0x18000f9c0  mov     rcx, r9
0x18000f9c3  mov     rax, [rdi+70h]
0x18000f9c7  mov     [rbp+var_50], rax
0x18000f9cb  mov     eax, [rdi+68h]
0x18000f9ce  mov     r8, [rbx+110h]
0x18000f9d5  mov     dword ptr [rbp+SRWLock], eax
0x18000f9d8  add     r8, 8
0x18000f9dc  mov     rax, [rdi+60h]
0x18000f9e0  mov     [rbp+var_48], rax
0x18000f9e4  mov     rax, [rdi+58h]
0x18000f9e8  mov     [rbp+var_40], rax
0x18000f9ec  mov     eax, [rdi+50h]
0x18000f9ef  mov     [rbp+arg_18], eax
0x18000f9f2  mov     rax, [rdi+48h]
0x18000f9f6  mov     [rbp+var_38], rax
0x18000f9fa  mov     eax, [rdi+20h]
0x18000f9fd  mov     [rbp+var_80], eax
0x18000fa00  mov     rax, [rdi+18h]
0x18000fa04  mov     [rbp+var_30], rax
0x18000fa08  mov     eax, [rdi]
0x18000fa0a  mov     [rbp+var_7C], eax
0x18000fa0d  mov     rax, [rdi+80h]
0x18000fa14  mov     [rbp+var_28], rax
0x18000fa18  mov     eax, [rdi+40h]
0x18000fa1b  mov     [rbp+var_78], eax
0x18000fa1e  mov     rax, [rdi+38h]
0x18000fa22  mov     [rbp+var_20], rax
0x18000fa26  mov     eax, [rdi+8]
0x18000fa29  mov     [rbp+var_74], eax
0x18000fa2c  mov     eax, 1000000h
0x18000fa31  mov     [rbp+var_70], rax
0x18000fa35  mov     [rbp+var_68], rax
0x18000fa39  lea     rax, [rbp+arg_10]
0x18000fa3d  mov     [rsp+130h+var_88], rax
0x18000fa45  lea     rax, [rbp+var_60]
0x18000fa49  mov     [rsp+130h+var_90], rax
0x18000fa51  lea     rax, [rbp+var_58]
0x18000fa55  mov     [rsp+130h+var_98], rax
0x18000fa5d  lea     rax, [rbp+var_50]
0x18000fa61  mov     [rsp+130h+var_A0], rax
0x18000fa69  lea     rax, [rbp+SRWLock]
0x18000fa6d  mov     [rsp+130h+var_A8], rax
0x18000fa75  lea     rax, [rbp+var_48]
0x18000fa79  mov     [rsp+130h+var_B0], rax
0x18000fa81  lea     rax, [rbp+var_40]
0x18000fa85  mov     [rsp+130h+var_B8], rax
0x18000fa8a  lea     rax, [rbp+arg_18]
0x18000fa8e  mov     [rsp+130h+var_C0], rax
0x18000fa93  lea     rax, [rbp+var_38]
0x18000fa97  mov     [rsp+130h+var_C8], rax
0x18000fa9c  lea     rax, [rbp+var_80]
0x18000faa0  mov     [rsp+130h+var_D0], rax
0x18000faa5  lea     rax, [rbp+var_30]
0x18000faa9  mov     [rsp+130h+var_D8], rax
0x18000faae  lea     rax, [rbp+var_7C]
0x18000fab2  mov     [rsp+130h+var_E0], rax
0x18000fab7  lea     rax, [rbp+var_28]
0x18000fabb  mov     [rsp+130h+var_E8], rax
0x18000fac0  lea     rax, [rbp+var_78]
0x18000fac4  mov     [rsp+130h+var_F0], rax
0x18000fac9  lea     rax, [rbp+var_20]
0x18000facd  mov     [rsp+130h+var_F8], rax
0x18000fad2  lea     rax, [rbp+var_74]
0x18000fad6  mov     [rsp+130h+var_100], rax
0x18000fadb  lea     rax, [rbp+var_70]
0x18000fadf  mov     [rsp+130h+var_108], rax
0x18000fae4  lea     rax, [rbp+var_68]
0x18000fae8  mov     [rsp+130h+var_110], rax
0x18000faed  mov     [rbp+arg_10], 0
0x18000faf4  mov     [rbp+var_60], rsi
0x18000faf8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000fafd  jmp     loc_18000FBC7
0x18000fb02  lea     rdx, [rbp+SRWLock]
0x18000fb06  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fb0b  mov     rax, [rbx+110h]
0x18000fb12  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000fb16  mov     dword ptr [rax], 2
0x18000fb1c  test    rcx, rcx
0x18000fb1f  jz      short loc_18000FB27
0x18000fb21  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fb27  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000fb2c  mov     rdi, rax
0x18000fb2f  mov     ecx, [rax]
0x18000fb31  cmp     ecx, 5
0x18000fb34  jbe     loc_18000FBC7
0x18000fb3a  mov     rax, [rax+18h]
0x18000fb3e  mov     rdx, 400000000000h
0x18000fb48  mov     rcx, [rdi+10h]
0x18000fb4c  test    rdx, rcx
0x18000fb4f  jz      short loc_18000FBC7
0x18000fb51  mov     rcx, rax
0x18000fb54  and     rcx, rdx
0x18000fb57  cmp     rcx, rax
0x18000fb5a  jnz     short loc_18000FBC7
0x18000fb5c  mov     [rbp+arg_10], 0
0x18000fb63  mov     [rbp+var_68], rsi
0x18000fb67  call    cs:__imp_GetCurrentThreadId
0x18000fb6d  mov     r8, [rbx+110h]
0x18000fb74  lea     rdx, byte_18001551D
0x18000fb7b  mov     dword ptr [rbp+SRWLock], eax
0x18000fb7e  mov     rcx, rdi
0x18000fb81  mov     eax, [r8+48h]
0x18000fb85  add     r8, 8
0x18000fb89  mov     [rbp+arg_18], eax
0x18000fb8c  mov     eax, 1000000h
0x18000fb91  mov     [rbp+var_70], rax
0x18000fb95  lea     rax, [rbp+arg_10]
0x18000fb99  mov     [rsp+130h+var_F0], rax
0x18000fb9e  lea     rax, [rbp+var_68]
0x18000fba2  mov     [rsp+130h+var_F8], rax
0x18000fba7  lea     rax, [rbp+SRWLock]
0x18000fbab  mov     [rsp+130h+var_100], rax
0x18000fbb0  lea     rax, [rbp+arg_18]
0x18000fbb4  mov     [rsp+130h+var_108], rax
0x18000fbb9  lea     rax, [rbp+var_70]
0x18000fbbd  mov     [rsp+130h+var_110], rax
0x18000fbc2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000fbc7  mov     rcx, rbx
0x18000fbca  mov     rbx, [rsp+130h+arg_8]
0x18000fbd2  add     rsp, 120h
0x18000fbd9  pop     rdi
0x18000fbda  pop     rsi
0x18000fbdb  pop     rbp
0x18000fbdc  jmp     ?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
