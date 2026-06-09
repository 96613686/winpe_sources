# MtfPlatformTelemetry::RequestSuggestion::StopActivity(void)

- ea: `0x18001bc80`
- end: `0x18001beee`
- name: `?StopActivity@RequestSuggestion@MtfPlatformTelemetry@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(MtfPlatformTelemetry::RequestSuggestion *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800016dc`
- `0x1800019f0`
- `0x1800053cc`
- `0x180018c84`
- `0x180018d00`
- `0x18001bc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bcda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bcda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8f`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::RequestSuggestion::StopActivity(MtfPlatformTelemetry::RequestSuggestion *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  _DWORD *v6; // rcx
  int v7; // r9d
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
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
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v6 > 5u )
    {
      v18 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)&dword_18003699C,
        v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&byte_180036B2F,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001bc80  push    rbp
0x18001bc82  push    rbx
0x18001bc83  push    rdi
0x18001bc84  lea     rbp, [rsp+10h]
0x18001bc89  sub     rsp, 130h
0x18001bc90  mov     rdi, [rcx+110h]
0x18001bc97  mov     rbx, rcx
0x18001bc9a  mov     eax, [rdi+48h]
0x18001bc9d  test    eax, eax
0x18001bc9f  jns     loc_18001BE5A
0x18001bca5  add     rdi, 50h ; 'P'
0x18001bca9  cmp     eax, [rdi+8]
0x18001bcac  jnz     loc_18001BE5A
0x18001bcb2  test    rdi, rdi
0x18001bcb5  jz      loc_18001BE5A
0x18001bcbb  lea     rdx, [rbp+SRWLock]
0x18001bcbf  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001bcc4  mov     rax, [rbx+110h]
0x18001bccb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001bccf  mov     dword ptr [rax], 2
0x18001bcd5  test    rcx, rcx
0x18001bcd8  jz      short loc_18001BCE0
0x18001bcda  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bce0  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001bce5  mov     rcx, [rax+8]
0x18001bce9  mov     eax, [rcx]
0x18001bceb  cmp     eax, 5
0x18001bcee  jbe     loc_18001BEDC
0x18001bcf4  mov     rax, [rdi+30h]
0x18001bcf8  lea     rdx, dword_18003699C
0x18001bcff  mov     [rbp+var_70], rax
0x18001bd03  mov     eax, [rdi+44h]
0x18001bd06  mov     dword ptr [rbp+SRWLock], eax
0x18001bd09  mov     eax, [rdi+10h]
0x18001bd0c  mov     [rbp+arg_8], eax
0x18001bd0f  mov     rax, [rdi+78h]
0x18001bd13  mov     [rbp+var_68], rax
0x18001bd17  mov     rax, [rdi+70h]
0x18001bd1b  mov     [rbp+var_60], rax
0x18001bd1f  mov     eax, [rdi+68h]
0x18001bd22  mov     r8, [rbx+110h]
0x18001bd29  mov     dword ptr [rbp+arg_10], eax
0x18001bd2c  add     r8, 8
0x18001bd30  mov     rax, [rdi+60h]
0x18001bd34  mov     [rbp+var_58], rax
0x18001bd38  mov     rax, [rdi+58h]
0x18001bd3c  mov     [rbp+var_50], rax
0x18001bd40  mov     eax, [rdi+50h]
0x18001bd43  mov     [rbp+arg_18], eax
0x18001bd46  mov     rax, [rdi+48h]
0x18001bd4a  mov     [rbp+var_48], rax
0x18001bd4e  mov     eax, [rdi+20h]
0x18001bd51  mov     [rbp+var_80], eax
0x18001bd54  mov     rax, [rdi+18h]
0x18001bd58  mov     [rbp+var_40], rax
0x18001bd5c  mov     eax, [rdi]
0x18001bd5e  mov     [rbp+var_7C], eax
0x18001bd61  mov     rax, [rdi+80h]
0x18001bd68  mov     [rbp+var_38], rax
0x18001bd6c  mov     eax, [rdi+40h]
0x18001bd6f  mov     [rbp+var_78], eax
0x18001bd72  mov     rax, [rdi+38h]
0x18001bd76  mov     [rbp+var_30], rax
0x18001bd7a  mov     eax, [rdi+8]
0x18001bd7d  mov     [rbp+var_74], eax
0x18001bd80  lea     rax, [rbp+var_70]
0x18001bd84  mov     [rsp+140h+var_90], rax
0x18001bd8c  lea     rax, [rbp+SRWLock]
0x18001bd90  mov     [rsp+140h+var_98], rax
0x18001bd98  lea     rax, [rbp+arg_8]
0x18001bd9c  mov     [rsp+140h+var_A0], rax
0x18001bda4  lea     rax, [rbp+var_68]
0x18001bda8  mov     [rsp+140h+var_A8], rax
0x18001bdb0  lea     rax, [rbp+var_60]
0x18001bdb4  mov     [rsp+140h+var_B0], rax
0x18001bdbc  lea     rax, [rbp+arg_10]
0x18001bdc0  mov     [rsp+140h+var_B8], rax
0x18001bdc8  lea     rax, [rbp+var_58]
0x18001bdcc  mov     [rsp+140h+var_C0], rax
0x18001bdd4  lea     rax, [rbp+var_50]
0x18001bdd8  mov     [rsp+140h+var_C8], rax
0x18001bddd  lea     rax, [rbp+arg_18]
0x18001bde1  mov     [rsp+140h+var_D0], rax
0x18001bde6  lea     rax, [rbp+var_48]
0x18001bdea  mov     [rsp+140h+var_D8], rax
0x18001bdef  lea     rax, [rbp+var_80]
0x18001bdf3  mov     [rsp+140h+var_E0], rax
0x18001bdf8  lea     rax, [rbp+var_40]
0x18001bdfc  mov     [rsp+140h+var_E8], rax
0x18001be01  lea     rax, [rbp+var_7C]
0x18001be05  mov     [rsp+140h+var_F0], rax
0x18001be0a  lea     rax, [rbp+var_38]
0x18001be0e  mov     [rsp+140h+var_F8], rax
0x18001be13  lea     rax, [rbp+var_78]
0x18001be17  mov     [rsp+140h+var_100], rax
0x18001be1c  lea     rax, [rbp+var_30]
0x18001be20  mov     [rsp+140h+var_108], rax
0x18001be25  lea     rax, [rbp+var_74]
0x18001be29  mov     [rsp+140h+var_110], rax
0x18001be2e  lea     rax, [rbp+var_28]
0x18001be32  mov     [rsp+140h+var_118], rax
0x18001be37  lea     rax, [rbp+var_20]
0x18001be3b  mov     [rsp+140h+var_120], rax
0x18001be40  mov     [rbp+var_28], 1000000h
0x18001be48  mov     [rbp+var_20], 0
0x18001be50  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001be55  jmp     loc_18001BEDC
0x18001be5a  lea     rdx, [rbp+SRWLock]
0x18001be5e  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001be63  mov     rax, [rbx+110h]
0x18001be6a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001be6e  mov     dword ptr [rax], 2
0x18001be74  test    rcx, rcx
0x18001be77  jz      short loc_18001BE7F
0x18001be79  call    cs:__imp_ReleaseSRWLockExclusive
0x18001be7f  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001be84  mov     rdi, [rax+8]
0x18001be88  mov     eax, [rdi]
0x18001be8a  cmp     eax, 5
0x18001be8d  jbe     short loc_18001BEDC
0x18001be8f  call    cs:__imp_GetCurrentThreadId
0x18001be95  mov     r8, [rbx+110h]
0x18001be9c  lea     rdx, byte_180036B2F
0x18001bea3  mov     dword ptr [rbp+SRWLock], eax
0x18001bea6  mov     rcx, rdi
0x18001bea9  mov     eax, [r8+48h]
0x18001bead  add     r8, 8
0x18001beb1  mov     [rbp+arg_8], eax
0x18001beb4  lea     rax, [rbp+SRWLock]
0x18001beb8  mov     [rsp+140h+var_110], rax
0x18001bebd  lea     rax, [rbp+arg_8]
0x18001bec1  mov     [rsp+140h+var_118], rax
0x18001bec6  lea     rax, [rbp+arg_10]
0x18001beca  mov     [rsp+140h+var_120], rax
0x18001becf  mov     [rbp+arg_10], 0
0x18001bed7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001bedc  mov     rcx, rbx
0x18001bedf  add     rsp, 130h
0x18001bee6  pop     rdi
0x18001bee7  pop     rbx
0x18001bee8  pop     rbp
0x18001bee9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
