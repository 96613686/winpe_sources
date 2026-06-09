# RoutePolicyProxy::SetRoutingRulesForInterface

- ea: `0x1400089c8`
- end: `0x140008abb`
- name: `RoutePolicyProxy::SetRoutingRulesForInterface`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400081ec`

## callees

- `0x140001008`
- `0x140002abc`
- `0x1400089c8`
- `0x14000935c`

## string_xrefs

- `0x140008a40`: `RoutePolicyCache::UpdateRoutingRulesForInterface failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyProxy::SetRoutingRulesForInterface(RoutePolicyCache *a1, size_t a2)
{
  unsigned int v2; // r11d
  unsigned int v3; // r8d
  int v4; // r10d
  _DWORD *v5; // r9
  __int64 v6; // rax
  unsigned int v7; // r8d
  int updated; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v14; // [rsp+40h] [rbp+8h] BYREF
  const char *v15; // [rsp+50h] [rbp+18h] BYREF

  if ( !a1 || (unsigned int)a2 < 0xC )
    goto LABEL_12;
  v2 = *((_DWORD *)a1 + 2);
  v3 = a2 - 12;
  v4 = 0;
  v5 = (_DWORD *)((char *)a1 + 12);
  if ( v2 )
  {
    while ( v3 >= 0x1D8 )
    {
      v6 = (unsigned int)v5[117];
      v7 = v3 - 472;
      if ( v7 < (unsigned int)v6 )
        break;
      v3 = v7 - v6;
      v5 = (_DWORD *)((char *)v5 + v6 + 472);
      if ( ++v4 >= v2 )
        goto LABEL_7;
    }
LABEL_12:
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    updated = -1073741811;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v15 = "Invalid input buffer";
      v12 = (unsigned __int8 *)&word_1400109E6;
      v11 = (__int64)&v15;
      goto LABEL_14;
    }
    return (unsigned int)updated;
  }
LABEL_7:
  if ( v3 )
    goto LABEL_12;
  updated = RoutePolicyCache::UpdateRoutingRulesForInterface(a1, a2, 0);
  if ( updated >= 0 )
    return 0;
  v11 = (unsigned int)dword_140012050;
  if ( (unsigned int)dword_140012050 > 2 )
  {
    v15 = "RoutePolicyCache::UpdateRoutingRulesForInterface failed";
    v12 = (unsigned __int8 *)byte_140010A25;
LABEL_14:
    v14 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      v12,
      v9,
      v10,
      (int **)&v15,
      (__int64)&v14);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400089c8  push    rbx
0x1400089ca  sub     rsp, 30h
0x1400089ce  test    rcx, rcx
0x1400089d1  jz      loc_140008A6D
0x1400089d7  cmp     edx, 0Ch
0x1400089da  jb      loc_140008A6D
0x1400089e0  mov     r11d, [rcx+8]
0x1400089e4  lea     r8d, [rdx-0Ch]
0x1400089e8  xor     r10d, r10d
0x1400089eb  lea     r9, [rcx+0Ch]
0x1400089ef  test    r11d, r11d
0x1400089f2  jz      short loc_140008A25
0x1400089f4  cmp     r8d, 1D8h
0x1400089fb  jb      short loc_140008A6D
0x1400089fd  mov     eax, [r9+1D4h]
0x140008a04  add     r8d, 0FFFFFE28h
0x140008a0b  cmp     r8d, eax
0x140008a0e  jb      short loc_140008A6D
0x140008a10  add     r9, 1D8h
0x140008a17  sub     r8d, eax; unsigned int
0x140008a1a  add     r9, rax
0x140008a1d  inc     r10d
0x140008a20  cmp     r10d, r11d
0x140008a23  jb      short loc_1400089F4
0x140008a25  test    r8d, r8d
0x140008a28  jnz     short loc_140008A6D
0x140008a2a  call    ?UpdateRoutingRulesForInterface@RoutePolicyCache@@YAJPEBURoutingRulesForInterface@WcmRoutePolicy@@K@Z; RoutePolicyCache::UpdateRoutingRulesForInterface(WcmRoutePolicy::RoutingRulesForInterface const *,ulong)
0x140008a2f  mov     ebx, eax
0x140008a31  test    eax, eax
0x140008a33  jns     short loc_140008A69
0x140008a35  mov     ecx, cs:dword_140012050
0x140008a3b  cmp     ecx, 2
0x140008a3e  jbe     short loc_140008AB2
0x140008a40  lea     rax, aRoutepolicycac_1; "RoutePolicyCache::UpdateRoutingRulesFor"...
0x140008a47  mov     [rsp+38h+arg_10], rax
0x140008a4c  lea     rdx, byte_140010A25
0x140008a53  lea     rax, [rsp+38h+arg_0]
0x140008a58  mov     [rsp+38h+var_10], rax
0x140008a5d  lea     rax, [rsp+38h+arg_10]
0x140008a62  mov     [rsp+38h+var_18], rax
0x140008a67  jmp     short loc_140008AA9
0x140008a69  xor     eax, eax
0x140008a6b  jmp     short loc_140008AB4
0x140008a6d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008a72  mov     eax, cs:dword_140012050
0x140008a78  mov     ebx, 0C000000Dh
0x140008a7d  cmp     eax, 2
0x140008a80  jbe     short loc_140008AB2
0x140008a82  lea     rcx, aInvalidInputBu; "Invalid input buffer"
0x140008a89  mov     [rsp+38h+arg_10], rcx
0x140008a8e  lea     rdx, word_1400109E6
0x140008a95  lea     rcx, [rsp+38h+arg_0]
0x140008a9a  mov     [rsp+38h+var_10], rcx
0x140008a9f  lea     rcx, [rsp+38h+arg_10]
0x140008aa4  mov     [rsp+38h+var_18], rcx
0x140008aa9  mov     [rsp+38h+arg_0], ebx
0x140008aad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140008ab2  mov     eax, ebx
0x140008ab4  add     rsp, 30h
0x140008ab8  pop     rbx
0x140008ab9  retn
```
