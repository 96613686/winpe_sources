# NgcIsoContainer::InternalAuthenticatedReqResp(_GUID,unsigned __int64,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180020cd0`
- end: `0x1800210fa`
- name: `?InternalAuthenticatedReqResp@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEBEKPEAPEAEPEAK@Z`
- size: `1066`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007670`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180011108`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180013088`
- `0x180018818`
- `0x18001cbe8`
- `0x18001e1ac`
- `0x180020cd0`
- `0x180023a48`
- `0x180026754`
- `0x180027448`
- `0x18002bf98`
- `0x18004a0e0`
- `0x1800528c0`
- `0x180064cd4`
- `0x180067b58`
- `0x18006f3cc`
- `0x180070e3c`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020d9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020d9c`

## string_xrefs

- `0x180020d7f`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180020dcc`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180020eb8`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180020f55`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002109b`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcIsoContainer::InternalAuthenticatedReqResp(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  unsigned int *v12; // r15
  unsigned int v13; // ebx
  int KeyObject; // eax
  struct Properties::UserIdKey *v15; // rsi
  int updated; // eax
  void **v17; // r9
  __int64 v18; // rdx
  int TpmKspKeyName; // eax
  __int64 v20; // rdx
  RTL_SRWLOCK *v21; // rdi
  const WCHAR *v22; // rbx
  NCRYPT_PROV_HANDLE *v23; // rax
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // rdx
  NgcIsoPregenPool *v27; // rax
  int v28; // edi
  __int64 v29; // r9
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  char v32; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[7]; // [rsp+51h] [rbp-AFh] BYREF
  RTL_SRWLOCK *v34; // [rsp+58h] [rbp-A8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  NgcUtils *v36[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  const unsigned __int8 *v38; // [rsp+80h] [rbp-80h]
  unsigned int *v39; // [rsp+88h] [rbp-78h]
  unsigned __int64 v40; // [rsp+90h] [rbp-70h]
  _OWORD v41[2]; // [rsp+98h] [rbp-68h] BYREF
  BYTE pbOutput[40]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+100h] [rbp+0h]
  char v47; // [rsp+108h] [rbp+8h]
  _QWORD v48[42]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v38 = a5;
  v40 = (unsigned __int64)a7;
  v12 = a8;
  v39 = a8;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v48);
  v48[0] = &LogProvider::NgcIsoAuthenticatedReqResp::`vftable';
  LogProvider::NgcIsoAuthenticatedReqResp::StartActivity((LogProvider::NgcIsoAuthenticatedReqResp *)v48, a4);
  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v34 = this + 2;
    hObject = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject(
                  (NgcIsoContainer *)this,
                  a4,
                  (struct Properties::UserIdKey **)&hObject);
    v13 = KeyObject;
    if ( KeyObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)KeyObject,
        v31);
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v34);
      goto LABEL_35;
    }
    *(_OWORD *)v36 = 0;
    v37 = 0;
    v32 = 0;
    v33[0] = 0;
    v15 = (struct Properties::UserIdKey *)hObject;
    if ( (unsigned int)Properties::Key::GetImplementationType(hObject) == 1 )
    {
      updated = NgcIsoTrustlet::AuthenticatedReqResp(
                  (int)this + 136,
                  a3,
                  *((_QWORD *)v15 + 10),
                  0,
                  0,
                  a6,
                  (__int64)a5,
                  (__int64)v36,
                  (__int64)&v32,
                  (__int64)v33);
      v13 = updated;
      if ( updated < 0 )
      {
        v18 = 2206;
LABEL_29:
        v29 = (unsigned int)updated;
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)v29,
          v31);
        goto LABEL_33;
      }
LABEL_21:
      if ( v32
        && (wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
              &v34,
              0),
            updated = NgcIsoContainer::InternalUpdateKey((NgcIsoContainer *)this, a4, v15),
            v13 = updated,
            updated < 0) )
      {
        v18 = 2247;
      }
      else if ( v33[0]
             && (v27 = NgcIsoPregenPool::Instance(),
                 updated = NgcIsoPregenPool::SaveTpmCounterStore(v27),
                 v13 = updated,
                 updated < 0) )
      {
        v18 = 2252;
      }
      else
      {
        v28 = LODWORD(v36[1]) - LODWORD(v36[0]);
        updated = NgcUtils::CoMemAllocCopy(
                    v36[0],
                    (unsigned int)(LODWORD(v36[1]) - LODWORD(v36[0])),
                    (_QWORD *)v40,
                    v17);
        v13 = updated;
        if ( updated >= 0 )
        {
          *v12 = v28;
          std::vector<unsigned char>::_Tidy(v36);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v34);
          LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp((LogProvider::NgcIsoAuthenticatedReqResp *)v48);
          return 0;
        }
        v18 = 2256;
      }
      goto LABEL_29;
    }
    if ( (unsigned int)Properties::Key::GetImplementationType(v15) != 2 )
    {
      v13 = -2147024809;
      v29 = 2147942487LL;
      v18 = 2239;
      goto LABEL_32;
    }
    v41[0] = 0;
    v41[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v41[0]) = 0;
    TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *((_QWORD *)v15 + 10), v41);
    v13 = TpmKspKeyName;
    if ( TpmKspKeyName >= 0 )
    {
      hObject = 0;
      v21 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
      v23 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v21, *v23, v22, v24, v31, &hObject);
      v13 = TpmKspKeyName;
      if ( TpmKspKeyName >= 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v25 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hObject);
        v13 = v25;
        if ( v25 >= 0 )
        {
          v25 = NgcIsoTrustlet::AuthenticatedReqResp(
                  (int)this + 136,
                  a3,
                  *((_QWORD *)v15 + 10),
                  80,
                  (__int64)pbOutput,
                  a6,
                  (__int64)v38,
                  (__int64)v36,
                  (__int64)&v32,
                  (__int64)v33);
          v13 = v25;
          if ( v25 >= 0 )
          {
            VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
            std::wstring::_Tidy_deallocate(v41);
            v12 = v39;
            goto LABEL_21;
          }
          v26 = 2235;
        }
        else
        {
          v26 = 2223;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v25,
          v31);
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
LABEL_12:
        std::wstring::_Tidy_deallocate(v41);
LABEL_33:
        std::vector<unsigned char>::_Tidy(v36);
        goto LABEL_34;
      }
      v20 = 2220;
    }
    else
    {
      v20 = 2212;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKspKeyName,
      v31);
    goto LABEL_12;
  }
  v13 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x888,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    v31);
LABEL_35:
  LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp((LogProvider::NgcIsoAuthenticatedReqResp *)v48);
  return v13;
}

```

