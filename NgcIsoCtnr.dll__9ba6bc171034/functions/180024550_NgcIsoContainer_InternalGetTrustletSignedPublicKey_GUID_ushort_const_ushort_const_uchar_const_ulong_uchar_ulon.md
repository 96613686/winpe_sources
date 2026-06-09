# NgcIsoContainer::InternalGetTrustletSignedPublicKey(_GUID,ushort const *,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180024550`
- end: `0x180024813`
- name: `?InternalGetTrustletSignedPublicKey@NgcIsoContainer@@AEAAJU_GUID@@PEBG1PEBEKPEAPEAEPEAK@Z`
- size: `707`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007670`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180018818`
- `0x18001cbe8`
- `0x180023a48`
- `0x180024550`
- `0x1800528c0`
- `0x180067b58`
- `0x180067f0c`
- `0x18006f3cc`
- `0x180070e3c`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800245d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800245d4`

## string_xrefs

- `0x1800245b7`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024627`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002467b`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024719`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024778`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcIsoContainer::InternalGetTrustletSignedPublicKey(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  int v8; // r12d
  unsigned int v11; // ebx
  int KeyObject; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  NCRYPT_HANDLE v15; // rbx
  int v16; // esi
  int TpmKspKeyName; // eax
  __int64 v18; // rdx
  RTL_SRWLOCK *v19; // rdi
  const WCHAR *v20; // rbx
  NCRYPT_PROV_HANDLE *v21; // rax
  __int64 v22; // r9
  int v23; // eax
  int v24; // edx
  int TrustletSignedPublicKey; // eax
  void **v26; // r9
  __int64 v27; // rdx
  int v28; // edi
  unsigned int v30; // [rsp+20h] [rbp-C9h]
  int v31; // [rsp+20h] [rbp-C9h]
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-A9h] BYREF
  NgcUtils *v33[2]; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v34; // [rsp+58h] [rbp-91h]
  RTL_SRWLOCK *v35; // [rsp+60h] [rbp-89h] BYREF
  _OWORD v36[2]; // [rsp+68h] [rbp-81h] BYREF
  BYTE pbOutput[40]; // [rsp+90h] [rbp-59h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-31h]
  int v39; // [rsp+C0h] [rbp-29h]
  __int64 v40; // [rsp+C8h] [rbp-21h]
  __int64 v41; // [rsp+D0h] [rbp-19h]
  char v42; // [rsp+D8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  v8 = (int)a4;
  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v35 = this + 2;
    hObject = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject(
                  (NgcIsoContainer *)this,
                  a3,
                  (struct Properties::UserIdKey **)&hObject);
    v11 = KeyObject;
    if ( KeyObject < 0 )
    {
      v13 = (unsigned int)KeyObject;
      v14 = 1633;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)v13,
        v30);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v35);
      return v11;
    }
    v15 = hObject;
    if ( (unsigned int)Properties::Key::GetImplementationType(hObject) != 2 )
    {
      v11 = -2147024809;
      v13 = 2147942487LL;
      v14 = 1636;
      goto LABEL_7;
    }
    v36[0] = 0;
    v36[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v36[0]) = 0;
    v16 = (_DWORD)this + 136;
    TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *(_QWORD *)(v15 + 80), v36);
    v11 = TpmKspKeyName;
    if ( TpmKspKeyName >= 0 )
    {
      hObject = 0;
      v19 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
      v21 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v19, *v21, v20, v22, v30, &hObject);
      v11 = TpmKspKeyName;
      if ( TpmKspKeyName >= 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        v23 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hObject);
        v11 = v23;
        if ( v23 >= 0 )
        {
          *(_OWORD *)v33 = 0;
          v34 = 0;
          TrustletSignedPublicKey = NgcIsoTrustlet::GetTrustletSignedPublicKey(
                                      v16,
                                      v24,
                                      (unsigned int)pbOutput,
                                      v8,
                                      a6,
                                      (__int64)a5,
                                      (__int64)v33);
          v11 = TrustletSignedPublicKey;
          if ( TrustletSignedPublicKey >= 0 )
          {
            v28 = LODWORD(v33[1]) - LODWORD(v33[0]);
            TrustletSignedPublicKey = NgcUtils::CoMemAllocCopy(
                                        v33[0],
                                        (unsigned int)(LODWORD(v33[1]) - LODWORD(v33[0])),
                                        a7,
                                        v26);
            v11 = TrustletSignedPublicKey;
            if ( TrustletSignedPublicKey >= 0 )
            {
              *a8 = v28;
              std::vector<unsigned char>::_Tidy(v33);
              VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
              std::wstring::_Tidy_deallocate(v36);
              v11 = 0;
              goto LABEL_23;
            }
            v27 = 1662;
          }
          else
          {
            v27 = 1659;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)TrustletSignedPublicKey,
            v31);
          std::vector<unsigned char>::_Tidy(v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x66F,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)v23,
            v30);
        }
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
        goto LABEL_11;
      }
      v18 = 1644;
    }
    else
    {
      v18 = 1640;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKspKeyName,
      v30);
LABEL_11:
    std::wstring::_Tidy_deallocate(v36);
    goto LABEL_23;
  }
  v11 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65C,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    v30);
  return v11;
}

```

