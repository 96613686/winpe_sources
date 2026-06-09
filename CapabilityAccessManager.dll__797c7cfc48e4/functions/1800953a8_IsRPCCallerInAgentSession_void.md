# IsRPCCallerInAgentSession(void)

- ea: `0x1800953a8`
- end: `0x180095468`
- name: `?IsRPCCallerInAgentSession@@YA_NXZ`
- size: `192`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x180093de0`
- `0x180095470`

## callees

- `0x18002392c`
- `0x180039e9c`
- `0x180042d60`
- `0x180043a40`
- `0x1800953a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800953c9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800953c9`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180095406`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180095406`

## pseudocode

```c
bool __fastcall IsRPCCallerInAgentSession(Windows::Internal::CapabilityAccess::Private *a1)
{
  Windows::Internal::CapabilityAccess::Private *v1; // rcx
  DWORD RpcClientProcessId; // eax
  const char *v3; // r9
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD pSessionId; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF

  if ( !Windows::Internal::CapabilityAccess::Private::IsAsyncSessionSupportEnabled(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityconsentmanagerserver.cpp",
      (const char *)0x8000FFFFLL,
      v6);
  pSessionId = 0;
  RpcClientProcessId = Windows::Internal::CapabilityAccess::Private::GetRpcClientProcessId(v1);
  if ( !ProcessIdToSessionId(RpcClientProcessId, &pSessionId) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityconsentmanagerserver.cpp",
      v3);
  v9 = 0;
  v10 = 0;
  if ( !(unsigned __int8)WinStationQueryInformationW(0, pSessionId, 39, &v9, 4, &v10) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityconsentmanagerserver.cpp",
      v4);
  return v9 == 9;
}

```

## disassembly

```asm
0x1800953a8  sub     rsp, 38h
0x1800953ac  call    ?IsAsyncSessionSupportEnabled@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsAsyncSessionSupportEnabled(void)
0x1800953b1  test    al, al
0x1800953b3  jz      short loc_18009541D
0x1800953b5  mov     [rsp+38h+pSessionId], 0
0x1800953bd  call    ?GetRpcClientProcessId@Private@CapabilityAccess@Internal@Windows@@YAKXZ; Windows::Internal::CapabilityAccess::Private::GetRpcClientProcessId(void)
0x1800953c2  mov     ecx, eax; dwProcessId
0x1800953c4  lea     rdx, [rsp+38h+pSessionId]; pSessionId
0x1800953c9  call    cs:__imp_ProcessIdToSessionId
0x1800953cf  test    eax, eax
0x1800953d1  jz      short loc_18009543A
0x1800953d3  mov     edx, [rsp+38h+pSessionId]
0x1800953d7  lea     rax, [rsp+38h+arg_10]
0x1800953dc  mov     [rsp+38h+var_10], rax
0x1800953e1  lea     r9, [rsp+38h+arg_8]
0x1800953e6  mov     r8d, 27h ; '''
0x1800953ec  mov     [rsp+38h+var_18], 4
0x1800953f4  xor     ecx, ecx
0x1800953f6  mov     [rsp+38h+arg_8], 0
0x1800953fe  mov     [rsp+38h+arg_10], 0
0x180095406  call    cs:__imp_WinStationQueryInformationW
0x18009540c  test    al, al
0x18009540e  jz      short loc_180095451
0x180095410  cmp     [rsp+38h+arg_8], 9
0x180095415  setz    al
0x180095418  add     rsp, 38h
0x18009541c  retn
0x18009541d  mov     rcx, [rsp+38h]; this
0x180095422  lea     r8, aOnecoreBaseDev_49; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180095429  mov     r9d, 8000FFFFh; char *
0x18009542f  mov     edx, 36h ; '6'; void *
0x180095434  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009543a  mov     rcx, [rsp+38h]; this
0x18009543f  lea     r8, aOnecoreBaseDev_49; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180095446  mov     edx, 39h ; '9'; void *
0x18009544b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180095451  mov     rcx, [rsp+38h]; this
0x180095456  lea     r8, aOnecoreBaseDev_49; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18009545d  mov     edx, 46h ; 'F'; void *
0x180095462  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