## disassembly

```asm
0x180020cd0  mov     [rsp-8+arg_8], rbx
0x180020cd5  push    rbp
0x180020cd6  push    rsi
0x180020cd7  push    rdi
0x180020cd8  push    r12
0x180020cda  push    r13
0x180020cdc  push    r14
0x180020cde  push    r15
0x180020ce0  lea     rbp, [rsp-170h]
0x180020ce8  sub     rsp, 270h
0x180020cef  mov     rax, cs:__security_cookie
0x180020cf6  xor     rax, rsp
0x180020cf9  mov     [rbp+1A0h+var_40], rax
0x180020d00  mov     r12, r9
0x180020d03  mov     r13, r8
0x180020d06  mov     rbx, rdx
0x180020d09  mov     r14, rcx
0x180020d0c  mov     rdi, [rbp+1A0h+arg_20]
0x180020d13  mov     [rbp+1A0h+var_220], rdi
0x180020d17  mov     rax, [rbp+1A0h+arg_30]
0x180020d1e  mov     [rbp+1A0h+var_210], rax
0x180020d22  mov     r15, [rbp+1A0h+arg_38]
0x180020d29  mov     [rbp+1A0h+var_218], r15
0x180020d2d  lea     rdx, aNgcisoauthenti; "NgcIsoAuthenticatedReqResp"
0x180020d34  lea     rcx, [rbp+1A0h+var_190]; struct wil::details::IFailureCallback *
0x180020d38  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020d3d  lea     rax, ??_7NgcIsoAuthenticatedReqResp@LogProvider@@6B@; const LogProvider::NgcIsoAuthenticatedReqResp::`vftable'
0x180020d44  mov     [rbp+1A0h+var_190], rax
0x180020d48  mov     rdx, r12; unsigned __int16 *
0x180020d4b  lea     rcx, [rbp+1A0h+var_190]; this
0x180020d4f  call    ?StartActivity@NgcIsoAuthenticatedReqResp@LogProvider@@QEAAXPEBG@Z; LogProvider::NgcIsoAuthenticatedReqResp::StartActivity(ushort const *)
0x180020d54  nop
0x180020d55  mov     r8d, 10h; Size
0x180020d5b  lea     rdx, qword_1800947A8; Buf2
0x180020d62  mov     rcx, rbx; Buf1
0x180020d65  call    memcmp_0
0x180020d6a  xor     esi, esi
0x180020d6c  test    eax, eax
0x180020d6e  jz      short loc_180020D95
0x180020d70  mov     rcx, [rbp+1A8h]; this
0x180020d77  mov     ebx, 80070057h
0x180020d7c  mov     r9d, ebx; char *
0x180020d7f  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180020d86  mov     edx, 888h; void *
0x180020d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d90  jmp     loc_1800210C5
0x180020d95  lea     rbx, [r14+10h]
0x180020d99  mov     rcx, rbx; SRWLock
0x180020d9c  call    cs:__imp_AcquireSRWLockShared
0x180020da2  mov     [rsp+2A0h+var_248], rbx
0x180020da7  mov     [rsp+2A0h+hObject], rsi
0x180020dac  lea     r8, [rsp+2A0h+hObject]; struct Properties::UserIdKey **
0x180020db1  mov     rdx, r12; unsigned __int16 *
0x180020db4  mov     rcx, r14; this
0x180020db7  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x180020dbc  mov     ebx, eax
0x180020dbe  test    eax, eax
0x180020dc0  jns     short loc_180020DE2
0x180020dc2  mov     rcx, [rbp+1A8h]; this
0x180020dc9  mov     r9d, eax; char *
0x180020dcc  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180020dd3  mov     edx, 88Dh; void *
0x180020dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ddd  jmp     loc_1800210BA
0x180020de2  xorps   xmm0, xmm0
0x180020de5  movdqu  xmmword ptr [rsp+2A0h+var_238], xmm0
0x180020deb  mov     [rsp+2A0h+var_228], rsi
0x180020df0  mov     [rsp+2A0h+var_250], sil
0x180020df5  mov     [rsp+2A0h+var_24F], sil
0x180020dfa  mov     rsi, [rsp+2A0h+hObject]
0x180020dff  mov     rcx, rsi
0x180020e02  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180020e07  cmp     eax, 1
0x180020e0a  jnz     short loc_180020E6B
0x180020e0c  mov     eax, [rbp+1A0h+arg_28]
0x180020e12  lea     rcx, [r14+88h]
0x180020e19  lea     rdx, [rsp+2A0h+var_24F]
0x180020e1e  mov     [rsp+2A0h+var_258], rdx
0x180020e23  lea     rdx, [rsp+2A0h+var_250]
0x180020e28  mov     [rsp+2A0h+var_260], rdx
0x180020e2d  lea     rdx, [rsp+2A0h+var_238]
0x180020e32  mov     [rsp+2A0h+var_268], rdx
0x180020e37  mov     [rsp+2A0h+var_270], rdi
0x180020e3c  mov     [rsp+2A0h+var_278], rax
0x180020e41  xor     edi, edi
0x180020e43  mov     [rsp+2A0h+var_280], rdi
0x180020e48  xor     r9d, r9d
0x180020e4b  mov     r8, [rsi+50h]
0x180020e4f  mov     rdx, r13
0x180020e52  call    ?AuthenticatedReqResp@NgcIsoTrustlet@@YAJAEBU_GUID@@_KPEBUKeyMaterial@Properties@@1PEBE13PEAV?$vector@EV?$allocator@E@std@@@std@@PEA_N5@Z; NgcIsoTrustlet::AuthenticatedReqResp(_GUID const &,unsigned __int64,Properties::KeyMaterial const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,std::vector<uchar> *,bool *,bool *)
0x180020e57  mov     ebx, eax
0x180020e59  test    eax, eax
0x180020e5b  jns     loc_180020FF1
0x180020e61  mov     edx, 89Eh
0x180020e66  jmp     loc_180021063
0x180020e6b  mov     rcx, rsi
0x180020e6e  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180020e73  cmp     eax, 2
0x180020e76  jnz     loc_18002108E
0x180020e7c  xorps   xmm0, xmm0
0x180020e7f  movups  [rbp+1A0h+var_208], xmm0
0x180020e83  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180020e8b  movdqu  [rbp+1A0h+var_1F8], xmm1
0x180020e90  xor     eax, eax
0x180020e92  mov     word ptr [rbp+1A0h+var_208], ax
0x180020e96  lea     r15, [r14+88h]
0x180020e9d  lea     r8, [rbp+1A0h+var_208]
0x180020ea1  mov     rdx, [rsi+50h]
0x180020ea5  mov     rcx, r15
0x180020ea8  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x180020ead  mov     ebx, eax
0x180020eaf  test    eax, eax
0x180020eb1  jns     short loc_180020EDD
0x180020eb3  mov     edx, 8A4h; void *
0x180020eb8  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180020ebf  mov     r9d, eax; char *
0x180020ec2  mov     rcx, [rbp+1A8h]; this
0x180020ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ece  nop
0x180020ecf  lea     rcx, [rbp+1A0h+var_208]
0x180020ed3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020ed8  jmp     loc_1800210AF
0x180020edd  mov     [rsp+2A0h+hObject], 0
0x180020ee6  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x180020eeb  mov     rdi, rax
0x180020eee  lea     rcx, [rbp+1A0h+var_208]
0x180020ef2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020ef7  mov     rbx, rax
0x180020efa  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x180020eff  lea     rcx, [rsp+2A0h+hObject]
0x180020f04  mov     [rsp+2A0h+var_278], rcx; unsigned __int64 *
0x180020f09  mov     r8, rbx; pszKeyName
0x180020f0c  mov     rdx, [rax]; hProvider
0x180020f0f  mov     rcx, rdi; SRWLock
0x180020f12  call    ?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)
0x180020f17  mov     ebx, eax
0x180020f19  xor     edi, edi
0x180020f1b  test    eax, eax
0x180020f1d  jns     short loc_180020F26
0x180020f1f  mov     edx, 8ACh
0x180020f24  jmp     short loc_180020EB8
0x180020f26  mov     dword ptr [rbp+1A0h+pbOutput], edi
0x180020f29  mov     [rbp+1A0h+var_1B8], rdi
0x180020f2d  mov     [rbp+1A0h+var_1B0], edi
0x180020f30  mov     [rbp+1A0h+var_1A8], rdi
0x180020f34  mov     [rbp+1A0h+var_1A0], rdi
0x180020f38  mov     [rbp+1A0h+var_198], dil
0x180020f3c  mov     rdx, [rsp+2A0h+hObject]; hObject
0x180020f41  lea     rcx, [rbp+1A0h+pbOutput]; pbOutput
0x180020f45  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x180020f4a  mov     ebx, eax
0x180020f4c  test    eax, eax
0x180020f4e  jns     short loc_180020F7A
0x180020f50  mov     edx, 8AFh; void *
0x180020f55  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180020f5c  mov     r9d, eax; char *
0x180020f5f  mov     rcx, [rbp+1A8h]; this
0x180020f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f6b  nop
0x180020f6c  lea     rcx, [rbp+1A0h+pbOutput]; this
0x180020f70  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180020f75  jmp     loc_180020ECF
0x180020f7a  mov     eax, [rbp+1A0h+arg_28]
0x180020f80  lea     rcx, [rsp+2A0h+var_24F]
0x180020f85  mov     [rsp+2A0h+var_258], rcx
0x180020f8a  lea     rcx, [rsp+2A0h+var_250]
0x180020f8f  mov     [rsp+2A0h+var_260], rcx
0x180020f94  lea     rcx, [rsp+2A0h+var_238]
0x180020f99  mov     [rsp+2A0h+var_268], rcx
0x180020f9e  mov     rcx, [rbp+1A0h+var_220]
0x180020fa2  mov     [rsp+2A0h+var_270], rcx
0x180020fa7  mov     [rsp+2A0h+var_278], rax
0x180020fac  lea     rax, [rbp+1A0h+pbOutput]
0x180020fb0  mov     [rsp+2A0h+var_280], rax
0x180020fb5  mov     r9d, 50h ; 'P'
0x180020fbb  mov     r8, [rsi+50h]
0x180020fbf  mov     rdx, r13
0x180020fc2  mov     rcx, r15
0x180020fc5  call    ?AuthenticatedReqResp@NgcIsoTrustlet@@YAJAEBU_GUID@@_KPEBUKeyMaterial@Properties@@1PEBE13PEAV?$vector@EV?$allocator@E@std@@@std@@PEA_N5@Z; NgcIsoTrustlet::AuthenticatedReqResp(_GUID const &,unsigned __int64,Properties::KeyMaterial const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,std::vector<uchar> *,bool *,bool *)
0x180020fca  mov     ebx, eax
0x180020fcc  test    eax, eax
0x180020fce  jns     short loc_180020FDA
0x180020fd0  mov     edx, 8BBh
0x180020fd5  jmp     loc_180020F55
0x180020fda  lea     rcx, [rbp+1A0h+pbOutput]; this
0x180020fde  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180020fe3  nop
0x180020fe4  lea     rcx, [rbp+1A0h+var_208]
0x180020fe8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020fed  mov     r15, [rbp+1A0h+var_218]
0x180020ff1  cmp     [rsp+2A0h+var_250], dil
0x180020ff6  jz      short loc_18002101F
0x180020ff8  xor     edx, edx
0x180020ffa  lea     rcx, [rsp+2A0h+var_248]
0x180020fff  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180021004  mov     r8, rsi; struct Properties::UserIdKey *
0x180021007  mov     rdx, r12; unsigned __int16 *
0x18002100a  mov     rcx, r14; this
0x18002100d  call    ?InternalUpdateKey@NgcIsoContainer@@AEAAJPEBGPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalUpdateKey(ushort const *,Properties::UserIdKey *)
0x180021012  mov     ebx, eax
0x180021014  test    eax, eax
0x180021016  jns     short loc_18002101F
0x180021018  mov     edx, 8C7h
0x18002101d  jmp     short loc_180021063
0x18002101f  cmp     [rsp+2A0h+var_24F], dil
0x180021024  jz      short loc_180021040
0x180021026  call    ?Instance@NgcIsoPregenPool@@SAAEAV1@XZ; NgcIsoPregenPool::Instance(void)
0x18002102b  mov     rcx, rax; this
0x18002102e  call    ?SaveTpmCounterStore@NgcIsoPregenPool@@QEAAJXZ; NgcIsoPregenPool::SaveTpmCounterStore(void)
0x180021033  mov     ebx, eax
0x180021035  test    eax, eax
0x180021037  jns     short loc_180021040
0x180021039  mov     edx, 8CCh
0x18002103e  jmp     short loc_180021063
0x180021040  mov     eax, dword ptr [rsp+2A0h+var_238+8]
0x180021044  mov     rcx, [rsp+2A0h+var_238]; this
0x180021049  sub     eax, ecx
0x18002104b  mov     edi, eax
0x18002104d  mov     edx, eax; SourceSize
0x18002104f  mov     r8, [rbp+1A0h+var_210]; unsigned __int64
0x180021053  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180021058  mov     ebx, eax
0x18002105a  test    eax, eax
0x18002105c  jns     short loc_180021068
0x18002105e  mov     edx, 8D0h
0x180021063  mov     r9d, eax
0x180021066  jmp     short loc_18002109B
0x180021068  mov     [r15], edi
0x18002106b  lea     rcx, [rsp+2A0h+var_238]
0x180021070  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021075  nop
0x180021076  lea     rcx, [rsp+2A0h+var_248]
0x18002107b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021080  nop
0x180021081  lea     rcx, [rbp+1A0h+var_190]; this
0x180021085  call    ??1NgcIsoAuthenticatedReqResp@LogProvider@@QEAA@XZ; LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp(void)
0x18002108a  xor     eax, eax
0x18002108c  jmp     short loc_1800210D0
0x18002108e  mov     ebx, 80070057h
0x180021093  mov     r9d, ebx; char *
0x180021096  mov     edx, 8BFh; void *
0x18002109b  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800210a2  mov     rcx, [rbp+1A8h]; this
0x1800210a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800210ae  nop
0x1800210af  lea     rcx, [rsp+2A0h+var_238]
0x1800210b4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800210b9  nop
0x1800210ba  lea     rcx, [rsp+2A0h+var_248]
0x1800210bf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800210c4  nop
0x1800210c5  lea     rcx, [rbp+1A0h+var_190]; this
0x1800210c9  call    ??1NgcIsoAuthenticatedReqResp@LogProvider@@QEAA@XZ; LogProvider::NgcIsoAuthenticatedReqResp::~NgcIsoAuthenticatedReqResp(void)
0x1800210ce  mov     eax, ebx
0x1800210d0  mov     rcx, [rbp+1A0h+var_40]
0x1800210d7  xor     rcx, rsp; StackCookie
0x1800210da  call    __security_check_cookie
0x1800210df  mov     rbx, [rsp+2A0h+arg_8]
0x1800210e7  add     rsp, 270h
0x1800210ee  pop     r15
0x1800210f0  pop     r14
0x1800210f2  pop     r13
0x1800210f4  pop     r12
0x1800210f6  pop     rdi
0x1800210f7  pop     rsi
0x1800210f8  pop     rbp
0x1800210f9  retn
```
