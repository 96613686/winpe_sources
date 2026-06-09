# RoutePolicyProxy::QueryConnectionCache

- ea: `0x140008798`
- end: `0x140008870`
- name: `RoutePolicyProxy::QueryConnectionCache`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400081ec`

## callees

- `0x140001008`
- `0x140005b60`
- `0x140008798`
- `0x14000935c`

## string_xrefs

- `0x1400087fb`: `RoutePolicyCallout::QueryConnectionCacheForInterface failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyProxy::QueryConnectionCache(
        RoutePolicyCallout *a1,
        struct RoutePolicyCallout::CONNECTION_CACHE_LIST *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int v4; // r8d
  int v5; // r9d
  unsigned int ConnectionCache; // ebx
  const char *v7; // rcx
  __int16 *v8; // rdx
  const char **v9; // rcx
  unsigned int v11; // [rsp+40h] [rbp+10h] BYREF
  const char *v12; // [rsp+58h] [rbp+28h] BYREF

  if ( a1 && (_DWORD)a2 )
  {
    if ( (unsigned int)a2 >= 8 )
    {
      ConnectionCache = RoutePolicyCallout::QueryConnectionCache(a1, a2, a3, a4);
      if ( (ConnectionCache & 0xC0000000) == 0xC0000000 )
      {
        LODWORD(v9) = dword_140012050;
        if ( (unsigned int)dword_140012050 > 2 )
        {
          v12 = "RoutePolicyCallout::QueryConnectionCacheForInterface failed";
          v8 = (__int16 *)&byte_1400106D7;
LABEL_12:
          v11 = ConnectionCache;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)v9,
            (_DWORD)v8,
            v4,
            v5,
            (__int64)&v12,
            (__int64)&v11);
        }
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      ConnectionCache = -1073741789;
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v7 = "out buffer smaller than minimum";
        v8 = (__int16 *)&unk_140010790;
LABEL_11:
        v12 = v7;
        v9 = &v12;
        goto LABEL_12;
      }
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    ConnectionCache = -1073741811;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v7 = "Invalid out buffer";
      v8 = word_1400109A2;
      goto LABEL_11;
    }
  }
  return ConnectionCache;
}

```

## disassembly

```asm
0x140008798  mov     [rsp-8+arg_8], rbx
0x14000879d  push    rbp
0x14000879e  mov     rbp, rsp
0x1400087a1  sub     rsp, 30h
0x1400087a5  test    rcx, rcx
0x1400087a8  jz      short loc_140008821
0x1400087aa  test    edx, edx
0x1400087ac  jz      short loc_140008821
0x1400087ae  cmp     edx, 8
0x1400087b1  jnb     short loc_1400087DC
0x1400087b3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400087b8  mov     eax, cs:dword_140012050
0x1400087be  mov     ebx, 0C0000023h
0x1400087c3  cmp     eax, 2
0x1400087c6  jbe     loc_140008862
0x1400087cc  lea     rcx, aOutBufferSmall; "out buffer smaller than minimum"
0x1400087d3  lea     rdx, unk_140010790; struct RoutePolicyCallout::CONNECTION_CACHE_LIST *
0x1400087da  jmp     short loc_140008844
0x1400087dc  call    ?QueryConnectionCache@RoutePolicyCallout@@YAJQEAUCONNECTION_CACHE_LIST@1@KPEAK@Z; RoutePolicyCallout::QueryConnectionCache(RoutePolicyCallout::CONNECTION_CACHE_LIST * const,ulong,ulong *)
0x1400087e1  mov     ecx, eax
0x1400087e3  mov     ebx, eax
0x1400087e5  mov     eax, 0C0000000h
0x1400087ea  and     ecx, eax
0x1400087ec  cmp     ecx, eax
0x1400087ee  jnz     short loc_140008862
0x1400087f0  mov     ecx, cs:dword_140012050
0x1400087f6  cmp     ecx, 2
0x1400087f9  jbe     short loc_140008862
0x1400087fb  lea     rax, aRoutepolicycal; "RoutePolicyCallout::QueryConnectionCach"...
0x140008802  mov     [rbp+arg_18], rax
0x140008806  lea     rdx, byte_1400106D7
0x14000880d  lea     rax, [rbp+arg_0]
0x140008811  mov     [rsp+30h+var_8], rax
0x140008816  lea     rax, [rbp+arg_18]
0x14000881a  mov     [rsp+30h+var_10], rax
0x14000881f  jmp     short loc_14000885A
0x140008821  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008826  mov     eax, cs:dword_140012050
0x14000882c  mov     ebx, 0C000000Dh
0x140008831  cmp     eax, 2
0x140008834  jbe     short loc_140008862
0x140008836  lea     rcx, aInvalidOutBuff; "Invalid out buffer"
0x14000883d  lea     rdx, word_1400109A2
0x140008844  mov     [rbp+arg_18], rcx
0x140008848  lea     rcx, [rbp+arg_0]
0x14000884c  mov     [rsp+30h+var_8], rcx
0x140008851  lea     rcx, [rbp+arg_18]
0x140008855  mov     [rsp+30h+var_10], rcx
0x14000885a  mov     [rbp+arg_0], ebx
0x14000885d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140008862  mov     eax, ebx
0x140008864  mov     rbx, [rsp+30h+arg_8]
0x140008869  add     rsp, 30h
0x14000886d  pop     rbp
0x14000886e  retn
```
