# SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::Stop(int)

- ea: `0x18000ac60`
- end: `0x18000af4f`
- name: `?Stop@GetDiagnosticResult@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXH@Z`
- size: `751`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008040`

## callees

- `0x180001640`
- `0x180001d24`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000ac60`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000accb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae7f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000accb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae7f`
- `KERNEL32!GetCurrentThreadId` at `0x18000aea2`
- `KERNEL32!GetCurrentThreadId` at `0x18000aea2`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  _DWORD *v8; // rcx
  int v9; // r9d
  __int64 v10; // r8
  RTL_SRWLOCK *v11; // rcx
  _DWORD *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v16; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+D0h] [rbp-70h] BYREF
  int v19; // [rsp+D8h] [rbp-68h] BYREF
  int v20; // [rsp+DCh] [rbp-64h] BYREF
  int v21; // [rsp+E0h] [rbp-60h] BYREF
  int v22; // [rsp+E4h] [rbp-5Ch] BYREF
  int v23; // [rsp+E8h] [rbp-58h] BYREF
  int v24; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+100h] [rbp-40h] BYREF
  __int64 v28; // [rsp+108h] [rbp-38h] BYREF
  __int64 v29; // [rsp+110h] [rbp-30h] BYREF
  __int64 v30; // [rsp+118h] [rbp-28h] BYREF
  __int64 v31; // [rsp+120h] [rbp-20h] BYREF
  __int64 v32; // [rsp+128h] [rbp-18h] BYREF
  __int64 v33; // [rsp+130h] [rbp-10h] BYREF
  __int64 v34; // [rsp+138h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v36; // [rsp+160h] [rbp+20h]
  __int64 v37; // [rsp+168h] [rbp+28h]
  int *v38; // [rsp+170h] [rbp+30h]
  __int64 v39; // [rsp+178h] [rbp+38h]
  DWORD *v40; // [rsp+180h] [rbp+40h]
  __int64 v41; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v43; // [rsp+198h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v7 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v8 > 5u )
    {
      v25 = *((_QWORD *)v6 + 6);
      v20 = v6[17];
      v21 = v6[4];
      v26 = *((_QWORD *)v6 + 15);
      v27 = *((_QWORD *)v6 + 14);
      v22 = v6[26];
      v10 = *((_QWORD *)this + 34);
      v28 = *((_QWORD *)v6 + 12);
      v29 = *((_QWORD *)v6 + 11);
      v23 = v6[20];
      v30 = *((_QWORD *)v6 + 9);
      v24 = v6[8];
      v31 = *((_QWORD *)v6 + 3);
      v15 = *v6;
      v32 = *((_QWORD *)v6 + 16);
      v16 = v6[16];
      v33 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v19 = a2;
      v34 = 0x1000000;
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&word_180014BA6,
        v10 + 8,
        v9,
        (__int64)&v18,
        (__int64)&v34,
        (__int64)&SRWLock,
        (__int64)&v33,
        (__int64)&v16,
        (__int64)&v32,
        (__int64)&v15,
        (__int64)&v31,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v18);
    v11 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v12 > 5u )
    {
      LODWORD(SRWLock) = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v16 = CurrentThreadId;
      v43 = 4;
      v41 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      p_SRWLock = &SRWLock;
      v40 = &v16;
      v38 = &v15;
      v36 = &v18;
      v18 = 0;
      v39 = 4;
      v37 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v12,
        (unsigned __int8 *)&dword_180014CFC,
        (const GUID *)(v14 + 8),
        0,
        6u,
        &v35);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000ac60  push    rbp
0x18000ac62  push    rbx
0x18000ac63  push    rsi
0x18000ac64  push    rdi
0x18000ac65  lea     rbp, [rsp-78h]
0x18000ac6a  sub     rsp, 1B8h
0x18000ac71  mov     rax, cs:__security_cookie
0x18000ac78  xor     rax, rsp
0x18000ac7b  mov     [rbp+90h+var_30], rax
0x18000ac7f  mov     rdi, [rcx+110h]
0x18000ac86  mov     esi, edx
0x18000ac88  mov     rbx, rcx
0x18000ac8b  mov     eax, [rdi+48h]
0x18000ac8e  test    eax, eax
0x18000ac90  jns     loc_18000AE60
0x18000ac96  add     rdi, 50h ; 'P'
0x18000ac9a  cmp     eax, [rdi+8]
0x18000ac9d  jnz     loc_18000AE60
0x18000aca3  test    rdi, rdi
0x18000aca6  jz      loc_18000AE60
0x18000acac  lea     rdx, [rbp+90h+SRWLock]
0x18000acb0  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000acb5  mov     rax, [rbx+110h]
0x18000acbc  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x18000acc0  mov     dword ptr [rax], 2
0x18000acc6  test    rcx, rcx
0x18000acc9  jz      short loc_18000ACD7
0x18000accb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000acd2  nop     dword ptr [rax+rax+00h]
0x18000acd7  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000acdc  mov     rcx, [rax+8]
0x18000ace0  mov     eax, [rcx]
0x18000ace2  cmp     eax, 5
0x18000ace5  jbe     loc_18000AF2E
0x18000aceb  mov     rax, [rdi+30h]
0x18000acef  lea     rdx, word_180014BA6
0x18000acf6  mov     [rbp+90h+var_E0], rax
0x18000acfa  mov     eax, [rdi+44h]
0x18000acfd  mov     [rbp+90h+var_F4], eax
0x18000ad00  mov     eax, [rdi+10h]
0x18000ad03  mov     [rbp+90h+var_F0], eax
0x18000ad06  mov     rax, [rdi+78h]
0x18000ad0a  mov     [rbp+90h+var_D8], rax
0x18000ad0e  mov     rax, [rdi+70h]
0x18000ad12  mov     [rbp+90h+var_D0], rax
0x18000ad16  mov     eax, [rdi+68h]
0x18000ad19  mov     [rbp+90h+var_EC], eax
0x18000ad1c  mov     rax, [rdi+60h]
0x18000ad20  mov     r8, [rbx+110h]
0x18000ad27  mov     [rbp+90h+var_C8], rax
0x18000ad2b  add     r8, 8
0x18000ad2f  mov     rax, [rdi+58h]
0x18000ad33  mov     [rbp+90h+var_C0], rax
0x18000ad37  mov     eax, [rdi+50h]
0x18000ad3a  mov     [rbp+90h+var_E8], eax
0x18000ad3d  mov     rax, [rdi+48h]
0x18000ad41  mov     [rbp+90h+var_B8], rax
0x18000ad45  mov     eax, [rdi+20h]
0x18000ad48  mov     [rbp+90h+var_E4], eax
0x18000ad4b  mov     rax, [rdi+18h]
0x18000ad4f  mov     [rbp+90h+var_B0], rax
0x18000ad53  mov     eax, [rdi]
0x18000ad55  mov     [rbp+90h+var_110], eax
0x18000ad58  mov     rax, [rdi+80h]
0x18000ad5f  mov     [rbp+90h+var_A8], rax
0x18000ad63  mov     eax, [rdi+40h]
0x18000ad66  mov     [rbp+90h+var_10C], eax
0x18000ad69  mov     rax, [rdi+38h]
0x18000ad6d  mov     [rbp+90h+var_A0], rax
0x18000ad71  mov     eax, [rdi+8]
0x18000ad74  mov     dword ptr [rbp+90h+SRWLock], eax
0x18000ad77  lea     rax, [rbp+90h+var_F8]
0x18000ad7b  mov     [rsp+1D0h+var_118], rax
0x18000ad83  lea     rax, [rbp+90h+var_E0]
0x18000ad87  mov     [rsp+1D0h+var_120], rax
0x18000ad8f  lea     rax, [rbp+90h+var_F4]
0x18000ad93  mov     [rsp+1D0h+var_128], rax
0x18000ad9b  lea     rax, [rbp+90h+var_F0]
0x18000ad9f  mov     [rsp+1D0h+var_130], rax
0x18000ada7  lea     rax, [rbp+90h+var_D8]
0x18000adab  mov     [rsp+1D0h+var_138], rax
0x18000adb3  lea     rax, [rbp+90h+var_D0]
0x18000adb7  mov     [rsp+1D0h+var_140], rax
0x18000adbf  lea     rax, [rbp+90h+var_EC]
0x18000adc3  mov     [rsp+1D0h+var_148], rax
0x18000adcb  lea     rax, [rbp+90h+var_C8]
0x18000adcf  mov     [rsp+1D0h+var_150], rax
0x18000add7  lea     rax, [rbp+90h+var_C0]
0x18000addb  mov     [rsp+1D0h+var_158], rax
0x18000ade0  lea     rax, [rbp+90h+var_E8]
0x18000ade4  mov     [rsp+1D0h+var_160], rax
0x18000ade9  lea     rax, [rbp+90h+var_B8]
0x18000aded  mov     [rsp+1D0h+var_168], rax
0x18000adf2  lea     rax, [rbp+90h+var_E4]
0x18000adf6  mov     [rsp+1D0h+var_170], rax
0x18000adfb  lea     rax, [rbp+90h+var_B0]
0x18000adff  mov     [rsp+1D0h+var_178], rax
0x18000ae04  lea     rax, [rbp+90h+var_110]
0x18000ae08  mov     [rsp+1D0h+var_180], rax
0x18000ae0d  lea     rax, [rbp+90h+var_A8]
0x18000ae11  mov     [rsp+1D0h+var_188], rax
0x18000ae16  lea     rax, [rbp+90h+var_10C]
0x18000ae1a  mov     [rsp+1D0h+var_190], rax
0x18000ae1f  lea     rax, [rbp+90h+var_A0]
0x18000ae23  mov     [rsp+1D0h+var_198], rax
0x18000ae28  lea     rax, [rbp+90h+SRWLock]
0x18000ae2c  mov     [rsp+1D0h+var_1A0], rax
0x18000ae31  lea     rax, [rbp+90h+var_98]
0x18000ae35  mov     [rsp+1D0h+var_1A8], rax
0x18000ae3a  lea     rax, [rbp+90h+var_100]
0x18000ae3e  mov     [rsp+1D0h+var_1B0], rax
0x18000ae43  mov     [rbp+90h+var_F8], esi
0x18000ae46  mov     [rbp+90h+var_98], 1000000h
0x18000ae4e  mov     [rbp+90h+var_100], 0
0x18000ae56  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000ae5b  jmp     loc_18000AF2E
0x18000ae60  lea     rdx, [rbp+90h+var_100]
0x18000ae64  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ae69  mov     rax, [rbx+110h]
0x18000ae70  mov     rcx, [rbp+90h+var_100]; SRWLock
0x18000ae74  mov     dword ptr [rax], 2
0x18000ae7a  test    rcx, rcx
0x18000ae7d  jz      short loc_18000AE8B
0x18000ae7f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae86  nop     dword ptr [rax+rax+00h]
0x18000ae8b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000ae90  mov     rdi, [rax+8]
0x18000ae94  mov     eax, [rdi]
0x18000ae96  cmp     eax, 5
0x18000ae99  jbe     loc_18000AF2E
0x18000ae9f  mov     dword ptr [rbp+90h+SRWLock], esi
0x18000aea2  call    cs:__imp_GetCurrentThreadId
0x18000aea9  nop     dword ptr [rax+rax+00h]
0x18000aeae  mov     r8, [rbx+110h]
0x18000aeb5  lea     rdx, dword_180014CFC
0x18000aebc  mov     [rbp+90h+var_10C], eax
0x18000aebf  xor     r9d, r9d
0x18000aec2  mov     rcx, rdi
0x18000aec5  mov     [rbp+90h+var_38], 4
0x18000aecd  mov     [rbp+90h+var_48], 4
0x18000aed5  mov     eax, [r8+48h]
0x18000aed9  add     r8, 8
0x18000aedd  mov     [rbp+90h+var_110], eax
0x18000aee0  lea     rax, [rbp+90h+SRWLock]
0x18000aee4  mov     [rbp+90h+var_40], rax
0x18000aee8  lea     rax, [rbp+90h+var_10C]
0x18000aeec  mov     [rbp+90h+var_50], rax
0x18000aef0  lea     rax, [rbp+90h+var_110]
0x18000aef4  mov     [rbp+90h+var_60], rax
0x18000aef8  lea     rax, [rbp+90h+var_100]
0x18000aefc  mov     [rbp+90h+var_70], rax
0x18000af00  lea     rax, [rbp+90h+var_90]
0x18000af04  mov     [rsp+1D0h+var_1A8], rax
0x18000af09  mov     dword ptr [rsp+1D0h+var_1B0], 6
0x18000af11  mov     [rbp+90h+var_100], 0
0x18000af19  mov     [rbp+90h+var_58], 4
0x18000af21  mov     [rbp+90h+var_68], 8
0x18000af29  call    _tlgWriteTransfer_EventWriteTransfer
0x18000af2e  mov     rcx, rbx
0x18000af31  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000af36  mov     rcx, [rbp+90h+var_30]
0x18000af3a  xor     rcx, rsp; StackCookie
0x18000af3d  call    __security_check_cookie
0x18000af42  add     rsp, 1B8h
0x18000af49  pop     rdi
0x18000af4a  pop     rsi
0x18000af4b  pop     rbx
0x18000af4c  pop     rbp
0x18000af4d  retn
```
