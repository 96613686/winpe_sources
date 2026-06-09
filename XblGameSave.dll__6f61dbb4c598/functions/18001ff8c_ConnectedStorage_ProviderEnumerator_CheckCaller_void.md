# ConnectedStorage::ProviderEnumerator::CheckCaller(void)

- ea: `0x18001ff8c`
- end: `0x18002007e`
- name: `?CheckCaller@ProviderEnumerator@ConnectedStorage@@AEAAXXZ`
- size: `242`
- prototype: `void __fastcall(ConnectedStorage::ProviderEnumerator *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800200d0`
- `0x180020340`
- `0x1800205a0`
- `0x180020630`

## callees

- `0x18000aae4`
- `0x18001265c`
- `0x18001ff8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ffd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ffd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ffc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ffc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002005c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002005c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ff95`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ff95`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180020051`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180020051`
- `ntdll!RtlCapabilityCheck` at `0x180020010`
- `ntdll!RtlCapabilityCheck` at `0x180020010`
- `ntdll!RtlInitUnicodeString` at `0x18001fff6`
- `ntdll!RtlInitUnicodeString` at `0x18001fff6`

## string_xrefs

- `0x18001ff9f`: `CoImpersonateClient()`
- `0x18002006f`: `OpenThreadToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectedStorage::ProviderEnumerator::CheckCaller(ConnectedStorage::ProviderEnumerator *this)
{
  HRESULT v1; // eax
  const unsigned __int16 *v2; // r8
  HANDLE CurrentThread; // rax
  int v4; // eax
  const unsigned __int16 *v5; // r8
  signed int LastError; // eax
  const unsigned __int16 *v7; // r8
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  ConnectedStorage::ProviderEnumerator *v9; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  v9 = this;
  v1 = CoImpersonateClient();
  if ( v1 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v1, (int)L"CoImpersonateClient()", v2);
  TokenHandle = (void *)-1LL;
  ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"OpenThreadToken failed",
      v7);
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"shellExperience");
  LOBYTE(v9) = 0;
  v4 = RtlCapabilityCheck(TokenHandle, &DestinationString, &v9);
  if ( v4 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(v4 | 0x10000000u), (int)L"RtlCapabilityCheck failed", v5);
  if ( !(_BYTE)v9 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x80070005LL,
      (int)L"caller missing shellExperience capability",
      v5);
  ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
  CoRevertToSelf();
}

```

## disassembly

```asm
0x18001ff8c  mov     [rsp+arg_0], rcx
0x18001ff91  sub     rsp, 48h
0x18001ff95  call    cs:__imp_CoImpersonateClient
0x18001ff9b  test    eax, eax
0x18001ff9d  jns     short loc_18001FFAE
0x18001ff9f  lea     rdx, aCoimpersonatec; "CoImpersonateClient()"
0x18001ffa6  mov     ecx, eax; this
0x18001ffa8  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001ffae  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001ffb7  lea     rcx, [rsp+48h+TokenHandle]; this
0x18001ffbc  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x18001ffc1  call    cs:__imp_GetCurrentThread
0x18001ffc7  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18001ffcc  mov     edx, 8; DesiredAccess
0x18001ffd1  lea     r8d, [rdx-7]; OpenAsSelf
0x18001ffd5  mov     rcx, rax; ThreadHandle
0x18001ffd8  call    cs:__imp_OpenThreadToken
0x18001ffde  test    eax, eax
0x18001ffe0  jz      short loc_18002005C
0x18001ffe2  xorps   xmm0, xmm0
0x18001ffe5  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18001ffea  lea     rdx, SourceString; "shellExperience"
0x18001fff1  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18001fff6  call    cs:__imp_RtlInitUnicodeString
0x18001fffc  mov     byte ptr [rsp+48h+arg_0], 0
0x180020001  lea     r8, [rsp+48h+arg_0]
0x180020006  lea     rdx, [rsp+48h+DestinationString]
0x18002000b  mov     rcx, [rsp+48h+TokenHandle]
0x180020010  call    cs:__imp_RtlCapabilityCheck
0x180020016  test    eax, eax
0x180020018  jz      short loc_18002002D
0x18002001a  bts     eax, 1Ch
0x18002001e  lea     rdx, aRtlcapabilityc; "RtlCapabilityCheck failed"
0x180020025  mov     ecx, eax; this
0x180020027  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002002d  cmp     byte ptr [rsp+48h+arg_0], 0
0x180020032  jnz     short loc_180020046
0x180020034  lea     rdx, aCallerMissingS; "caller missing shellExperience capabili"...
0x18002003b  mov     ecx, 80070005h; this
0x180020040  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180020046  lea     rcx, [rsp+48h+TokenHandle]; this
0x18002004b  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x180020050  nop
0x180020051  call    cs:__imp_CoRevertToSelf
0x180020057  add     rsp, 48h
0x18002005b  retn
0x18002005c  call    cs:__imp_GetLastError
0x180020062  nop
0x180020063  test    eax, eax
0x180020065  jle     short loc_18002006F
0x180020067  movzx   eax, ax
0x18002006a  or      eax, 80070000h
0x18002006f  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed"
0x180020076  mov     ecx, eax; this
0x180020078  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
