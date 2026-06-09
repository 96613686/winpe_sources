# CXmlSig2::ComputeReferenceDigest(CXmlReference2 const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18002f38c`
- end: `0x18002f3cd`
- name: `?ComputeReferenceDigest@CXmlSig2@@IEAAJAEBVCXmlReference2@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `65`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f0c4`

## callees

- `0x180026c8c`
- `0x18002f38c`
- `0x18002f3d4`

## string_xrefs

- `0x18002f3b9`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig2.cpp`
- `0x18002f3b2`: `CXmlSig2::ComputeReferenceDigest`
- `0x18002f39d`: `hr = ComputeSHADigest(xmlRef, strEncodedDigest)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CXmlSig2::ComputeReferenceDigest()
{
  int v0; // ebx

  v0 = CXmlSig2::ComputeSHADigest();
  if ( v0 < 0 )
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig2.cpp",
      "CXmlSig2::ComputeReferenceDigest",
      0xAFu,
      v0,
      "hr = ComputeSHADigest(xmlRef, strEncodedDigest)");
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002f38c  push    rbx
0x18002f38e  sub     rsp, 30h
0x18002f392  call    ?ComputeSHADigest@CXmlSig2@@AEAAJAEBVCXmlReference2@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CXmlSig2::ComputeSHADigest(CXmlReference2 const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18002f397  mov     ebx, eax
0x18002f399  test    eax, eax
0x18002f39b  jns     short loc_18002F3C5
0x18002f39d  lea     rax, aHrComputeshadi; "hr = ComputeSHADigest(xmlRef, strEncode"...
0x18002f3a4  mov     r9d, ebx; int
0x18002f3a7  mov     r8d, 0AFh; unsigned int
0x18002f3ad  mov     [rsp+38h+var_18], rax; char *
0x18002f3b2  lea     rdx, aCxmlsig2Comput; "CXmlSig2::ComputeReferenceDigest"
0x18002f3b9  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18002f3c0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002f3c5  mov     eax, ebx
0x18002f3c7  add     rsp, 30h
0x18002f3cb  pop     rbx
0x18002f3cc  retn
```
