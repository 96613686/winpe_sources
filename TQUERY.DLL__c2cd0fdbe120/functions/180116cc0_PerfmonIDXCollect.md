# PerfmonIDXCollect

- ea: `0x180116cc0`
- end: `0x180116f06`
- name: `PerfmonIDXCollect`
- size: `582`
- prototype: `__int64 __fastcall(wchar_t *, void **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1800751d4`
- `0x180116cc0`
- `0x180116f0c`
- `0x1801480fc`
- `0x18016a494`
- `0x180173bf0`
- `0x180173c2c`
- `0x180175698`
- `0x180177d5c`
- `0x180188d90`
- `0x180188e04`
- `0x18019b810`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180116d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180116ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180116d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180116ea9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180116d74`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180116e90`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180116d74`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180116e90`

## string_xrefs

- `0x180116d09`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116d39`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116db7`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116dfd`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116e31`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116e55`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180116d2d`: `[PerfCounter] MSFTESQL: did not open correctly.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall PerfmonIDXCollect(wchar_t *a1, void **a2, unsigned int *a3, unsigned int *a4)
{
  const wchar_t *v8; // r9
  unsigned int v9; // r15d
  const wchar_t *v11; // r9
  unsigned int QueryType; // r14d
  const wchar_t *v13; // rdi
  HANDLE hObject; // [rsp+30h] [rbp-568h] BYREF
  LPCVOID lpBaseAddress; // [rsp+38h] [rbp-560h]
  _BYTE v16[1280]; // [rsp+50h] [rbp-548h] BYREF

  PerfLibraryData::PerfLibraryData((PerfLibraryData *)&hObject);
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
    (const wchar_t *)0x24D,
    (unsigned int)L"[PerfCounter] MSFTESQL: In PerfmonIDXCollect().  Query='%ls'.",
    a1);
  v9 = *a3;
  *a3 = 0;
  *a4 = 0;
  if ( g_fInitOkIDX )
  {
    QueryType = GetQueryType(a1);
    if ( QueryType == 3 )
    {
      SearchIndexerTrace::Verbose(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
        (const wchar_t *)0x272,
        (unsigned int)L"[PerfCounter] MSFTESQL: Foreign request not supported.",
        v11);
      PerfLibraryData::~PerfLibraryData((PerfLibraryData *)&hObject);
      return 0;
    }
    else
    {
      if ( !(unsigned int)PerfLibraryData::GetPerformanceStatistics((PerfLibraryData *)&hObject, L"WSearchIdxPi") )
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
          (const wchar_t *)0x279,
          (unsigned int)L"[PerfCounter] MSFTESQL: Cannot get perf statistics on library %ls.",
          L"WSearchIdxPi");
      v13 = (const wchar_t *)((PerfLibraryData::SpaceNeeded((PerfLibraryData *)&hObject, QueryType, a1) + 3) & 0xFFFFFFFC);
      SearchIndexerTrace::Verbose(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
        (const wchar_t *)0x282,
        (unsigned int)L"[PerfCounter] MSFTESQL: space needed = %u.",
        v13);
      if ( v9 >= (unsigned int)v13 )
      {
        PerfLibraryData::SavePerformanceData((PerfLibraryData *)&hObject, a2, a3, a4);
        PerfLibraryData::Close((PerfLibraryData *)&hObject);
        PerfLibraryData::~PerfLibraryData((PerfLibraryData *)&hObject);
        return 0;
      }
      else
      {
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
          (const wchar_t *)0x28B,
          (unsigned int)L"[PerfCounter] MSFTESQL: Insufficient buffer. Size=%u, Needed=%u.",
          (const wchar_t *)v9,
          (_DWORD)v13);
        PerfLibraryData::Close((PerfLibraryData *)&hObject);
        `eh vector destructor iterator'(v16, 0x50u, 0x10u, (void (*)(void *))PerfObjectData::~PerfObjectData);
        if ( lpBaseAddress )
        {
          UnmapViewOfFile(lpBaseAddress);
          lpBaseAddress = 0;
        }
        if ( hObject )
          CloseHandle(hObject);
        return 234;
      }
    }
  }
  else
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x265,
      (unsigned int)L"[PerfCounter] MSFTESQL: did not open correctly.",
      v8);
    PerfLibraryData::Close((PerfLibraryData *)&hObject);
    `eh vector destructor iterator'(v16, 0x50u, 0x10u, (void (*)(void *))PerfObjectData::~PerfObjectData);
    if ( lpBaseAddress )
    {
      UnmapViewOfFile(lpBaseAddress);
      lpBaseAddress = 0;
    }
    if ( hObject )
      CloseHandle(hObject);
    return 0;
  }
}

```

