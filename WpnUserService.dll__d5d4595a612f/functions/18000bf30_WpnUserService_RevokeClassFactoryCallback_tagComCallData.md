# WpnUserService::RevokeClassFactoryCallback(tagComCallData *)

- ea: `0x18000bf30`
- end: `0x18000c125`
- name: `?RevokeClassFactoryCallback@WpnUserService@@SAJPEAUtagComCallData@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180006244`
- `0x18000a648`
- `0x18000bf30`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c10d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c10d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0c8`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000c055`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000c055`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18000c0de`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18000c0de`

## string_xrefs

- `0x18000bf53`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000c0ef`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnUserService::RevokeClassFactoryCallback(struct tagComCallData *a1)
{
  unsigned int v1; // ebx
  HANDLE *pUserDefined; // rcx
  HANDLE v3; // rbx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  int v6; // r9d
  const struct _tlgProvider_t *v7; // r8
  __int64 v8; // rax
  HANDLE v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  int v11; // r9d
  const struct _tlgProvider_t *v12; // r8
  __int64 v13; // rax
  HRESULT v14; // eax
  __int64 v15; // rdx
  HANDLE v16; // rbx
  const struct _tlgProvider_t *v17; // rax
  int v18; // r9d
  const struct _tlgProvider_t *v19; // r8
  __int64 v20; // rax
  BOOL v21; // eax
  int v23; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HANDLE *v25; // [rsp+50h] [rbp+10h]
  __int64 v26; // [rsp+58h] [rbp+18h] BYREF

  if ( a1 )
  {
    pUserDefined = (HANDLE *)a1->pUserDefined;
    v25 = pUserDefined;
    if ( *(_QWORD *)pUserDefined[2] )
    {
      v3 = pUserDefined[3];
      v4 = ServiceHostLogging::Provider();
      v7 = v4;
      if ( *(_DWORD *)v4 > 5u )
      {
        v8 = *((_QWORD *)v4 + 3);
        if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
        {
          v26 = (__int64)v3 + 8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v7,
            (unsigned int)word_1800149F2,
            (_DWORD)v7,
            v6,
            (__int64)&v26);
        }
      }
      (*(void (__fastcall **)(_QWORD, __int64, const struct _tlgProvider_t *))(**(_QWORD **)v25[2] + 32LL))(
        *(_QWORD *)v25[2],
        v5,
        v7);
      pUserDefined = v25;
    }
    if ( *(_DWORD *)pUserDefined[1] )
    {
      v9 = pUserDefined[3];
      v10 = ServiceHostLogging::Provider();
      v12 = v10;
      if ( *(_DWORD *)v10 > 5u )
      {
        v13 = *((_QWORD *)v10 + 3);
        if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
        {
          v26 = (__int64)v9 + 8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v12,
            (unsigned int)word_1800149C2,
            (_DWORD)v12,
            v11,
            (__int64)&v26);
        }
      }
      v14 = CoRevokeClassObject(*(_DWORD *)v25[1]);
      v1 = v14;
      if ( v14 < 0 )
      {
        v15 = 380;
        goto LABEL_23;
      }
      *(_DWORD *)v25[1] = 0;
      pUserDefined = v25;
    }
    v16 = pUserDefined[3];
    v17 = ServiceHostLogging::Provider();
    v19 = v17;
    if ( *(_DWORD *)v17 > 5u )
    {
      v20 = *((_QWORD *)v17 + 3);
      if ( (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0 && (v20 & 0x400000000000LL) == v20 )
      {
        v26 = (__int64)v16 + 8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v19,
          (unsigned int)byte_180014991,
          (_DWORD)v19,
          v18,
          (__int64)&v26);
      }
    }
    v21 = IsDebuggerPresent();
    v14 = CoDisconnectContext(v21 ? -1 : 10000);
    v1 = v14;
    if ( v14 >= 0 )
    {
      v1 = 0;
      goto LABEL_25;
    }
    v15 = 387;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v14,
      v23);
LABEL_25:
    SetEvent(*v25);
    return v1;
  }
  v1 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x168,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
    (const char *)0x80070057LL,
    v23);
  return v1;
}

