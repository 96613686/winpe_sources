# ClientTelemetry::Run::Stop(wil::basic_zstring_view<wchar_t>,int)

- ea: `0x18000af08`
- end: `0x18000b3ad`
- name: `?Stop@Run@ClientTelemetry@@QEAAXV?$basic_zstring_view@_W@wil@@H@Z`
- size: `1189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800150a0`

## callees

- `0x1800013a4`
- `0x180001f60`
- `0x18000a2ac`
- `0x18000af08`
- `0x18001a1bc`
- `0x180035ec8`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b337`

## pseudocode

```c
struct ClientTelemetry *__fastcall ClientTelemetry::Run::Stop(__int64 a1, __int64 *a2, int a3)
{
  _DWORD **v3; // rsi
  __int64 v4; // r14
  int v8; // eax
  int *v9; // r14
  _DWORD **v10; // rbx
  RTL_SRWLOCK *v11; // rcx
  struct ClientTelemetry *result; // rax
  __int64 v13; // r9
  _DWORD *v14; // r8
  _DWORD *v15; // rax
  int v16; // ebx
  RTL_SRWLOCK *v17; // rcx
  __int64 v18; // r13
  const wchar_t *v19; // r14
  const wchar_t *v20; // r15
  const wchar_t *v21; // r12
  DWORD CurrentThreadId; // eax
  _DWORD *v23; // r8
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // ecx
  __int64 v27; // rcx
  int v28; // ecx
  struct ClientTelemetry *v29; // rbx
  void *v30; // rdx
  unsigned int v31; // r8d
  struct ClientTelemetry **v32; // rcx
  int v33; // [rsp+28h] [rbp-130h]
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-80h] BYREF
  int v35; // [rsp+E0h] [rbp-78h] BYREF
  DWORD v36; // [rsp+E4h] [rbp-74h] BYREF
  __int64 v37; // [rsp+E8h] [rbp-70h] BYREF
  int v38; // [rsp+F0h] [rbp-68h] BYREF
  int v39; // [rsp+F4h] [rbp-64h] BYREF
  int v40; // [rsp+F8h] [rbp-60h] BYREF
  int v41; // [rsp+FCh] [rbp-5Ch] BYREF
  __int64 v42; // [rsp+100h] [rbp-58h] BYREF
  __int64 v43; // [rsp+108h] [rbp-50h] BYREF
  __int64 v44; // [rsp+110h] [rbp-48h] BYREF
  __int64 v45; // [rsp+118h] [rbp-40h] BYREF
  __int64 v46; // [rsp+120h] [rbp-38h] BYREF
  __int64 v47; // [rsp+128h] [rbp-30h] BYREF
  __int64 v48; // [rsp+130h] [rbp-28h] BYREF
  __int64 v49; // [rsp+138h] [rbp-20h] BYREF
  __int64 v50; // [rsp+140h] [rbp-18h] BYREF
  __int64 v51; // [rsp+148h] [rbp-10h] BYREF
  __int64 v52; // [rsp+150h] [rbp-8h] BYREF
  __int64 v53; // [rsp+158h] [rbp+0h] BYREF
  __int64 v54; // [rsp+160h] [rbp+8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+168h] [rbp+10h] BYREF
  __int64 *v56; // [rsp+188h] [rbp+30h]
  __int64 v57; // [rsp+190h] [rbp+38h]
  int *v58; // [rsp+198h] [rbp+40h]
  __int64 v59; // [rsp+1A0h] [rbp+48h]
  DWORD *v60; // [rsp+1A8h] [rbp+50h]
  __int64 v61; // [rsp+1B0h] [rbp+58h]
  const wchar_t *v62; // [rsp+1B8h] [rbp+60h]
  int v63; // [rsp+1C0h] [rbp+68h]
  int v64; // [rsp+1C4h] [rbp+6Ch]
  PSRWLOCK *p_SRWLock; // [rsp+1C8h] [rbp+70h]
  __int64 v66; // [rsp+1D0h] [rbp+78h]
  const char *v67; // [rsp+1D8h] [rbp+80h]
  __int64 v68; // [rsp+1E0h] [rbp+88h]
  const wchar_t *v69; // [rsp+1E8h] [rbp+90h]
  int v70; // [rsp+1F0h] [rbp+98h]
  int v71; // [rsp+1F4h] [rbp+9Ch]
  const wchar_t *v72; // [rsp+1F8h] [rbp+A0h]
  int v73; // [rsp+200h] [rbp+A8h]
  int v74; // [rsp+204h] [rbp+ACh]
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+E8h]

  v3 = (_DWORD **)(a1 + 272);
  v37 = (__int64)a2;
  v4 = *(_QWORD *)(a1 + 272);
  v8 = *(_DWORD *)(v4 + 72);
  if ( v8 < 0 && (v9 = (int *)(v4 + 80), v8 == v9[2]) )
  {
    v10 = (_DWORD **)(a1 + 272);
    if ( v9 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v11 = SRWLock;
      **v3 = 2;
      if ( v11 )
        ReleaseSRWLockExclusive(v11);
      result = ClientTelemetry::Instance();
      v13 = *((_QWORD *)result + 1);
      if ( *(_DWORD *)v13 > 5u && (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0 )
      {
        result = (struct ClientTelemetry *)(*(_QWORD *)(v13 + 24) & 0x400000000000LL);
        if ( result == *(struct ClientTelemetry **)(v13 + 24) )
        {
          v42 = *(_QWORD *)(a1 + 336);
          v43 = *(_QWORD *)(a1 + 328);
          v45 = *a2;
          v46 = *((_QWORD *)v9 + 15);
          v47 = *((_QWORD *)v9 + 14);
          v39 = v9[26];
          v48 = *((_QWORD *)v9 + 12);
          v14 = *v3;
          v49 = *((_QWORD *)v9 + 11);
          v40 = v9[20];
          v50 = *((_QWORD *)v9 + 9);
          v41 = v9[8];
          v51 = *((_QWORD *)v9 + 3);
          v35 = *v9;
          v52 = *((_QWORD *)v9 + 16);
          v36 = v9[16];
          v53 = *((_QWORD *)v9 + 7);
          LODWORD(SRWLock) = v9[2];
          v54 = 0x1000000;
          v37 = 0x1000000;
          v44 = (__int64)"1507.2603.28012.0";
          v38 = a3;
          result = (struct ClientTelemetry *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
                                               v13,
                                               (int)&dword_18009087C,
                                               (int)v14 + 8,
                                               (__int64)&v37,
                                               (__int64)&v54,
                                               (__int64)&SRWLock,
                                               (__int64)&v53,
                                               (__int64)&v36,
                                               (__int64)&v52,
                                               (__int64)&v35,
                                               (__int64)&v51,
                                               (__int64)&v41,
                                               (__int64)&v50,
                                               (__int64)&v40,
                                               (__int64)&v49,
                                               (__int64)&v48,
                                               (__int64)&v39,
                                               (__int64)&v47,
                                               (__int64)&v46,
                                               (__int64)&v45,
                                               (__int64)&v38,
                                               (__int64)&v44,
                                               (__int64)&v43,
                                               (__int64)&v42);
        }
      }
      goto LABEL_31;
    }
  }
  else
  {
    v10 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v15 = *v10;
  v16 = 2;
  v17 = SRWLock;
  *v15 = 2;
  if ( v17 )
    ReleaseSRWLockExclusive(v17);
  result = ClientTelemetry::Instance();
  v18 = *((_QWORD *)result + 1);
  if ( *(_DWORD *)v18 > 5u && (*(_QWORD *)(v18 + 16) & 0x400000000000LL) != 0 )
  {
    result = (struct ClientTelemetry *)(*(_QWORD *)(v18 + 24) & 0x400000000000LL);
    if ( result == *(struct ClientTelemetry **)(v18 + 24) )
    {
      v19 = *(const wchar_t **)(a1 + 336);
      v20 = *(const wchar_t **)(a1 + 328);
      LODWORD(SRWLock) = a3;
      v21 = *(const wchar_t **)v37;
      CurrentThreadId = GetCurrentThreadId();
      v23 = *v3;
      v36 = CurrentThreadId;
      v35 = v23[18];
      v37 = 0x1000000;
      v24 = -1;
      if ( v19 )
      {
        v25 = -1;
        do
          ++v25;
        while ( v19[v25] );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v19 = &S2;
        v26 = 2;
      }
      v72 = v19;
      v73 = v26;
      v74 = 0;
      if ( v20 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v20[v27] );
        v28 = 2 * v27 + 2;
      }
      else
      {
        v20 = &S2;
        v28 = 2;
      }
      v70 = v28;
      v67 = "1507.2603.28012.0";
      p_SRWLock = &SRWLock;
      v69 = v20;
      v71 = 0;
      v68 = 18;
      v66 = 4;
      if ( v21 )
      {
        do
          ++v24;
        while ( v21[v24] );
        v16 = 2 * v24 + 2;
      }
      else
      {
        v21 = &S2;
      }
      v64 = 0;
      v60 = &v36;
      v62 = v21;
      v58 = &v35;
      v63 = v16;
      v56 = &v37;
      v61 = 4;
      v59 = 4;
      v57 = 8;
      result = (struct ClientTelemetry *)tlgWriteTransfer_EventWriteTransfer(
                                           v18,
                                           (int)&word_1800907FE,
                                           (int)v23 + 8,
                                           0,
                                           0xAu,
                                           &v55);
    }
  }
LABEL_31:
  if ( *(_DWORD *)(a1 + 312) )
  {
    v29 = (struct ClientTelemetry *)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v30, v31, (const char *)0x8007029CLL, v33);
    v32 = *(struct ClientTelemetry ***)v29;
    *(_DWORD *)(a1 + 312) = 0;
    while ( 1 )
    {
      result = *v32;
      if ( !*v32 )
        break;
      if ( result == v29 )
      {
        result = *(struct ClientTelemetry **)(a1 + 304);
        *v32 = result;
        break;
      }
      v32 = (struct ClientTelemetry **)((char *)result + 16);
      *(_QWORD *)v29 = (char *)result + 16;
    }
    *(_QWORD *)v29 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000af08  mov     rax, rsp
0x18000af0b  mov     [rax+10h], rbx
0x18000af0f  mov     [rax+18h], rsi
0x18000af13  mov     [rax+20h], rdi
0x18000af17  push    rbp
0x18000af18  push    r12
0x18000af1a  push    r13
0x18000af1c  push    r14
0x18000af1e  push    r15
0x18000af20  lea     rbp, [rax-0E8h]
0x18000af27  sub     rsp, 210h
0x18000af2e  mov     rax, cs:__security_cookie
0x18000af35  xor     rax, rsp
0x18000af38  mov     [rbp+0E0h+var_30], rax
0x18000af3f  lea     rsi, [rcx+110h]
0x18000af46  mov     [rbp+0E0h+var_150], rdx
0x18000af4a  mov     r14, [rsi]
0x18000af4d  xor     r13d, r13d
0x18000af50  mov     r12d, r8d
0x18000af53  mov     r15, rdx
0x18000af56  mov     rdi, rcx
0x18000af59  mov     eax, [r14+48h]
0x18000af5d  test    eax, eax
0x18000af5f  jns     loc_18000B174
0x18000af65  add     r14, 50h ; 'P'
0x18000af69  cmp     eax, [r14+8]
0x18000af6d  jnz     loc_18000B174
0x18000af73  mov     rbx, rsi
0x18000af76  test    r14, r14
0x18000af79  jz      loc_18000B177
0x18000af7f  lea     rdx, [rbp+0E0h+SRWLock]
0x18000af83  mov     [rbp+0E0h+SRWLock], r13
0x18000af87  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000af8c  mov     rax, [rsi]
0x18000af8f  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18000af93  mov     dword ptr [rax], 2
0x18000af99  test    rcx, rcx
0x18000af9c  jz      short loc_18000AFA4
0x18000af9e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000afa4  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000afa9  mov     r9, [rax+8]
0x18000afad  cmp     dword ptr [r9], 5
0x18000afb1  jbe     loc_18000B327
0x18000afb7  mov     rcx, 400000000000h
0x18000afc1  test    [r9+10h], rcx
0x18000afc5  jz      loc_18000B327
0x18000afcb  mov     rax, [r9+18h]
0x18000afcf  and     rax, rcx
0x18000afd2  cmp     rax, [r9+18h]
0x18000afd6  jnz     loc_18000B327
0x18000afdc  mov     rax, [rdi+150h]
0x18000afe3  lea     rcx, a15072603280120; "1507.2603.28012.0"
0x18000afea  mov     [rbp+0E0h+var_138], rax
0x18000afee  mov     rax, [rdi+148h]
0x18000aff5  mov     [rbp+0E0h+var_130], rax
0x18000aff9  mov     rax, [r15]
0x18000affc  mov     [rbp+0E0h+var_120], rax
0x18000b000  mov     rax, [r14+78h]
0x18000b004  mov     [rbp+0E0h+var_118], rax
0x18000b008  mov     rax, [r14+70h]
0x18000b00c  mov     [rbp+0E0h+var_110], rax
0x18000b010  mov     eax, [r14+68h]
0x18000b014  mov     dword ptr [rbp+0E0h+var_148+4], eax
0x18000b017  mov     rax, [r14+60h]
0x18000b01b  mov     [rbp+0E0h+var_108], rax
0x18000b01f  mov     rax, [r14+58h]
0x18000b023  mov     r8, [rsi]
0x18000b026  mov     [rbp+0E0h+var_100], rax
0x18000b02a  add     r8, 8; int
0x18000b02e  mov     eax, [r14+50h]
0x18000b032  mov     dword ptr [rbp+0E0h+var_140], eax
0x18000b035  mov     rax, [r14+48h]
0x18000b039  mov     [rbp+0E0h+var_F8], rax
0x18000b03d  mov     eax, [r14+20h]
0x18000b041  mov     dword ptr [rbp+0E0h+var_140+4], eax
0x18000b044  mov     rax, [r14+18h]
0x18000b048  mov     [rbp+0E0h+var_F0], rax
0x18000b04c  mov     eax, [r14]
0x18000b04f  mov     dword ptr [rbp+0E0h+var_158], eax
0x18000b052  mov     rax, [r14+80h]
0x18000b059  mov     [rbp+0E0h+var_E8], rax
0x18000b05d  mov     eax, [r14+40h]
0x18000b061  mov     dword ptr [rbp+0E0h+var_158+4], eax
0x18000b064  mov     rax, [r14+38h]
0x18000b068  mov     [rbp+0E0h+var_E0], rax
0x18000b06c  mov     eax, [r14+8]
0x18000b070  mov     dword ptr [rbp+0E0h+SRWLock], eax
0x18000b073  mov     eax, 1000000h
0x18000b078  mov     [rbp+0E0h+var_D8], rax
0x18000b07c  mov     [rbp+0E0h+var_150], rax
0x18000b080  lea     rax, [rbp+0E0h+var_138]
0x18000b084  mov     [rsp+230h+var_170], rax; __int64
0x18000b08c  lea     rax, [rbp+0E0h+var_130]
0x18000b090  mov     [rsp+230h+var_178], rax; __int64
0x18000b098  lea     rax, [rbp+0E0h+var_128]
0x18000b09c  mov     [rsp+230h+var_180], rax; __int64
0x18000b0a4  lea     rax, [rbp+0E0h+var_148]
0x18000b0a8  mov     [rsp+230h+var_188], rax; __int64
0x18000b0b0  lea     rax, [rbp+0E0h+var_120]
0x18000b0b4  mov     [rsp+230h+var_190], rax; __int64
0x18000b0bc  lea     rax, [rbp+0E0h+var_118]
0x18000b0c0  mov     [rsp+230h+var_198], rax; __int64
0x18000b0c8  lea     rax, [rbp+0E0h+var_110]
0x18000b0cc  mov     [rsp+230h+var_1A0], rax; __int64
0x18000b0d4  lea     rax, [rbp+0E0h+var_148+4]
0x18000b0d8  mov     [rsp+230h+var_1A8], rax; __int64
0x18000b0e0  lea     rax, [rbp+0E0h+var_108]
0x18000b0e4  mov     [rsp+230h+var_1B0], rax; __int64
0x18000b0ec  lea     rax, [rbp+0E0h+var_100]
0x18000b0f0  mov     [rsp+230h+var_1B8], rax; __int64
0x18000b0f5  lea     rax, [rbp+0E0h+var_140]
0x18000b0f9  mov     [rsp+230h+var_1C0], rax; __int64
0x18000b0fe  lea     rax, [rbp+0E0h+var_F8]
0x18000b102  mov     [rsp+230h+var_1C8], rax; __int64
0x18000b107  lea     rax, [rbp+0E0h+var_140+4]
0x18000b10b  mov     [rsp+230h+var_1D0], rax; __int64
0x18000b110  lea     rax, [rbp+0E0h+var_F0]
0x18000b114  mov     [rsp+230h+var_1D8], rax; __int64
0x18000b119  lea     rax, [rbp+0E0h+var_158]
0x18000b11d  mov     [rsp+230h+var_1E0], rax; __int64
0x18000b122  lea     rax, [rbp+0E0h+var_E8]
0x18000b126  mov     [rsp+230h+var_1E8], rax; __int64
0x18000b12b  lea     rax, [rbp+0E0h+var_158+4]
0x18000b12f  mov     [rsp+230h+var_1F0], rax; __int64
0x18000b134  lea     rax, [rbp+0E0h+var_E0]
0x18000b138  mov     [rsp+230h+var_1F8], rax; __int64
0x18000b13d  lea     rax, [rbp+0E0h+SRWLock]
0x18000b141  mov     [rsp+230h+var_200], rax; __int64
0x18000b146  lea     rax, [rbp+0E0h+var_D8]
0x18000b14a  mov     [rbp+0E0h+var_128], rcx
0x18000b14e  mov     dword ptr [rbp+0E0h+var_148], r12d
0x18000b152  mov     [rsp+230h+var_208], rax; __int64
0x18000b157  lea     rdx, dword_18009087C; int
0x18000b15e  lea     rax, [rbp+0E0h+var_150]
0x18000b162  mov     rcx, r9; int
0x18000b165  mov     qword ptr [rsp+230h+var_210], rax; __int64
0x18000b16a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645664566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18000b16f  jmp     loc_18000B327
0x18000b174  mov     rbx, rsi
0x18000b177  lea     rdx, [rbp+0E0h+SRWLock]
0x18000b17b  mov     [rbp+0E0h+SRWLock], r13
0x18000b17f  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b184  mov     rax, [rbx]
0x18000b187  mov     ebx, 2
0x18000b18c  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18000b190  mov     [rax], ebx
0x18000b192  test    rcx, rcx
0x18000b195  jz      short loc_18000B19D
0x18000b197  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b19d  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000b1a2  mov     r13, [rax+8]
0x18000b1a6  cmp     dword ptr [r13+0], 5
0x18000b1ab  jbe     loc_18000B324
0x18000b1b1  mov     rcx, 400000000000h
0x18000b1bb  test    [r13+10h], rcx
0x18000b1bf  jz      loc_18000B324
0x18000b1c5  mov     rax, [r13+18h]
0x18000b1c9  and     rax, rcx
0x18000b1cc  cmp     rax, [r13+18h]
0x18000b1d0  jnz     loc_18000B324
0x18000b1d6  mov     r14, [rdi+150h]
0x18000b1dd  mov     r15, [rdi+148h]
0x18000b1e4  mov     dword ptr [rbp+0E0h+SRWLock], r12d
0x18000b1e8  mov     r12, [rbp+0E0h+var_150]
0x18000b1ec  mov     r12, [r12]
0x18000b1f0  call    cs:__imp_GetCurrentThreadId
0x18000b1f6  mov     r8, [rsi]
0x18000b1f9  lea     r9, S2
0x18000b200  mov     dword ptr [rbp+0E0h+var_158+4], eax
0x18000b203  xor     edx, edx
0x18000b205  mov     eax, [r8+48h]
0x18000b209  mov     dword ptr [rbp+0E0h+var_158], eax
0x18000b20c  mov     eax, 1000000h
0x18000b211  mov     [rbp+0E0h+var_150], rax
0x18000b215  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b219  test    r14, r14
0x18000b21c  jz      short loc_18000B234
0x18000b21e  mov     rcx, rax
0x18000b221  inc     rcx
0x18000b224  cmp     [r14+rcx*2], dx
0x18000b229  jnz     short loc_18000B221
0x18000b22b  lea     ecx, ds:2[rcx*2]
0x18000b232  jmp     short loc_18000B239
0x18000b234  mov     r14, r9
0x18000b237  mov     ecx, ebx
0x18000b239  mov     [rbp+0E0h+var_40], r14
0x18000b240  mov     [rbp+0E0h+var_38], ecx
0x18000b246  mov     [rbp+0E0h+var_34], edx
0x18000b24c  test    r15, r15
0x18000b24f  jz      short loc_18000B267
0x18000b251  mov     rcx, rax
0x18000b254  inc     rcx
0x18000b257  cmp     [r15+rcx*2], dx
0x18000b25c  jnz     short loc_18000B254
0x18000b25e  lea     ecx, ds:2[rcx*2]
0x18000b265  jmp     short loc_18000B26C
0x18000b267  mov     r15, r9
0x18000b26a  mov     ecx, ebx
0x18000b26c  mov     [rbp+0E0h+var_48], ecx
0x18000b272  lea     rcx, a15072603280120; "1507.2603.28012.0"
0x18000b279  mov     [rbp+0E0h+var_60], rcx
0x18000b280  lea     rcx, [rbp+0E0h+SRWLock]
0x18000b284  mov     [rbp+0E0h+var_70], rcx
0x18000b288  mov     [rbp+0E0h+var_50], r15
0x18000b28f  mov     [rbp+0E0h+var_44], edx
0x18000b295  mov     [rbp+0E0h+var_58], 12h
0x18000b2a0  mov     [rbp+0E0h+var_68], 4
0x18000b2a8  test    r12, r12
0x18000b2ab  jz      short loc_18000B2C0
0x18000b2ad  inc     rax
0x18000b2b0  cmp     [r12+rax*2], dx
0x18000b2b5  jnz     short loc_18000B2AD
0x18000b2b7  lea     ebx, ds:2[rax*2]
0x18000b2be  jmp     short loc_18000B2C3
0x18000b2c0  mov     r12, r9
0x18000b2c3  lea     rax, [rbp+0E0h+var_158+4]
0x18000b2c7  mov     [rbp+0E0h+var_74], edx
0x18000b2ca  mov     [rbp+0E0h+var_90], rax
0x18000b2ce  lea     rdx, word_1800907FE; int
0x18000b2d5  lea     rax, [rbp+0E0h+var_158]
0x18000b2d9  mov     [rbp+0E0h+var_80], r12
0x18000b2dd  mov     [rbp+0E0h+var_A0], rax
0x18000b2e1  add     r8, 8; int
0x18000b2e5  lea     rax, [rbp+0E0h+var_150]
0x18000b2e9  mov     [rbp+0E0h+var_78], ebx
0x18000b2ec  mov     [rbp+0E0h+var_B0], rax
0x18000b2f0  xor     r9d, r9d; int
0x18000b2f3  lea     rax, [rbp+0E0h+var_D0]
0x18000b2f7  mov     [rbp+0E0h+var_88], 4
0x18000b2ff  mov     [rsp+230h+var_208], rax; PEVENT_DATA_DESCRIPTOR
0x18000b304  mov     rcx, r13; int
0x18000b307  mov     [rsp+230h+var_210], 0Ah; int
0x18000b30f  mov     [rbp+0E0h+var_98], 4
0x18000b317  mov     [rbp+0E0h+var_A8], 8
0x18000b31f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b324  xor     r13d, r13d
0x18000b327  cmp     [rdi+138h], r13d
0x18000b32e  jz      short loc_18000B37D
0x18000b330  lea     rbx, [rdi+120h]
0x18000b337  call    cs:__imp_GetCurrentThreadId
0x18000b33d  cmp     [rbx+18h], eax
0x18000b340  jz      short loc_18000B354
0x18000b342  mov     rcx, [rbp+0E8h]; this
0x18000b349  mov     r9d, 8007029Ch; char *
0x18000b34f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000b354  mov     rcx, [rbx]
0x18000b357  mov     [rbx+18h], r13d
0x18000b35b  jmp     short loc_18000B369
0x18000b35d  cmp     rax, rbx
0x18000b360  jz      short loc_18000B373
0x18000b362  lea     rcx, [rax+10h]
0x18000b366  mov     [rbx], rcx
0x18000b369  mov     rax, [rcx]
0x18000b36c  test    rax, rax
0x18000b36f  jnz     short loc_18000B35D
0x18000b371  jmp     short loc_18000B37A
0x18000b373  mov     rax, [rbx+10h]
0x18000b377  mov     [rcx], rax
0x18000b37a  mov     [rbx], r13
0x18000b37d  mov     rcx, [rbp+0E0h+var_30]
0x18000b384  xor     rcx, rsp; StackCookie
0x18000b387  call    __security_check_cookie
0x18000b38c  lea     r11, [rsp+230h+var_20]
0x18000b394  mov     rbx, [r11+38h]
0x18000b398  mov     rsi, [r11+40h]
0x18000b39c  mov     rdi, [r11+48h]
0x18000b3a0  mov     rsp, r11
0x18000b3a3  pop     r15
0x18000b3a5  pop     r14
0x18000b3a7  pop     r13
0x18000b3a9  pop     r12
0x18000b3ab  pop     rbp
0x18000b3ac  retn
```
