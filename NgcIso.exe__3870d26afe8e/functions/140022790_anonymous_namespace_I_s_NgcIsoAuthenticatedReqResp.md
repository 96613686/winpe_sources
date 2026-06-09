# _anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp

- ea: `0x140022790`
- end: `0x14002390f`
- name: `_anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp`
- size: `4479`
- prototype: ``
- caller_count: `0`
- callee_count: `62`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003338`
- `0x140009be0`
- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b678`
- `0x14000cbe4`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x14000f914`
- `0x14000fabc`
- `0x14000fb24`
- `0x14000fc48`
- `0x1400104f0`
- `0x1400104fc`
- `0x140015fa8`
- `0x140016eb8`
- `0x140017adc`
- `0x14001850c`
- `0x140018884`
- `0x1400188c4`
- `0x140018cc4`
- `0x140018e04`
- `0x14001909c`
- `0x14001963c`
- `0x14001a894`
- `0x14001a9cc`
- `0x14001ad5c`
- `0x14001b2e8`
- `0x14001b50c`
- `0x14001b5fc`
- `0x14001b6e4`
- `0x14001c4ec`
- `0x14001cec0`
- `0x14001d19c`
- `0x14001d1f4`
- `0x14001dc88`
- `0x14001de18`
- `0x14001df58`
- `0x14001e8cc`
- `0x14001e944`
- `0x14001ec0c`
- `0x140020604`
- `0x140021ec4`
- `0x140022790`
- `0x14002a5e0`
- `0x14002a6b0`
- `0x14002bdcc`
- `0x14002c068`
- `0x140038254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400229d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140022fd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002347e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400229d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140022fd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002347e`
- `bcrypt!BCryptGenRandom` at `0x140023017`
- `bcrypt!BCryptGenRandom` at `0x14002327c`
- `bcrypt!BCryptGenRandom` at `0x140023017`
- `bcrypt!BCryptGenRandom` at `0x14002327c`

## string_xrefs

- `0x1400228a1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400228fb`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022a3e`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022ab1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022bde`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022c3b`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022c8c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022dec`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140022f67`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002302d`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400230e0`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140023290`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140023342`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002350c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140023607`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400236e1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400237ce`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        VsmUtils *a7,
        int a8,
        __int64 a9,
        _DWORD *a10,
        _QWORD *a11,
        __int64 a12,
        _DWORD *a13)
{
  NgcIsoContainerImpl *v15; // r14
  int v16; // eax
  unsigned int v17; // ebx
  _QWORD *v18; // rax
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v20; // rdi
  __int64 v21; // rsi
  RTL_SRWLOCK *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  char v25; // al
  _QWORD *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rax
  _QWORD *v32; // r8
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  unsigned __int64 v35; // r9
  int v36; // eax
  int v37; // r9d
  __int64 v38; // r9
  __int64 v39; // rdx
  __int16 v40; // cx
  int v41; // esi
  int v42; // edi
  int v43; // r14d
  int v44; // r15d
  int v45; // eax
  VsmUtils *v46; // rbx
  _DWORD *v47; // r9
  __int64 v48; // rdx
  _QWORD *v49; // rax
  VsmUtils *v50; // rax
  NTSTATUS v51; // eax
  unsigned __int64 v52; // rbx
  unsigned __int64 v53; // rbx
  CounterStore *v54; // rax
  int v55; // eax
  CounterStore *v56; // rax
  int v57; // eax
  _QWORD *v58; // rcx
  CounterStore *v59; // rax
  NTSTATUS v60; // eax
  CounterStore *v61; // rax
  int v62; // eax
  __int128 v63; // xmm6
  int OwnerId; // eax
  void *v65; // rcx
  char v66; // di
  unsigned int v67; // ebx
  int v68; // edi
  int v69; // esi
  __int64 v70; // rax
  int v71; // edi
  __int64 v72; // rcx
  __int64 v73; // rbx
  int v74; // eax
  int v75; // eax
  int PublicKey; // eax
  RTL_SRWLOCK *v77; // rax
  int v78; // eax
  void *v79; // rax
  void *v80; // rbx
  _QWORD *v82; // rax
  unsigned __int8 *v83; // [rsp+28h] [rbp-E0h]
  int v84; // [rsp+28h] [rbp-E0h]
  int v85; // [rsp+28h] [rbp-E0h]
  unsigned __int8 *v86; // [rsp+28h] [rbp-E0h]
  int v87; // [rsp+28h] [rbp-E0h]
  int v88; // [rsp+28h] [rbp-E0h]
  unsigned __int8 *v89; // [rsp+38h] [rbp-D0h]
  unsigned __int8 *v90; // [rsp+38h] [rbp-D0h]
  unsigned int v91; // [rsp+40h] [rbp-C8h]
  unsigned int v92; // [rsp+40h] [rbp-C8h]
  unsigned __int8 *v93; // [rsp+58h] [rbp-B0h] BYREF
  VsmUtils *v94; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 v95[4]; // [rsp+68h] [rbp-A0h] BYREF
  NgcIsoContainerImpl *v96; // [rsp+70h] [rbp-98h] BYREF
  std::_Ref_count_base *v97; // [rsp+78h] [rbp-90h]
  _QWORD *v98; // [rsp+80h] [rbp-88h] BYREF
  struct _GUID v99; // [rsp+88h] [rbp-80h] BYREF
  __int64 v100; // [rsp+98h] [rbp-70h]
  __int128 v101; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v102; // [rsp+B8h] [rbp-50h]
  __int128 v103; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-38h]
  unsigned int v105[4]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v106; // [rsp+E8h] [rbp-20h]
  UCHAR pbBuffer[8]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v108[3]; // [rsp+F8h] [rbp-10h] BYREF
  void *Buf2[2]; // [rsp+110h] [rbp+8h] BYREF
  _QWORD *v110; // [rsp+120h] [rbp+18h]
  void *Src[2]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v112; // [rsp+138h] [rbp+30h]
  void *v113[2]; // [rsp+140h] [rbp+38h] BYREF
  __int64 v114; // [rsp+150h] [rbp+48h]
  _QWORD *v115; // [rsp+158h] [rbp+50h]
  _DWORD *v116; // [rsp+160h] [rbp+58h]
  char v117[8]; // [rsp+168h] [rbp+60h] BYREF
  int v118; // [rsp+170h] [rbp+68h]
  _QWORD v119[4]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v120; // [rsp+198h] [rbp+90h]
  UCHAR v121[16]; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 Buf1; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v123; // [rsp+1C8h] [rbp+C0h]
  _QWORD *v124; // [rsp+1F0h] [rbp+E8h]
  _BYTE v125[64]; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _GUID v126; // [rsp+238h] [rbp+130h] BYREF
  _QWORD v127[2]; // [rsp+248h] [rbp+140h] BYREF
  unsigned __int64 v128; // [rsp+258h] [rbp+150h]
  unsigned __int64 v129; // [rsp+260h] [rbp+158h]
  _BYTE v130[96]; // [rsp+268h] [rbp+160h] BYREF
  unsigned int v131; // [rsp+2C8h] [rbp+1C0h]
  int v132; // [rsp+2CCh] [rbp+1C4h]
  int v133; // [rsp+2D0h] [rbp+1C8h]
  _BYTE v134[112]; // [rsp+358h] [rbp+250h] BYREF
  char v135[112]; // [rsp+3C8h] [rbp+2C0h] BYREF
  __int64 v136; // [rsp+438h] [rbp+330h]
  __int64 v137; // [rsp+440h] [rbp+338h]
  _QWORD v138[42]; // [rsp+468h] [rbp+360h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+610h] [rbp+508h]

  *(_QWORD *)pbBuffer = a3;
  LODWORD(v93) = a8;
  v116 = a10;
  v115 = a11;
  *(_QWORD *)v95 = a12;
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v138);
  v138[0] = &LogProvider::NgcIsoAuthenticatedReqResp::`vftable';
  LogProvider::NgcIsoAuthenticatedReqResp::StartActivity((LogProvider::NgcIsoAuthenticatedReqResp *)v138);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(&v96, a2);
  v101 = 0;
  v102 = 0;
  BYTE4(v93) = 0;
  v15 = v96;
  v16 = (*(__int64 (__fastcall **)(NgcIsoContainerImpl *, _QWORD, __int64, __int128 *))(*(_QWORD *)v96 + 32LL))(
          v96,
          a4,
          a5,
          &v101);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x779,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v16,
      (int)&v93 + 4);
    goto LABEL_129;
  }
  **(_DWORD **)v95 = BYTE4(v93) == 1;
  *a13 = 0;
  Properties::FromCbor<Properties::TpmKeyMaterial>(v125, &v101);
  if ( !Properties::SoftwareKeyMaterial::IsValid((Properties::SoftwareKeyMaterial *)v125) )
  {
    v17 = -2146893814;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8009000ALL,
      (int)&v93 + 4);
LABEL_128:
    Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v125);
LABEL_129:
    std::vector<unsigned char>::_Tidy(&v101);
    if ( v97 )
      std::_Ref_count_base::_Decref(v97);
LABEL_131:
    LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp((LogProvider::NgcIsoAuthenticatedReqResp *)v138);
    return v17;
  }
  v18 = v127;
  if ( v129 > 7 )
    v18 = (_QWORD *)v127[0];
  v98 = v18;
  LogProvider::NgcIsoAuthenticatedReqResp::KeyName<unsigned short const *>(v138, &v98);
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v20 = *ThreadLocalStoragePointer;
  if ( dword_14009DD30 > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&dword_14009DD30);
    if ( dword_14009DD30 == -1 )
    {
      v82 = operator new(0x78u);
      *v82 = v82;
      v82[1] = v82;
      v82[2] = v82;
      *((_WORD *)v82 + 12) = 257;
      qword_14009DD40 = v82;
      atexit(_anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::_dynamic_atexit_destructor_for__retryRequests__);
      Init_thread_footer(&dword_14009DD30);
    }
  }
  *(_OWORD *)v105 = 0;
  v106 = 0;
  v98 = 0;
  NgcReqResp::Request::Request((NgcReqResp::Request *)v117);
  v21 = a9 + (unsigned int)v93;
  std::vector<unsigned char>::vector<unsigned char>(v108, a9, v21);
  v22 = (RTL_SRWLOCK *)ClientAuth::Instance();
  v17 = ClientAuth::InternalDecryptRequest(v22, (__int64)v105);
  std::vector<unsigned char>::_Tidy(v108);
  if ( v17 == -2146893809 )
  {
    AcquireSRWLockExclusive(&stru_14009D888);
    v94 = (VsmUtils *)&stru_14009D888;
    std::vector<unsigned char>::vector<unsigned char>(v108, a9, v21);
    std::_Tree_std::_Tmap_traits_std::vector_unsigned_char_std::allocator_unsigned_char______anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest_std::less_std::vector_unsigned_char_std::allocator_unsigned_char______std::allocator_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest____0___::_Find_lower_bound_std::vector_unsigned_char_std::allocator_unsigned_char_____(
      v23,
      Buf2,
      v108);
    v25 = std::_Tree_std::_Tmap_traits_std::vector_unsigned_char_std::allocator_unsigned_char______anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest_std::less_std::vector_unsigned_char_std::allocator_unsigned_char______std::allocator_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest____0___::_Lower_bound_duplicate_std::vector_unsigned_char_std::allocator_unsigned_char_____(
            v24,
            v110,
            v108);
    v26 = qword_14009DD40;
    if ( v25 )
      v26 = v110;
    std::vector<unsigned char>::_Tidy(v108);
    if ( v26 == qword_14009DD40 )
    {
      v17 = -2146893809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)0x8009000FLL,
        (int)v83);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v94);
LABEL_127:
      NgcReqResp::Request::~Request((NgcReqResp::Request *)v117);
      std::vector<unsigned char>::_Tidy(v105);
      goto LABEL_128;
    }
    NgcReqResp::Request::operator=(v117, v26 + 7);
    v98 = (_QWORD *)v26[14];
    v27 = std::_Tree_val_std::_Tree_simple_types_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest_____::_Extract(
            &qword_14009DD40,
            v26);
    std::_Tree_node_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest__void___::_Freenode_std::allocator_std::_Tree_node_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest__void_______(
      v28,
      v27);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v94);
    v29 = v98;
  }
  else
  {
    if ( (v17 & 0x80000000) != 0 )
    {
      v30 = 1953;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)v17,
        (int)v83);
      goto LABEL_127;
    }
    v31 = NgcReqResp::Request::FromVector(&Buf1, v105);
    NgcReqResp::Request::operator=(v117, v31);
    NgcReqResp::Request::~Request((NgcReqResp::Request *)&Buf1);
    v29 = v98;
  }
  LODWORD(v93) = v118;
  LogProvider::NgcIsoAuthenticatedReqResp::Operation<unsigned int>(v138, &v93);
  v32 = v119;
  if ( v119[3] > 7u )
    v32 = (_QWORD *)v119[0];
  v33 = v127;
  if ( v129 > 7 )
    v33 = (_QWORD *)v127[0];
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v33, v128, v32, v119[2]) )
  {
    v17 = -2146893819;
    v30 = 1957;
    goto LABEL_16;
  }
  if ( a6 != 80 )
  {
    v17 = -2147024809;
    v30 = 1959;
    goto LABEL_16;
  }
  v103 = 0;
  v104 = 0;
  switch ( v118 )
  {
    case 1:
      *(_QWORD *)v95 = 0;
      LODWORD(v93) = 0;
      PublicKey = VsmUtils::GetPublicKey(
                    a7,
                    (struct VsmUtils::Vtl0KeyBlob *)L"ECCPUBLICBLOB",
                    v95,
                    &v93,
                    (unsigned int *)v83);
      v17 = PublicKey;
      if ( PublicKey < 0 )
      {
        v35 = (unsigned int)PublicKey;
        v34 = 1969;
        goto LABEL_37;
      }
      std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v103, *(_QWORD *)v95, (unsigned int)v93);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v95);
      break;
    case 2:
      v94 = 0;
      v71 = NgcIsoContainerImpl::TpmSecretAgreement(
              v15,
              *(unsigned __int64 *)pbBuffer,
              v131,
              (struct Properties::TpmKeyMaterial *)v125,
              0x50u,
              (const unsigned __int8 *)a7,
              *(const unsigned __int8 **)v120,
              *(_DWORD *)(v120 + 8) - (unsigned int)*(_QWORD *)v120,
              0,
              (unsigned __int64 *)&v94);
      if ( v71 == -2146893778 )
      {
        AcquireSRWLockExclusive(&stru_14009D888);
        *(_QWORD *)v95 = &stru_14009D888;
        NgcReqResp::Request::Request(&Buf1, v117);
        v124 = v29;
        std::vector<unsigned char>::vector<unsigned char>(v108, a9, v21);
        v73 = *(_QWORD *)std::map_std::vector_unsigned_char_std::allocator_unsigned_char______anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest_std::less_std::vector_unsigned_char_std::allocator_unsigned_char______std::allocator_std::pair_std::vector_unsigned_char_std::allocator_unsigned_char____const____anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_2_::RetryRequest_____::_Try_emplace_std::vector_unsigned_char_std::allocator_unsigned_char_____(
                           v72,
                           &v99,
                           v108);
        NgcReqResp::Request::operator=(v73 + 56, &Buf1);
        *(_QWORD *)(v73 + 112) = v124;
        std::vector<unsigned char>::_Tidy(v108);
        NgcReqResp::Request::~Request((NgcReqResp::Request *)&Buf1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v95);
      }
      else if ( v71 >= 0 )
      {
        LODWORD(v93) = 0;
        LODWORD(v89) = 0;
        LODWORD(v86) = 0;
        v74 = VsmUtils::DeriveKey(
                v94,
                (unsigned __int64)L"TRUNCATE",
                0,
                0,
                v86,
                (unsigned int)&v93,
                (unsigned int *)v89,
                v91);
        v17 = v74;
        if ( v74 < 0 )
        {
          v35 = (unsigned int)v74;
          v34 = 2004;
          goto LABEL_37;
        }
        std::vector<unsigned char>::vector<unsigned char>(Buf2, (unsigned int)v93);
        LODWORD(v90) = 0;
        LODWORD(v83) = LODWORD(Buf2[1]) - LODWORD(Buf2[0]);
        v75 = VsmUtils::DeriveKey(
                v94,
                (unsigned __int64)L"TRUNCATE",
                0,
                (struct _BCryptBufferDesc *)Buf2[0],
                v83,
                (unsigned int)&v93,
                (unsigned int *)v90,
                v92);
        v17 = v75;
        if ( v75 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7DE,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
            (const char *)(unsigned int)v75,
            v87);
          v65 = Buf2;
          goto LABEL_125;
        }
        std::vector<unsigned char>::operator=(&v103, Buf2);
        v58 = Buf2;
LABEL_113:
        std::vector<unsigned char>::_Tidy(v58);
        break;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7CA,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v71,
        (int)v86);
      std::vector<unsigned char>::_Tidy(&v103);
      NgcReqResp::Request::~Request((NgcReqResp::Request *)v117);
      std::vector<unsigned char>::_Tidy(v105);
      Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v125);
      std::vector<unsigned char>::_Tidy(&v101);
      if ( v97 )
        std::_Ref_count_base::_Decref(v97);
      v17 = v71;
      goto LABEL_131;
    case 3:
      v67 = v131;
      v68 = v132;
      v69 = v133;
      std::vector<unsigned char>::vector<unsigned char>(&v99, 12);
      v70 = *(_QWORD *)&v99.Data1;
      **(_DWORD **)&v99.Data1 = v67;
      *(_DWORD *)(v70 + 4) = v68;
      *(_DWORD *)(v70 + 8) = v69;
      std::vector<unsigned char>::operator=(&v103, &v99);
LABEL_101:
      v58 = &v99;
      goto LABEL_113;
    case 4:
      v99 = 0;
      v100 = 0;
      OwnerId = ClientAuth::GetOwnerId(v130, &v99);
      v17 = OwnerId;
      if ( OwnerId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F3,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)(unsigned int)OwnerId,
          (int)v83);
        v65 = &v99;
LABEL_125:
        std::vector<unsigned char>::_Tidy(v65);
        goto LABEL_126;
      }
      Buf1 = *(_OWORD *)((char *)v15 + 28);
      v123 = *(_OWORD *)((char *)v15 + 44);
      if ( *(_QWORD *)v99.Data4 - *(_QWORD *)&v99.Data1 != 32
        || (v66 = 1, memcmp_0(&Buf1, *(const void **)&v99.Data1, 0x20u)) )
      {
        v66 = 0;
      }
      std::vector<unsigned char>::vector<unsigned char>(v108, 1);
      *(_BYTE *)v108[0] = v66;
      std::vector<unsigned char>::operator=(&v103, v108);
      std::vector<unsigned char>::_Tidy(v108);
      goto LABEL_101;
    case 5:
      v94 = 0;
      v99 = 0;
      if ( memcmp_0(&v126, &v99, 0x10u) )
      {
        v59 = CounterStore::Instance();
        v99 = v126;
        if ( (unsigned int)CounterStore::QueryCounter(v59, &v99, (unsigned __int64 *)&v94) != -2146893807 )
        {
          v17 = -2146893809;
          v34 = 2055;
          goto LABEL_36;
        }
      }
      *(_OWORD *)v121 = 0;
      v60 = BCryptGenRandom(0, v121, 0x10u, 2u);
      if ( v60 < 0 )
      {
        v17 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x80B,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
                (const char *)(unsigned int)v60,
                (int)v83);
        goto LABEL_126;
      }
      v61 = CounterStore::Instance();
      v99 = *(struct _GUID *)v121;
      v62 = CounterStore::AddCounter(v61, &v99);
      v17 = v62;
      if ( v62 < 0 )
      {
        v35 = (unsigned int)v62;
        v34 = 2060;
        goto LABEL_37;
      }
      v63 = *(_OWORD *)v121;
      *(_OWORD *)(*(_QWORD *)std::map<std::vector<unsigned char>,_GUID>::_Try_emplace<std::vector<unsigned char> const &,>(
                               (char *)v15 + 192,
                               &v99,
                               v130)
                + 56LL) = v63;
      **(_DWORD **)v95 = 1;
      goto LABEL_93;
    case 6:
      *(_QWORD *)v95 = 0;
      v56 = CounterStore::Instance();
      v99 = v126;
      v57 = CounterStore::QueryCounter(v56, &v99, (unsigned __int64 *)v95);
      v17 = v57;
      if ( v57 < 0 )
      {
        v35 = (unsigned int)v57;
        v34 = 2073;
        goto LABEL_37;
      }
      std::vector<unsigned char>::vector<unsigned char>(v108, 8);
      *(_QWORD *)v108[0] = *(_QWORD *)v95;
      std::vector<unsigned char>::operator=(&v103, v108);
      v58 = v108;
      goto LABEL_113;
    case 7:
      v99 = 0;
      if ( !memcmp_0(&v126, &v99, 0x10u) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x822,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)0x80090011LL,
          (int)v83);
        std::vector<unsigned char>::_Tidy(&v103);
        NgcReqResp::Request::~Request((NgcReqResp::Request *)v117);
        std::vector<unsigned char>::_Tidy(v105);
        Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v125);
        std::vector<unsigned char>::_Tidy(&v101);
        if ( v97 )
          std::_Ref_count_base::_Decref(v97);
        v17 = -2146893807;
        goto LABEL_131;
      }
      v54 = CounterStore::Instance();
      v99 = v126;
      v55 = CounterStore::IncrementCounter(v54, &v99);
      v17 = v55;
      if ( v55 < 0 )
      {
        v35 = (unsigned int)v55;
        v34 = 2083;
        goto LABEL_37;
      }
LABEL_93:
      *a13 = 1;
      break;
    case 8:
      if ( dword_14009DD50 > *(_DWORD *)(v20 + 4) )
      {
        Init_thread_header(&dword_14009DD50);
        if ( dword_14009DD50 == -1 )
        {
          std::map<std::vector<unsigned char>,unsigned __int64>::map<std::vector<unsigned char>,unsigned __int64>(&qword_14009DD58);
          atexit(_anonymous_namespace_::I_s_NgcIsoAuthenticatedReqResp_::_160_::_dynamic_atexit_destructor_for__ephemeralCountersMap__);
          Init_thread_footer(&dword_14009DD50);
        }
      }
      AcquireSRWLockExclusive(&stru_14009D880);
      *(_QWORD *)v95 = &stru_14009D880;
      std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,unsigned __int64,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,unsigned __int64>>,0>>::find(
        &qword_14009DD58,
        &v94,
        v130);
      v50 = v94;
      if ( v94 == qword_14009DD58 )
      {
        *(_QWORD *)pbBuffer = 0;
        v51 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
        v17 = v51;
        if ( v51 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x834,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
            (const char *)(unsigned int)v51,
            (int)v83);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v95);
          goto LABEL_126;
        }
        v52 = *(_QWORD *)pbBuffer;
        *(_QWORD *)(*(_QWORD *)std::map<std::vector<unsigned char>,unsigned __int64>::_Try_emplace<std::vector<unsigned char> const &,>(
                                 &qword_14009DD58,
                                 &v99,
                                 v130)
                  + 56LL) = v52;
        v53 = *(_QWORD *)pbBuffer;
      }
      else
      {
        ++*((_QWORD *)v94 + 7);
        v53 = *((_QWORD *)v50 + 7);
      }
      std::vector<unsigned char>::vector<unsigned char>(v108, 8);
      *(_QWORD *)v108[0] = v53;
      std::vector<unsigned char>::operator=(&v103, v108);
      std::vector<unsigned char>::_Tidy(v108);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v95);
      break;
    case 9:
      if ( !(unsigned __int8)VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_UserBindingForEnclaves>>(0) )
      {
        v17 = -2147467263;
        v34 = 2119;
        goto LABEL_36;
      }
      Properties::FromCbor<Properties::SoftwareKeyMaterial>(v134, &v101);
      if ( v136 == v137 )
      {
        v17 = -2146893821;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84D,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)0x80090003LL,
          (int)v83);
LABEL_42:
        Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v134);
        goto LABEL_126;
      }
      *(_OWORD *)Buf2 = 0;
      v110 = 0;
      v36 = ClientAuth::GetOwnerId(v135, Buf2);
      v17 = v36;
      if ( v36 < 0 )
      {
        v38 = (unsigned int)v36;
        v39 = 2129;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)v38,
          (int)v83);
LABEL_46:
        std::vector<unsigned char>::_Tidy(Buf2);
        goto LABEL_42;
      }
      Buf1 = *(_OWORD *)((char *)v15 + 28);
      v123 = *(_OWORD *)((char *)v15 + 44);
      if ( *(_DWORD *)g_logProvider > 4u )
      {
        v40 = -1;
        if ( (unsigned int)(LODWORD(Buf2[1]) - LODWORD(Buf2[0])) <= 0xFFFF )
          v40 = LOWORD(Buf2[1]) - LOWORD(Buf2[0]);
        *(void **)v121 = Buf2[0];
        *(_WORD *)&v121[8] = v40;
        *(_QWORD *)&v99.Data1 = &Buf1;
        strcpy((char *)v99.Data4, " ");
        v94 = (VsmUtils *)((char *)Buf2[1] - (char *)Buf2[0]);
        *(_QWORD *)pbBuffer = 32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
          g_logProvider,
          (unsigned int)byte_1400871E1,
          g_logProvider,
          v37,
          (__int64)pbBuffer,
          (__int64)&v94,
          (__int64)&v99,
          (__int64)v121);
      }
      if ( (void *)((char *)Buf2[1] - (char *)Buf2[0]) != (void *)32 || (v41 = 1, memcmp_0(&Buf1, Buf2[0], 0x20u)) )
        v41 = 0;
      if ( v131 == 1 )
      {
        v42 = 0;
      }
      else
      {
        if ( v131 != 2 )
        {
          v17 = -2147024809;
          v38 = 2147942487LL;
          v39 = 2164;
          goto LABEL_45;
        }
        v42 = 1;
      }
      *(_OWORD *)Src = 0;
      v112 = 0;
      v43 = v132;
      v44 = v133;
      v94 = 0;
      LODWORD(v93) = 0;
      v45 = VsmUtils::GetPublicKey(
              a7,
              (struct VsmUtils::Vtl0KeyBlob *)L"ECCPUBLICBLOB",
              (const unsigned __int16 *)&v94,
              &v93,
              (unsigned int *)v83);
      v17 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x880,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)(unsigned int)v45,
          v84);
LABEL_60:
        std::vector<unsigned char>::_Tidy(Src);
        goto LABEL_46;
      }
      v46 = v94;
      *(_QWORD *)v95 = 0;
      std::vector<unsigned char>::vector<unsigned char>(v108, v95, &v96);
      std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(Src, v108[0], v108[1] - v108[0]);
      std::vector<unsigned char>::insert<unsigned char *,0>(
        (unsigned int)Src,
        (unsigned int)pbBuffer,
        Src[1],
        (_DWORD)v46,
        (__int64)v46 + (unsigned int)v93);
      std::vector<unsigned char>::vector<unsigned char>(&v99, (char *)Src[1] - (char *)Src[0] + 544);
      v47 = *(_DWORD **)&v99.Data1;
      **(_DWORD **)&v99.Data1 = 544;
      v47[1] = v41;
      v47[2] = v42;
      v47[3] = v43;
      v47[4] = v44;
      v47[5] = v128;
      if ( v128 >= 0x100 )
      {
        v17 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89F,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)0x80070057LL,
          v85);
        std::vector<unsigned char>::_Tidy(&v99);
        std::vector<unsigned char>::_Tidy(v108);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v94);
        goto LABEL_60;
      }
      v48 = 0;
      if ( (_DWORD)v128 )
      {
        do
        {
          v49 = v127;
          if ( v129 > 7 )
            v49 = (_QWORD *)v127[0];
          *((_WORD *)v47 + v48 + 12) = *((_WORD *)v49 + v48);
          v48 = (unsigned int)(v48 + 1);
        }
        while ( (unsigned int)v48 < v47[5] );
      }
      v47[134] = LODWORD(Src[1]) - LODWORD(Src[0]);
      memcpy_0(v47 + 135, Src[0], (char *)Src[1] - (char *)Src[0]);
      std::vector<unsigned char>::operator=(&v103, &v99);
      std::vector<unsigned char>::_Tidy(&v99);
      std::vector<unsigned char>::_Tidy(v108);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v94);
      std::vector<unsigned char>::_Tidy(Src);
      std::vector<unsigned char>::_Tidy(Buf2);
      Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v134);
      break;
    default:
      v17 = -2146893814;
      v34 = 2220;
LABEL_36:
      v35 = v17;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)v35,
        (int)v83);
LABEL_126:
      std::vector<unsigned char>::_Tidy(&v103);
      goto LABEL_127;
  }
  *(_OWORD *)v113 = 0;
  v114 = 0;
  v77 = (RTL_SRWLOCK *)ClientAuth::Instance();
  v78 = ClientAuth::InternalEncryptResponse(v77, (__int64)v113);
  v17 = v78;
  if ( v78 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v78,
      v88);
LABEL_124:
    v65 = v113;
    goto LABEL_125;
  }
  v79 = MIDL_user_allocate((char *)v113[1] - (char *)v113[0]);
  v80 = v79;
  v98 = v79;
  if ( !v79 )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8007000ELL,
      v88);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v98);
    goto LABEL_124;
  }
  memcpy_0(v79, v113[0], (char *)v113[1] - (char *)v113[0]);
  v98 = 0;
  *v115 = v80;
  *v116 = LODWORD(v113[1]) - LODWORD(v113[0]);
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v138, 0);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v98);
  std::vector<unsigned char>::_Tidy(v113);
  std::vector<unsigned char>::_Tidy(&v103);
  NgcReqResp::Request::~Request((NgcReqResp::Request *)v117);
  std::vector<unsigned char>::_Tidy(v105);
  Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v125);
  std::vector<unsigned char>::_Tidy(&v101);
  if ( v97 )
    std::_Ref_count_base::_Decref(v97);
  LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp((LogProvider::NgcIsoAuthenticatedReqResp *)v138);
  return 0;
}

```