## disassembly

```asm
0x180116cc0  push    rbx
0x180116cc2  push    rsi
0x180116cc3  push    rdi
0x180116cc4  push    r12
0x180116cc6  push    r14
0x180116cc8  push    r15
0x180116cca  sub     rsp, 568h
0x180116cd1  mov     rax, cs:__security_cookie
0x180116cd8  xor     rax, rsp
0x180116cdb  mov     [rsp+598h+var_48], rax
0x180116ce3  mov     rsi, r9
0x180116ce6  mov     rbx, r8
0x180116ce9  mov     r12, rdx
0x180116cec  mov     rdi, rcx
0x180116cef  lea     rcx, [rsp+598h+hObject]; this
0x180116cf4  call    ??0PerfLibraryData@@QEAA@XZ; PerfLibraryData::PerfLibraryData(void)
0x180116cf9  nop
0x180116cfa  mov     r9, rdi; wchar_t *
0x180116cfd  lea     r8, aPerfcounterMsf_4; "[PerfCounter] MSFTESQL: In PerfmonIDXCo"...
0x180116d04  mov     edx, 24Dh; wchar_t *
0x180116d09  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116d10  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180116d15  mov     r15d, [rbx]
0x180116d18  mov     dword ptr [rbx], 0
0x180116d1e  mov     dword ptr [rsi], 0
0x180116d24  cmp     cs:?g_fInitOkIDX@@3HA, 0; int g_fInitOkIDX
0x180116d2b  jnz     short loc_180116D9B
0x180116d2d  lea     r8, aPerfcounterMsf_28; "[PerfCounter] MSFTESQL: did not open co"...
0x180116d34  mov     edx, 265h; wchar_t *
0x180116d39  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116d40  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180116d45  nop
0x180116d46  lea     rcx, [rsp+598h+hObject]; this
0x180116d4b  call    ?Close@PerfLibraryData@@QEAAXXZ; PerfLibraryData::Close(void)
0x180116d50  lea     r9, ??1PerfObjectData@@QEAA@XZ; void (*)(void *)
0x180116d57  mov     edx, 50h ; 'P'; unsigned __int64
0x180116d5c  lea     r8d, [rdx-40h]; unsigned __int64
0x180116d60  lea     rcx, [rsp+598h+var_548]; void *
0x180116d65  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180116d6a  mov     rcx, [rsp+598h+lpBaseAddress]; lpBaseAddress
0x180116d6f  test    rcx, rcx
0x180116d72  jz      short loc_180116D83
0x180116d74  call    cs:__imp_UnmapViewOfFile
0x180116d7a  mov     [rsp+598h+lpBaseAddress], 0
0x180116d83  mov     rcx, [rsp+598h+hObject]; hObject
0x180116d88  test    rcx, rcx
0x180116d8b  jz      short loc_180116D94
0x180116d8d  call    cs:__imp_CloseHandle
0x180116d93  nop
0x180116d94  xor     eax, eax
0x180116d96  jmp     loc_180116EE4
0x180116d9b  mov     rcx, rdi; wchar_t *
0x180116d9e  call    ?GetQueryType@@YAKPEB_W@Z; GetQueryType(wchar_t const *)
0x180116da3  mov     r14d, eax
0x180116da6  cmp     eax, 3
0x180116da9  jnz     short loc_180116DD5
0x180116dab  lea     r8, aPerfcounterMsf_16; "[PerfCounter] MSFTESQL: Foreign request"...
0x180116db2  mov     edx, 272h; wchar_t *
0x180116db7  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116dbe  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180116dc3  nop
0x180116dc4  lea     rcx, [rsp+598h+hObject]; this
0x180116dc9  call    ??1PerfLibraryData@@QEAA@XZ; PerfLibraryData::~PerfLibraryData(void)
0x180116dce  xor     eax, eax
0x180116dd0  jmp     loc_180116EE4
0x180116dd5  lea     rdx, aWsearchidxpi; "WSearchIdxPi"
0x180116ddc  lea     rcx, [rsp+598h+hObject]; this
0x180116de1  call    ?GetPerformanceStatistics@PerfLibraryData@@QEAAHPEB_W@Z; PerfLibraryData::GetPerformanceStatistics(wchar_t const *)
0x180116de6  test    eax, eax
0x180116de8  jnz     short loc_180116E09
0x180116dea  lea     r9, aWsearchidxpi; "WSearchIdxPi"
0x180116df1  lea     r8, aPerfcounterMsf_22; "[PerfCounter] MSFTESQL: Cannot get perf"...
0x180116df8  mov     edx, 279h; wchar_t *
0x180116dfd  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116e04  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180116e09  mov     r8, rdi; wchar_t *
0x180116e0c  mov     edx, r14d; unsigned int
0x180116e0f  lea     rcx, [rsp+598h+hObject]; this
0x180116e14  call    ?SpaceNeeded@PerfLibraryData@@QEAAKKPEB_W@Z; PerfLibraryData::SpaceNeeded(ulong,wchar_t const *)
0x180116e19  mov     edi, eax
0x180116e1b  add     rdi, 3
0x180116e1f  and     edi, 0FFFFFFFCh
0x180116e22  mov     r9d, edi; wchar_t *
0x180116e25  lea     r8, aPerfcounterMsf_6; "[PerfCounter] MSFTESQL: space needed = "...
0x180116e2c  mov     edx, 282h; wchar_t *
0x180116e31  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116e38  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180116e3d  cmp     r15d, edi
0x180116e40  jnb     short loc_180116EB7
0x180116e42  mov     [rsp+598h+var_578], edi
0x180116e46  mov     r9d, r15d; wchar_t *
0x180116e49  lea     r8, aPerfcounterMsf_8; "[PerfCounter] MSFTESQL: Insufficient bu"...
0x180116e50  mov     edx, 28Bh; wchar_t *
0x180116e55  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180116e5c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180116e61  nop
0x180116e62  lea     rcx, [rsp+598h+hObject]; this
0x180116e67  call    ?Close@PerfLibraryData@@QEAAXXZ; PerfLibraryData::Close(void)
0x180116e6c  lea     r9, ??1PerfObjectData@@QEAA@XZ; void (*)(void *)
0x180116e73  mov     edx, 50h ; 'P'; unsigned __int64
0x180116e78  lea     r8d, [rdx-40h]; unsigned __int64
0x180116e7c  lea     rcx, [rsp+598h+var_548]; void *
0x180116e81  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180116e86  mov     rcx, [rsp+598h+lpBaseAddress]; lpBaseAddress
0x180116e8b  test    rcx, rcx
0x180116e8e  jz      short loc_180116E9F
0x180116e90  call    cs:__imp_UnmapViewOfFile
0x180116e96  mov     [rsp+598h+lpBaseAddress], 0
0x180116e9f  mov     rcx, [rsp+598h+hObject]; hObject
0x180116ea4  test    rcx, rcx
0x180116ea7  jz      short loc_180116EB0
0x180116ea9  call    cs:__imp_CloseHandle
0x180116eaf  nop
0x180116eb0  mov     eax, 0EAh
0x180116eb5  jmp     short loc_180116EE4
0x180116eb7  mov     r9, rsi; unsigned int *
0x180116eba  mov     r8, rbx; unsigned int *
0x180116ebd  mov     rdx, r12; void **
0x180116ec0  lea     rcx, [rsp+598h+hObject]; this
0x180116ec5  call    ?SavePerformanceData@PerfLibraryData@@QEAAXPEAPEAXPEAK1@Z; PerfLibraryData::SavePerformanceData(void * *,ulong *,ulong *)
0x180116eca  lea     rcx, [rsp+598h+hObject]; this
0x180116ecf  call    ?Close@PerfLibraryData@@QEAAXXZ; PerfLibraryData::Close(void)
0x180116ed4  nop
0x180116ed5  lea     rcx, [rsp+598h+hObject]; this
0x180116eda  call    ??1PerfLibraryData@@QEAA@XZ; PerfLibraryData::~PerfLibraryData(void)
0x180116edf  nop
0x180116ee0  jmp     short $+2
0x180116ee2  xor     eax, eax
0x180116ee4  mov     rcx, [rsp+598h+var_48]
0x180116eec  xor     rcx, rsp; StackCookie
0x180116eef  call    __security_check_cookie
0x180116ef4  add     rsp, 568h
0x180116efb  pop     r15
0x180116efd  pop     r14
0x180116eff  pop     r12
0x180116f01  pop     rdi
0x180116f02  pop     rsi
0x180116f03  pop     rbx
0x180116f04  retn
```
