# SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::Stop(ushort const *)

- ea: `0x18000b26c`
- end: `0x18000b58a`
- name: `?Stop@GetPreferredMicDeviceId@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEBG@Z`
- size: `798`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800082d0`

## callees

- `0x180001640`
- `0x180002050`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000b26c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b2e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b49e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b2e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b49e`
- `KERNEL32!GetCurrentThreadId` at `0x18000b4bf`
- `KERNEL32!GetCurrentThreadId` at `0x18000b4bf`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // r14
  int v5; // eax
  int *v6; // r14
  RTL_SRWLOCK *v7; // rcx
  _DWORD *v8; // rcx
  int v9; // r9d
  __int64 v10; // r8
  int v11; // edi
  RTL_SRWLOCK *v12; // rcx
  _DWORD *v13; // r14
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // rdi
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v19; // [rsp+D0h] [rbp-70h] BYREF
  int v20; // [rsp+D8h] [rbp-68h] BYREF
  int v21; // [rsp+DCh] [rbp-64h] BYREF
  int v22; // [rsp+E0h] [rbp-60h] BYREF
  int v23; // [rsp+E4h] [rbp-5Ch] BYREF
  int v24; // [rsp+E8h] [rbp-58h] BYREF
  int v25; // [rsp+ECh] [rbp-54h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33; // [rsp+128h] [rbp-18h] BYREF
  __int64 v34; // [rsp+130h] [rbp-10h] BYREF
  __int64 v35; // [rsp+138h] [rbp-8h] BYREF
  __int64 v36; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+150h] [rbp+10h] BYREF
  PSRWLOCK *v38; // [rsp+170h] [rbp+30h]
  __int64 v39; // [rsp+178h] [rbp+38h]
  int *v40; // [rsp+180h] [rbp+40h]
  __int64 v41; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v43; // [rsp+198h] [rbp+58h]
  const unsigned __int16 *v44; // [rsp+1A0h] [rbp+60h]
  int v45; // [rsp+1A8h] [rbp+68h]
  int v46; // [rsp+1ACh] [rbp+6Ch]

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
      v27 = *((_QWORD *)v6 + 6);
      v20 = v6[17];
      v21 = v6[4];
      v28 = *((_QWORD *)v6 + 15);
      v29 = *((_QWORD *)v6 + 14);
      v22 = v6[26];
      v10 = *((_QWORD *)this + 34);
      v30 = *((_QWORD *)v6 + 12);
      v31 = *((_QWORD *)v6 + 11);
      v23 = v6[20];
      v32 = *((_QWORD *)v6 + 9);
      v24 = v6[8];
      v33 = *((_QWORD *)v6 + 3);
      v25 = *v6;
      v34 = *((_QWORD *)v6 + 16);
      v17 = v6[16];
      v35 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v26 = a2;
      v36 = 0x1000000;
      v19 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&word_1800150A6,
        v10 + 8,
        v9,
        (__int64)&v19,
        (__int64)&v36,
        (__int64)&SRWLock,
        (__int64)&v35,
        (__int64)&v17,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v32,
        (__int64)&v23,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v19);
    v11 = 2;
    v12 = v19;
    **((_DWORD **)this + 34) = 2;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v13 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v13 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v17 = *(_DWORD *)(v15 + 72);
      v19 = 0;
      if ( a2 )
      {
        v16 = -1;
        do
          ++v16;
        while ( a2[v16] );
        v11 = 2 * v16 + 2;
      }
      else
      {
        a2 = (const unsigned __int16 *)qword_180012C50;
      }
      v44 = a2;
      p_SRWLock = &SRWLock;
      v45 = v11;
      v40 = &v17;
      v46 = 0;
      v38 = &v19;
      v43 = 4;
      v41 = 4;
      v39 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v13,
        (unsigned __int8 *)word_180015202,
        (const GUID *)(v15 + 8),
        0,
        6u,
        &v37);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000b26c  push    rbp
