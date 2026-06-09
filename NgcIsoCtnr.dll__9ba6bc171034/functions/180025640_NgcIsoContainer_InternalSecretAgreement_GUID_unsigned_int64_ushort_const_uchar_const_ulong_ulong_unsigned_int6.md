# NgcIsoContainer::InternalSecretAgreement(_GUID,unsigned __int64,ushort const *,uchar const *,ulong,ulong,unsigned __int64 *)

- ea: `0x180025640`
- end: `0x180025a0b`
- name: `?InternalSecretAgreement@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEBEKKPEA_K@Z`
- size: `971`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007670`
- `0x180007d4c`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180011174`
- `0x180011c9c`
- `0x180018818`
- `0x18001cbe8`
- `0x18001e0fc`
- `0x180023a48`
- `0x180025640`
- `0x180026754`
- `0x18002bf98`
- `0x1800528c0`
- `0x180067b58`
- `0x180069164`
- `0x18006f3cc`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800256d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800256d4`

## string_xrefs

- `0x1800256b7`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180025701`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002580a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800258a0`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800259bc`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcIsoContainer::InternalSecretAgreement(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int64 *a8)
{
  unsigned int v11; // ebx
  int KeyObject; // eax
  _DWORD *v13; // r14
  NCRYPT_HANDLE v14; // rsi
  __int64 v15; // rbx
  unsigned int v16; // edi
  unsigned int ImplementationType; // eax
  int v18; // eax
  __int64 v19; // rdx
  int TpmKspKeyName; // eax
  __int64 v21; // rdx
  RTL_SRWLOCK *v22; // rdi
  const WCHAR *v23; // rbx
  NCRYPT_PROV_HANDLE *v24; // rax
  __int64 v25; // r9
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rbx
  unsigned int v29; // edi
  unsigned int v30; // eax
  __int64 v31; // r9
  unsigned int v33; // [rsp+20h] [rbp-E0h]
  _DWORD *v34; // [rsp+68h] [rbp-98h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v36[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h]
  unsigned __int64 *v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  BYTE pbOutput[40]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+100h] [rbp+0h]
  char v47; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v37 = a3;
  v36[1] = a5;
  v38 = a8;
  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v36[0] = this + 2;
    hObject = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject(
                  (NgcIsoContainer *)this,
                  a4,
                  (struct Properties::UserIdKey **)&hObject);
    v11 = KeyObject;
    if ( KeyObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x805,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)KeyObject,
        v33);
LABEL_25:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v36);
      return v11;
    }
    v13 = operator new(0x10u);
    *(_OWORD *)v13 = 0;
    v34 = v13;
    v14 = hObject;
    if ( (unsigned int)Properties::Key::GetImplementationType(hObject) == 1 )
    {
      v15 = *(_QWORD *)(v14 + 80);
      v16 = *(_DWORD *)(v14 + 72);
      ImplementationType = Properties::Key::GetImplementationType(v14);
      v33 = v15;
      v18 = NgcIsoTrustlet::SecretAgreement(&this[17], a3, ImplementationType, v16);
      v11 = v18;
      if ( v18 < 0 )
      {
        v19 = 2071;
        v31 = (unsigned int)v18;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)v31,
          v33);
        goto LABEL_24;
      }
LABEL_21:
      v13[2] = Properties::Key::GetImplementationType(v14);
      v34 = 0;
      *v38 = (unsigned __int64)v13;
      std::unique_ptr<NgcIsoSecretHandle>::~unique_ptr<NgcIsoSecretHandle>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v36);
      return 0;
    }
    if ( (unsigned int)Properties::Key::GetImplementationType(v14) != 2 )
    {
      v11 = -2147024809;
      v31 = 2147942487LL;
      v19 = 2106;
      goto LABEL_23;
    }
    v39 = 0;
    v40 = 0;
    v41 = 7;
    LOWORD(v39) = 0;
    TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *(_QWORD *)(v14 + 80), &v39);
    v11 = TpmKspKeyName;
    if ( TpmKspKeyName >= 0 )
    {
      hObject = 0;
      v22 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v39);
      v24 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v22, *v24, v23, v25, v33, &hObject);
      v11 = TpmKspKeyName;
      if ( TpmKspKeyName >= 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v26 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hObject);
        v11 = v26;
        if ( v26 >= 0 )
        {
          v28 = *(_QWORD *)(v14 + 80);
          v29 = *(_DWORD *)(v14 + 72);
          v30 = Properties::Key::GetImplementationType(v14);
          v33 = v28;
          v26 = NgcIsoTrustlet::SecretAgreement(&this[17], v37, v30, v29);
          v11 = v26;
          if ( v26 >= 0 )
          {
            VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
            std::wstring::_Tidy_deallocate(&v39);
            goto LABEL_21;
          }
          v27 = 2102;
        }
        else
        {
          v27 = 2088;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v26,
          v33);
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
LABEL_12:
        std::wstring::_Tidy_deallocate(&v39);
