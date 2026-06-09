# CEtwLogHelper::UpdateProviderInTraceSession(ushort const *,_EVENT_PROVIDER_PROPERTIES *)

- ea: `0x180014ab4`
- end: `0x180014c6b`
- name: `?UpdateProviderInTraceSession@CEtwLogHelper@@SAJPEBGPEAU_EVENT_PROVIDER_PROPERTIES@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, LPCGUID ProviderId)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f478`

## callees

- `0x180001108`
- `0x180001b90`
- `0x1800143b8`
- `0x180014ab4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c39`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180014b6a`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180014b6a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180014b1a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180014b1a`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
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
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)&word_1800420F6, 0, 0, 5u, &v14);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x180014ab4  mov     [rsp-8+arg_10], rbx
0x180014ab9  push    rbp
0x180014aba  push    rsi
0x180014abb  push    rdi
0x180014abc  push    r14
0x180014abe  push    r15
0x180014ac0  lea     rbp, [rsp-37h]
0x180014ac5  sub     rsp, 0B0h
0x180014acc  mov     rax, cs:__security_cookie
0x180014ad3  xor     rax, rsp
0x180014ad6  mov     [rbp+57h+var_30], rax
0x180014ada  xor     r15d, r15d
0x180014add  mov     rsi, rdx
0x180014ae0  mov     [rbp+57h+Properties], r15
0x180014ae4  mov     r14, rcx
0x180014ae7  mov     edi, r15d
0x180014aea  test    rcx, rcx
0x180014aed  jz      loc_180014B89
0x180014af3  test    rdx, rdx
0x180014af6  jz      loc_180014B89
0x180014afc  lea     rcx, [rbp+57h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180014b00  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180014b05  mov     rdi, [rbp+57h+Properties]
0x180014b09  mov     ebx, eax
0x180014b0b  test    eax, eax
0x180014b0d  js      short loc_180014B8E
0x180014b0f  xor     r9d, r9d; ControlCode
0x180014b12  mov     r8, rdi; Properties
0x180014b15  mov     rdx, r14; InstanceName
0x180014b18  xor     ecx, ecx; TraceHandle
0x180014b1a  call    cs:__imp_ControlTraceW
0x180014b21  nop     dword ptr [rax+rax+00h]
0x180014b26  test    eax, eax
0x180014b28  jz      short loc_180014B3B
0x180014b2a  jg      short loc_180014B30
0x180014b2c  mov     ebx, eax
0x180014b2e  jmp     short loc_180014B8E
0x180014b30  movzx   ebx, ax
0x180014b33  or      ebx, 80070000h
0x180014b39  jmp     short loc_180014B8E
0x180014b3b  mov     rdx, rsi; ProviderId
0x180014b3e  mov     rcx, [rdi+8]; TraceHandle
0x180014b42  mov     [rsp+0D0h+EnableParameters], r15; EnableParameters
0x180014b47  mov     [rsp+0D0h+Timeout], r15d; Timeout
0x180014b4c  mov     [rsp+0D0h+MatchAllKeyword], r15; MatchAllKeyword
0x180014b51  cmp     [rsi+1Ch], r15d
0x180014b55  jz      short loc_180014B7C
0x180014b57  mov     rax, [rsi+10h]
0x180014b5b  mov     r8d, 1; ControlCode
0x180014b61  mov     r9b, [rsi+18h]; Level
0x180014b65  mov     [rsp+0D0h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180014b6a  call    cs:__imp_EnableTraceEx2
0x180014b71  nop     dword ptr [rax+rax+00h]
0x180014b76  test    eax, eax
0x180014b78  jz      short loc_180014B8E
0x180014b7a  jmp     short loc_180014B2A
0x180014b7c  xor     r9d, r9d
0x180014b7f  mov     [rsp+0D0h+MatchAnyKeyword], r15
0x180014b84  xor     r8d, r8d
0x180014b87  jmp     short loc_180014B6A
0x180014b89  mov     ebx, 80070057h
0x180014b8e  mov     eax, cs:dword_18004AE90
0x180014b94  cmp     eax, 5
0x180014b97  jbe     loc_180014C31
0x180014b9d  test    r14, r14
0x180014ba0  mov     dword ptr [rbp+57h+Properties], ebx
0x180014ba3  lea     rax, [rbp+57h+Properties]
0x180014ba7  mov     [rbp+57h+var_38], 4
0x180014baf  lea     rcx, String2
0x180014bb6  mov     [rbp+57h+var_40], rax
0x180014bba  cmovz   r14, rcx
0x180014bbe  mov     [rbp+57h+var_48], 10h
0x180014bc6  test    rsi, rsi
0x180014bc9  lea     rax, GUID_NULL
0x180014bd0  cmovz   rsi, rax
0x180014bd4  mov     [rbp+57h+var_50], rsi
0x180014bd8  test    r14, r14
0x180014bdb  jz      short loc_180014BF4
0x180014bdd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014be1  inc     rax
0x180014be4  cmp     [r14+rax*2], r15w
0x180014be9  jnz     short loc_180014BE1
0x180014beb  lea     eax, ds:2[rax*2]
0x180014bf2  jmp     short loc_180014BFC
0x180014bf4  mov     r14, rcx
0x180014bf7  mov     eax, 2
0x180014bfc  mov     [rbp+57h+var_58], eax
0x180014bff  lea     rdx, word_1800420F6
0x180014c06  lea     rax, [rbp+57h+var_80]
0x180014c0a  mov     [rbp+57h+var_60], r14
0x180014c0e  mov     [rsp+0D0h+MatchAllKeyword], rax
0x180014c13  lea     rcx, dword_18004AE90
0x180014c1a  xor     r9d, r9d
0x180014c1d  mov     dword ptr [rsp+0D0h+MatchAnyKeyword], 5
0x180014c25  xor     r8d, r8d
0x180014c28  mov     [rbp+57h+var_54], r15d
0x180014c2c  call    _tlgWriteTransfer_EventWriteTransfer
0x180014c31  test    rdi, rdi
0x180014c34  jz      short loc_180014C45
0x180014c36  mov     rcx, rdi; pv
0x180014c39  call    cs:__imp_CoTaskMemFree
0x180014c40  nop     dword ptr [rax+rax+00h]
0x180014c45  mov     eax, ebx
0x180014c47  mov     rcx, [rbp+57h+var_30]
0x180014c4b  xor     rcx, rsp; StackCookie
0x180014c4e  call    __security_check_cookie
0x180014c53  mov     rbx, [rsp+0D0h+arg_10]
0x180014c5b  add     rsp, 0B0h
0x180014c62  pop     r15
0x180014c64  pop     r14
0x180014c66  pop     rdi
0x180014c67  pop     rsi
0x180014c68  pop     rbp
0x180014c69  retn
```
