# RoutePolicyProxy::QueryRoutingRulesForInterface

- ea: `0x140008878`
- end: `0x140008950`
- name: `RoutePolicyProxy::QueryRoutingRulesForInterface`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400081ec`

## callees

- `0x140001008`
- `0x140002618`
- `0x140008878`
- `0x14000935c`

## string_xrefs

- `0x1400088db`: `RoutePolicyCache::QueryRoutingRulesForInterface failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyProxy::QueryRoutingRulesForInterface(
        RoutePolicyCache *a1,
        struct WcmRoutePolicy::RoutingRulesForInterface *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int RoutingRulesForInterface; // ebx
  const char *v7; // rcx
  char *v8; // rdx
  __int64 v9; // rcx
  unsigned int v11; // [rsp+40h] [rbp+10h] BYREF
  const char *v12; // [rsp+58h] [rbp+28h] BYREF

  if ( a1 && (_DWORD)a2 )
  {
    if ( (unsigned int)a2 >= 0xC )
    {
      RoutingRulesForInterface = RoutePolicyCache::QueryRoutingRulesForInterface(a1, a2, a3, a4);
      if ( (RoutingRulesForInterface & 0xC0000000) == 0xC0000000 )
      {
        v9 = (unsigned int)dword_140012050;
        if ( (unsigned int)dword_140012050 > 2 )
        {
          v12 = "RoutePolicyCache::QueryRoutingRulesForInterface failed";
          v8 = byte_140010843;
LABEL_12:
          v11 = RoutingRulesForInterface;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v9,
            (unsigned __int8 *)v8,
            v4,
            v5,
            (int **)&v12,
            (__int64)&v11);
        }
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      RoutingRulesForInterface = -1073741789;
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v7 = "out buffer smaller than minimum";
        v8 = (char *)&unk_1400107C8;
LABEL_11:
        v12 = v7;
        v9 = (__int64)&v12;
        goto LABEL_12;
      }
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    RoutingRulesForInterface = -1073741811;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v7 = "Invalid out buffer";
      v8 = &byte_140010937;
      goto LABEL_11;
    }
  }
  return RoutingRulesForInterface;
}

```

## disassembly

```asm
0x140008878  mov     [rsp-8+arg_8], rbx
0x14000887d  push    rbp
0x14000887e  mov     rbp, rsp
0x140008881  sub     rsp, 30h
0x140008885  test    rcx, rcx
0x140008888  jz      short loc_140008901
0x14000888a  test    edx, edx
0x14000888c  jz      short loc_140008901
0x14000888e  cmp     edx, 0Ch
0x140008891  jnb     short loc_1400088BC
0x140008893  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008898  mov     eax, cs:dword_140012050
0x14000889e  mov     ebx, 0C0000023h
0x1400088a3  cmp     eax, 2
0x1400088a6  jbe     loc_140008942
0x1400088ac  lea     rcx, aOutBufferSmall; "out buffer smaller than minimum"
0x1400088b3  lea     rdx, unk_1400107C8; struct WcmRoutePolicy::RoutingRulesForInterface *
0x1400088ba  jmp     short loc_140008924
0x1400088bc  call    ?QueryRoutingRulesForInterface@RoutePolicyCache@@YAJQEAURoutingRulesForInterface@WcmRoutePolicy@@KPEAK@Z; RoutePolicyCache::QueryRoutingRulesForInterface(WcmRoutePolicy::RoutingRulesForInterface * const,ulong,ulong *)
0x1400088c1  mov     ecx, eax
0x1400088c3  mov     ebx, eax
0x1400088c5  mov     eax, 0C0000000h
0x1400088ca  and     ecx, eax
0x1400088cc  cmp     ecx, eax
0x1400088ce  jnz     short loc_140008942
0x1400088d0  mov     ecx, cs:dword_140012050
0x1400088d6  cmp     ecx, 2
0x1400088d9  jbe     short loc_140008942
0x1400088db  lea     rax, aRoutepolicycac_0; "RoutePolicyCache::QueryRoutingRulesForI"...
0x1400088e2  mov     [rbp+arg_18], rax
0x1400088e6  lea     rdx, byte_140010843
0x1400088ed  lea     rax, [rbp+arg_0]
0x1400088f1  mov     [rsp+30h+var_8], rax
0x1400088f6  lea     rax, [rbp+arg_18]
0x1400088fa  mov     [rsp+30h+var_10], rax
0x1400088ff  jmp     short loc_14000893A
0x140008901  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008906  mov     eax, cs:dword_140012050
0x14000890c  mov     ebx, 0C000000Dh
0x140008911  cmp     eax, 2
0x140008914  jbe     short loc_140008942
0x140008916  lea     rcx, aInvalidOutBuff; "Invalid out buffer"
0x14000891d  lea     rdx, byte_140010937
0x140008924  mov     [rbp+arg_18], rcx
0x140008928  lea     rcx, [rbp+arg_0]
0x14000892c  mov     [rsp+30h+var_8], rcx
0x140008931  lea     rcx, [rbp+arg_18]
0x140008935  mov     [rsp+30h+var_10], rcx
0x14000893a  mov     [rbp+arg_0], ebx
0x14000893d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140008942  mov     eax, ebx
0x140008944  mov     rbx, [rsp+30h+arg_8]
0x140008949  add     rsp, 30h
0x14000894d  pop     rbp
0x14000894e  retn
```
