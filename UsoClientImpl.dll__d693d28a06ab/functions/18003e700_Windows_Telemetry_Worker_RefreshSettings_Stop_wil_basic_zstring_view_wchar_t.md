# Windows::Telemetry::Worker::RefreshSettings::Stop(wil::basic_zstring_view<wchar_t>)

- ea: `0x18003e700`
- end: `0x18003ea95`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003ef00`

## callees

- `0x180001f60`
- `0x180002314`
- `0x18001a1bc`
- `0x18003e044`
- `0x18003e700`
- `0x1800434ec`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e950`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e998`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(__int64 a1, __int64 *a2)
{
  _DWORD **v2; // r14
  __int64 v3; // rsi
  int v6; // eax
  __int64 v7; // rsi
  _DWORD **v8; // rbx
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  _DWORD *v11; // r8
  _DWORD *v12; // rax
  int v13; // ebx
  RTL_SRWLOCK *v14; // rcx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // rsi
  const wchar_t *v17; // r15
  DWORD CurrentThreadId; // eax
  _DWORD *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  int v24; // [rsp+D4h] [rbp-6Ch] BYREF
  int v25; // [rsp+D8h] [rbp-68h] BYREF
  int v26; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+100h] [rbp-40h] BYREF
  __int64 v32; // [rsp+108h] [rbp-38h] BYREF
  __int64 v33; // [rsp+110h] [rbp-30h] BYREF
  __int64 v34; // [rsp+118h] [rbp-28h] BYREF
  __int64 v35; // [rsp+120h] [rbp-20h] BYREF
  __int64 v36; // [rsp+128h] [rbp-18h] BYREF
  __int64 v37; // [rsp+130h] [rbp-10h] BYREF
  __int64 v38; // [rsp+138h] [rbp-8h] BYREF
  __int64 v39; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v41; // [rsp+170h] [rbp+30h]
  __int64 v42; // [rsp+178h] [rbp+38h]
  int *v43; // [rsp+180h] [rbp+40h]
  __int64 v44; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v46; // [rsp+198h] [rbp+58h]
  const wchar_t *v47; // [rsp+1A0h] [rbp+60h]
  int v48; // [rsp+1A8h] [rbp+68h]
  int v49; // [rsp+1ACh] [rbp+6Ch]
  __int64 *v50; // [rsp+1B0h] [rbp+70h]
  __int64 v51; // [rsp+1B8h] [rbp+78h]
  const char *v52; // [rsp+1C0h] [rbp+80h]
  __int64 v53; // [rsp+1C8h] [rbp+88h]

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
      v10 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v10 > 5u
        && (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
      {
        v11 = *v2;
        v29 = (__int64)"1507.2603.28012.0";
        LOBYTE(v21) = *(_BYTE *)(a1 + 328);
        v30 = *a2;
        v31 = *(_QWORD *)(v7 + 120);
        v32 = *(_QWORD *)(v7 + 112);
        v24 = *(_DWORD *)(v7 + 104);
        v33 = *(_QWORD *)(v7 + 96);
        v34 = *(_QWORD *)(v7 + 88);
        v25 = *(_DWORD *)(v7 + 80);
        v35 = *(_QWORD *)(v7 + 72);
        v26 = *(_DWORD *)(v7 + 32);
        v36 = *(_QWORD *)(v7 + 24);
        LODWORD(v27) = *(_DWORD *)v7;
        v37 = *(_QWORD *)(v7 + 128);
        v23 = *(_DWORD *)(v7 + 64);
        v38 = *(_QWORD *)(v7 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v7 + 8);
        v39 = 0x1000000;
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
          (int)v10,
          (int)&byte_180091705,
          (_DWORD)v11 + 8,
          (__int64)&v28,
          (__int64)&v39,
          (__int64)&SRWLock,
          (__int64)&v38,
          (__int64)&v23,
          (__int64)&v37,
          (__int64)&v27,
          (__int64)&v36,
          (__int64)&v26,
          (__int64)&v35,
          (__int64)&v25,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v24,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v21,
          (__int64)&v29);
      }
      goto LABEL_22;
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
  v12 = *v8;
  v13 = 2;
  v14 = SRWLock;
  *v12 = 2;
  if ( v14 )
    ReleaseSRWLockExclusive(v14);
  v15 = Windows::Telemetry::Base::Provider();
  v16 = (__int64)v15;
  if ( *(_DWORD *)v15 > 5u
    && (*((_QWORD *)v15 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v15 + 3) & 0x400000000000LL) == *((_QWORD *)v15 + 3) )
  {
    v17 = (const wchar_t *)*a2;
    LOBYTE(v21) = *(_BYTE *)(a1 + 328);
    CurrentThreadId = GetCurrentThreadId();
    v19 = *v2;
    LODWORD(SRWLock) = CurrentThreadId;
    v53 = 18;
    v51 = 1;
    v23 = v19[18];
    v28 = 0x1000000;
    v52 = "1507.2603.28012.0";
    v50 = &v21;
    if ( v17 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v17[v20] );
      v13 = 2 * v20 + 2;
    }
    else
    {
      v17 = &S2;
    }
    v47 = v17;
    p_SRWLock = &SRWLock;
    v48 = v13;
    v43 = &v23;
    v49 = 0;
    v41 = &v28;
    v46 = 4;
    v44 = 4;
    v42 = 8;
    tlgWriteTransfer_EventWriteTransfer(v16, (unsigned __int8 *)&unk_180091688, (const GUID *)(v19 + 2), 0, 8u, &v40);
  }
LABEL_22:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18003e700  mov     [rsp-8+arg_8], rbx
0x18003e705  mov     [rsp-8+arg_10], rsi
0x18003e70a  push    rbp
0x18003e70b  push    rdi
0x18003e70c  push    r12
0x18003e70e  push    r14
0x18003e710  push    r15
0x18003e712  lea     rbp, [rsp-0A0h]
0x18003e71a  sub     rsp, 1E0h
0x18003e721  mov     rax, cs:__security_cookie
0x18003e728  xor     rax, rsp
0x18003e72b  mov     [rbp+0C0h+var_30], rax
0x18003e732  lea     r14, [rcx+110h]
0x18003e739  xor     r12d, r12d
0x18003e73c  mov     rsi, [r14]
0x18003e73f  mov     r15, rdx
0x18003e742  mov     rdi, rcx
0x18003e745  mov     eax, [rsi+48h]
0x18003e748  test    eax, eax
0x18003e74a  jns     loc_18003E92D
0x18003e750  add     rsi, 50h ; 'P'
0x18003e754  cmp     eax, [rsi+8]
0x18003e757  jnz     loc_18003E92D
0x18003e75d  mov     rbx, r14
0x18003e760  test    rsi, rsi
0x18003e763  jz      loc_18003E930
0x18003e769  lea     rdx, [rbp+0C0h+SRWLock]
0x18003e76d  mov     [rbp+0C0h+SRWLock], r12
0x18003e771  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003e776  mov     rax, [r14]
0x18003e779  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x18003e77d  mov     dword ptr [rax], 2
0x18003e783  test    rcx, rcx
0x18003e786  jz      short loc_18003E78E
0x18003e788  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e78e  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003e793  mov     r9, rax
0x18003e796  cmp     dword ptr [rax], 5
0x18003e799  jbe     loc_18003EA62
0x18003e79f  mov     rdx, 400000000000h
0x18003e7a9  test    [rax+10h], rdx
0x18003e7ad  jz      loc_18003EA62
0x18003e7b3  mov     rcx, [rax+18h]
0x18003e7b7  and     rcx, rdx
0x18003e7ba  cmp     rcx, [rax+18h]
0x18003e7be  jnz     loc_18003EA62
0x18003e7c4  mov     r8, [r14]
0x18003e7c7  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18003e7ce  mov     [rbp+0C0h+var_110], rax
0x18003e7d2  lea     rdx, byte_180091705; int
0x18003e7d9  mov     al, [rdi+148h]
0x18003e7df  add     r8, 8; int
0x18003e7e3  mov     byte ptr [rbp+0C0h+var_140], al
0x18003e7e6  mov     rcx, r9; int
0x18003e7e9  mov     rax, [r15]
0x18003e7ec  mov     [rbp+0C0h+var_108], rax
0x18003e7f0  mov     rax, [rsi+78h]
0x18003e7f4  mov     [rbp+0C0h+var_100], rax
0x18003e7f8  mov     rax, [rsi+70h]
0x18003e7fc  mov     [rbp+0C0h+var_F8], rax
0x18003e800  mov     eax, [rsi+68h]
0x18003e803  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x18003e806  mov     rax, [rsi+60h]
0x18003e80a  mov     [rbp+0C0h+var_F0], rax
0x18003e80e  mov     rax, [rsi+58h]
0x18003e812  mov     [rbp+0C0h+var_E8], rax
0x18003e816  mov     eax, [rsi+50h]
0x18003e819  mov     dword ptr [rbp+0C0h+var_128], eax
0x18003e81c  mov     rax, [rsi+48h]
0x18003e820  mov     [rbp+0C0h+var_E0], rax
0x18003e824  mov     eax, [rsi+20h]
0x18003e827  mov     dword ptr [rbp+0C0h+var_128+4], eax
0x18003e82a  mov     rax, [rsi+18h]
0x18003e82e  mov     [rbp+0C0h+var_D8], rax
0x18003e832  mov     eax, [rsi]
0x18003e834  mov     dword ptr [rbp+0C0h+var_120], eax
0x18003e837  mov     rax, [rsi+80h]
0x18003e83e  mov     [rbp+0C0h+var_D0], rax
0x18003e842  mov     eax, [rsi+40h]
0x18003e845  mov     dword ptr [rbp+0C0h+var_130], eax
0x18003e848  mov     rax, [rsi+38h]
0x18003e84c  mov     [rbp+0C0h+var_C8], rax
0x18003e850  mov     eax, [rsi+8]
0x18003e853  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x18003e856  mov     eax, 1000000h
0x18003e85b  mov     [rbp+0C0h+var_C0], rax
0x18003e85f  mov     [rbp+0C0h+var_118], rax
0x18003e863  lea     rax, [rbp+0C0h+var_110]
0x18003e867  mov     [rsp+200h+var_150], rax; __int64
0x18003e86f  lea     rax, [rbp+0C0h+var_140]
0x18003e873  mov     [rsp+200h+var_158], rax; __int64
0x18003e87b  lea     rax, [rbp+0C0h+var_108]
0x18003e87f  mov     [rsp+200h+var_160], rax; __int64
0x18003e887  lea     rax, [rbp+0C0h+var_100]
0x18003e88b  mov     [rsp+200h+var_168], rax; __int64
0x18003e893  lea     rax, [rbp+0C0h+var_F8]
0x18003e897  mov     [rsp+200h+var_170], rax; __int64
0x18003e89f  lea     rax, [rbp+0C0h+var_130+4]
0x18003e8a3  mov     [rsp+200h+var_178], rax; __int64
0x18003e8ab  lea     rax, [rbp+0C0h+var_F0]
0x18003e8af  mov     [rsp+200h+var_180], rax; __int64
0x18003e8b7  lea     rax, [rbp+0C0h+var_E8]
0x18003e8bb  mov     [rsp+200h+var_188], rax; __int64
0x18003e8c0  lea     rax, [rbp+0C0h+var_128]
0x18003e8c4  mov     [rsp+200h+var_190], rax; __int64
0x18003e8c9  lea     rax, [rbp+0C0h+var_E0]
0x18003e8cd  mov     [rsp+200h+var_198], rax; __int64
0x18003e8d2  lea     rax, [rbp+0C0h+var_128+4]
0x18003e8d6  mov     [rsp+200h+var_1A0], rax; __int64
0x18003e8db  lea     rax, [rbp+0C0h+var_D8]
0x18003e8df  mov     [rsp+200h+var_1A8], rax; __int64
0x18003e8e4  lea     rax, [rbp+0C0h+var_120]
0x18003e8e8  mov     [rsp+200h+var_1B0], rax; __int64
0x18003e8ed  lea     rax, [rbp+0C0h+var_D0]
0x18003e8f1  mov     [rsp+200h+var_1B8], rax; __int64
0x18003e8f6  lea     rax, [rbp+0C0h+var_130]
0x18003e8fa  mov     [rsp+200h+var_1C0], rax; __int64
0x18003e8ff  lea     rax, [rbp+0C0h+var_C8]
0x18003e903  mov     [rsp+200h+var_1C8], rax; __int64
0x18003e908  lea     rax, [rbp+0C0h+SRWLock]
0x18003e90c  mov     [rsp+200h+var_1D0], rax; __int64
0x18003e911  lea     rax, [rbp+0C0h+var_C0]
0x18003e915  mov     [rsp+200h+var_1D8], rax; __int64
0x18003e91a  lea     rax, [rbp+0C0h+var_118]
0x18003e91e  mov     qword ptr [rsp+200h+var_1E0], rax; __int64
0x18003e923  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x18003e928  jmp     loc_18003EA62
0x18003e92d  mov     rbx, r14
0x18003e930  lea     rdx, [rbp+0C0h+SRWLock]
0x18003e934  mov     [rbp+0C0h+SRWLock], r12
0x18003e938  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003e93d  mov     rax, [rbx]
0x18003e940  mov     ebx, 2
0x18003e945  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x18003e949  mov     [rax], ebx
0x18003e94b  test    rcx, rcx
0x18003e94e  jz      short loc_18003E956
0x18003e950  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e956  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003e95b  mov     rsi, rax
0x18003e95e  cmp     dword ptr [rax], 5
0x18003e961  jbe     loc_18003EA62
0x18003e967  mov     rdx, 400000000000h
0x18003e971  test    [rax+10h], rdx
0x18003e975  jz      loc_18003EA62
0x18003e97b  mov     rcx, [rax+18h]
0x18003e97f  and     rcx, rdx
0x18003e982  cmp     rcx, [rax+18h]
0x18003e986  jnz     loc_18003EA62
0x18003e98c  mov     al, [rdi+148h]
0x18003e992  mov     r15, [r15]
0x18003e995  mov     byte ptr [rbp+0C0h+var_140], al
0x18003e998  call    cs:__imp_GetCurrentThreadId
0x18003e99e  mov     r8, [r14]
0x18003e9a1  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x18003e9a4  mov     [rbp+0C0h+var_38], 12h
0x18003e9af  mov     [rbp+0C0h+var_48], 1
0x18003e9b7  mov     eax, [r8+48h]
0x18003e9bb  mov     dword ptr [rbp+0C0h+var_130], eax
0x18003e9be  mov     eax, 1000000h
0x18003e9c3  mov     [rbp+0C0h+var_118], rax
0x18003e9c7  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18003e9ce  mov     [rbp+0C0h+var_40], rax
0x18003e9d5  lea     rax, [rbp+0C0h+var_140]
0x18003e9d9  mov     [rbp+0C0h+var_50], rax
0x18003e9dd  test    r15, r15
0x18003e9e0  jz      short loc_18003E9F9
0x18003e9e2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003e9e6  inc     rbx
0x18003e9e9  cmp     [r15+rbx*2], r12w
0x18003e9ee  jnz     short loc_18003E9E6
0x18003e9f0  lea     ebx, ds:2[rbx*2]
0x18003e9f7  jmp     short loc_18003EA00
0x18003e9f9  lea     r15, S2
0x18003ea00  lea     rax, [rbp+0C0h+SRWLock]
0x18003ea04  mov     [rbp+0C0h+var_60], r15
0x18003ea08  mov     [rbp+0C0h+var_70], rax
0x18003ea0c  lea     rdx, unk_180091688; int
0x18003ea13  lea     rax, [rbp+0C0h+var_130]
0x18003ea17  mov     [rbp+0C0h+var_58], ebx
0x18003ea1a  mov     [rbp+0C0h+var_80], rax
0x18003ea1e  add     r8, 8; int
0x18003ea22  lea     rax, [rbp+0C0h+var_118]
0x18003ea26  mov     [rbp+0C0h+var_54], r12d
0x18003ea2a  mov     [rbp+0C0h+var_90], rax
0x18003ea2e  xor     r9d, r9d; int
0x18003ea31  lea     rax, [rbp+0C0h+var_B0]
0x18003ea35  mov     [rbp+0C0h+var_68], 4
0x18003ea3d  mov     [rsp+200h+var_1D8], rax; PEVENT_DATA_DESCRIPTOR
0x18003ea42  mov     rcx, rsi; int
0x18003ea45  mov     [rsp+200h+var_1E0], 8; ULONG
0x18003ea4d  mov     [rbp+0C0h+var_78], 4
0x18003ea55  mov     [rbp+0C0h+var_88], 8
0x18003ea5d  call    _tlgWriteTransfer_EventWriteTransfer
0x18003ea62  mov     rcx, rdi
0x18003ea65  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18003ea6a  mov     rcx, [rbp+0C0h+var_30]
0x18003ea71  xor     rcx, rsp; StackCookie
0x18003ea74  call    __security_check_cookie
0x18003ea79  lea     r11, [rsp+200h+var_20]
0x18003ea81  mov     rbx, [r11+38h]
0x18003ea85  mov     rsi, [r11+40h]
0x18003ea89  mov     rsp, r11
0x18003ea8c  pop     r15
0x18003ea8e  pop     r14
0x18003ea90  pop     r12
0x18003ea92  pop     rdi
0x18003ea93  pop     rbp
0x18003ea94  retn
```
