# AipServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18000d540`
- end: `0x18000d603`
- name: `?AipServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `195`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x18000d540`
- `0x18000d60c`
- `0x18000d700`
- `0x18000d7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d5e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d5e9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d5d5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d5d5`

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
0x18000d540  mov     [rsp+arg_0], rbx
0x18000d545  push    rdi
0x18000d546  sub     rsp, 20h
0x18000d54a  mov     rdi, r9
0x18000d54d  mov     rbx, r8
0x18000d550  sub     ecx, 1
0x18000d553  jz      short loc_18000D5B2
0x18000d555  cmp     ecx, 0Dh
0x18000d558  jnz     short loc_18000D5A1
0x18000d55a  cmp     edx, 6
0x18000d55d  jnz     loc_18000D5F5
0x18000d563  test    rbx, rbx
0x18000d566  jz      loc_18000D5F5
0x18000d56c  mov     ecx, [r8+4]; unsigned int
0x18000d570  call    ?AiRemoveProfilesForSession@@YAXK@Z; AiRemoveProfilesForSession(ulong)
0x18000d575  mov     ecx, [rbx+4]
0x18000d578  test    ecx, ecx
0x18000d57a  jz      short loc_18000D58B
0x18000d57c  cmp     ecx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000d582  ja      short loc_18000D58B
0x18000d584  dec     ecx; unsigned int
0x18000d586  call    ?AipCleanupSessionEntry@@YAXK@Z; AipCleanupSessionEntry(ulong)
0x18000d58b  mov     ecx, [rbx+4]; unsigned int
0x18000d58e  call    ?AiFreeSessionIdEntry@@YAKK@Z; AiFreeSessionIdEntry(ulong)
0x18000d593  xor     eax, eax
0x18000d595  mov     rbx, [rsp+28h+arg_0]
0x18000d59a  add     rsp, 20h
0x18000d59e  pop     rdi
0x18000d59f  retn
0x18000d5a1  mov     eax, 78h ; 'x'
0x18000d5a6  mov     rbx, [rsp+28h+arg_0]
0x18000d5ab  add     rsp, 20h
0x18000d5af  pop     rdi
0x18000d5b0  retn
0x18000d5b2  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000d5b9  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000d5c0  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_ssService ...
0x18000d5ca  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x18000d5d5  call    cs:__imp_SetServiceStatus
0x18000d5dc  nop     dword ptr [rax+rax+00h]
0x18000d5e1  test    rdi, rdi
0x18000d5e4  jz      short loc_18000D5F5
0x18000d5e6  mov     rcx, rdi; hEvent
0x18000d5e9  call    cs:__imp_SetEvent
0x18000d5f0  nop     dword ptr [rax+rax+00h]
0x18000d5f5  mov     rbx, [rsp+28h+arg_0]
0x18000d5fa  xor     eax, eax
0x18000d5fc  add     rsp, 20h
0x18000d600  pop     rdi
0x18000d601  retn
```
