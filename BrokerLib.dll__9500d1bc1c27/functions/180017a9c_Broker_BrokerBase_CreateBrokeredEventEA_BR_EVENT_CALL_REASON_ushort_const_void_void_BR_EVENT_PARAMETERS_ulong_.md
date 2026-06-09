# Broker::BrokerBase::CreateBrokeredEventEA(_BR_EVENT_CALL_REASON,ushort const *,void *,void *,_BR_EVENT_PARAMETERS *,ulong,_GUID const *,_BROKERED_EVENT * *,_BR_NEW_EVENT_INFORMATION *,_CBROKERED_EVENT_ID *)

- ea: `0x180017a9c`
- end: `0x180017ffb`
- name: `?CreateBrokeredEventEA@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEBGPEAX2PEAU_BR_EVENT_PARAMETERS@@KPEBU_GUID@@PEAPEAU_BROKERED_EVENT@@PEAU_BR_NEW_EVENT_INFORMATION@@PEAU_CBROKERED_EVENT_ID@@@Z`
- size: `1375`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ab8c`

## callees

- `0x180004ae0`
- `0x180005b50`
- `0x18000ab90`
- `0x18000bc2c`
- `0x18000d5cc`
- `0x18000e8a4`
- `0x18000eb40`
- `0x18000ed50`
- `0x18000f648`
- `0x18001184c`
- `0x1800126e0`
- `0x180015af0`
- `0x1800165da`
- `0x180017460`
- `0x180017a9c`
- `0x1800186a8`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180017f3d`
- `ntdll!RtlNtStatusToDosError` at `0x180017fd0`
- `ntdll!RtlNtStatusToDosError` at `0x180017f3d`
- `ntdll!RtlNtStatusToDosError` at `0x180017fd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::CreateBrokeredEventEA(
        Broker::BrokerBase *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        _OWORD *a8,
        struct _BROKERED_EVENT **a9,
        _OWORD *a10,
        _QWORD *a11)
{
  struct _BROKERED_EVENT *Event; // rbx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  void *v22; // r9
  unsigned int v23; // r14d
  __int64 v24; // r8
  NTSTATUS TemporaryStateName; // eax
  __int64 v26; // rax
  ULONG v27; // eax
  ULONG v28; // eax
  struct _BROKERED_EVENT *v29; // rbx
  char v30[3]; // [rsp+61h] [rbp-1A7h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-1A4h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 v33; // [rsp+70h] [rbp-198h] BYREF
  __int64 v34; // [rsp+78h] [rbp-190h] BYREF
  struct _BROKERED_EVENT *v35; // [rsp+80h] [rbp-188h] BYREF
  const WCHAR *v36; // [rsp+88h] [rbp-180h] BYREF
  void *v37; // [rsp+90h] [rbp-178h] BYREF
  unsigned int v38; // [rsp+98h] [rbp-170h]
  struct _BROKERED_EVENT *v39; // [rsp+A0h] [rbp-168h]
  std::_Ref_count_base *v40[2]; // [rsp+A8h] [rbp-160h] BYREF
  std::_Ref_count_base *v41[2]; // [rsp+B8h] [rbp-150h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-140h] BYREF
  unsigned int v43[2]; // [rsp+D0h] [rbp-138h] BYREF
  struct _BROKERED_EVENT **v44; // [rsp+D8h] [rbp-130h]
  Broker::BrokerBase *v45; // [rsp+E0h] [rbp-128h]
  _BYTE v46[32]; // [rsp+E8h] [rbp-120h] BYREF
  _BYTE v47[32]; // [rsp+108h] [rbp-100h] BYREF
  _BYTE v48[40]; // [rsp+128h] [rbp-E0h] BYREF
  _BYTE v49[40]; // [rsp+150h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+178h] [rbp-90h] BYREF
  __int64 v51; // [rsp+1A0h] [rbp-68h] BYREF
  __int128 v52; // [rsp+1A8h] [rbp-60h] BYREF
  __int128 v53; // [rsp+1B8h] [rbp-50h]

  v45 = a1;
  v38 = a2;
  v33 = a6;
  v44 = a9;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)a1 + 1));
  v52 = 0;
  v53 = 0;
  *(_OWORD *)v41 = 0;
  v31 = 0;
  v51 = 0;
  v32 = 0;
  *(_OWORD *)v40 = 0;
  std::shared_ptr<Broker::BrokerEvent>::operator=(v41, v40);
  if ( v40[1] )
    std::_Ref_count_base::_Decref(v40[1]);
  v31 = 1;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  LODWORD(v52) = -1;
  DWORD2(v52) = 0;
  if ( !a10 )
  {
    Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)v46);
    throw (Broker::InvalidParameter *)v46;
  }
  if ( !*((_QWORD *)a1 + 15) || !*((_QWORD *)a1 + 16) )
  {
    v27 = RtlNtStatusToDosError(-1073741822);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, v27);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  v39 = 0;
  if ( a11 )
    *a11 = 0;
  try
  {
    Event = Broker::BrokerBase::AllocateEvent(a1, a3, a4);
    v39 = Event;
    if ( a8 )
      *(_OWORD *)Event = *a8;
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v16, v17) )
    {
      v37 = a4;
      v36 = a3;
      v30[0] = a2;
      v35 = Event;
      v34 = *((_QWORD *)a1 + 1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>>(
        v18,
        byte_1800221B7,
        v19,
        v20,
        &v34,
        (__int64 *)&v35,
        (__int64)v30,
        &v36,
        (__int64 *)&v37);
    }
    v23 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, struct _BROKERED_EVENT *, __int64, const unsigned __int16 *, void *, _QWORD, _QWORD, __int64 *, unsigned int *, __int128 *))a1
           + 15))(
            a2,
            *((_QWORD *)a1 + 1),
            Event,
            v33,
            a3,
            a4,
            0,
            0,
            &v32,
            &v31,
            &v52);
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v21, v22) )
    {
      LODWORD(v33) = v31;
      LODWORD(v34) = DWORD2(v52);
      LODWORD(v35) = DWORD1(v52);
      LODWORD(v36) = v52;
      v42 = v32;
      LODWORD(v37) = v23;
      *(_QWORD *)v43 = Event;
      v40[0] = *((std::_Ref_count_base **)a1 + 1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        byte_1800220F4,
        v24,
        (__int64)v22,
        (__int64 *)v40,
        (__int64 *)v43,
        (__int64)&v37,
        (__int64)&v42,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33);
    }
    if ( v23 )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v48, v23);
      throw (Broker::Win32Error *)v48;
    }
    if ( (_DWORD)v52 == -1 )
    {
      Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)v47);
      throw (Broker::InvalidParameter *)v47;
    }
    TemporaryStateName = Broker::CreateTemporaryStateName((Broker *)&v51, (struct _WNF_STATE_NAME *)0x1000, a4, v22);
    if ( TemporaryStateName < 0 )
    {
      v28 = RtlNtStatusToDosError(TemporaryStateName);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v49, v28);
      throw (Broker::Win32Error *)v49;
    }
    *((_QWORD *)Event + 2) = v51;
    *((_QWORD *)Event + 5) = *(_QWORD *)((char *)&v52 + 4);
    *((_DWORD *)Event + 12) = a7;
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v40, (struct _RTL_SRWLOCK *)a1, 1);
    Broker::BrokerBase::RegisterEvent((_DWORD)a1, a2, (_DWORD)Event, v52, v31, v32, SBYTE12(v53));
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v40);
    v26 = *((_QWORD *)v41[0] + 8);
    if ( a11 && v26 )
      *a11 = v26;
    *v44 = Event;
    *a10 = v52;
    a10[1] = v53;
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
  }
  catch ( ... )
  {
    if ( v51 )
    {
      NtDeleteWnfStateName(&v51);
      v29 = v39;
      *((_QWORD *)v39 + 2) = 0;
    }
    else
    {
      v29 = v39;
    }
    (*((void (__fastcall **)(_QWORD, _QWORD, struct _BROKERED_EVENT *, __int64))v45 + 16))(
      v38,
      *((_QWORD *)v45 + 1),
      v29,
      v32);
    if ( v29 )
      BciHeapFree(v29);
    throw;
  }
}

```