## disassembly

```asm
0x180024550  mov     [rsp-8+arg_8], rbx
0x180024555  push    rbp
0x180024556  push    rsi
0x180024557  push    rdi
0x180024558  push    r12
0x18002455a  push    r13
0x18002455c  push    r14
0x18002455e  push    r15
0x180024560  lea     rbp, [rsp-7]
0x180024565  sub     rsp, 0F0h
0x18002456c  mov     rax, cs:__security_cookie
0x180024573  xor     rax, rsp
0x180024576  mov     [rbp+37h+var_40], rax
0x18002457a  mov     r12, r9
0x18002457d  mov     rsi, r8
0x180024580  mov     rax, rdx
0x180024583  mov     rdi, rcx
0x180024586  mov     r13, [rbp+37h+arg_20]
0x18002458a  mov     r15, [rbp+37h+arg_30]
0x18002458e  mov     r14, [rbp+37h+arg_38]
0x180024592  mov     r8d, 10h; Size
0x180024598  lea     rdx, qword_1800947A8; Buf2
0x18002459f  mov     rcx, rax; Buf1
0x1800245a2  call    memcmp_0
0x1800245a7  test    eax, eax
0x1800245a9  jz      short loc_1800245CD
0x1800245ab  mov     rcx, [rbp+3Fh]; this
0x1800245af  mov     ebx, 80070057h
0x1800245b4  mov     r9d, ebx; char *
0x1800245b7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800245be  mov     edx, 65Ch; void *
0x1800245c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800245c8  jmp     loc_1800247EA
0x1800245cd  lea     rbx, [rdi+10h]
0x1800245d1  mov     rcx, rbx; SRWLock
0x1800245d4  call    cs:__imp_AcquireSRWLockShared
0x1800245da  mov     [rsp+120h+var_C0], rbx
0x1800245df  mov     [rsp+120h+hObject], 0
0x1800245e8  lea     r8, [rsp+120h+hObject]; struct Properties::UserIdKey **
0x1800245ed  mov     rdx, rsi; unsigned __int16 *
0x1800245f0  mov     rcx, rdi; this
0x1800245f3  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x1800245f8  mov     ebx, eax
0x1800245fa  test    eax, eax
0x1800245fc  jns     short loc_180024608
0x1800245fe  mov     r9d, eax
0x180024601  mov     edx, 661h
0x180024606  jmp     short loc_180024627
0x180024608  mov     rbx, [rsp+120h+hObject]
0x18002460d  mov     rcx, rbx
0x180024610  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180024615  cmp     eax, 2
0x180024618  jz      short loc_18002463C
0x18002461a  mov     ebx, 80070057h
0x18002461f  mov     r9d, ebx; char *
0x180024622  mov     edx, 664h; void *
0x180024627  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002462e  mov     rcx, [rbp+3Fh]; this
0x180024632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024637  jmp     loc_1800247E0
0x18002463c  xorps   xmm0, xmm0
0x18002463f  movups  [rsp+120h+var_B8], xmm0
0x180024644  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002464c  movdqu  [rbp+37h+var_A8], xmm1
0x180024651  xor     eax, eax
0x180024653  mov     word ptr [rsp+120h+var_B8], ax
0x180024658  lea     rsi, [rdi+88h]
0x18002465f  lea     r8, [rsp+120h+var_B8]
0x180024664  mov     rdx, [rbx+50h]
0x180024668  mov     rcx, rsi
0x18002466b  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x180024670  mov     ebx, eax
0x180024672  test    eax, eax
0x180024674  jns     short loc_18002469E
0x180024676  mov     edx, 668h; void *
0x18002467b  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180024682  mov     r9d, eax; char *
0x180024685  mov     rcx, [rbp+3Fh]; this
0x180024689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002468e  nop
0x18002468f  lea     rcx, [rsp+120h+var_B8]
0x180024694  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024699  jmp     loc_1800247E0
0x18002469e  mov     [rsp+120h+hObject], 0
0x1800246a7  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x1800246ac  mov     rdi, rax
0x1800246af  lea     rcx, [rsp+120h+var_B8]
0x1800246b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800246b9  mov     rbx, rax
0x1800246bc  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x1800246c1  lea     rcx, [rsp+120h+hObject]
0x1800246c6  mov     [rsp+120h+var_F8], rcx; unsigned __int64 *
0x1800246cb  mov     r8, rbx; pszKeyName
0x1800246ce  mov     rdx, [rax]; hProvider
0x1800246d1  mov     rcx, rdi; SRWLock
0x1800246d4  call    ?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)
0x1800246d9  mov     ebx, eax
0x1800246db  xor     edi, edi
0x1800246dd  test    eax, eax
0x1800246df  jns     short loc_1800246E8
0x1800246e1  mov     edx, 66Ch
0x1800246e6  jmp     short loc_18002467B
0x1800246e8  mov     dword ptr [rbp+37h+pbOutput], edi
0x1800246eb  mov     [rbp+37h+var_68], rdi
0x1800246ef  mov     [rbp+37h+var_60], edi
0x1800246f2  mov     [rbp+37h+var_58], rdi
0x1800246f6  mov     [rbp+37h+var_50], rdi
0x1800246fa  mov     [rbp+37h+var_48], dil
0x1800246fe  mov     rdx, [rsp+120h+hObject]; hObject
0x180024703  lea     rcx, [rbp+37h+pbOutput]; pbOutput
0x180024707  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x18002470c  mov     ebx, eax
0x18002470e  test    eax, eax
0x180024710  jns     short loc_180024739
0x180024712  mov     rcx, [rbp+3Fh]; this
0x180024716  mov     r9d, eax; char *
0x180024719  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180024720  mov     edx, 66Fh; void *
0x180024725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002472a  nop
0x18002472b  lea     rcx, [rbp+37h+pbOutput]; this
0x18002472f  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180024734  jmp     loc_18002468F
0x180024739  xorps   xmm0, xmm0
0x18002473c  movdqu  xmmword ptr [rsp+120h+var_D8], xmm0
0x180024742  mov     [rsp+120h+var_C8], rdi
0x180024747  mov     eax, [rbp+37h+arg_28]
0x18002474a  lea     rcx, [rsp+120h+var_D8]
0x18002474f  mov     [rsp+120h+var_F0], rcx
0x180024754  mov     [rsp+120h+var_F8], r13
0x180024759  mov     qword ptr [rsp+120h+var_100], rax; int
0x18002475e  mov     r9, r12
0x180024761  lea     r8, [rbp+37h+pbOutput]
0x180024765  mov     rcx, rsi
0x180024768  call    ?GetTrustletSignedPublicKey@NgcIsoTrustlet@@YAJAEBU_GUID@@_KPEBEPEBG12PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoTrustlet::GetTrustletSignedPublicKey(_GUID const &,unsigned __int64,uchar const *,ushort const *,unsigned __int64,uchar const *,std::vector<uchar> *)
0x18002476d  mov     ebx, eax
0x18002476f  test    eax, eax
0x180024771  jns     short loc_180024798
0x180024773  mov     edx, 67Bh; void *
0x180024778  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002477f  mov     r9d, eax; char *
0x180024782  mov     rcx, [rbp+3Fh]; this
0x180024786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002478b  nop
0x18002478c  lea     rcx, [rsp+120h+var_D8]
0x180024791  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180024796  jmp     short loc_18002472B
0x180024798  mov     eax, dword ptr [rsp+120h+var_D8+8]
0x18002479c  mov     rcx, [rsp+120h+var_D8]; this
0x1800247a1  sub     eax, ecx
0x1800247a3  mov     edi, eax
0x1800247a5  mov     edx, eax; SourceSize
0x1800247a7  mov     r8, r15; unsigned __int64
0x1800247aa  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x1800247af  mov     ebx, eax
0x1800247b1  test    eax, eax
0x1800247b3  jns     short loc_1800247BC
0x1800247b5  mov     edx, 67Eh
0x1800247ba  jmp     short loc_180024778
0x1800247bc  mov     [r14], edi
0x1800247bf  lea     rcx, [rsp+120h+var_D8]
0x1800247c4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800247c9  nop
0x1800247ca  lea     rcx, [rbp+37h+pbOutput]; this
0x1800247ce  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x1800247d3  nop
0x1800247d4  lea     rcx, [rsp+120h+var_B8]
0x1800247d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800247de  xor     ebx, ebx
0x1800247e0  lea     rcx, [rsp+120h+var_C0]
0x1800247e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800247ea  mov     eax, ebx
0x1800247ec  mov     rcx, [rbp+37h+var_40]
0x1800247f0  xor     rcx, rsp; StackCookie
0x1800247f3  call    __security_check_cookie
0x1800247f8  mov     rbx, [rsp+120h+arg_8]
0x180024800  add     rsp, 0F0h
0x180024807  pop     r15
0x180024809  pop     r14
0x18002480b  pop     r13
0x18002480d  pop     r12
0x18002480f  pop     rdi
0x180024810  pop     rsi
0x180024811  pop     rbp
0x180024812  retn
```
