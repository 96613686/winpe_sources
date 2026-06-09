# ServiceHandler

- ea: `0x1800114d0`
- end: `0x1800115e7`
- name: `ServiceHandler`
- size: `279`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009534`
- `0x180010194`
- `0x18001136c`
- `0x1800114d0`
- `0x180012b2c`
- `0x180012dc8`
- `0x180026010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800115bd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800115bd`

## string_xrefs

- `0x18001151d`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v12; // [rsp+20h] [rbp-10h] BYREF
  __int64 v13; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]

  v4 = dwControl - 1;
  if ( v4 )
  {
    v5 = v4 - 13;
    if ( v5 )
    {
      v6 = v5 - 19;
      if ( v6 )
      {
        if ( v6 == 95 )
        {
          v7 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD *, LPVOID))(*(_QWORD *)qword_180036BF8 + 24LL))(
                 qword_180036BF8,
                 1,
                 lpEventData,
                 lpContext);
          if ( v7 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x75,
              (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
              (const char *)(unsigned int)v7,
              v12);
        }
        return 0;
      }
      v13 = *((unsigned int *)lpEventData + 1);
      v12 = lpEventData[1];
      if ( dwEventType == 5 )
      {
        LogonTrigger::HandleLogOn(qword_180036C00, &v12, lpEventData, lpContext);
        return 0;
      }
    }
    else
    {
      v13 = *((unsigned int *)lpEventData + 1);
      v12 = 0;
    }
    if ( dwEventType == 6 )
      LogonTrigger::HandleLogOff(qword_180036C00, &v12, lpEventData, lpContext);
  }
  else
  {
    *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
    if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x48, v9, v10);
    wil::details::SetEvent(qword_180036BD8, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800114d0  push    rbp
0x1800114d2  mov     rbp, rsp
0x1800114d5  sub     rsp, 30h
0x1800114d9  sub     ecx, 1
0x1800114dc  jz      loc_1800115A4
0x1800114e2  sub     ecx, 0Dh
0x1800114e5  jz      loc_18001158C
0x1800114eb  sub     ecx, 13h
0x1800114ee  jz      short loc_180011536
0x1800114f0  cmp     ecx, 5Fh ; '_'
0x1800114f3  jnz     loc_1800115DF
0x1800114f9  mov     rcx, cs:qword_180036BF8
0x180011500  mov     edx, 1
0x180011505  mov     rax, [rcx]
0x180011508  mov     rax, [rax+18h]
0x18001150c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011511  test    eax, eax
0x180011513  jns     loc_1800115DF
0x180011519  mov     rcx, [rbp+8]; this
0x18001151d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180011524  mov     r9d, eax; char *
0x180011527  mov     edx, 75h ; 'u'; void *
0x18001152c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011531  jmp     loc_1800115DF
0x180011536  mov     eax, [r8+4]
0x18001153a  mov     dword ptr [rbp+var_10+8], eax
0x18001153d  mov     rax, [r8+8]
0x180011541  mov     qword ptr [rbp+var_10], rax
0x180011545  mov     dword ptr [rbp+var_10+0Ch], 0
0x18001154c  cmp     edx, 5
0x18001154f  jnz     short loc_18001156C
0x180011551  movaps  xmm0, [rbp+var_10]
0x180011555  lea     rdx, [rbp+var_10]
0x180011559  mov     rcx, cs:qword_180036C00
0x180011560  movdqa  [rbp+var_10], xmm0
0x180011565  call    ?HandleLogOn@LogonTrigger@@QEAAXU_SESSION_USER_CONTEXT@@@Z; LogonTrigger::HandleLogOn(_SESSION_USER_CONTEXT)
0x18001156a  jmp     short loc_1800115DF
0x18001156c  cmp     edx, 6
0x18001156f  jnz     short loc_1800115DF
0x180011571  movaps  xmm0, [rbp+var_10]
0x180011575  lea     rdx, [rbp+var_10]
0x180011579  mov     rcx, cs:qword_180036C00
0x180011580  movdqa  [rbp+var_10], xmm0
0x180011585  call    ?HandleLogOff@LogonTrigger@@QEAAXU_SESSION_USER_CONTEXT@@@Z; LogonTrigger::HandleLogOff(_SESSION_USER_CONTEXT)
0x18001158a  jmp     short loc_1800115DF
0x18001158c  mov     eax, [r8+4]
0x180011590  mov     dword ptr [rbp+var_10+8], eax
0x180011593  mov     dword ptr [rbp+var_10+0Ch], 0
0x18001159a  mov     qword ptr [rbp+var_10], 0
0x1800115a2  jmp     short loc_18001156C
0x1800115a4  mov     rcx, cs:?g_serviceState@@3VServiceState@@A; hServiceStatus
0x1800115ab  lea     rdx, ServiceStatus; lpServiceStatus
0x1800115b2  mov     qword ptr cs:ServiceStatus.dwCurrentState, 3
0x1800115bd  call    cs:__imp_SetServiceStatus
0x1800115c3  test    eax, eax
0x1800115c5  jnz     short loc_1800115D3
0x1800115c7  mov     rcx, [rbp+8]; this
0x1800115cb  lea     edx, [rax+48h]; void *
0x1800115ce  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800115d3  mov     rcx, cs:qword_180036BD8; this
0x1800115da  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800115df  xor     eax, eax
0x1800115e1  add     rsp, 30h
0x1800115e5  pop     rbp
0x1800115e6  retn
```