LABEL_24:
        std::unique_ptr<NgcIsoSecretHandle>::~unique_ptr<NgcIsoSecretHandle>(&v34);
        goto LABEL_25;
      }
      v21 = 2085;
    }
    else
    {
      v21 = 2077;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKspKeyName,
      v33);
    goto LABEL_12;
  }
  v11 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x800,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    v33);
  return v11;
}

```

## disassembly

```asm
0x180025640  mov     [rsp-8+arg_8], rbx
0x180025645  push    rbp
0x180025646  push    rsi
0x180025647  push    rdi
0x180025648  push    r12
0x18002564a  push    r13
0x18002564c  push    r14
0x18002564e  push    r15
0x180025650  lea     rbp, [rsp-20h]
0x180025655  sub     rsp, 120h
0x18002565c  mov     rax, cs:__security_cookie
0x180025663  xor     rax, rsp
0x180025666  mov     [rbp+50h+var_40], rax
0x18002566a  mov     r13, r9
0x18002566d  mov     r12, r8
0x180025670  mov     [rbp+50h+var_C8], r8
0x180025674  mov     rax, rdx
0x180025677  mov     r15, rcx
0x18002567a  mov     rcx, [rbp+50h+arg_20]
0x180025681  mov     [rbp+50h+var_D0], rcx
0x180025685  mov     rcx, [rbp+50h+arg_38]
0x18002568c  mov     [rbp+50h+var_C0], rcx
0x180025690  xor     edi, edi
0x180025692  lea     esi, [rdi+10h]
0x180025695  mov     r8d, esi; Size
0x180025698  lea     rdx, qword_1800947A8; Buf2
0x18002569f  mov     rcx, rax; Buf1
0x1800256a2  call    memcmp_0
0x1800256a7  test    eax, eax
0x1800256a9  jz      short loc_1800256CD
0x1800256ab  mov     rcx, [rbp+58h]; this
0x1800256af  mov     ebx, 80070057h
0x1800256b4  mov     r9d, ebx; char *
0x1800256b7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800256be  mov     edx, 800h; void *
0x1800256c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256c8  jmp     loc_1800259E2
0x1800256cd  lea     rbx, [r15+10h]
0x1800256d1  mov     rcx, rbx; SRWLock
0x1800256d4  call    cs:__imp_AcquireSRWLockShared
0x1800256da  mov     [rsp+150h+var_D8], rbx
0x1800256df  mov     [rsp+150h+hObject], rdi
0x1800256e4  lea     r8, [rsp+150h+hObject]; struct Properties::UserIdKey **
0x1800256e9  mov     rdx, r13; unsigned __int16 *
0x1800256ec  mov     rcx, r15; this
0x1800256ef  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x1800256f4  mov     ebx, eax
0x1800256f6  test    eax, eax
0x1800256f8  jns     short loc_180025717
0x1800256fa  mov     rcx, [rbp+58h]; this
0x1800256fe  mov     r9d, eax; char *
0x180025701  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180025708  mov     edx, 805h; void *
0x18002570d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025712  jmp     loc_1800259D8
0x180025717  mov     rcx, rsi; Size
0x18002571a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002571f  mov     r14, rax
0x180025722  xorps   xmm0, xmm0
0x180025725  movups  xmmword ptr [rax], xmm0
0x180025728  mov     [rsp+150h+var_E8], rax
0x18002572d  mov     [rsp+150h+var_F0], dil
0x180025732  mov     rsi, [rsp+150h+hObject]
0x180025737  mov     rcx, rsi
0x18002573a  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x18002573f  mov     rcx, rsi
0x180025742  cmp     eax, 1
0x180025745  jnz     short loc_1800257C3
0x180025747  mov     rbx, [rsi+50h]
0x18002574b  mov     edi, [rsi+48h]
0x18002574e  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180025753  lea     rcx, [r15+88h]
0x18002575a  lea     rdx, [rsp+150h+var_F0]
0x18002575f  mov     [rsp+150h+var_F8], rdx
0x180025764  mov     [rsp+150h+var_100], r14
0x180025769  mov     r8d, [rbp+50h+arg_30]
0x180025770  mov     [rsp+150h+var_108], r8d
0x180025775  mov     r8d, [rbp+50h+arg_28]
0x18002577c  mov     [rsp+150h+var_110], r8d
0x180025781  mov     rdx, [rbp+50h+var_D0]
0x180025785  mov     [rsp+150h+var_118], rdx
0x18002578a  mov     [rsp+150h+var_120], 0
0x180025793  mov     [rsp+150h+var_128], 0
0x18002579c  mov     [rsp+150h+var_130], rbx
0x1800257a1  mov     r9d, edi
0x1800257a4  mov     r8d, eax
0x1800257a7  mov     rdx, r12
0x1800257aa  call    ?SecretAgreement@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@KPEBUKeyMaterial@5@1PEBE4KKPEA_KPEA_N@Z; NgcIsoTrustlet::SecretAgreement(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,ulong,Properties::KeyMaterial const *,unsigned __int64,uchar const *,uchar const *,ulong,ulong,unsigned __int64 *,bool *)
0x1800257af  mov     ebx, eax
0x1800257b1  test    eax, eax
0x1800257b3  jns     loc_180025949
0x1800257b9  mov     edx, 817h
0x1800257be  jmp     loc_180025975
0x1800257c3  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x1800257c8  cmp     eax, 2
0x1800257cb  jnz     loc_1800259AF
0x1800257d1  xorps   xmm0, xmm0
0x1800257d4  movups  [rbp+50h+var_B8], xmm0
0x1800257d8  mov     [rbp+50h+var_A8], rdi
0x1800257dc  mov     [rbp+50h+var_A0], 7
0x1800257e4  mov     word ptr [rbp+50h+var_B8], di
0x1800257e8  lea     r12, [r15+88h]
0x1800257ef  lea     r8, [rbp+50h+var_B8]
0x1800257f3  mov     rdx, [rsi+50h]
0x1800257f7  mov     rcx, r12
0x1800257fa  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x1800257ff  mov     ebx, eax
0x180025801  test    eax, eax
0x180025803  jns     short loc_18002582C
0x180025805  mov     edx, 81Dh; void *
0x18002580a  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180025811  mov     r9d, eax; char *
0x180025814  mov     rcx, [rbp+58h]; this
0x180025818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002581d  nop
0x18002581e  lea     rcx, [rbp+50h+var_B8]
0x180025822  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025827  jmp     loc_1800259CD
0x18002582c  mov     [rsp+150h+hObject], rdi
0x180025831  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x180025836  mov     rdi, rax
0x180025839  lea     rcx, [rbp+50h+var_B8]
0x18002583d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180025842  mov     rbx, rax
0x180025845  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x18002584a  lea     rcx, [rsp+150h+hObject]
0x18002584f  mov     [rsp+150h+var_128], rcx; unsigned __int64 *
0x180025854  mov     r8, rbx; pszKeyName
0x180025857  mov     rdx, [rax]; hProvider
0x18002585a  mov     rcx, rdi; SRWLock
0x18002585d  call    ?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)
0x180025862  mov     ebx, eax
0x180025864  xor     edi, edi
0x180025866  test    eax, eax
0x180025868  jns     short loc_180025871
0x18002586a  mov     edx, 825h
0x18002586f  jmp     short loc_18002580A
0x180025871  mov     dword ptr [rbp+50h+pbOutput], edi
0x180025874  mov     [rbp+50h+var_68], rdi
0x180025878  mov     [rbp+50h+var_60], edi
0x18002587b  mov     [rbp+50h+var_58], rdi
0x18002587f  mov     [rbp+50h+var_50], rdi
0x180025883  mov     [rbp+50h+var_48], dil
0x180025887  mov     rdx, [rsp+150h+hObject]; hObject
0x18002588c  lea     rcx, [rbp+50h+pbOutput]; pbOutput
0x180025890  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x180025895  mov     ebx, eax
0x180025897  test    eax, eax
0x180025899  jns     short loc_1800258C2
0x18002589b  mov     edx, 828h; void *
0x1800258a0  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800258a7  mov     r9d, eax; char *
0x1800258aa  mov     rcx, [rbp+58h]; this
0x1800258ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800258b3  nop
0x1800258b4  lea     rcx, [rbp+50h+pbOutput]; this
0x1800258b8  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x1800258bd  jmp     loc_18002581E
0x1800258c2  mov     rbx, [rsi+50h]
0x1800258c6  mov     edi, [rsi+48h]
0x1800258c9  mov     rcx, rsi
0x1800258cc  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x1800258d1  lea     rcx, [rsp+150h+var_F0]
0x1800258d6  mov     [rsp+150h+var_F8], rcx
0x1800258db  mov     [rsp+150h+var_100], r14
0x1800258e0  mov     ecx, [rbp+50h+arg_30]
0x1800258e6  mov     [rsp+150h+var_108], ecx
0x1800258ea  mov     ecx, [rbp+50h+arg_28]
0x1800258f0  mov     [rsp+150h+var_110], ecx
0x1800258f4  mov     rdx, [rbp+50h+var_D0]
0x1800258f8  mov     [rsp+150h+var_118], rdx
0x1800258fd  lea     rcx, [rbp+50h+pbOutput]
0x180025901  mov     [rsp+150h+var_120], rcx
0x180025906  mov     [rsp+150h+var_128], 50h ; 'P'
0x18002590f  mov     [rsp+150h+var_130], rbx
0x180025914  mov     r9d, edi
0x180025917  mov     r8d, eax
0x18002591a  mov     rdx, [rbp+50h+var_C8]
0x18002591e  mov     rcx, r12
0x180025921  call    ?SecretAgreement@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@KPEBUKeyMaterial@5@1PEBE4KKPEA_KPEA_N@Z; NgcIsoTrustlet::SecretAgreement(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,ulong,Properties::KeyMaterial const *,unsigned __int64,uchar const *,uchar const *,ulong,ulong,unsigned __int64 *,bool *)
0x180025926  mov     ebx, eax
0x180025928  test    eax, eax
0x18002592a  jns     short loc_180025936
0x18002592c  mov     edx, 836h
0x180025931  jmp     loc_1800258A0
0x180025936  lea     rcx, [rbp+50h+pbOutput]; this
0x18002593a  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x18002593f  nop
0x180025940  lea     rcx, [rbp+50h+var_B8]
0x180025944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025949  cmp     [rsp+150h+var_F0], 0
0x18002594e  jz      short loc_18002597A
0x180025950  xor     edx, edx
0x180025952  lea     rcx, [rsp+150h+var_D8]
0x180025957  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18002595c  mov     r8, rsi; struct Properties::UserIdKey *
0x18002595f  mov     rdx, r13; unsigned __int16 *
0x180025962  mov     rcx, r15; this
0x180025965  call    ?InternalUpdateKey@NgcIsoContainer@@AEAAJPEBGPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalUpdateKey(ushort const *,Properties::UserIdKey *)
0x18002596a  mov     ebx, eax
0x18002596c  test    eax, eax
0x18002596e  jns     short loc_18002597A
0x180025970  mov     edx, 842h
0x180025975  mov     r9d, eax
0x180025978  jmp     short loc_1800259BC
0x18002597a  mov     rcx, rsi
0x18002597d  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180025982  mov     [r14+8], eax
0x180025986  mov     [rsp+150h+var_E8], 0
0x18002598f  mov     rax, [rbp+50h+var_C0]
0x180025993  mov     [rax], r14
0x180025996  lea     rcx, [rsp+150h+var_E8]
0x18002599b  call    ??1?$unique_ptr@UNgcIsoSecretHandle@@U?$default_delete@UNgcIsoSecretHandle@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcIsoSecretHandle>::~unique_ptr<NgcIsoSecretHandle>(void)
0x1800259a0  nop
0x1800259a1  lea     rcx, [rsp+150h+var_D8]
0x1800259a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800259ab  xor     eax, eax
0x1800259ad  jmp     short loc_1800259E4
0x1800259af  mov     ebx, 80070057h
0x1800259b4  mov     r9d, ebx; char *
0x1800259b7  mov     edx, 83Ah; void *
0x1800259bc  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800259c3  mov     rcx, [rbp+58h]; this
0x1800259c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259cc  nop
0x1800259cd  lea     rcx, [rsp+150h+var_E8]
0x1800259d2  call    ??1?$unique_ptr@UNgcIsoSecretHandle@@U?$default_delete@UNgcIsoSecretHandle@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcIsoSecretHandle>::~unique_ptr<NgcIsoSecretHandle>(void)
0x1800259d7  nop
0x1800259d8  lea     rcx, [rsp+150h+var_D8]
0x1800259dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800259e2  mov     eax, ebx
0x1800259e4  mov     rcx, [rbp+50h+var_40]
0x1800259e8  xor     rcx, rsp; StackCookie
0x1800259eb  call    __security_check_cookie
0x1800259f0  mov     rbx, [rsp+150h+arg_8]
0x1800259f8  add     rsp, 120h
0x1800259ff  pop     r15
0x180025a01  pop     r14
0x180025a03  pop     r13
0x180025a05  pop     r12
0x180025a07  pop     rdi
0x180025a08  pop     rsi
0x180025a09  pop     rbp
0x180025a0a  retn
```
