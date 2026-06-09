# CEtwLogHelper::UpdateProviderInTraceSession(ushort const *,_EVENT_PROVIDER_PROPERTIES *)

- ea: `0x180014004`
- end: `0x1800141a8`
- name: `?UpdateProviderInTraceSession@CEtwLogHelper@@SAJPEBGPEAU_EVENT_PROVIDER_PROPERTIES@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, LPCGUID ProviderId)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000ed34`

## callees

- `0x180001104`
- `0x180001b60`
- `0x18001395c`
- `0x180014004`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001417d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001417d`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800140b4`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800140b4`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001406a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001406a`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::UpdateProviderInTraceSession(LPCWSTR InstanceName, GUID *ProviderId)
{
  GUID *v2; // rsi
  const WCHAR *v3; // r14
  PEVENT_TRACE_PROPERTIES v4; // rdi
  int SessionProperty; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  bool v8; // cc
  TRACEHANDLE HistoricalContext; // rcx
  __int64 v10; // rax
  int v11; // eax
  PEVENT_TRACE_PROPERTIES Properties[2]; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v15; // [rsp+70h] [rbp-9h]
  int v16; // [rsp+78h] [rbp-1h]
  int v17; // [rsp+7Ch] [rbp+3h]
  GUID *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  PEVENT_TRACE_PROPERTIES *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]

  v2 = ProviderId;
  Properties[0] = 0;
  v3 = InstanceName;
  v4 = 0;
  if ( InstanceName && ProviderId )
  {
    SessionProperty = CEtwLogHelper::CreateSessionProperty(Properties);
    v4 = Properties[0];
    v6 = SessionProperty;
    if ( SessionProperty >= 0 )
    {
      v7 = ControlTraceW(0, v3, Properties[0], 0);
      v8 = v7 <= 0;
      if ( v7
        || ((HistoricalContext = v4->Wnode.HistoricalContext, !*(_DWORD *)&v2[1].Data4[4])
          ? (v7 = EnableTraceEx2(HistoricalContext, v2, 0, 0, 0, 0, 0, 0))
          : (v7 = EnableTraceEx2(HistoricalContext, v2, 1u, v2[1].Data4[0], *(_QWORD *)&v2[1].Data1, 0, 0, 0)),
            v8 = v7 <= 0,
            v7) )
      {
        if ( v8 )
          v6 = v7;
        else
          v6 = (unsigned __int16)v7 | 0x80070000;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(Properties[0]) = v6;
    v21 = 4;
    v20 = Properties;
    if ( !v3 )
      v3 = &String2;
    v19 = 16;
    if ( !v2 )
      v2 = &GUID_NULL;
    v18 = v2;
    if ( v3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v3[v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      v3 = &String2;
      v11 = 2;
    }
    v16 = v11;
    v15 = v3;
    v17 = 0;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)&word_1800400F6, 0, 0, 5u, &v14);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x180014004  mov     [rsp-8+arg_10], rbx
0x180014009  push    rbp
0x18001400a  push    rsi
0x18001400b  push    rdi
0x18001400c  push    r14
0x18001400e  push    r15
0x180014010  lea     rbp, [rsp-37h]
0x180014015  sub     rsp, 0B0h
0x18001401c  mov     rax, cs:__security_cookie
0x180014023  xor     rax, rsp
0x180014026  mov     [rbp+57h+var_30], rax
0x18001402a  xor     r15d, r15d
0x18001402d  mov     rsi, rdx
0x180014030  mov     [rbp+57h+Properties], r15
0x180014034  mov     r14, rcx
0x180014037  mov     edi, r15d
0x18001403a  test    rcx, rcx
0x18001403d  jz      loc_1800140CD
0x180014043  test    rdx, rdx
0x180014046  jz      loc_1800140CD
0x18001404c  lea     rcx, [rbp+57h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180014050  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180014055  mov     rdi, [rbp+57h+Properties]
0x180014059  mov     ebx, eax
0x18001405b  test    eax, eax
0x18001405d  js      short loc_1800140D2
0x18001405f  xor     r9d, r9d; ControlCode
0x180014062  mov     r8, rdi; Properties
0x180014065  mov     rdx, r14; InstanceName
0x180014068  xor     ecx, ecx; TraceHandle
0x18001406a  call    cs:__imp_ControlTraceW
0x180014070  test    eax, eax
0x180014072  jz      short loc_180014085
0x180014074  jg      short loc_18001407A
0x180014076  mov     ebx, eax
0x180014078  jmp     short loc_1800140D2
0x18001407a  movzx   ebx, ax
0x18001407d  or      ebx, 80070000h
0x180014083  jmp     short loc_1800140D2
0x180014085  mov     rdx, rsi; ProviderId
0x180014088  mov     rcx, [rdi+8]; TraceHandle
0x18001408c  mov     [rsp+0D0h+EnableParameters], r15; EnableParameters
0x180014091  mov     [rsp+0D0h+Timeout], r15d; Timeout
0x180014096  mov     [rsp+0D0h+MatchAllKeyword], r15; MatchAllKeyword
0x18001409b  cmp     [rsi+1Ch], r15d
0x18001409f  jz      short loc_1800140C0
0x1800140a1  mov     rax, [rsi+10h]
0x1800140a5  mov     r8d, 1; ControlCode
0x1800140ab  mov     r9b, [rsi+18h]; Level
0x1800140af  mov     [rsp+0D0h+MatchAnyKeyword], rax; MatchAnyKeyword
0x1800140b4  call    cs:__imp_EnableTraceEx2
0x1800140ba  test    eax, eax
0x1800140bc  jz      short loc_1800140D2
0x1800140be  jmp     short loc_180014074
0x1800140c0  xor     r9d, r9d
0x1800140c3  mov     [rsp+0D0h+MatchAnyKeyword], r15
0x1800140c8  xor     r8d, r8d
0x1800140cb  jmp     short loc_1800140B4
0x1800140cd  mov     ebx, 80070057h
0x1800140d2  mov     eax, cs:dword_180048E90
0x1800140d8  cmp     eax, 5
0x1800140db  jbe     loc_180014175
0x1800140e1  test    r14, r14
0x1800140e4  mov     dword ptr [rbp+57h+Properties], ebx
0x1800140e7  lea     rax, [rbp+57h+Properties]
0x1800140eb  mov     [rbp+57h+var_38], 4
0x1800140f3  lea     rcx, String2
0x1800140fa  mov     [rbp+57h+var_40], rax
0x1800140fe  cmovz   r14, rcx
0x180014102  mov     [rbp+57h+var_48], 10h
0x18001410a  test    rsi, rsi
0x18001410d  lea     rax, GUID_NULL
0x180014114  cmovz   rsi, rax
0x180014118  mov     [rbp+57h+var_50], rsi
0x18001411c  test    r14, r14
0x18001411f  jz      short loc_180014138
0x180014121  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014125  inc     rax
0x180014128  cmp     [r14+rax*2], r15w
0x18001412d  jnz     short loc_180014125
0x18001412f  lea     eax, ds:2[rax*2]
0x180014136  jmp     short loc_180014140
0x180014138  mov     r14, rcx
0x18001413b  mov     eax, 2
0x180014140  mov     [rbp+57h+var_58], eax
0x180014143  lea     rdx, word_1800400F6
0x18001414a  lea     rax, [rbp+57h+var_80]
0x18001414e  mov     [rbp+57h+var_60], r14
0x180014152  mov     [rsp+0D0h+MatchAllKeyword], rax
0x180014157  lea     rcx, dword_180048E90
0x18001415e  xor     r9d, r9d
0x180014161  mov     dword ptr [rsp+0D0h+MatchAnyKeyword], 5
0x180014169  xor     r8d, r8d
0x18001416c  mov     [rbp+57h+var_54], r15d
0x180014170  call    _tlgWriteTransfer_EventWriteTransfer
0x180014175  test    rdi, rdi
0x180014178  jz      short loc_180014183
0x18001417a  mov     rcx, rdi; pv
0x18001417d  call    cs:__imp_CoTaskMemFree
0x180014183  mov     eax, ebx
0x180014185  mov     rcx, [rbp+57h+var_30]
0x180014189  xor     rcx, rsp; StackCookie
0x18001418c  call    __security_check_cookie
0x180014191  mov     rbx, [rsp+0D0h+arg_10]
0x180014199  add     rsp, 0B0h
0x1800141a0  pop     r15
0x1800141a2  pop     r14
0x1800141a4  pop     rdi
0x1800141a5  pop     rsi
0x1800141a6  pop     rbp
0x1800141a7  retn
```
