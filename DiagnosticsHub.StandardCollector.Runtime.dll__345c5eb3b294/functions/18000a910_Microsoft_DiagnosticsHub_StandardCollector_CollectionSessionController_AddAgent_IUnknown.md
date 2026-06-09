# Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::AddAgent(IUnknown *)

- ea: `0x18000a910`
- end: `0x18000aa11`
- name: `?AddAgent@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUIUnknown@@@Z`
- size: `257`
- prototype: `HRESULT __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d5d0`

## callees

- `0x18000a910`
- `0x18000dd60`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad58`

## import_xrefs

- `ole32!CoCreateGuid` at `0x18000a950`
- `ole32!CoCreateGuid` at `0x18000a950`
- `ole32!StringFromGUID2` at `0x18000a97f`
- `ole32!StringFromGUID2` at `0x18000a97f`

## string_xrefs

- `0x18000a995`: `Agent is loading an additional agent. Assigning ID: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::AddAgent(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this,
        struct IUnknown *a2)
{
  HRESULT result; // eax
  int pExceptionObject; // [rsp+20h] [rbp-118h] BYREF
  GUID pguid; // [rsp+28h] [rbp-110h] BYREF
  OLECHAR sz[112]; // [rsp+40h] [rbp-F8h] BYREF

  if ( !a2 )
    return -2147467261;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
    {
      if ( !StringFromGUID2(&pguid, sz, 39) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      sz[39] = 0;
      sz[78] = 0;
      DiagHubCommon::LogStream::Write(
        _logger,
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessionController.cpp",
        L"Agent is loading an additional agent. Assigning ID: %s",
        sz);
    }
    result = Microsoft::DiagnosticsHub::StandardCollector::AgentController::AddAgentInstance(
               (Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *)((char *)this + 24),
               a2,
               &pguid,
               0);
    if ( result >= 0 )
      return 0;
  }
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x18000a910  mov     [rsp+arg_10], rbx
0x18000a915  mov     [rsp+arg_18], rsi
0x18000a91a  push    rdi
0x18000a91b  sub     rsp, 130h
0x18000a922  mov     rax, cs:__security_cookie
0x18000a929  xor     rax, rsp
0x18000a92c  mov     [rsp+138h+var_18], rax
0x18000a934  xor     esi, esi
0x18000a936  mov     rbx, rdx
0x18000a939  mov     rdi, rcx
0x18000a93c  test    rdx, rdx
0x18000a93f  jnz     short loc_18000A94B
0x18000a941  mov     eax, 80004003h
0x18000a946  jmp     loc_18000A9D2
0x18000a94b  lea     rcx, [rsp+138h+pguid]; pguid
0x18000a950  call    cs:__imp_CoCreateGuid
0x18000a956  test    eax, eax
0x18000a958  jns     short loc_18000A95F
0x18000a95a  lfence
0x18000a95d  jmp     short loc_18000A9D2
0x18000a95f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000a966  mov     rax, [rcx+8]
0x18000a96a  cmp     [rcx], rax
0x18000a96d  jz      short loc_18000A9B8
0x18000a96f  mov     r8d, 27h ; '''; cchMax
0x18000a975  lea     rdx, [rsp+138h+sz]; lpsz
0x18000a97a  lea     rcx, [rsp+138h+pguid]; rguid
0x18000a97f  call    cs:__imp_StringFromGUID2
0x18000a985  test    eax, eax
0x18000a987  jz      short loc_18000A9F7
0x18000a989  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18000a990  lea     r9, [rsp+138h+sz]
0x18000a995  lea     r8, aAgentIsLoading; "Agent is loading an additional agent. A"...
0x18000a99c  mov     [rsp+138h+var_AA], si
0x18000a9a4  lea     rdx, aDAWork1SSource_3; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000a9ab  mov     [rsp+138h+var_5C], si
0x18000a9b3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000a9b8  lea     rcx, [rdi+18h]; this
0x18000a9bc  xor     r9d, r9d; unsigned __int16 *
0x18000a9bf  lea     r8, [rsp+138h+pguid]; struct _GUID *
0x18000a9c4  mov     rdx, rbx; struct IUnknown *
0x18000a9c7  call    ?AddAgentInstance@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::AgentController::AddAgentInstance(IUnknown *,_GUID const &,ushort const *)
0x18000a9cc  test    eax, eax
0x18000a9ce  js      short loc_18000A95A
0x18000a9d0  xor     eax, eax
0x18000a9d2  mov     rcx, [rsp+138h+var_18]
0x18000a9da  xor     rcx, rsp; StackCookie
0x18000a9dd  call    __security_check_cookie
0x18000a9e2  lea     r11, [rsp+138h+var_8]
0x18000a9ea  mov     rbx, [r11+20h]
0x18000a9ee  mov     rsi, [r11+28h]
0x18000a9f2  mov     rsp, r11
0x18000a9f5  pop     rdi
0x18000a9f6  retn
0x18000a9f7  lea     rdx, _TI1J; pThrowInfo
0x18000a9fe  mov     [rsp+138h+pExceptionObject], 8007000Eh
0x18000aa06  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18000aa0b  call    _CxxThrowException_0
```
