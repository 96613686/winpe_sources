# MicrodomImplementation::CMicrodom::Initialize(MicrodomImplementation::MdCreateParams const &)

- ea: `0x180058efc`
- end: `0x18005938f`
- name: `?Initialize@CMicrodom@MicrodomImplementation@@QEAAJAEBUMdCreateParams@2@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *__hidden this, const struct MicrodomImplementation::MdCreateParams *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cd2c`

## callees

- `0x180018cac`
- `0x18001a284`
- `0x18001af00`
- `0x18001f1d8`
- `0x18001f840`
- `0x1800217cc`
- `0x1800254b4`
- `0x18002d2b0`
- `0x180056788`
- `0x180056824`
- `0x1800569dc`
- `0x180058efc`
- `0x1800650b0`
- `0x18009e020`

## string_xrefs

- `0x180059043`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005908d`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800590bc`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800590e8`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059117`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059146`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800591bb`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059209`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005923d`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059333`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059359`: `m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::Initialize(
        MicrodomImplementation::CMicrodom *this,
        const struct MicrodomImplementation::MdCreateParams *a2)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  int v6; // edi
  const char *v7; // rcx
  __int64 result; // rax
  _QWORD *v9; // rdi
  struct Windows::Rtl::CRtlTrackTypeDescription *v10; // rcx
  const char *v11; // rax
  _DWORD *v12; // rax
  __int64 v13; // rcx
  const struct _MICRODOM_STRINGPOOL_HEADER *v14; // rdx
  const struct _MICRODOM_DOM_HEADER *v15; // rsi
  const struct _MICRODOM_LOCATION_HEADER *v16; // r14
  _DWORD *v17; // rdi
  const char *v18; // rax
  int v19; // [rsp+30h] [rbp-30h] BYREF
  const char *v20; // [rsp+38h] [rbp-28h] BYREF
  const char *v21; // [rsp+40h] [rbp-20h]
  __int64 v22; // [rsp+48h] [rbp-18h]
  const char *v23; // [rsp+50h] [rbp-10h]

  v19 = 0;
  v3 = (__int64 *)*((_QWORD *)a2 + 3);
  if ( !v3 )
  {
    v9 = (_QWORD *)((char *)this + 496);
    if ( *((_BYTE *)a2 + 48) )
    {
      *v9 = *(_QWORD *)a2;
      *((_QWORD *)this + 63) = *((_QWORD *)a2 + 1);
      *((_QWORD *)this + 64) = *((_QWORD *)a2 + 2);
    }
    else
    {
      result = RtlDuplicateLBlob(a2, (char *)this + 496);
      if ( (int)result < 0 )
        return result;
      v10 = Windows::Rtl::g_pTrackTypeDescription;
      *((_BYTE *)this + 552) = 1;
      if ( v10 )
        (*(void (__fastcall **)(struct Windows::Rtl::CRtlTrackTypeDescription *, const char *, __int64, _QWORD, char))(*(_QWORD *)v10 + 16LL))(
          v10,
          "CMicrodom_Blob",
          1,
          *(unsigned int *)v9,
          1);
    }
LABEL_15:
    if ( *v9 >= 0x18u )
    {
      v12 = (_DWORD *)*((_QWORD *)this + 64);
      v13 = (unsigned int)v12[1];
      if ( v13 == *v9 )
      {
        if ( *v12 == 1682465869 )
        {
          if ( v12[3] < (unsigned int)v13 )
          {
            if ( v12[2] < (unsigned int)v13 )
            {
              if ( v12[4] < (unsigned int)v13 )
              {
                v14 = 0;
                *((_QWORD *)this + 68) = v12;
                if ( v12[2] )
                  v14 = (const struct _MICRODOM_STRINGPOOL_HEADER *)((char *)v12 + (unsigned int)v12[2]);
                v15 = 0;
                if ( v12[3] )
                  v15 = (const struct _MICRODOM_DOM_HEADER *)((char *)v12 + (unsigned int)v12[3]);
                v16 = 0;
                if ( v12[4] )
                  v16 = (const struct _MICRODOM_LOCATION_HEADER *)((char *)v12 + (unsigned int)v12[4]);
                v17 = 0;
                if ( v12[5] )
                  v17 = (_DWORD *)((char *)v12 + (unsigned int)v12[5]);
                if ( !v14 || *(_DWORD *)v14 == 1884513357 )
                {
                  if ( !v15 || *(_DWORD *)v15 == 1816421453 )
                  {
                    if ( !v17 || *v17 == 1950639181 )
                    {
                      result = MicrodomImplementation::CStringpoolCache::AttachToStringPool(
                                 (MicrodomImplementation::CMicrodom *)((char *)this + 32),
                                 v14);
                      if ( (int)result >= 0 )
                      {
                        result = MicrodomImplementation::CDomLayoutCache::Attach(
                                   (MicrodomImplementation::CMicrodom *)((char *)this + 48),
                                   v15);
                        if ( (int)result >= 0 )
                        {
                          if ( *((MicrodomImplementation::CMicrodom **)this + 15) == (MicrodomImplementation::CMicrodom *)((char *)this + 160) )
                          {
                            BUCL::Implementation::CMultiplier<unsigned __int64,BUCL::Rtl::CCallDisposition>::Multiply(
                              &v20,
                              *((_QWORD *)this + 17),
                              5);
                            *((_QWORD *)this + 19) = v20;
                            result = (unsigned int)v21;
                            if ( (int)v21 >= 0 )
                            {
                              *((_QWORD *)this + 56) = v17;
                              *((_QWORD *)this + 53) = v17 + 2;
                              *((_QWORD *)this + 54) = v17 + 2;
                              result = *(unsigned int *)BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(
                                                          (char *)this + 392,
                                                          &v20,
                                                          (unsigned int)v17[1]);
                              if ( (int)result >= 0 )
                              {
                                if ( !v16
                                  || (result = MicrodomImplementation::CDomPositionCache::AttachToPositionList(
                                                 (MicrodomImplementation::CMicrodom *)((char *)this + 456),
                                                 v16),
                                      (int)result >= 0) )
                                {
                                  if ( Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>,Windows::Auto<Windows::Vector<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>>>::Allocate(
                                         (char *)this + 600,
                                         *(unsigned int *)(*((_QWORD *)this + 12) + 8LL)) )
                                  {
                                    return 0;
                                  }
                                  else
                                  {
                                    v22 = 2485;
                                    v20 = "onecore\\base\\xml\\udom_microdom.cpp";
                                    v21 = "MicrodomImplementation::CMicrodom::Initialize";
                                    v23 = "m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())";
                                    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                                             &v19,
                                             &v20);
                                  }
                                }
                              }
                            }
                          }
                          else
                          {
                            __debugbreak();
                            return 3221225701LL;
                          }
                        }
                      }
                      return result;
                    }
                    v22 = 2469;
                    v20 = "onecore\\base\\xml\\udom_microdom.cpp";
                    v21 = "MicrodomImplementation::CMicrodom::Initialize";
                    v18 = "pDoctype->ulSignature == ('tDdM')";
                  }
                  else
                  {
                    v22 = 2466;
                    v20 = "onecore\\base\\xml\\udom_microdom.cpp";
                    v21 = "MicrodomImplementation::CMicrodom::Initialize";
                    v18 = "pDomLayout->ulSignature == ('lDdM')";
                  }
                }
                else
                {
                  v22 = 2463;
                  v20 = "onecore\\base\\xml\\udom_microdom.cpp";
                  v21 = "MicrodomImplementation::CMicrodom::Initialize";
                  v18 = "pStringPool->Signature == ('pSdM')";
                }
                v23 = v18;
                return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                         &v19,
                         &v20,
                         3221225595LL);
              }
              v22 = 2447;
              v20 = "onecore\\base\\xml\\udom_microdom.cpp";
              v21 = "MicrodomImplementation::CMicrodom::Initialize";
              v11 = "pHeader->ulOffsetToPositionData < pHeader->ulTotalSize";
            }
            else
            {
              v22 = 2446;
              v20 = "onecore\\base\\xml\\udom_microdom.cpp";
              v21 = "MicrodomImplementation::CMicrodom::Initialize";
              v11 = "pHeader->ulOffsetToStringPool < pHeader->ulTotalSize";
            }
          }
          else
          {
            v22 = 2445;
            v20 = "onecore\\base\\xml\\udom_microdom.cpp";
            v21 = "MicrodomImplementation::CMicrodom::Initialize";
            v11 = "pHeader->ulOffsetToDomLayout < pHeader->ulTotalSize";
          }
        }
        else
        {
          v22 = 2444;
          v20 = "onecore\\base\\xml\\udom_microdom.cpp";
          v21 = "MicrodomImplementation::CMicrodom::Initialize";
          v11 = "pHeader->ulSignature == ('dHdM')";
        }
      }
      else
      {
        v22 = 2443;
        v20 = "onecore\\base\\xml\\udom_microdom.cpp";
        v21 = "MicrodomImplementation::CMicrodom::Initialize";
        v11 = "pHeader->ulTotalSize == m_MicrodomDataBlob.Length";
      }
    }
    else
    {
      v22 = 2440;
      v20 = "onecore\\base\\xml\\udom_microdom.cpp";
      v21 = "MicrodomImplementation::CMicrodom::Initialize";
      v11 = "m_MicrodomDataBlob.Length >= sizeof(MICRODOM_HEADER)";
    }
    v23 = v11;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v19,
             &v20);
  }
  v5 = *v3;
  v20 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, GUID *, const char **))(v5 + 8))(
         v3,
         &GUID_31257d4b_3df7_46f9_86c5_1c76711e334e,
         &v20);
  if ( v6 >= 0 )
  {
    v7 = v20;
    if ( v20 )
    {
      v20 = (const char *)*((_QWORD *)this + 70);
      *((_QWORD *)this + 70) = v7;
    }
    else
    {
      v6 = -1073741127;
    }
  }
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v20);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v9 = (_QWORD *)((char *)this + 496);
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, char *))(**((_QWORD **)this + 70) + 16LL))(
             *((_QWORD *)this + 70),
             *((_QWORD *)a2 + 4),
             *((_QWORD *)a2 + 5),
             (char *)this + 568,
             (char *)this + 496);
  if ( (int)result >= 0 )
    goto LABEL_15;
  return result;
}

```

