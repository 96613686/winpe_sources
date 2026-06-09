# Windows::Telemetry::Worker::RefreshSettings::Stop(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003ea9c`
- end: `0x18003eef6`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@00@Z`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003ef00`

## callees

- `0x180001f60`
- `0x180002648`
- `0x18001a1bc`
- `0x18003e044`
- `0x18003ea9c`
- `0x1800434ec`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003eb36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ed30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003eb36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ed30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed84`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(__int64 a1, __int64 *a2, __int64 *a3, __int64 *a4)
{
  _DWORD **v4; // rsi
  __int64 v5; // r14
  int v10; // eax
  int *v11; // r14
  _DWORD **v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  _DWORD *v15; // r8
  _DWORD *v16; // rax
  int v17; // ebx
  RTL_SRWLOCK *v18; // rcx
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // r13
  const wchar_t *v21; // r14
  const wchar_t *v22; // r15
  const wchar_t *v23; // r12
  DWORD CurrentThreadId; // eax
  _DWORD *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // ecx
  __int64 v29; // rcx
  int v30; // ecx
  __int64 v31; // [rsp+D8h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v33; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v34; // [rsp+F0h] [rbp-68h] BYREF
  int v35; // [rsp+F8h] [rbp-60h] BYREF
  int v36; // [rsp+FCh] [rbp-5Ch] BYREF
  int v37; // [rsp+100h] [rbp-58h] BYREF
  int v38; // [rsp+104h] [rbp-54h] BYREF
  __int64 v39; // [rsp+108h] [rbp-50h] BYREF
  __int64 v40; // [rsp+110h] [rbp-48h] BYREF
  __int64 v41; // [rsp+118h] [rbp-40h] BYREF
  __int64 v42; // [rsp+120h] [rbp-38h] BYREF
  __int64 v43; // [rsp+128h] [rbp-30h] BYREF
  __int64 v44; // [rsp+130h] [rbp-28h] BYREF
  __int64 v45; // [rsp+138h] [rbp-20h] BYREF
  __int64 v46; // [rsp+140h] [rbp-18h] BYREF
  __int64 v47; // [rsp+148h] [rbp-10h] BYREF
  __int64 v48; // [rsp+150h] [rbp-8h] BYREF
  __int64 v49; // [rsp+158h] [rbp+0h] BYREF
  __int64 v50; // [rsp+160h] [rbp+8h] BYREF
  __int64 v51; // [rsp+168h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+178h] [rbp+20h] BYREF
  __int64 *v53; // [rsp+198h] [rbp+40h]
  __int64 v54; // [rsp+1A0h] [rbp+48h]
  __int64 *v55; // [rsp+1A8h] [rbp+50h]
  __int64 v56; // [rsp+1B0h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+1B8h] [rbp+60h]
  __int64 v58; // [rsp+1C0h] [rbp+68h]
  const wchar_t *v59; // [rsp+1C8h] [rbp+70h]
  int v60; // [rsp+1D0h] [rbp+78h]
  int v61; // [rsp+1D4h] [rbp+7Ch]
  __int64 *v62; // [rsp+1D8h] [rbp+80h]
  __int64 v63; // [rsp+1E0h] [rbp+88h]
  const wchar_t *v64; // [rsp+1E8h] [rbp+90h]
  int v65; // [rsp+1F0h] [rbp+98h]
  int v66; // [rsp+1F4h] [rbp+9Ch]
  const wchar_t *v67; // [rsp+1F8h] [rbp+A0h]
  int v68; // [rsp+200h] [rbp+A8h]
  int v69; // [rsp+204h] [rbp+ACh]
  const char *v70; // [rsp+208h] [rbp+B0h]
  __int64 v71; // [rsp+210h] [rbp+B8h]

  v4 = (_DWORD **)(a1 + 272);
  v34 = (__int64)a2;
  v5 = *(_QWORD *)(a1 + 272);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = (int *)(v5 + 80), v10 == v11[2]) )
  {
    v12 = (_DWORD **)(a1 + 272);
    if ( v11 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v13 = SRWLock;
      **v4 = 2;
      if ( v13 )
        ReleaseSRWLockExclusive(v13);
      v14 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v14 > 5u
        && (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v14 + 3) & 0x400000000000LL) == *((_QWORD *)v14 + 3) )
      {
        v15 = *v4;
        v39 = (__int64)"1507.2603.28012.0";
        v40 = *a4;
        v41 = *a3;
        LOBYTE(v31) = *(_BYTE *)(a1 + 328);
        v42 = *a2;
        v43 = *((_QWORD *)v11 + 15);
        v44 = *((_QWORD *)v11 + 14);
        v35 = v11[26];
        v45 = *((_QWORD *)v11 + 12);
        v46 = *((_QWORD *)v11 + 11);
        v36 = v11[20];
        v47 = *((_QWORD *)v11 + 9);
        v37 = v11[8];
        v48 = *((_QWORD *)v11 + 3);
        v38 = *v11;
        v49 = *((_QWORD *)v11 + 16);
        LODWORD(v33) = v11[16];
        v50 = *((_QWORD *)v11 + 7);
        LODWORD(SRWLock) = v11[2];
        v51 = 0x1000000;
        v34 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          (int)v14,
          (int)&dword_18009151C,
          (_DWORD)v15 + 8,
          (__int64)&v34,
          (__int64)&v51,
          (__int64)&SRWLock,
          (__int64)&v50,
          (__int64)&v33,
          (__int64)&v49,
          (__int64)&v38,
          (__int64)&v48,
          (__int64)&v37,
          (__int64)&v47,
          (__int64)&v36,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v35,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v31,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v39);
      }
      goto LABEL_31;
    }
  }
  else
  {
    v12 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v16 = *v12;
  v17 = 2;
  v18 = SRWLock;
  *v16 = 2;
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  v19 = Windows::Telemetry::Base::Provider();
  v20 = (__int64)v19;
  if ( *(_DWORD *)v19 > 5u
    && (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v19 + 3) & 0x400000000000LL) == *((_QWORD *)v19 + 3) )
  {
    v21 = (const wchar_t *)*a3;
    v22 = (const wchar_t *)*a4;
    LOBYTE(v31) = *(_BYTE *)(a1 + 328);
    v23 = *(const wchar_t **)v34;
    CurrentThreadId = GetCurrentThreadId();
    v25 = *v4;
    LODWORD(SRWLock) = CurrentThreadId;
    v71 = 18;
    LODWORD(v33) = v25[18];
    v34 = 0x1000000;
    v70 = "1507.2603.28012.0";
    v26 = -1;
    if ( v22 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v22[v27] );
      v28 = 2 * v27 + 2;
    }
    else
    {
      v22 = &S2;
      v28 = 2;
    }
    v67 = v22;
    v68 = v28;
    v69 = 0;
    if ( v21 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v21[v29] );
      v30 = 2 * v29 + 2;
    }
    else
    {
      v21 = &S2;
      v30 = 2;
    }
    v65 = v30;
    v62 = &v31;
    v64 = v21;
    v66 = 0;
    v63 = 1;
    if ( v23 )
    {
      do
        ++v26;
      while ( v23[v26] );
      v17 = 2 * v26 + 2;
    }
    else
    {
      v23 = &S2;
    }
    v61 = 0;
    p_SRWLock = &SRWLock;
    v59 = v23;
    v55 = &v33;
    v60 = v17;
    v53 = &v34;
    v58 = 4;
    v56 = 4;
    v54 = 8;
    tlgWriteTransfer_EventWriteTransfer(v20, (unsigned __int8 *)&byte_180091487, (const GUID *)(v25 + 2), 0, 0xAu, &v52);
  }
LABEL_31:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18003ea9c  mov     rax, rsp
0x18003ea9f  mov     [rax+10h], rbx
0x18003eaa3  mov     [rax+18h], rsi
0x18003eaa7  mov     [rax+20h], rdi
0x18003eaab  push    rbp
0x18003eaac  push    r12
0x18003eaae  push    r13
0x18003eab0  push    r14
0x18003eab2  push    r15
0x18003eab4  lea     rbp, [rax-0F8h]
0x18003eabb  sub     rsp, 220h
0x18003eac2  mov     rax, cs:__security_cookie
0x18003eac9  xor     rax, rsp
0x18003eacc  mov     [rbp+0F0h+var_30], rax
0x18003ead3  lea     rsi, [rcx+110h]
0x18003eada  mov     [rbp+0F0h+var_158], rdx
0x18003eade  mov     r14, [rsi]
0x18003eae1  mov     r15, r9
0x18003eae4  mov     r12, r8
0x18003eae7  mov     r13, rdx
0x18003eaea  mov     rdi, rcx
0x18003eaed  mov     eax, [r14+48h]
0x18003eaf1  test    eax, eax
0x18003eaf3  jns     loc_18003ED09
0x18003eaf9  add     r14, 50h ; 'P'
0x18003eafd  cmp     eax, [r14+8]
0x18003eb01  jnz     loc_18003ED09
0x18003eb07  mov     rbx, rsi
0x18003eb0a  test    r14, r14
0x18003eb0d  jz      loc_18003ED0C
0x18003eb13  lea     rdx, [rbp+0F0h+SRWLock]
0x18003eb17  mov     [rbp+0F0h+SRWLock], 0
0x18003eb1f  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003eb24  mov     rax, [rsi]
0x18003eb27  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x18003eb2b  mov     dword ptr [rax], 2
0x18003eb31  test    rcx, rcx
0x18003eb34  jz      short loc_18003EB3C
0x18003eb36  call    cs:__imp_ReleaseSRWLockExclusive
0x18003eb3c  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003eb41  mov     r9, rax
0x18003eb44  cmp     dword ptr [rax], 5
0x18003eb47  jbe     loc_18003EEBE
0x18003eb4d  mov     rdx, 400000000000h
0x18003eb57  test    [rax+10h], rdx
0x18003eb5b  jz      loc_18003EEBE
0x18003eb61  mov     rcx, [rax+18h]
0x18003eb65  and     rcx, rdx
0x18003eb68  cmp     rcx, [rax+18h]
0x18003eb6c  jnz     loc_18003EEBE
0x18003eb72  mov     r8, [rsi]
0x18003eb75  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18003eb7c  mov     [rbp+0F0h+var_140], rax
0x18003eb80  add     r8, 8; int
0x18003eb84  mov     rax, [r15]
0x18003eb87  mov     [rbp+0F0h+var_138], rax
0x18003eb8b  mov     rax, [r12]
0x18003eb8f  mov     [rbp+0F0h+var_130], rax
0x18003eb93  mov     al, [rdi+148h]
0x18003eb99  mov     byte ptr [rbp+0F0h+var_170], al
0x18003eb9c  mov     rax, [r13+0]
0x18003eba0  mov     [rbp+0F0h+var_128], rax
0x18003eba4  mov     rax, [r14+78h]
0x18003eba8  mov     [rbp+0F0h+var_120], rax
0x18003ebac  mov     rax, [r14+70h]
0x18003ebb0  mov     [rbp+0F0h+var_118], rax
0x18003ebb4  mov     eax, [r14+68h]
0x18003ebb8  mov     dword ptr [rbp+0F0h+var_150], eax
0x18003ebbb  mov     rax, [r14+60h]
0x18003ebbf  mov     [rbp+0F0h+var_110], rax
0x18003ebc3  mov     rax, [r14+58h]
0x18003ebc7  mov     [rbp+0F0h+var_108], rax
0x18003ebcb  mov     eax, [r14+50h]
0x18003ebcf  mov     dword ptr [rbp+0F0h+var_150+4], eax
0x18003ebd2  mov     rax, [r14+48h]
0x18003ebd6  mov     [rbp+0F0h+var_100], rax
0x18003ebda  mov     eax, [r14+20h]
0x18003ebde  mov     dword ptr [rbp+0F0h+var_148], eax
0x18003ebe1  mov     rax, [r14+18h]
0x18003ebe5  mov     [rbp+0F0h+var_F8], rax
0x18003ebe9  mov     eax, [r14]
0x18003ebec  mov     dword ptr [rbp+0F0h+var_148+4], eax
0x18003ebef  mov     rax, [r14+80h]
0x18003ebf6  mov     [rbp+0F0h+var_F0], rax
0x18003ebfa  mov     eax, [r14+40h]
0x18003ebfe  mov     dword ptr [rbp+0F0h+var_160], eax
0x18003ec01  mov     rax, [r14+38h]
0x18003ec05  mov     [rbp+0F0h+var_E8], rax
0x18003ec09  mov     eax, [r14+8]
0x18003ec0d  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x18003ec10  mov     eax, 1000000h
0x18003ec15  mov     [rbp+0F0h+var_E0], rax
0x18003ec19  mov     [rbp+0F0h+var_158], rax
0x18003ec1d  lea     rax, [rbp+0F0h+var_140]
0x18003ec21  mov     [rsp+240h+var_180], rax; __int64
0x18003ec29  lea     rax, [rbp+0F0h+var_138]
0x18003ec2d  mov     [rsp+240h+var_188], rax; __int64
0x18003ec35  lea     rax, [rbp+0F0h+var_130]
0x18003ec39  mov     [rsp+240h+var_190], rax; __int64
0x18003ec41  lea     rax, [rbp+0F0h+var_170]
0x18003ec45  mov     [rsp+240h+var_198], rax; __int64
0x18003ec4d  lea     rax, [rbp+0F0h+var_128]
0x18003ec51  mov     [rsp+240h+var_1A0], rax; __int64
0x18003ec59  lea     rax, [rbp+0F0h+var_120]
0x18003ec5d  mov     [rsp+240h+var_1A8], rax; __int64
0x18003ec65  lea     rax, [rbp+0F0h+var_118]
0x18003ec69  mov     [rsp+240h+var_1B0], rax; __int64
0x18003ec71  lea     rax, [rbp+0F0h+var_150]
0x18003ec75  mov     [rsp+240h+var_1B8], rax; __int64
0x18003ec7d  lea     rax, [rbp+0F0h+var_110]
0x18003ec81  mov     [rsp+240h+var_1C0], rax; __int64
0x18003ec89  lea     rax, [rbp+0F0h+var_108]
0x18003ec8d  mov     [rsp+240h+var_1C8], rax; __int64
0x18003ec92  lea     rax, [rbp+0F0h+var_150+4]
0x18003ec96  mov     [rsp+240h+var_1D0], rax; __int64
0x18003ec9b  lea     rax, [rbp+0F0h+var_100]
0x18003ec9f  mov     [rsp+240h+var_1D8], rax; __int64
0x18003eca4  lea     rax, [rbp+0F0h+var_148]
0x18003eca8  mov     [rsp+240h+var_1E0], rax; __int64
0x18003ecad  lea     rax, [rbp+0F0h+var_F8]
0x18003ecb1  mov     [rsp+240h+var_1E8], rax; __int64
0x18003ecb6  lea     rax, [rbp+0F0h+var_148+4]
0x18003ecba  mov     [rsp+240h+var_1F0], rax; __int64
0x18003ecbf  lea     rax, [rbp+0F0h+var_F0]
0x18003ecc3  mov     [rsp+240h+var_1F8], rax; __int64
0x18003ecc8  lea     rax, [rbp+0F0h+var_160]
0x18003eccc  mov     [rsp+240h+var_200], rax; __int64
0x18003ecd1  lea     rax, [rbp+0F0h+var_E8]
0x18003ecd5  mov     [rsp+240h+var_208], rax; __int64
0x18003ecda  lea     rax, [rbp+0F0h+SRWLock]
0x18003ecde  mov     [rsp+240h+var_210], rax; __int64
0x18003ece3  lea     rax, [rbp+0F0h+var_E0]
0x18003ece7  mov     rcx, r9; int
0x18003ecea  mov     [rsp+240h+var_218], rax; __int64
0x18003ecef  lea     rdx, dword_18009151C; int
0x18003ecf6  lea     rax, [rbp+0F0h+var_158]
0x18003ecfa  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x18003ecff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U4@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@665@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x18003ed04  jmp     loc_18003EEBE
0x18003ed09  mov     rbx, rsi
0x18003ed0c  lea     rdx, [rbp+0F0h+SRWLock]
0x18003ed10  mov     [rbp+0F0h+SRWLock], 0
0x18003ed18  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ed1d  mov     rax, [rbx]
0x18003ed20  mov     ebx, 2
0x18003ed25  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x18003ed29  mov     [rax], ebx
0x18003ed2b  test    rcx, rcx
0x18003ed2e  jz      short loc_18003ED36
0x18003ed30  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ed36  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003ed3b  mov     r13, rax
0x18003ed3e  cmp     dword ptr [rax], 5
0x18003ed41  jbe     loc_18003EEBE
0x18003ed47  mov     rdx, 400000000000h
0x18003ed51  test    [rax+10h], rdx
0x18003ed55  jz      loc_18003EEBE
0x18003ed5b  mov     rcx, [rax+18h]
0x18003ed5f  and     rcx, rdx
0x18003ed62  cmp     rcx, [rax+18h]
0x18003ed66  jnz     loc_18003EEBE
0x18003ed6c  mov     r14, [r12]
0x18003ed70  mov     r12, [rbp+0F0h+var_158]
0x18003ed74  mov     al, [rdi+148h]
0x18003ed7a  mov     r15, [r15]
0x18003ed7d  mov     byte ptr [rbp+0F0h+var_170], al
0x18003ed80  mov     r12, [r12]
0x18003ed84  call    cs:__imp_GetCurrentThreadId
0x18003ed8a  mov     r8, [rsi]
0x18003ed8d  lea     r9, S2
0x18003ed94  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x18003ed97  xor     edx, edx
0x18003ed99  mov     [rbp+0F0h+var_38], 12h
0x18003eda4  mov     eax, [r8+48h]
0x18003eda8  mov     dword ptr [rbp+0F0h+var_160], eax
0x18003edab  mov     eax, 1000000h
0x18003edb0  mov     [rbp+0F0h+var_158], rax
0x18003edb4  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18003edbb  mov     [rbp+0F0h+var_40], rax
0x18003edc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003edc6  test    r15, r15
0x18003edc9  jz      short loc_18003EDE1
0x18003edcb  mov     rcx, rax
0x18003edce  inc     rcx
0x18003edd1  cmp     [r15+rcx*2], dx
0x18003edd6  jnz     short loc_18003EDCE
0x18003edd8  lea     ecx, ds:2[rcx*2]
0x18003eddf  jmp     short loc_18003EDE6
0x18003ede1  mov     r15, r9
0x18003ede4  mov     ecx, ebx
0x18003ede6  mov     [rbp+0F0h+var_50], r15
0x18003eded  mov     [rbp+0F0h+var_48], ecx
0x18003edf3  mov     [rbp+0F0h+var_44], edx
0x18003edf9  test    r14, r14
0x18003edfc  jz      short loc_18003EE14
0x18003edfe  mov     rcx, rax
0x18003ee01  inc     rcx
0x18003ee04  cmp     [r14+rcx*2], dx
0x18003ee09  jnz     short loc_18003EE01
0x18003ee0b  lea     ecx, ds:2[rcx*2]
0x18003ee12  jmp     short loc_18003EE19
0x18003ee14  mov     r14, r9
0x18003ee17  mov     ecx, ebx
0x18003ee19  mov     [rbp+0F0h+var_58], ecx
0x18003ee1f  lea     rcx, [rbp+0F0h+var_170]
0x18003ee23  mov     [rbp+0F0h+var_70], rcx
0x18003ee2a  mov     [rbp+0F0h+var_60], r14
0x18003ee31  mov     [rbp+0F0h+var_54], edx
0x18003ee37  mov     [rbp+0F0h+var_68], 1
0x18003ee42  test    r12, r12
0x18003ee45  jz      short loc_18003EE5A
0x18003ee47  inc     rax
0x18003ee4a  cmp     [r12+rax*2], dx
0x18003ee4f  jnz     short loc_18003EE47
0x18003ee51  lea     ebx, ds:2[rax*2]
0x18003ee58  jmp     short loc_18003EE5D
0x18003ee5a  mov     r12, r9
0x18003ee5d  lea     rax, [rbp+0F0h+SRWLock]
0x18003ee61  mov     [rbp+0F0h+var_74], edx
0x18003ee64  mov     [rbp+0F0h+var_90], rax
0x18003ee68  lea     rdx, byte_180091487; int
0x18003ee6f  lea     rax, [rbp+0F0h+var_160]
0x18003ee73  mov     [rbp+0F0h+var_80], r12
0x18003ee77  mov     [rbp+0F0h+var_A0], rax
0x18003ee7b  add     r8, 8; int
0x18003ee7f  lea     rax, [rbp+0F0h+var_158]
0x18003ee83  mov     [rbp+0F0h+var_78], ebx
0x18003ee86  mov     [rbp+0F0h+var_B0], rax
0x18003ee8a  xor     r9d, r9d; int
0x18003ee8d  lea     rax, [rbp+0F0h+var_D0]
0x18003ee91  mov     [rbp+0F0h+var_88], 4
0x18003ee99  mov     [rsp+240h+var_218], rax; PEVENT_DATA_DESCRIPTOR
0x18003ee9e  mov     rcx, r13; int
0x18003eea1  mov     [rsp+240h+var_220], 0Ah; ULONG
0x18003eea9  mov     [rbp+0F0h+var_98], 4
0x18003eeb1  mov     [rbp+0F0h+var_A8], 8
0x18003eeb9  call    _tlgWriteTransfer_EventWriteTransfer
0x18003eebe  mov     rcx, rdi
0x18003eec1  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18003eec6  mov     rcx, [rbp+0F0h+var_30]
0x18003eecd  xor     rcx, rsp; StackCookie
0x18003eed0  call    __security_check_cookie
0x18003eed5  lea     r11, [rsp+240h+var_20]
0x18003eedd  mov     rbx, [r11+38h]
0x18003eee1  mov     rsi, [r11+40h]
0x18003eee5  mov     rdi, [r11+48h]
0x18003eee9  mov     rsp, r11
0x18003eeec  pop     r15
0x18003eeee  pop     r14
0x18003eef0  pop     r13
0x18003eef2  pop     r12
0x18003eef4  pop     rbp
0x18003eef5  retn
```
