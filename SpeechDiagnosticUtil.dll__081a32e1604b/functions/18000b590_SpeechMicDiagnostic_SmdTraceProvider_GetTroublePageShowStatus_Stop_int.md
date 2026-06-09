# SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::Stop(int)

- ea: `0x18000b590`
- end: `0x18000b87f`
- name: `?Stop@GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXH@Z`
- size: `751`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x180001640`
- `0x180001d24`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000b590`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b5fb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b7af`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b5fb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b7af`
- `KERNEL32!GetCurrentThreadId` at `0x18000b7d2`
- `KERNEL32!GetCurrentThreadId` at `0x18000b7d2`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *this,
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
        (unsigned int)&word_18001540E,
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
        (unsigned __int8 *)byte_18001557B,
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
0x18000b590  push    rbp
0x18000b592  push    rbx
0x18000b593  push    rsi
0x18000b594  push    rdi
0x18000b595  lea     rbp, [rsp-78h]
0x18000b59a  sub     rsp, 1B8h
0x18000b5a1  mov     rax, cs:__security_cookie
0x18000b5a8  xor     rax, rsp
0x18000b5ab  mov     [rbp+90h+var_30], rax
0x18000b5af  mov     rdi, [rcx+110h]
0x18000b5b6  mov     esi, edx
0x18000b5b8  mov     rbx, rcx
0x18000b5bb  mov     eax, [rdi+48h]
0x18000b5be  test    eax, eax
0x18000b5c0  jns     loc_18000B790
0x18000b5c6  add     rdi, 50h ; 'P'
0x18000b5ca  cmp     eax, [rdi+8]
0x18000b5cd  jnz     loc_18000B790
0x18000b5d3  test    rdi, rdi
0x18000b5d6  jz      loc_18000B790
0x18000b5dc  lea     rdx, [rbp+90h+SRWLock]
0x18000b5e0  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b5e5  mov     rax, [rbx+110h]
0x18000b5ec  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x18000b5f0  mov     dword ptr [rax], 2
0x18000b5f6  test    rcx, rcx
0x18000b5f9  jz      short loc_18000B607
0x18000b5fb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b602  nop     dword ptr [rax+rax+00h]
0x18000b607  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b60c  mov     rcx, [rax+8]
0x18000b610  mov     eax, [rcx]
0x18000b612  cmp     eax, 5
0x18000b615  jbe     loc_18000B85E
0x18000b61b  mov     rax, [rdi+30h]
0x18000b61f  lea     rdx, word_18001540E
0x18000b626  mov     [rbp+90h+var_E0], rax
0x18000b62a  mov     eax, [rdi+44h]
0x18000b62d  mov     [rbp+90h+var_F4], eax
0x18000b630  mov     eax, [rdi+10h]
0x18000b633  mov     [rbp+90h+var_F0], eax
0x18000b636  mov     rax, [rdi+78h]
0x18000b63a  mov     [rbp+90h+var_D8], rax
0x18000b63e  mov     rax, [rdi+70h]
0x18000b642  mov     [rbp+90h+var_D0], rax
0x18000b646  mov     eax, [rdi+68h]
0x18000b649  mov     [rbp+90h+var_EC], eax
0x18000b64c  mov     rax, [rdi+60h]
0x18000b650  mov     r8, [rbx+110h]
0x18000b657  mov     [rbp+90h+var_C8], rax
0x18000b65b  add     r8, 8
0x18000b65f  mov     rax, [rdi+58h]
0x18000b663  mov     [rbp+90h+var_C0], rax
0x18000b667  mov     eax, [rdi+50h]
0x18000b66a  mov     [rbp+90h+var_E8], eax
0x18000b66d  mov     rax, [rdi+48h]
0x18000b671  mov     [rbp+90h+var_B8], rax
0x18000b675  mov     eax, [rdi+20h]
0x18000b678  mov     [rbp+90h+var_E4], eax
0x18000b67b  mov     rax, [rdi+18h]
0x18000b67f  mov     [rbp+90h+var_B0], rax
0x18000b683  mov     eax, [rdi]
0x18000b685  mov     [rbp+90h+var_110], eax
0x18000b688  mov     rax, [rdi+80h]
0x18000b68f  mov     [rbp+90h+var_A8], rax
0x18000b693  mov     eax, [rdi+40h]
0x18000b696  mov     [rbp+90h+var_10C], eax
0x18000b699  mov     rax, [rdi+38h]
0x18000b69d  mov     [rbp+90h+var_A0], rax
0x18000b6a1  mov     eax, [rdi+8]
0x18000b6a4  mov     dword ptr [rbp+90h+SRWLock], eax
0x18000b6a7  lea     rax, [rbp+90h+var_F8]
0x18000b6ab  mov     [rsp+1D0h+var_118], rax
0x18000b6b3  lea     rax, [rbp+90h+var_E0]
0x18000b6b7  mov     [rsp+1D0h+var_120], rax
0x18000b6bf  lea     rax, [rbp+90h+var_F4]
0x18000b6c3  mov     [rsp+1D0h+var_128], rax
0x18000b6cb  lea     rax, [rbp+90h+var_F0]
0x18000b6cf  mov     [rsp+1D0h+var_130], rax
0x18000b6d7  lea     rax, [rbp+90h+var_D8]
0x18000b6db  mov     [rsp+1D0h+var_138], rax
0x18000b6e3  lea     rax, [rbp+90h+var_D0]
0x18000b6e7  mov     [rsp+1D0h+var_140], rax
0x18000b6ef  lea     rax, [rbp+90h+var_EC]
0x18000b6f3  mov     [rsp+1D0h+var_148], rax
0x18000b6fb  lea     rax, [rbp+90h+var_C8]
0x18000b6ff  mov     [rsp+1D0h+var_150], rax
0x18000b707  lea     rax, [rbp+90h+var_C0]
0x18000b70b  mov     [rsp+1D0h+var_158], rax
0x18000b710  lea     rax, [rbp+90h+var_E8]
0x18000b714  mov     [rsp+1D0h+var_160], rax
0x18000b719  lea     rax, [rbp+90h+var_B8]
0x18000b71d  mov     [rsp+1D0h+var_168], rax
0x18000b722  lea     rax, [rbp+90h+var_E4]
0x18000b726  mov     [rsp+1D0h+var_170], rax
0x18000b72b  lea     rax, [rbp+90h+var_B0]
0x18000b72f  mov     [rsp+1D0h+var_178], rax
0x18000b734  lea     rax, [rbp+90h+var_110]
0x18000b738  mov     [rsp+1D0h+var_180], rax
0x18000b73d  lea     rax, [rbp+90h+var_A8]
0x18000b741  mov     [rsp+1D0h+var_188], rax
0x18000b746  lea     rax, [rbp+90h+var_10C]
0x18000b74a  mov     [rsp+1D0h+var_190], rax
0x18000b74f  lea     rax, [rbp+90h+var_A0]
0x18000b753  mov     [rsp+1D0h+var_198], rax
0x18000b758  lea     rax, [rbp+90h+SRWLock]
0x18000b75c  mov     [rsp+1D0h+var_1A0], rax
0x18000b761  lea     rax, [rbp+90h+var_98]
0x18000b765  mov     [rsp+1D0h+var_1A8], rax
0x18000b76a  lea     rax, [rbp+90h+var_100]
0x18000b76e  mov     [rsp+1D0h+var_1B0], rax
0x18000b773  mov     [rbp+90h+var_F8], esi
0x18000b776  mov     [rbp+90h+var_98], 1000000h
0x18000b77e  mov     [rbp+90h+var_100], 0
0x18000b786  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000b78b  jmp     loc_18000B85E
0x18000b790  lea     rdx, [rbp+90h+var_100]
0x18000b794  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b799  mov     rax, [rbx+110h]
0x18000b7a0  mov     rcx, [rbp+90h+var_100]; SRWLock
0x18000b7a4  mov     dword ptr [rax], 2
0x18000b7aa  test    rcx, rcx
0x18000b7ad  jz      short loc_18000B7BB
0x18000b7af  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b7b6  nop     dword ptr [rax+rax+00h]
0x18000b7bb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b7c0  mov     rdi, [rax+8]
0x18000b7c4  mov     eax, [rdi]
0x18000b7c6  cmp     eax, 5
0x18000b7c9  jbe     loc_18000B85E
0x18000b7cf  mov     dword ptr [rbp+90h+SRWLock], esi
0x18000b7d2  call    cs:__imp_GetCurrentThreadId
0x18000b7d9  nop     dword ptr [rax+rax+00h]
0x18000b7de  mov     r8, [rbx+110h]
0x18000b7e5  lea     rdx, byte_18001557B
0x18000b7ec  mov     [rbp+90h+var_10C], eax
0x18000b7ef  xor     r9d, r9d
0x18000b7f2  mov     rcx, rdi
0x18000b7f5  mov     [rbp+90h+var_38], 4
0x18000b7fd  mov     [rbp+90h+var_48], 4
0x18000b805  mov     eax, [r8+48h]
0x18000b809  add     r8, 8
0x18000b80d  mov     [rbp+90h+var_110], eax
0x18000b810  lea     rax, [rbp+90h+SRWLock]
0x18000b814  mov     [rbp+90h+var_40], rax
0x18000b818  lea     rax, [rbp+90h+var_10C]
0x18000b81c  mov     [rbp+90h+var_50], rax
0x18000b820  lea     rax, [rbp+90h+var_110]
0x18000b824  mov     [rbp+90h+var_60], rax
0x18000b828  lea     rax, [rbp+90h+var_100]
0x18000b82c  mov     [rbp+90h+var_70], rax
0x18000b830  lea     rax, [rbp+90h+var_90]
0x18000b834  mov     [rsp+1D0h+var_1A8], rax
0x18000b839  mov     dword ptr [rsp+1D0h+var_1B0], 6
0x18000b841  mov     [rbp+90h+var_100], 0
0x18000b849  mov     [rbp+90h+var_58], 4
0x18000b851  mov     [rbp+90h+var_68], 8
0x18000b859  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b85e  mov     rcx, rbx
0x18000b861  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b866  mov     rcx, [rbp+90h+var_30]
0x18000b86a  xor     rcx, rsp; StackCookie
0x18000b86d  call    __security_check_cookie
0x18000b872  add     rsp, 1B8h
0x18000b879  pop     rdi
0x18000b87a  pop     rsi
0x18000b87b  pop     rbx
0x18000b87c  pop     rbp
0x18000b87d  retn
```
