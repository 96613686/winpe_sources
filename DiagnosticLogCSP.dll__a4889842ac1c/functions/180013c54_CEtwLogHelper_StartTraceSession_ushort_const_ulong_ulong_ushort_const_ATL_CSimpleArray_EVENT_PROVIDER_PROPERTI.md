# CEtwLogHelper::StartTraceSession(ushort const *,ulong,ulong,ushort const *,ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)

- ea: `0x180013c54`
- end: `0x180013e44`
- name: `?StartTraceSession@CEtwLogHelper@@SAJPEBGKK0AEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z`
- size: `496`
- prototype: `__int64 __usercall@<rax>(LPCWSTR InstanceName@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e7e8`

## callees

- `0x1800011a4`
- `0x1800073e0`
- `0x18001395c`
- `0x180013a4c`
- `0x180013c54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e20`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180013d53`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180013d53`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180013dc2`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180013dc2`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::StartTraceSession(__int64 InstanceName, int a2, __int64 a3, __int64 a4, __int64 a5)
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
  bool v16; // cc
  __int64 v17; // r15
  unsigned int v18; // esi
  int v19; // r12d
  __int64 v20; // rdx
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp-18h] BYREF
  ULONG64 TraceHandle[2]; // [rsp+48h] [rbp-10h] BYREF
  int v24; // [rsp+A0h] [rbp+48h] BYREF

  v5 = (unsigned __int16 *)a4;
  v24 = 0;
  v6 = a3;
  Properties = 0;
  TraceHandle[0] = 0;
  v8 = (WCHAR *)InstanceName;
  v9 = 0;
  if ( !InstanceName || !a4 )
    goto LABEL_25;
  TraceSessionStatus = CEtwLogHelper::GetTraceSessionStatus((LPCWSTR)InstanceName, &v24);
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
    InstanceName = (__int64)(v14 - 1);
    if ( v13 )
      InstanceName = (__int64)v14;
    *(_WORD *)InstanceName = 0;
    TraceSessionStatus = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
    {
      started = StartTraceW(TraceHandle, v8, v9);
      v16 = started <= 0;
      if ( started )
      {
LABEL_15:
        if ( v16 )
          TraceSessionStatus = started;
        else
          TraceSessionStatus = (unsigned __int16)started | 0x80070000;
        goto LABEL_26;
      }
      v17 = a5;
      v18 = 0;
      v19 = *(_DWORD *)(a5 + 8);
      if ( v19 <= 0 )
        goto LABEL_26;
      while ( 1 )
      {
        if ( (signed int)v18 >= *(_DWORD *)(v17 + 8) )
        {
          ATL::_AtlRaiseException(0xC000008C);
          JUMPOUT(0x180013E43LL);
        }
        InstanceName = v18;
        v20 = *(_QWORD *)(*(_QWORD *)v17 + 8LL * v18);
        if ( !v20 )
          break;
        if ( *(_DWORD *)(v20 + 28) )
        {
          started = EnableTraceEx2(
                      TraceHandle[0],
                      (LPCGUID)v20,
                      1u,
                      *(_BYTE *)(v20 + 24),
                      *(_QWORD *)(v20 + 16),
                      0,
                      0,
                      0);
          v16 = started <= 0;
          if ( started )
            goto LABEL_15;
        }
        if ( (int)++v18 >= v19 )
          goto LABEL_26;
      }
LABEL_25:
      TraceSessionStatus = -2147024809;
    }
  }
LABEL_26:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v24 = TraceSessionStatus;
    if ( !v8 )
      v8 = (WCHAR *)&String2;
    Properties = (PEVENT_TRACE_PROPERTIES)v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      InstanceName,
      (__int64)&dword_1800401A4,
      a3,
      a4,
      (const WCHAR **)&Properties,
      (__int64)&v24);
  }
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)TraceSessionStatus;
}

