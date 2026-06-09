# CTrace::CTrace(void)

- ea: `0x180014314`
- end: `0x1800144c2`
- name: `??0CTrace@@QEAA@XZ`
- size: `430`
- prototype: `CTrace *__fastcall(CTrace *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800022a0`

## callees

- `0x1800063b0`
- `0x18000a7c0`
- `0x180014314`
- `0x1800144c8`
- `0x180014508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001444a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001444a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001434f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001434f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001445c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001445c`

## string_xrefs

- `0x180014484`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800143b3`: `com\complus\src\shared\util\utsem.cpp`
- `0x180014462`: `CreateEvent for m_hSessionEvent Failed`

## pseudocode

```c
CTrace *__fastcall CTrace::CTrace(CTrace *this)
{
  signed int LastError; // eax
  __int64 v3; // [rsp+28h] [rbp-50h]
  signed int v4; // [rsp+40h] [rbp-38h] BYREF
  __int16 v5; // [rsp+44h] [rbp-34h]
  int v6; // [rsp+48h] [rbp-30h]
  const unsigned __int16 *v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]
  int v10; // [rsp+68h] [rbp-10h]
  int v11; // [rsp+6Ch] [rbp-Ch]

  qword_18015CE20 = (__int64)&CSemExclusive::`vftable';
  dword_18015CE50 = 0;
  if ( InitializeCriticalSectionAndSpinCount(&stru_18015CE28, 0x1F4u) )
  {
    dword_18015CE50 = 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    v5 = 21;
    v6 = -1073606063;
    v7 = L"InitializeCriticalSectionAndSpinCount";
    v8 = 0;
    v9 = 0;
    v11 = 1;
    v10 = 1;
    CError::WriteToLog(
      (CError *)&v4,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x94u,
      L"InitializeCriticalSectionAndSpinCount");
  }
  qword_18015D470 = 0;
  qword_18015D478 = 0;
  qword_18015D470 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,_TRACE_CONTEXT *>,throwing_allocator<_TRACE_CONTEXT *>>>::_Buyheadnode();
  g_Trace = 0;
  dword_18015CE18 = 0;
  qword_18015D460 = 0;
  RegistrationHandle = 0;
  xmmword_18015D480 = 0;
  xmmword_18015D490 = 0;
  qword_18015D4A0 = 0;
  qword_18015D4A0 = CreateEventW(0, 1, 0, 0);
  if ( qword_18015D4A0 )
  {
    *(&g_Trace + 1) = (unsigned int)CheckIfTraceDisabled() != 0 ? 1 : 3;
  }
  else
  {
    LODWORD(v3) = GetLastError();
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
      203,
      L"CTrace::CTrace",
      v3,
      L"CreateEvent for m_hSessionEvent Failed");
    *(&g_Trace + 1) = 2;
  }
  return (CTrace *)&g_Trace;
}

```

## disassembly

```asm
0x180014314  mov     rax, rsp
0x180014317  mov     [rax+8], rcx
0x18001431b  push    rsi
0x18001431c  sub     rsp, 70h
0x180014320  lea     rsi, ?g_Trace@@3VCTrace@@A; CTrace g_Trace
0x180014327  mov     [rax+8], rsi
0x18001432b  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180014332  mov     cs:qword_18015CE20, rax
0x180014339  mov     cs:dword_18015CE50, 0
0x180014343  mov     edx, 1F4h; dwSpinCount
0x180014348  lea     rcx, stru_18015CE28; lpCriticalSection
0x18001434f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180014355  test    eax, eax
0x180014357  jnz     short loc_1800143C6
0x180014359  call    cs:__imp_GetLastError
0x18001435f  test    eax, eax
0x180014361  jle     short loc_18001436B
0x180014363  movzx   eax, ax
0x180014366  or      eax, 80070000h
0x18001436b  mov     [rsp+78h+var_38], eax
0x18001436f  mov     eax, 15h
0x180014374  mov     [rsp+78h+var_34], ax
0x180014379  mov     [rsp+78h+var_30], 0C0021251h
0x180014381  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x180014388  mov     [rsp+78h+var_28], r9
0x18001438d  mov     [rsp+78h+var_20], 0
0x180014396  mov     [rsp+78h+var_18], 0
0x18001439f  mov     [rsp+78h+var_C], 1
0x1800143a7  mov     [rsp+78h+var_10], 1
0x1800143af  lea     r8d, [rax+7Fh]; unsigned int
0x1800143b3  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x1800143ba  lea     rcx, [rsp+78h+var_38]; this
0x1800143bf  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800143c4  jmp     short loc_1800143D0
0x1800143c6  mov     cs:dword_18015CE50, 1
0x1800143d0  mov     cs:qword_18015D470, 0
0x1800143db  mov     cs:qword_18015D478, 0
0x1800143e6  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@V?$throwing_allocator@PEAU_TRACE_CONTEXT@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,_TRACE_CONTEXT *>,throwing_allocator<_TRACE_CONTEXT *>>>::_Buyheadnode(void)
0x1800143eb  mov     cs:qword_18015D470, rax
0x1800143f2  mov     cs:?g_Trace@@3VCTrace@@A, 0; CTrace g_Trace
0x1800143fd  mov     cs:dword_18015CE18, 0
0x180014407  mov     cs:qword_18015D460, 0
0x180014412  mov     cs:RegistrationHandle, 0
0x18001441d  xorps   xmm0, xmm0
0x180014420  movdqa  cs:xmmword_18015D480, xmm0
0x180014428  xorps   xmm1, xmm1
0x18001442b  movdqa  cs:xmmword_18015D490, xmm1
0x180014433  mov     cs:qword_18015D4A0, 0
0x18001443e  xor     r9d, r9d; lpName
0x180014441  xor     r8d, r8d; bInitialState
0x180014444  lea     edx, [r9+1]; bManualReset
0x180014448  xor     ecx, ecx; lpEventAttributes
0x18001444a  call    cs:__imp_CreateEventW
0x180014450  mov     cs:qword_18015D4A0, rax
0x180014457  test    rax, rax
0x18001445a  jnz     short loc_1800144A4
0x18001445c  call    cs:__imp_GetLastError
0x180014462  lea     rcx, aCreateeventFor; "CreateEvent for m_hSessionEvent Failed"
0x180014469  mov     [rsp+78h+var_48], rcx
0x18001446e  mov     dword ptr [rsp+78h+var_50], eax
0x180014472  lea     rax, aCtraceCtrace; "CTrace::CTrace"
0x180014479  mov     [rsp+78h+var_58], rax
0x18001447e  mov     r9d, 0CBh
0x180014484  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001448b  mov     edx, 1
0x180014490  lea     ecx, [rdx+0Dh]
0x180014493  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014498  mov     dword ptr cs:?g_Trace@@3VCTrace@@A+4, 2; CTrace g_Trace
0x1800144a2  jmp     short loc_1800144B9
0x1800144a4  call    CheckIfTraceDisabled
0x1800144a9  neg     eax
0x1800144ab  sbb     ecx, ecx
0x1800144ad  and     ecx, 0FFFFFFFEh
0x1800144b0  add     ecx, 3
0x1800144b3  mov     dword ptr cs:?g_Trace@@3VCTrace@@A+4, ecx; CTrace g_Trace
0x1800144b9  mov     rax, rsi
0x1800144bc  add     rsp, 70h
0x1800144c0  pop     rsi
0x1800144c1  retn
```
