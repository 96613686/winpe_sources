# Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback(void *,_NL_NETWORK_CONNECTIVITY_HINT)

- ea: `0x18002f850`
- end: `0x18002f8f0`
- name: `?PnetworkConnectivityHintChangeCallback@BasicInventoryScheduler@Service@Inventory@Compat@Windows@@CAXPEAXU_NL_NETWORK_CONNECTIVITY_HINT@@@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800108d4`
- `0x1800152d0`
- `0x18002f850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f889`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f889`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f8b2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f8b2`

## string_xrefs

- `0x18002f8de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f8c7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f879`: `Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback`
- `0x18002f8a2`: `Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback`

## pseudocode

```c
BOOL __fastcall Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback(
        __int64 a1,
        __int64 a2)
{
  BOOL result; // eax
  const char *v4; // r9
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)a2 != 3 || *(_BYTE *)(a2 + 9) || *(_BYTE *)(a2 + 10) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback",
      66,
      "Received network disconnected notification.");
    result = ResetEvent(*(HANDLE *)(a1 + 48));
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback",
      61,
      "Received network connected notification.");
    result = SetEvent(*(HANDLE *)(a1 + 48));
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
  return result;
}

```

## disassembly

```asm
0x18002f850  push    rbx
0x18002f852  sub     rsp, 20h
0x18002f856  mov     rbx, rcx
0x18002f859  mov     ecx, 3
0x18002f85e  cmp     [rdx], ecx
0x18002f860  jnz     short loc_18002F895
0x18002f862  cmp     byte ptr [rdx+9], 0
0x18002f866  jnz     short loc_18002F895
0x18002f868  cmp     byte ptr [rdx+0Ah], 0
0x18002f86c  jnz     short loc_18002F895
0x18002f86e  lea     r9, aReceivedNetwor_0; "Received network connected notification"...
0x18002f875  lea     r8d, [rcx+3Ah]
0x18002f879  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Inventory::Service::Ba"...
0x18002f880  call    AslLogCallPrintf
0x18002f885  mov     rcx, [rbx+30h]; hEvent
0x18002f889  call    cs:__imp_SetEvent
0x18002f88f  test    eax, eax
0x18002f891  jz      short loc_18002F8D9
0x18002f893  jmp     short loc_18002F8BC
0x18002f895  lea     r9, aReceivedNetwor; "Received network disconnected notificat"...
0x18002f89c  mov     r8d, 42h ; 'B'
0x18002f8a2  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Inventory::Service::Ba"...
0x18002f8a9  call    AslLogCallPrintf
0x18002f8ae  mov     rcx, [rbx+30h]; hEvent
0x18002f8b2  call    cs:__imp_ResetEvent
0x18002f8b8  test    eax, eax
0x18002f8ba  jz      short loc_18002F8C2
0x18002f8bc  add     rsp, 20h
0x18002f8c0  pop     rbx
0x18002f8c1  retn
0x18002f8c2  mov     rcx, [rsp+28h]; this
0x18002f8c7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f8ce  mov     edx, 0A06h; void *
0x18002f8d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f8d9  mov     rcx, [rsp+28h]; this
0x18002f8de  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f8e5  mov     edx, 0A01h; void *
0x18002f8ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
