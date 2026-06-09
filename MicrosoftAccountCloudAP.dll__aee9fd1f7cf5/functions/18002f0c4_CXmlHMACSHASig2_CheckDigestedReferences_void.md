# CXmlHMACSHASig2::CheckDigestedReferences(void)

- ea: `0x18002f0c4`
- end: `0x18002f1ba`
- name: `?CheckDigestedReferences@CXmlHMACSHASig2@@QEAAJXZ`
- size: `246`
- prototype: `__int64 __fastcall(CXmlHMACSHASig2 *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fb00`

## callees

- `0x18000d824`
- `0x180010830`
- `0x180026c8c`
- `0x18002e51c`
- `0x18002f0c4`
- `0x18002f28c`
- `0x18002f38c`
- `0x18002fa88`

## string_xrefs

- `0x18002f184`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig2.cpp`
- `0x18002f154`: `hr = ComputeReferenceDigest(xmlRef, strEncodedDigest)`
- `0x18002f168`: `!xmlRef.m_strText.IsEmpty() && !xmlRef.m_strDigestValue.IsEmpty()`
- `0x18002f17d`: `CXmlHMACSHASig2::CheckDigestedReferences`
- `0x18002f145`: `xmlRef.CompareDigest(strEncodedDigest)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXmlHMACSHASig2::CheckDigestedReferences(CXmlHMACSHASig2 *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  const char *v4; // rax
  unsigned int v5; // r8d
  _QWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v8; // [rsp+60h] [rbp+10h] BYREF

  v2 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v8);
  while ( *((_QWORD *)this + 2) )
  {
    ATL::CAtlList<CXmlReference2,ATL::CElementTraits<CXmlReference2>>::RemoveHead(this, v7);
    if ( !*(_DWORD *)(v7[0] - 16LL) || !*(_DWORD *)(v7[1] - 16LL) )
    {
      v2 = -2147216615;
      v4 = "!xmlRef.m_strText.IsEmpty() && !xmlRef.m_strDigestValue.IsEmpty()";
      v5 = 235;
      goto LABEL_11;
    }
    v2 = CXmlSig2::ComputeReferenceDigest(v3, v7, &v8);
    if ( v2 < 0 )
    {
      v4 = "hr = ComputeReferenceDigest(xmlRef, strEncodedDigest)";
      v5 = 237;
      goto LABEL_11;
    }
    if ( !(unsigned __int8)CXmlReference2::CompareDigest(v7, &v8) )
    {
      v2 = -2147216617;
      v4 = "xmlRef.CompareDigest(strEncodedDigest)";
      v5 = 239;
LABEL_11:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig2.cpp",
        "CXmlHMACSHASig2::CheckDigestedReferences",
        v5,
        v2,
        v4);
      CXmlReference2::~CXmlReference2((CXmlReference2 *)v7);
      break;
    }
    CXmlReference2::~CXmlReference2((CXmlReference2 *)v7);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002f0c4  mov     [rsp-8+arg_8], rbx
0x18002f0c9  mov     [rsp-8+arg_10], rdi
0x18002f0ce  push    rbp
0x18002f0cf  mov     rbp, rsp
0x18002f0d2  sub     rsp, 50h
0x18002f0d6  mov     rdi, rcx
0x18002f0d9  xor     ebx, ebx
0x18002f0db  lea     rcx, [rbp+arg_0]
0x18002f0df  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002f0e4  nop
0x18002f0e5  cmp     qword ptr [rdi+10h], 0
0x18002f0ea  jz      loc_18002F19B
0x18002f0f0  lea     rdx, [rbp+var_20]
0x18002f0f4  mov     rcx, rdi
0x18002f0f7  call    ?RemoveHead@?$CAtlList@VCXmlReference2@@V?$CElementTraits@VCXmlReference2@@@ATL@@@ATL@@QEAA?AVCXmlReference2@@XZ; ATL::CAtlList<CXmlReference2,ATL::CElementTraits<CXmlReference2>>::RemoveHead(void)
0x18002f0fc  nop
0x18002f0fd  mov     rax, [rbp+var_20]
0x18002f101  cmp     dword ptr [rax-10h], 0
0x18002f105  jz      short loc_18002F163
0x18002f107  mov     rax, [rbp+var_18]
0x18002f10b  cmp     dword ptr [rax-10h], 0
0x18002f10f  jz      short loc_18002F163
0x18002f111  lea     r8, [rbp+arg_0]
0x18002f115  lea     rdx, [rbp+var_20]
0x18002f119  call    ?ComputeReferenceDigest@CXmlSig2@@IEAAJAEBVCXmlReference2@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CXmlSig2::ComputeReferenceDigest(CXmlReference2 const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18002f11e  mov     ebx, eax
0x18002f120  test    eax, eax
0x18002f122  js      short loc_18002F154
0x18002f124  lea     rdx, [rbp+arg_0]
0x18002f128  lea     rcx, [rbp+var_20]
0x18002f12c  call    ?CompareDigest@CXmlReference2@@AEAA_NAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CXmlReference2::CompareDigest(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18002f131  test    al, al
0x18002f133  jz      short loc_18002F140
0x18002f135  lea     rcx, [rbp+var_20]; this
0x18002f139  call    ??1CXmlReference2@@QEAA@XZ; CXmlReference2::~CXmlReference2(void)
0x18002f13e  jmp     short loc_18002F0E5
0x18002f140  mov     ebx, 80041317h
0x18002f145  lea     rax, aXmlrefCompared; "xmlRef.CompareDigest(strEncodedDigest)"
0x18002f14c  mov     r8d, 0EFh
0x18002f152  jmp     short loc_18002F175
0x18002f154  lea     rax, aHrComputerefer; "hr = ComputeReferenceDigest(xmlRef, str"...
0x18002f15b  mov     r8d, 0EDh
0x18002f161  jmp     short loc_18002F175
0x18002f163  mov     ebx, 80041319h
0x18002f168  lea     rax, aXmlrefMStrtext; "!xmlRef.m_strText.IsEmpty() && !xmlRef."...
0x18002f16f  mov     r8d, 0EBh; unsigned int
0x18002f175  mov     [rsp+50h+var_30], rax; char *
0x18002f17a  mov     r9d, ebx; int
0x18002f17d  lea     rdx, aCxmlhmacshasig_2; "CXmlHMACSHASig2::CheckDigestedReference"...
0x18002f184  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18002f18b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002f190  nop
0x18002f191  lea     rcx, [rbp+var_20]; this
0x18002f195  call    ??1CXmlReference2@@QEAA@XZ; CXmlReference2::~CXmlReference2(void)
0x18002f19a  nop
0x18002f19b  mov     rcx, [rbp+arg_0]
0x18002f19f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002f1a3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002f1a8  mov     eax, ebx
0x18002f1aa  mov     rbx, [rsp+50h+arg_8]
0x18002f1af  mov     rdi, [rsp+50h+arg_10]
0x18002f1b4  add     rsp, 50h
0x18002f1b8  pop     rbp
0x18002f1b9  retn
```
