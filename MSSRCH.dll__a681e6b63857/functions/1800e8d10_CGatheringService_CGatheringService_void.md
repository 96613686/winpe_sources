# CGatheringService::CGatheringService(void)

- ea: `0x1800e8d10`
- end: `0x1800e958c`
- name: `??0CGatheringService@@QEAA@XZ`
- size: `2172`
- prototype: `CGatheringService *__fastcall(CGatheringService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180142040`

## callees

- `0x18001b470`
- `0x180026b58`
- `0x18006a040`
- `0x18008d92c`
- `0x1800b8b7c`
- `0x1800b8bc0`
- `0x1800e8d10`
- `0x1800e9594`
- `0x1800e95f0`
- `0x1800e9b78`
- `0x1800e9ca4`
- `0x1800e9d34`
- `0x1800e9d78`
- `0x1801244f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e935a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e93a1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e935a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e93a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e94ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e94fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e953b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e94ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e94fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e953b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e8d84`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e8d84`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
CGatheringService *__fastcall CGatheringService::CGatheringService(CGatheringService *this)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  const wchar_t *v6; // rdx
  const wchar_t *v7; // r8
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  struct PerfCounterDefinition *v10; // r9
  unsigned int v11; // r9d
  struct PerfCounterDefinition *v12; // r9
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  unsigned int v15; // r9d
  unsigned int v16; // r9d
  unsigned int v17; // r9d
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  unsigned int v23; // r9d
  unsigned int v24; // r9d
  struct PerfCounterDefinition *v25; // r9
  unsigned int v26; // r9d
  unsigned int v27; // r9d
  unsigned int v28; // r9d
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  struct PerfCounterDefinition *v31; // r9
  unsigned int v32; // r9d
  unsigned int v33; // r9d
  unsigned int v34; // r9d
  struct PerfCounterDefinition *v35; // r9
  unsigned int v36; // r9d
  unsigned int v37; // r9d
  unsigned int v38; // r9d
  int v39; // edx
  const wchar_t *v40; // rdx
  unsigned __int16 v41; // r8
  HANDLE EventW; // rax
  const char *v43; // r9
  HANDLE v44; // rax
  const char *v45; // r9
  HANDLE v46; // rax
  const char *v47; // r9
  unsigned int v49; // [rsp+20h] [rbp-48h]
  unsigned int v50; // [rsp+20h] [rbp-48h]
  unsigned int v51; // [rsp+20h] [rbp-48h]
  unsigned int v52; // [rsp+20h] [rbp-48h]
  unsigned int v53; // [rsp+20h] [rbp-48h]
  unsigned int v54; // [rsp+20h] [rbp-48h]
  unsigned int v55; // [rsp+20h] [rbp-48h]
  unsigned int v56; // [rsp+20h] [rbp-48h]
  unsigned int v57; // [rsp+20h] [rbp-48h]
  unsigned int v58; // [rsp+20h] [rbp-48h]
  unsigned int v59; // [rsp+20h] [rbp-48h]
  unsigned int v60; // [rsp+20h] [rbp-48h]
  unsigned int v61; // [rsp+20h] [rbp-48h]
  unsigned int v62; // [rsp+20h] [rbp-48h]
  unsigned int v63; // [rsp+20h] [rbp-48h]
  unsigned int v64; // [rsp+20h] [rbp-48h]
  unsigned int v65; // [rsp+20h] [rbp-48h]
  unsigned int v66; // [rsp+20h] [rbp-48h]
  unsigned int v67; // [rsp+20h] [rbp-48h]
  unsigned int v68; // [rsp+20h] [rbp-48h]
  unsigned int v69; // [rsp+20h] [rbp-48h]
  unsigned int v70; // [rsp+20h] [rbp-48h]
  unsigned int v71; // [rsp+20h] [rbp-48h]
  unsigned int v72; // [rsp+20h] [rbp-48h]
  unsigned int v73; // [rsp+20h] [rbp-48h]
  unsigned int v74; // [rsp+20h] [rbp-48h]
  unsigned int v75; // [rsp+20h] [rbp-48h]
  unsigned int v76; // [rsp+20h] [rbp-48h]
  unsigned int v77; // [rsp+20h] [rbp-48h]
  unsigned int v78; // [rsp+20h] [rbp-48h]
  unsigned int v79; // [rsp+20h] [rbp-48h]
  unsigned int v80; // [rsp+20h] [rbp-48h]
  unsigned int v81; // [rsp+20h] [rbp-48h]
  unsigned int v82; // [rsp+20h] [rbp-48h]
  unsigned int v83; // [rsp+20h] [rbp-48h]
  unsigned int v84; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  CEventLog *v86; // [rsp+78h] [rbp+10h]

  *((_QWORD *)this + 2) = (char *)this + 32;
  *((_QWORD *)this + 3) = 65;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 1) = &CCICommonPathString::`vftable';
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 22) = 0;
  *(_QWORD *)this = &CGatheringService::`vftable';
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>((char *)this + 184);
  CSyncReadWrite::CSyncReadWrite((CGatheringService *)((char *)this + 208), v2);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 8);
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 51) = (char *)this + 424;
  *((_QWORD *)this + 52) = 65;
  *((_WORD *)this + 212) = 0;
  *((_QWORD *)this + 50) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 72) = (char *)this + 592;
  *((_QWORD *)this + 73) = 33;
  *((_WORD *)this + 296) = 0;
  *((_QWORD *)this + 71) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 84) = (char *)this + 688;
  *((_QWORD *)this + 85) = 33;
  *((_WORD *)this + 344) = 0;
  *((_QWORD *)this + 83) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 96) = (char *)this + 784;
  *((_QWORD *)this + 97) = 65;
  *((_WORD *)this + 392) = 0;
  *((_QWORD *)this + 95) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 116) = (char *)this + 944;
  *((_QWORD *)this + 117) = 65;
  *((_WORD *)this + 472) = 0;
  *((_QWORD *)this + 115) = &CCICommonPathString::`vftable';
  *((_DWORD *)this + 270) = 1;
  *((_QWORD *)this + 137) = (char *)this + 1112;
  *((_QWORD *)this + 138) = 65;
  *((_WORD *)this + 556) = 0;
  *((_QWORD *)this + 136) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 165) = (char *)this + 1336;
  *((_QWORD *)this + 166) = 65;
  *((_WORD *)this + 668) = 0;
  *((_QWORD *)this + 164) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 186) = (char *)this + 1504;
  *((_QWORD *)this + 187) = 1025;
  *((_WORD *)this + 752) = 0;
  *((_QWORD *)this + 185) = &TLMString<1024,1024,1048576>::`vftable';
  CSyncReadWrite::CSyncReadWrite((CGatheringService *)((char *)this + 3656), v3);
  CSyncReadWrite::CSyncReadWrite((CGatheringService *)((char *)this + 3768), v4);
  *((_DWORD *)this + 972) = 32;
  *(_QWORD *)((char *)this + 3892) = 1;
  *((_DWORD *)this + 975) = 0;
  *((_QWORD *)this + 488) = 0;
  *((_QWORD *)this + 489) = 0;
  *((_QWORD *)this + 490) = 0;
  CTComObjHMap<TLMString<32,32,1024>,CGthrPrj,CLMSubStr>::CTComObjHMap<TLMString<32,32,1024>,CGthrPrj,CLMSubStr>(
    (_DWORD)this + 3928,
    (unsigned int)SIDHash,
    (unsigned int)PSubStringHash,
    17,
    0,
    3);
  *((_QWORD *)this + 498) = 0;
  *((_QWORD *)this + 499) = 0;
  *((_QWORD *)this + 500) = 0;
  *((_QWORD *)this + 501) = 0;
  *((_DWORD *)this + 1004) = 0;
  *((_QWORD *)this + 503) = 0;
  *((_QWORD *)this + 504) = 0;
  TLMString<32,32,1024>::TLMString<32,32,1024>((char *)this + 4040, L"SQLServer");
  *((_QWORD *)this + 517) = 0;
  *((_QWORD *)this + 518) = 0;
  *((_QWORD *)this + 519) = 0;
  *((_QWORD *)this + 520) = 0;
  *((_QWORD *)this + 521) = 0;
  *((_QWORD *)this + 522) = 0;
  *((_QWORD *)this + 523) = 0;
  *((_QWORD *)this + 524) = 0;
  *((_QWORD *)this + 525) = 0;
  *((_QWORD *)this + 526) = 0;
  *((_DWORD *)this + 1054) = 0;
  *((_QWORD *)this + 529) = (char *)this + 4248;
  *((_QWORD *)this + 530) = 33;
  *((_WORD *)this + 2124) = 0;
  *((_QWORD *)this + 528) = &TLMString<32,32,1024>::`vftable';
  CSyncReadWrite::CSyncReadWrite((CGatheringService *)((char *)this + 4328), v5);
  PerfLibrary::PerfLibrary((CGatheringService *)((char *)this + 4448), v6);
  PerfObjectDefinition::PerfObjectDefinition(
    (CGatheringService *)((char *)this + 4656),
    (CGatheringService *)((char *)this + 4448),
    v7,
    v8,
    v49);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5272),
    (CGatheringService *)((char *)this + 4656),
    2u,
    v9,
    v50);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5312),
    (CGatheringService *)((char *)this + 4656),
    4u,
    (_DWORD)this + 5312,
    v51);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5352),
    v10,
    6u,
    (unsigned int)v10,
    v52);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5392),
    (CGatheringService *)((char *)this + 4656),
    8u,
    v11,
    v53);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5432),
    (CGatheringService *)((char *)this + 4656),
    0xAu,
    (_DWORD)this + 5432,
    v54);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5472),
    v12,
    0xCu,
    (unsigned int)v12,
    v55);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5512),
    (CGatheringService *)((char *)this + 4656),
    0xEu,
    v13,
    v56);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5552),
    (CGatheringService *)((char *)this + 4656),
    0x10u,
    v14,
    v57);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5592),
    (CGatheringService *)((char *)this + 4656),
    0x12u,
    v15,
    v58);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5632),
    (CGatheringService *)((char *)this + 4656),
    0x14u,
    v16,
    v59);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5672),
    (CGatheringService *)((char *)this + 4656),
    0x16u,
    v17,
    v60);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5712),
    (CGatheringService *)((char *)this + 4656),
    0x18u,
    v18,
    v61);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5752),
    (CGatheringService *)((char *)this + 4656),
    0x1Au,
    v19,
    v62);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5792),
    (CGatheringService *)((char *)this + 4656),
    0x1Cu,
    v20,
    v63);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5832),
    (CGatheringService *)((char *)this + 4656),
    0x1Eu,
    v21,
    v64);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5872),
    (CGatheringService *)((char *)this + 4656),
    0x20u,
    v22,
    v65);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5912),
    (CGatheringService *)((char *)this + 4656),
    0x22u,
    v23,
    v66);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5952),
    (CGatheringService *)((char *)this + 4656),
    0x24u,
    v24,
    v67);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 5992),
    (CGatheringService *)((char *)this + 4656),
    0x26u,
    (_DWORD)this + 5992,
    v68);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6032),
    v25,
    0x28u,
    (unsigned int)v25,
    v69);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6072),
    (CGatheringService *)((char *)this + 4656),
    0x2Au,
    v26,
    v70);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6112),
    (CGatheringService *)((char *)this + 4656),
    0x2Cu,
    v27,
    v71);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6152),
    (CGatheringService *)((char *)this + 4656),
    0x2Eu,
    v28,
    v72);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6192),
    (CGatheringService *)((char *)this + 4656),
    0x30u,
    v29,
    v73);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6232),
    (CGatheringService *)((char *)this + 4656),
    0x32u,
    v30,
    v74);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6272),
    (CGatheringService *)((char *)this + 4656),
    0x34u,
    (_DWORD)this + 6272,
    v75);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6312),
    v31,
    0x36u,
    (unsigned int)v31,
    v76);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6352),
    (CGatheringService *)((char *)this + 4656),
    0x38u,
    v32,
    v77);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6392),
    (CGatheringService *)((char *)this + 4656),
    0x3Au,
    v33,
    v78);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6432),
    (CGatheringService *)((char *)this + 4656),
    0x3Cu,
    v34,
    v79);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6472),
    (CGatheringService *)((char *)this + 4656),
    0x3Eu,
    (_DWORD)this + 6472,
    v80);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6512),
    v35,
    0x40u,
    (unsigned int)v35,
    v81);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6552),
    (CGatheringService *)((char *)this + 4656),
    0x42u,
    v36,
    v82);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6592),
    (CGatheringService *)((char *)this + 4656),
    0x44u,
    v37,
    v83);
  PerfCounterDefinition::PerfCounterDefinition(
    (CGatheringService *)((char *)this + 6632),
    (CGatheringService *)((char *)this + 4656),
    0x46u,
    v38,
    v84);
  *((_QWORD *)this + 834) = 0;
  *((_DWORD *)this + 1670) = 0;
  *((_DWORD *)this + 1671) = 0;
  CUserSettings::CUserSettings((CGatheringService *)((char *)this + 6688));
  CSyncReadWrite::CSyncReadWrite((CGatheringService *)((char *)this + 7112), v39);
  *((_BYTE *)this + 7224) = 0;
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>((char *)this + 7232);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 7256), 0, 0);
  *((_DWORD *)this + 1824) = 0;
  *((_DWORD *)this + 1825) = 0;
  *((_DWORD *)this + 1826) = 0;
  *((_QWORD *)this + 914) = 0;
  *((_QWORD *)this + 915) = -1;
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>((char *)this + 7328);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 7352), 0, 0);
  *((_QWORD *)this + 924) = 0;
  *((_QWORD *)this + 925) = 0;
  *((_QWORD *)this + 926) = 0;
  *((_QWORD *)this + 927) = 0;
  *((_QWORD *)this + 928) = 0;
  *((_QWORD *)this + 929) = 0;
  *((_QWORD *)this + 930) = 0;
  *((_QWORD *)this + 931) = 0;
  *((_QWORD *)this + 932) = 0;
  *((_QWORD *)this + 933) = 0;
  *((_QWORD *)this + 934) = 0;
  *((_QWORD *)this + 935) = 0;
  *((_QWORD *)this + 936) = 0;
  *((_QWORD *)this + 937) = 0;
  *((_QWORD *)this + 938) = 0;
  *((_QWORD *)this + 939) = 0;
  *((_QWORD *)this + 940) = 0;
  *((_QWORD *)this + 941) = 0;
  *((_QWORD *)this + 942) = 0;
  *((_QWORD *)this + 943) = 0;
  *((_QWORD *)this + 944) = 0;
  *((_QWORD *)this + 945) = 0;
  *((_QWORD *)this + 946) = 0;
  *((_QWORD *)this + 947) = 0;
  *((_QWORD *)this + 948) = 0;
  *((_QWORD *)this + 949) = 0;
  *((_QWORD *)this + 950) = 0;
  *((_QWORD *)this + 951) = 0;
  *((_QWORD *)this + 952) = 0;
  *((_QWORD *)this + 953) = 0;
  *((_DWORD *)this + 1909) = 0;
  *((_QWORD *)this + 955) = 0;
  *((_QWORD *)this + 956) = 0;
  v86 = (CEventLog *)operator new(0x10u);
  *((_QWORD *)this + 49) = CEventLog::CEventLog(v86, v40, v41);
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 4136,
    EventW);
  if ( ((*((_QWORD *)this + 517) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      v43);
  v44 = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 4024,
    v44);
  if ( ((*((_QWORD *)this + 503) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      v45);
  v46 = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 4032,
    v46);
  if ( ((*((_QWORD *)this + 504) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      v47);
  return this;
}

```

## disassembly

```asm
0x1800e8d10  mov     [rsp+arg_10], rbx
0x1800e8d15  mov     [rsp+arg_0], rcx
0x1800e8d1a  push    rbp
0x1800e8d1b  push    rsi
0x1800e8d1c  push    rdi
0x1800e8d1d  push    r12
0x1800e8d1f  push    r13
0x1800e8d21  push    r14
0x1800e8d23  push    r15
0x1800e8d25  sub     rsp, 30h
0x1800e8d29  mov     r14, rcx
0x1800e8d2c  lea     rdx, [rcx+20h]
0x1800e8d30  mov     [rcx+10h], rdx
0x1800e8d34  mov     qword ptr [rcx+18h], 41h ; 'A'
0x1800e8d3c  xor     esi, esi
0x1800e8d3e  mov     [rdx], si
0x1800e8d41  lea     rbx, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800e8d48  mov     [rcx+8], rbx
0x1800e8d4c  mov     [rcx+0A8h], esi
0x1800e8d52  mov     [rcx+0B0h], rsi
0x1800e8d59  lea     rax, ??_7CGatheringService@@6B@; const CGatheringService::`vftable'
0x1800e8d60  mov     [rcx], rax
0x1800e8d63  add     rcx, 0B8h; void *
0x1800e8d6a  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800e8d6f  nop
0x1800e8d70  lea     rcx, [r14+0D0h]; this
0x1800e8d77  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e8d7c  nop
0x1800e8d7d  lea     rcx, [r14+140h]; lpCriticalSection
0x1800e8d84  call    cs:__imp_InitializeCriticalSection
0x1800e8d8a  nop
0x1800e8d8b  mov     [r14+178h], rsi
0x1800e8d92  mov     [r14+180h], rsi
0x1800e8d99  mov     [r14+188h], rsi
0x1800e8da0  lea     rcx, [r14+1A8h]
0x1800e8da7  mov     [r14+198h], rcx
0x1800e8dae  mov     qword ptr [r14+1A0h], 41h ; 'A'
0x1800e8db9  mov     [rcx], si
0x1800e8dbc  mov     [r14+190h], rbx
0x1800e8dc3  lea     rcx, [r14+250h]
0x1800e8dca  mov     [r14+240h], rcx
0x1800e8dd1  mov     qword ptr [r14+248h], 21h ; '!'
0x1800e8ddc  mov     [rcx], si
0x1800e8ddf  lea     r13, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x1800e8de6  mov     [r14+238h], r13
0x1800e8ded  lea     rcx, [r14+2B0h]
0x1800e8df4  mov     [r14+2A0h], rcx
0x1800e8dfb  mov     qword ptr [r14+2A8h], 21h ; '!'
0x1800e8e06  mov     [rcx], si
0x1800e8e09  mov     [r14+298h], r13
0x1800e8e10  lea     rcx, [r14+310h]
0x1800e8e17  mov     [r14+300h], rcx
0x1800e8e1e  mov     qword ptr [r14+308h], 41h ; 'A'
0x1800e8e29  mov     [rcx], si
0x1800e8e2c  mov     [r14+2F8h], rbx
0x1800e8e33  lea     rcx, [r14+3B0h]
0x1800e8e3a  mov     [r14+3A0h], rcx
0x1800e8e41  mov     qword ptr [r14+3A8h], 41h ; 'A'
0x1800e8e4c  mov     [rcx], si
0x1800e8e4f  mov     [r14+398h], rbx
0x1800e8e56  mov     dword ptr [r14+438h], 1
0x1800e8e61  lea     rcx, [r14+458h]
0x1800e8e68  mov     [r14+448h], rcx
0x1800e8e6f  mov     qword ptr [r14+450h], 41h ; 'A'
0x1800e8e7a  mov     [rcx], si
0x1800e8e7d  mov     [r14+440h], rbx
0x1800e8e84  lea     rcx, [r14+538h]
0x1800e8e8b  mov     [r14+528h], rcx
0x1800e8e92  mov     qword ptr [r14+530h], 41h ; 'A'
0x1800e8e9d  mov     [rcx], si
0x1800e8ea0  mov     [r14+520h], rbx
0x1800e8ea7  lea     rcx, [r14+5E0h]
0x1800e8eae  mov     [r14+5D0h], rcx
0x1800e8eb5  mov     qword ptr [r14+5D8h], 401h
0x1800e8ec0  mov     [rcx], si
0x1800e8ec3  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800e8eca  mov     [r14+5C8h], rax
0x1800e8ed1  lea     rcx, [r14+0E48h]; this
0x1800e8ed8  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e8edd  nop
0x1800e8ede  lea     rcx, [r14+0EB8h]; this
0x1800e8ee5  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e8eea  nop
0x1800e8eeb  mov     dword ptr [r14+0F30h], 20h ; ' '
0x1800e8ef6  mov     qword ptr [r14+0F34h], 1
0x1800e8f01  mov     [r14+0F3Ch], esi
0x1800e8f08  mov     [r14+0F40h], rsi
0x1800e8f0f  mov     [r14+0F48h], rsi
0x1800e8f16  mov     [r14+0F50h], rsi
0x1800e8f1d  lea     rcx, [r14+0F58h]
0x1800e8f24  mov     [rsp+68h+var_40], 3
0x1800e8f2c  mov     [rsp+68h+var_48], esi; int
0x1800e8f30  lea     r9d, [rsi+11h]
0x1800e8f34  lea     r8, ?PSubStringHash@@YAKPEBVCLMSubStr@@@Z; PSubStringHash(CLMSubStr const *)
0x1800e8f3b  lea     rdx, ?SIDHash@@YAKPEBV?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@@Z; SIDHash(TLMString<256,512,1048576> const *)
0x1800e8f42  call    ??0?$CTComObjHMap@V?$TLMString@$0CA@$0CA@$0EAA@@@VCGthrPrj@@VCLMSubStr@@@@QEAA@P6AKPEBV?$TLMString@$0CA@$0CA@$0EAA@@@@ZP6AKPEBVCLMSubStr@@@ZKKK@Z; CTComObjHMap<TLMString<32,32,1024>,CGthrPrj,CLMSubStr>::CTComObjHMap<TLMString<32,32,1024>,CGthrPrj,CLMSubStr>(ulong (*)(TLMString<32,32,1024> const *),ulong (*)(CLMSubStr const *),ulong,ulong,ulong)
0x1800e8f47  nop
0x1800e8f48  mov     [r14+0F90h], rsi
0x1800e8f4f  mov     [r14+0F98h], rsi
0x1800e8f56  mov     [r14+0FA0h], rsi
0x1800e8f5d  mov     [r14+0FA8h], rsi
0x1800e8f64  mov     [r14+0FB0h], esi
0x1800e8f6b  lea     rbp, [r14+0FB8h]
0x1800e8f72  mov     [rbp+0], rsi
0x1800e8f76  lea     r15, [r14+0FC0h]
0x1800e8f7d  mov     [r15], rsi
0x1800e8f80  lea     rcx, [r14+0FC8h]
0x1800e8f87  lea     rdx, aSqlserver; "SQLServer"
0x1800e8f8e  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e8f93  nop
0x1800e8f94  lea     rsi, [r14+1028h]
0x1800e8f9b  xor     eax, eax
0x1800e8f9d  mov     [rsi], rax
0x1800e8fa0  mov     [r14+1030h], rax
0x1800e8fa7  mov     [r14+1038h], rax
0x1800e8fae  mov     [r14+1040h], rax
0x1800e8fb5  mov     [r14+1048h], rax
0x1800e8fbc  mov     [r14+1050h], rax
0x1800e8fc3  mov     [r14+1058h], rax
0x1800e8fca  mov     [r14+1060h], rax
0x1800e8fd1  mov     [r14+1068h], rax
0x1800e8fd8  mov     [r14+1070h], rax
0x1800e8fdf  mov     [r14+1078h], eax
0x1800e8fe6  lea     rcx, [r14+1098h]
0x1800e8fed  mov     [r14+1088h], rcx
0x1800e8ff4  mov     qword ptr [r14+1090h], 21h ; '!'
0x1800e8fff  xor     r12d, r12d
0x1800e9002  mov     [rcx], r12w
0x1800e9006  mov     [r14+1080h], r13
0x1800e900d  lea     rcx, [r14+10E8h]; this
0x1800e9014  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e9019  nop
0x1800e901a  lea     rbx, [r14+1160h]
0x1800e9021  mov     rcx, rbx; this
0x1800e9024  call    ??0PerfLibrary@@QEAA@PEB_W@Z; PerfLibrary::PerfLibrary(wchar_t const *)
0x1800e9029  nop
0x1800e902a  lea     rdi, [r14+1230h]
0x1800e9031  mov     rdx, rbx; struct PerfLibrary *
0x1800e9034  mov     rcx, rdi; this
0x1800e9037  call    ??0PerfObjectDefinition@@QEAA@AEAVPerfLibrary@@PEB_WKK@Z; PerfObjectDefinition::PerfObjectDefinition(PerfLibrary &,wchar_t const *,ulong,ulong)
0x1800e903c  nop
0x1800e903d  lea     rcx, [r14+1498h]; this
0x1800e9044  lea     r8d, [r12+2]; unsigned int
0x1800e9049  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e904c  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9051  lea     r9, [r14+14C0h]; unsigned int
0x1800e9058  lea     r8d, [r12+4]; unsigned int
0x1800e905d  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9060  mov     rcx, r9; this
0x1800e9063  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9068  lea     rcx, [r14+14E8h]; this
0x1800e906f  lea     r8d, [r12+6]; unsigned int
0x1800e9074  mov     rdx, r9; struct PerfCounterDefinition *
0x1800e9077  call    ??0PerfCounterDefinition@@QEAA@AEAV0@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfCounterDefinition &,ulong,ulong,long)
0x1800e907c  lea     rcx, [r14+1510h]; this
0x1800e9083  lea     r8d, [r12+8]; unsigned int
0x1800e9088  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e908b  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9090  lea     r9, [r14+1538h]; unsigned int
0x1800e9097  lea     r8d, [r12+0Ah]; unsigned int
0x1800e909c  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e909f  mov     rcx, r9; this
0x1800e90a2  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e90a7  lea     rcx, [r14+1560h]; this
0x1800e90ae  lea     r8d, [r12+0Ch]; unsigned int
0x1800e90b3  mov     rdx, r9; struct PerfCounterDefinition *
0x1800e90b6  call    ??0PerfCounterDefinition@@QEAA@AEAV0@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfCounterDefinition &,ulong,ulong,long)
0x1800e90bb  lea     rcx, [r14+1588h]; this
0x1800e90c2  lea     r8d, [r12+0Eh]; unsigned int
0x1800e90c7  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e90ca  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e90cf  lea     rcx, [r14+15B0h]; this
0x1800e90d6  lea     ebx, [r12+10h]
0x1800e90db  mov     r8d, ebx; unsigned int
0x1800e90de  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e90e1  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e90e6  lea     rcx, [r14+15D8h]; this
0x1800e90ed  lea     r8d, [r12+12h]; unsigned int
0x1800e90f2  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e90f5  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e90fa  lea     rcx, [r14+1600h]; this
0x1800e9101  lea     r8d, [r12+14h]; unsigned int
0x1800e9106  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9109  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e910e  lea     rcx, [r14+1628h]; this
0x1800e9115  lea     r8d, [r12+16h]; unsigned int
0x1800e911a  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e911d  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9122  lea     rcx, [r14+1650h]; this
0x1800e9129  lea     r8d, [r12+18h]; unsigned int
0x1800e912e  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9131  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9136  lea     rcx, [r14+1678h]; this
0x1800e913d  lea     r8d, [r12+1Ah]; unsigned int
0x1800e9142  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9145  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e914a  lea     rcx, [r14+16A0h]; this
0x1800e9151  lea     r8d, [r12+1Ch]; unsigned int
0x1800e9156  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9159  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e915e  lea     rcx, [r14+16C8h]; this
0x1800e9165  lea     r8d, [r12+1Eh]; unsigned int
0x1800e916a  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e916d  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9172  lea     rcx, [r14+16F0h]; this
0x1800e9179  lea     r8d, [r12+20h]; unsigned int
0x1800e917e  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9181  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9186  lea     rcx, [r14+1718h]; this
0x1800e918d  lea     r8d, [r12+22h]; unsigned int
0x1800e9192  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9195  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e919a  lea     rcx, [r14+1740h]; this
0x1800e91a1  lea     r8d, [r12+24h]; unsigned int
0x1800e91a6  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e91a9  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e91ae  lea     r9, [r14+1768h]; unsigned int
0x1800e91b5  lea     r8d, [r12+26h]; unsigned int
0x1800e91ba  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e91bd  mov     rcx, r9; this
0x1800e91c0  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e91c5  lea     rcx, [r14+1790h]; this
0x1800e91cc  lea     r8d, [r12+28h]; unsigned int
0x1800e91d1  mov     rdx, r9; struct PerfCounterDefinition *
0x1800e91d4  call    ??0PerfCounterDefinition@@QEAA@AEAV0@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfCounterDefinition &,ulong,ulong,long)
0x1800e91d9  lea     rcx, [r14+17B8h]; this
0x1800e91e0  lea     r8d, [r12+2Ah]; unsigned int
0x1800e91e5  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e91e8  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e91ed  lea     rcx, [r14+17E0h]; this
0x1800e91f4  lea     r8d, [r12+2Ch]; unsigned int
0x1800e91f9  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e91fc  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9201  lea     rcx, [r14+1808h]; this
0x1800e9208  lea     r8d, [r12+2Eh]; unsigned int
0x1800e920d  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9210  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9215  lea     rcx, [r14+1830h]; this
0x1800e921c  lea     r8d, [r12+30h]; unsigned int
0x1800e9221  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9224  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9229  lea     rcx, [r14+1858h]; this
0x1800e9230  lea     r8d, [r12+32h]; unsigned int
0x1800e9235  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9238  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e923d  lea     r9, [r14+1880h]; unsigned int
0x1800e9244  lea     r8d, [r12+34h]; unsigned int
0x1800e9249  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e924c  mov     rcx, r9; this
0x1800e924f  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9254  lea     rcx, [r14+18A8h]; this
0x1800e925b  lea     r8d, [r12+36h]; unsigned int
0x1800e9260  mov     rdx, r9; struct PerfCounterDefinition *
0x1800e9263  call    ??0PerfCounterDefinition@@QEAA@AEAV0@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfCounterDefinition &,ulong,ulong,long)
0x1800e9268  lea     rcx, [r14+18D0h]; this
0x1800e926f  lea     r8d, [r12+38h]; unsigned int
0x1800e9274  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9277  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e927c  lea     rcx, [r14+18F8h]; this
0x1800e9283  lea     r8d, [r12+3Ah]; unsigned int
0x1800e9288  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e928b  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e9290  lea     rcx, [r14+1920h]; this
0x1800e9297  lea     r8d, [r12+3Ch]; unsigned int
0x1800e929c  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e929f  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e92a4  lea     r9, [r14+1948h]; unsigned int
0x1800e92ab  lea     r8d, [r12+3Eh]; unsigned int
0x1800e92b0  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e92b3  mov     rcx, r9; this
0x1800e92b6  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e92bb  lea     rcx, [r14+1970h]; this
0x1800e92c2  lea     r8d, [r12+40h]; unsigned int
0x1800e92c7  mov     rdx, r9; struct PerfCounterDefinition *
0x1800e92ca  call    ??0PerfCounterDefinition@@QEAA@AEAV0@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfCounterDefinition &,ulong,ulong,long)
0x1800e92cf  lea     rcx, [r14+1998h]; this
0x1800e92d6  lea     r8d, [r12+42h]; unsigned int
0x1800e92db  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e92de  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e92e3  lea     rcx, [r14+19C0h]; this
0x1800e92ea  lea     r8d, [r12+44h]; unsigned int
0x1800e92ef  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e92f2  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e92f7  lea     rcx, [r14+19E8h]; this
0x1800e92fe  lea     r8d, [r12+46h]; unsigned int
0x1800e9303  mov     rdx, rdi; struct PerfObjectDefinition *
0x1800e9306  call    ??0PerfCounterDefinition@@QEAA@AEAVPerfObjectDefinition@@KKJ@Z; PerfCounterDefinition::PerfCounterDefinition(PerfObjectDefinition &,ulong,ulong,long)
0x1800e930b  mov     [r14+1A10h], r12
0x1800e9312  mov     [r14+1A18h], r12d
0x1800e9319  mov     [r14+1A1Ch], r12d
0x1800e9320  lea     rcx, [r14+1A20h]; this
0x1800e9327  call    ??0CUserSettings@@QEAA@XZ; CUserSettings::CUserSettings(void)
0x1800e932c  nop
0x1800e932d  lea     rcx, [r14+1BC8h]; this
0x1800e9334  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e9339  nop
0x1800e933a  mov     [r14+1C38h], r12b
0x1800e9341  lea     rcx, [r14+1C40h]; void *
0x1800e9348  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800e934d  nop
  ... truncated ...
```
