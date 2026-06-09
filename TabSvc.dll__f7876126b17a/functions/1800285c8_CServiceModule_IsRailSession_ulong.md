# CServiceModule::_IsRailSession(ulong)

- ea: `0x1800285c8`
- end: `0x18002866e`
- name: `?_IsRailSession@CServiceModule@@AEAA_NK@Z`
- size: `166`
- prototype: `bool __fastcall(CServiceModule *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f0fc`
- `0x18001506c`
- `0x1800244ec`
- `0x1800245fc`
- `0x180024730`

## callees

- `0x180001ec0`
- `0x180015630`
- `0x18001cc70`
- `0x1800285c8`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002860e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002860e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180028652`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180028652`

## pseudocode

```c
bool __fastcall CServiceModule::_IsRailSession(CServiceModule *this, unsigned int a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  bool result; // al
  CServiceModule *v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = this;
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v8 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v3,
      (int)&byte_18003A15F,
      v4,
      v5,
      (__int64)&v8);
  }
  result = WTSGetActiveConsoleSessionId() != a2
        && (unsigned __int8)IsWinStationQueryInformationWPresent()
        && (v8 = 0, LODWORD(v7) = 0, (unsigned __int8)WinStationQueryInformationW(0, a2, 39, &v8, 4, &v7))
        && v8 == 5;
  return result;
}

```

## disassembly

```asm
0x1800285c8  mov     [rsp+arg_0], rcx
0x1800285cd  push    rbx
0x1800285ce  sub     rsp, 30h
0x1800285d2  mov     eax, cs:dword_1800411A8
0x1800285d8  mov     ebx, edx
0x1800285da  cmp     eax, 5
0x1800285dd  jbe     short loc_18002860E
0x1800285df  mov     edx, 4000000h
0x1800285e4  lea     rcx, dword_1800411A8
0x1800285eb  call    _tlgKeywordOn
0x1800285f0  test    al, al
0x1800285f2  jz      short loc_18002860E
0x1800285f4  lea     rax, [rsp+38h+arg_8]
0x1800285f9  mov     [rsp+38h+arg_8], ebx
0x1800285fd  lea     rdx, byte_18003A15F
0x180028604  mov     [rsp+38h+var_18], rax
0x180028609  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002860e  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180028614  cmp     eax, ebx
0x180028616  jz      short loc_180028666
0x180028618  call    IsWinStationQueryInformationWPresent
0x18002861d  test    al, al
0x18002861f  jz      short loc_180028666
0x180028621  lea     rax, [rsp+38h+arg_0]
0x180028626  mov     [rsp+38h+arg_8], 0
0x18002862e  mov     [rsp+38h+var_10], rax
0x180028633  lea     r9, [rsp+38h+arg_8]
0x180028638  mov     r8d, 27h ; '''
0x18002863e  mov     dword ptr [rsp+38h+var_18], 4
0x180028646  mov     edx, ebx
0x180028648  mov     dword ptr [rsp+38h+arg_0], 0
0x180028650  xor     ecx, ecx
0x180028652  call    cs:__imp_WinStationQueryInformationW
0x180028658  test    al, al
0x18002865a  jz      short loc_180028666
0x18002865c  cmp     [rsp+38h+arg_8], 5
0x180028661  setz    al
0x180028664  jmp     short loc_180028668
0x180028666  xor     al, al
0x180028668  add     rsp, 30h
0x18002866c  pop     rbx
0x18002866d  retn
```
