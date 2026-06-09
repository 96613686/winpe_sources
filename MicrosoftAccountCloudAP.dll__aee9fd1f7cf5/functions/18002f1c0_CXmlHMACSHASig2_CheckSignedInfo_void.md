# CXmlHMACSHASig2::CheckSignedInfo(void)

- ea: `0x18002f1c0`
- end: `0x18002f284`
- name: `?CheckSignedInfo@CXmlHMACSHASig2@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(CXmlHMACSHASig2 *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fb00`

## callees

- `0x18000d824`
- `0x18000dc74`
- `0x180010830`
- `0x180026c8c`
- `0x18002f1c0`
- `0x18002f6cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x18002f224`
- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x18002f224`

## string_xrefs

- `0x18002f251`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig2.cpp`
- `0x18002f24a`: `CXmlHMACSHASig2::CheckSignedInfo`
- `0x18002f204`: `hr = GetHMACDigest(strComputedSigValue)`
- `0x18002f22f`: `strComputedSigValue == m_strSigValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXmlHMACSHASig2::CheckSignedInfo(CXmlHMACSHASig2 *this)
{
  const char *v2; // rax
  unsigned int v3; // r8d
  int HMACDigest; // ebx
  int v5; // r9d
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v7);
  if ( !*(_DWORD *)(*((_QWORD *)this + 10) - 16LL) )
  {
    v2 = "!m_strSigValue.IsEmpty()";
    v3 = 259;
LABEL_8:
    v5 = -2147216617;
    HMACDigest = -2147216617;
    goto LABEL_9;
  }
  HMACDigest = CXmlHMACSHASig2::GetHMACDigest(this, &v7);
  if ( HMACDigest < 0 )
  {
    v2 = "hr = GetHMACDigest(strComputedSigValue)";
    v5 = HMACDigest;
    v3 = 261;
LABEL_9:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig2.cpp",
      "CXmlHMACSHASig2::CheckSignedInfo",
      v3,
      v5,
      v2);
    goto LABEL_10;
  }
  if ( !*((_QWORD *)this + 10) )
    ATL::AtlThrowImpl(-2147467259);
  if ( (unsigned int)_o__mbscmp(v7) )
  {
    v2 = "strComputedSigValue == m_strSigValue";
    v3 = 263;
    goto LABEL_8;
  }
LABEL_10:
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
  return (unsigned int)HMACDigest;
}

```

## disassembly

```asm
0x18002f1c0  mov     [rsp+arg_8], rbx
0x18002f1c5  push    rdi
0x18002f1c6  sub     rsp, 30h
0x18002f1ca  mov     rdi, rcx
0x18002f1cd  lea     rcx, [rsp+38h+arg_0]
0x18002f1d2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002f1d7  nop
0x18002f1d8  mov     rax, [rdi+50h]
0x18002f1dc  cmp     dword ptr [rax-10h], 0
0x18002f1e0  jnz     short loc_18002F1F1
0x18002f1e2  lea     rax, aMStrsigvalueIs; "!m_strSigValue.IsEmpty()"
0x18002f1e9  mov     r8d, 103h
0x18002f1ef  jmp     short loc_18002F23C
0x18002f1f1  lea     rdx, [rsp+38h+arg_0]
0x18002f1f6  mov     rcx, rdi
0x18002f1f9  call    ?GetHMACDigest@CXmlHMACSHASig2@@QEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CXmlHMACSHASig2::GetHMACDigest(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18002f1fe  mov     ebx, eax
0x18002f200  test    eax, eax
0x18002f202  jns     short loc_18002F216
0x18002f204  lea     rax, aHrGethmacdiges; "hr = GetHMACDigest(strComputedSigValue)"
0x18002f20b  mov     r9d, ebx
0x18002f20e  mov     r8d, 105h
0x18002f214  jmp     short loc_18002F245
0x18002f216  mov     rdx, [rdi+50h]
0x18002f21a  test    rdx, rdx
0x18002f21d  jz      short loc_18002F279
0x18002f21f  mov     rcx, [rsp+38h+arg_0]
0x18002f224  call    cs:__imp__o__mbscmp
0x18002f22a  nop
0x18002f22b  test    eax, eax
0x18002f22d  jz      short loc_18002F25E
0x18002f22f  lea     rax, aStrcomputedsig; "strComputedSigValue == m_strSigValue"
0x18002f236  mov     r8d, 107h; unsigned int
0x18002f23c  mov     r9d, 80041317h; int
0x18002f242  mov     ebx, r9d
0x18002f245  mov     [rsp+38h+var_18], rax; char *
0x18002f24a  lea     rdx, aCxmlhmacshasig_1; "CXmlHMACSHASig2::CheckSignedInfo"
0x18002f251  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18002f258  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002f25d  nop
0x18002f25e  mov     rcx, [rsp+38h+arg_0]
0x18002f263  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002f267  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002f26c  mov     eax, ebx
0x18002f26e  mov     rbx, [rsp+38h+arg_8]
0x18002f273  add     rsp, 30h
0x18002f277  pop     rdi
0x18002f278  retn
0x18002f279  mov     ecx, 80004005h; int
0x18002f27e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
