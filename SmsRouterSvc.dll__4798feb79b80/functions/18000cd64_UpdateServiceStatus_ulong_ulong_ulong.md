# UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18000cd64`
- end: `0x18000ce15`
- name: `?UpdateServiceStatus@@YAJKKK@Z`
- size: `177`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000c430`
- `0x18000c840`
- `0x18000c8e0`
- `0x18000cb70`

## callees

- `0x18000cd64`
- `0x180051628`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000cdde`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000cdde`

## string_xrefs

- `0x18000cdf7`: `UpdateServiceStatus`

## pseudocode

```c
__int64 __fastcall UpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  unsigned int v5; // edi

  if ( hServiceStatus )
  {
    v5 = 0;
    ServiceStatus.dwCurrentState = a1;
    ServiceStatus.dwWin32ExitCode = a2;
    ServiceStatus.dwWaitHint = a3;
    ServiceStatus.dwControlsAccepted = a1 != 2 ? 0x405 : 0;
    if ( a1 == 4 || a1 == 1 )
      ServiceStatus.dwCheckPoint = 0;
    else
      ServiceStatus.dwCheckPoint = dword_18008CAD8++;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    LogSmsRouterInfo("UpdateServiceStatus", 0x5Fu, "SmsRouterSvc status=%d, waitHint=%d", a1, a3);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v5;
}

```

## disassembly

```asm
0x18000cd64  mov     [rsp+arg_0], rbx
0x18000cd69  mov     [rsp+arg_8], rsi
0x18000cd6e  push    rdi
0x18000cd6f  sub     rsp, 30h
0x18000cd73  mov     ebx, ecx
0x18000cd75  mov     esi, r8d
0x18000cd78  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000cd7f  test    rcx, rcx
0x18000cd82  jnz     short loc_18000CD8B
0x18000cd84  mov     edi, 8000FFFFh
0x18000cd89  jmp     short loc_18000CE03
0x18000cd8b  xor     edi, edi
0x18000cd8d  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000cd93  lea     eax, [rbx-2]
0x18000cd96  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x18000cd9c  neg     eax
0x18000cd9e  mov     cs:ServiceStatus.dwWaitHint, esi
0x18000cda4  sbb     eax, eax
0x18000cda6  and     eax, 405h
0x18000cdab  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x18000cdb1  cmp     ebx, 4
0x18000cdb4  jz      short loc_18000CDD1
0x18000cdb6  cmp     ebx, 1
0x18000cdb9  jz      short loc_18000CDD1
0x18000cdbb  mov     eax, cs:dword_18008CAD8
0x18000cdc1  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000cdc7  inc     eax
0x18000cdc9  mov     cs:dword_18008CAD8, eax
0x18000cdcf  jmp     short loc_18000CDD7
0x18000cdd1  mov     cs:ServiceStatus.dwCheckPoint, edi
0x18000cdd7  lea     rdx, ServiceStatus; lpServiceStatus
0x18000cdde  call    cs:__imp_SetServiceStatus
0x18000cde4  mov     r9d, ebx
0x18000cde7  mov     [rsp+38h+var_18], esi
0x18000cdeb  lea     r8, aSmsroutersvcSt; "SmsRouterSvc status=%d, waitHint=%d"
0x18000cdf2  mov     edx, 5Fh ; '_'; unsigned int
0x18000cdf7  lea     rcx, aUpdateservices; "UpdateServiceStatus"
0x18000cdfe  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000ce03  mov     rbx, [rsp+38h+arg_0]
0x18000ce08  mov     eax, edi
0x18000ce0a  mov     rsi, [rsp+38h+arg_8]
0x18000ce0f  add     rsp, 30h
0x18000ce13  pop     rdi
0x18000ce14  retn
```