## disassembly

```asm
0x180058efc  mov     [rsp-18h+arg_10], rbx
0x180058f01  mov     [rsp-18h+arg_18], rsi
0x180058f06  push    rbp
0x180058f07  push    rdi
0x180058f08  push    r14
0x180058f0a  mov     rbp, rsp
0x180058f0d  sub     rsp, 60h
0x180058f11  mov     rax, cs:__security_cookie
0x180058f18  xor     rax, rsp
0x180058f1b  mov     [rbp+var_8], rax
0x180058f1f  mov     rbx, rcx
0x180058f22  mov     [rbp+var_30], 0
0x180058f29  mov     rcx, [rdx+18h]
0x180058f2d  mov     rsi, rdx
0x180058f30  test    rcx, rcx
0x180058f33  jz      loc_180058FCB
0x180058f39  mov     rax, [rcx]
0x180058f3c  lea     r8, [rbp+var_28]
0x180058f40  lea     rdx, _GUID_31257d4b_3df7_46f9_86c5_1c76711e334e
0x180058f47  mov     [rbp+var_28], 0
0x180058f4f  mov     rax, [rax+8]
0x180058f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f58  mov     edi, eax
0x180058f5a  test    eax, eax
0x180058f5c  js      short loc_180058F80
0x180058f5e  mov     rcx, [rbp+var_28]
0x180058f62  test    rcx, rcx
0x180058f65  jnz     short loc_180058F6E
0x180058f67  mov     edi, 0C00002B9h
0x180058f6c  jmp     short loc_180058F80
0x180058f6e  mov     rax, [rbx+230h]
0x180058f75  mov     [rbp+var_28], rax
0x180058f79  mov     [rbx+230h], rcx
0x180058f80  lea     rcx, [rbp+var_28]
0x180058f84  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180058f89  test    edi, edi
0x180058f8b  jns     short loc_180058F94
0x180058f8d  mov     eax, edi
0x180058f8f  jmp     loc_18005936D
0x180058f94  mov     rcx, [rbx+230h]
0x180058f9b  lea     rdi, [rbx+1F0h]
0x180058fa2  mov     r8, [rsi+28h]
0x180058fa6  lea     r9, [rbx+238h]
0x180058fad  mov     rdx, [rsi+20h]
0x180058fb1  mov     [rsp+60h+var_40], rdi
0x180058fb6  mov     rax, [rcx]
0x180058fb9  mov     rax, [rax+10h]
0x180058fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fc2  test    eax, eax
0x180058fc4  jns     short loc_18005903D
0x180058fc6  jmp     loc_18005936D
0x180058fcb  cmp     byte ptr [rdx+30h], 0
0x180058fcf  lea     rdi, [rbx+1F0h]
0x180058fd6  jz      short loc_180058FF6
0x180058fd8  mov     rax, [rdx]
0x180058fdb  mov     [rdi], rax
0x180058fde  mov     rax, [rdx+8]
0x180058fe2  mov     [rbx+1F8h], rax
0x180058fe9  mov     rax, [rdx+10h]
0x180058fed  mov     [rbx+200h], rax
0x180058ff4  jmp     short loc_18005903D
0x180058ff6  mov     rdx, rdi
0x180058ff9  mov     rcx, rsi
0x180058ffc  call    RtlDuplicateLBlob
0x180059001  test    eax, eax
0x180059003  js      loc_18005936D
0x180059009  mov     rcx, cs:?g_pTrackTypeDescription@Rtl@Windows@@3PEAVCRtlTrackTypeDescription@12@EA; Windows::Rtl::CRtlTrackTypeDescription * Windows::Rtl::g_pTrackTypeDescription
0x180059010  mov     byte ptr [rbx+228h], 1
0x180059017  test    rcx, rcx
0x18005901a  jz      short loc_18005903D
0x18005901c  mov     rax, [rcx]
0x18005901f  lea     rdx, aCmicrodomBlob; "CMicrodom_Blob"
0x180059026  mov     r9d, [rdi]
0x180059029  mov     r8d, 1
0x18005902f  mov     byte ptr [rsp+60h+var_40], 1
0x180059034  mov     rax, [rax+10h]
0x180059038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005903d  cmp     qword ptr [rdi], 18h
0x180059041  jnb     short loc_18005907E
0x180059043  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005904a  mov     [rbp+var_18], 988h
0x180059052  mov     [rbp+var_28], rax
0x180059056  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x18005905d  mov     [rbp+var_20], rax
0x180059061  lea     rax, aMMicrodomdatab; "m_MicrodomDataBlob.Length >= sizeof(MIC"...
0x180059068  lea     rdx, [rbp+var_28]
0x18005906c  mov     [rbp+var_10], rax
0x180059070  lea     rcx, [rbp+var_30]
0x180059074  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180059079  jmp     loc_18005936D
0x18005907e  mov     rax, [rbx+200h]
0x180059085  mov     ecx, [rax+4]
0x180059088  cmp     rcx, [rdi]
0x18005908b  jz      short loc_1800590B4
0x18005908d  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180059094  mov     [rbp+var_18], 98Bh
0x18005909c  mov     [rbp+var_28], rax
0x1800590a0  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800590a7  mov     [rbp+var_20], rax
0x1800590ab  lea     rax, aPheaderUltotal; "pHeader->ulTotalSize == m_MicrodomDataB"...
0x1800590b2  jmp     short loc_180059068
0x1800590b4  cmp     dword ptr [rax], 6448644Dh
0x1800590ba  jz      short loc_1800590E3
0x1800590bc  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800590c3  mov     [rbp+var_18], 98Ch
0x1800590cb  mov     [rbp+var_28], rax
0x1800590cf  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800590d6  mov     [rbp+var_20], rax
0x1800590da  lea     rax, aPheaderUlsigna; "pHeader->ulSignature == ('dHdM')"
0x1800590e1  jmp     short loc_180059068
0x1800590e3  cmp     [rax+0Ch], ecx
0x1800590e6  jb      short loc_180059112
0x1800590e8  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800590ef  mov     [rbp+var_18], 98Dh
0x1800590f7  mov     [rbp+var_28], rax
0x1800590fb  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059102  mov     [rbp+var_20], rax
0x180059106  lea     rax, aPheaderUloffse; "pHeader->ulOffsetToDomLayout < pHeader-"...
0x18005910d  jmp     loc_180059068
0x180059112  cmp     [rax+8], ecx
0x180059115  jb      short loc_180059141
0x180059117  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005911e  mov     [rbp+var_18], 98Eh
0x180059126  mov     [rbp+var_28], rax
0x18005912a  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059131  mov     [rbp+var_20], rax
0x180059135  lea     rax, aPheaderUloffse_1; "pHeader->ulOffsetToStringPool < pHeader"...
0x18005913c  jmp     loc_180059068
0x180059141  cmp     [rax+10h], ecx
0x180059144  jb      short loc_180059170
0x180059146  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005914d  mov     [rbp+var_18], 98Fh
0x180059155  mov     [rbp+var_28], rax
0x180059159  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059160  mov     [rbp+var_20], rax
0x180059164  lea     rax, aPheaderUloffse_0; "pHeader->ulOffsetToPositionData < pHead"...
0x18005916b  jmp     loc_180059068
0x180059170  xor     edx, edx
0x180059172  mov     [rbx+220h], rax
0x180059179  cmp     [rax+8], edx
0x18005917c  jz      short loc_180059184
0x18005917e  mov     edx, [rax+8]
0x180059181  add     rdx, rax; struct _MICRODOM_STRINGPOOL_HEADER *
0x180059184  xor     esi, esi
0x180059186  cmp     [rax+0Ch], esi
0x180059189  jz      short loc_180059191
0x18005918b  mov     esi, [rax+0Ch]
0x18005918e  add     rsi, rax
0x180059191  xor     r14d, r14d
0x180059194  cmp     [rax+10h], r14d
0x180059198  jz      short loc_1800591A1
0x18005919a  mov     r14d, [rax+10h]
0x18005919e  add     r14, rax
0x1800591a1  xor     edi, edi
0x1800591a3  cmp     [rax+14h], edi
0x1800591a6  jz      short loc_1800591AE
0x1800591a8  mov     edi, [rax+14h]
0x1800591ab  add     rdi, rax
0x1800591ae  test    rdx, rdx
0x1800591b1  jz      short loc_1800591FC
0x1800591b3  cmp     dword ptr [rdx], 7053644Dh
0x1800591b9  jz      short loc_1800591FC
0x1800591bb  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800591c2  mov     [rbp+var_18], 99Fh
0x1800591ca  mov     [rbp+var_28], rax
0x1800591ce  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800591d5  mov     [rbp+var_20], rax
0x1800591d9  lea     rax, aPstringpoolSig; "pStringPool->Signature == ('pSdM')"
0x1800591e0  mov     r8d, 0C000007Bh
0x1800591e6  mov     [rbp+var_10], rax
0x1800591ea  lea     rdx, [rbp+var_28]
0x1800591ee  lea     rcx, [rbp+var_30]
0x1800591f2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800591f7  jmp     loc_18005936D
0x1800591fc  test    rsi, rsi
0x1800591ff  jz      short loc_180059230
0x180059201  cmp     dword ptr [rsi], 6C44644Dh
0x180059207  jz      short loc_180059230
0x180059209  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180059210  mov     [rbp+var_18], 9A2h
0x180059218  mov     [rbp+var_28], rax
0x18005921c  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059223  mov     [rbp+var_20], rax
0x180059227  lea     rax, aPdomlayoutUlsi; "pDomLayout->ulSignature == ('lDdM')"
0x18005922e  jmp     short loc_1800591E0
0x180059230  test    rdi, rdi
0x180059233  jz      short loc_180059267
0x180059235  cmp     dword ptr [rdi], 7444644Dh
0x18005923b  jz      short loc_180059267
0x18005923d  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180059244  mov     [rbp+var_18], 9A5h
0x18005924c  mov     [rbp+var_28], rax
0x180059250  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059257  mov     [rbp+var_20], rax
0x18005925b  lea     rax, aPdoctypeUlsign; "pDoctype->ulSignature == ('tDdM')"
0x180059262  jmp     loc_1800591E0
0x180059267  lea     rcx, [rbx+20h]; this
0x18005926b  call    ?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z; MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)
0x180059270  test    eax, eax
0x180059272  js      loc_18005936D
0x180059278  lea     rcx, [rbx+30h]; this
0x18005927c  mov     rdx, rsi; struct _MICRODOM_DOM_HEADER *
0x18005927f  call    ?Attach@CDomLayoutCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_DOM_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::Attach(_MICRODOM_DOM_HEADER const *)
0x180059284  test    eax, eax
0x180059286  js      loc_18005936D
0x18005928c  lea     rax, [rbx+0A0h]
0x180059293  cmp     [rbx+78h], rax
0x180059297  jz      short loc_1800592A4
0x180059299  int     3; Trap to Debugger
0x18005929a  mov     eax, 0C00000E5h
0x18005929f  jmp     loc_18005936D
0x1800592a4  mov     rdx, [rbx+88h]
0x1800592ab  lea     rcx, [rbp+var_28]
0x1800592af  mov     r8d, 5
0x1800592b5  call    ?Multiply@?$CMultiplier@_KVCCallDisposition@Rtl@BUCL@@@Implementation@BUCL@@SA@_K0@Z; BUCL::Implementation::CMultiplier<unsigned __int64,BUCL::Rtl::CCallDisposition>::Multiply(unsigned __int64,unsigned __int64)
0x1800592ba  mov     rax, [rbp+var_28]
0x1800592be  mov     [rbx+98h], rax
0x1800592c5  mov     eax, dword ptr [rbp+var_20]
0x1800592c8  test    eax, eax
0x1800592ca  js      loc_18005936D
0x1800592d0  lea     rax, [rdi+8]
0x1800592d4  mov     [rbx+1C0h], rdi
0x1800592db  mov     [rbx+1A8h], rax
0x1800592e2  lea     rcx, [rbx+188h]
0x1800592e9  mov     [rbx+1B0h], rax
0x1800592f0  lea     rdx, [rbp+var_28]
0x1800592f4  mov     r8d, [rdi+4]
0x1800592f8  call    ?Reserve@?$CVector@PEAU_MICRODOM_DOCTYPE_NODE_HEADER@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(unsigned __int64)
0x1800592fd  mov     eax, [rax]
0x1800592ff  test    eax, eax
0x180059301  js      short loc_18005936D
0x180059303  test    r14, r14
0x180059306  jz      short loc_18005931B
0x180059308  lea     rcx, [rbx+1C8h]; this
0x18005930f  mov     rdx, r14; struct _MICRODOM_LOCATION_HEADER *
0x180059312  call    ?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z; MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)
0x180059317  test    eax, eax
0x180059319  js      short loc_18005936D
0x18005931b  mov     rax, [rbx+60h]
0x18005931f  lea     rcx, [rbx+258h]
0x180059326  mov     edx, [rax+8]
0x180059329  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@V?$Auto@U?$Vector@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@@2@@Windows@@QEAAPEAVCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>,Windows::Auto<Windows::Vector<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>>>::Allocate(unsigned __int64)
0x18005932e  test    rax, rax
0x180059331  jnz     short loc_18005936B
0x180059333  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005933a  mov     [rbp+var_18], 9B5h
0x180059342  mov     [rbp+var_28], rax
0x180059346  lea     rdx, [rbp+var_28]
0x18005934a  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180059351  mov     [rbp+var_20], rax
0x180059355  lea     rcx, [rbp+var_30]
0x180059359  lea     rax, aMPropertycache; "m_PropertyCache.Allocate(m_LayoutCache."...
0x180059360  mov     [rbp+var_10], rax
0x180059364  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180059369  jmp     short loc_18005936D
0x18005936b  xor     eax, eax
0x18005936d  mov     rcx, [rbp+var_8]
0x180059371  xor     rcx, rsp; StackCookie
0x180059374  call    __security_check_cookie
0x180059379  lea     r11, [rsp+60h+var_s0]
0x18005937e  mov     rbx, [r11+30h]
0x180059382  mov     rsi, [r11+38h]
0x180059386  mov     rsp, r11
0x180059389  pop     r14
0x18005938b  pop     rdi
0x18005938c  pop     rbp
0x18005938d  retn
```
