# ClientTelemetry::Run::Stop(wil::basic_zstring_view<wchar_t>)

- ea: `0x18000aa8c`
- end: `0x18000aeff`
- name: `?Stop@Run@ClientTelemetry@@QEAAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800150a0`

## callees

- `0x180001008`
- `0x180001f60`
- `0x18000a2ac`
- `0x18000aa8c`
- `0x18001a1bc`
- `0x180035ec8`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae89`

## pseudocode

```c
struct ClientTelemetry *__fastcall ClientTelemetry::Run::Stop(__int64 a1, __int64 *a2)
{
  _DWORD **v2; // rsi
  __int64 v3; // r14
  int v6; // eax
  __int64 v7; // r14
  _DWORD **v8; // rbx
  RTL_SRWLOCK *v9; // rcx
  struct ClientTelemetry *result; // rax
  __int64 v11; // r9
  _DWORD *v12; // r8
  _DWORD *v13; // rax
  int v14; // ebx
  RTL_SRWLOCK *v15; // rcx
  __int64 v16; // r13
  const wchar_t *v17; // r14
  const wchar_t *v18; // r15
  const wchar_t *v19; // r12
  DWORD CurrentThreadId; // eax
  _DWORD *v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // ecx
  __int64 v25; // rcx
  int v26; // ecx
  struct ClientTelemetry *v27; // rbx
  void *v28; // rdx
  unsigned int v29; // r8d
  struct ClientTelemetry **v30; // rcx
  int v31; // [rsp+28h] [rbp-120h]
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-80h] BYREF
  int v33; // [rsp+D0h] [rbp-78h] BYREF
  int v34; // [rsp+D4h] [rbp-74h] BYREF
  int v35; // [rsp+D8h] [rbp-70h] BYREF
  int v36; // [rsp+DCh] [rbp-6Ch] BYREF
  __int64 v37; // [rsp+E0h] [rbp-68h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v39; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v40; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v41; // [rsp+100h] [rbp-48h] BYREF
  __int64 v42; // [rsp+108h] [rbp-40h] BYREF
  __int64 v43; // [rsp+110h] [rbp-38h] BYREF
  __int64 v44; // [rsp+118h] [rbp-30h] BYREF
  __int64 v45; // [rsp+120h] [rbp-28h] BYREF
  __int64 v46; // [rsp+128h] [rbp-20h] BYREF
  __int64 v47; // [rsp+130h] [rbp-18h] BYREF
  __int64 v48; // [rsp+138h] [rbp-10h] BYREF
  __int64 v49; // [rsp+140h] [rbp-8h] BYREF
  __int64 v50; // [rsp+148h] [rbp+0h] BYREF
  __int64 v51; // [rsp+150h] [rbp+8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+158h] [rbp+10h] BYREF
  __int64 *v53; // [rsp+178h] [rbp+30h]
  __int64 v54; // [rsp+180h] [rbp+38h]
  int *v55; // [rsp+188h] [rbp+40h]
  __int64 v56; // [rsp+190h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+198h] [rbp+50h]
  __int64 v58; // [rsp+1A0h] [rbp+58h]
  const wchar_t *v59; // [rsp+1A8h] [rbp+60h]
  int v60; // [rsp+1B0h] [rbp+68h]
  int v61; // [rsp+1B4h] [rbp+6Ch]
  const char *v62; // [rsp+1B8h] [rbp+70h]
  __int64 v63; // [rsp+1C0h] [rbp+78h]
  const wchar_t *v64; // [rsp+1C8h] [rbp+80h]
  int v65; // [rsp+1D0h] [rbp+88h]
  int v66; // [rsp+1D4h] [rbp+8Ch]
  const wchar_t *v67; // [rsp+1D8h] [rbp+90h]
  int v68; // [rsp+1E0h] [rbp+98h]
  int v69; // [rsp+1E4h] [rbp+9Ch]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+D8h]

  v2 = (_DWORD **)(a1 + 272);
  v3 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v3 + 72);
  if ( v6 < 0 && (v7 = v3 + 80, v6 == *(_DWORD *)(v7 + 8)) )
  {
    v8 = (_DWORD **)(a1 + 272);
    if ( v7 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v9 = SRWLock;
      **v2 = 2;
      if ( v9 )
        ReleaseSRWLockExclusive(v9);
      result = ClientTelemetry::Instance();
      v11 = *((_QWORD *)result + 1);
      if ( *(_DWORD *)v11 > 5u && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0 )
      {
        result = (struct ClientTelemetry *)(*(_QWORD *)(v11 + 24) & 0x400000000000LL);
        if ( result == *(struct ClientTelemetry **)(v11 + 24) )
        {
          v39 = *(_QWORD *)(a1 + 336);
          v40 = *(_QWORD *)(a1 + 328);
          v42 = *a2;
          v43 = *(_QWORD *)(v7 + 120);
          v44 = *(_QWORD *)(v7 + 112);
          v34 = *(_DWORD *)(v7 + 104);
          v45 = *(_QWORD *)(v7 + 96);
          v12 = *v2;
          v46 = *(_QWORD *)(v7 + 88);
          v35 = *(_DWORD *)(v7 + 80);
          v47 = *(_QWORD *)(v7 + 72);
          v36 = *(_DWORD *)(v7 + 32);
          v48 = *(_QWORD *)(v7 + 24);
          LODWORD(v37) = *(_DWORD *)v7;
          v49 = *(_QWORD *)(v7 + 128);
          v33 = *(_DWORD *)(v7 + 64);
          v50 = *(_QWORD *)(v7 + 56);
          LODWORD(SRWLock) = *(_DWORD *)(v7 + 8);
          v51 = 0x1000000;
          v38 = 0x1000000;
          v41 = (__int64)"1507.2603.28012.0";
          result = (struct ClientTelemetry *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
                                               v11,
                                               (int)&byte_180090A3F,
                                               (int)v12 + 8,
                                               (__int64)&v38,
                                               (__int64)&v51,
                                               (__int64)&SRWLock,
                                               (__int64)&v50,
                                               (__int64)&v33,
                                               (__int64)&v49,
                                               (__int64)&v37,
                                               (__int64)&v48,
                                               (__int64)&v36,
                                               (__int64)&v47,
                                               (__int64)&v35,
                                               (__int64)&v46,
                                               (__int64)&v45,
                                               (__int64)&v34,
                                               (__int64)&v44,
                                               (__int64)&v43,
                                               (__int64)&v42,
                                               (__int64)&v41,
                                               (__int64)&v40,
                                               (__int64)&v39);
        }
      }
      goto LABEL_31;
    }
  }
  else
  {
    v8 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v13 = *v8;
  v14 = 2;
  v15 = SRWLock;
  *v13 = 2;
  if ( v15 )
    ReleaseSRWLockExclusive(v15);
  result = ClientTelemetry::Instance();
  v16 = *((_QWORD *)result + 1);
  if ( *(_DWORD *)v16 > 5u && (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0 )
  {
    result = (struct ClientTelemetry *)(*(_QWORD *)(v16 + 24) & 0x400000000000LL);
    if ( result == *(struct ClientTelemetry **)(v16 + 24) )
    {
      v17 = *(const wchar_t **)(a1 + 336);
      v18 = *(const wchar_t **)(a1 + 328);
      v19 = (const wchar_t *)*a2;
      CurrentThreadId = GetCurrentThreadId();
      v21 = *v2;
      LODWORD(SRWLock) = CurrentThreadId;
      v33 = v21[18];
      v38 = 0x1000000;
      v22 = -1;
      if ( v17 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v17[v23] );
        v24 = 2 * v23 + 2;
      }
      else
      {
        v17 = &S2;
        v24 = 2;
      }
      v67 = v17;
      v68 = v24;
      v69 = 0;
      if ( v18 )
      {
        v25 = -1;
        do
          ++v25;
        while ( v18[v25] );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v18 = &S2;
        v26 = 2;
      }
      v64 = v18;
      v65 = v26;
      v66 = 0;
      v62 = "1507.2603.28012.0";
      v63 = 18;
      if ( v19 )
      {
        do
          ++v22;
        while ( v19[v22] );
        v14 = 2 * v22 + 2;
      }
      else
      {
        v19 = &S2;
      }
      v59 = v19;
      p_SRWLock = &SRWLock;
      v60 = v14;
      v55 = &v33;
      v61 = 0;
      v53 = &v38;
      v58 = 4;
      v56 = 4;
      v54 = 8;
      result = (struct ClientTelemetry *)tlgWriteTransfer_EventWriteTransfer(
                                           v16,
                                           (int)&byte_1800909D1,
                                           (int)v21 + 8,
                                           0,
                                           9u,
                                           &v52);
    }
  }
LABEL_31:
  if ( *(_DWORD *)(a1 + 312) )
  {
    v27 = (struct ClientTelemetry *)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v28, v29, (const char *)0x8007029CLL, v31);
    v30 = *(struct ClientTelemetry ***)v27;
    *(_DWORD *)(a1 + 312) = 0;
    while ( 1 )
    {
      result = *v30;
      if ( !*v30 )
        break;
      if ( result == v27 )
      {
        result = *(struct ClientTelemetry **)(a1 + 304);
        *v30 = result;
        break;
      }
      v30 = (struct ClientTelemetry **)((char *)result + 16);
      *(_QWORD *)v27 = (char *)result + 16;
    }
    *(_QWORD *)v27 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa8c  mov     rax, rsp
0x18000aa8f  mov     [rax+10h], rbx
0x18000aa93  mov     [rax+18h], rsi
0x18000aa97  mov     [rax+20h], rdi
0x18000aa9b  push    rbp
0x18000aa9c  push    r12
0x18000aa9e  push    r13
0x18000aaa0  push    r14
0x18000aaa2  push    r15
0x18000aaa4  lea     rbp, [rax-0D8h]
0x18000aaab  sub     rsp, 1F0h
0x18000aab2  mov     rax, cs:__security_cookie
0x18000aab9  xor     rax, rsp
0x18000aabc  mov     [rbp+0D0h+var_30], rax
0x18000aac3  lea     rsi, [rcx+110h]
0x18000aaca  xor     r15d, r15d
0x18000aacd  mov     r14, [rsi]
0x18000aad0  mov     r12, rdx
0x18000aad3  mov     rdi, rcx
0x18000aad6  mov     eax, [r14+48h]
0x18000aada  test    eax, eax
0x18000aadc  jns     loc_18000ACE2
0x18000aae2  add     r14, 50h ; 'P'
0x18000aae6  cmp     eax, [r14+8]
0x18000aaea  jnz     loc_18000ACE2
0x18000aaf0  mov     rbx, rsi
0x18000aaf3  test    r14, r14
0x18000aaf6  jz      loc_18000ACE5
0x18000aafc  lea     rdx, [rbp+0D0h+SRWLock]
0x18000ab00  mov     [rbp+0D0h+SRWLock], r15
0x18000ab04  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ab09  mov     rax, [rsi]
0x18000ab0c  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18000ab10  mov     dword ptr [rax], 2
0x18000ab16  test    rcx, rcx
0x18000ab19  jz      short loc_18000AB21
0x18000ab1b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab21  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000ab26  mov     r9, [rax+8]
0x18000ab2a  cmp     dword ptr [r9], 5
0x18000ab2e  jbe     loc_18000AE79
0x18000ab34  mov     rcx, 400000000000h
0x18000ab3e  test    [r9+10h], rcx
0x18000ab42  jz      loc_18000AE79
0x18000ab48  mov     rax, [r9+18h]
0x18000ab4c  and     rax, rcx
0x18000ab4f  cmp     rax, [r9+18h]
0x18000ab53  jnz     loc_18000AE79
0x18000ab59  mov     rax, [rdi+150h]
0x18000ab60  lea     rcx, a15072603280120; "1507.2603.28012.0"
0x18000ab67  mov     [rbp+0D0h+var_128], rax
0x18000ab6b  mov     rax, [rdi+148h]
0x18000ab72  mov     [rbp+0D0h+var_120], rax
0x18000ab76  mov     rax, [r12]
0x18000ab7a  mov     [rbp+0D0h+var_110], rax
0x18000ab7e  mov     rax, [r14+78h]
0x18000ab82  mov     [rbp+0D0h+var_108], rax
0x18000ab86  mov     rax, [r14+70h]
0x18000ab8a  mov     [rbp+0D0h+var_100], rax
0x18000ab8e  mov     eax, [r14+68h]
0x18000ab92  mov     dword ptr [rbp+0D0h+var_148+4], eax
0x18000ab95  mov     rax, [r14+60h]
0x18000ab99  mov     [rbp+0D0h+var_F8], rax
0x18000ab9d  mov     rax, [r14+58h]
0x18000aba1  mov     r8, [rsi]
0x18000aba4  mov     [rbp+0D0h+var_F0], rax
0x18000aba8  add     r8, 8; int
0x18000abac  mov     eax, [r14+50h]
0x18000abb0  mov     dword ptr [rbp+0D0h+var_140], eax
0x18000abb3  mov     rax, [r14+48h]
0x18000abb7  mov     [rbp+0D0h+var_E8], rax
0x18000abbb  mov     eax, [r14+20h]
0x18000abbf  mov     dword ptr [rbp+0D0h+var_140+4], eax
0x18000abc2  mov     rax, [r14+18h]
0x18000abc6  mov     [rbp+0D0h+var_E0], rax
0x18000abca  mov     eax, [r14]
0x18000abcd  mov     dword ptr [rbp+0D0h+var_138], eax
0x18000abd0  mov     rax, [r14+80h]
0x18000abd7  mov     [rbp+0D0h+var_D8], rax
0x18000abdb  mov     eax, [r14+40h]
0x18000abdf  mov     dword ptr [rbp+0D0h+var_148], eax
0x18000abe2  mov     rax, [r14+38h]
0x18000abe6  mov     [rbp+0D0h+var_D0], rax
0x18000abea  mov     eax, [r14+8]
0x18000abee  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x18000abf1  mov     eax, 1000000h
0x18000abf6  mov     [rbp+0D0h+var_C8], rax
0x18000abfa  mov     [rbp+0D0h+var_130], rax
0x18000abfe  lea     rax, [rbp+0D0h+var_128]
0x18000ac02  mov     [rsp+210h+var_158], rax; __int64
0x18000ac0a  lea     rax, [rbp+0D0h+var_120]
0x18000ac0e  mov     [rsp+210h+var_160], rax; __int64
0x18000ac16  lea     rax, [rbp+0D0h+var_118]
0x18000ac1a  mov     [rsp+210h+var_168], rax; __int64
0x18000ac22  lea     rax, [rbp+0D0h+var_110]
0x18000ac26  mov     [rsp+210h+var_170], rax; __int64
0x18000ac2e  lea     rax, [rbp+0D0h+var_108]
0x18000ac32  mov     [rsp+210h+var_178], rax; __int64
0x18000ac3a  lea     rax, [rbp+0D0h+var_100]
0x18000ac3e  mov     [rsp+210h+var_180], rax; __int64
0x18000ac46  lea     rax, [rbp+0D0h+var_148+4]
0x18000ac4a  mov     [rsp+210h+var_188], rax; __int64
0x18000ac52  lea     rax, [rbp+0D0h+var_F8]
0x18000ac56  mov     [rsp+210h+var_190], rax; __int64
0x18000ac5e  lea     rax, [rbp+0D0h+var_F0]
0x18000ac62  mov     [rsp+210h+var_198], rax; __int64
0x18000ac67  lea     rax, [rbp+0D0h+var_140]
0x18000ac6b  mov     [rsp+210h+var_1A0], rax; __int64
0x18000ac70  lea     rax, [rbp+0D0h+var_E8]
0x18000ac74  mov     [rsp+210h+var_1A8], rax; __int64
0x18000ac79  lea     rax, [rbp+0D0h+var_140+4]
0x18000ac7d  mov     [rsp+210h+var_1B0], rax; __int64
0x18000ac82  lea     rax, [rbp+0D0h+var_E0]
0x18000ac86  mov     [rsp+210h+var_1B8], rax; __int64
0x18000ac8b  lea     rax, [rbp+0D0h+var_138]
0x18000ac8f  mov     [rsp+210h+var_1C0], rax; __int64
0x18000ac94  lea     rax, [rbp+0D0h+var_D8]
0x18000ac98  mov     [rsp+210h+var_1C8], rax; __int64
0x18000ac9d  lea     rax, [rbp+0D0h+var_148]
0x18000aca1  mov     [rsp+210h+var_1D0], rax; __int64
0x18000aca6  lea     rax, [rbp+0D0h+var_D0]
0x18000acaa  mov     [rsp+210h+var_1D8], rax; __int64
0x18000acaf  lea     rax, [rbp+0D0h+SRWLock]
0x18000acb3  mov     [rsp+210h+var_1E0], rax; __int64
0x18000acb8  lea     rax, [rbp+0D0h+var_C8]
0x18000acbc  mov     [rsp+210h+var_1E8], rax; __int64
0x18000acc1  lea     rax, [rbp+0D0h+var_130]
0x18000acc5  mov     qword ptr [rsp+210h+var_1F0], rax; __int64
0x18000acca  mov     [rbp+0D0h+var_118], rcx
0x18000acce  lea     rdx, byte_180090A3F; int
0x18000acd5  mov     rcx, r9; int
0x18000acd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18000acdd  jmp     loc_18000AE79
0x18000ace2  mov     rbx, rsi
0x18000ace5  lea     rdx, [rbp+0D0h+SRWLock]
0x18000ace9  mov     [rbp+0D0h+SRWLock], r15
0x18000aced  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000acf2  mov     rax, [rbx]
0x18000acf5  mov     ebx, 2
0x18000acfa  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18000acfe  mov     [rax], ebx
0x18000ad00  test    rcx, rcx
0x18000ad03  jz      short loc_18000AD0B
0x18000ad05  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad0b  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000ad10  mov     r13, [rax+8]
0x18000ad14  cmp     dword ptr [r13+0], 5
0x18000ad19  jbe     loc_18000AE79
0x18000ad1f  mov     rcx, 400000000000h
0x18000ad29  test    [r13+10h], rcx
0x18000ad2d  jz      loc_18000AE79
0x18000ad33  mov     rax, [r13+18h]
0x18000ad37  and     rax, rcx
0x18000ad3a  cmp     rax, [r13+18h]
0x18000ad3e  jnz     loc_18000AE79
0x18000ad44  mov     r14, [rdi+150h]
0x18000ad4b  mov     r15, [rdi+148h]
0x18000ad52  mov     r12, [r12]
0x18000ad56  call    cs:__imp_GetCurrentThreadId
0x18000ad5c  mov     r8, [rsi]
0x18000ad5f  lea     r9, S2
0x18000ad66  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x18000ad69  xor     edx, edx
0x18000ad6b  mov     eax, [r8+48h]
0x18000ad6f  mov     dword ptr [rbp+0D0h+var_148], eax
0x18000ad72  mov     eax, 1000000h
0x18000ad77  mov     [rbp+0D0h+var_130], rax
0x18000ad7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ad7f  test    r14, r14
0x18000ad82  jz      short loc_18000AD9A
0x18000ad84  mov     rcx, rax
0x18000ad87  inc     rcx
0x18000ad8a  cmp     [r14+rcx*2], dx
0x18000ad8f  jnz     short loc_18000AD87
0x18000ad91  lea     ecx, ds:2[rcx*2]
0x18000ad98  jmp     short loc_18000AD9F
0x18000ad9a  mov     r14, r9
0x18000ad9d  mov     ecx, ebx
0x18000ad9f  mov     [rbp+0D0h+var_40], r14
0x18000ada6  mov     [rbp+0D0h+var_38], ecx
0x18000adac  mov     [rbp+0D0h+var_34], edx
0x18000adb2  test    r15, r15
0x18000adb5  jz      short loc_18000ADCD
0x18000adb7  mov     rcx, rax
0x18000adba  inc     rcx
0x18000adbd  cmp     [r15+rcx*2], dx
0x18000adc2  jnz     short loc_18000ADBA
0x18000adc4  lea     ecx, ds:2[rcx*2]
0x18000adcb  jmp     short loc_18000ADD2
0x18000adcd  mov     r15, r9
0x18000add0  mov     ecx, ebx
0x18000add2  mov     [rbp+0D0h+var_50], r15
0x18000add9  xor     r15d, r15d
0x18000addc  mov     [rbp+0D0h+var_48], ecx
0x18000ade2  lea     rcx, a15072603280120; "1507.2603.28012.0"
0x18000ade9  mov     [rbp+0D0h+var_44], r15d
0x18000adf0  mov     [rbp+0D0h+var_60], rcx
0x18000adf4  mov     [rbp+0D0h+var_58], 12h
0x18000adfc  test    r12, r12
0x18000adff  jz      short loc_18000AE14
0x18000ae01  inc     rax
0x18000ae04  cmp     [r12+rax*2], r15w
0x18000ae09  jnz     short loc_18000AE01
0x18000ae0b  lea     ebx, ds:2[rax*2]
0x18000ae12  jmp     short loc_18000AE17
0x18000ae14  mov     r12, r9
0x18000ae17  lea     rax, [rbp+0D0h+SRWLock]
0x18000ae1b  mov     [rbp+0D0h+var_70], r12
0x18000ae1f  mov     [rbp+0D0h+var_80], rax
0x18000ae23  lea     rdx, byte_1800909D1; int
0x18000ae2a  lea     rax, [rbp+0D0h+var_148]
0x18000ae2e  mov     [rbp+0D0h+var_68], ebx
0x18000ae31  mov     [rbp+0D0h+var_90], rax
0x18000ae35  add     r8, 8; int
0x18000ae39  lea     rax, [rbp+0D0h+var_130]
0x18000ae3d  mov     [rbp+0D0h+var_64], r15d
0x18000ae41  mov     [rbp+0D0h+var_A0], rax
0x18000ae45  xor     r9d, r9d; int
0x18000ae48  lea     rax, [rbp+0D0h+var_C0]
0x18000ae4c  mov     [rbp+0D0h+var_78], 4
0x18000ae54  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x18000ae59  mov     rcx, r13; int
0x18000ae5c  mov     [rsp+210h+var_1F0], 9; int
0x18000ae64  mov     [rbp+0D0h+var_88], 4
0x18000ae6c  mov     [rbp+0D0h+var_98], 8
0x18000ae74  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ae79  cmp     [rdi+138h], r15d
0x18000ae80  jz      short loc_18000AECF
0x18000ae82  lea     rbx, [rdi+120h]
0x18000ae89  call    cs:__imp_GetCurrentThreadId
0x18000ae8f  cmp     [rbx+18h], eax
0x18000ae92  jz      short loc_18000AEA6
0x18000ae94  mov     rcx, [rbp+0D8h]; this
0x18000ae9b  mov     r9d, 8007029Ch; char *
0x18000aea1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000aea6  mov     rcx, [rbx]
0x18000aea9  mov     [rbx+18h], r15d
0x18000aead  jmp     short loc_18000AEBB
0x18000aeaf  cmp     rax, rbx
0x18000aeb2  jz      short loc_18000AEC5
0x18000aeb4  lea     rcx, [rax+10h]
0x18000aeb8  mov     [rbx], rcx
0x18000aebb  mov     rax, [rcx]
0x18000aebe  test    rax, rax
0x18000aec1  jnz     short loc_18000AEAF
0x18000aec3  jmp     short loc_18000AECC
0x18000aec5  mov     rax, [rbx+10h]
0x18000aec9  mov     [rcx], rax
0x18000aecc  mov     [rbx], r15
0x18000aecf  mov     rcx, [rbp+0D0h+var_30]
0x18000aed6  xor     rcx, rsp; StackCookie
0x18000aed9  call    __security_check_cookie
0x18000aede  lea     r11, [rsp+210h+var_20]
0x18000aee6  mov     rbx, [r11+38h]
0x18000aeea  mov     rsi, [r11+40h]
0x18000aeee  mov     rdi, [r11+48h]
0x18000aef2  mov     rsp, r11
0x18000aef5  pop     r15
0x18000aef7  pop     r14
0x18000aef9  pop     r13
0x18000aefb  pop     r12
0x18000aefd  pop     rbp
0x18000aefe  retn
```
