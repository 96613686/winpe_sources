# MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)

- ea: `0x180002f8c`
- end: `0x180003018`
- name: `??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800066d4`

## callees

- `0x180001008`
- `0x180002f8c`
- `0x180005820`

## pseudocode

```c
__int64 __fastcall MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v4; // r9d
  __int64 v5; // r8
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  const char *v8; // [rsp+68h] [rbp+20h] BYREF

  v6 = a1;
  result = (__int64)MSAClientTraceTelemetry::Provider();
  v5 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      LODWORD(v6) = *a2;
      v7 = 50331648;
      v8 = "WLIDCCleanupIdentity";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
               v5,
               (unsigned int)word_180011122,
               v5,
               v4,
               (__int64)&v8,
               (__int64)&v6,
               (__int64)&v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f8c  mov     [rsp+arg_0], rcx
0x180002f91  push    rbx
0x180002f92  sub     rsp, 40h
0x180002f96  mov     rbx, rdx
0x180002f99  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180002f9e  mov     r8, rax
0x180002fa1  mov     ecx, [rax]
0x180002fa3  cmp     ecx, 5
0x180002fa6  jbe     short loc_180003012
0x180002fa8  mov     rax, [rax+18h]
0x180002fac  mov     rdx, 400000000000h
0x180002fb6  mov     rcx, [r8+10h]
0x180002fba  test    rdx, rcx
0x180002fbd  jz      short loc_180003012
0x180002fbf  mov     rcx, rax
0x180002fc2  and     rcx, rdx
0x180002fc5  cmp     rcx, rax
0x180002fc8  jnz     short loc_180003012
0x180002fca  mov     eax, [rbx]
0x180002fcc  lea     rdx, word_180011122
0x180002fd3  mov     dword ptr [rsp+48h+arg_0], eax
0x180002fd7  mov     rcx, r8
0x180002fda  lea     rax, aWlidccleanupid; "WLIDCCleanupIdentity"
0x180002fe1  mov     [rsp+48h+arg_10], 3000000h
0x180002fea  mov     [rsp+48h+arg_18], rax
0x180002fef  lea     rax, [rsp+48h+arg_10]
0x180002ff4  mov     [rsp+48h+var_18], rax
0x180002ff9  lea     rax, [rsp+48h+arg_0]
0x180002ffe  mov     [rsp+48h+var_20], rax
0x180003003  lea     rax, [rsp+48h+arg_18]
0x180003008  mov     [rsp+48h+var_28], rax
0x18000300d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180003012  add     rsp, 40h
0x180003016  pop     rbx
0x180003017  retn
```
