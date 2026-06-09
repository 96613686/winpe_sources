# CTrace::Init(void)

- ea: `0x180006420`
- end: `0x18000673e`
- name: `?Init@CTrace@@QEAAJXZ`
- size: `798`
- prototype: `__int64 __fastcall(CTrace *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800489a0`

## callees

- `0x1800063b0`
- `0x180006420`
- `0x18000753c`
- `0x1800146f0`
- `0x180015604`
- `0x18001f34c`
- `0x1800984f8`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000663f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000663f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000654b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000658e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000654b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000658e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065ea`

## string_xrefs

- `0x180006447`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800064d4`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18000667a`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180006713`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180006578`: `CreateEvent Failed`
- `0x1800065bb`: `CreateEvent Failed`
- `0x1800065fe`: `RegOpenKeyEx Failed`
- `0x180006616`: `RegOpenKeyEx Failed`
- `0x180006670`: `CreateThread Failed`
- `0x180006532`: `RegQueryComponentTraceContext Failed`

## pseudocode

```c
__int64 __fastcall CTrace::Init(CTrace *this)
{
  int v1; // edi
  int inited; // ebx
  CTrace *v3; // rcx
  CTrace *v4; // rcx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  signed int v7; // eax
  __int64 v8; // r9
  const wchar_t *v9; // rax
  signed int v10; // eax
  LSTATUS v11; // eax
  signed int LastError; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-40h]
  int v15; // [rsp+30h] [rbp-38h]
  DWORD ThreadId; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+74h] [rbp+Ch]

  v17 = HIDWORD(this);
  ThreadId = 0;
  TraceStringInline(14, 6, L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp", 1310, L"CTrace::Init", 0, L"In");
  if ( (unsigned int)(HIDWORD(g_Trace) - 3) > 1 )
  {
    v1 = 0;
    inited = -2147467263;
    goto LABEL_30;
  }
  (*(void (__fastcall **)(__int64 *))qword_18015CE20)(&qword_18015CE20);
  LODWORD(g_Trace) = g_Trace + 1;
  if ( HIDWORD(g_Trace) == 4 )
  {
    inited = 0;
    goto LABEL_33;
  }
  v1 = 1;
  inited = CTrace::RegisterGuids(v3);
  if ( inited < 0 )
  {
    v5 = L"RegisterGuids Failed";
    v6 = 1333;
LABEL_7:
    LODWORD(lpThreadId) = inited;
    TraceStringInline(14, 1, L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp", v6, L"CTrace::Init", lpThreadId, v5);
    goto LABEL_30;
  }
  inited = CTrace::InitSession(v4);
  if ( inited < 0 )
  {
    v5 = L"InitSession Failed";
    v6 = 1340;
    goto LABEL_7;
  }
  inited = CTrace::RegQueryComponentTraceContext(
             (CTrace *)&g_Trace,
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Modules",
             0);
  if ( inited < 0 )
  {
    v5 = L"RegQueryComponentTraceContext Failed";
    v6 = 1347;
    goto LABEL_7;
  }
  *((_QWORD *)&xmmword_18015D480 + 1) = CreateEventW(0, 0, 0, 0);
  if ( *((_QWORD *)&xmmword_18015D480 + 1) )
  {
    *(_QWORD *)&xmmword_18015D490 = CreateEventW(0, 0, 0, 0);
    if ( (_QWORD)xmmword_18015D490 )
    {
      v11 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Changed",
              0,
              0x20119u,
              (PHKEY)&xmmword_18015D490 + 1);
      if ( v11 )
      {
        if ( v11 > 0 )
        {
          v8 = 1373;
          inited = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          inited = v11;
          v8 = 1373;
        }
        v9 = L"RegOpenKeyEx Failed";
      }
      else
      {
        *(_QWORD *)&xmmword_18015D480 = CreateThread(0, 0, ThreadProc, &g_Trace, 0, &ThreadId);
        if ( (_QWORD)xmmword_18015D480 )
        {
          HIDWORD(g_Trace) = 4;
          goto LABEL_33;
        }
        LastError = GetLastError();
        inited = LastError;
        if ( LastError > 0 )
          inited = (unsigned __int16)LastError | 0x80070000;
        v8 = 1383;
        v9 = L"CreateThread Failed";
      }
    }
    else
    {
      v10 = GetLastError();
      inited = v10;
      if ( v10 > 0 )
        inited = (unsigned __int16)v10 | 0x80070000;
      v8 = 1365;
      v9 = (const wchar_t *)L"CreateEvent Failed";
    }
  }
  else
  {
    v7 = GetLastError();
    inited = v7;
    if ( v7 > 0 )
      inited = (unsigned __int16)v7 | 0x80070000;
    v8 = 1356;
    v9 = (const wchar_t *)L"CreateEvent Failed";
  }
  LODWORD(lpThreadId) = inited;
  TraceStringInline(14, 1, L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp", v8, L"CTrace::Init", lpThreadId, v9);
  if ( inited < 0 )
  {
LABEL_30:
    CTrace::InternalTerminate((CTrace *)&g_Trace);
    DtcWriteToEventLoggerA(1u, 0xDu, 0xC0001134, 0, 0, "none available", v15);
    if ( !v1 )
      goto LABEL_34;
  }
LABEL_33:
  (*(void (__fastcall **)(__int64 *))(qword_18015CE20 + 8))(&qword_18015CE20);
LABEL_34:
  TraceStringInline(14, 6, L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp", 1403, L"CTrace::Init", 0, L"Out");
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180006420  mov     qword ptr [rsp+ThreadId], rcx
0x180006425  push    rbx
0x180006426  push    rbp
0x180006427  push    rsi
0x180006428  push    rdi
0x180006429  sub     rsp, 48h
0x18000642d  lea     rax, aIn_0; "In"
0x180006434  xor     esi, esi
0x180006436  mov     qword ptr [rsp+68h+var_38], rax
0x18000643b  lea     rbp, aCtraceInit; "CTrace::Init"
0x180006442  mov     [rsp+68h+lpThreadId], rsi
0x180006447  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18000644e  mov     r9d, 51Eh
0x180006454  mov     [rsp+68h+phkResult], rbp
0x180006459  mov     edx, 6
0x18000645e  mov     [rsp+68h+ThreadId], esi
0x180006462  mov     ecx, 0Eh
0x180006467  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000646c  mov     eax, dword ptr cs:?g_Trace@@3VCTrace@@A+4; CTrace g_Trace
0x180006472  add     eax, 0FFFFFFFDh
0x180006475  cmp     eax, 1
0x180006478  jbe     short loc_180006486
0x18000647a  mov     edi, esi
0x18000647c  mov     ebx, 80004001h
0x180006481  jmp     loc_1800066A5
0x180006486  mov     rax, cs:qword_18015CE20
0x18000648d  lea     rcx, qword_18015CE20
0x180006494  mov     rax, [rax]
0x180006497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649c  inc     dword ptr cs:?g_Trace@@3VCTrace@@A; CTrace g_Trace
0x1800064a2  cmp     dword ptr cs:?g_Trace@@3VCTrace@@A+4, 4; CTrace g_Trace
0x1800064a9  jnz     short loc_1800064B2
0x1800064ab  mov     ebx, esi
0x1800064ad  jmp     loc_1800066EA
0x1800064b2  mov     edi, 1
0x1800064b7  call    ?RegisterGuids@CTrace@@AEAAJXZ; CTrace::RegisterGuids(void)
0x1800064bc  mov     ebx, eax
0x1800064be  test    eax, eax
0x1800064c0  jns     short loc_1800064F5
0x1800064c2  lea     rax, aRegisterguidsF; "RegisterGuids Failed"
0x1800064c9  mov     r9d, 535h
0x1800064cf  mov     qword ptr [rsp+68h+var_38], rax
0x1800064d4  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800064db  mov     dword ptr [rsp+68h+lpThreadId], ebx
0x1800064df  mov     edx, edi
0x1800064e1  mov     ecx, 0Eh
0x1800064e6  mov     [rsp+68h+phkResult], rbp
0x1800064eb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800064f0  jmp     loc_1800066A5
0x1800064f5  call    ?InitSession@CTrace@@QEAAJH@Z; CTrace::InitSession(int)
0x1800064fa  mov     ebx, eax
0x1800064fc  test    eax, eax
0x1800064fe  jns     short loc_18000650F
0x180006500  lea     rax, aInitsessionFai; "InitSession Failed"
0x180006507  mov     r9d, 53Ch
0x18000650d  jmp     short loc_1800064CF
0x18000650f  xor     r9d, r9d; struct _TRACE_CONTEXT *
0x180006512  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180006519  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180006520  lea     rcx, ?g_Trace@@3VCTrace@@A; this
0x180006527  call    ?RegQueryComponentTraceContext@CTrace@@AEAAJPEAUHKEY__@@PEAGPEAU_TRACE_CONTEXT@@@Z; CTrace::RegQueryComponentTraceContext(HKEY__ *,ushort *,_TRACE_CONTEXT *)
0x18000652c  mov     ebx, eax
0x18000652e  test    eax, eax
0x180006530  jns     short loc_180006541
0x180006532  lea     rax, aRegquerycompon; "RegQueryComponentTraceContext Failed"
0x180006539  mov     r9d, 543h
0x18000653f  jmp     short loc_1800064CF
0x180006541  xor     r9d, r9d; lpName
0x180006544  xor     r8d, r8d; bInitialState
0x180006547  xor     edx, edx; bManualReset
0x180006549  xor     ecx, ecx; lpEventAttributes
0x18000654b  call    cs:__imp_CreateEventW
0x180006551  mov     qword ptr cs:xmmword_18015D480+8, rax
0x180006558  test    rax, rax
0x18000655b  jnz     short loc_180006584
0x18000655d  call    cs:__imp_GetLastError
0x180006563  mov     ebx, eax
0x180006565  test    eax, eax
0x180006567  jle     short loc_180006572
0x180006569  movzx   ebx, ax
0x18000656c  or      ebx, 80070000h
0x180006572  mov     r9d, 54Ch
0x180006578  lea     rax, aCreateeventFai_0; "CreateEvent Failed"
0x18000657f  jmp     loc_180006677
0x180006584  xor     r9d, r9d; lpName
0x180006587  xor     r8d, r8d; bInitialState
0x18000658a  xor     edx, edx; bManualReset
0x18000658c  xor     ecx, ecx; lpEventAttributes
0x18000658e  call    cs:__imp_CreateEventW
0x180006594  mov     qword ptr cs:xmmword_18015D490, rax
0x18000659b  test    rax, rax
0x18000659e  jnz     short loc_1800065C7
0x1800065a0  call    cs:__imp_GetLastError
0x1800065a6  mov     ebx, eax
0x1800065a8  test    eax, eax
0x1800065aa  jle     short loc_1800065B5
0x1800065ac  movzx   ebx, ax
0x1800065af  or      ebx, 80070000h
0x1800065b5  mov     r9d, 555h
0x1800065bb  lea     rax, aCreateeventFai_0; "CreateEvent Failed"
0x1800065c2  jmp     loc_180006677
0x1800065c7  lea     rax, xmmword_18015D490+8
0x1800065ce  mov     r9d, 20119h; samDesired
0x1800065d4  xor     r8d, r8d; ulOptions
0x1800065d7  mov     [rsp+68h+phkResult], rax; phkResult
0x1800065dc  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800065e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800065ea  call    cs:__imp_RegOpenKeyExW
0x1800065f0  test    eax, eax
0x1800065f2  jz      short loc_18000661F
0x1800065f4  jg      short loc_180006607
0x1800065f6  mov     ebx, eax
0x1800065f8  mov     r9d, 55Dh
0x1800065fe  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx Failed"
0x180006605  jmp     short loc_180006677
0x180006607  movzx   ebx, ax
0x18000660a  mov     r9d, 55Dh
0x180006610  or      ebx, 80070000h
0x180006616  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx Failed"
0x18000661d  jmp     short loc_180006677
0x18000661f  lea     rax, [rsp+68h+ThreadId]
0x180006624  xor     edx, edx; dwStackSize
0x180006626  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18000662b  lea     r9, ?g_Trace@@3VCTrace@@A; lpParameter
0x180006632  lea     r8, ThreadProc; lpStartAddress
0x180006639  mov     dword ptr [rsp+68h+phkResult], esi; dwCreationFlags
0x18000663d  xor     ecx, ecx; lpThreadAttributes
0x18000663f  call    cs:__imp_CreateThread
0x180006645  mov     qword ptr cs:xmmword_18015D480, rax
0x18000664c  test    rax, rax
0x18000664f  jnz     loc_1800066E0
0x180006655  call    cs:__imp_GetLastError
0x18000665b  mov     ebx, eax
0x18000665d  test    eax, eax
0x18000665f  jle     short loc_18000666A
0x180006661  movzx   ebx, ax
0x180006664  or      ebx, 80070000h
0x18000666a  mov     r9d, 567h
0x180006670  lea     rax, aCreatethreadFa_0; "CreateThread Failed"
0x180006677  mov     r11d, ebx
0x18000667a  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x180006681  mov     r10, rbp
0x180006684  mov     dl, 1
0x180006686  mov     ecx, 0Eh
0x18000668b  mov     qword ptr [rsp+68h+var_38], rax; int
0x180006690  mov     dword ptr [rsp+68h+lpThreadId], ebx
0x180006694  movzx   edx, dl
0x180006697  mov     [rsp+68h+phkResult], rbp
0x18000669c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800066a1  test    ebx, ebx
0x1800066a3  jns     short loc_1800066EA
0x1800066a5  lea     rcx, ?g_Trace@@3VCTrace@@A; this
0x1800066ac  call    ?InternalTerminate@CTrace@@AEAAXXZ; CTrace::InternalTerminate(void)
0x1800066b1  lea     rax, aNoneAvailable; "none available"
0x1800066b8  xor     r9d, r9d; unsigned int
0x1800066bb  mov     [rsp+68h+lpThreadId], rax; char *
0x1800066c0  mov     edx, 0Dh; unsigned int
0x1800066c5  mov     ecx, 1; unsigned int
0x1800066ca  mov     [rsp+68h+phkResult], rsi; void *
0x1800066cf  mov     r8d, 0C0001134h; unsigned int
0x1800066d5  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x1800066da  test    edi, edi
0x1800066dc  jnz     short loc_1800066EA
0x1800066de  jmp     short loc_180006701
0x1800066e0  mov     dword ptr cs:?g_Trace@@3VCTrace@@A+4, 4; CTrace g_Trace
0x1800066ea  mov     rax, cs:qword_18015CE20
0x1800066f1  lea     rcx, qword_18015CE20
0x1800066f8  mov     rax, [rax+8]
0x1800066fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006701  lea     rax, aOut; "Out"
0x180006708  mov     r9d, 57Bh
0x18000670e  mov     qword ptr [rsp+68h+var_38], rax
0x180006713  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18000671a  mov     [rsp+68h+lpThreadId], rsi
0x18000671f  mov     edx, 6
0x180006724  mov     ecx, 0Eh
0x180006729  mov     [rsp+68h+phkResult], rbp
0x18000672e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006733  mov     eax, ebx
0x180006735  add     rsp, 48h
0x180006739  pop     rdi
0x18000673a  pop     rsi
0x18000673b  pop     rbp
0x18000673c  pop     rbx
0x18000673d  retn
```
