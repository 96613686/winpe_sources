# ControlServiceThread(void *)

- ea: `0x18002ce40`
- end: `0x18002ced4`
- name: `?ControlServiceThread@@YAKPEAX@Z`
- size: `148`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001084`
- `0x18002ce40`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce85`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002ce7b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002ce7b`

## pseudocode

```c
__int64 __fastcall ControlServiceThread(PVOID Parameter)
{
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !Parameter )
    return 87;
  if ( ControlService(*((SC_HANDLE *)Parameter + 2), *((_DWORD *)Parameter + 2), &ServiceStatus) )
    goto LABEL_6;
  LastError = GetLastError();
  if ( LastError != 1062 )
  {
    if ( LastError <= 0 )
      goto LABEL_7;
LABEL_11:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_7;
  }
  if ( *((_DWORD *)Parameter + 2) != 1 )
    goto LABEL_11;
LABEL_6:
  LastError = 0;
LABEL_7:
  *(_DWORD *)Parameter = LastError;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 1, 0xFFFFFFFF) == 1 )
    operator delete(Parameter);
  return 0;
}

```

## disassembly

```asm
0x18002ce40  push    rbx
0x18002ce42  sub     rsp, 50h
0x18002ce46  mov     rax, cs:__security_cookie
0x18002ce4d  xor     rax, rsp
0x18002ce50  mov     [rsp+58h+var_18], rax
0x18002ce55  xorps   xmm0, xmm0
0x18002ce58  mov     rbx, rcx
0x18002ce5b  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18002ce60  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002ce65  test    rcx, rcx
0x18002ce68  jnz     short loc_18002CE6F
0x18002ce6a  lea     eax, [rcx+57h]
0x18002ce6d  jmp     short loc_18002CEB3
0x18002ce6f  mov     edx, [rcx+8]; dwControl
0x18002ce72  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002ce77  mov     rcx, [rcx+10h]; hService
0x18002ce7b  call    cs:__imp_ControlService
0x18002ce81  test    eax, eax
0x18002ce83  jnz     short loc_18002CE98
0x18002ce85  call    cs:__imp_GetLastError
0x18002ce8b  cmp     eax, 426h
0x18002ce90  jnz     short loc_18002CEC6
0x18002ce92  cmp     dword ptr [rbx+8], 1
0x18002ce96  jnz     short loc_18002CECA
0x18002ce98  xor     eax, eax
0x18002ce9a  mov     [rbx], eax
0x18002ce9c  or      eax, 0FFFFFFFFh
0x18002ce9f  lock xadd [rbx+4], eax
0x18002cea4  cmp     eax, 1
0x18002cea7  jnz     short loc_18002CEB1
0x18002cea9  mov     rcx, rbx; Block
0x18002ceac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ceb1  xor     eax, eax
0x18002ceb3  mov     rcx, [rsp+58h+var_18]
0x18002ceb8  xor     rcx, rsp; StackCookie
0x18002cebb  call    __security_check_cookie
0x18002cec0  add     rsp, 50h
0x18002cec4  pop     rbx
0x18002cec5  retn
0x18002cec6  test    eax, eax
0x18002cec8  jle     short loc_18002CE9A
0x18002ceca  movzx   eax, ax
0x18002cecd  or      eax, 80070000h
0x18002ced2  jmp     short loc_18002CE9A
```
