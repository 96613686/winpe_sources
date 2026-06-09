# ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[8],long &>(ushort (&)[32],ushort const (&)[8],long &)

- ea: `0x18000d564`
- end: `0x18000d5f9`
- name: `??$ServiceBaseError@AEAY0CA@GAEAY07$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY07$$CBGAEAJ@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010444`

## callees

- `0x180001d58`
- `0x18000a648`
- `0x18000d564`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[8],long &>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 result; // rax
  __int64 v6; // r9
  _QWORD v7[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF
  const wchar_t *v9; // [rsp+78h] [rbp+20h] BYREF

  v8 = a2;
  result = (__int64)ServiceHostLogging::Provider();
  v6 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      LODWORD(v8) = *a3;
      v7[0] = a1;
      v9 = L"Started";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v6,
               (unsigned int)&byte_1800153FF,
               0,
               v6,
               (__int64)v7,
               (__int64)&v9,
               (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d564  mov     [rsp+arg_0], rbx
0x18000d569  mov     [rsp+arg_8], rdx
0x18000d56e  push    rdi
0x18000d56f  sub     rsp, 50h
0x18000d573  mov     rbx, r8
0x18000d576  mov     rdi, rcx
0x18000d579  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000d57e  mov     r9, rax
0x18000d581  mov     edx, [rax]
0x18000d583  cmp     edx, 5
0x18000d586  jbe     short loc_18000D5EE
0x18000d588  mov     rax, [rax+18h]
0x18000d58c  mov     r8, 400000000000h
0x18000d596  mov     rdx, [r9+10h]
0x18000d59a  test    r8, rdx
0x18000d59d  jz      short loc_18000D5EE
0x18000d59f  mov     rcx, rax
0x18000d5a2  and     rcx, r8
0x18000d5a5  cmp     rcx, rax
0x18000d5a8  jnz     short loc_18000D5EE
0x18000d5aa  mov     eax, [rbx]
0x18000d5ac  lea     rdx, byte_1800153FF
0x18000d5b3  mov     dword ptr [rsp+58h+arg_8], eax
0x18000d5b7  mov     rcx, r9
0x18000d5ba  lea     rax, aStarted; "Started"
0x18000d5c1  mov     [rsp+58h+var_18], rdi
0x18000d5c6  mov     [rsp+58h+arg_18], rax
0x18000d5cb  lea     rax, [rsp+58h+arg_8]
0x18000d5d0  mov     [rsp+58h+var_28], rax
0x18000d5d5  lea     rax, [rsp+58h+arg_18]
0x18000d5da  mov     [rsp+58h+var_30], rax
0x18000d5df  lea     rax, [rsp+58h+var_18]
0x18000d5e4  mov     [rsp+58h+var_38], rax
0x18000d5e9  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000d5ee  mov     rbx, [rsp+58h+arg_0]
0x18000d5f3  add     rsp, 50h
0x18000d5f7  pop     rdi
0x18000d5f8  retn
```