## disassembly

```asm
0x140022790  mov     rax, rsp
0x140022793  mov     [rax+8], rbx
0x140022797  push    rbp
0x140022798  push    rsi
0x140022799  push    rdi
0x14002279a  push    r12
0x14002279c  push    r13
0x14002279e  push    r14
0x1400227a0  push    r15
0x1400227a2  lea     rbp, [rax-508h]
0x1400227a9  sub     rsp, 5D0h
0x1400227b0  movaps  xmmword ptr [rax-48h], xmm6
0x1400227b4  mov     rax, cs:__security_cookie
0x1400227bb  xor     rax, rsp
0x1400227be  mov     [rbp+500h+var_50], rax
0x1400227c5  mov     esi, r9d
0x1400227c8  mov     qword ptr [rbp+500h+pbBuffer], r8
0x1400227cc  mov     rbx, rdx
0x1400227cf  mov     rdi, [rbp+500h+arg_20]
0x1400227d6  mov     r13, [rbp+500h+arg_30]
0x1400227dd  mov     eax, [rbp+500h+arg_38]
0x1400227e3  mov     dword ptr [rsp+600h+var_5B0], eax
0x1400227e7  mov     r12, [rbp+500h+arg_40]
0x1400227ee  mov     rax, [rbp+500h+arg_48]
0x1400227f5  mov     [rbp+500h+var_4A8], rax
0x1400227f9  mov     rax, [rbp+500h+arg_50]
0x140022800  mov     [rbp+500h+var_4B0], rax
0x140022804  mov     rax, [rbp+500h+arg_58]
0x14002280b  mov     qword ptr [rsp+600h+var_5A0], rax
0x140022810  mov     r15, [rbp+500h+arg_60]
0x140022817  lea     rdx, aNgcisoauthenti_0; "NgcIsoAuthenticatedReqResp"
0x14002281e  lea     rcx, [rbp+500h+var_1A0]; struct wil::details::IFailureCallback *
0x140022825  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14002282a  lea     rax, ??_7NgcIsoAuthenticatedReqResp@LogProvider@@6B@; const LogProvider::NgcIsoAuthenticatedReqResp::`vftable'
0x140022831  mov     [rbp+500h+var_1A0], rax
0x140022838  lea     rcx, [rbp+500h+var_1A0]; this
0x14002283f  call    ?StartActivity@NgcIsoAuthenticatedReqResp@LogProvider@@QEAAXXZ; LogProvider::NgcIsoAuthenticatedReqResp::StartActivity(void)
0x140022844  nop
0x140022845  mov     rdx, rbx
0x140022848  lea     rcx, [rsp+600h+var_598]
0x14002284d  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x140022852  nop
0x140022853  xorps   xmm0, xmm0
0x140022856  movdqu  [rbp+500h+var_560], xmm0
0x14002285b  mov     [rbp+500h+var_550], 0
0x140022863  mov     byte ptr [rsp+600h+var_5B0+4], 0
0x140022868  mov     r14, [rsp+600h+var_598]
0x14002286d  mov     rax, [r14]
0x140022870  lea     rcx, [rsp+600h+var_5B0+4]
0x140022875  mov     [rsp+600h+var_5E0], rcx; int
0x14002287a  lea     r9, [rbp+500h+var_560]
0x14002287e  mov     r8, rdi
0x140022881  mov     edx, esi
0x140022883  mov     rcx, r14
0x140022886  mov     rax, [rax+20h]
0x14002288a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002288f  mov     ebx, eax
0x140022891  xor     esi, esi
0x140022893  test    eax, eax
0x140022895  jns     short loc_1400228B7
0x140022897  mov     rcx, [rbp+508h]; this
0x14002289e  mov     r9d, eax; char *
0x1400228a1  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400228a8  mov     edx, 779h; void *
0x1400228ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400228b2  jmp     loc_14002381F
0x1400228b7  mov     eax, esi
0x1400228b9  cmp     byte ptr [rsp+600h+var_5B0+4], 1
0x1400228be  setz    al
0x1400228c1  mov     rcx, qword ptr [rsp+600h+var_5A0]
0x1400228c6  mov     [rcx], eax
0x1400228c8  mov     [r15], esi
0x1400228cb  lea     rdx, [rbp+500h+var_560]
0x1400228cf  lea     rcx, [rbp+500h+var_410]
0x1400228d6  call    ??$FromCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AUTpmKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::TpmKeyMaterial>(std::vector<uchar> const &)
0x1400228db  nop
0x1400228dc  lea     rcx, [rbp+500h+var_410]; this
0x1400228e3  call    ?IsValid@SoftwareKeyMaterial@Properties@@QEBA_NXZ; Properties::SoftwareKeyMaterial::IsValid(void)
0x1400228e8  test    al, al
0x1400228ea  jnz     short loc_140022911
0x1400228ec  mov     rcx, [rbp+508h]; this
0x1400228f3  mov     ebx, 8009000Ah
0x1400228f8  mov     r9d, ebx; char *
0x1400228fb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022902  mov     edx, 77Fh; void *
0x140022907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002290c  jmp     loc_140023812
0x140022911  lea     rax, [rbp+500h+var_3C0]
0x140022918  cmp     [rbp+500h+var_3A8], 7
0x140022920  cmova   rax, [rbp+500h+var_3C0]
0x140022928  mov     [rsp+600h+var_588], rax
0x14002292d  lea     rdx, [rsp+600h+var_588]
0x140022932  lea     rcx, [rbp+500h+var_1A0]
0x140022939  call    ??$KeyName@PEBG@NgcIsoAuthenticatedReqResp@LogProvider@@QEAAX$$QEAPEBG@Z; LogProvider::NgcIsoAuthenticatedReqResp::KeyName<ushort const *>(ushort const * &&)
0x14002293e  mov     ecx, 4
0x140022943  mov     rax, gs:58h
0x14002294c  mov     rdi, [rax]
0x14002294f  mov     eax, [rcx+rdi]
0x140022952  cmp     cs:dword_14009DD30, eax
0x140022958  jg      loc_1400238B5
0x14002295e  xorps   xmm0, xmm0
0x140022961  movdqu  xmmword ptr [rbp+500h+var_530], xmm0
0x140022966  mov     [rbp+500h+var_520], rsi
0x14002296a  mov     [rsp+600h+var_588], rsi
0x14002296f  lea     rcx, [rbp+500h+var_4A0]; this
0x140022973  call    ??0Request@NgcReqResp@@QEAA@XZ; NgcReqResp::Request::Request(void)
0x140022978  nop
0x140022979  mov     esi, dword ptr [rsp+600h+var_5B0]
0x14002297d  add     rsi, r12
0x140022980  mov     r8, rsi
0x140022983  mov     rdx, r12
0x140022986  lea     rcx, [rbp+500h+var_510]
0x14002298a  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<uchar> const &)
0x14002298f  nop
0x140022990  call    ?Instance@ClientAuth@@CAAEAV1@XZ; ClientAuth::Instance(void)
0x140022995  lea     rcx, [rbp+500h+var_530]
0x140022999  mov     [rsp+600h+var_5E0], rcx; unsigned int *
0x14002299e  lea     r9, [rsp+600h+var_588]
0x1400229a3  lea     r8, [rbp+500h+var_510]
0x1400229a7  lea     rdx, [rbp+500h+var_3A0]
0x1400229ae  mov     rcx, rax; SRWLock
0x1400229b1  call    ?InternalDecryptRequest@ClientAuth@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@0PEA_KAEAV23@@Z; ClientAuth::InternalDecryptRequest(std::vector<uchar> const &,std::vector<uchar> const &,unsigned __int64 *,std::vector<uchar> &)
0x1400229b6  mov     ebx, eax
0x1400229b8  lea     rcx, [rbp+500h+var_510]
0x1400229bc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400229c1  cmp     ebx, 8009000Fh
0x1400229c7  jnz     loc_140022A9E
0x1400229cd  lea     rcx, stru_14009D888; SRWLock
0x1400229d4  call    cs:__imp_AcquireSRWLockExclusive
0x1400229da  lea     rax, stru_14009D888
0x1400229e1  mov     [rsp+600h+var_5A8], rax
0x1400229e6  mov     r8, rsi
0x1400229e9  mov     rdx, r12
0x1400229ec  lea     rcx, [rbp+500h+var_510]
0x1400229f0  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<uchar> const &)
0x1400229f5  lea     r8, [rbp+500h+var_510]
0x1400229f9  lea     rdx, [rbp+500h+Buf2]
0x1400229fd  call    std___Tree_std___Tmap_traits_std__vector_unsigned_char_std__allocator_unsigned_char______anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest_std__less_std__vector_unsigned_char_std__allocator_unsigned_char______std__allocator_std__pair_std__vector_unsigned_char_std__allocator_unsigned_char____const____anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest____0______Find_lower_bound_std__vector_unsigned_char_std__allocator_unsigned_char_____
0x140022a02  lea     r8, [rbp+500h+var_510]
0x140022a06  mov     rdx, [rbp+500h+var_4E8]
0x140022a0a  call    std___Tree_std___Tmap_traits_std__vector_unsigned_char_std__allocator_unsigned_char______anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest_std__less_std__vector_unsigned_char_std__allocator_unsigned_char______std__allocator_std__pair_std__vector_unsigned_char_std__allocator_unsigned_char____const____anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest____0______Lower_bound_duplicate_std__vector_unsigned_char_std__allocator_unsigned_char_____
0x140022a0f  mov     rbx, cs:qword_14009DD40
0x140022a16  test    al, al
0x140022a18  cmovnz  rbx, [rbp+500h+var_4E8]
0x140022a1d  lea     rcx, [rbp+500h+var_510]
0x140022a21  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140022a26  cmp     rbx, cs:qword_14009DD40
0x140022a2d  jnz     short loc_140022A5F
0x140022a2f  mov     rcx, [rbp+508h]; this
0x140022a36  mov     ebx, 8009000Fh
0x140022a3b  mov     r9d, ebx; char *
0x140022a3e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022a45  mov     edx, 79Ch; void *
0x140022a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022a4f  nop
0x140022a50  lea     rcx, [rsp+600h+var_5A8]
0x140022a55  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140022a5a  jmp     loc_1400237FE
0x140022a5f  lea     rdx, [rbx+38h]
0x140022a63  lea     rcx, [rbp+500h+var_4A0]
0x140022a67  call    ??4Request@NgcReqResp@@QEAAAEAU01@$$QEAU01@@Z; NgcReqResp::Request::operator=(NgcReqResp::Request &&)
0x140022a6c  mov     r9, [rbx+70h]
0x140022a70  mov     [rsp+600h+var_588], r9
0x140022a75  mov     rdx, rbx
0x140022a78  lea     rcx, qword_14009DD40
0x140022a7f  call    std___Tree_val_std___Tree_simple_types_std__pair_std__vector_unsigned_char_std__allocator_unsigned_char____const____anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest________Extract
0x140022a84  mov     rdx, rax
0x140022a87  call    std___Tree_node_std__pair_std__vector_unsigned_char_std__allocator_unsigned_char____const____anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest__void______Freenode_std__allocator_std___Tree_node_std__pair_std__vector_unsigned_char_std__allocator_unsigned_char____const____anonymous_namespace___I_s_NgcIsoAuthenticatedReqResp____2___RetryRequest__void_______
0x140022a8c  nop
0x140022a8d  lea     rcx, [rsp+600h+var_5A8]
0x140022a92  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140022a97  mov     rbx, [rsp+600h+var_588]
0x140022a9c  jmp     short loc_140022AF4
0x140022a9e  test    ebx, ebx
0x140022aa0  jns     short loc_140022AC2
0x140022aa2  mov     edx, 7A1h; void *
0x140022aa7  mov     rcx, [rbp+508h]; this
0x140022aae  mov     r9d, ebx; char *
0x140022ab1  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022ab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022abd  jmp     loc_1400237FE
0x140022ac2  lea     rdx, [rbp+500h+var_530]
0x140022ac6  lea     rcx, [rbp+500h+Buf1]
0x140022acd  call    ?FromVector@Request@NgcReqResp@@SA?AU12@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcReqResp::Request::FromVector(std::vector<uchar> const &)
0x140022ad2  mov     rdx, rax
0x140022ad5  lea     rcx, [rbp+500h+var_4A0]
0x140022ad9  call    ??4Request@NgcReqResp@@QEAAAEAU01@$$QEAU01@@Z; NgcReqResp::Request::operator=(NgcReqResp::Request &&)
0x140022ade  lea     rcx, [rbp+500h+Buf1]; this
0x140022ae5  call    ??1Request@NgcReqResp@@QEAA@XZ; NgcReqResp::Request::~Request(void)
0x140022aea  mov     rbx, [rsp+600h+var_588]
0x140022aef  mov     [rsp+600h+var_588], rbx
0x140022af4  mov     eax, [rbp+500h+var_498]
0x140022af7  mov     dword ptr [rsp+600h+var_5B0], eax
0x140022afb  lea     rdx, [rsp+600h+var_5B0]
0x140022b00  lea     rcx, [rbp+500h+var_1A0]
0x140022b07  call    ??$Operation@I@NgcIsoAuthenticatedReqResp@LogProvider@@QEAAX$$QEAI@Z; LogProvider::NgcIsoAuthenticatedReqResp::Operation<uint>(uint &&)
0x140022b0c  lea     r8, [rbp+500h+var_490]
0x140022b10  cmp     [rbp+500h+var_478], 7
0x140022b18  cmova   r8, [rbp+500h+var_490]
0x140022b1d  lea     rcx, [rbp+500h+var_3C0]
0x140022b24  cmp     [rbp+500h+var_3A8], 7
0x140022b2c  cmova   rcx, [rbp+500h+var_3C0]
0x140022b34  mov     r9, [rbp+500h+var_480]
0x140022b3b  mov     rdx, [rbp+500h+var_3B0]
0x140022b42  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140022b47  xor     ecx, ecx
0x140022b49  test    al, al
0x140022b4b  jnz     short loc_140022B5C
0x140022b4d  mov     ebx, 80090005h
0x140022b52  mov     edx, 7A5h
0x140022b57  jmp     loc_140022AA7
0x140022b5c  cmp     [rbp+500h+arg_28], 50h ; 'P'
0x140022b64  jz      short loc_140022B75
0x140022b66  mov     ebx, 80070057h
0x140022b6b  mov     edx, 7A7h
0x140022b70  jmp     loc_140022AA7
0x140022b75  xorps   xmm0, xmm0
0x140022b78  movdqu  [rbp+500h+var_548], xmm0
0x140022b7d  mov     [rbp+500h+var_538], rcx
0x140022b81  mov     eax, [rbp+500h+var_498]
0x140022b84  sub     eax, 1
0x140022b87  jz      loc_14002363B
0x140022b8d  sub     eax, 1
0x140022b90  jz      loc_140023413
0x140022b96  sub     eax, 1
0x140022b99  jz      loc_1400233D1
0x140022b9f  sub     eax, 1
0x140022ba2  jz      loc_140023315
0x140022ba8  sub     eax, 1
0x140022bab  jz      loc_1400231F6
0x140022bb1  sub     eax, 1
0x140022bb4  jz      loc_14002317E
0x140022bba  sub     eax, 1
0x140022bbd  jz      loc_1400230B5
0x140022bc3  sub     eax, 1
0x140022bc6  jz      loc_140022FAD
0x140022bcc  cmp     eax, 1
0x140022bcf  jz      short loc_140022BF6
0x140022bd1  mov     ebx, 8009000Ah
0x140022bd6  mov     edx, 8ACh; void *
0x140022bdb  mov     r9d, ebx; char *
0x140022bde  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022be5  mov     rcx, [rbp+508h]; this
0x140022bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022bf1  jmp     loc_1400237F4
0x140022bf6  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_UserBindingForEnclaves@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_UserBindingForEnclaves>>(void)
0x140022bfb  test    al, al
0x140022bfd  jnz     short loc_140022C0B
0x140022bff  mov     ebx, 80004001h
0x140022c04  mov     edx, 847h
0x140022c09  jmp     short loc_140022BDB
0x140022c0b  lea     rdx, [rbp+500h+var_560]
0x140022c0f  lea     rcx, [rbp+500h+var_2B0]
0x140022c16  call    ??$FromCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AUSoftwareKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::SoftwareKeyMaterial>(std::vector<uchar> const &)
0x140022c1b  nop
0x140022c1c  mov     rax, [rbp+500h+var_1C8]
0x140022c23  cmp     [rbp+500h+var_1D0], rax
0x140022c2a  jnz     short loc_140022C5E
0x140022c2c  mov     rcx, [rbp+508h]; this
0x140022c33  mov     ebx, 80090003h
0x140022c38  mov     r9d, ebx; char *
0x140022c3b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022c42  mov     edx, 84Dh; void *
0x140022c47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022c4c  nop
0x140022c4d  lea     rcx, [rbp+500h+var_2B0]; this
0x140022c54  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140022c59  jmp     loc_1400237F4
0x140022c5e  xorps   xmm0, xmm0
0x140022c61  movdqu  xmmword ptr [rbp+500h+Buf2], xmm0
0x140022c66  mov     [rbp+500h+var_4E8], 0
0x140022c6e  lea     rdx, [rbp+500h+Buf2]
0x140022c72  lea     rcx, [rbp+500h+var_240]
0x140022c79  call    ?GetOwnerId@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ClientAuth::GetOwnerId(std::vector<uchar> const &,std::vector<uchar> &)
0x140022c7e  mov     ebx, eax
0x140022c80  test    eax, eax
0x140022c82  jns     short loc_140022CAB
0x140022c84  mov     r9d, eax; char *
0x140022c87  mov     edx, 851h; void *
0x140022c8c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140022c93  mov     rcx, [rbp+508h]; this
0x140022c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022c9f  nop
0x140022ca0  lea     rcx, [rbp+500h+Buf2]
0x140022ca4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140022ca9  jmp     short loc_140022C4D
0x140022cab  movups  xmm0, xmmword ptr [r14+1Ch]
0x140022cb0  movups  [rbp+500h+Buf1], xmm0
0x140022cb7  movups  xmm1, xmmword ptr [r14+2Ch]
0x140022cbc  movups  [rbp+500h+var_440], xmm1
0x140022cc3  mov     r8, cs:g_logProvider
0x140022cca  mov     eax, [r8]
0x140022ccd  mov     ebx, 20h ; ' '
0x140022cd2  cmp     eax, 4
0x140022cd5  jbe     short loc_140022D4B
0x140022cd7  mov     rdx, [rbp+500h+Buf2]
0x140022cdb  mov     rax, [rbp+500h+Buf2+8]
0x140022cdf  sub     rax, rdx
0x140022ce2  mov     ecx, 0FFFFh
0x140022ce7  cmp     eax, ecx
  ... truncated ...
```
