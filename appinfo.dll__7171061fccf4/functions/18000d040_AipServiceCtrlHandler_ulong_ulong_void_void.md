# AipServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18000d040`
- end: `0x18000d0f0`
- name: `?AipServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `176`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, _DWORD *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x18000d040`
- `0x18000d0f8`
- `0x18000d17c`
- `0x18000d240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d0dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d0dd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d0cf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d0cf`

## pseudocode

```c
__int64 __fastcall AipServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, _DWORD *lpEventData, LPVOID lpContext)
{
  DWORD v6; // ecx
  unsigned int v7; // ecx

  v6 = dwControl - 1;
  if ( !v6 )
  {
    g_ssService.dwCurrentState = 4;
    *(_QWORD *)&g_ssService.dwCheckPoint = 0;
    SetServiceStatus(g_hssService, &g_ssService);
    if ( lpContext )
      SetEvent(lpContext);
    return 0;
  }
  if ( v6 != 13 )
    return 120;
  if ( dwEventType != 6 || !lpEventData )
    return 0;
  AiRemoveProfilesForSession(lpEventData[1]);
  v7 = lpEventData[1];
  if ( v7 )
  {
    if ( v7 <= g_dwSessions )
      AipCleanupSessionEntry(v7 - 1);
  }
  AiFreeSessionIdEntry(lpEventData[1]);
  return 0;
}

```

## disassembly

```asm
0x18000d040  mov     [rsp+arg_0], rbx
0x18000d045  push    rdi
0x18000d046  sub     rsp, 20h
0x18000d04a  mov     rdi, r9
0x18000d04d  mov     rbx, r8
0x18000d050  sub     ecx, 1
0x18000d053  jz      short loc_18000D0AC
0x18000d055  cmp     ecx, 0Dh
0x18000d058  jnz     short loc_18000D09C
0x18000d05a  cmp     edx, 6
0x18000d05d  jnz     loc_18000D0E3
0x18000d063  test    rbx, rbx
0x18000d066  jz      short loc_18000D0E3
0x18000d068  mov     ecx, [r8+4]; unsigned int
0x18000d06c  call    ?AiRemoveProfilesForSession@@YAXK@Z; AiRemoveProfilesForSession(ulong)
0x18000d071  mov     ecx, [rbx+4]
0x18000d074  test    ecx, ecx
0x18000d076  jz      short loc_18000D087
0x18000d078  cmp     ecx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000d07e  ja      short loc_18000D087
0x18000d080  dec     ecx; unsigned int
0x18000d082  call    ?AipCleanupSessionEntry@@YAXK@Z; AipCleanupSessionEntry(ulong)
0x18000d087  mov     ecx, [rbx+4]; unsigned int
0x18000d08a  call    ?AiFreeSessionIdEntry@@YAKK@Z; AiFreeSessionIdEntry(ulong)
0x18000d08f  xor     eax, eax
0x18000d091  mov     rbx, [rsp+28h+arg_0]
0x18000d096  add     rsp, 20h
0x18000d09a  pop     rdi
0x18000d09b  retn
0x18000d09c  mov     eax, 78h ; 'x'
0x18000d0a1  mov     rbx, [rsp+28h+arg_0]
0x18000d0a6  add     rsp, 20h
0x18000d0aa  pop     rdi
0x18000d0ab  retn
0x18000d0ac  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000d0b3  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000d0ba  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_ssService ...
0x18000d0c4  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x18000d0cf  call    cs:__imp_SetServiceStatus
0x18000d0d5  test    rdi, rdi
0x18000d0d8  jz      short loc_18000D0E3
0x18000d0da  mov     rcx, rdi; hEvent
0x18000d0dd  call    cs:__imp_SetEvent
0x18000d0e3  mov     rbx, [rsp+28h+arg_0]
0x18000d0e8  xor     eax, eax
0x18000d0ea  add     rsp, 20h
0x18000d0ee  pop     rdi
0x18000d0ef  retn
```
