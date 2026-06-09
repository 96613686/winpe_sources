# WaasMedic::TelemetryProvider::AddProtectedTaskActivity::Stop(long,long,long,long,long)

- ea: `0x18003ad74`
- end: `0x18003b0ae`
- name: `?Stop@AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXJJJJJ@Z`
- size: `826`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AddProtectedTaskActivity *__hidden this, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180039e40`

## callees

- `0x180003178`
- `0x1800034a0`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18003ad74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003addc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003afc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003addc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003afc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b01c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b01c`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AddProtectedTaskActivity::Stop(
        WaasMedic::TelemetryProvider::AddProtectedTaskActivity *this,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6)
{
  __int64 v6; // rdi
  int v11; // eax
  int *v12; // rdi
  RTL_SRWLOCK *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // r8
  RTL_SRWLOCK *v16; // rcx
  __int64 v17; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // r9d
  int v21; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v22; // [rsp+D4h] [rbp-7Ch] BYREF
  int v23; // [rsp+D8h] [rbp-78h] BYREF
  int v24; // [rsp+DCh] [rbp-74h] BYREF
  int v25; // [rsp+E0h] [rbp-70h] BYREF
  int v26; // [rsp+E4h] [rbp-6Ch] BYREF
  int v27; // [rsp+E8h] [rbp-68h] BYREF
  int v28; // [rsp+ECh] [rbp-64h] BYREF
  int v29; // [rsp+F0h] [rbp-60h] BYREF
  int v30; // [rsp+F4h] [rbp-5Ch] BYREF
  __int64 v31; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v32; // [rsp+100h] [rbp-50h] BYREF
  __int64 v33; // [rsp+108h] [rbp-48h] BYREF
  __int64 v34; // [rsp+110h] [rbp-40h] BYREF
  __int64 v35; // [rsp+118h] [rbp-38h] BYREF
  __int64 v36; // [rsp+120h] [rbp-30h] BYREF
  __int64 v37; // [rsp+128h] [rbp-28h] BYREF
  __int64 v38; // [rsp+130h] [rbp-20h] BYREF
  __int64 v39; // [rsp+138h] [rbp-18h] BYREF
  __int64 v40[8]; // [rsp+140h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+190h] [rbp+40h] BYREF

  v6 = *((_QWORD *)this + 34);
  v11 = *(_DWORD *)(v6 + 72);
  if ( v11 < 0 && (v12 = (int *)(v6 + 80), v11 == v12[2]) && v12 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v13 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v14 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v14 > 5u
      && (*(_QWORD *)(v14 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v14 + 24) & 0x200000000000LL) == *(_QWORD *)(v14 + 24) )
    {
      LODWORD(SRWLock) = a6;
      v27 = a5;
      v32 = *((_QWORD *)v12 + 15);
      v33 = *((_QWORD *)v12 + 14);
      v21 = v12[26];
      v34 = *((_QWORD *)v12 + 12);
      v35 = *((_QWORD *)v12 + 11);
      v15 = *((_QWORD *)this + 34);
      v22 = v12[20];
      v36 = *((_QWORD *)v12 + 9);
      v23 = v12[8];
      v37 = *((_QWORD *)v12 + 3);
      v24 = *v12;
      v38 = *((_QWORD *)v12 + 16);
      v25 = v12[16];
      v39 = *((_QWORD *)v12 + 7);
      v26 = v12[2];
      v40[0] = 0x1000000;
      v31 = 0x1000000;
      v28 = a4;
      v29 = a3;
      v30 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_180094465,
        v15 + 8,
        v14,
        (__int64)&v31,
        (__int64)v40,
        (__int64)&v26,
        (__int64)&v39,
        (__int64)&v25,
        (__int64)&v38,
        (__int64)&v24,
        (__int64)&v37,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v22,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v16 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    v17 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v17 > 5u
      && (*(_QWORD *)(v17 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v17 + 24) & 0x200000000000LL) == *(_QWORD *)(v17 + 24) )
    {
      LODWORD(SRWLock) = a6;
      v26 = a5;
      v25 = a4;
      v24 = a3;
      v23 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v22 = CurrentThreadId;
      v21 = *(_DWORD *)(v19 + 72);
      v31 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)byte_180094619,
        v19 + 8,
        v20,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18003ad74  push    rbp
0x18003ad76  push    rbx
0x18003ad77  push    rsi
0x18003ad78  push    rdi
0x18003ad79  push    r14
0x18003ad7b  push    r15
0x18003ad7d  lea     rbp, [rsp-8]
0x18003ad82  sub     rsp, 158h
0x18003ad89  mov     rdi, [rcx+110h]
0x18003ad90  mov     esi, r9d
0x18003ad93  mov     r14d, r8d
0x18003ad96  mov     r15d, edx
0x18003ad99  mov     rbx, rcx
0x18003ad9c  mov     eax, [rdi+48h]
0x18003ad9f  test    eax, eax
0x18003ada1  jns     loc_18003AFA2
0x18003ada7  add     rdi, 50h ; 'P'
0x18003adab  cmp     eax, [rdi+8]
0x18003adae  jnz     loc_18003AFA2
0x18003adb4  test    rdi, rdi
0x18003adb7  jz      loc_18003AFA2
0x18003adbd  lea     rdx, [rbp+30h+SRWLock]
0x18003adc1  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003adc6  mov     rax, [rbx+110h]
0x18003adcd  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18003add1  mov     dword ptr [rax], 2
0x18003add7  test    rcx, rcx
0x18003adda  jz      short loc_18003ADE2
0x18003addc  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ade2  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003ade7  mov     r9, [rax+8]
0x18003adeb  mov     eax, [r9]
0x18003adee  cmp     eax, 5
0x18003adf1  jbe     loc_18003B097
0x18003adf7  mov     rdx, [r9+18h]
0x18003adfb  mov     rcx, 200000000000h
0x18003ae05  mov     rax, [r9+10h]
0x18003ae09  test    rcx, rax
0x18003ae0c  jz      loc_18003B097
0x18003ae12  mov     rax, rdx
0x18003ae15  and     rax, rcx
0x18003ae18  cmp     rax, rdx
0x18003ae1b  jnz     loc_18003B097
0x18003ae21  mov     eax, [rbp+30h+arg_28]
0x18003ae24  mov     dword ptr [rbp+30h+SRWLock], eax
0x18003ae27  mov     eax, [rbp+30h+arg_20]
0x18003ae2a  mov     [rbp+30h+var_98], eax
0x18003ae2d  mov     rax, [rdi+78h]
0x18003ae31  mov     [rbp+30h+var_80], rax
0x18003ae35  mov     rax, [rdi+70h]
0x18003ae39  mov     [rbp+30h+var_78], rax
0x18003ae3d  mov     eax, [rdi+68h]
0x18003ae40  mov     [rbp+30h+var_B0], eax
0x18003ae43  mov     rax, [rdi+60h]
0x18003ae47  mov     [rbp+30h+var_70], rax
0x18003ae4b  mov     rax, [rdi+58h]
0x18003ae4f  mov     [rbp+30h+var_68], rax
0x18003ae53  mov     eax, [rdi+50h]
0x18003ae56  mov     r8, [rbx+110h]
0x18003ae5d  mov     [rbp+30h+var_AC], eax
0x18003ae60  add     r8, 8
0x18003ae64  mov     rax, [rdi+48h]
0x18003ae68  mov     [rbp+30h+var_60], rax
0x18003ae6c  mov     eax, [rdi+20h]
0x18003ae6f  mov     [rbp+30h+var_A8], eax
0x18003ae72  mov     rax, [rdi+18h]
0x18003ae76  mov     [rbp+30h+var_58], rax
0x18003ae7a  mov     eax, [rdi]
0x18003ae7c  mov     [rbp+30h+var_A4], eax
0x18003ae7f  mov     rax, [rdi+80h]
0x18003ae86  mov     [rbp+30h+var_50], rax
0x18003ae8a  mov     eax, [rdi+40h]
0x18003ae8d  mov     [rbp+30h+var_A0], eax
0x18003ae90  mov     rax, [rdi+38h]
0x18003ae94  mov     [rbp+30h+var_48], rax
0x18003ae98  mov     eax, [rdi+8]
0x18003ae9b  mov     [rbp+30h+var_9C], eax
0x18003ae9e  mov     eax, 1000000h
0x18003aea3  mov     [rbp+30h+var_40], rax
0x18003aea7  mov     [rbp+30h+var_88], rax
0x18003aeab  lea     rax, [rbp+30h+SRWLock]
0x18003aeaf  mov     [rsp+180h+var_C0], rax
0x18003aeb7  lea     rax, [rbp+30h+var_98]
0x18003aebb  mov     [rsp+180h+var_C8], rax
0x18003aec3  lea     rax, [rbp+30h+var_94]
0x18003aec7  mov     [rsp+180h+var_D0], rax
0x18003aecf  lea     rax, [rbp+30h+var_90]
0x18003aed3  mov     [rsp+180h+var_D8], rax
0x18003aedb  lea     rax, [rbp+30h+var_8C]
0x18003aedf  mov     [rsp+180h+var_E0], rax
0x18003aee7  lea     rax, [rbp+30h+var_80]
0x18003aeeb  mov     [rsp+180h+var_E8], rax
0x18003aef3  lea     rax, [rbp+30h+var_78]
0x18003aef7  mov     [rsp+180h+var_F0], rax
0x18003aeff  lea     rax, [rbp+30h+var_B0]
0x18003af03  mov     [rsp+180h+var_F8], rax
0x18003af0b  lea     rax, [rbp+30h+var_70]
0x18003af0f  mov     [rsp+180h+var_100], rax
0x18003af17  lea     rax, [rbp+30h+var_68]
0x18003af1b  mov     [rsp+180h+var_108], rax
0x18003af20  lea     rax, [rbp+30h+var_AC]
0x18003af24  mov     [rsp+180h+var_110], rax
0x18003af29  lea     rax, [rbp+30h+var_60]
0x18003af2d  mov     [rsp+180h+var_118], rax
0x18003af32  lea     rax, [rbp+30h+var_A8]
0x18003af36  mov     [rsp+180h+var_120], rax
0x18003af3b  lea     rax, [rbp+30h+var_58]
0x18003af3f  mov     [rsp+180h+var_128], rax
0x18003af44  lea     rax, [rbp+30h+var_A4]
0x18003af48  mov     [rsp+180h+var_130], rax
0x18003af4d  lea     rax, [rbp+30h+var_50]
0x18003af51  mov     [rsp+180h+var_138], rax
0x18003af56  lea     rax, [rbp+30h+var_A0]
0x18003af5a  mov     [rsp+180h+var_140], rax
0x18003af5f  lea     rax, [rbp+30h+var_48]
0x18003af63  mov     [rsp+180h+var_148], rax
0x18003af68  lea     rax, [rbp+30h+var_9C]
0x18003af6c  mov     [rsp+180h+var_150], rax
0x18003af71  lea     rax, [rbp+30h+var_40]
0x18003af75  mov     [rsp+180h+var_158], rax
0x18003af7a  lea     rax, [rbp+30h+var_88]
0x18003af7e  mov     [rbp+30h+var_94], esi
0x18003af81  mov     [rbp+30h+var_90], r14d
0x18003af85  mov     [rbp+30h+var_8C], r15d
0x18003af89  lea     rdx, byte_180094465
0x18003af90  mov     [rsp+180h+var_160], rax
0x18003af95  mov     rcx, r9
0x18003af98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003af9d  jmp     loc_18003B097
0x18003afa2  lea     rdx, [rbp+30h+SRWLock]
0x18003afa6  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003afab  mov     rax, [rbx+110h]
0x18003afb2  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18003afb6  mov     dword ptr [rax], 2
0x18003afbc  test    rcx, rcx
0x18003afbf  jz      short loc_18003AFC7
0x18003afc1  call    cs:__imp_ReleaseSRWLockExclusive
0x18003afc7  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003afcc  mov     rdi, [rax+8]
0x18003afd0  mov     eax, [rdi]
0x18003afd2  cmp     eax, 5
0x18003afd5  jbe     loc_18003B097
0x18003afdb  mov     rdx, [rdi+18h]
0x18003afdf  mov     rcx, 200000000000h
0x18003afe9  mov     rax, [rdi+10h]
0x18003afed  test    rcx, rax
0x18003aff0  jz      loc_18003B097
0x18003aff6  mov     rax, rdx
0x18003aff9  and     rax, rcx
0x18003affc  cmp     rax, rdx
0x18003afff  jnz     loc_18003B097
0x18003b005  mov     eax, [rbp+30h+arg_28]
0x18003b008  mov     dword ptr [rbp+30h+SRWLock], eax
0x18003b00b  mov     eax, [rbp+30h+arg_20]
0x18003b00e  mov     [rbp+30h+var_9C], eax
0x18003b011  mov     [rbp+30h+var_A0], esi
0x18003b014  mov     [rbp+30h+var_A4], r14d
0x18003b018  mov     [rbp+30h+var_A8], r15d
0x18003b01c  call    cs:__imp_GetCurrentThreadId
0x18003b022  mov     r8, [rbx+110h]
0x18003b029  lea     rdx, byte_180094619
0x18003b030  mov     [rbp+30h+var_AC], eax
0x18003b033  mov     rcx, rdi
0x18003b036  mov     eax, [r8+48h]
0x18003b03a  add     r8, 8
0x18003b03e  mov     [rbp+30h+var_B0], eax
0x18003b041  mov     eax, 1000000h
0x18003b046  mov     [rbp+30h+var_88], rax
0x18003b04a  lea     rax, [rbp+30h+SRWLock]
0x18003b04e  mov     [rsp+180h+var_128], rax
0x18003b053  lea     rax, [rbp+30h+var_9C]
0x18003b057  mov     [rsp+180h+var_130], rax
0x18003b05c  lea     rax, [rbp+30h+var_A0]
0x18003b060  mov     [rsp+180h+var_138], rax
0x18003b065  lea     rax, [rbp+30h+var_A4]
0x18003b069  mov     [rsp+180h+var_140], rax
0x18003b06e  lea     rax, [rbp+30h+var_A8]
0x18003b072  mov     [rsp+180h+var_148], rax
0x18003b077  lea     rax, [rbp+30h+var_AC]
0x18003b07b  mov     [rsp+180h+var_150], rax
0x18003b080  lea     rax, [rbp+30h+var_B0]
0x18003b084  mov     [rsp+180h+var_158], rax
0x18003b089  lea     rax, [rbp+30h+var_88]
0x18003b08d  mov     [rsp+180h+var_160], rax
0x18003b092  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b097  mov     rcx, rbx
0x18003b09a  add     rsp, 158h
0x18003b0a1  pop     r15
0x18003b0a3  pop     r14
0x18003b0a5  pop     rdi
0x18003b0a6  pop     rsi
0x18003b0a7  pop     rbx
0x18003b0a8  pop     rbp
0x18003b0a9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
