# NvAgentService::SetStatus(ulong,ulong)

- ea: `0x180005bb0`
- end: `0x180005c17`
- name: `?SetStatus@NvAgentService@@IEAAXKK@Z`
- size: `103`
- prototype: `void __fastcall(SERVICE_STATUS_HANDLE *this, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005b74`
- `0x180005c20`
- `0x180005de0`

## callees

- `0x180001590`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005bff`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005bff`

## pseudocode

```c
void __fastcall NvAgentService::SetStatus(SERVICE_STATUS_HANDLE *this, DWORD a2)
{
  SERVICE_STATUS_HANDLE v2; // rcx
  DWORD v3; // r8d
  struct _SERVICE_STATUS v4; // [rsp+20h] [rbp-38h] BYREF

  v2 = *this;
  v3 = 0;
  *(_QWORD *)&v4.dwServiceSpecificExitCode = 0;
  v4.dwCurrentState = a2;
  v4.dwServiceType = 32;
  if ( a2 - 2 <= 1 )
    v3 = 30000;
  *(_QWORD *)&v4.dwControlsAccepted = 13;
  v4.dwWaitHint = v3;
  SetServiceStatus(v2, &v4);
}

```

## disassembly

```asm
0x180005bb0  mov     r11, rsp
0x180005bb3  sub     rsp, 58h
0x180005bb7  mov     rax, cs:__security_cookie
0x180005bbe  xor     rax, rsp
0x180005bc1  mov     [rsp+58h+var_18], rax
0x180005bc6  mov     rcx, [rcx]; hServiceStatus
0x180005bc9  lea     eax, [rdx-2]
0x180005bcc  xor     r8d, r8d
0x180005bcf  mov     qword ptr [r11-28h], 0
0x180005bd7  mov     [rsp+58h+var_34], edx
0x180005bdb  cmp     eax, 1
0x180005bde  mov     [rsp+58h+var_38], 20h ; ' '
0x180005be6  mov     edx, 7530h
0x180005beb  cmovbe  r8d, edx
0x180005bef  mov     qword ptr [r11-30h], 0Dh
0x180005bf7  lea     rdx, [r11-38h]; lpServiceStatus
0x180005bfb  mov     [r11-20h], r8d
0x180005bff  call    cs:__imp_SetServiceStatus
0x180005c05  mov     rcx, [rsp+58h+var_18]
0x180005c0a  xor     rcx, rsp; StackCookie
0x180005c0d  call    __security_check_cookie
0x180005c12  add     rsp, 58h
0x180005c16  retn
```
