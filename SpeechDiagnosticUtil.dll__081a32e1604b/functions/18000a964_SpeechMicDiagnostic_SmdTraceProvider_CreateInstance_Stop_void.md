# SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::Stop(void *)

- ea: `0x18000a964`
- end: `0x18000ac59`
- name: `?Stop@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `757`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007e38`

## callees

- `0x180001640`
- `0x1800019f8`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000a964`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a9d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ab88`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a9d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ab88`
- `KERNEL32!GetCurrentThreadId` at `0x18000abac`
- `KERNEL32!GetCurrentThreadId` at `0x18000abac`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *this,
        RTL_SRWLOCK *a2)
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
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+D0h] [rbp-70h] BYREF
  int v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  int v20; // [rsp+E0h] [rbp-60h] BYREF
  int v21; // [rsp+E4h] [rbp-5Ch] BYREF
  int v22; // [rsp+E8h] [rbp-58h] BYREF
  int v23; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+128h] [rbp-18h] BYREF
  __int64 v32; // [rsp+130h] [rbp-10h] BYREF
  __int64 v33; // [rsp+138h] [rbp-8h] BYREF
  __int64 v34; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v36; // [rsp+170h] [rbp+30h]
  __int64 v37; // [rsp+178h] [rbp+38h]
  int *v38; // [rsp+180h] [rbp+40h]
  __int64 v39; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v41; // [rsp+198h] [rbp+58h]
  PSRWLOCK *v42; // [rsp+1A0h] [rbp+60h]
  __int64 v43; // [rsp+1A8h] [rbp+68h]

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
      v26 = *((_QWORD *)v6 + 6);
      v18 = v6[17];
      v19 = v6[4];
      v27 = *((_QWORD *)v6 + 15);
      v28 = *((_QWORD *)v6 + 14);
      v20 = v6[26];
      v10 = *((_QWORD *)this + 34);
      v29 = *((_QWORD *)v6 + 12);
      v30 = *((_QWORD *)v6 + 11);
      v21 = v6[20];
      v31 = *((_QWORD *)v6 + 9);
      v22 = v6[8];
      v32 = *((_QWORD *)v6 + 3);
      v23 = *v6;
      v33 = *((_QWORD *)v6 + 16);
      v15 = v6[16];
      v34 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v25 = a2;
      v24 = 0x1000000;
      v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v8,
        (unsigned int)word_18001579A,
        v10 + 8,
        v9,
        (__int64)&v17,
        (__int64)&v24,
        (__int64)&SRWLock,
        (__int64)&v34,
        (__int64)&v15,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v25);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    v11 = v17;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v12 > 5u )
    {
      v17 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v43 = 8;
      v41 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      v42 = &v17;
      p_SRWLock = &SRWLock;
      v38 = &v15;
      v36 = &v24;
      v24 = 0;
      v39 = 4;
      v37 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v12,
        (unsigned __int8 *)&word_1800158FE,
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
0x18000a964  push    rbp
0x18000a966  push    rbx
0x18000a967  push    rsi
0x18000a968  push    rdi
0x18000a969  lea     rbp, [rsp-88h]
0x18000a971  sub     rsp, 1C8h
0x18000a978  mov     rax, cs:__security_cookie
0x18000a97f  xor     rax, rsp
0x18000a982  mov     [rbp+0A0h+var_30], rax
0x18000a986  mov     rdi, [rcx+110h]
0x18000a98d  mov     rsi, rdx
0x18000a990  mov     rbx, rcx
0x18000a993  mov     eax, [rdi+48h]
0x18000a996  test    eax, eax
0x18000a998  jns     loc_18000AB69
0x18000a99e  add     rdi, 50h ; 'P'
0x18000a9a2  cmp     eax, [rdi+8]
0x18000a9a5  jnz     loc_18000AB69
0x18000a9ab  test    rdi, rdi
0x18000a9ae  jz      loc_18000AB69
0x18000a9b4  lea     rdx, [rbp+0A0h+SRWLock]
0x18000a9b8  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a9bd  mov     rax, [rbx+110h]
0x18000a9c4  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x18000a9c8  mov     dword ptr [rax], 2
0x18000a9ce  test    rcx, rcx
0x18000a9d1  jz      short loc_18000A9DF
0x18000a9d3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a9da  nop     dword ptr [rax+rax+00h]
0x18000a9df  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a9e4  mov     rcx, [rax+8]
0x18000a9e8  mov     eax, [rcx]
0x18000a9ea  cmp     eax, 5
0x18000a9ed  jbe     loc_18000AC38
0x18000a9f3  mov     rax, [rdi+30h]
0x18000a9f7  lea     rdx, word_18001579A
0x18000a9fe  mov     [rbp+0A0h+var_E0], rax
0x18000aa02  mov     eax, [rdi+44h]
0x18000aa05  mov     [rbp+0A0h+var_108], eax
0x18000aa08  mov     eax, [rdi+10h]
0x18000aa0b  mov     [rbp+0A0h+var_104], eax
0x18000aa0e  mov     rax, [rdi+78h]
0x18000aa12  mov     [rbp+0A0h+var_D8], rax
0x18000aa16  mov     rax, [rdi+70h]
0x18000aa1a  mov     [rbp+0A0h+var_D0], rax
0x18000aa1e  mov     eax, [rdi+68h]
0x18000aa21  mov     [rbp+0A0h+var_100], eax
0x18000aa24  mov     rax, [rdi+60h]
0x18000aa28  mov     r8, [rbx+110h]
0x18000aa2f  mov     [rbp+0A0h+var_C8], rax
0x18000aa33  add     r8, 8
0x18000aa37  mov     rax, [rdi+58h]
0x18000aa3b  mov     [rbp+0A0h+var_C0], rax
0x18000aa3f  mov     eax, [rdi+50h]
0x18000aa42  mov     [rbp+0A0h+var_FC], eax
0x18000aa45  mov     rax, [rdi+48h]
0x18000aa49  mov     [rbp+0A0h+var_B8], rax
0x18000aa4d  mov     eax, [rdi+20h]
0x18000aa50  mov     [rbp+0A0h+var_F8], eax
0x18000aa53  mov     rax, [rdi+18h]
0x18000aa57  mov     [rbp+0A0h+var_B0], rax
0x18000aa5b  mov     eax, [rdi]
0x18000aa5d  mov     [rbp+0A0h+var_F4], eax
0x18000aa60  mov     rax, [rdi+80h]
0x18000aa67  mov     [rbp+0A0h+var_A8], rax
0x18000aa6b  mov     eax, [rdi+40h]
0x18000aa6e  mov     [rbp+0A0h+var_120], eax
0x18000aa71  mov     rax, [rdi+38h]
0x18000aa75  mov     [rbp+0A0h+var_A0], rax
0x18000aa79  mov     eax, [rdi+8]
0x18000aa7c  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x18000aa7f  lea     rax, [rbp+0A0h+var_E8]
0x18000aa83  mov     [rsp+1E0h+var_128], rax
0x18000aa8b  lea     rax, [rbp+0A0h+var_E0]
0x18000aa8f  mov     [rsp+1E0h+var_130], rax
0x18000aa97  lea     rax, [rbp+0A0h+var_108]
0x18000aa9b  mov     [rsp+1E0h+var_138], rax
0x18000aaa3  lea     rax, [rbp+0A0h+var_104]
0x18000aaa7  mov     [rsp+1E0h+var_140], rax
0x18000aaaf  lea     rax, [rbp+0A0h+var_D8]
0x18000aab3  mov     [rsp+1E0h+var_148], rax
0x18000aabb  lea     rax, [rbp+0A0h+var_D0]
0x18000aabf  mov     [rsp+1E0h+var_150], rax
0x18000aac7  lea     rax, [rbp+0A0h+var_100]
0x18000aacb  mov     [rsp+1E0h+var_158], rax
0x18000aad3  lea     rax, [rbp+0A0h+var_C8]
0x18000aad7  mov     [rsp+1E0h+var_160], rax
0x18000aadf  lea     rax, [rbp+0A0h+var_C0]
0x18000aae3  mov     [rsp+1E0h+var_168], rax
0x18000aae8  lea     rax, [rbp+0A0h+var_FC]
0x18000aaec  mov     [rsp+1E0h+var_170], rax
0x18000aaf1  lea     rax, [rbp+0A0h+var_B8]
0x18000aaf5  mov     [rsp+1E0h+var_178], rax
0x18000aafa  lea     rax, [rbp+0A0h+var_F8]
0x18000aafe  mov     [rsp+1E0h+var_180], rax
0x18000ab03  lea     rax, [rbp+0A0h+var_B0]
0x18000ab07  mov     [rsp+1E0h+var_188], rax
0x18000ab0c  lea     rax, [rbp+0A0h+var_F4]
0x18000ab10  mov     [rsp+1E0h+var_190], rax
0x18000ab15  lea     rax, [rbp+0A0h+var_A8]
0x18000ab19  mov     [rsp+1E0h+var_198], rax
0x18000ab1e  lea     rax, [rbp+0A0h+var_120]
0x18000ab22  mov     [rsp+1E0h+var_1A0], rax
0x18000ab27  lea     rax, [rbp+0A0h+var_A0]
0x18000ab2b  mov     [rsp+1E0h+var_1A8], rax
0x18000ab30  lea     rax, [rbp+0A0h+SRWLock]
0x18000ab34  mov     [rsp+1E0h+var_1B0], rax
0x18000ab39  lea     rax, [rbp+0A0h+var_F0]
0x18000ab3d  mov     [rsp+1E0h+var_1B8], rax
0x18000ab42  lea     rax, [rbp+0A0h+var_110]
0x18000ab46  mov     [rsp+1E0h+var_1C0], rax
0x18000ab4b  mov     [rbp+0A0h+var_E8], rsi
0x18000ab4f  mov     [rbp+0A0h+var_F0], 1000000h
0x18000ab57  mov     [rbp+0A0h+var_110], 0
0x18000ab5f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564453@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ab64  jmp     loc_18000AC38
0x18000ab69  lea     rdx, [rbp+0A0h+var_110]
0x18000ab6d  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ab72  mov     rax, [rbx+110h]
0x18000ab79  mov     rcx, [rbp+0A0h+var_110]; SRWLock
0x18000ab7d  mov     dword ptr [rax], 2
0x18000ab83  test    rcx, rcx
0x18000ab86  jz      short loc_18000AB94
0x18000ab88  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab8f  nop     dword ptr [rax+rax+00h]
0x18000ab94  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000ab99  mov     rdi, [rax+8]
0x18000ab9d  mov     eax, [rdi]
0x18000ab9f  cmp     eax, 5
0x18000aba2  jbe     loc_18000AC38
0x18000aba8  mov     [rbp+0A0h+var_110], rsi
0x18000abac  call    cs:__imp_GetCurrentThreadId
0x18000abb3  nop     dword ptr [rax+rax+00h]
0x18000abb8  mov     r8, [rbx+110h]
0x18000abbf  lea     rdx, word_1800158FE
0x18000abc6  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x18000abc9  xor     r9d, r9d
0x18000abcc  mov     rcx, rdi
0x18000abcf  mov     [rbp+0A0h+var_38], 8
0x18000abd7  mov     [rbp+0A0h+var_48], 4
0x18000abdf  mov     eax, [r8+48h]
0x18000abe3  add     r8, 8
0x18000abe7  mov     [rbp+0A0h+var_120], eax
0x18000abea  lea     rax, [rbp+0A0h+var_110]
0x18000abee  mov     [rbp+0A0h+var_40], rax
0x18000abf2  lea     rax, [rbp+0A0h+SRWLock]
0x18000abf6  mov     [rbp+0A0h+var_50], rax
0x18000abfa  lea     rax, [rbp+0A0h+var_120]
0x18000abfe  mov     [rbp+0A0h+var_60], rax
0x18000ac02  lea     rax, [rbp+0A0h+var_F0]
0x18000ac06  mov     [rbp+0A0h+var_70], rax
0x18000ac0a  lea     rax, [rbp+0A0h+var_90]
0x18000ac0e  mov     [rsp+1E0h+var_1B8], rax
0x18000ac13  mov     dword ptr [rsp+1E0h+var_1C0], 6
0x18000ac1b  mov     [rbp+0A0h+var_F0], 0
0x18000ac23  mov     [rbp+0A0h+var_58], 4
0x18000ac2b  mov     [rbp+0A0h+var_68], 8
0x18000ac33  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ac38  mov     rcx, rbx
0x18000ac3b  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000ac40  mov     rcx, [rbp+0A0h+var_30]
0x18000ac44  xor     rcx, rsp; StackCookie
0x18000ac47  call    __security_check_cookie
0x18000ac4c  add     rsp, 1C8h
0x18000ac53  pop     rdi
0x18000ac54  pop     rsi
0x18000ac55  pop     rbx
0x18000ac56  pop     rbp
0x18000ac57  retn
```
