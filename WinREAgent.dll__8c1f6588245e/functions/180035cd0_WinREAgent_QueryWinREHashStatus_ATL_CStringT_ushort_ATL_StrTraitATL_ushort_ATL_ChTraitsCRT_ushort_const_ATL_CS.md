# WinREAgent::QueryWinREHashStatus(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool &,bool &,bool &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180035cd0`
- end: `0x180036199`
- name: `?QueryWinREHashStatus@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEA_N11PEAV23@@Z`
- size: `1225`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b050`
- `0x18002b5e0`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002a90c`
- `0x180035cd0`
- `0x1800361a0`
- `0x18003717c`
- `0x180037344`
- `0x180054cc4`
- `0x180054e80`
- `0x180054f80`
- `0x180054ff8`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180035e4c`
- `KERNEL32!GetLastError` at `0x180035e8d`
- `KERNEL32!GetLastError` at `0x180035f8d`
- `KERNEL32!GetLastError` at `0x180035fc9`
- `KERNEL32!GetLastError` at `0x180035e4c`
- `KERNEL32!GetLastError` at `0x180035e8d`
- `KERNEL32!GetLastError` at `0x180035f8d`
- `KERNEL32!GetLastError` at `0x180035fc9`
- `ReAgent!WinReGetConfig` at `0x180035f83`
- `ReAgent!WinReGetConfig` at `0x180035f83`
- `ReAgent!WinReHashWimFile` at `0x180035e3f`
- `ReAgent!WinReHashWimFile` at `0x180035e3f`

## string_xrefs

- `0x180035d55`: `WinRE path:    [%s]`
- `0x180035daf`: `base\diagnosis\srt\winreagent\lib\api\src\validation.cpp`
- `0x180035dec`: `base\diagnosis\srt\winreagent\lib\api\src\validation.cpp`
- `0x180035db6`: `WinREAgent::QueryWinREHashStatus`
- `0x180035df3`: `WinREAgent::QueryWinREHashStatus`
- `0x180035fa3`: `Failed to get WinRE config`
- `0x180035fed`: `No hash in WinRE config`
- `0x180036069`: `Encoded WinRE config hash: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::QueryWinREHashStatus(_QWORD *a1, __int64 *a2, bool *a3, bool *a4, bool *a5, _QWORD *a6)
{
  __int64 v10; // rax
  signed int v11; // esi
  PushButtonReset::BitLocker *v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  signed int v15; // eax
  signed int v16; // eax
  __int64 v17; // rdx
  ATL::CStringData *v18; // rcx
  __int64 v19; // rdi
  signed int LastError; // eax
  signed int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rbx
  const wchar_t *v24; // rbx
  const wchar_t *v25; // r8
  const wchar_t *v26; // r8
  _QWORD *v27; // rcx
  int *v28; // r14
  __int64 v29; // rbx
  _QWORD *v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  bool *v33; // [rsp+50h] [rbp-B0h]
  _QWORD v34[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v35[387]; // [rsp+70h] [rbp-90h] BYREF
  char v36[648]; // [rsp+C88h] [rbp+B88h] BYREF
  _OWORD v37[2]; // [rsp+F10h] [rbp+E10h] BYREF

  v33 = a3;
  v31 = a1;
  memset_0(v35, 0, 0xEA0u);
  PushButtonReset::Logging::Trace(0, L"Query WinRE hash status");
  PushButtonReset::Logging::Trace(0, L"Target volume: [%s]", *a1);
  PushButtonReset::Logging::Trace(0, L"WinRE path:    [%s]", *a2);
  v34[1] = 0;
  v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::`vftable';
  v10 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v34);
  v11 = PushButtonReset::BitLocker::Open(a1, v10);
  if ( v11 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v11,
      "WinREAgent::QueryWinREHashStatus",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
      52,
      L"Failed to get encryption information for [%s]",
      *a1);
    goto LABEL_41;
  }
  v12 = (PushButtonReset::BitLocker *)(*(__int64 (__fastcall **)(_QWORD *))(v34[0] + 24LL))(v34);
  v13 = PushButtonReset::BitLocker::CheckActive(v12, a3);
  if ( v13 < 0 )
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v13,
      "WinREAgent::QueryWinREHashStatus",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
      57,
      L"Failed to check if BitLocker is active, assume not");
  memset(v37, 0, sizeof(v37));
  if ( (unsigned int)WinReHashWimFile(*a2, v37) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v32);
    v11 = PushButtonReset::Encode::EncodeBase64(v37, v17, &v32);
    if ( v11 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "WinREAgent::QueryWinREHashStatus",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
        69,
        L"Failed to encode hash");
      v18 = (ATL::CStringData *)(v32 - 24);
LABEL_40:
      ATL::CStringData::Release(v18);
      goto LABEL_41;
    }
    v19 = v32;
    if ( *v33 )
    {
      v11 = PushButtonReset::BitLocker::CheckIsWimTrusted(v31, v37, 32, a4);
      if ( v11 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v11,
          "WinREAgent::QueryWinREHashStatus",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
          81,
          L"Failed to check if wim is trusted, assume not");
        v11 = 0;
        *a4 = 0;
      }
      *a5 = *a4;
    }
    else
    {
      *a4 = 0;
      PushButtonReset::Logging::Trace(0, L"BitLocker is not active, assume wim is not trusted");
      v35[0] = 3744;
      if ( !(unsigned int)WinReGetConfig(0, v35) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "WinREAgent::QueryWinREHashStatus",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
          98,
          L"Failed to get WinRE config");
        v21 = GetLastError();
        v11 = v21;
        if ( v21 > 0 )
          v11 = (unsigned __int16)v21 | 0x80070000;
        goto LABEL_39;
      }
      if ( v36[0] )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v31);
        v11 = PushButtonReset::Encode::EncodeBase64(v36, v22, &v31);
        if ( v11 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v11,
            "WinREAgent::QueryWinREHashStatus",
            "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
            110,
            L"Failed to encode validated hash");
          ATL::CStringData::Release((ATL::CStringData *)(v31 - 3));
LABEL_39:
          v18 = (ATL::CStringData *)(v19 - 24);
          goto LABEL_40;
        }
        v23 = v31;
        PushButtonReset::Logging::Trace(0, L"Encoded WinRE config hash: [%s]", v31);
        PushButtonReset::Logging::Trace(0, L"Input WinRE hash:          [%s]", v19);
        *a5 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(&v31) == 0;
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 3));
      }
      else
      {
        PushButtonReset::Logging::Trace(0, L"No hash in WinRE config");
        *a5 = 0;
      }
    }
    v24 = L"true";
    v25 = L"true";
    if ( !*v33 )
      v25 = L"false";
    PushButtonReset::Logging::Trace(0, L"Is BitLocker active: %s", v25);
    v26 = L"true";
    if ( !*a4 )
      v26 = L"false";
    PushButtonReset::Logging::Trace(0, L"Is hash trusted:   %s", v26);
    if ( !*a5 )
      v24 = L"false";
    PushButtonReset::Logging::Trace(0, L"Is hash validated: %s", v24);
    if ( a6 )
    {
      v27 = (_QWORD *)(v19 - 24);
      v28 = (int *)(*a6 - 24LL);
      if ( (int *)(v19 - 24) != v28 )
      {
        if ( v28[4] >= 0 && *v27 == *(_QWORD *)v28 )
        {
          v29 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v27);
          ATL::CStringData::Release((ATL::CStringData *)v28);
          *a6 = v29 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a6, v19, *(unsigned int *)(v19 - 16));
        }
      }
    }
    goto LABEL_39;
  }
  v14 = *a2;
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v15,
    "WinREAgent::QueryWinREHashStatus",
    "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
    64,
    L"Failed to hash wim file [%s]",
    v14);
  v16 = GetLastError();
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  v11 = v16;
LABEL_41:
  v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::Release(v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180035cd0  push    rbp
0x180035cd2  push    rbx
0x180035cd3  push    rsi
0x180035cd4  push    rdi
0x180035cd5  push    r12
0x180035cd7  push    r13
0x180035cd9  push    r14
0x180035cdb  push    r15
0x180035cdd  lea     rbp, [rsp-0E48h]
0x180035ce5  sub     rsp, 0F48h
0x180035cec  mov     rax, cs:__security_cookie
0x180035cf3  xor     rax, rsp
0x180035cf6  mov     [rbp+0E80h+var_50], rax
0x180035cfd  mov     r15, r9
0x180035d00  mov     r14, r8
0x180035d03  mov     [rsp+0F80h+var_F30], r8
0x180035d08  mov     rdi, rdx
0x180035d0b  mov     rbx, rcx
0x180035d0e  mov     [rsp+0F80h+var_F40], rcx
0x180035d13  mov     r12, [rbp+0E80h+arg_28]
0x180035d1a  mov     r13, [rbp+0E80h+arg_20]
0x180035d21  xor     edx, edx; Val
0x180035d23  mov     r8d, 0EA0h; Size
0x180035d29  lea     rcx, [rsp+0F80h+var_F10]; void *
0x180035d2e  call    memset_0
0x180035d33  lea     rdx, aQueryWinreHash; "Query WinRE hash status"
0x180035d3a  xor     ecx, ecx
0x180035d3c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180035d41  mov     r8, [rbx]
0x180035d44  lea     rdx, aTargetVolumeS; "Target volume: [%s]"
0x180035d4b  xor     ecx, ecx
0x180035d4d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180035d52  mov     r8, [rdi]
0x180035d55  lea     rdx, aWinrePathS; "WinRE path:    [%s]"
0x180035d5c  xor     ecx, ecx
0x180035d5e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180035d63  mov     [rsp+0F80h+var_F20], 0
0x180035d6c  lea     rax, ??_7?$CAutoPbrDelete@PEAVBitLocker@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::`vftable'
0x180035d73  mov     [rsp+0F80h+var_F28], rax
0x180035d78  lea     rcx, [rsp+0F80h+var_F28]
0x180035d7d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180035d82  mov     rdx, rax
0x180035d85  mov     rcx, rbx
0x180035d88  call    ?Open@BitLocker@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::BitLocker::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::BitLocker * *)
0x180035d8d  mov     esi, eax
0x180035d8f  test    eax, eax
0x180035d91  jns     short loc_180035DCE
0x180035d93  mov     rcx, [rbx]
0x180035d96  mov     [rsp+0F80h+var_F50], rcx
0x180035d9b  lea     rax, aFailedToGetEnc; "Failed to get encryption information fo"...
0x180035da2  mov     [rsp+0F80h+var_F58], rax
0x180035da7  mov     [rsp+0F80h+var_F60], 34h ; '4'
0x180035daf  lea     r9, aBaseDiagnosisS_13; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180035db6  lea     r8, aWinreagentQuer; "WinREAgent::QueryWinREHashStatus"
0x180035dbd  mov     edx, esi
0x180035dbf  mov     ecx, 2
0x180035dc4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035dc9  jmp     loc_18003615E
0x180035dce  mov     rax, [rsp+0F80h+var_F28]
0x180035dd3  lea     rcx, [rsp+0F80h+var_F28]
0x180035dd8  mov     rax, [rax+18h]
0x180035ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035de1  mov     rdx, r14; bool *
0x180035de4  mov     rcx, rax; this
0x180035de7  call    ?CheckActive@BitLocker@PushButtonReset@@QEAAJPEA_N@Z; PushButtonReset::BitLocker::CheckActive(bool *)
0x180035dec  lea     rbx, aBaseDiagnosisS_13; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180035df3  lea     r14, aWinreagentQuer; "WinREAgent::QueryWinREHashStatus"
0x180035dfa  test    eax, eax
0x180035dfc  jns     short loc_180035E24
0x180035dfe  lea     rcx, aFailedToCheckI_0; "Failed to check if BitLocker is active,"...
0x180035e05  mov     [rsp+0F80h+var_F58], rcx
0x180035e0a  mov     [rsp+0F80h+var_F60], 39h ; '9'
0x180035e12  mov     r9, rbx
0x180035e15  mov     r8, r14
0x180035e18  mov     edx, eax
0x180035e1a  mov     ecx, 1
0x180035e1f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035e24  xorps   xmm0, xmm0
0x180035e27  movups  [rbp+0E80h+var_70], xmm0
0x180035e2e  movups  [rbp+0E80h+var_60], xmm0
0x180035e35  lea     rdx, [rbp+0E80h+var_70]
0x180035e3c  mov     rcx, [rdi]
0x180035e3f  call    cs:__imp_WinReHashWimFile
0x180035e45  test    eax, eax
0x180035e47  jnz     short loc_180035EA4
0x180035e49  mov     rdi, [rdi]
0x180035e4c  call    cs:__imp_GetLastError
0x180035e52  mov     r15d, 80070000h
0x180035e58  test    eax, eax
0x180035e5a  jle     short loc_180035E62
0x180035e5c  movzx   eax, ax
0x180035e5f  or      eax, r15d
0x180035e62  mov     [rsp+0F80h+var_F50], rdi
0x180035e67  lea     rcx, aFailedToHashWi; "Failed to hash wim file [%s]"
0x180035e6e  mov     [rsp+0F80h+var_F58], rcx
0x180035e73  mov     [rsp+0F80h+var_F60], 40h ; '@'
0x180035e7b  mov     r9, rbx
0x180035e7e  mov     r8, r14
0x180035e81  mov     edx, eax
0x180035e83  mov     ecx, 2
0x180035e88  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035e8d  call    cs:__imp_GetLastError
0x180035e93  test    eax, eax
0x180035e95  jle     short loc_180035E9D
0x180035e97  movzx   eax, ax
0x180035e9a  or      eax, r15d
0x180035e9d  mov     esi, eax
0x180035e9f  jmp     loc_18003615E
0x180035ea4  lea     rcx, [rsp+0F80h+var_F38]
0x180035ea9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180035eae  nop
0x180035eaf  lea     r8, [rsp+0F80h+var_F38]
0x180035eb4  lea     rcx, [rbp+0E80h+var_70]
0x180035ebb  call    ?EncodeBase64@Encode@PushButtonReset@@SAJPEAEKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Encode::EncodeBase64(uchar *,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035ec0  mov     esi, eax
0x180035ec2  test    eax, eax
0x180035ec4  jns     short loc_180035EFB
0x180035ec6  lea     rax, aFailedToEncode; "Failed to encode hash"
0x180035ecd  mov     [rsp+0F80h+var_F58], rax
0x180035ed2  mov     [rsp+0F80h+var_F60], 45h ; 'E'
0x180035eda  mov     r9, rbx
0x180035edd  mov     r8, r14
0x180035ee0  mov     edx, esi
0x180035ee2  mov     ecx, 2
0x180035ee7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035eec  nop
0x180035eed  mov     rcx, [rsp+0F80h+var_F38]
0x180035ef2  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180035ef6  jmp     loc_180036158
0x180035efb  mov     rdi, [rsp+0F80h+var_F38]
0x180035f00  mov     rax, [rsp+0F80h+var_F30]
0x180035f05  cmp     byte ptr [rax], 0
0x180035f08  jz      short loc_180035F61
0x180035f0a  mov     r9, r15
0x180035f0d  mov     r8d, 20h ; ' '
0x180035f13  lea     rdx, [rbp+0E80h+var_70]
0x180035f1a  mov     rcx, [rsp+0F80h+var_F40]
0x180035f1f  call    ?CheckIsWimTrusted@BitLocker@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAEKPEA_N@Z; PushButtonReset::BitLocker::CheckIsWimTrusted(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uchar *,ulong,bool *)
0x180035f24  mov     esi, eax
0x180035f26  test    eax, eax
0x180035f28  jns     short loc_180035F55
0x180035f2a  lea     rax, aFailedToCheckI_2; "Failed to check if wim is trusted, assu"...
0x180035f31  mov     [rsp+0F80h+var_F58], rax
0x180035f36  mov     [rsp+0F80h+var_F60], 51h ; 'Q'
0x180035f3e  mov     r9, rbx
0x180035f41  mov     r8, r14
0x180035f44  mov     edx, esi
0x180035f46  mov     ecx, 1
0x180035f4b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035f50  xor     esi, esi
0x180035f52  mov     [r15], sil
0x180035f55  mov     al, [r15]
0x180035f58  mov     [r13+0], al
0x180035f5c  jmp     loc_1800360A7
0x180035f61  mov     byte ptr [r15], 0
0x180035f65  lea     rdx, aBitlockerIsNot; "BitLocker is not active, assume wim is "...
0x180035f6c  xor     ecx, ecx
0x180035f6e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180035f73  mov     [rsp+0F80h+var_F10], 0EA0h
0x180035f7c  lea     rdx, [rsp+0F80h+var_F10]
0x180035f81  xor     ecx, ecx
0x180035f83  call    cs:__imp_WinReGetConfig
0x180035f89  test    eax, eax
0x180035f8b  jnz     short loc_180035FE4
0x180035f8d  call    cs:__imp_GetLastError
0x180035f93  mov     r15d, 80070000h
0x180035f99  test    eax, eax
0x180035f9b  jle     short loc_180035FA3
0x180035f9d  movzx   eax, ax
0x180035fa0  or      eax, r15d
0x180035fa3  lea     rcx, aFailedToGetWin_2; "Failed to get WinRE config"
0x180035faa  mov     [rsp+0F80h+var_F58], rcx
0x180035faf  mov     [rsp+0F80h+var_F60], 62h ; 'b'
0x180035fb7  mov     r9, rbx
0x180035fba  mov     r8, r14
0x180035fbd  mov     edx, eax
0x180035fbf  mov     ecx, 2
0x180035fc4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035fc9  call    cs:__imp_GetLastError
0x180035fcf  mov     esi, eax
0x180035fd1  test    eax, eax
0x180035fd3  jle     loc_180036154
0x180035fd9  movzx   esi, ax
0x180035fdc  or      esi, r15d
0x180035fdf  jmp     loc_180036154
0x180035fe4  cmp     [rbp+0E80h+var_2F8], 0
0x180035feb  jnz     short loc_180036005
0x180035fed  lea     rdx, aNoHashInWinreC; "No hash in WinRE config"
0x180035ff4  xor     ecx, ecx
0x180035ff6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180035ffb  mov     byte ptr [r13+0], 0
0x180036000  jmp     loc_1800360A7
0x180036005  lea     rcx, [rsp+0F80h+var_F40]
0x18003600a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003600f  nop
0x180036010  lea     r8, [rsp+0F80h+var_F40]
0x180036015  lea     rcx, [rbp+0E80h+var_2F8]
0x18003601c  call    ?EncodeBase64@Encode@PushButtonReset@@SAJPEAEKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Encode::EncodeBase64(uchar *,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180036021  mov     esi, eax
0x180036023  test    eax, eax
0x180036025  jns     short loc_180036061
0x180036027  lea     rax, aFailedToEncode_2; "Failed to encode validated hash"
0x18003602e  mov     [rsp+0F80h+var_F58], rax
0x180036033  mov     [rsp+0F80h+var_F60], 6Eh ; 'n'
0x18003603b  mov     r9, rbx
0x18003603e  mov     r8, r14
0x180036041  mov     edx, esi
0x180036043  mov     ecx, 2
0x180036048  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003604d  nop
0x18003604e  mov     rcx, [rsp+0F80h+var_F40]
0x180036053  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036057  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003605c  jmp     loc_180036154
0x180036061  mov     rbx, [rsp+0F80h+var_F40]
0x180036066  mov     r8, rbx
0x180036069  lea     rdx, aEncodedWinreCo; "Encoded WinRE config hash: [%s]"
0x180036070  xor     ecx, ecx
0x180036072  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180036077  mov     r8, rdi
0x18003607a  lea     rdx, aInputWinreHash; "Input WinRE hash:          [%s]"
0x180036081  xor     ecx, ecx
0x180036083  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180036088  mov     rdx, rdi
0x18003608b  lea     rcx, [rsp+0F80h+var_F40]
0x180036090  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180036095  test    eax, eax
0x180036097  setz    al
0x18003609a  mov     [r13+0], al
0x18003609e  lea     rcx, [rbx-18h]; this
0x1800360a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800360a7  lea     r14, aFalse; "false"
0x1800360ae  lea     rbx, aTrue; "true"
0x1800360b5  mov     r8, rbx
0x1800360b8  mov     rax, [rsp+0F80h+var_F30]
0x1800360bd  cmp     byte ptr [rax], 0
0x1800360c0  cmovz   r8, r14
0x1800360c4  lea     rdx, aIsBitlockerAct; "Is BitLocker active: %s"
0x1800360cb  xor     ecx, ecx
0x1800360cd  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800360d2  mov     r8, rbx
0x1800360d5  cmp     byte ptr [r15], 0
0x1800360d9  cmovz   r8, r14
0x1800360dd  lea     rdx, aIsHashTrustedS; "Is hash trusted:   %s"
0x1800360e4  xor     ecx, ecx
0x1800360e6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800360eb  cmp     byte ptr [r13+0], 0
0x1800360f0  cmovz   rbx, r14
0x1800360f4  mov     r8, rbx
0x1800360f7  lea     rdx, aIsHashValidate; "Is hash validated: %s"
0x1800360fe  xor     ecx, ecx
0x180036100  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180036105  test    r12, r12
0x180036108  jz      short loc_180036154
0x18003610a  lea     rcx, [rdi-18h]
0x18003610e  mov     r14, [r12]
0x180036112  add     r14, 0FFFFFFFFFFFFFFE8h
0x180036116  cmp     rcx, r14
0x180036119  jz      short loc_180036154
0x18003611b  cmp     dword ptr [r14+10h], 0
0x180036120  jl      short loc_180036144
0x180036122  mov     rax, [r14]
0x180036125  cmp     [rcx], rax
0x180036128  jnz     short loc_180036144
0x18003612a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003612f  mov     rbx, rax
0x180036132  mov     rcx, r14; this
0x180036135  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003613a  lea     rax, [rbx+18h]
0x18003613e  mov     [r12], rax
0x180036142  jmp     short loc_180036154
0x180036144  mov     r8d, [rdi-10h]
0x180036148  mov     rdx, rdi
0x18003614b  mov     rcx, r12
0x18003614e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180036153  nop
0x180036154  lea     rcx, [rdi-18h]; this
0x180036158  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003615d  nop
0x18003615e  lea     rax, ??_7?$CAutoPbrDelete@PEAVBitLocker@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::`vftable'
0x180036165  mov     [rsp+0F80h+var_F28], rax
0x18003616a  lea     rcx, [rsp+0F80h+var_F28]
0x18003616f  call    ?Release@?$CAutoPbrDelete@PEAVBitLocker@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::BitLocker *>::Release(void)
0x180036174  mov     eax, esi
0x180036176  mov     rcx, [rbp+0E80h+var_50]
0x18003617d  xor     rcx, rsp; StackCookie
0x180036180  call    __security_check_cookie
0x180036185  add     rsp, 0F48h
0x18003618c  pop     r15
0x18003618e  pop     r14
0x180036190  pop     r13
0x180036192  pop     r12
0x180036194  pop     rdi
0x180036195  pop     rsi
0x180036196  pop     rbx
0x180036197  pop     rbp
0x180036198  retn
```
