# UpdateStatus(ulong)

- ea: `0x18003b5d8`
- end: `0x18003b670`
- name: `?UpdateStatus@@YAEK@Z`
- size: `152`
- prototype: `unsigned __int8 __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180035a44`
- `0x180038094`
- `0x18003a5fc`
- `0x18004b498`

## callees

- `0x1800101ec`
- `0x18003b5d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b640`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003b61d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003b61d`

## pseudocode

```c
unsigned __int8 __fastcall UpdateStatus(DWORD a1)
{
  DWORD LastError; // eax

  if ( !hService )
    return 0;
  SStatus.dwCurrentState = a1;
  if ( a1 - 2 <= 1 )
  {
    ++SStatus.dwCheckPoint;
    SStatus.dwWaitHint = 10000;
  }
  else
  {
    *(_QWORD *)&SStatus.dwCheckPoint = 0;
  }
  if ( !SetServiceStatus(hService, &SStatus) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, LastError);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18003b5d8  sub     rsp, 28h
0x18003b5dc  mov     r8, cs:?hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * hService
0x18003b5e3  test    r8, r8
0x18003b5e6  jz      short loc_18003B665
0x18003b5e8  lea     eax, [rcx-2]
0x18003b5eb  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS SStatus ...
0x18003b5f1  cmp     eax, 1
0x18003b5f4  jbe     short loc_18003B603
0x18003b5f6  mov     qword ptr cs:?SStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS SStatus ...
0x18003b601  jmp     short loc_18003B613
0x18003b603  inc     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS SStatus ...
0x18003b609  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS SStatus ...
0x18003b613  lea     rdx, ?SStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18003b61a  mov     rcx, r8; hServiceStatus
0x18003b61d  call    cs:__imp_SetServiceStatus
0x18003b623  test    eax, eax
0x18003b625  jnz     short loc_18003B66C
0x18003b627  mov     rax, cs:WPP_GLOBAL_Control
0x18003b62e  lea     rcx, WPP_GLOBAL_Control
0x18003b635  cmp     rax, rcx
0x18003b638  jz      short loc_18003B665
0x18003b63a  test    byte ptr [rax+1Ch], 1
0x18003b63e  jz      short loc_18003B665
0x18003b640  call    cs:__imp_GetLastError
0x18003b646  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b64d  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003b654  mov     edx, 0Ch
0x18003b659  mov     r9d, eax
0x18003b65c  mov     rcx, [rcx+10h]
0x18003b660  call    WPP_SF_d
0x18003b665  xor     al, al
0x18003b667  add     rsp, 28h
0x18003b66b  retn
0x18003b66c  mov     al, 1
0x18003b66e  jmp     short loc_18003B667
```
