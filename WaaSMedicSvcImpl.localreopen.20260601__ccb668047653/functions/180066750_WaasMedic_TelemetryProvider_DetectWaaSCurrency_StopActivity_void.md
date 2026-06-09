# WaasMedic::TelemetryProvider::DetectWaaSCurrency::StopActivity(void)

- ea: `0x180066750`
- end: `0x1800669d4`
- name: `?StopActivity@DetectWaaSCurrency@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::DetectWaaSCurrency *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x180066750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800667aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006693c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800667aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006693c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066974`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066974`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::DetectWaaSCurrency::StopActivity(
        WaasMedic::TelemetryProvider::DetectWaaSCurrency *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&byte_1800950DF,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&word_180094E7E,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180066750  push    rbp
0x180066752  push    rbx
0x180066753  push    rdi
0x180066754  lea     rbp, [rsp-47h]
0x180066759  sub     rsp, 100h
0x180066760  mov     rdi, [rcx+110h]
0x180066767  mov     rbx, rcx
0x18006676a  mov     eax, [rdi+48h]
0x18006676d  test    eax, eax
0x18006676f  jns     loc_18006691D
0x180066775  add     rdi, 50h ; 'P'
0x180066779  cmp     eax, [rdi+8]
0x18006677c  jnz     loc_18006691D
0x180066782  test    rdi, rdi
0x180066785  jz      loc_18006691D
0x18006678b  lea     rdx, [rbp+57h+SRWLock]
0x18006678f  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180066794  mov     rax, [rbx+110h]
0x18006679b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006679f  mov     dword ptr [rax], 2
0x1800667a5  test    rcx, rcx
0x1800667a8  jz      short loc_1800667B0
0x1800667aa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800667b0  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x1800667b5  mov     r9, [rax+8]
0x1800667b9  mov     eax, [r9]
0x1800667bc  cmp     eax, 5
0x1800667bf  jbe     loc_1800669C2
0x1800667c5  mov     rdx, [r9+18h]
0x1800667c9  mov     rcx, 400000000000h
0x1800667d3  mov     rax, [r9+10h]
0x1800667d7  test    rcx, rax
0x1800667da  jz      loc_1800669C2
0x1800667e0  mov     rax, rdx
0x1800667e3  and     rax, rcx
0x1800667e6  cmp     rax, rdx
0x1800667e9  jnz     loc_1800669C2
0x1800667ef  mov     rax, [rdi+78h]
0x1800667f3  lea     rdx, byte_1800950DF
0x1800667fa  mov     r8, [rbx+110h]
0x180066801  mov     rcx, r9
0x180066804  mov     [rbp+57h+var_68], rax
0x180066808  add     r8, 8
0x18006680c  mov     rax, [rdi+70h]
0x180066810  mov     [rbp+57h+var_60], rax
0x180066814  mov     eax, [rdi+68h]
0x180066817  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006681a  mov     rax, [rdi+60h]
0x18006681e  mov     [rbp+57h+var_58], rax
0x180066822  mov     rax, [rdi+58h]
0x180066826  mov     [rbp+57h+var_50], rax
0x18006682a  mov     eax, [rdi+50h]
0x18006682d  mov     [rbp+57h+arg_8], eax
0x180066830  mov     rax, [rdi+48h]
0x180066834  mov     [rbp+57h+var_48], rax
0x180066838  mov     eax, [rdi+20h]
0x18006683b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006683e  mov     rax, [rdi+18h]
0x180066842  mov     [rbp+57h+var_40], rax
0x180066846  mov     eax, [rdi]
0x180066848  mov     [rbp+57h+arg_18], eax
0x18006684b  mov     rax, [rdi+80h]
0x180066852  mov     [rbp+57h+var_38], rax
0x180066856  mov     eax, [rdi+40h]
0x180066859  mov     [rbp+57h+var_70], eax
0x18006685c  mov     rax, [rdi+38h]
0x180066860  mov     [rbp+57h+var_30], rax
0x180066864  mov     eax, [rdi+8]
0x180066867  mov     [rbp+57h+var_6C], eax
0x18006686a  mov     eax, 1000000h
0x18006686f  mov     [rbp+57h+var_28], rax
0x180066873  mov     [rbp+57h+var_20], rax
0x180066877  lea     rax, [rbp+57h+var_68]
0x18006687b  mov     [rsp+110h+var_78], rax
0x180066883  lea     rax, [rbp+57h+var_60]
0x180066887  mov     [rsp+110h+var_80], rax
0x18006688f  lea     rax, [rbp+57h+SRWLock]
0x180066893  mov     [rsp+110h+var_88], rax
0x18006689b  lea     rax, [rbp+57h+var_58]
0x18006689f  mov     [rsp+110h+var_90], rax
0x1800668a7  lea     rax, [rbp+57h+var_50]
0x1800668ab  mov     [rsp+110h+var_98], rax
0x1800668b0  lea     rax, [rbp+57h+arg_8]
0x1800668b4  mov     [rsp+110h+var_A0], rax
0x1800668b9  lea     rax, [rbp+57h+var_48]
0x1800668bd  mov     [rsp+110h+var_A8], rax
0x1800668c2  lea     rax, [rbp+57h+arg_10]
0x1800668c6  mov     [rsp+110h+var_B0], rax
0x1800668cb  lea     rax, [rbp+57h+var_40]
0x1800668cf  mov     [rsp+110h+var_B8], rax
0x1800668d4  lea     rax, [rbp+57h+arg_18]
0x1800668d8  mov     [rsp+110h+var_C0], rax
0x1800668dd  lea     rax, [rbp+57h+var_38]
0x1800668e1  mov     [rsp+110h+var_C8], rax
0x1800668e6  lea     rax, [rbp+57h+var_70]
0x1800668ea  mov     [rsp+110h+var_D0], rax
0x1800668ef  lea     rax, [rbp+57h+var_30]
0x1800668f3  mov     [rsp+110h+var_D8], rax
0x1800668f8  lea     rax, [rbp+57h+var_6C]
0x1800668fc  mov     [rsp+110h+var_E0], rax
0x180066901  lea     rax, [rbp+57h+var_28]
0x180066905  mov     [rsp+110h+var_E8], rax
0x18006690a  lea     rax, [rbp+57h+var_20]
0x18006690e  mov     [rsp+110h+var_F0], rax
0x180066913  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180066918  jmp     loc_1800669C2
0x18006691d  lea     rdx, [rbp+57h+SRWLock]
0x180066921  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180066926  mov     rax, [rbx+110h]
0x18006692d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180066931  mov     dword ptr [rax], 2
0x180066937  test    rcx, rcx
0x18006693a  jz      short loc_180066942
0x18006693c  call    cs:__imp_ReleaseSRWLockExclusive
0x180066942  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180066947  mov     rdi, [rax+8]
0x18006694b  mov     eax, [rdi]
0x18006694d  cmp     eax, 5
0x180066950  jbe     short loc_1800669C2
0x180066952  mov     rdx, [rdi+18h]
0x180066956  mov     rcx, 400000000000h
0x180066960  mov     rax, [rdi+10h]
0x180066964  test    rcx, rax
0x180066967  jz      short loc_1800669C2
0x180066969  mov     rax, rdx
0x18006696c  and     rax, rcx
0x18006696f  cmp     rax, rdx
0x180066972  jnz     short loc_1800669C2
0x180066974  call    cs:__imp_GetCurrentThreadId
0x18006697a  mov     r8, [rbx+110h]
0x180066981  lea     rdx, word_180094E7E
0x180066988  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006698b  mov     rcx, rdi
0x18006698e  mov     eax, [r8+48h]
0x180066992  add     r8, 8
0x180066996  mov     [rbp+57h+arg_8], eax
0x180066999  mov     eax, 1000000h
0x18006699e  mov     [rbp+57h+arg_10], rax
0x1800669a2  lea     rax, [rbp+57h+SRWLock]
0x1800669a6  mov     [rsp+110h+var_E0], rax
0x1800669ab  lea     rax, [rbp+57h+arg_8]
0x1800669af  mov     [rsp+110h+var_E8], rax
0x1800669b4  lea     rax, [rbp+57h+arg_10]
0x1800669b8  mov     [rsp+110h+var_F0], rax
0x1800669bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800669c2  mov     rcx, rbx
0x1800669c5  add     rsp, 100h
0x1800669cc  pop     rdi
0x1800669cd  pop     rbx
0x1800669ce  pop     rbp
0x1800669cf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
