# SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel::Stop(float)

- ea: `0x18000af58`
- end: `0x18000b265`
- name: `?Stop@GetMicrophoneLevel@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXM@Z`
- size: `781`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel *__hidden this, float)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008190`

## callees

- `0x180001640`
- `0x180001d24`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000af58`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000afcf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b185`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000afcf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b185`
- `KERNEL32!GetCurrentThreadId` at `0x18000b1aa`
- `KERNEL32!GetCurrentThreadId` at `0x18000b1aa`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel *this,
        float a2)
{
  __int64 v2; // rdi
  int v4; // eax
  int *v5; // rdi
  RTL_SRWLOCK *v6; // rcx
  _DWORD *v7; // rcx
  int v8; // r9d
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  _DWORD *v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v15; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+D0h] [rbp-70h] BYREF
  float v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  int v20; // [rsp+E0h] [rbp-60h] BYREF
  int v21; // [rsp+E4h] [rbp-5Ch] BYREF
  int v22; // [rsp+E8h] [rbp-58h] BYREF
  int v23; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+128h] [rbp-18h] BYREF
  __int64 v32; // [rsp+130h] [rbp-10h] BYREF
  __int64 v33; // [rsp+138h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v35; // [rsp+160h] [rbp+20h]
  __int64 v36; // [rsp+168h] [rbp+28h]
  int *v37; // [rsp+170h] [rbp+30h]
  __int64 v38; // [rsp+178h] [rbp+38h]
  DWORD *v39; // [rsp+180h] [rbp+40h]
  __int64 v40; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v42; // [rsp+198h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v2 + 72);
  if ( v4 < 0 && (v5 = (int *)(v2 + 80), v4 == v5[2]) && v5 )
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v6 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    v7 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v7 > 5u )
    {
      v24 = *((_QWORD *)v5 + 6);
      v19 = v5[17];
      v20 = v5[4];
      v25 = *((_QWORD *)v5 + 15);
      v26 = *((_QWORD *)v5 + 14);
      v21 = v5[26];
      v9 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v5 + 12);
      v28 = *((_QWORD *)v5 + 11);
      v22 = v5[20];
      v29 = *((_QWORD *)v5 + 9);
      v23 = v5[8];
      v30 = *((_QWORD *)v5 + 3);
      v14 = *v5;
      v31 = *((_QWORD *)v5 + 16);
      v15 = v5[16];
      v32 = *((_QWORD *)v5 + 7);
      LODWORD(SRWLock) = v5[2];
      v18 = a2;
      v33 = 0x1000000;
      v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)&unk_180014368,
        v9 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v33,
        (__int64)&SRWLock,
        (__int64)&v32,
        (__int64)&v15,
        (__int64)&v31,
        (__int64)&v14,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v24,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    v10 = v17;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v11 > 5u )
    {
      *(float *)&SRWLock = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v15 = CurrentThreadId;
      v42 = 4;
      v40 = 4;
      v14 = *(_DWORD *)(v13 + 72);
      p_SRWLock = &SRWLock;
      v39 = &v15;
      v37 = &v14;
      v35 = &v17;
      v17 = 0;
      v38 = 4;
      v36 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v11,
        (unsigned __int8 *)&dword_1800144BC,
        (const GUID *)(v13 + 8),
        0,
        6u,
        &v34);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000af58  mov     rax, rsp
