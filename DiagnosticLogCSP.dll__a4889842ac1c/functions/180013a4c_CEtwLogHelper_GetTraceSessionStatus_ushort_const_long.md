# CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)

- ea: `0x180013a4c`
- end: `0x180013b2b`
- name: `?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dd98`
- `0x180013c54`
- `0x180013e4c`

## callees

- `0x180001250`
- `0x18001395c`
- `0x180013a4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b15`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180013a92`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180013a92`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::GetTraceSessionStatus(__int64 InstanceName, int *a2, __int64 a3, __int64 a4)
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
  v6 = (const WCHAR *)InstanceName;
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v12 = *a2;
    LODWORD(Properties) = v7;
    if ( !v6 )
      v6 = &String2;
    v13 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      InstanceName,
      (__int64)&byte_1800401EF,
      a3,
      a4,
      &v13,
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
0x180013a4c  mov     [rsp+arg_8], rbx
0x180013a51  push    rsi
0x180013a52  push    rdi
0x180013a53  push    r14
0x180013a55  sub     rsp, 40h
0x180013a59  xor     ebx, ebx
0x180013a5b  mov     r14, rdx
0x180013a5e  mov     [rsp+58h+Properties], rbx
0x180013a63  mov     rsi, rcx
0x180013a66  test    rcx, rcx
0x180013a69  jnz     short loc_180013A72
0x180013a6b  mov     edi, 80070057h
0x180013a70  jmp     short loc_180013ABA
0x180013a72  lea     rcx, [rsp+58h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180013a77  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180013a7c  mov     rbx, [rsp+58h+Properties]
0x180013a81  mov     edi, eax
0x180013a83  test    eax, eax
0x180013a85  js      short loc_180013ABA
0x180013a87  xor     r9d, r9d; ControlCode
0x180013a8a  mov     r8, rbx; Properties
0x180013a8d  mov     rdx, rsi; InstanceName
0x180013a90  xor     ecx, ecx; TraceHandle
0x180013a92  call    cs:__imp_ControlTraceW
0x180013a98  test    eax, eax
0x180013a9a  jnz     short loc_180013AA5
0x180013a9c  mov     dword ptr [r14], 1
0x180013aa3  jmp     short loc_180013ABA
0x180013aa5  cmp     eax, 1069h
0x180013aaa  jnz     short loc_180013AB5
0x180013aac  mov     dword ptr [r14], 0
0x180013ab3  jmp     short loc_180013ABA
0x180013ab5  mov     edi, 8000FFFFh
0x180013aba  mov     eax, cs:dword_180048E90
0x180013ac0  cmp     eax, 5
0x180013ac3  jbe     short loc_180013B0D
0x180013ac5  mov     eax, [r14]
0x180013ac8  lea     rdx, byte_1800401EF
0x180013acf  mov     [rsp+58h+arg_10], eax
0x180013ad3  test    rsi, rsi
0x180013ad6  lea     rax, String2
0x180013add  mov     dword ptr [rsp+58h+Properties], edi
0x180013ae1  cmovz   rsi, rax
0x180013ae5  lea     rax, [rsp+58h+Properties]
0x180013aea  mov     [rsp+58h+var_28], rax
0x180013aef  lea     rax, [rsp+58h+arg_10]
0x180013af4  mov     [rsp+58h+var_30], rax
0x180013af9  lea     rax, [rsp+58h+arg_18]
0x180013afe  mov     [rsp+58h+var_38], rax
0x180013b03  mov     [rsp+58h+arg_18], rsi
0x180013b08  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013b0d  test    rbx, rbx
0x180013b10  jz      short loc_180013B1B
0x180013b12  mov     rcx, rbx; pv
0x180013b15  call    cs:__imp_CoTaskMemFree
0x180013b1b  mov     rbx, [rsp+58h+arg_8]
0x180013b20  mov     eax, edi
0x180013b22  add     rsp, 40h
0x180013b26  pop     r14
0x180013b28  pop     rdi
0x180013b29  pop     rsi
0x180013b2a  retn
```