## disassembly

```asm
0x180017a9c  push    rbx
0x180017a9e  push    rsi
0x180017a9f  push    rdi
0x180017aa0  push    r12
0x180017aa2  push    r13
0x180017aa4  push    r14
0x180017aa6  push    r15
0x180017aa8  sub     rsp, 1D0h
0x180017aaf  mov     rax, cs:__security_cookie
0x180017ab6  xor     rax, rsp
0x180017ab9  mov     [rsp+208h+var_40], rax
0x180017ac1  mov     r12, r9
0x180017ac4  mov     r14, r8
0x180017ac7  mov     r13d, edx
0x180017aca  mov     rdi, rcx
0x180017acd  mov     [rsp+208h+var_128], rcx
0x180017ad5  mov     [rsp+208h+var_170], edx
0x180017adc  mov     rax, [rsp+208h+arg_28]
0x180017ae4  mov     [rsp+208h+var_198], rax
0x180017ae9  mov     rax, [rsp+208h+arg_40]
0x180017af1  mov     [rsp+208h+var_130], rax
0x180017af9  mov     r15, [rsp+208h+arg_48]
0x180017b01  mov     rsi, [rsp+208h+arg_50]
0x180017b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b10  test    dword ptr [rcx+1Ch], 800h
0x180017b17  jz      short loc_180017B38
0x180017b19  cmp     byte ptr [rcx+19h], 5
0x180017b1d  jb      short loc_180017B38
0x180017b1f  mov     edx, 1Ch
0x180017b24  mov     r9, [rdi+8]
0x180017b28  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180017b2f  mov     rcx, [rcx+10h]
0x180017b33  call    WPP_SF__guid_
0x180017b38  xorps   xmm0, xmm0
0x180017b3b  movups  [rsp+208h+var_60], xmm0
0x180017b43  movups  [rsp+208h+var_50], xmm0
0x180017b4b  xorps   xmm1, xmm1
0x180017b4e  movdqu  xmmword ptr [rsp+208h+var_150], xmm1
0x180017b57  xor     ebx, ebx
0x180017b59  mov     [rsp+208h+var_1A4], ebx
0x180017b5d  mov     [rsp+208h+var_68], rbx
0x180017b65  mov     [rsp+208h+var_1A0], rbx
0x180017b6a  movdqu  xmmword ptr [rsp+208h+var_160], xmm0
0x180017b73  lea     rdx, [rsp+208h+var_160]
0x180017b7b  lea     rcx, [rsp+208h+var_150]
0x180017b83  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x180017b88  mov     rcx, [rsp+208h+var_160+8]; this
0x180017b90  test    rcx, rcx
0x180017b93  jz      short loc_180017B9A
0x180017b95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017b9a  mov     [rsp+208h+var_1A4], 1
0x180017ba2  mov     [rsp+208h+var_68], rbx
0x180017baa  xorps   xmm0, xmm0
0x180017bad  movups  [rsp+208h+var_60], xmm0
0x180017bb5  movups  [rsp+208h+var_50], xmm0
0x180017bbd  mov     dword ptr [rsp+208h+var_60], 0FFFFFFFFh
0x180017bc8  mov     dword ptr [rsp+208h+var_60+8], ebx
0x180017bcf  test    r15, r15
0x180017bd2  jz      loc_180017F67
0x180017bd8  cmp     [rdi+78h], rbx
0x180017bdc  jz      loc_180017F38
0x180017be2  cmp     [rdi+80h], rbx
0x180017be9  jz      loc_180017F38
0x180017bef  mov     [rsp+208h+var_168], rbx
0x180017bf7  mov     [rsp+208h+var_1A8], bl
0x180017bfb  test    rsi, rsi
0x180017bfe  jz      short loc_180017C05
0x180017c00  xor     eax, eax
0x180017c02  mov     [rsi], rax
0x180017c05  mov     r8, r12; void *
0x180017c08  mov     rdx, r14; unsigned __int16 *
0x180017c0b  mov     rcx, rdi; this
0x180017c0e  call    ?AllocateEvent@BrokerBase@Broker@@AEAAPEAU_BROKERED_EVENT@@PEBGPEAX@Z; Broker::BrokerBase::AllocateEvent(ushort const *,void *)
0x180017c13  mov     rbx, rax
0x180017c16  mov     [rsp+208h+var_168], rax
0x180017c1e  mov     rax, [rsp+208h+arg_38]
0x180017c26  test    rax, rax
0x180017c29  jz      short loc_180017C32
0x180017c2b  movups  xmm0, xmmword ptr [rax]
0x180017c2e  movdqu  xmmword ptr [rbx], xmm0
0x180017c32  mov     ecx, cs:dword_180028000
0x180017c38  cmp     ecx, 4
0x180017c3b  jbe     short loc_180017CB8
0x180017c3d  mov     edx, 2
0x180017c42  call    _tlgKeywordOn
0x180017c47  test    al, al
0x180017c49  jz      short loc_180017CB8
0x180017c4b  mov     [rsp+208h+var_178], r12
0x180017c53  mov     [rsp+208h+var_180], r14
0x180017c5b  mov     [rsp+208h+var_1A7], r13b
0x180017c60  mov     [rsp+208h+var_188], rbx
0x180017c68  mov     rax, [rdi+8]
0x180017c6c  mov     [rsp+208h+var_190], rax
0x180017c71  lea     rax, [rsp+208h+var_178]
0x180017c79  mov     [rsp+208h+var_1C8], rax
0x180017c7e  lea     rax, [rsp+208h+var_180]
0x180017c86  mov     [rsp+208h+var_1D0], rax
0x180017c8b  lea     rax, [rsp+208h+var_1A7]
0x180017c90  mov     [rsp+208h+var_1D8], rax
0x180017c95  lea     rax, [rsp+208h+var_188]
0x180017c9d  mov     qword ptr [rsp+208h+var_1E0], rax
0x180017ca2  lea     rax, [rsp+208h+var_190]
0x180017ca7  mov     [rsp+208h+var_1E8], rax
0x180017cac  lea     rdx, byte_1800221B7
0x180017cb3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSid<_SID>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &)
0x180017cb8  lea     rax, [rsp+208h+var_60]
0x180017cc0  mov     [rsp+208h+var_1B8], rax
0x180017cc5  lea     rax, [rsp+208h+var_1A4]
0x180017cca  mov     [rsp+208h+var_1C0], rax
0x180017ccf  lea     rax, [rsp+208h+var_1A0]
0x180017cd4  mov     [rsp+208h+var_1C8], rax
0x180017cd9  mov     [rsp+208h+var_1D0], 0
0x180017ce2  mov     [rsp+208h+var_1D8], 0
0x180017ceb  mov     qword ptr [rsp+208h+var_1E0], r12
0x180017cf0  mov     [rsp+208h+var_1E8], r14
0x180017cf5  mov     r9, [rsp+208h+var_198]
0x180017cfa  mov     r8, rbx
0x180017cfd  mov     rdx, [rdi+8]
0x180017d01  mov     ecx, r13d
0x180017d04  mov     rax, [rdi+78h]
0x180017d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d0d  mov     r14d, eax
0x180017d10  mov     ecx, cs:dword_180028000
0x180017d16  cmp     ecx, 4
0x180017d19  jbe     loc_180017DF7
0x180017d1f  mov     edx, 2
0x180017d24  call    _tlgKeywordOn
0x180017d29  test    al, al
0x180017d2b  jz      loc_180017DF7
0x180017d31  mov     ecx, [rsp+208h+var_1A4]
0x180017d35  mov     dword ptr [rsp+208h+var_198], ecx
0x180017d39  mov     eax, dword ptr [rsp+208h+var_60+8]
0x180017d40  mov     dword ptr [rsp+208h+var_190], eax
0x180017d44  mov     eax, dword ptr [rsp+208h+var_60+4]
0x180017d4b  mov     dword ptr [rsp+208h+var_188], eax
0x180017d52  mov     eax, dword ptr [rsp+208h+var_60]
0x180017d59  mov     dword ptr [rsp+208h+var_180], eax
0x180017d60  mov     rax, [rsp+208h+var_1A0]
0x180017d65  mov     [rsp+208h+var_140], rax
0x180017d6d  mov     dword ptr [rsp+208h+var_178], r14d
0x180017d75  mov     qword ptr [rsp+208h+var_138], rbx
0x180017d7d  mov     rax, [rdi+8]
0x180017d81  mov     [rsp+208h+var_160], rax
0x180017d89  lea     rax, [rsp+208h+var_198]
0x180017d8e  mov     [rsp+208h+var_1B0], rax
0x180017d93  lea     rax, [rsp+208h+var_190]
0x180017d98  mov     [rsp+208h+var_1B8], rax
0x180017d9d  lea     rax, [rsp+208h+var_188]
0x180017da5  mov     [rsp+208h+var_1C0], rax
0x180017daa  lea     rax, [rsp+208h+var_180]
0x180017db2  mov     [rsp+208h+var_1C8], rax
0x180017db7  lea     rax, [rsp+208h+var_140]
0x180017dbf  mov     [rsp+208h+var_1D0], rax
0x180017dc4  lea     rax, [rsp+208h+var_178]
0x180017dcc  mov     [rsp+208h+var_1D8], rax
0x180017dd1  lea     rax, [rsp+208h+var_138]
0x180017dd9  mov     qword ptr [rsp+208h+var_1E0], rax; unsigned int
0x180017dde  lea     rax, [rsp+208h+var_160]
0x180017de6  mov     [rsp+208h+var_1E8], rax; void *
0x180017deb  lea     rdx, byte_1800220F4
0x180017df2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017df7  test    r14d, r14d
0x180017dfa  jnz     loc_180017F89
0x180017e00  mov     [rsp+208h+var_1A8], 1
0x180017e05  cmp     dword ptr [rsp+208h+var_60], 0FFFFFFFFh
0x180017e0d  jz      loc_180017FAD
0x180017e13  mov     r8, r12; unsigned int
0x180017e16  mov     edx, 1000h; struct _WNF_STATE_NAME *
0x180017e1b  lea     rcx, [rsp+208h+var_68]; this
0x180017e23  call    ?CreateTemporaryStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x180017e28  test    eax, eax
0x180017e2a  js      loc_180017FCE
0x180017e30  mov     rax, [rsp+208h+var_68]
0x180017e38  mov     [rbx+10h], rax
0x180017e3c  mov     eax, dword ptr [rsp+208h+var_60+4]
0x180017e43  mov     [rbx+28h], eax
0x180017e46  mov     eax, dword ptr [rsp+208h+var_60+8]
0x180017e4d  mov     [rbx+2Ch], eax
0x180017e50  mov     eax, [rsp+208h+arg_30]
0x180017e57  mov     [rbx+30h], eax
0x180017e5a  mov     r8b, 1; bool
0x180017e5d  mov     rdx, rdi; struct _RTL_SRWLOCK *
0x180017e60  lea     rcx, [rsp+208h+var_160]; this
0x180017e68  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180017e6d  nop
0x180017e6e  lea     rax, [rsp+208h+var_150]
0x180017e76  mov     [rsp+208h+var_1C8], rax
0x180017e7b  mov     al, byte ptr [rsp+208h+var_50+0Ch]
0x180017e82  mov     byte ptr [rsp+208h+var_1D8], al
0x180017e86  mov     rax, [rsp+208h+var_1A0]
0x180017e8b  mov     qword ptr [rsp+208h+var_1E0], rax
0x180017e90  mov     eax, [rsp+208h+var_1A4]
0x180017e94  mov     dword ptr [rsp+208h+var_1E8], eax
0x180017e98  mov     r9d, dword ptr [rsp+208h+var_60]
0x180017ea0  mov     r8, rbx
0x180017ea3  mov     edx, r13d
0x180017ea6  mov     rcx, rdi
0x180017ea9  call    ?RegisterEvent@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@KKPEAXEPEAU_WNF_STATE_NAME@@PEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::RegisterEvent(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *,ulong,ulong,void *,uchar,_WNF_STATE_NAME *,std::shared_ptr<Broker::BrokerEvent> *)
0x180017eae  nop
0x180017eaf  lea     rcx, [rsp+208h+var_160]; this
0x180017eb7  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180017ebc  mov     rax, [rsp+208h+var_150]
0x180017ec4  mov     rax, [rax+40h]
0x180017ec8  test    rsi, rsi
0x180017ecb  jz      short loc_180017EDF
0x180017ecd  test    eax, eax
0x180017ecf  jnz     short loc_180017EDC
0x180017ed1  mov     rcx, rax
0x180017ed4  shr     rcx, 20h
0x180017ed8  test    ecx, ecx
0x180017eda  jz      short loc_180017EDF
0x180017edc  mov     [rsi], rax
0x180017edf  mov     rax, [rsp+208h+var_130]
0x180017ee7  mov     [rax], rbx
0x180017eea  movups  xmm0, [rsp+208h+var_60]
0x180017ef2  movups  xmmword ptr [r15], xmm0
0x180017ef6  movups  xmm1, [rsp+208h+var_50]
0x180017efe  movups  xmmword ptr [r15+10h], xmm1
0x180017f03  mov     rcx, [rsp+208h+var_150+8]; this
0x180017f0b  test    rcx, rcx
0x180017f0e  jz      short loc_180017F15
0x180017f10  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017f15  mov     rcx, [rsp+208h+var_40]
0x180017f1d  xor     rcx, rsp; StackCookie
0x180017f20  call    __security_check_cookie
0x180017f25  add     rsp, 1D0h
0x180017f2c  pop     r15
0x180017f2e  pop     r14
0x180017f30  pop     r13
0x180017f32  pop     r12
0x180017f34  pop     rdi
0x180017f35  pop     rsi
0x180017f36  pop     rbx
0x180017f37  retn
0x180017f38  mov     ecx, 0C0000002h; Status
0x180017f3d  call    cs:__imp_RtlNtStatusToDosError
0x180017f43  mov     edx, eax; unsigned int
0x180017f45  lea     rcx, [rsp+208h+pExceptionObject]; this
0x180017f4d  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180017f52  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180017f59  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x180017f61  call    _CxxThrowException_0
0x180017f67  lea     rcx, [rsp+208h+var_120]; this
0x180017f6f  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x180017f74  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180017f7b  lea     rcx, [rsp+208h+var_120]; pExceptionObject
0x180017f83  call    _CxxThrowException_0
0x180017f89  mov     edx, r14d; unsigned int
0x180017f8c  lea     rcx, [rsp+208h+var_E0]; this
0x180017f94  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180017f99  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180017fa0  lea     rcx, [rsp+208h+var_E0]; pExceptionObject
0x180017fa8  call    _CxxThrowException_0
0x180017fad  lea     rcx, [rsp+208h+var_100]; this
0x180017fb5  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x180017fba  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180017fc1  lea     rcx, [rsp+208h+var_100]; pExceptionObject
0x180017fc9  call    _CxxThrowException_0
0x180017fce  mov     ecx, eax; Status
0x180017fd0  call    cs:__imp_RtlNtStatusToDosError
0x180017fd6  mov     edx, eax; unsigned int
0x180017fd8  lea     rcx, [rsp+208h+var_B8]; this
0x180017fe0  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180017fe5  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180017fec  lea     rcx, [rsp+208h+var_B8]; pExceptionObject
0x180017ff4  call    _CxxThrowException_0
```
