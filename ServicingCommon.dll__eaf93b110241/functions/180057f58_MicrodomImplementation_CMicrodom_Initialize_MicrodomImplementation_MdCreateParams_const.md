# MicrodomImplementation::CMicrodom::Initialize(MicrodomImplementation::MdCreateParams const &)

- ea: `0x180057f58`
- end: `0x1800583f6`
- name: `?Initialize@CMicrodom@MicrodomImplementation@@QEAAJAEBUMdCreateParams@2@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *__hidden this, const struct MicrodomImplementation::MdCreateParams *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800539e0`

## callees

- `0x18000fa14`
- `0x180010c10`
- `0x180012a18`
- `0x18001f4ac`
- `0x18001f554`
- `0x18001f5d4`
- `0x180021a4c`
- `0x1800293a0`
- `0x1800543b4`
- `0x180054450`
- `0x180054598`
- `0x180054dbc`
- `0x180057f58`
- `0x1800647a0`
- `0x1800a0020`

## string_xrefs

- `0x1800580bc`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058106`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058135`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058161`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058190`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800581bf`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005821b`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005826d`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800582a5`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005839c`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800583c2`: `m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::Initialize(
        MicrodomImplementation::CMicrodom *this,
        const struct MicrodomImplementation::MdCreateParams *a2)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  int v6; // edi
  __int64 v7; // rcx
  __int64 result; // rax
  _QWORD *v9; // rdi
  struct Windows::Rtl::CRtlTrackTypeDescription *v10; // rcx
  const char *v11; // rax
  unsigned int *v12; // rcx
  __int64 v13; // rax
  const char *v14; // rax
  struct _MICRODOM_STRINGPOOL_HEADER *v15; // rsi
  struct _MICRODOM_LOCATION_HEADER *v16; // rdi
  const struct _MICRODOM_DOCTYPE_HEADER **v17; // [rsp+28h] [rbp-58h]
  struct _MICRODOM_LOCATION_HEADER *v18; // [rsp+30h] [rbp-50h] BYREF
  const char *v19; // [rsp+38h] [rbp-48h]
  __int64 v20; // [rsp+40h] [rbp-40h]
  const char *v21; // [rsp+48h] [rbp-38h]
  struct _MICRODOM_STRINGPOOL_HEADER *v22; // [rsp+50h] [rbp-30h] BYREF
  struct _MICRODOM_STRINGPOOL_HEADER *v23; // [rsp+58h] [rbp-28h] BYREF
  struct _MICRODOM_DOM_HEADER *v24; // [rsp+60h] [rbp-20h] BYREF
  int v25; // [rsp+68h] [rbp-18h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h] BYREF

  v25 = 0;
  v3 = (__int64 *)*((_QWORD *)a2 + 3);
  v22 = 0;
  v23 = 0;
  v18 = 0;
  v24 = 0;
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
      v12 = (unsigned int *)*((_QWORD *)this + 64);
      v13 = v12[1];
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
                *((_QWORD *)this + 68) = v12;
                MicrodomImplementation::FindActualObjectPointers(
                  (MicrodomImplementation *)v12,
                  (const struct _MICRODOM_HEADER *)&v22,
                  &v23,
                  &v24,
                  &v18,
                  v17);
                if ( !v22 || *(_DWORD *)v22 == 1884513357 )
                {
                  v15 = v23;
                  if ( !v23 || *(_DWORD *)v23 == 1816421453 )
                  {
                    v16 = v18;
                    if ( !v18 || *(_DWORD *)v18 == 1950639181 )
                    {
                      result = MicrodomImplementation::CStringpoolCache::AttachToStringPool(
                                 (MicrodomImplementation::CMicrodom *)((char *)this + 32),
                                 v22);
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
                              &v18,
                              *((_QWORD *)this + 17),
                              5);
                            *((_QWORD *)this + 19) = v18;
                            result = (unsigned int)v19;
                            if ( (int)v19 >= 0 )
                            {
                              *((_QWORD *)this + 56) = v16;
                              *((_QWORD *)this + 53) = (char *)v16 + 8;
                              *((_QWORD *)this + 54) = (char *)v16 + 8;
                              result = *(unsigned int *)BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(
                                                          (char *)this + 392,
                                                          &v26,
                                                          *((unsigned int *)v16 + 1));
                              if ( (int)result >= 0 )
                              {
                                if ( !v24
                                  || (result = MicrodomImplementation::CDomPositionCache::AttachToPositionList(
                                                 (MicrodomImplementation::CMicrodom *)((char *)this + 456),
                                                 v24),
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
                                    v20 = 2485;
                                    v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
                                    v19 = "MicrodomImplementation::CMicrodom::Initialize";
                                    v21 = "m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())";
                                    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                                             &v25,
                                             &v18);
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
                    v20 = 2469;
                    v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
                    v19 = "MicrodomImplementation::CMicrodom::Initialize";
                    v14 = "pDoctype->ulSignature == ('tDdM')";
                  }
                  else
                  {
                    v20 = 2466;
                    v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
                    v19 = "MicrodomImplementation::CMicrodom::Initialize";
                    v14 = "pDomLayout->ulSignature == ('lDdM')";
                  }
                }
                else
                {
                  v20 = 2463;
                  v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
                  v19 = "MicrodomImplementation::CMicrodom::Initialize";
                  v14 = "pStringPool->Signature == ('pSdM')";
                }
                v21 = v14;
                return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                         &v25,
                         &v18,
                         3221225595LL);
              }
              v20 = 2447;
              v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
              v19 = "MicrodomImplementation::CMicrodom::Initialize";
              v11 = "pHeader->ulOffsetToPositionData < pHeader->ulTotalSize";
            }
            else
            {
              v20 = 2446;
              v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
              v19 = "MicrodomImplementation::CMicrodom::Initialize";
              v11 = "pHeader->ulOffsetToStringPool < pHeader->ulTotalSize";
            }
          }
          else
          {
            v20 = 2445;
            v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
            v19 = "MicrodomImplementation::CMicrodom::Initialize";
            v11 = "pHeader->ulOffsetToDomLayout < pHeader->ulTotalSize";
          }
        }
        else
        {
          v20 = 2444;
          v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
          v19 = "MicrodomImplementation::CMicrodom::Initialize";
          v11 = "pHeader->ulSignature == ('dHdM')";
        }
      }
      else
      {
        v20 = 2443;
        v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
        v19 = "MicrodomImplementation::CMicrodom::Initialize";
        v11 = "pHeader->ulTotalSize == m_MicrodomDataBlob.Length";
      }
    }
    else
    {
      v20 = 2440;
      v18 = (struct _MICRODOM_LOCATION_HEADER *)"onecore\\base\\xml\\udom_microdom.cpp";
      v19 = "MicrodomImplementation::CMicrodom::Initialize";
      v11 = "m_MicrodomDataBlob.Length >= sizeof(MICRODOM_HEADER)";
    }
    v21 = v11;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v25,
             &v18);
  }
  v5 = *v3;
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(v5 + 8))(
         v3,
         &GUID_31257d4b_3df7_46f9_86c5_1c76711e334e,
         &v26);
  if ( v6 >= 0 )
  {
    v7 = v26;
    if ( v26 )
    {
      v26 = *((_QWORD *)this + 70);
      *((_QWORD *)this + 70) = v7;
    }
    else
    {
      v6 = -1073741127;
    }
  }
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v26);
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
0x180057f58  mov     [rsp-18h+arg_10], rbx
0x180057f5d  push    rbp
0x180057f5e  push    rsi
0x180057f5f  push    rdi
0x180057f60  mov     rbp, rsp
0x180057f63  sub     rsp, 80h
0x180057f6a  mov     rax, cs:__security_cookie
0x180057f71  xor     rax, rsp
0x180057f74  mov     [rbp+var_8], rax
0x180057f78  mov     rbx, rcx
0x180057f7b  mov     [rbp+var_18], 0
0x180057f82  mov     rcx, [rdx+18h]
0x180057f86  mov     rsi, rdx
0x180057f89  mov     [rbp+var_30], 0
0x180057f91  mov     [rbp+var_28], 0
0x180057f99  mov     [rbp+var_50], 0
0x180057fa1  mov     [rbp+var_20], 0
0x180057fa9  test    rcx, rcx
0x180057fac  jz      loc_180058044
0x180057fb2  mov     rax, [rcx]
0x180057fb5  lea     r8, [rbp+var_10]
0x180057fb9  lea     rdx, _GUID_31257d4b_3df7_46f9_86c5_1c76711e334e
0x180057fc0  mov     [rbp+var_10], 0
0x180057fc8  mov     rax, [rax+8]
0x180057fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fd1  mov     edi, eax
0x180057fd3  test    eax, eax
0x180057fd5  js      short loc_180057FF9
0x180057fd7  mov     rcx, [rbp+var_10]
0x180057fdb  test    rcx, rcx
0x180057fde  jnz     short loc_180057FE7
0x180057fe0  mov     edi, 0C00002B9h
0x180057fe5  jmp     short loc_180057FF9
0x180057fe7  mov     rax, [rbx+230h]
0x180057fee  mov     [rbp+var_10], rax
0x180057ff2  mov     [rbx+230h], rcx
0x180057ff9  lea     rcx, [rbp+var_10]
0x180057ffd  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180058002  test    edi, edi
0x180058004  jns     short loc_18005800D
0x180058006  mov     eax, edi
0x180058008  jmp     loc_1800583D6
0x18005800d  mov     rcx, [rbx+230h]
0x180058014  lea     rdi, [rbx+1F0h]
0x18005801b  mov     r8, [rsi+28h]
0x18005801f  lea     r9, [rbx+238h]
0x180058026  mov     rdx, [rsi+20h]
0x18005802a  mov     [rsp+80h+var_60], rdi
0x18005802f  mov     rax, [rcx]
0x180058032  mov     rax, [rax+10h]
0x180058036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005803b  test    eax, eax
0x18005803d  jns     short loc_1800580B6
0x18005803f  jmp     loc_1800583D6
0x180058044  cmp     byte ptr [rdx+30h], 0
0x180058048  lea     rdi, [rbx+1F0h]
0x18005804f  jz      short loc_18005806F
0x180058051  mov     rax, [rdx]
0x180058054  mov     [rdi], rax
0x180058057  mov     rax, [rdx+8]
0x18005805b  mov     [rbx+1F8h], rax
0x180058062  mov     rax, [rdx+10h]
0x180058066  mov     [rbx+200h], rax
0x18005806d  jmp     short loc_1800580B6
0x18005806f  mov     rdx, rdi
0x180058072  mov     rcx, rsi
0x180058075  call    RtlDuplicateLBlob
0x18005807a  test    eax, eax
0x18005807c  js      loc_1800583D6
0x180058082  mov     rcx, cs:?g_pTrackTypeDescription@Rtl@Windows@@3PEAVCRtlTrackTypeDescription@12@EA; Windows::Rtl::CRtlTrackTypeDescription * Windows::Rtl::g_pTrackTypeDescription
0x180058089  mov     byte ptr [rbx+228h], 1
0x180058090  test    rcx, rcx
0x180058093  jz      short loc_1800580B6
0x180058095  mov     rax, [rcx]
0x180058098  lea     rdx, aCmicrodomBlob; "CMicrodom_Blob"
0x18005809f  mov     r9d, [rdi]
0x1800580a2  mov     r8d, 1
0x1800580a8  mov     byte ptr [rsp+80h+var_60], 1
0x1800580ad  mov     rax, [rax+10h]
0x1800580b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580b6  cmp     qword ptr [rdi], 18h
0x1800580ba  jnb     short loc_1800580F7
0x1800580bc  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800580c3  mov     [rbp+var_40], 988h
0x1800580cb  mov     [rbp+var_50], rax
0x1800580cf  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800580d6  mov     [rbp+var_48], rax
0x1800580da  lea     rax, aMMicrodomdatab; "m_MicrodomDataBlob.Length >= sizeof(MIC"...
0x1800580e1  lea     rdx, [rbp+var_50]
0x1800580e5  mov     [rbp+var_38], rax
0x1800580e9  lea     rcx, [rbp+var_18]
0x1800580ed  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800580f2  jmp     loc_1800583D6
0x1800580f7  mov     rcx, [rbx+200h]; this
0x1800580fe  mov     eax, [rcx+4]
0x180058101  cmp     rax, [rdi]
0x180058104  jz      short loc_18005812D
0x180058106  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005810d  mov     [rbp+var_40], 98Bh
0x180058115  mov     [rbp+var_50], rax
0x180058119  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180058120  mov     [rbp+var_48], rax
0x180058124  lea     rax, aPheaderUltotal; "pHeader->ulTotalSize == m_MicrodomDataB"...
0x18005812b  jmp     short loc_1800580E1
0x18005812d  cmp     dword ptr [rcx], 6448644Dh
0x180058133  jz      short loc_18005815C
0x180058135  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005813c  mov     [rbp+var_40], 98Ch
0x180058144  mov     [rbp+var_50], rax
0x180058148  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x18005814f  mov     [rbp+var_48], rax
0x180058153  lea     rax, aPheaderUlsigna; "pHeader->ulSignature == ('dHdM')"
0x18005815a  jmp     short loc_1800580E1
0x18005815c  cmp     [rcx+0Ch], eax
0x18005815f  jb      short loc_18005818B
0x180058161  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058168  mov     [rbp+var_40], 98Dh
0x180058170  mov     [rbp+var_50], rax
0x180058174  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x18005817b  mov     [rbp+var_48], rax
0x18005817f  lea     rax, aPheaderUloffse; "pHeader->ulOffsetToDomLayout < pHeader-"...
0x180058186  jmp     loc_1800580E1
0x18005818b  cmp     [rcx+8], eax
0x18005818e  jb      short loc_1800581BA
0x180058190  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058197  mov     [rbp+var_40], 98Eh
0x18005819f  mov     [rbp+var_50], rax
0x1800581a3  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800581aa  mov     [rbp+var_48], rax
0x1800581ae  lea     rax, aPheaderUloffse_1; "pHeader->ulOffsetToStringPool < pHeader"...
0x1800581b5  jmp     loc_1800580E1
0x1800581ba  cmp     [rcx+10h], eax
0x1800581bd  jb      short loc_1800581E9
0x1800581bf  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800581c6  mov     [rbp+var_40], 98Fh
0x1800581ce  mov     [rbp+var_50], rax
0x1800581d2  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800581d9  mov     [rbp+var_48], rax
0x1800581dd  lea     rax, aPheaderUloffse_0; "pHeader->ulOffsetToPositionData < pHead"...
0x1800581e4  jmp     loc_1800580E1
0x1800581e9  lea     rax, [rbp+var_50]
0x1800581ed  mov     [rbx+220h], rcx
0x1800581f4  lea     r9, [rbp+var_20]; struct _MICRODOM_DOM_HEADER **
0x1800581f8  mov     [rsp+80h+var_60], rax; struct _MICRODOM_LOCATION_HEADER **
0x1800581fd  lea     r8, [rbp+var_28]; struct _MICRODOM_STRINGPOOL_HEADER **
0x180058201  lea     rdx, [rbp+var_30]; struct _MICRODOM_HEADER *
0x180058205  call    ?FindActualObjectPointers@MicrodomImplementation@@YAXPEBU_MICRODOM_HEADER@@PEAPEBU_MICRODOM_STRINGPOOL_HEADER@@PEAPEBU_MICRODOM_DOM_HEADER@@PEAPEBU_MICRODOM_LOCATION_HEADER@@PEAPEBU_MICRODOM_DOCTYPE_HEADER@@@Z; MicrodomImplementation::FindActualObjectPointers(_MICRODOM_HEADER const *,_MICRODOM_STRINGPOOL_HEADER const * *,_MICRODOM_DOM_HEADER const * *,_MICRODOM_LOCATION_HEADER const * *,_MICRODOM_DOCTYPE_HEADER const * *)
0x18005820a  mov     rdx, [rbp+var_30]; struct _MICRODOM_STRINGPOOL_HEADER *
0x18005820e  test    rdx, rdx
0x180058211  jz      short loc_18005825C
0x180058213  cmp     dword ptr [rdx], 7053644Dh
0x180058219  jz      short loc_18005825C
0x18005821b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058222  mov     [rbp+var_40], 99Fh
0x18005822a  mov     [rbp+var_50], rax
0x18005822e  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180058235  mov     [rbp+var_48], rax
0x180058239  lea     rax, aPstringpoolSig; "pStringPool->Signature == ('pSdM')"
0x180058240  mov     r8d, 0C000007Bh
0x180058246  mov     [rbp+var_38], rax
0x18005824a  lea     rdx, [rbp+var_50]
0x18005824e  lea     rcx, [rbp+var_18]
0x180058252  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180058257  jmp     loc_1800583D6
0x18005825c  mov     rsi, [rbp+var_28]
0x180058260  test    rsi, rsi
0x180058263  jz      short loc_180058294
0x180058265  cmp     dword ptr [rsi], 6C44644Dh
0x18005826b  jz      short loc_180058294
0x18005826d  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058274  mov     [rbp+var_40], 9A2h
0x18005827c  mov     [rbp+var_50], rax
0x180058280  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x180058287  mov     [rbp+var_48], rax
0x18005828b  lea     rax, aPdomlayoutUlsi; "pDomLayout->ulSignature == ('lDdM')"
0x180058292  jmp     short loc_180058240
0x180058294  mov     rdi, [rbp+var_50]
0x180058298  test    rdi, rdi
0x18005829b  jz      short loc_1800582CF
0x18005829d  cmp     dword ptr [rdi], 7444644Dh
0x1800582a3  jz      short loc_1800582CF
0x1800582a5  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800582ac  mov     [rbp+var_40], 9A5h
0x1800582b4  mov     [rbp+var_50], rax
0x1800582b8  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800582bf  mov     [rbp+var_48], rax
0x1800582c3  lea     rax, aPdoctypeUlsign; "pDoctype->ulSignature == ('tDdM')"
0x1800582ca  jmp     loc_180058240
0x1800582cf  lea     rcx, [rbx+20h]; this
0x1800582d3  call    ?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z; MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)
0x1800582d8  test    eax, eax
0x1800582da  js      loc_1800583D6
0x1800582e0  lea     rcx, [rbx+30h]; this
0x1800582e4  mov     rdx, rsi; struct _MICRODOM_DOM_HEADER *
0x1800582e7  call    ?Attach@CDomLayoutCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_DOM_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::Attach(_MICRODOM_DOM_HEADER const *)
0x1800582ec  test    eax, eax
0x1800582ee  js      loc_1800583D6
0x1800582f4  lea     rax, [rbx+0A0h]
0x1800582fb  cmp     [rbx+78h], rax
0x1800582ff  jz      short loc_18005830C
0x180058301  int     3; Trap to Debugger
0x180058302  mov     eax, 0C00000E5h
0x180058307  jmp     loc_1800583D6
0x18005830c  mov     rdx, [rbx+88h]
0x180058313  lea     rcx, [rbp+var_50]
0x180058317  mov     r8d, 5
0x18005831d  call    ?Multiply@?$CMultiplier@_KVCCallDisposition@Rtl@BUCL@@@Implementation@BUCL@@SA@_K0@Z; BUCL::Implementation::CMultiplier<unsigned __int64,BUCL::Rtl::CCallDisposition>::Multiply(unsigned __int64,unsigned __int64)
0x180058322  mov     rax, [rbp+var_50]
0x180058326  mov     [rbx+98h], rax
0x18005832d  mov     eax, dword ptr [rbp+var_48]
0x180058330  test    eax, eax
0x180058332  js      loc_1800583D6
0x180058338  lea     rax, [rdi+8]
0x18005833c  mov     [rbx+1C0h], rdi
0x180058343  mov     [rbx+1A8h], rax
0x18005834a  lea     rcx, [rbx+188h]
0x180058351  mov     [rbx+1B0h], rax
0x180058358  lea     rdx, [rbp+var_10]
0x18005835c  mov     r8d, [rdi+4]
0x180058360  call    ?Reserve@?$CVector@PEAU_MICRODOM_DOCTYPE_NODE_HEADER@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(unsigned __int64)
0x180058365  mov     eax, [rax]
0x180058367  test    eax, eax
0x180058369  js      short loc_1800583D6
0x18005836b  mov     rdx, [rbp+var_20]; struct _MICRODOM_LOCATION_HEADER *
0x18005836f  test    rdx, rdx
0x180058372  jz      short loc_180058384
0x180058374  lea     rcx, [rbx+1C8h]; this
0x18005837b  call    ?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z; MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)
0x180058380  test    eax, eax
0x180058382  js      short loc_1800583D6
0x180058384  mov     rax, [rbx+60h]
0x180058388  lea     rcx, [rbx+258h]
0x18005838f  mov     edx, [rax+8]
0x180058392  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@V?$Auto@U?$Vector@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@@2@@Windows@@QEAAPEAVCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>,Windows::Auto<Windows::Vector<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>>>::Allocate(unsigned __int64)
0x180058397  test    rax, rax
0x18005839a  jnz     short loc_1800583D4
0x18005839c  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800583a3  mov     [rbp+var_40], 9B5h
0x1800583ab  mov     [rbp+var_50], rax
0x1800583af  lea     rdx, [rbp+var_50]
0x1800583b3  lea     rax, aMicrodomimplem_20; "MicrodomImplementation::CMicrodom::Init"...
0x1800583ba  mov     [rbp+var_48], rax
0x1800583be  lea     rcx, [rbp+var_18]
0x1800583c2  lea     rax, aMPropertycache; "m_PropertyCache.Allocate(m_LayoutCache."...
0x1800583c9  mov     [rbp+var_38], rax
0x1800583cd  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800583d2  jmp     short loc_1800583D6
0x1800583d4  xor     eax, eax
0x1800583d6  mov     rcx, [rbp+var_8]
0x1800583da  xor     rcx, rsp; StackCookie
0x1800583dd  call    __security_check_cookie
0x1800583e2  mov     rbx, [rsp+80h+arg_10]
0x1800583ea  add     rsp, 80h
0x1800583f1  pop     rdi
0x1800583f2  pop     rsi
0x1800583f3  pop     rbp
0x1800583f4  retn
```