0x18000af5b  mov     [rax+10h], rbx
0x18000af5f  mov     [rax+18h], rdi
0x18000af63  push    rbp
0x18000af64  lea     rbp, [rsp-80h]
0x18000af69  sub     rsp, 1C0h
0x18000af70  movaps  xmmword ptr [rax-18h], xmm6
0x18000af74  mov     rax, cs:__security_cookie
0x18000af7b  xor     rax, rsp
0x18000af7e  mov     [rbp+80h+var_20], rax
0x18000af82  mov     rdi, [rcx+110h]
0x18000af89  movaps  xmm6, xmm1
0x18000af8c  mov     rbx, rcx
0x18000af8f  mov     eax, [rdi+48h]
0x18000af92  test    eax, eax
0x18000af94  jns     loc_18000B166
0x18000af9a  add     rdi, 50h ; 'P'
0x18000af9e  cmp     eax, [rdi+8]
0x18000afa1  jnz     loc_18000B166
0x18000afa7  test    rdi, rdi
0x18000afaa  jz      loc_18000B166
0x18000afb0  lea     rdx, [rbp+80h+SRWLock]
0x18000afb4  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000afb9  mov     rax, [rbx+110h]
0x18000afc0  mov     rcx, [rbp+80h+SRWLock]; SRWLock
0x18000afc4  mov     dword ptr [rax], 2
0x18000afca  test    rcx, rcx
0x18000afcd  jz      short loc_18000AFDB
0x18000afcf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000afd6  nop     dword ptr [rax+rax+00h]
0x18000afdb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000afe0  mov     rcx, [rax+8]
0x18000afe4  mov     eax, [rcx]
0x18000afe6  cmp     eax, 5
0x18000afe9  jbe     loc_18000B236
0x18000afef  mov     rax, [rdi+30h]
0x18000aff3  lea     rdx, unk_180014368
0x18000affa  mov     [rbp+80h+var_D0], rax
0x18000affe  mov     eax, [rdi+44h]
0x18000b001  mov     [rbp+80h+var_E4], eax
0x18000b004  mov     eax, [rdi+10h]
0x18000b007  mov     [rbp+80h+var_E0], eax
0x18000b00a  mov     rax, [rdi+78h]
0x18000b00e  mov     [rbp+80h+var_C8], rax
0x18000b012  mov     rax, [rdi+70h]
0x18000b016  mov     [rbp+80h+var_C0], rax
0x18000b01a  mov     eax, [rdi+68h]
0x18000b01d  mov     [rbp+80h+var_DC], eax
0x18000b020  mov     rax, [rdi+60h]
0x18000b024  mov     r8, [rbx+110h]
0x18000b02b  mov     [rbp+80h+var_B8], rax
0x18000b02f  add     r8, 8
0x18000b033  mov     rax, [rdi+58h]
0x18000b037  mov     [rbp+80h+var_B0], rax
0x18000b03b  mov     eax, [rdi+50h]
0x18000b03e  mov     [rbp+80h+var_D8], eax
0x18000b041  mov     rax, [rdi+48h]
0x18000b045  mov     [rbp+80h+var_A8], rax
0x18000b049  mov     eax, [rdi+20h]
0x18000b04c  mov     [rbp+80h+var_D4], eax
0x18000b04f  mov     rax, [rdi+18h]
0x18000b053  mov     [rbp+80h+var_A0], rax
0x18000b057  mov     eax, [rdi]
0x18000b059  mov     [rbp+80h+var_100], eax
0x18000b05c  mov     rax, [rdi+80h]
0x18000b063  mov     [rbp+80h+var_98], rax
0x18000b067  mov     eax, [rdi+40h]
0x18000b06a  mov     [rbp+80h+var_FC], eax
0x18000b06d  mov     rax, [rdi+38h]
0x18000b071  mov     [rbp+80h+var_90], rax
0x18000b075  mov     eax, [rdi+8]
0x18000b078  mov     dword ptr [rbp+80h+SRWLock], eax
0x18000b07b  lea     rax, [rbp+80h+var_E8]
0x18000b07f  mov     [rsp+1C0h+var_108], rax
0x18000b087  lea     rax, [rbp+80h+var_D0]
0x18000b08b  mov     [rsp+1C0h+var_110], rax
0x18000b093  lea     rax, [rbp+80h+var_E4]
0x18000b097  mov     [rsp+1C0h+var_118], rax
0x18000b09f  lea     rax, [rbp+80h+var_E0]
0x18000b0a3  mov     [rsp+1C0h+var_120], rax
0x18000b0ab  lea     rax, [rbp+80h+var_C8]
0x18000b0af  mov     [rsp+1C0h+var_128], rax
0x18000b0b7  lea     rax, [rbp+80h+var_C0]
0x18000b0bb  mov     [rsp+1C0h+var_130], rax
0x18000b0c3  lea     rax, [rbp+80h+var_DC]
0x18000b0c7  mov     [rsp+1C0h+var_138], rax
0x18000b0cf  lea     rax, [rbp+80h+var_B8]
0x18000b0d3  mov     [rsp+1C0h+var_140], rax
0x18000b0db  lea     rax, [rbp+80h+var_B0]
0x18000b0df  mov     [rsp+1C0h+var_148], rax
0x18000b0e4  lea     rax, [rbp+80h+var_D8]
0x18000b0e8  mov     [rsp+1C0h+var_150], rax
0x18000b0ed  lea     rax, [rbp+80h+var_A8]
0x18000b0f1  mov     [rsp+1C0h+var_158], rax
0x18000b0f6  lea     rax, [rbp+80h+var_D4]
0x18000b0fa  mov     [rsp+1C0h+var_160], rax
0x18000b0ff  lea     rax, [rbp+80h+var_A0]
0x18000b103  mov     [rsp+1C0h+var_168], rax
0x18000b108  lea     rax, [rbp+80h+var_100]
0x18000b10c  mov     [rsp+1C0h+var_170], rax
0x18000b111  lea     rax, [rbp+80h+var_98]
0x18000b115  mov     [rsp+1C0h+var_178], rax
0x18000b11a  lea     rax, [rbp+80h+var_FC]
0x18000b11e  mov     [rsp+1C0h+var_180], rax
0x18000b123  lea     rax, [rbp+80h+var_90]
0x18000b127  mov     [rsp+1C0h+var_188], rax
0x18000b12c  lea     rax, [rbp+80h+SRWLock]
0x18000b130  mov     [rsp+1C0h+var_190], rax
0x18000b135  lea     rax, [rbp+80h+var_88]
0x18000b139  mov     [rsp+1C0h+var_198], rax
0x18000b13e  lea     rax, [rbp+80h+var_F0]
0x18000b142  mov     [rsp+1C0h+var_1A0], rax
0x18000b147  movss   [rbp+80h+var_E8], xmm6
0x18000b14c  mov     [rbp+80h+var_88], 1000000h
0x18000b154  mov     [rbp+80h+var_F0], 0
0x18000b15c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000b161  jmp     loc_18000B236
0x18000b166  lea     rdx, [rbp+80h+var_F0]
0x18000b16a  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b16f  mov     rax, [rbx+110h]
0x18000b176  mov     rcx, [rbp+80h+var_F0]; SRWLock
0x18000b17a  mov     dword ptr [rax], 2
0x18000b180  test    rcx, rcx
0x18000b183  jz      short loc_18000B191
0x18000b185  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b18c  nop     dword ptr [rax+rax+00h]
0x18000b191  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b196  mov     rdi, [rax+8]
0x18000b19a  mov     eax, [rdi]
0x18000b19c  cmp     eax, 5
0x18000b19f  jbe     loc_18000B236
0x18000b1a5  movss   dword ptr [rbp+80h+SRWLock], xmm6
0x18000b1aa  call    cs:__imp_GetCurrentThreadId
0x18000b1b1  nop     dword ptr [rax+rax+00h]
0x18000b1b6  mov     r8, [rbx+110h]
0x18000b1bd  lea     rdx, dword_1800144BC
0x18000b1c4  mov     [rbp+80h+var_FC], eax
0x18000b1c7  xor     r9d, r9d
0x18000b1ca  mov     rcx, rdi
0x18000b1cd  mov     [rbp+80h+var_28], 4
0x18000b1d5  mov     [rbp+80h+var_38], 4
0x18000b1dd  mov     eax, [r8+48h]
0x18000b1e1  add     r8, 8
0x18000b1e5  mov     [rbp+80h+var_100], eax
0x18000b1e8  lea     rax, [rbp+80h+SRWLock]
0x18000b1ec  mov     [rbp+80h+var_30], rax
0x18000b1f0  lea     rax, [rbp+80h+var_FC]
0x18000b1f4  mov     [rbp+80h+var_40], rax
0x18000b1f8  lea     rax, [rbp+80h+var_100]
0x18000b1fc  mov     [rbp+80h+var_50], rax
0x18000b200  lea     rax, [rbp+80h+var_F0]
0x18000b204  mov     [rbp+80h+var_60], rax
0x18000b208  lea     rax, [rbp+80h+var_80]
0x18000b20c  mov     [rsp+1C0h+var_198], rax
0x18000b211  mov     dword ptr [rsp+1C0h+var_1A0], 6
0x18000b219  mov     [rbp+80h+var_F0], 0
0x18000b221  mov     [rbp+80h+var_48], 4
0x18000b229  mov     [rbp+80h+var_58], 8
0x18000b231  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b236  mov     rcx, rbx
0x18000b239  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b23e  mov     rcx, [rbp+80h+var_20]
0x18000b242  xor     rcx, rsp; StackCookie
0x18000b245  call    __security_check_cookie
0x18000b24a  lea     r11, [rsp+1C0h+var_s0]
0x18000b252  mov     rbx, [r11+18h]
0x18000b256  mov     rdi, [r11+20h]
0x18000b25a  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b25f  mov     rsp, r11
0x18000b262  pop     rbp
0x18000b263  retn
```