```

## disassembly

```asm
0x180013c54  push    rbp
0x180013c56  push    rbx
0x180013c57  push    rsi
0x180013c58  push    rdi
0x180013c59  push    r12
0x180013c5b  push    r13
0x180013c5d  push    r14
0x180013c5f  push    r15
0x180013c61  mov     rbp, rsp
0x180013c64  sub     rsp, 58h
0x180013c68  xor     r13d, r13d
0x180013c6b  mov     rsi, r9
0x180013c6e  mov     [rbp+arg_0], r13d
0x180013c72  mov     r12d, r8d
0x180013c75  mov     [rbp+Properties], r13
0x180013c79  mov     r15d, edx
0x180013c7c  mov     [rbp+TraceHandle], r13
0x180013c80  mov     r14, rcx
0x180013c83  mov     edi, r13d
0x180013c86  test    rcx, rcx
0x180013c89  jz      loc_180013DD5
0x180013c8f  test    r9, r9
0x180013c92  jz      loc_180013DD5
0x180013c98  lea     rdx, [rbp+arg_0]; int *
0x180013c9c  call    ?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z; CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)
0x180013ca1  mov     ebx, eax
0x180013ca3  test    eax, eax
0x180013ca5  js      loc_180013DDA
0x180013cab  cmp     [rbp+arg_0], 1
0x180013caf  jnz     short loc_180013CB9
0x180013cb1  mov     ebx, r13d
0x180013cb4  jmp     loc_180013DDA
0x180013cb9  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180013cbd  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180013cc2  mov     rdi, [rbp+Properties]
0x180013cc6  mov     ebx, eax
0x180013cc8  test    eax, eax
0x180013cca  js      loc_180013DDA
0x180013cd0  mov     dword ptr [rdi+2Ch], 20000h
0x180013cd7  or      r15d, 18000000h
0x180013cde  mov     dword ptr [rdi+28h], 2
0x180013ce5  mov     ecx, 7FFFFFFEh
0x180013cea  mov     [rdi+40h], r15d
0x180013cee  mov     edx, 401h
0x180013cf3  mov     [rdi+3Ch], r12d
0x180013cf7  mov     eax, [rdi+70h]
0x180013cfa  add     rax, rdi
0x180013cfd  test    rcx, rcx
0x180013d00  jz      short loc_180013D21
0x180013d02  movzx   r8d, word ptr [rsi]
0x180013d06  test    r8w, r8w
0x180013d0a  jz      short loc_180013D21
0x180013d0c  mov     [rax], r8w
0x180013d10  add     rsi, 2
0x180013d14  add     rax, 2
0x180013d18  dec     rcx
0x180013d1b  sub     rdx, 1
0x180013d1f  jnz     short loc_180013CFD
0x180013d21  test    rdx, rdx
0x180013d24  lea     rcx, [rax-2]
0x180013d28  cmovnz  rcx, rax
0x180013d2c  mov     rax, rdx
0x180013d2f  neg     rax
0x180013d32  sbb     ebx, ebx
0x180013d34  not     ebx
0x180013d36  mov     [rcx], r13w
0x180013d3a  and     ebx, 8007007Ah
0x180013d40  test    rdx, rdx
0x180013d43  jz      loc_180013DDA
0x180013d49  mov     r8, rdi; Properties
0x180013d4c  lea     rcx, [rbp+TraceHandle]; TraceHandle
0x180013d50  mov     rdx, r14; InstanceName
0x180013d53  call    cs:__imp_StartTraceW
0x180013d59  test    eax, eax
0x180013d5b  jz      short loc_180013D6E
0x180013d5d  jg      short loc_180013D63
0x180013d5f  mov     ebx, eax
0x180013d61  jmp     short loc_180013DDA
0x180013d63  movzx   ebx, ax
0x180013d66  or      ebx, 80070000h
0x180013d6c  jmp     short loc_180013DDA
0x180013d6e  mov     r15, [rbp+arg_20]
0x180013d72  mov     esi, r13d
0x180013d75  mov     r12d, [r15+8]
0x180013d79  test    r12d, r12d
0x180013d7c  jle     short loc_180013DDA
0x180013d7e  cmp     esi, [r15+8]
0x180013d82  jge     loc_180013E39
0x180013d88  mov     rax, [r15]
0x180013d8b  mov     ecx, esi
0x180013d8d  mov     rdx, [rax+rcx*8]; ProviderId
0x180013d91  test    rdx, rdx
0x180013d94  jz      short loc_180013DD5
0x180013d96  cmp     [rdx+1Ch], r13d
0x180013d9a  jz      short loc_180013DCC
0x180013d9c  mov     rax, [rdx+10h]
0x180013da0  mov     r8d, 1; ControlCode
0x180013da6  mov     r9b, [rdx+18h]; Level
0x180013daa  mov     rcx, [rbp+TraceHandle]; TraceHandle
0x180013dae  mov     [rsp+58h+EnableParameters], r13; EnableParameters
0x180013db3  mov     [rsp+58h+Timeout], r13d; Timeout
0x180013db8  mov     [rsp+58h+MatchAllKeyword], r13; MatchAllKeyword
0x180013dbd  mov     [rsp+58h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180013dc2  call    cs:__imp_EnableTraceEx2
0x180013dc8  test    eax, eax
0x180013dca  jnz     short loc_180013D5D
0x180013dcc  inc     esi
0x180013dce  cmp     esi, r12d
0x180013dd1  jl      short loc_180013D7E
0x180013dd3  jmp     short loc_180013DDA
0x180013dd5  mov     ebx, 80070057h
0x180013dda  mov     eax, cs:dword_180048E90
0x180013de0  cmp     eax, 5
0x180013de3  jbe     short loc_180013E18
0x180013de5  test    r14, r14
0x180013de8  mov     [rbp+arg_0], ebx
0x180013deb  lea     rax, String2
0x180013df2  cmovz   r14, rax
0x180013df6  lea     rdx, dword_1800401A4
0x180013dfd  lea     rax, [rbp+arg_0]
0x180013e01  mov     [rbp+Properties], r14
0x180013e05  mov     [rsp+58h+MatchAllKeyword], rax
0x180013e0a  lea     rax, [rbp+Properties]
0x180013e0e  mov     [rsp+58h+MatchAnyKeyword], rax
0x180013e13  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013e18  test    rdi, rdi
0x180013e1b  jz      short loc_180013E26
0x180013e1d  mov     rcx, rdi; pv
0x180013e20  call    cs:__imp_CoTaskMemFree
0x180013e26  mov     eax, ebx
0x180013e28  add     rsp, 58h
0x180013e2c  pop     r15
0x180013e2e  pop     r14
0x180013e30  pop     r13
0x180013e32  pop     r12
0x180013e34  pop     rdi
0x180013e35  pop     rsi
0x180013e36  pop     rbx
0x180013e37  pop     rbp
0x180013e38  retn
0x180013e39  mov     ecx, 0C000008Ch; unsigned int
0x180013e3e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
