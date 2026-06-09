# CEtwLogHelper::StartTraceSession(ushort const *,ulong,ulong,ushort const *,ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)

- ea: `0x1800146e4`
- end: `0x1800148e7`
- name: `?StartTraceSession@CEtwLogHelper@@SAJPEBGKK0AEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z`
- size: `515`
- prototype: `__int64 __usercall@<rax>(LPCWSTR InstanceName@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ef14`

## callees

- `0x1800011ac`
- `0x180007530`
- `0x1800143b8`
- `0x1800144bc`
- `0x1800146e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148bc`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800147e3`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800147e3`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180014858`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180014858`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::StartTraceSession(
        WCHAR *InstanceName,
        int a2,
        ULONG a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  unsigned __int16 *v5; // rsi
  ULONG v6; // r12d
  WCHAR *v8; // r14
  PEVENT_TRACE_PROPERTIES v9; // rdi
  signed int TraceSessionStatus; // ebx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rax
  signed int started; // eax
  __int64 v16; // rdx
  bool v17; // cc
  __int64 v18; // r15
  unsigned int v19; // esi
  int v20; // r12d
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp-18h] BYREF
  ULONG64 TraceHandle[2]; // [rsp+48h] [rbp-10h] BYREF
  int v24; // [rsp+A0h] [rbp+48h] BYREF

  v5 = a4;
  v24 = 0;
  v6 = a3;
  Properties = 0;
  TraceHandle[0] = 0;
  v8 = InstanceName;
  v9 = 0;
  if ( !InstanceName || !a4 )
    goto LABEL_25;
  TraceSessionStatus = CEtwLogHelper::GetTraceSessionStatus(InstanceName, &v24);
  if ( TraceSessionStatus < 0 )
    goto LABEL_26;
  if ( v24 == 1 )
  {
    TraceSessionStatus = 0;
    goto LABEL_26;
  }
  v11 = CEtwLogHelper::CreateSessionProperty(&Properties);
  v9 = Properties;
  TraceSessionStatus = v11;
  if ( v11 >= 0 )
  {
    Properties->Wnode.Flags = 0x20000;
    v9->Wnode.ClientContext = 2;
    v12 = 2147483646;
    v9->LogFileMode = a2 | 0x18000000;
    v13 = 1025;
    v9->MaximumFileSize = v6;
    v14 = (WCHAR *)((char *)v9 + v9->LogFileNameOffset);
    do
    {
      if ( !v12 )
        break;
      a3 = *v5;
      if ( !(_WORD)a3 )
        break;
      *v14 = a3;
      ++v5;
      ++v14;
      --v12;
      --v13;
    }
    while ( v13 );
    InstanceName = v14 - 1;
    if ( v13 )
      InstanceName = v14;
    *InstanceName = 0;
    TraceSessionStatus = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
    {
      started = StartTraceW(TraceHandle, v8, v9);
      v17 = started <= 0;
      if ( started )
      {
LABEL_15:
        if ( v17 )
          TraceSessionStatus = started;
        else
          TraceSessionStatus = (unsigned __int16)started | 0x80070000;
        goto LABEL_26;
      }
      v18 = a5;
      v19 = 0;
      v20 = *(_DWORD *)(a5 + 8);
      if ( v20 <= 0 )
        goto LABEL_26;
      while ( 1 )
      {
        if ( (signed int)v19 >= *(_DWORD *)(v18 + 8) )
        {
          ATL::_AtlRaiseException(0xC000008C, v16);
          JUMPOUT(0x1800148E6LL);
        }
        LODWORD(InstanceName) = v19;
        v16 = *(_QWORD *)(*(_QWORD *)v18 + 8LL * v19);
        if ( !v16 )
          break;
        if ( *(_DWORD *)(v16 + 28) )
        {
          started = EnableTraceEx2(
                      TraceHandle[0],
                      (LPCGUID)v16,
                      1u,
                      *(_BYTE *)(v16 + 24),
                      *(_QWORD *)(v16 + 16),
                      0,
                      0,
                      0);
          v17 = started <= 0;
          if ( started )
            goto LABEL_15;
        }
        if ( (int)++v19 >= v20 )
          goto LABEL_26;
      }
LABEL_25:
      TraceSessionStatus = -2147024809;
    }
  }
