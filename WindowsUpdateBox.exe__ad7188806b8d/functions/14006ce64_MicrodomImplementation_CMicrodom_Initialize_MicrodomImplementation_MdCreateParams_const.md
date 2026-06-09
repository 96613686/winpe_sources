# MicrodomImplementation::CMicrodom::Initialize(MicrodomImplementation::MdCreateParams const &)

- ea: `0x14006ce64`
- end: `0x14006d3a2`
- name: `?Initialize@CMicrodom@MicrodomImplementation@@QEAAJAEBUMdCreateParams@2@@Z`
- size: `1342`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *__hidden this, const struct MicrodomImplementation::MdCreateParams *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400663c8`

## callees

- `0x14006261c`
- `0x140066b74`
- `0x1400676b4`
- `0x1400678d0`
- `0x140067a94`
- `0x14006ce64`
- `0x14006d874`
- `0x140071644`
- `0x140072764`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14006d2ea`
- `KERNEL32!HeapAlloc` at `0x14006d2ea`
- `KERNEL32!GetProcessHeap` at `0x14006d2d6`
- `KERNEL32!GetProcessHeap` at `0x14006d2d6`

## string_xrefs

- `0x14006cfb6`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d007`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d036`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d065`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d094`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d0c3`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d138`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d187`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d1bb`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d344`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006d36c`: `m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::Initialize(
        MicrodomImplementation::CMicrodom *this,
        const struct MicrodomImplementation::MdCreateParams *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  void (__fastcall ***v7)(_QWORD); // rdx
  __int64 result; // rax
  _QWORD *v9; // rbx
  struct Windows::Rtl::CRtlTrackTypeDescription *v10; // rcx
  const char *v11; // rax
  _DWORD *v12; // rax
  __int64 v13; // rcx
  const struct _MICRODOM_STRINGPOOL_HEADER *v14; // rdx
  const struct _MICRODOM_DOM_HEADER *v15; // rsi
  const struct _MICRODOM_LOCATION_HEADER *v16; // r14
  _DWORD *v17; // rbx
  const char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned __int64 v21; // r14
  __int64 v22; // rbx
  bool v23; // cf
  SIZE_T v24; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v26; // rax
  __int64 v27; // rsi
  MicrodomImplementation::CMicrodom::CPropertyCacheEntry *v28; // r15
  __int64 v29; // rbx
  const char *v30; // [rsp+30h] [rbp-30h] BYREF
  const char *v31; // [rsp+38h] [rbp-28h]
  __int64 v32; // [rsp+40h] [rbp-20h]
  const char *v33; // [rsp+48h] [rbp-18h]
  void (__fastcall ***v34)(_QWORD); // [rsp+50h] [rbp-10h] BYREF

  v4 = (__int64 *)*((_QWORD *)a2 + 3);
  if ( v4 )
  {
    v5 = *v4;
    v34 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, GUID *, void (__fastcall ****)(_QWORD)))(v5 + 8))(
           v4,
           &GUID_31257d4b_3df7_46f9_86c5_1c76711e334e,
           &v34);
    if ( v6 < 0 )
    {
      v7 = v34;
    }
    else
    {
      if ( !v34 )
        return (unsigned int)-1073741127;
      v7 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 70);
      *((_QWORD *)this + 70) = v34;
    }
    if ( v7 )
    {
      v34 = 0;
      (**v7)(v7);
    }
    if ( v6 < 0 )
      return (unsigned int)v6;
    v9 = (_QWORD *)((char *)this + 496);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, char *))(**((_QWORD **)this + 70) + 16LL))(
               *((_QWORD *)this + 70),
               *((_QWORD *)a2 + 4),
               *((_QWORD *)a2 + 5),
               (char *)this + 568,
               (char *)this + 496);
    if ( (int)result < 0 )
      return result;
  }
  else
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
  }
  if ( *v9 < 0x18u )
  {
    v32 = 2440;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "m_MicrodomDataBlob.Length >= sizeof(MICRODOM_HEADER)";
LABEL_20:
    v33 = v11;
    RtlReportErrorOrigination(&v30, a2, 3221225485LL);
    return 3221225485LL;
  }
  v12 = (_DWORD *)*((_QWORD *)this + 64);
  v13 = (unsigned int)v12[1];
  if ( v13 != *v9 )
  {
    v32 = 2443;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "pHeader->ulTotalSize == m_MicrodomDataBlob.Length";
    goto LABEL_20;
  }
  if ( *v12 != 1682465869 )
  {
    v32 = 2444;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "pHeader->ulSignature == ('dHdM')";
    goto LABEL_20;
  }
  if ( v12[3] >= (unsigned int)v13 )
  {
    v32 = 2445;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "pHeader->ulOffsetToDomLayout < pHeader->ulTotalSize";
    goto LABEL_20;
  }
  if ( v12[2] >= (unsigned int)v13 )
  {
    v32 = 2446;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "pHeader->ulOffsetToStringPool < pHeader->ulTotalSize";
    goto LABEL_20;
  }
  if ( v12[4] >= (unsigned int)v13 )
  {
    v32 = 2447;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v11 = "pHeader->ulOffsetToPositionData < pHeader->ulTotalSize";
    goto LABEL_20;
  }
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
  if ( v14 && *(_DWORD *)v14 != 1884513357 )
  {
    v32 = 2463;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v18 = "pStringPool->Signature == ('pSdM')";
LABEL_42:
    v33 = v18;
    RtlReportErrorOrigination(&v30, v14, 3221225595LL);
    return 3221225595LL;
  }
  if ( v15 && *(_DWORD *)v15 != 1816421453 )
  {
    v32 = 2466;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v18 = "pDomLayout->ulSignature == ('lDdM')";
    goto LABEL_42;
  }
  if ( v17 && *v17 != 1950639181 )
  {
    v32 = 2469;
    v30 = "onecore\\base\\xml\\udom_microdom.cpp";
    v31 = "MicrodomImplementation::CMicrodom::Initialize";
    v18 = "pDoctype->ulSignature == ('tDdM')";
    goto LABEL_42;
  }
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
      if ( *((MicrodomImplementation::CMicrodom **)this + 15) != (MicrodomImplementation::CMicrodom *)((char *)this + 160) )
      {
        __debugbreak();
        return 3221225701LL;
      }
      BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
        (unsigned int *)&v34,
        *((_QWORD *)this + 17),
        5u,
        (unsigned __int64 *)this + 19);
      result = (unsigned int)v34;
      if ( (int)v34 >= 0 )
      {
        *((_QWORD *)this + 56) = v17;
        *((_QWORD *)this + 53) = v17 + 2;
        *((_QWORD *)this + 54) = v17 + 2;
        result = *(unsigned int *)BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(
                                    (char *)this + 392,
                                    &v34,
                                    (unsigned int)v17[1]);
        if ( (int)result >= 0 )
        {
          if ( !v16
            || (result = MicrodomImplementation::CDomPositionCache::AttachToPositionList(
                           (MicrodomImplementation::CMicrodom *)((char *)this + 456),
                           v16),
                (int)result >= 0) )
          {
            v20 = *((_QWORD *)this + 12);
            v21 = *(unsigned int *)(v20 + 8);
            if ( *((_QWORD *)this + 75) )
              goto LABEL_72;
            if ( *(_DWORD *)(v20 + 8) )
            {
              v22 = 152 * v21;
              if ( !is_mul_ok(v21, 0x98u) )
                v22 = -1;
              v23 = __CFADD__(v22, 8);
              v24 = v22 + 8;
              if ( v23 )
                v24 = -1;
              ProcessHeap = GetProcessHeap();
              v26 = HeapAlloc(ProcessHeap, 0, v24);
              if ( v26 )
              {
                v27 = (__int64)(v26 + 1);
                *v26 = v21;
                v28 = (MicrodomImplementation::CMicrodom::CPropertyCacheEntry *)(v26 + 1);
                v29 = (unsigned int)v21;
                do
                {
                  MicrodomImplementation::CMicrodom::CPropertyCacheEntry::CPropertyCacheEntry(v28);
                  v28 = (MicrodomImplementation::CMicrodom::CPropertyCacheEntry *)((char *)v28 + 152);
                  --v29;
                }
                while ( v29 );
                if ( v27 )
                {
                  *((_QWORD *)this + 75) = v27;
                  *((_QWORD *)this + 76) = v21;
                  goto LABEL_70;
                }
LABEL_72:
                v32 = 2485;
                v30 = "onecore\\base\\xml\\udom_microdom.cpp";
                v31 = "MicrodomImplementation::CMicrodom::Initialize";
                v33 = "m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())";
                RtlReportErrorOrigination(&v30, v19, 3221225495LL);
                return 3221225495LL;
              }
              v27 = 0;
            }
            else
            {
              v27 = 8;
            }
LABEL_70:
            if ( v27 )
              return 0;
            goto LABEL_72;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14006ce64  mov     [rsp-28h+arg_10], rbx
0x14006ce69  push    rbp
0x14006ce6a  push    rsi
0x14006ce6b  push    rdi
0x14006ce6c  push    r14
0x14006ce6e  push    r15
0x14006ce70  mov     rbp, rsp
0x14006ce73  sub     rsp, 60h
0x14006ce77  mov     rax, cs:__security_cookie
0x14006ce7e  xor     rax, rsp
0x14006ce81  mov     [rbp+var_8], rax
0x14006ce85  mov     rdi, rcx
0x14006ce88  mov     rsi, rdx
0x14006ce8b  mov     rcx, [rdx+18h]
0x14006ce8f  test    rcx, rcx
0x14006ce92  jz      loc_14006CF3E
0x14006ce98  mov     rax, [rcx]
0x14006ce9b  lea     r8, [rbp+var_10]
0x14006ce9f  lea     rdx, _GUID_31257d4b_3df7_46f9_86c5_1c76711e334e
0x14006cea6  mov     [rbp+var_10], 0
0x14006ceae  mov     rax, [rax+8]
0x14006ceb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ceb7  mov     ebx, eax
0x14006ceb9  test    eax, eax
0x14006cebb  js      short loc_14006CEDD
0x14006cebd  mov     rcx, [rbp+var_10]
0x14006cec1  test    rcx, rcx
0x14006cec4  jnz     short loc_14006CECD
0x14006cec6  mov     ebx, 0C00002B9h
0x14006cecb  jmp     short loc_14006CF00
0x14006cecd  mov     rdx, [rdi+230h]
0x14006ced4  mov     [rdi+230h], rcx
0x14006cedb  jmp     short loc_14006CEE1
0x14006cedd  mov     rdx, [rbp+var_10]
0x14006cee1  test    rdx, rdx
0x14006cee4  jz      short loc_14006CEFC
0x14006cee6  mov     [rbp+var_10], 0
0x14006ceee  mov     rcx, rdx
0x14006cef1  mov     rax, [rdx]
0x14006cef4  mov     rax, [rax]
0x14006cef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006cefc  test    ebx, ebx
0x14006cefe  jns     short loc_14006CF07
0x14006cf00  mov     eax, ebx
0x14006cf02  jmp     loc_14006D381
0x14006cf07  mov     rcx, [rdi+230h]
0x14006cf0e  lea     rbx, [rdi+1F0h]
0x14006cf15  mov     r8, [rsi+28h]
0x14006cf19  lea     r9, [rdi+238h]
0x14006cf20  mov     rdx, [rsi+20h]
0x14006cf24  mov     [rsp+60h+var_40], rbx
0x14006cf29  mov     rax, [rcx]
0x14006cf2c  mov     rax, [rax+10h]
0x14006cf30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006cf35  test    eax, eax
0x14006cf37  jns     short loc_14006CFB0
0x14006cf39  jmp     loc_14006D381
0x14006cf3e  cmp     byte ptr [rdx+30h], 0
0x14006cf42  lea     rbx, [rdi+1F0h]
0x14006cf49  jz      short loc_14006CF69
0x14006cf4b  mov     rax, [rdx]
0x14006cf4e  mov     [rbx], rax
0x14006cf51  mov     rax, [rdx+8]
0x14006cf55  mov     [rdi+1F8h], rax
0x14006cf5c  mov     rax, [rdx+10h]
0x14006cf60  mov     [rdi+200h], rax
0x14006cf67  jmp     short loc_14006CFB0
0x14006cf69  mov     rdx, rbx
0x14006cf6c  mov     rcx, rsi
0x14006cf6f  call    RtlDuplicateLBlob
0x14006cf74  test    eax, eax
0x14006cf76  js      loc_14006D381
0x14006cf7c  mov     rcx, cs:?g_pTrackTypeDescription@Rtl@Windows@@3PEAVCRtlTrackTypeDescription@12@EA; Windows::Rtl::CRtlTrackTypeDescription * Windows::Rtl::g_pTrackTypeDescription
0x14006cf83  mov     byte ptr [rdi+228h], 1
0x14006cf8a  test    rcx, rcx
0x14006cf8d  jz      short loc_14006CFB0
0x14006cf8f  mov     rax, [rcx]
0x14006cf92  lea     rdx, aCmicrodomBlob; "CMicrodom_Blob"
0x14006cf99  mov     r9d, [rbx]
0x14006cf9c  mov     r8d, 1
0x14006cfa2  mov     byte ptr [rsp+60h+var_40], 1
0x14006cfa7  mov     rax, [rax+10h]
0x14006cfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006cfb0  cmp     qword ptr [rbx], 18h
0x14006cfb4  jnb     short loc_14006CFF8
0x14006cfb6  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006cfbd  mov     [rbp+var_20], 988h
0x14006cfc5  mov     [rbp+var_30], rax
0x14006cfc9  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006cfd0  mov     [rbp+var_28], rax
0x14006cfd4  lea     rax, aMMicrodomdatab; "m_MicrodomDataBlob.Length >= sizeof(MIC"...
0x14006cfdb  mov     r8d, 0C000000Dh
0x14006cfe1  mov     [rbp+var_18], rax
0x14006cfe5  lea     rcx, [rbp+var_30]
0x14006cfe9  call    RtlReportErrorOrigination
0x14006cfee  mov     eax, 0C000000Dh
0x14006cff3  jmp     loc_14006D381
0x14006cff8  mov     rax, [rdi+200h]
0x14006cfff  mov     ecx, [rax+4]
0x14006d002  cmp     rcx, [rbx]
0x14006d005  jz      short loc_14006D02E
0x14006d007  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d00e  mov     [rbp+var_20], 98Bh
0x14006d016  mov     [rbp+var_30], rax
0x14006d01a  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d021  mov     [rbp+var_28], rax
0x14006d025  lea     rax, aPheaderUltotal; "pHeader->ulTotalSize == m_MicrodomDataB"...
0x14006d02c  jmp     short loc_14006CFDB
0x14006d02e  cmp     dword ptr [rax], 6448644Dh
0x14006d034  jz      short loc_14006D060
0x14006d036  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d03d  mov     [rbp+var_20], 98Ch
0x14006d045  mov     [rbp+var_30], rax
0x14006d049  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d050  mov     [rbp+var_28], rax
0x14006d054  lea     rax, aPheaderUlsigna; "pHeader->ulSignature == ('dHdM')"
0x14006d05b  jmp     loc_14006CFDB
0x14006d060  cmp     [rax+0Ch], ecx
0x14006d063  jb      short loc_14006D08F
0x14006d065  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d06c  mov     [rbp+var_20], 98Dh
0x14006d074  mov     [rbp+var_30], rax
0x14006d078  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d07f  mov     [rbp+var_28], rax
0x14006d083  lea     rax, aPheaderUloffse; "pHeader->ulOffsetToDomLayout < pHeader-"...
0x14006d08a  jmp     loc_14006CFDB
0x14006d08f  cmp     [rax+8], ecx
0x14006d092  jb      short loc_14006D0BE
0x14006d094  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d09b  mov     [rbp+var_20], 98Eh
0x14006d0a3  mov     [rbp+var_30], rax
0x14006d0a7  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d0ae  mov     [rbp+var_28], rax
0x14006d0b2  lea     rax, aPheaderUloffse_1; "pHeader->ulOffsetToStringPool < pHeader"...
0x14006d0b9  jmp     loc_14006CFDB
0x14006d0be  cmp     [rax+10h], ecx
0x14006d0c1  jb      short loc_14006D0ED
0x14006d0c3  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d0ca  mov     [rbp+var_20], 98Fh
0x14006d0d2  mov     [rbp+var_30], rax
0x14006d0d6  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d0dd  mov     [rbp+var_28], rax
0x14006d0e1  lea     rax, aPheaderUloffse_0; "pHeader->ulOffsetToPositionData < pHead"...
0x14006d0e8  jmp     loc_14006CFDB
0x14006d0ed  xor     edx, edx
0x14006d0ef  mov     [rdi+220h], rax
0x14006d0f6  cmp     [rax+8], edx
0x14006d0f9  jz      short loc_14006D101
0x14006d0fb  mov     edx, [rax+8]
0x14006d0fe  add     rdx, rax; struct _MICRODOM_STRINGPOOL_HEADER *
0x14006d101  xor     esi, esi
0x14006d103  cmp     [rax+0Ch], esi
0x14006d106  jz      short loc_14006D10E
0x14006d108  mov     esi, [rax+0Ch]
0x14006d10b  add     rsi, rax
0x14006d10e  xor     r14d, r14d
0x14006d111  cmp     [rax+10h], r14d
0x14006d115  jz      short loc_14006D11E
0x14006d117  mov     r14d, [rax+10h]
0x14006d11b  add     r14, rax
0x14006d11e  xor     ebx, ebx
0x14006d120  cmp     [rax+14h], ebx
0x14006d123  jz      short loc_14006D12B
0x14006d125  mov     ebx, [rax+14h]
0x14006d128  add     rbx, rax
0x14006d12b  test    rdx, rdx
0x14006d12e  jz      short loc_14006D17A
0x14006d130  cmp     dword ptr [rdx], 7053644Dh
0x14006d136  jz      short loc_14006D17A
0x14006d138  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d13f  mov     [rbp+var_20], 99Fh
0x14006d147  mov     [rbp+var_30], rax
0x14006d14b  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d152  mov     [rbp+var_28], rax
0x14006d156  lea     rax, aPstringpoolSig; "pStringPool->Signature == ('pSdM')"
0x14006d15d  mov     r8d, 0C000007Bh
0x14006d163  mov     [rbp+var_18], rax
0x14006d167  lea     rcx, [rbp+var_30]
0x14006d16b  call    RtlReportErrorOrigination
0x14006d170  mov     eax, 0C000007Bh
0x14006d175  jmp     loc_14006D381
0x14006d17a  test    rsi, rsi
0x14006d17d  jz      short loc_14006D1AE
0x14006d17f  cmp     dword ptr [rsi], 6C44644Dh
0x14006d185  jz      short loc_14006D1AE
0x14006d187  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d18e  mov     [rbp+var_20], 9A2h
0x14006d196  mov     [rbp+var_30], rax
0x14006d19a  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d1a1  mov     [rbp+var_28], rax
0x14006d1a5  lea     rax, aPdomlayoutUlsi; "pDomLayout->ulSignature == ('lDdM')"
0x14006d1ac  jmp     short loc_14006D15D
0x14006d1ae  test    rbx, rbx
0x14006d1b1  jz      short loc_14006D1E5
0x14006d1b3  cmp     dword ptr [rbx], 7444644Dh
0x14006d1b9  jz      short loc_14006D1E5
0x14006d1bb  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d1c2  mov     [rbp+var_20], 9A5h
0x14006d1ca  mov     [rbp+var_30], rax
0x14006d1ce  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d1d5  mov     [rbp+var_28], rax
0x14006d1d9  lea     rax, aPdoctypeUlsign; "pDoctype->ulSignature == ('tDdM')"
0x14006d1e0  jmp     loc_14006D15D
0x14006d1e5  lea     rcx, [rdi+20h]; this
0x14006d1e9  call    ?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z; MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)
0x14006d1ee  test    eax, eax
0x14006d1f0  js      loc_14006D381
0x14006d1f6  lea     rcx, [rdi+30h]; this
0x14006d1fa  mov     rdx, rsi; struct _MICRODOM_DOM_HEADER *
0x14006d1fd  call    ?Attach@CDomLayoutCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_DOM_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::Attach(_MICRODOM_DOM_HEADER const *)
0x14006d202  test    eax, eax
0x14006d204  js      loc_14006D381
0x14006d20a  lea     rax, [rdi+0A0h]
0x14006d211  cmp     [rdi+78h], rax
0x14006d215  jz      short loc_14006D222
0x14006d217  int     3; Trap to Debugger
0x14006d218  mov     eax, 0C00000E5h
0x14006d21d  jmp     loc_14006D381
0x14006d222  mov     rdx, [rdi+88h]
0x14006d229  lea     r9, [rdi+98h]
0x14006d230  mov     r8d, 5
0x14006d236  lea     rcx, [rbp+var_10]
0x14006d23a  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x14006d23f  mov     eax, dword ptr [rbp+var_10]
0x14006d242  test    eax, eax
0x14006d244  js      loc_14006D381
0x14006d24a  lea     rax, [rbx+8]
0x14006d24e  mov     [rdi+1C0h], rbx
0x14006d255  mov     [rdi+1A8h], rax
0x14006d25c  lea     rcx, [rdi+188h]
0x14006d263  mov     [rdi+1B0h], rax
0x14006d26a  lea     rdx, [rbp+var_10]
0x14006d26e  mov     r8d, [rbx+4]
0x14006d272  call    ?Reserve@?$CVector@PEAU_MICRODOM_DOCTYPE_NODE_HEADER@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(unsigned __int64)
0x14006d277  mov     eax, [rax]
0x14006d279  test    eax, eax
0x14006d27b  js      loc_14006D381
0x14006d281  test    r14, r14
0x14006d284  jz      short loc_14006D29D
0x14006d286  lea     rcx, [rdi+1C8h]; this
0x14006d28d  mov     rdx, r14; struct _MICRODOM_LOCATION_HEADER *
0x14006d290  call    ?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z; MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)
0x14006d295  test    eax, eax
0x14006d297  js      loc_14006D381
0x14006d29d  cmp     qword ptr [rdi+258h], 0
0x14006d2a5  mov     rax, [rdi+60h]
0x14006d2a9  mov     r14d, [rax+8]
0x14006d2ad  jnz     loc_14006D344
0x14006d2b3  test    r14, r14
0x14006d2b6  jz      short loc_14006D336
0x14006d2b8  mov     eax, 98h
0x14006d2bd  mul     r14
0x14006d2c0  mov     rbx, rax
0x14006d2c3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14006d2ca  cmovb   rbx, rax
0x14006d2ce  add     rbx, 8
0x14006d2d2  cmovb   rbx, rax
0x14006d2d6  call    cs:__imp_GetProcessHeap
0x14006d2dd  nop     dword ptr [rax+rax+00h]
0x14006d2e2  mov     r8, rbx; dwBytes
0x14006d2e5  xor     edx, edx; dwFlags
0x14006d2e7  mov     rcx, rax; hHeap
0x14006d2ea  call    cs:__imp_HeapAlloc
0x14006d2f1  nop     dword ptr [rax+rax+00h]
0x14006d2f6  test    rax, rax
0x14006d2f9  jz      short loc_14006D332
0x14006d2fb  lea     rsi, [rax+8]
0x14006d2ff  mov     [rax], r14
0x14006d302  mov     r15, rsi
0x14006d305  mov     ebx, r14d
0x14006d308  mov     rcx, r15; this
0x14006d30b  call    ??0CPropertyCacheEntry@CMicrodom@MicrodomImplementation@@QEAA@XZ; MicrodomImplementation::CMicrodom::CPropertyCacheEntry::CPropertyCacheEntry(void)
0x14006d310  add     r15, 98h
0x14006d317  sub     rbx, 1
0x14006d31b  jnz     short loc_14006D308
0x14006d31d  test    rsi, rsi
0x14006d320  jz      short loc_14006D344
0x14006d322  mov     [rdi+258h], rsi
0x14006d329  mov     [rdi+260h], r14
0x14006d330  jmp     short loc_14006D33B
0x14006d332  xor     esi, esi
0x14006d334  jmp     short loc_14006D33B
0x14006d336  mov     esi, 8
0x14006d33b  test    rsi, rsi
0x14006d33e  jz      short loc_14006D344
0x14006d340  xor     eax, eax
0x14006d342  jmp     short loc_14006D381
0x14006d344  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006d34b  mov     [rbp+var_20], 9B5h
0x14006d353  mov     [rbp+var_30], rax
0x14006d357  lea     rcx, [rbp+var_30]
0x14006d35b  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CMicrodom::Init"...
0x14006d362  mov     r8d, 0C0000017h
0x14006d368  mov     [rbp+var_28], rax
0x14006d36c  lea     rax, aMPropertycache; "m_PropertyCache.Allocate(m_LayoutCache."...
0x14006d373  mov     [rbp+var_18], rax
0x14006d377  call    RtlReportErrorOrigination
0x14006d37c  mov     eax, 0C0000017h
0x14006d381  mov     rcx, [rbp+var_8]
0x14006d385  xor     rcx, rsp; StackCookie
  ... truncated ...
```
