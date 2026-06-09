# wil::details::ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___::_ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___

- ea: `0x180015dc0`
- end: `0x180015e3b`
- name: `wil::details::ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___::_ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180057c3e`

## callees

- `0x180015dc0`
- `0x18001609c`
- `0x180016c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015e11`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015e11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___::_ScopeExitFn__lambda_c6cc160110a17cfdf82f761737ad3c67___(
        int **a1)
{
  int **v1; // rbx
  ServiceComContextRegistrar *v2; // rcx
  signed int LastError; // eax
  unsigned int v4; // ecx

  if ( *((_BYTE *)a1 + 16) )
  {
    *((_BYTE *)a1 + 16) = 0;
    v1 = a1 + 1;
    if ( **a1 || **v1 < 0 )
    {
      ServiceComContextRegistrar::Unregister((ServiceComContextRegistrar *)a1);
      ServiceComContextRegistrar::Disconnect(v2);
      g_serviceStatus.dwCurrentState = 1;
    }
    *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      **v1 = v4;
    }
  }
}

```

## disassembly

```asm
0x180015dc0  push    rbx
0x180015dc2  sub     rsp, 20h
0x180015dc6  cmp     byte ptr [rcx+10h], 0
0x180015dca  jz      short loc_180015E35
0x180015dcc  mov     byte ptr [rcx+10h], 0
0x180015dd0  lea     rbx, [rcx+8]
0x180015dd4  mov     rax, [rcx]
0x180015dd7  cmp     dword ptr [rax], 0
0x180015dda  jnz     short loc_180015DE4
0x180015ddc  mov     rax, [rbx]
0x180015ddf  cmp     dword ptr [rax], 0
0x180015de2  jge     short loc_180015DF8
0x180015de4  call    ?Unregister@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Unregister(void)
0x180015de9  call    ?Disconnect@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Disconnect(void)
0x180015dee  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180015df8  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x180015e03  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180015e0a  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180015e11  call    cs:__imp_SetServiceStatus
0x180015e17  test    eax, eax
0x180015e19  jnz     short loc_180015E35
0x180015e1b  call    cs:__imp_GetLastError
0x180015e21  mov     ecx, eax
0x180015e23  test    eax, eax
0x180015e25  jle     short loc_180015E30
0x180015e27  movzx   ecx, ax
0x180015e2a  or      ecx, 80070000h
0x180015e30  mov     rax, [rbx]
0x180015e33  mov     [rax], ecx
0x180015e35  add     rsp, 20h
0x180015e39  pop     rbx
0x180015e3a  retn
```
