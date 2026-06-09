# CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)

- ea: `0x1800144bc`
- end: `0x1800145a8`
- name: `?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z`
- size: `236`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e470`
- `0x1800146e4`
- `0x1800148f0`

## callees

- `0x180001258`
- `0x1800143b8`
- `0x1800144bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001458b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001458b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180014502`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180014502`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::GetTraceSessionStatus(LPCWSTR InstanceName, int *a2, int a3, int a4)
{
  PEVENT_TRACE_PROPERTIES v4; // rbx
  const WCHAR *v6; // rsi
  unsigned int v7; // edi
  int v8; // eax
  ULONG v9; // eax
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF
  const WCHAR *v13; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  Properties = 0;
  v6 = InstanceName;
  if ( InstanceName )
  {
    v8 = CEtwLogHelper::CreateSessionProperty(&Properties);
    v4 = Properties;
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = ControlTraceW(0, v6, Properties, 0);
      if ( v9 )
      {
        if ( v9 == 4201 )
          *a2 = 0;
        else
          v7 = -2147418113;
      }
      else
      {
        *a2 = 1;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v12 = *a2;
    LODWORD(Properties) = v7;
    if ( !v6 )
      v6 = &String2;
    v13 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)InstanceName,
      (unsigned int)&byte_1800421EF,
      a3,
      a4,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&Properties);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return v7;
}

```

## disassembly

```asm
0x1800144bc  mov     [rsp+arg_8], rbx
0x1800144c1  push    rsi
0x1800144c2  push    rdi
0x1800144c3  push    r14
0x1800144c5  sub     rsp, 40h
0x1800144c9  xor     ebx, ebx
0x1800144cb  mov     r14, rdx
0x1800144ce  mov     [rsp+58h+Properties], rbx
0x1800144d3  mov     rsi, rcx
0x1800144d6  test    rcx, rcx
0x1800144d9  jnz     short loc_1800144E2
0x1800144db  mov     edi, 80070057h
0x1800144e0  jmp     short loc_180014530
0x1800144e2  lea     rcx, [rsp+58h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800144e7  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x1800144ec  mov     rbx, [rsp+58h+Properties]
0x1800144f1  mov     edi, eax
0x1800144f3  test    eax, eax
0x1800144f5  js      short loc_180014530
0x1800144f7  xor     r9d, r9d; ControlCode
0x1800144fa  mov     r8, rbx; Properties
0x1800144fd  mov     rdx, rsi; InstanceName
0x180014500  xor     ecx, ecx; TraceHandle
0x180014502  call    cs:__imp_ControlTraceW
0x180014509  nop     dword ptr [rax+rax+00h]
0x18001450e  test    eax, eax
0x180014510  jnz     short loc_18001451B
0x180014512  mov     dword ptr [r14], 1
0x180014519  jmp     short loc_180014530
0x18001451b  cmp     eax, 1069h
0x180014520  jnz     short loc_18001452B
0x180014522  mov     dword ptr [r14], 0
0x180014529  jmp     short loc_180014530
0x18001452b  mov     edi, 8000FFFFh
0x180014530  mov     eax, cs:dword_18004AE90
0x180014536  cmp     eax, 5
0x180014539  jbe     short loc_180014583
0x18001453b  mov     eax, [r14]
0x18001453e  lea     rdx, byte_1800421EF
0x180014545  mov     [rsp+58h+arg_10], eax
0x180014549  test    rsi, rsi
0x18001454c  lea     rax, String2
0x180014553  mov     dword ptr [rsp+58h+Properties], edi
0x180014557  cmovz   rsi, rax
0x18001455b  lea     rax, [rsp+58h+Properties]
0x180014560  mov     [rsp+58h+var_28], rax
0x180014565  lea     rax, [rsp+58h+arg_10]
0x18001456a  mov     [rsp+58h+var_30], rax
0x18001456f  lea     rax, [rsp+58h+arg_18]
0x180014574  mov     [rsp+58h+var_38], rax
0x180014579  mov     [rsp+58h+arg_18], rsi
0x18001457e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014583  test    rbx, rbx
0x180014586  jz      short loc_180014597
0x180014588  mov     rcx, rbx; pv
0x18001458b  call    cs:__imp_CoTaskMemFree
0x180014592  nop     dword ptr [rax+rax+00h]
0x180014597  mov     rbx, [rsp+58h+arg_8]
0x18001459c  mov     eax, edi
0x18001459e  add     rsp, 40h
0x1800145a2  pop     r14
0x1800145a4  pop     rdi
0x1800145a5  pop     rsi
0x1800145a6  retn
```
