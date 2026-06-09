# LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity::Stop(ushort const *)

- ea: `0x180046750`
- end: `0x180046a81`
- name: `?Stop@InstallSystemLanguagePackActivity@LanguageOverlayTraceProvider@@QEAAXPEBG@Z`
- size: `817`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180045570`

## callees

- `0x18000163c`
- `0x180002930`
- `0x180003a00`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180046750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800467c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800467c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046969`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800469ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800469ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity::Stop(
        LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rsi
  int v5; // eax
  int *v6; // rsi
  __int64 v7; // r9
  int v8; // edi
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rdi
  int v12; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v14; // [rsp+C0h] [rbp-70h] BYREF
  int v15; // [rsp+C8h] [rbp-68h] BYREF
  int v16; // [rsp+CCh] [rbp-64h] BYREF
  int v17; // [rsp+D0h] [rbp-60h] BYREF
  int v18; // [rsp+D4h] [rbp-5Ch] BYREF
  const int *v19; // [rsp+D8h] [rbp-58h] BYREF
  const int *v20; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-48h] BYREF
  const int *v22; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-30h] BYREF
  const int *v25; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v27; // [rsp+118h] [rbp-18h] BYREF
  __int64 v28; // [rsp+120h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v30; // [rsp+150h] [rbp+20h]
  __int64 v31; // [rsp+158h] [rbp+28h]
  int *v32; // [rsp+160h] [rbp+30h]
  __int64 v33; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v35; // [rsp+178h] [rbp+48h]
  const unsigned __int16 *v36; // [rsp+180h] [rbp+50h]
  int v37; // [rsp+188h] [rbp+58h]
  int v38; // [rsp+18Ch] [rbp+5Ch]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v19 = (const int *)a2;
      v20 = (const int *)*((_QWORD *)v6 + 15);
      v21 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v15 = v6[26];
      v22 = (const int *)*((_QWORD *)v6 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v16 = v6[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v17 = v6[8];
      v25 = (const int *)*((_QWORD *)v6 + 3);
      v18 = *v6;
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v12 = v6[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v28 = 0x1000000;
      v14 = (PSRWLOCK)50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_180078E91,
        *((_QWORD *)this + 34) + 8LL,
        v7,
        (__int64)&v14,
        (__int64)&v28,
        (__int64)&SRWLock,
        &v27,
        (__int64)&v12,
        &v26,
        (__int64)&v18,
        &v25,
        (__int64)&v17,
        &v24,
        (__int64)&v16,
        &v23,
        &v22,
        (__int64)&v15,
        &v21,
        &v20,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v14);
    v8 = 2;
    **((_DWORD **)this + 34) = 2;
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    v9 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v12 = *(_DWORD *)(v10 + 72);
      v14 = (PSRWLOCK)50331648;
      if ( a2 )
      {
        v11 = -1;
        do
          ++v11;
        while ( a2[v11] );
        v8 = 2 * v11 + 2;
      }
      else
      {
        a2 = (const unsigned __int16 *)&qword_180070100;
      }
      v36 = a2;
      v37 = v8;
      v38 = 0;
      p_SRWLock = &SRWLock;
      v35 = 4;
      v32 = &v12;
      v33 = 4;
      v30 = &v14;
      v31 = 8;
      tlgWriteTransfer_EventWriteTransfer(v9, (unsigned __int8 *)byte_180078CE1, (const GUID *)(v10 + 8), 0, 6u, &v29);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180046750  push    rbp
0x180046752  push    rbx
0x180046753  push    rsi
0x180046754  push    rdi
0x180046755  push    r14
0x180046757  push    r15
0x180046759  lea     rbp, [rsp-78h]
0x18004675e  sub     rsp, 1A8h
0x180046765  mov     rax, cs:__security_cookie
0x18004676c  xor     rax, rsp
0x18004676f  mov     [rbp+0A0h+var_40], rax
0x180046773  mov     r14, rdx
0x180046776  mov     rbx, rcx
0x180046779  mov     rsi, [rcx+110h]
0x180046780  mov     eax, [rsi+48h]
0x180046783  xor     r15d, r15d
0x180046786  test    eax, eax
0x180046788  jns     loc_180046949
0x18004678e  add     rsi, 50h ; 'P'
0x180046792  cmp     eax, [rsi+8]
0x180046795  jnz     loc_180046949
0x18004679b  test    rsi, rsi
0x18004679e  jz      loc_180046949
0x1800467a4  lea     rdx, [rbp+0A0h+SRWLock]
0x1800467a8  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800467ad  mov     rax, [rbx+110h]
0x1800467b4  mov     dword ptr [rax], 2
0x1800467ba  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x1800467be  test    rcx, rcx
0x1800467c1  jz      short loc_1800467C9
0x1800467c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800467c9  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800467ce  mov     r9, [rax+8]
0x1800467d2  mov     eax, [r9]
0x1800467d5  cmp     eax, 5
0x1800467d8  jbe     loc_180046A52
0x1800467de  mov     rdx, [r9+18h]
0x1800467e2  mov     rax, [r9+10h]
0x1800467e6  mov     rcx, 400000000000h
0x1800467f0  test    rcx, rax
0x1800467f3  jz      loc_180046A52
0x1800467f9  mov     rax, rdx
0x1800467fc  and     rax, rcx
0x1800467ff  cmp     rax, rdx
0x180046802  jnz     loc_180046A52
0x180046808  mov     [rbp+0A0h+var_F8], r14
0x18004680c  mov     rax, [rsi+78h]
0x180046810  mov     [rbp+0A0h+var_F0], rax
0x180046814  mov     rax, [rsi+70h]
0x180046818  mov     [rbp+0A0h+var_E8], rax
0x18004681c  mov     eax, [rsi+68h]
0x18004681f  mov     [rbp+0A0h+var_108], eax
0x180046822  mov     rax, [rsi+60h]
0x180046826  mov     [rbp+0A0h+var_E0], rax
0x18004682a  mov     rax, [rsi+58h]
0x18004682e  mov     [rbp+0A0h+var_D8], rax
0x180046832  mov     eax, [rsi+50h]
0x180046835  mov     [rbp+0A0h+var_104], eax
0x180046838  mov     rax, [rsi+48h]
0x18004683c  mov     [rbp+0A0h+var_D0], rax
0x180046840  mov     eax, [rsi+20h]
0x180046843  mov     [rbp+0A0h+var_100], eax
0x180046846  mov     rax, [rsi+18h]
0x18004684a  mov     [rbp+0A0h+var_C8], rax
0x18004684e  mov     eax, [rsi]
0x180046850  mov     [rbp+0A0h+var_FC], eax
0x180046853  mov     rax, [rsi+80h]
0x18004685a  mov     [rbp+0A0h+var_C0], rax
0x18004685e  mov     eax, [rsi+40h]
0x180046861  mov     [rbp+0A0h+var_120], eax
0x180046864  mov     rax, [rsi+38h]
0x180046868  mov     [rbp+0A0h+var_B8], rax
0x18004686c  mov     eax, [rsi+8]
0x18004686f  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x180046872  mov     [rbp+0A0h+var_B0], 1000000h
0x18004687a  mov     [rbp+0A0h+var_110], 3000000h
0x180046882  mov     r8, [rbx+110h]
0x180046889  add     r8, 8
0x18004688d  lea     rax, [rbp+0A0h+var_F8]
0x180046891  mov     [rsp+1D0h+var_130], rax
0x180046899  lea     rax, [rbp+0A0h+var_F0]
0x18004689d  mov     [rsp+1D0h+var_138], rax
0x1800468a5  lea     rax, [rbp+0A0h+var_E8]
0x1800468a9  mov     [rsp+1D0h+var_140], rax
0x1800468b1  lea     rax, [rbp+0A0h+var_108]
0x1800468b5  mov     [rsp+1D0h+var_148], rax
0x1800468bd  lea     rax, [rbp+0A0h+var_E0]
0x1800468c1  mov     [rsp+1D0h+var_150], rax
0x1800468c9  lea     rax, [rbp+0A0h+var_D8]
0x1800468cd  mov     [rsp+1D0h+var_158], rax
0x1800468d2  lea     rax, [rbp+0A0h+var_104]
0x1800468d6  mov     [rsp+1D0h+var_160], rax
0x1800468db  lea     rax, [rbp+0A0h+var_D0]
0x1800468df  mov     [rsp+1D0h+var_168], rax
0x1800468e4  lea     rax, [rbp+0A0h+var_100]
0x1800468e8  mov     [rsp+1D0h+var_170], rax
0x1800468ed  lea     rax, [rbp+0A0h+var_C8]
0x1800468f1  mov     [rsp+1D0h+var_178], rax
0x1800468f6  lea     rax, [rbp+0A0h+var_FC]
0x1800468fa  mov     [rsp+1D0h+var_180], rax
0x1800468ff  lea     rax, [rbp+0A0h+var_C0]
0x180046903  mov     [rsp+1D0h+var_188], rax
0x180046908  lea     rax, [rbp+0A0h+var_120]
0x18004690c  mov     [rsp+1D0h+var_190], rax
0x180046911  lea     rax, [rbp+0A0h+var_B8]
0x180046915  mov     [rsp+1D0h+var_198], rax
0x18004691a  lea     rax, [rbp+0A0h+SRWLock]
0x18004691e  mov     [rsp+1D0h+var_1A0], rax
0x180046923  lea     rax, [rbp+0A0h+var_B0]
0x180046927  mov     [rsp+1D0h+var_1A8], rax
0x18004692c  lea     rax, [rbp+0A0h+var_110]
0x180046930  mov     [rsp+1D0h+var_1B0], rax
0x180046935  lea     rdx, byte_180078E91
0x18004693c  mov     rcx, r9
0x18004693f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180046944  jmp     loc_180046A52
0x180046949  lea     rdx, [rbp+0A0h+var_110]
0x18004694d  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046952  mov     rax, [rbx+110h]
0x180046959  mov     edi, 2
0x18004695e  mov     [rax], edi
0x180046960  mov     rcx, [rbp+0A0h+var_110]; SRWLock
0x180046964  test    rcx, rcx
0x180046967  jz      short loc_18004696F
0x180046969  call    cs:__imp_ReleaseSRWLockExclusive
0x18004696f  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180046974  mov     rsi, [rax+8]
0x180046978  mov     eax, [rsi]
0x18004697a  cmp     eax, 5
0x18004697d  jbe     loc_180046A52
0x180046983  mov     rdx, [rsi+18h]
0x180046987  mov     rax, [rsi+10h]
0x18004698b  mov     rcx, 400000000000h
0x180046995  test    rcx, rax
0x180046998  jz      loc_180046A52
0x18004699e  mov     rax, rdx
0x1800469a1  and     rax, rcx
0x1800469a4  cmp     rax, rdx
0x1800469a7  jnz     loc_180046A52
0x1800469ad  call    cs:__imp_GetCurrentThreadId
0x1800469b3  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x1800469b6  mov     r8, [rbx+110h]
0x1800469bd  mov     eax, [r8+48h]
0x1800469c1  mov     [rbp+0A0h+var_120], eax
0x1800469c4  mov     [rbp+0A0h+var_110], 3000000h
0x1800469cc  test    r14, r14
0x1800469cf  jz      short loc_1800469E8
0x1800469d1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800469d5  inc     rdi
0x1800469d8  cmp     [r14+rdi*2], r15w
0x1800469dd  jnz     short loc_1800469D5
0x1800469df  lea     edi, ds:2[rdi*2]
0x1800469e6  jmp     short loc_1800469EF
0x1800469e8  lea     r14, qword_180070100
0x1800469ef  mov     [rbp+0A0h+var_50], r14
0x1800469f3  mov     [rbp+0A0h+var_48], edi
0x1800469f6  mov     [rbp+0A0h+var_44], r15d
0x1800469fa  lea     rax, [rbp+0A0h+SRWLock]
0x1800469fe  mov     [rbp+0A0h+var_60], rax
0x180046a02  mov     [rbp+0A0h+var_58], 4
0x180046a0a  lea     rax, [rbp+0A0h+var_120]
0x180046a0e  mov     [rbp+0A0h+var_70], rax
0x180046a12  mov     [rbp+0A0h+var_68], 4
0x180046a1a  lea     rax, [rbp+0A0h+var_110]
0x180046a1e  mov     [rbp+0A0h+var_80], rax
0x180046a22  mov     [rbp+0A0h+var_78], 8
0x180046a2a  add     r8, 8
0x180046a2e  lea     rax, [rbp+0A0h+var_A0]
0x180046a32  mov     [rsp+1D0h+var_1A8], rax
0x180046a37  mov     dword ptr [rsp+1D0h+var_1B0], 6
0x180046a3f  xor     r9d, r9d
0x180046a42  lea     rdx, byte_180078CE1
0x180046a49  mov     rcx, rsi
0x180046a4c  call    _tlgWriteTransfer_EventWriteTransfer
0x180046a51  nop
0x180046a52  lea     rcx, [rbx+120h]; this
0x180046a59  cmp     [rcx+18h], r15d
0x180046a5d  jz      short loc_180046A65
0x180046a5f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046a64  nop
0x180046a65  mov     rcx, [rbp+0A0h+var_40]
0x180046a69  xor     rcx, rsp; StackCookie
0x180046a6c  call    __security_check_cookie
0x180046a71  add     rsp, 1A8h
0x180046a78  pop     r15
0x180046a7a  pop     r14
0x180046a7c  pop     rdi
0x180046a7d  pop     rsi
0x180046a7e  pop     rbx
0x180046a7f  pop     rbp
0x180046a80  retn
```