0x18000b26e  push    rbx
0x18000b26f  push    rsi
0x18000b270  push    rdi
0x18000b271  push    r14
0x18000b273  push    r15
0x18000b275  lea     rbp, [rsp-88h]
0x18000b27d  sub     rsp, 1C8h
0x18000b284  mov     rax, cs:__security_cookie
0x18000b28b  xor     rax, rsp
0x18000b28e  mov     [rbp+0B0h+var_40], rax
0x18000b292  mov     r14, [rcx+110h]
0x18000b299  xor     r15d, r15d
0x18000b29c  mov     rsi, rdx
0x18000b29f  mov     rbx, rcx
0x18000b2a2  mov     eax, [r14+48h]
0x18000b2a6  test    eax, eax
0x18000b2a8  jns     loc_18000B47E
0x18000b2ae  add     r14, 50h ; 'P'
0x18000b2b2  cmp     eax, [r14+8]
0x18000b2b6  jnz     loc_18000B47E
0x18000b2bc  test    r14, r14
0x18000b2bf  jz      loc_18000B47E
0x18000b2c5  lea     rdx, [rbp+0B0h+SRWLock]
0x18000b2c9  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b2ce  mov     rax, [rbx+110h]
0x18000b2d5  mov     rcx, [rbp+0B0h+SRWLock]; SRWLock
0x18000b2d9  mov     dword ptr [rax], 2
0x18000b2df  test    rcx, rcx
0x18000b2e2  jz      short loc_18000B2F0
0x18000b2e4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2eb  nop     dword ptr [rax+rax+00h]
0x18000b2f0  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b2f5  mov     rcx, [rax+8]
0x18000b2f9  mov     eax, [rcx]
0x18000b2fb  cmp     eax, 5
0x18000b2fe  jbe     loc_18000B565
0x18000b304  mov     rax, [r14+30h]
0x18000b308  lea     rdx, word_1800150A6
0x18000b30f  mov     [rbp+0B0h+var_F8], rax
0x18000b313  mov     eax, [r14+44h]
0x18000b317  mov     [rbp+0B0h+var_118], eax
0x18000b31a  mov     eax, [r14+10h]
0x18000b31e  mov     [rbp+0B0h+var_114], eax
0x18000b321  mov     rax, [r14+78h]
0x18000b325  mov     [rbp+0B0h+var_F0], rax
0x18000b329  mov     rax, [r14+70h]
0x18000b32d  mov     [rbp+0B0h+var_E8], rax
0x18000b331  mov     eax, [r14+68h]
0x18000b335  mov     [rbp+0B0h+var_110], eax
0x18000b338  mov     rax, [r14+60h]
0x18000b33c  mov     r8, [rbx+110h]
0x18000b343  mov     [rbp+0B0h+var_E0], rax
0x18000b347  add     r8, 8
0x18000b34b  mov     rax, [r14+58h]
0x18000b34f  mov     [rbp+0B0h+var_D8], rax
0x18000b353  mov     eax, [r14+50h]
0x18000b357  mov     [rbp+0B0h+var_10C], eax
0x18000b35a  mov     rax, [r14+48h]
0x18000b35e  mov     [rbp+0B0h+var_D0], rax
0x18000b362  mov     eax, [r14+20h]
0x18000b366  mov     [rbp+0B0h+var_108], eax
0x18000b369  mov     rax, [r14+18h]
0x18000b36d  mov     [rbp+0B0h+var_C8], rax
0x18000b371  mov     eax, [r14]
0x18000b374  mov     [rbp+0B0h+var_104], eax
0x18000b377  mov     rax, [r14+80h]
0x18000b37e  mov     [rbp+0B0h+var_C0], rax
0x18000b382  mov     eax, [r14+40h]
0x18000b386  mov     [rbp+0B0h+var_130], eax
0x18000b389  mov     rax, [r14+38h]
0x18000b38d  mov     [rbp+0B0h+var_B8], rax
0x18000b391  mov     eax, [r14+8]
0x18000b395  mov     dword ptr [rbp+0B0h+SRWLock], eax
0x18000b398  lea     rax, [rbp+0B0h+var_100]
0x18000b39c  mov     [rsp+1F0h+var_138], rax
0x18000b3a4  lea     rax, [rbp+0B0h+var_F8]
0x18000b3a8  mov     [rsp+1F0h+var_140], rax
0x18000b3b0  lea     rax, [rbp+0B0h+var_118]
0x18000b3b4  mov     [rsp+1F0h+var_148], rax
0x18000b3bc  lea     rax, [rbp+0B0h+var_114]
0x18000b3c0  mov     [rsp+1F0h+var_150], rax
0x18000b3c8  lea     rax, [rbp+0B0h+var_F0]
0x18000b3cc  mov     [rsp+1F0h+var_158], rax
0x18000b3d4  lea     rax, [rbp+0B0h+var_E8]
0x18000b3d8  mov     [rsp+1F0h+var_160], rax
0x18000b3e0  lea     rax, [rbp+0B0h+var_110]
0x18000b3e4  mov     [rsp+1F0h+var_168], rax
0x18000b3ec  lea     rax, [rbp+0B0h+var_E0]
0x18000b3f0  mov     [rsp+1F0h+var_170], rax
0x18000b3f8  lea     rax, [rbp+0B0h+var_D8]
0x18000b3fc  mov     [rsp+1F0h+var_178], rax
0x18000b401  lea     rax, [rbp+0B0h+var_10C]
0x18000b405  mov     [rsp+1F0h+var_180], rax
0x18000b40a  lea     rax, [rbp+0B0h+var_D0]
0x18000b40e  mov     [rsp+1F0h+var_188], rax
0x18000b413  lea     rax, [rbp+0B0h+var_108]
0x18000b417  mov     [rsp+1F0h+var_190], rax
0x18000b41c  lea     rax, [rbp+0B0h+var_C8]
0x18000b420  mov     [rsp+1F0h+var_198], rax
0x18000b425  lea     rax, [rbp+0B0h+var_104]
0x18000b429  mov     [rsp+1F0h+var_1A0], rax
0x18000b42e  lea     rax, [rbp+0B0h+var_C0]
0x18000b432  mov     [rsp+1F0h+var_1A8], rax
0x18000b437  lea     rax, [rbp+0B0h+var_130]
0x18000b43b  mov     [rsp+1F0h+var_1B0], rax
0x18000b440  lea     rax, [rbp+0B0h+var_B8]
0x18000b444  mov     [rsp+1F0h+var_1B8], rax
0x18000b449  lea     rax, [rbp+0B0h+SRWLock]
0x18000b44d  mov     [rsp+1F0h+var_1C0], rax
0x18000b452  lea     rax, [rbp+0B0h+var_B0]
0x18000b456  mov     [rsp+1F0h+var_1C8], rax
0x18000b45b  lea     rax, [rbp+0B0h+var_120]
0x18000b45f  mov     [rsp+1F0h+var_1D0], rax
0x18000b464  mov     [rbp+0B0h+var_100], rsi
0x18000b468  mov     [rbp+0B0h+var_B0], 1000000h
0x18000b470  mov     [rbp+0B0h+var_120], r15
0x18000b474  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000b479  jmp     loc_18000B565
0x18000b47e  lea     rdx, [rbp+0B0h+var_120]
0x18000b482  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b487  mov     rax, [rbx+110h]
0x18000b48e  mov     edi, 2
0x18000b493  mov     rcx, [rbp+0B0h+var_120]; SRWLock
0x18000b497  mov     [rax], edi
0x18000b499  test    rcx, rcx
0x18000b49c  jz      short loc_18000B4AA
0x18000b49e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b4a5  nop     dword ptr [rax+rax+00h]
0x18000b4aa  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b4af  mov     r14, [rax+8]
0x18000b4b3  mov     eax, [r14]
0x18000b4b6  cmp     eax, 5
0x18000b4b9  jbe     loc_18000B565
0x18000b4bf  call    cs:__imp_GetCurrentThreadId
0x18000b4c6  nop     dword ptr [rax+rax+00h]
0x18000b4cb  mov     r8, [rbx+110h]
0x18000b4d2  mov     dword ptr [rbp+0B0h+SRWLock], eax
0x18000b4d5  mov     eax, [r8+48h]
0x18000b4d9  mov     [rbp+0B0h+var_130], eax
0x18000b4dc  mov     [rbp+0B0h+var_120], r15
0x18000b4e0  test    rsi, rsi
0x18000b4e3  jz      short loc_18000B4FC
0x18000b4e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b4e9  inc     rdi
0x18000b4ec  cmp     [rsi+rdi*2], r15w
0x18000b4f1  jnz     short loc_18000B4E9
0x18000b4f3  lea     edi, ds:2[rdi*2]
0x18000b4fa  jmp     short loc_18000B503
0x18000b4fc  lea     rsi, qword_180012C50
0x18000b503  lea     rax, [rbp+0B0h+SRWLock]
0x18000b507  mov     [rbp+0B0h+var_50], rsi
0x18000b50b  mov     [rbp+0B0h+var_60], rax
0x18000b50f  lea     rdx, word_180015202
0x18000b516  lea     rax, [rbp+0B0h+var_130]
0x18000b51a  mov     [rbp+0B0h+var_48], edi
0x18000b51d  mov     [rbp+0B0h+var_70], rax
0x18000b521  add     r8, 8
0x18000b525  lea     rax, [rbp+0B0h+var_120]
0x18000b529  mov     [rbp+0B0h+var_44], r15d
0x18000b52d  mov     [rbp+0B0h+var_80], rax
0x18000b531  xor     r9d, r9d
0x18000b534  lea     rax, [rbp+0B0h+var_A0]
0x18000b538  mov     [rbp+0B0h+var_58], 4
0x18000b540  mov     [rsp+1F0h+var_1C8], rax
0x18000b545  mov     rcx, r14
0x18000b548  mov     dword ptr [rsp+1F0h+var_1D0], 6
0x18000b550  mov     [rbp+0B0h+var_68], 4
0x18000b558  mov     [rbp+0B0h+var_78], 8
0x18000b560  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b565  mov     rcx, rbx
0x18000b568  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b56d  mov     rcx, [rbp+0B0h+var_40]
0x18000b571  xor     rcx, rsp; StackCookie
0x18000b574  call    __security_check_cookie
0x18000b579  add     rsp, 1C8h
0x18000b580  pop     r15
0x18000b582  pop     r14
0x18000b584  pop     rdi
0x18000b585  pop     rsi
0x18000b586  pop     rbx
0x18000b587  pop     rbp
0x18000b588  retn
```