```

## disassembly

```asm
0x18000bf30  mov     [rsp-8+arg_10], rbx
0x18000bf35  mov     [rsp-8+arg_18], rsi
0x18000bf3a  push    rbp
0x18000bf3b  mov     rbp, rsp
0x18000bf3e  sub     rsp, 40h
0x18000bf42  test    rcx, rcx
0x18000bf45  jnz     short loc_18000BF69
0x18000bf47  mov     rcx, [rbp+8]; this
0x18000bf4b  mov     ebx, 80070057h
0x18000bf50  mov     r9d, ebx; char *
0x18000bf53  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf5a  mov     edx, 168h; void *
0x18000bf5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf64  jmp     loc_18000C113
0x18000bf69  mov     rcx, [rcx+8]
0x18000bf6d  mov     [rbp+arg_0], rcx
0x18000bf71  lea     rax, [rbp+arg_0]
0x18000bf75  mov     [rbp+var_10], rax
0x18000bf79  mov     [rbp+var_8], 1
0x18000bf7d  mov     rax, [rcx+10h]
0x18000bf81  mov     rsi, 400000000000h
0x18000bf8b  cmp     qword ptr [rax], 0
0x18000bf8f  jz      short loc_18000BFF7
0x18000bf91  mov     rbx, [rcx+18h]
0x18000bf95  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000bf9a  mov     r8, rax
0x18000bf9d  mov     ecx, [rax]
0x18000bf9f  cmp     ecx, 5
0x18000bfa2  jbe     short loc_18000BFDC
0x18000bfa4  mov     rax, [rax+18h]
0x18000bfa8  mov     rcx, [r8+10h]
0x18000bfac  test    rsi, rcx
0x18000bfaf  jz      short loc_18000BFDC
0x18000bfb1  mov     rcx, rax
0x18000bfb4  and     rcx, rsi
0x18000bfb7  cmp     rcx, rax
0x18000bfba  jnz     short loc_18000BFDC
0x18000bfbc  lea     rax, [rbx+8]
0x18000bfc0  mov     [rbp+arg_8], rax
0x18000bfc4  lea     rax, [rbp+arg_8]
0x18000bfc8  mov     qword ptr [rsp+40h+var_20], rax
0x18000bfcd  lea     rdx, word_1800149F2
0x18000bfd4  mov     rcx, r8
0x18000bfd7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000bfdc  mov     rax, [rbp+arg_0]
0x18000bfe0  mov     rcx, [rax+10h]
0x18000bfe4  mov     rcx, [rcx]
0x18000bfe7  mov     rax, [rcx]
0x18000bfea  mov     rax, [rax+20h]
0x18000bfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff3  mov     rcx, [rbp+arg_0]
0x18000bff7  mov     rax, [rcx+8]
0x18000bffb  cmp     dword ptr [rax], 0
0x18000bffe  jz      short loc_18000C07D
0x18000c000  mov     rbx, [rcx+18h]
0x18000c004  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000c009  mov     r8, rax
0x18000c00c  mov     ecx, [rax]
0x18000c00e  cmp     ecx, 5
0x18000c011  jbe     short loc_18000C04B
0x18000c013  mov     rax, [rax+18h]
0x18000c017  mov     rcx, [r8+10h]
0x18000c01b  test    rsi, rcx
0x18000c01e  jz      short loc_18000C04B
0x18000c020  mov     rcx, rax
0x18000c023  and     rcx, rsi
0x18000c026  cmp     rcx, rax
0x18000c029  jnz     short loc_18000C04B
0x18000c02b  lea     rax, [rbx+8]
0x18000c02f  mov     [rbp+arg_8], rax
0x18000c033  lea     rax, [rbp+arg_8]
0x18000c037  mov     qword ptr [rsp+40h+var_20], rax
0x18000c03c  lea     rdx, word_1800149C2
0x18000c043  mov     rcx, r8
0x18000c046  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000c04b  mov     rax, [rbp+arg_0]
0x18000c04f  mov     rcx, [rax+8]
0x18000c053  mov     ecx, [rcx]; dwRegister
0x18000c055  call    cs:__imp_CoRevokeClassObject
0x18000c05b  mov     ebx, eax
0x18000c05d  test    eax, eax
0x18000c05f  jns     short loc_18000C06B
0x18000c061  mov     edx, 17Ch
0x18000c066  jmp     loc_18000C0EF
0x18000c06b  mov     rax, [rbp+arg_0]
0x18000c06f  mov     rcx, [rax+8]
0x18000c073  mov     dword ptr [rcx], 0
0x18000c079  mov     rcx, [rbp+arg_0]
0x18000c07d  mov     rbx, [rcx+18h]
0x18000c081  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000c086  mov     r8, rax
0x18000c089  mov     ecx, [rax]
0x18000c08b  cmp     ecx, 5
0x18000c08e  jbe     short loc_18000C0C8
0x18000c090  mov     rax, [rax+18h]
0x18000c094  mov     rcx, [r8+10h]
0x18000c098  test    rsi, rcx
0x18000c09b  jz      short loc_18000C0C8
0x18000c09d  mov     rcx, rax
0x18000c0a0  and     rcx, rsi
0x18000c0a3  cmp     rcx, rax
0x18000c0a6  jnz     short loc_18000C0C8
0x18000c0a8  lea     rax, [rbx+8]
0x18000c0ac  mov     [rbp+arg_8], rax
0x18000c0b0  lea     rax, [rbp+arg_8]
0x18000c0b4  mov     qword ptr [rsp+40h+var_20], rax; int
0x18000c0b9  lea     rdx, byte_180014991
0x18000c0c0  mov     rcx, r8
0x18000c0c3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000c0c8  call    cs:__imp_IsDebuggerPresent
0x18000c0ce  neg     eax
0x18000c0d0  sbb     ecx, ecx
0x18000c0d2  and     ecx, 0FFFFD8EFh
0x18000c0d8  add     ecx, 2710h; dwTimeout
0x18000c0de  call    cs:__imp_CoDisconnectContext
0x18000c0e4  mov     ebx, eax
0x18000c0e6  test    eax, eax
0x18000c0e8  jns     short loc_18000C104
0x18000c0ea  mov     edx, 183h; void *
0x18000c0ef  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c0f6  mov     r9d, eax; char *
0x18000c0f9  mov     rcx, [rbp+8]; this
0x18000c0fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c102  jmp     short loc_18000C106
0x18000c104  xor     ebx, ebx
0x18000c106  mov     rcx, [rbp+arg_0]
0x18000c10a  mov     rcx, [rcx]; hEvent
0x18000c10d  call    cs:__imp_SetEvent
0x18000c113  mov     eax, ebx
0x18000c115  mov     rbx, [rsp+40h+arg_10]
0x18000c11a  mov     rsi, [rsp+40h+arg_18]
0x18000c11f  add     rsp, 40h
0x18000c123  pop     rbp
0x18000c124  retn
```