LABEL_26:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v24 = TraceSessionStatus;
    if ( !v8 )
      v8 = (WCHAR *)&String2;
    Properties = (PEVENT_TRACE_PROPERTIES)v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)InstanceName,
      (unsigned int)&dword_1800421A4,
      a3,
      (_DWORD)a4,
      (__int64)&Properties,
      (__int64)&v24);
  }
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)TraceSessionStatus;
}

```

## disassembly

```asm
0x1800146e4  push    rbp
0x1800146e6  push    rbx
0x1800146e7  push    rsi
0x1800146e8  push    rdi
0x1800146e9  push    r12
0x1800146eb  push    r13
0x1800146ed  push    r14
0x1800146ef  push    r15
0x1800146f1  mov     rbp, rsp
0x1800146f4  sub     rsp, 58h
0x1800146f8  xor     r13d, r13d
0x1800146fb  mov     rsi, r9
0x1800146fe  mov     [rbp+arg_0], r13d
0x180014702  mov     r12d, r8d
0x180014705  mov     [rbp+Properties], r13
0x180014709  mov     r15d, edx
0x18001470c  mov     [rbp+TraceHandle], r13
0x180014710  mov     r14, rcx
0x180014713  mov     edi, r13d
0x180014716  test    rcx, rcx
0x180014719  jz      loc_180014871
0x18001471f  test    r9, r9
0x180014722  jz      loc_180014871
0x180014728  lea     rdx, [rbp+arg_0]; int *
0x18001472c  call    ?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z; CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)
0x180014731  mov     ebx, eax
0x180014733  test    eax, eax
0x180014735  js      loc_180014876
0x18001473b  cmp     [rbp+arg_0], 1
0x18001473f  jnz     short loc_180014749
0x180014741  mov     ebx, r13d
0x180014744  jmp     loc_180014876
0x180014749  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x18001474d  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180014752  mov     rdi, [rbp+Properties]
0x180014756  mov     ebx, eax
0x180014758  test    eax, eax
0x18001475a  js      loc_180014876
0x180014760  mov     dword ptr [rdi+2Ch], 20000h
0x180014767  or      r15d, 18000000h
0x18001476e  mov     dword ptr [rdi+28h], 2
0x180014775  mov     ecx, 7FFFFFFEh
0x18001477a  mov     [rdi+40h], r15d
0x18001477e  mov     edx, 401h
0x180014783  mov     [rdi+3Ch], r12d
0x180014787  mov     eax, [rdi+70h]
0x18001478a  add     rax, rdi
0x18001478d  test    rcx, rcx
0x180014790  jz      short loc_1800147B1
0x180014792  movzx   r8d, word ptr [rsi]
0x180014796  test    r8w, r8w
0x18001479a  jz      short loc_1800147B1
0x18001479c  mov     [rax], r8w
0x1800147a0  add     rsi, 2
0x1800147a4  add     rax, 2
0x1800147a8  dec     rcx
0x1800147ab  sub     rdx, 1
0x1800147af  jnz     short loc_18001478D
0x1800147b1  test    rdx, rdx
0x1800147b4  lea     rcx, [rax-2]
0x1800147b8  cmovnz  rcx, rax
0x1800147bc  mov     rax, rdx
0x1800147bf  neg     rax
0x1800147c2  sbb     ebx, ebx
0x1800147c4  not     ebx
0x1800147c6  mov     [rcx], r13w
0x1800147ca  and     ebx, 8007007Ah
0x1800147d0  test    rdx, rdx
0x1800147d3  jz      loc_180014876
0x1800147d9  mov     r8, rdi; Properties
0x1800147dc  lea     rcx, [rbp+TraceHandle]; TraceHandle
0x1800147e0  mov     rdx, r14; InstanceName
0x1800147e3  call    cs:__imp_StartTraceW
0x1800147ea  nop     dword ptr [rax+rax+00h]
0x1800147ef  test    eax, eax
0x1800147f1  jz      short loc_180014804
0x1800147f3  jg      short loc_1800147F9
0x1800147f5  mov     ebx, eax
0x1800147f7  jmp     short loc_180014876
0x1800147f9  movzx   ebx, ax
0x1800147fc  or      ebx, 80070000h
0x180014802  jmp     short loc_180014876
0x180014804  mov     r15, [rbp+arg_20]
0x180014808  mov     esi, r13d
0x18001480b  mov     r12d, [r15+8]
0x18001480f  test    r12d, r12d
0x180014812  jle     short loc_180014876
0x180014814  cmp     esi, [r15+8]
0x180014818  jge     loc_1800148DC
0x18001481e  mov     rax, [r15]
0x180014821  mov     ecx, esi
0x180014823  mov     rdx, [rax+rcx*8]; ProviderId
0x180014827  test    rdx, rdx
0x18001482a  jz      short loc_180014871
0x18001482c  cmp     [rdx+1Ch], r13d
0x180014830  jz      short loc_180014868
0x180014832  mov     rax, [rdx+10h]
0x180014836  mov     r8d, 1; ControlCode
0x18001483c  mov     r9b, [rdx+18h]; Level
0x180014840  mov     rcx, [rbp+TraceHandle]; TraceHandle
0x180014844  mov     [rsp+58h+EnableParameters], r13; EnableParameters
0x180014849  mov     [rsp+58h+Timeout], r13d; Timeout
0x18001484e  mov     [rsp+58h+MatchAllKeyword], r13; MatchAllKeyword
0x180014853  mov     [rsp+58h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180014858  call    cs:__imp_EnableTraceEx2
0x18001485f  nop     dword ptr [rax+rax+00h]
0x180014864  test    eax, eax
0x180014866  jnz     short loc_1800147F3
0x180014868  inc     esi
0x18001486a  cmp     esi, r12d
0x18001486d  jl      short loc_180014814
0x18001486f  jmp     short loc_180014876
0x180014871  mov     ebx, 80070057h
0x180014876  mov     eax, cs:dword_18004AE90
0x18001487c  cmp     eax, 5
0x18001487f  jbe     short loc_1800148B4
0x180014881  test    r14, r14
0x180014884  mov     [rbp+arg_0], ebx
0x180014887  lea     rax, String2
0x18001488e  cmovz   r14, rax
0x180014892  lea     rdx, dword_1800421A4
0x180014899  lea     rax, [rbp+arg_0]
0x18001489d  mov     [rbp+Properties], r14
0x1800148a1  mov     [rsp+58h+MatchAllKeyword], rax
0x1800148a6  lea     rax, [rbp+Properties]
0x1800148aa  mov     [rsp+58h+MatchAnyKeyword], rax
0x1800148af  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800148b4  test    rdi, rdi
0x1800148b7  jz      short loc_1800148C8
0x1800148b9  mov     rcx, rdi; pv
0x1800148bc  call    cs:__imp_CoTaskMemFree
0x1800148c3  nop     dword ptr [rax+rax+00h]
0x1800148c8  mov     eax, ebx
0x1800148ca  add     rsp, 58h
0x1800148ce  pop     r15
0x1800148d0  pop     r14
0x1800148d2  pop     r13
0x1800148d4  pop     r12
0x1800148d6  pop     rdi
0x1800148d7  pop     rsi
0x1800148d8  pop     rbx
0x1800148d9  pop     rbp
0x1800148da  retn
0x1800148dc  mov     ecx, 0C000008Ch; unsigned int
0x1800148e1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
