# CSQMUtil::OpenPDHQuery(void)

- ea: `0x1800416f8`
- end: `0x1800417c5`
- name: `?OpenPDHQuery@CSQMUtil@@SAJXZ`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180040a30`

## callees

- `0x180003f30`
- `0x18004112c`
- `0x1800416f8`

## import_xrefs

- `ext-ms-win-eventing-pdh-l1-1-0!PdhAddCounterW` at `0x180041779`
- `ext-ms-win-eventing-pdh-l1-1-0!PdhAddCounterW` at `0x180041779`
- `ext-ms-win-eventing-pdh-l1-1-0!PdhOpenQueryW` at `0x18004172b`
- `ext-ms-win-eventing-pdh-l1-1-0!PdhOpenQueryW` at `0x18004172b`

## string_xrefs

- `0x180041737`: `CSQMUtil::OpenPDHQuery`
- `0x180041785`: `CSQMUtil::OpenPDHQuery`
- `0x180041741`: `PdhOpenQuery failed: 0x%x in %s`

## pseudocode

```c
__int64 CSQMUtil::OpenPDHQuery(void)
{
  PDH_STATUS v0; // eax
  unsigned int v1; // ebx
  __int64 i; // rdi
  PDH_STATUS v3; // eax

  CSQMUtil::m_dwPdhQueryIntervalMS = CSQMUtil::GetPDHQueryTimeIntervalMS();
  if ( !CSQMUtil::m_dwPdhQueryIntervalMS )
    CSQMUtil::m_dwPdhQueryIntervalMS = 1000;
  v0 = PdhOpenQueryW(0, 0, &CSQMUtil::m_hQuery);
  v1 = v0;
  if ( v0 )
  {
    _DbgPrintMessage(4, "PdhOpenQuery failed: 0x%x in %s", v0, "CSQMUtil::OpenPDHQuery");
  }
  else
  {
    for ( i = 0; i != 13; ++i )
    {
      v3 = PdhAddCounterW(
             CSQMUtil::m_hQuery,
             (LPCWSTR)*(&CSQMUtil::m_perfCountersInfo + 2 * i),
             0,
             (PDH_HCOUNTER *)&qword_180084378[2 * i]);
      v1 = v3;
      if ( v3 )
        _DbgPrintMessage(4, "PdhAddCounter failed: 0x%x in %s", v3, "CSQMUtil::OpenPDHQuery");
    }
    CSQMUtil::bInitialized = 1;
  }
  return v1;
}

```

## disassembly

```asm
0x1800416f8  mov     [rsp+arg_0], rbx
0x1800416fd  mov     [rsp+arg_8], rsi
0x180041702  push    rdi
0x180041703  sub     rsp, 20h
0x180041707  call    ?GetPDHQueryTimeIntervalMS@CSQMUtil@@CAKXZ; CSQMUtil::GetPDHQueryTimeIntervalMS(void)
0x18004170c  mov     cs:?m_dwPdhQueryIntervalMS@CSQMUtil@@0KA, eax; ulong CSQMUtil::m_dwPdhQueryIntervalMS
0x180041712  test    eax, eax
0x180041714  jnz     short loc_180041720
0x180041716  mov     cs:?m_dwPdhQueryIntervalMS@CSQMUtil@@0KA, 3E8h; ulong CSQMUtil::m_dwPdhQueryIntervalMS
0x180041720  lea     r8, ?m_hQuery@CSQMUtil@@0PEAXEA; phQuery
0x180041727  xor     edx, edx; dwUserData
0x180041729  xor     ecx, ecx; szDataSource
0x18004172b  call    cs:__imp_PdhOpenQueryW
0x180041731  mov     ebx, eax
0x180041733  test    eax, eax
0x180041735  jz      short loc_180041754
0x180041737  lea     r9, aCsqmutilOpenpd_0; "CSQMUtil::OpenPDHQuery"
0x18004173e  mov     r8d, eax
0x180041741  lea     rdx, aPdhopenqueryFa; "PdhOpenQuery failed: 0x%x in %s"
0x180041748  mov     ecx, 4; int
0x18004174d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041752  jmp     short loc_1800417B3
0x180041754  xor     edi, edi
0x180041756  lea     rsi, ?m_perfCountersInfo@CSQMUtil@@0PAU_TSPerfCounterInfo@@A; _TSPerfCounterInfo near * CSQMUtil::m_perfCountersInfo
0x18004175d  mov     rcx, cs:?m_hQuery@CSQMUtil@@0PEAXEA; hQuery
0x180041764  lea     r9, [rsi+8]
0x180041768  mov     rdx, rdi
0x18004176b  xor     r8d, r8d; dwUserData
0x18004176e  shl     rdx, 4
0x180041772  add     r9, rdx; phCounter
0x180041775  mov     rdx, [rdx+rsi]; szFullCounterPath
0x180041779  call    cs:__imp_PdhAddCounterW
0x18004177f  mov     ebx, eax
0x180041781  test    eax, eax
0x180041783  jz      short loc_1800417A0
0x180041785  lea     r9, aCsqmutilOpenpd_0; "CSQMUtil::OpenPDHQuery"
0x18004178c  mov     r8d, eax
0x18004178f  lea     rdx, aPdhaddcounterF; "PdhAddCounter failed: 0x%x in %s"
0x180041796  mov     ecx, 4; int
0x18004179b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800417a0  inc     rdi
0x1800417a3  cmp     rdi, 0Dh
0x1800417a7  jnz     short loc_18004175D
0x1800417a9  mov     cs:?bInitialized@CSQMUtil@@0HA, 1; int CSQMUtil::bInitialized
0x1800417b3  mov     rsi, [rsp+28h+arg_8]
0x1800417b8  mov     eax, ebx
0x1800417ba  mov     rbx, [rsp+28h+arg_0]
0x1800417bf  add     rsp, 20h
0x1800417c3  pop     rdi
0x1800417c4  retn
```
