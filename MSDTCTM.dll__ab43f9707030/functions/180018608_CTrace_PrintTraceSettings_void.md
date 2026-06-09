# CTrace::PrintTraceSettings(void)

- ea: `0x180018608`
- end: `0x1800188b2`
- name: `?PrintTraceSettings@CTrace@@QEAAJXZ`
- size: `682`
- prototype: `__int64 __fastcall(CTrace *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006750`
- `0x180020830`

## callees

- `0x1800063b0`
- `0x18000862c`
- `0x18000fb90`
- `0x18001554c`
- `0x180018608`
- `0x18001931c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001869b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001869b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018866`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018866`

## string_xrefs

- `0x18001862f`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800186b3`: `OpenTracingLoggingOptionsKey failed`

## pseudocode

```c
__int64 __fastcall CTrace::PrintTraceSettings(CTrace *this)
{
  int TraceContext; // ebx
  const wchar_t *v3; // rax
  __int64 v4; // r9
  __int64 v6; // [rsp+28h] [rbp-91h]
  unsigned int v7; // [rsp+A0h] [rbp-19h] BYREF
  BOOL v8; // [rsp+A4h] [rbp-15h] BYREF
  DWORD CurrentProcessId; // [rsp+A8h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v11; // [rsp+B8h] [rbp-1h] BYREF
  int v12; // [rsp+C0h] [rbp+7h]
  int v13; // [rsp+120h] [rbp+67h] BYREF
  int v14; // [rsp+128h] [rbp+6Fh] BYREF
  int v15; // [rsp+130h] [rbp+77h] BYREF
  int v16; // [rsp+138h] [rbp+7Fh] BYREF

  CurrentProcessId = 0;
  v7 = 0;
  hKey = 0;
  v8 = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v11 = 0;
  v12 = 0;
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    326,
    L"CTrace::PrintTraceSettings",
    0,
    L"In");
  if ( (unsigned int)(*((_DWORD *)this + 2) - 1) > 2 )
  {
    TraceContext = -2147467263;
    goto LABEL_22;
  }
  CurrentProcessId = GetCurrentProcessId();
  TraceContext = OpenTracingLoggingOptionsKey(&hKey);
  if ( TraceContext < 0 )
  {
    v3 = L"OpenTracingLoggingOptionsKey failed";
    v4 = 339;
    goto LABEL_21;
  }
  TraceContext = RegQueryDword(hKey, L"MaxBuffers", &v7, 0x19u);
  if ( TraceContext < 0 )
  {
    v3 = L"RegQueryDword(dwMaxBuffers) failed";
    v4 = 347;
    goto LABEL_21;
  }
  TraceContext = CTrace::GetTraceContext(this, 1u, (struct _TRACE_CONTEXT *)&v11);
  if ( TraceContext < 0 )
  {
    v3 = L"GetTraceContext(TRACE_MODULE_DTC_ID) failed";
    v4 = 355;
    goto LABEL_21;
  }
  v8 = v11 != 0;
  TraceContext = CTrace::GetTraceContext(this, 2u, (struct _TRACE_CONTEXT *)&v11);
  if ( TraceContext < 0 )
  {
    v3 = L"GetTraceContext(TRACE_MODULE_DTC_ID) failed";
    v4 = 366;
    goto LABEL_21;
  }
  if ( (_DWORD)v11 )
  {
    v16 = 1;
    if ( (v12 & 0xFFFFFF) == 0xFFFFFF )
    {
      v14 = 1;
      v15 = 1;
    }
    else
    {
      if ( (v12 & 1) != 0 )
        v14 = 1;
      if ( (v12 & 2) == 0 )
        goto LABEL_19;
    }
    v13 = 1;
  }
  else
  {
    v16 = 0;
    v14 = 0;
    v13 = 0;
    v15 = 0;
  }
LABEL_19:
  TraceContext = CTrace::TraceEvent(
                   (CTrace *)&g_Trace,
                   1u,
                   0,
                   (union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&stru_18013E510,
                   0xBu,
                   4,
                   &CurrentProcessId,
                   4,
                   &v8,
                   4,
                   &v16,
                   4,
                   &v14,
                   4,
                   &v13,
                   4,
                   &v15,
                   4,
                   &v7,
                   0);
  if ( TraceContext >= 0 )
    goto LABEL_22;
  v3 = L"g_Trace.TraceEvent(TRACE_SETTINGS) FAILED";
  v4 = 408;
LABEL_21:
  LODWORD(v6) = TraceContext;
  TraceStringInline(
    14,
    1,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    v4,
    L"CTrace::PrintTraceSettings",
    v6,
    v3);
LABEL_22:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    418,
    L"CTrace::PrintTraceSettings",
    0,
    L"Out");
  return (unsigned int)TraceContext;
}

```

## disassembly

