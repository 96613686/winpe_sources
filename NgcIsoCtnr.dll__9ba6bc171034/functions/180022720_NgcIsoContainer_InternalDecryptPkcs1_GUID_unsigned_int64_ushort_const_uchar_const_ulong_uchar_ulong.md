# NgcIsoContainer::InternalDecryptPkcs1(_GUID,unsigned __int64,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180022720`
- end: `0x180022bc5`
- name: `?InternalDecryptPkcs1@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEBEKPEAPEAEPEAK@Z`
- size: `1189`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800019bc`
- `0x1800026b4`
- `0x180007670`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180011174`
- `0x180011c9c`
- `0x180013088`
- `0x1800163e8`
- `0x180018818`
- `0x18001cbe8`
- `0x18001e25c`
- `0x180022720`
- `0x180023a48`
- `0x180026754`
- `0x180027758`
- `0x18002bccc`
- `0x18002bf98`
- `0x1800528c0`
- `0x1800662c8`
- `0x180067b58`
- `0x18006f3cc`
- `0x180070e3c`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800227fb`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x180022acd`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800227fb`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x180022acd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800227f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800227f0`

## string_xrefs

- `0x1800227d3`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180022829`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180022924`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800229bd`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180022b66`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcIsoContainer::InternalDecryptPkcs1(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  int v9; // r12d
  unsigned int v12; // ebx
  clock_t v13; // r13d
  int KeyObject; // eax
  NCRYPT_HANDLE v15; // rsi
  __int64 v16; // rbx
  int v17; // edi
  int v18; // eax
  int v19; // r9d
  int updated; // eax
  void **v21; // r9
  __int64 v22; // rdx
  int TpmKspKeyName; // eax
  __int64 v24; // rdx
  RTL_SRWLOCK *v25; // rdi
  const WCHAR *v26; // rbx
  NCRYPT_PROV_HANDLE *v27; // rax
  __int64 v28; // r9
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rbx
  int v32; // edi
  int ImplementationType; // eax
  int v34; // r9d
  int v35; // edi
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 v38; // r9
  double v39; // xmm0_8
  int v40; // ebx
  int v41; // r8d
  int v42; // r9d
  unsigned int v44; // [rsp+20h] [rbp-E0h]
  _BYTE v45[8]; // [rsp+60h] [rbp-A0h] BYREF
  RTL_SRWLOCK *v46; // [rsp+68h] [rbp-98h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  NgcUtils *v48[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h]
  unsigned int *v50; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int8 *v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v53; // [rsp+A8h] [rbp-58h]
  _OWORD v54[2]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE pbOutput[40]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v56; // [rsp+F8h] [rbp-8h]
  int v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+108h] [rbp+8h]
  __int64 v59; // [rsp+110h] [rbp+10h]
  char v60; // [rsp+118h] [rbp+18h]
  _QWORD v61[42]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v9 = a3;
  v52 = a3;
  v51 = a5;
  v53 = (unsigned __int64)a7;
  v50 = a8;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
  v61[0] = &LogProvider::NgcIsoContainerDecryptPkcs1::`vftable';
  LogProvider::NgcIsoContainerDecryptPkcs1::StartActivity((LogProvider::NgcIsoContainerDecryptPkcs1 *)v61, a4);
  if ( memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x794,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)0x80070057LL,
      v44);
LABEL_35:
    LogProvider::NgcIsoContainerDecryptPkcs1::~NgcIsoContainerDecryptPkcs1((LogProvider::NgcIsoContainerDecryptPkcs1 *)v61);
    return v12;
  }
  AcquireSRWLockShared(this + 2);
  v46 = this + 2;
  v13 = clock();
  hObject = 0;
  KeyObject = NgcIsoContainer::InternalGetKeyObject(
                (NgcIsoContainer *)this,
                a4,
                (struct Properties::UserIdKey **)&hObject);
  v12 = KeyObject;
  if ( KeyObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79D,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)KeyObject,
      v44);
LABEL_34:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
    goto LABEL_35;
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v45[0] = 0;
  v15 = hObject;
  if ( (unsigned int)Properties::Key::GetImplementationType(hObject) != 1 )
  {
    if ( (unsigned int)Properties::Key::GetImplementationType(v15) != 2 )
    {
      v12 = -2147024809;
      v36 = 2147942487LL;
      v22 = 2002;
      goto LABEL_32;
    }
    v54[0] = 0;
    v54[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v54[0]) = 0;
    TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *(_QWORD *)(v15 + 80), v54);
    v12 = TpmKspKeyName;
    if ( TpmKspKeyName >= 0 )
    {
      hObject = 0;
      v25 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
      v27 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v25, *v27, v26, v28, v44, &hObject);
      v12 = TpmKspKeyName;
      if ( TpmKspKeyName >= 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v29 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hObject);
        v12 = v29;
        if ( v29 >= 0 )
        {
          v31 = *(_QWORD *)(v15 + 80);
          v32 = *(_DWORD *)(v15 + 72);
          ImplementationType = Properties::Key::GetImplementationType(v15);
          v29 = NgcIsoTrustlet::Decrypt(
                  (int)this + 136,
                  v52,
                  ImplementationType,
                  v34,
                  v32,
                  v31,
                  80,
                  (__int64)pbOutput,
                  a6,
                  (__int64)v51,
                  (__int64)v48,
                  (__int64)v45);
          v12 = v29;
          if ( v29 >= 0 )
          {
            VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
            std::wstring::_Tidy_deallocate(v54);
            goto LABEL_21;
          }
          v30 = 1998;
        }
        else
        {
          v30 = 1984;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v29,
          v44);
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
LABEL_12:
        std::wstring::_Tidy_deallocate(v54);
LABEL_33:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v48);
        goto LABEL_34;
      }
      v24 = 1981;
    }
    else
    {
      v24 = 1973;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKspKeyName,
      v44);
    goto LABEL_12;
  }
  v16 = *(_QWORD *)(v15 + 80);
  v17 = *(_DWORD *)(v15 + 72);
  v18 = Properties::Key::GetImplementationType(v15);
  updated = NgcIsoTrustlet::Decrypt(
              (int)this + 136,
              v9,
              v18,
              v19,
              v17,
              v16,
              0,
              0,
              a6,
              (__int64)v51,
              (__int64)v48,
              (__int64)v45);
  v12 = updated;
  if ( updated < 0 )
  {
    v22 = 1967;
LABEL_26:
    v36 = (unsigned int)updated;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)v36,
      v44);
    goto LABEL_33;
  }
LABEL_21:
  if ( v45[0] )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v46,
      0);
    updated = NgcIsoContainer::InternalUpdateKey((NgcIsoContainer *)this, a4, (struct Properties::UserIdKey *)v15);
    v12 = updated;
    if ( updated < 0 )
    {
      v22 = 2010;
      goto LABEL_26;
    }
  }
  v35 = LODWORD(v48[1]) - LODWORD(v48[0]);
  updated = NgcUtils::CoMemAllocCopy(v48[0], (unsigned int)(LODWORD(v48[1]) - LODWORD(v48[0])), (_QWORD *)v53, v21);
  v12 = updated;
  if ( updated < 0 )
  {
    v22 = 2016;
    goto LABEL_26;
  }
  *v50 = v35;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v61);
  v39 = (double)(clock() - v13);
  v40 = g_logProvider;
  if ( *(_DWORD *)g_logProvider > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(g_logProvider, 0x400000000000LL, v37, v38) )
    {
      v50 = *(unsigned int **)&v39;
      LODWORD(hObject) = Properties::Key::GetImplementationType(v15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v40,
        (unsigned int)byte_1800AB799,
        v41,
        v42,
        (__int64)&hObject,
        (__int64)&v50);
    }
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v48);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
  LogProvider::NgcIsoContainerDecryptPkcs1::~NgcIsoContainerDecryptPkcs1((LogProvider::NgcIsoContainerDecryptPkcs1 *)v61);
  return 0;
}

```