```asm
0x180018608  push    rbp
0x18001860a  push    rbx
0x18001860b  push    rsi
0x18001860c  push    rdi
0x18001860d  push    r12
0x18001860f  push    r13
0x180018611  push    r14
0x180018613  push    r15
0x180018615  lea     rbp, [rsp-1Fh]
0x18001861a  sub     rsp, 0D8h
0x180018621  xor     esi, esi
0x180018623  lea     rax, aIn_0; "In"
0x18001862a  mov     [rsp+110h+var_E0], rax
0x18001862f  lea     r15, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x180018636  mov     rdi, rcx
0x180018639  mov     [rsp+110h+var_E8], rsi
0x18001863e  lea     r13, aCtracePrinttra; "CTrace::PrintTraceSettings"
0x180018645  mov     [rbp+57h+var_68], esi
0x180018648  lea     r12d, [rsi+0Eh]
0x18001864c  mov     [rbp+57h+var_70], esi
0x18001864f  mov     ecx, r12d
0x180018652  mov     [rbp+57h+hKey], rsi
0x180018656  mov     r9d, 146h
0x18001865c  mov     [rbp+57h+var_6C], esi
0x18001865f  mov     r8, r15
0x180018662  mov     [rbp+57h+arg_18], esi
0x180018665  lea     edx, [rsi+6]
0x180018668  mov     [rbp+57h+arg_8], esi
0x18001866b  mov     [rbp+57h+arg_0], esi
0x18001866e  mov     [rbp+57h+arg_10], esi
0x180018671  mov     [rbp+57h+var_58], rsi
0x180018675  mov     [rbp+57h+var_50], esi
0x180018678  mov     qword ptr [rsp+110h+var_F0], r13
0x18001867d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180018682  mov     eax, [rdi+8]
0x180018685  lea     r14d, [rsi+1]
0x180018689  sub     eax, r14d
0x18001868c  cmp     eax, 2
0x18001868f  jbe     short loc_18001869B
0x180018691  mov     ebx, 80004001h
0x180018696  jmp     loc_18001885D
0x18001869b  call    cs:__imp_GetCurrentProcessId
0x1800186a1  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800186a5  mov     [rbp+57h+var_68], eax
0x1800186a8  call    OpenTracingLoggingOptionsKey
0x1800186ad  mov     ebx, eax
0x1800186af  test    eax, eax
0x1800186b1  jns     short loc_1800186C5
0x1800186b3  lea     rax, aOpentracinglog_0; "OpenTracingLoggingOptionsKey failed"
0x1800186ba  mov     r9d, 153h
0x1800186c0  jmp     loc_180018841
0x1800186c5  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800186c9  lea     r8, [rbp+57h+var_70]; unsigned int *
0x1800186cd  mov     r9d, 19h; unsigned int
0x1800186d3  lea     rdx, aMaxbuffers; "MaxBuffers"
0x1800186da  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x1800186df  mov     ebx, eax
0x1800186e1  mov     edx, r14d; unsigned int
0x1800186e4  test    eax, eax
0x1800186e6  jns     short loc_1800186FA
0x1800186e8  lea     rax, aRegquerydwordD; "RegQueryDword(dwMaxBuffers) failed"
0x1800186ef  mov     r9d, 15Bh
0x1800186f5  jmp     loc_180018844
0x1800186fa  lea     r8, [rbp+57h+var_58]; struct _TRACE_CONTEXT *
0x1800186fe  mov     rcx, rdi; this
0x180018701  call    ?GetTraceContext@CTrace@@QEAAJKPEAU_TRACE_CONTEXT@@@Z; CTrace::GetTraceContext(ulong,_TRACE_CONTEXT *)
0x180018706  mov     ebx, eax
0x180018708  test    eax, eax
0x18001870a  jns     short loc_18001871E
0x18001870c  lea     rax, aGettracecontex; "GetTraceContext(TRACE_MODULE_DTC_ID) fa"...
0x180018713  mov     r9d, 163h
0x180018719  jmp     loc_180018841
0x18001871e  cmp     dword ptr [rbp+57h+var_58], esi
0x180018721  lea     r8, [rbp+57h+var_58]; struct _TRACE_CONTEXT *
0x180018725  mov     eax, esi
0x180018727  mov     edx, 2; unsigned int
0x18001872c  setnz   al
0x18001872f  mov     rcx, rdi; this
0x180018732  mov     [rbp+57h+var_6C], eax
0x180018735  call    ?GetTraceContext@CTrace@@QEAAJKPEAU_TRACE_CONTEXT@@@Z; CTrace::GetTraceContext(ulong,_TRACE_CONTEXT *)
0x18001873a  mov     ebx, eax
0x18001873c  test    eax, eax
0x18001873e  jns     short loc_180018752
0x180018740  lea     rax, aGettracecontex; "GetTraceContext(TRACE_MODULE_DTC_ID) fa"...
0x180018747  mov     r9d, 16Eh
0x18001874d  jmp     loc_180018841
0x180018752  cmp     dword ptr [rbp+57h+var_58], esi
0x180018755  jnz     short loc_180018765
0x180018757  mov     [rbp+57h+arg_18], esi
0x18001875a  mov     [rbp+57h+arg_8], esi
0x18001875d  mov     [rbp+57h+arg_0], esi
0x180018760  mov     [rbp+57h+arg_10], esi
0x180018763  jmp     short loc_180018795
0x180018765  mov     ecx, [rbp+57h+var_50]
0x180018768  mov     edx, 0FFFFFFh
0x18001876d  mov     eax, ecx
0x18001876f  mov     [rbp+57h+arg_18], r14d
0x180018773  and     eax, edx
0x180018775  cmp     eax, edx
0x180018777  jnz     short loc_180018783
0x180018779  mov     [rbp+57h+arg_8], r14d
0x18001877d  mov     [rbp+57h+arg_10], r14d
0x180018781  jmp     short loc_180018791
0x180018783  test    r14b, cl
0x180018786  jz      short loc_18001878C
0x180018788  mov     [rbp+57h+arg_8], r14d
0x18001878c  test    cl, 2
0x18001878f  jz      short loc_180018795
0x180018791  mov     [rbp+57h+arg_0], r14d
0x180018795  mov     [rsp+110h+var_78], rsi
0x18001879d  lea     rax, [rbp+57h+var_70]
0x1800187a1  mov     [rsp+110h+var_80], rax
0x1800187a9  lea     r9, stru_18013E510; struct _GUID *
0x1800187b0  mov     ecx, 4
0x1800187b5  lea     rax, [rbp+57h+arg_10]
0x1800187b9  mov     [rsp+110h+var_88], rcx
0x1800187c1  xor     r8d, r8d; unsigned int
0x1800187c4  mov     [rsp+110h+var_90], rax
0x1800187cc  mov     edx, r14d; unsigned int
0x1800187cf  mov     [rsp+110h+var_98], rcx
0x1800187d4  lea     rax, [rbp+57h+arg_0]
0x1800187d8  mov     [rsp+110h+var_A0], rax
0x1800187dd  lea     rax, [rbp+57h+arg_8]
0x1800187e1  mov     [rsp+110h+var_A8], rcx
0x1800187e6  mov     [rsp+110h+var_B0], rax
0x1800187eb  lea     rax, [rbp+57h+arg_18]
0x1800187ef  mov     [rsp+110h+var_B8], rcx
0x1800187f4  mov     [rsp+110h+var_C0], rax
0x1800187f9  lea     rax, [rbp+57h+var_6C]
0x1800187fd  mov     [rsp+110h+var_C8], rcx
0x180018802  mov     [rsp+110h+var_D0], rax
0x180018807  lea     rax, [rbp+57h+var_68]
0x18001880b  mov     [rsp+110h+var_D8], rcx
0x180018810  mov     [rsp+110h+var_E0], rax
0x180018815  mov     [rsp+110h+var_E8], rcx
0x18001881a  lea     rcx, ?g_Trace@@3VCTrace@@A; this
0x180018821  mov     [rsp+110h+var_F0], 0Bh; unsigned int
0x180018829  call    ?TraceEvent@CTrace@@QEAAJKKQEBU_GUID@@KZZ; CTrace::TraceEvent(ulong,ulong,_GUID const * const,ulong,...)
0x18001882e  mov     ebx, eax
0x180018830  test    eax, eax
0x180018832  jns     short loc_18001885D
0x180018834  lea     rax, aGTraceTraceeve; "g_Trace.TraceEvent(TRACE_SETTINGS) FAIL"...
0x18001883b  mov     r9d, 198h
0x180018841  mov     edx, r14d
0x180018844  mov     [rsp+110h+var_E0], rax
0x180018849  mov     r8, r15
0x18001884c  mov     dword ptr [rsp+110h+var_E8], ebx
0x180018850  mov     ecx, r12d
0x180018853  mov     qword ptr [rsp+110h+var_F0], r13
0x180018858  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001885d  mov     rcx, [rbp+57h+hKey]; hKey
0x180018861  test    rcx, rcx
0x180018864  jz      short loc_180018870
0x180018866  call    cs:__imp_RegCloseKey
0x18001886c  mov     [rbp+57h+hKey], rsi
0x180018870  lea     rax, aOut; "Out"
0x180018877  mov     r9d, 1A2h
0x18001887d  mov     [rsp+110h+var_E0], rax
0x180018882  mov     r8, r15
0x180018885  mov     [rsp+110h+var_E8], rsi
0x18001888a  mov     edx, 6
0x18001888f  mov     ecx, r12d
0x180018892  mov     qword ptr [rsp+110h+var_F0], r13
0x180018897  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001889c  mov     eax, ebx
0x18001889e  add     rsp, 0D8h
0x1800188a5  pop     r15
0x1800188a7  pop     r14
0x1800188a9  pop     r13
0x1800188ab  pop     r12
0x1800188ad  pop     rdi
0x1800188ae  pop     rsi
0x1800188af  pop     rbx
0x1800188b0  pop     rbp
0x1800188b1  retn
```