## disassembly

```asm
0x180022720  mov     [rsp-8+arg_8], rbx
0x180022725  push    rbp
0x180022726  push    rsi
0x180022727  push    rdi
0x180022728  push    r12
0x18002272a  push    r13
0x18002272c  push    r14
0x18002272e  push    r15
0x180022730  lea     rbp, [rsp-180h]
0x180022738  sub     rsp, 280h
0x18002273f  mov     rax, cs:__security_cookie
0x180022746  xor     rax, rsp
0x180022749  mov     [rbp+1B0h+var_40], rax
0x180022750  mov     r15, r9
0x180022753  mov     r12, r8
0x180022756  mov     [rbp+1B0h+var_210], r8
0x18002275a  mov     rbx, rdx
0x18002275d  mov     r14, rcx
0x180022760  mov     rax, [rbp+1B0h+arg_20]
0x180022767  mov     [rbp+1B0h+var_218], rax
0x18002276b  mov     rax, [rbp+1B0h+arg_30]
0x180022772  mov     [rbp+1B0h+var_208], rax
0x180022776  mov     rax, [rbp+1B0h+arg_38]
0x18002277d  mov     [rbp+1B0h+var_220], rax
0x180022781  lea     rdx, aNgcisocontaine_27; "NgcIsoContainerDecryptPkcs1"
0x180022788  lea     rcx, [rbp+1B0h+var_190]; struct wil::details::IFailureCallback *
0x18002278c  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180022791  lea     rax, ??_7NgcIsoContainerDecryptPkcs1@LogProvider@@6B@; const LogProvider::NgcIsoContainerDecryptPkcs1::`vftable'
0x180022798  mov     [rbp+1B0h+var_190], rax
0x18002279c  mov     rdx, r15; unsigned __int16 *
0x18002279f  lea     rcx, [rbp+1B0h+var_190]; this
0x1800227a3  call    ?StartActivity@NgcIsoContainerDecryptPkcs1@LogProvider@@QEAAXPEBG@Z; LogProvider::NgcIsoContainerDecryptPkcs1::StartActivity(ushort const *)
0x1800227a8  nop
0x1800227a9  mov     r8d, 10h; Size
0x1800227af  lea     rdx, qword_1800947A8; Buf2
0x1800227b6  mov     rcx, rbx; Buf1
0x1800227b9  call    memcmp_0
0x1800227be  xor     edi, edi
0x1800227c0  test    eax, eax
0x1800227c2  jz      short loc_1800227E9
0x1800227c4  mov     rcx, [rbp+1B8h]; this
0x1800227cb  mov     ebx, 80070057h
0x1800227d0  mov     r9d, ebx; char *
0x1800227d3  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800227da  mov     edx, 794h; void *
0x1800227df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227e4  jmp     loc_180022B90
0x1800227e9  lea     rbx, [r14+10h]
0x1800227ed  mov     rcx, rbx; SRWLock
0x1800227f0  call    cs:__imp_AcquireSRWLockShared
0x1800227f6  mov     [rsp+2B0h+var_248], rbx
0x1800227fb  call    cs:__imp_clock
0x180022801  mov     r13d, eax
0x180022804  mov     [rsp+2B0h+hObject], rdi
0x180022809  lea     r8, [rsp+2B0h+hObject]; struct Properties::UserIdKey **
0x18002280e  mov     rdx, r15; unsigned __int16 *
0x180022811  mov     rcx, r14; this
0x180022814  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x180022819  mov     ebx, eax
0x18002281b  test    eax, eax
0x18002281d  jns     short loc_18002283F
0x18002281f  mov     rcx, [rbp+1B8h]; this
0x180022826  mov     r9d, eax; char *
0x180022829  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180022830  mov     edx, 79Dh; void *
0x180022835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002283a  jmp     loc_180022B85
0x18002283f  xorps   xmm0, xmm0
0x180022842  movdqu  xmmword ptr [rsp+2B0h+var_238], xmm0
0x180022848  mov     [rbp+1B0h+var_228], rdi
0x18002284c  mov     [rsp+2B0h+var_250], dil
0x180022851  mov     rsi, [rsp+2B0h+hObject]
0x180022856  mov     rcx, rsi
0x180022859  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x18002285e  mov     rcx, rsi
0x180022861  cmp     eax, 1
0x180022864  jnz     short loc_1800228DC
0x180022866  mov     rbx, [rsi+50h]
0x18002286a  mov     edi, [rsi+48h]
0x18002286d  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180022872  mov     r8d, [rbp+1B0h+arg_28]
0x180022879  lea     rcx, [r14+88h]
0x180022880  lea     rdx, [rsp+2B0h+var_250]
0x180022885  mov     [rsp+2B0h+var_258], rdx
0x18002288a  lea     rdx, [rsp+2B0h+var_238]
0x18002288f  mov     [rsp+2B0h+var_260], rdx
0x180022894  mov     rdx, [rbp+1B0h+var_218]
0x180022898  mov     [rsp+2B0h+var_268], rdx
0x18002289d  mov     [rsp+2B0h+var_270], r8
0x1800228a2  mov     [rsp+2B0h+var_278], 0
0x1800228ab  mov     [rsp+2B0h+var_280], 0
0x1800228b4  mov     [rsp+2B0h+var_288], rbx
0x1800228b9  mov     dword ptr [rsp+2B0h+var_290], edi
0x1800228bd  mov     r8d, eax
0x1800228c0  mov     rdx, r12
0x1800228c3  call    ?Decrypt@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@KPEBUKeyMaterial@5@1PEBE15PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEA_N@Z; NgcIsoTrustlet::Decrypt(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,ulong,Properties::KeyMaterial const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,bool *)
0x1800228c8  mov     ebx, eax
0x1800228ca  test    eax, eax
0x1800228cc  jns     loc_180022A66
0x1800228d2  mov     edx, 7AFh
0x1800228d7  jmp     loc_180022AB6
0x1800228dc  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x1800228e1  cmp     eax, 2
0x1800228e4  jnz     loc_180022B59
0x1800228ea  xorps   xmm0, xmm0
0x1800228ed  movups  [rbp+1B0h+var_200], xmm0
0x1800228f1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800228f9  movdqu  [rbp+1B0h+var_1F0], xmm1
0x1800228fe  mov     word ptr [rbp+1B0h+var_200], di
0x180022902  lea     r12, [r14+88h]
0x180022909  lea     r8, [rbp+1B0h+var_200]
0x18002290d  mov     rdx, [rsi+50h]
0x180022911  mov     rcx, r12
0x180022914  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x180022919  mov     ebx, eax
0x18002291b  test    eax, eax
0x18002291d  jns     short loc_180022949
0x18002291f  mov     edx, 7B5h; void *
0x180022924  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002292b  mov     r9d, eax; char *
0x18002292e  mov     rcx, [rbp+1B8h]; this
0x180022935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002293a  nop
0x18002293b  lea     rcx, [rbp+1B0h+var_200]
0x18002293f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022944  jmp     loc_180022B7A
0x180022949  mov     [rsp+2B0h+hObject], rdi
0x18002294e  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x180022953  mov     rdi, rax
0x180022956  lea     rcx, [rbp+1B0h+var_200]
0x18002295a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002295f  mov     rbx, rax
0x180022962  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x180022967  lea     rcx, [rsp+2B0h+hObject]
0x18002296c  mov     [rsp+2B0h+var_288], rcx; unsigned __int64 *
0x180022971  mov     r8, rbx; pszKeyName
0x180022974  mov     rdx, [rax]; hProvider
0x180022977  mov     rcx, rdi; SRWLock
0x18002297a  call    ?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)
0x18002297f  mov     ebx, eax
0x180022981  xor     edi, edi
0x180022983  test    eax, eax
0x180022985  jns     short loc_18002298E
0x180022987  mov     edx, 7BDh
0x18002298c  jmp     short loc_180022924
0x18002298e  mov     dword ptr [rbp+1B0h+pbOutput], edi
0x180022991  mov     [rbp+1B0h+var_1B8], rdi
0x180022995  mov     [rbp+1B0h+var_1B0], edi
0x180022998  mov     [rbp+1B0h+var_1A8], rdi
0x18002299c  mov     [rbp+1B0h+var_1A0], rdi
0x1800229a0  mov     [rbp+1B0h+var_198], dil
0x1800229a4  mov     rdx, [rsp+2B0h+hObject]; hObject
0x1800229a9  lea     rcx, [rbp+1B0h+pbOutput]; pbOutput
0x1800229ad  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x1800229b2  mov     ebx, eax
0x1800229b4  test    eax, eax
0x1800229b6  jns     short loc_1800229E2
0x1800229b8  mov     edx, 7C0h; void *
0x1800229bd  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800229c4  mov     r9d, eax; char *
0x1800229c7  mov     rcx, [rbp+1B8h]; this
0x1800229ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800229d3  nop
0x1800229d4  lea     rcx, [rbp+1B0h+pbOutput]; this
0x1800229d8  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x1800229dd  jmp     loc_18002293B
0x1800229e2  mov     rbx, [rsi+50h]
0x1800229e6  mov     edi, [rsi+48h]
0x1800229e9  mov     rcx, rsi
0x1800229ec  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x1800229f1  mov     ecx, [rbp+1B0h+arg_28]
0x1800229f7  lea     rdx, [rsp+2B0h+var_250]
0x1800229fc  mov     [rsp+2B0h+var_258], rdx
0x180022a01  lea     rdx, [rsp+2B0h+var_238]
0x180022a06  mov     [rsp+2B0h+var_260], rdx
0x180022a0b  mov     rdx, [rbp+1B0h+var_218]
0x180022a0f  mov     [rsp+2B0h+var_268], rdx
0x180022a14  mov     [rsp+2B0h+var_270], rcx
0x180022a19  lea     rcx, [rbp+1B0h+pbOutput]
0x180022a1d  mov     [rsp+2B0h+var_278], rcx
0x180022a22  mov     [rsp+2B0h+var_280], 50h ; 'P'
0x180022a2b  mov     [rsp+2B0h+var_288], rbx
0x180022a30  mov     dword ptr [rsp+2B0h+var_290], edi
0x180022a34  mov     r8d, eax
0x180022a37  mov     rdx, [rbp+1B0h+var_210]
0x180022a3b  mov     rcx, r12
0x180022a3e  call    ?Decrypt@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@KPEBUKeyMaterial@5@1PEBE15PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEA_N@Z; NgcIsoTrustlet::Decrypt(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,ulong,Properties::KeyMaterial const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,bool *)
0x180022a43  mov     ebx, eax
0x180022a45  test    eax, eax
0x180022a47  jns     short loc_180022A53
0x180022a49  mov     edx, 7CEh
0x180022a4e  jmp     loc_1800229BD
0x180022a53  lea     rcx, [rbp+1B0h+pbOutput]; this
0x180022a57  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180022a5c  nop
0x180022a5d  lea     rcx, [rbp+1B0h+var_200]
0x180022a61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a66  cmp     [rsp+2B0h+var_250], 0
0x180022a6b  jz      short loc_180022A94
0x180022a6d  xor     edx, edx
0x180022a6f  lea     rcx, [rsp+2B0h+var_248]
0x180022a74  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180022a79  mov     r8, rsi; struct Properties::UserIdKey *
0x180022a7c  mov     rdx, r15; unsigned __int16 *
0x180022a7f  mov     rcx, r14; this
0x180022a82  call    ?InternalUpdateKey@NgcIsoContainer@@AEAAJPEBGPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalUpdateKey(ushort const *,Properties::UserIdKey *)
0x180022a87  mov     ebx, eax
0x180022a89  test    eax, eax
0x180022a8b  jns     short loc_180022A94
0x180022a8d  mov     edx, 7DAh
0x180022a92  jmp     short loc_180022AB6
0x180022a94  mov     eax, dword ptr [rbp+1B0h+var_238+8]
0x180022a97  mov     rcx, [rsp+2B0h+var_238]; this
0x180022a9c  sub     eax, ecx
0x180022a9e  mov     edi, eax
0x180022aa0  mov     edx, eax; SourceSize
0x180022aa2  mov     r8, [rbp+1B0h+var_208]; unsigned __int64
0x180022aa6  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180022aab  mov     ebx, eax
0x180022aad  test    eax, eax
0x180022aaf  jns     short loc_180022ABE
0x180022ab1  mov     edx, 7E0h
0x180022ab6  mov     r9d, eax
0x180022ab9  jmp     loc_180022B66
0x180022abe  mov     rax, [rbp+1B0h+var_220]
0x180022ac2  mov     [rax], edi
0x180022ac4  lea     rcx, [rbp+1B0h+var_190]
0x180022ac8  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022acd  call    cs:__imp_clock
0x180022ad3  sub     eax, r13d
0x180022ad6  movd    xmm0, eax
0x180022ada  cvtdq2pd xmm0, xmm0
0x180022ade  mov     rbx, cs:g_logProvider
0x180022ae5  mov     eax, [rbx]
0x180022ae7  cmp     eax, 5
0x180022aea  jbe     short loc_180022B36
0x180022aec  mov     rdx, 400000000000h
0x180022af6  mov     rcx, rbx
0x180022af9  call    _tlgKeywordOn
0x180022afe  test    al, al
0x180022b00  jz      short loc_180022B36
0x180022b02  movsd   [rbp+1B0h+var_220], xmm0
0x180022b07  mov     rcx, rsi
0x180022b0a  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180022b0f  mov     dword ptr [rsp+2B0h+hObject], eax
0x180022b13  lea     rax, [rbp+1B0h+var_220]
0x180022b17  mov     [rsp+2B0h+var_288], rax
0x180022b1c  lea     rax, [rsp+2B0h+hObject]
0x180022b21  mov     [rsp+2B0h+var_290], rax
0x180022b26  lea     rdx, byte_1800AB799
0x180022b2d  mov     rcx, rbx
0x180022b30  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180022b35  nop
0x180022b36  lea     rcx, [rsp+2B0h+var_238]
0x180022b3b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180022b40  nop
0x180022b41  lea     rcx, [rsp+2B0h+var_248]
0x180022b46  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022b4b  nop
0x180022b4c  lea     rcx, [rbp+1B0h+var_190]; this
0x180022b50  call    ??1NgcIsoContainerDecryptPkcs1@LogProvider@@QEAA@XZ; LogProvider::NgcIsoContainerDecryptPkcs1::~NgcIsoContainerDecryptPkcs1(void)
0x180022b55  xor     eax, eax
0x180022b57  jmp     short loc_180022B9B
0x180022b59  mov     ebx, 80070057h
0x180022b5e  mov     r9d, ebx; char *
0x180022b61  mov     edx, 7D2h; void *
0x180022b66  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180022b6d  mov     rcx, [rbp+1B8h]; this
0x180022b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022b79  nop
0x180022b7a  lea     rcx, [rsp+2B0h+var_238]
0x180022b7f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180022b84  nop
0x180022b85  lea     rcx, [rsp+2B0h+var_248]
0x180022b8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022b8f  nop
0x180022b90  lea     rcx, [rbp+1B0h+var_190]; this
0x180022b94  call    ??1NgcIsoContainerDecryptPkcs1@LogProvider@@QEAA@XZ; LogProvider::NgcIsoContainerDecryptPkcs1::~NgcIsoContainerDecryptPkcs1(void)
0x180022b99  mov     eax, ebx
0x180022b9b  mov     rcx, [rbp+1B0h+var_40]
0x180022ba2  xor     rcx, rsp; StackCookie
0x180022ba5  call    __security_check_cookie
0x180022baa  mov     rbx, [rsp+2B0h+arg_8]
0x180022bb2  add     rsp, 280h
0x180022bb9  pop     r15
0x180022bbb  pop     r14
0x180022bbd  pop     r13
0x180022bbf  pop     r12
0x180022bc1  pop     rdi
0x180022bc2  pop     rsi
0x180022bc3  pop     rbp
0x180022bc4  retn
```
