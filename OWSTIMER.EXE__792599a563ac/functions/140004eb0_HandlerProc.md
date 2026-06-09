# HandlerProc

- ea: `0x140004eb0`
- end: `0x140005025`
- name: `HandlerProc`
- size: `373`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x140004e48`
- `0x140004eb0`
- `0x140007dd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140004edf`
- `ADVAPI32!OpenSCManagerW` at `0x140004edf`
- `ADVAPI32!OpenServiceW` at `0x140004f0a`
- `ADVAPI32!OpenServiceW` at `0x140004f0a`
- `ADVAPI32!QueryServiceStatus` at `0x140004f68`
- `ADVAPI32!QueryServiceStatus` at `0x140004fa5`
- `ADVAPI32!QueryServiceStatus` at `0x140004f68`
- `ADVAPI32!QueryServiceStatus` at `0x140004fa5`
- `ADVAPI32!CloseServiceHandle` at `0x140004ff2`
- `ADVAPI32!CloseServiceHandle` at `0x140004ffb`
- `ADVAPI32!CloseServiceHandle` at `0x140004ff2`
- `ADVAPI32!CloseServiceHandle` at `0x140004ffb`
- `KERNEL32!SetEvent` at `0x140004f8f`
- `KERNEL32!SetEvent` at `0x140004fdf`
- `KERNEL32!SetEvent` at `0x140004f8f`
- `KERNEL32!SetEvent` at `0x140004fdf`
- `KERNEL32!GetLastError` at `0x140004eed`
- `KERNEL32!GetLastError` at `0x140004f18`
- `KERNEL32!GetLastError` at `0x140004eed`
- `KERNEL32!GetLastError` at `0x140004f18`

## pseudocode

```c
__int64 __fastcall HandlerProc(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD LastError; // edi
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbp
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  int v13; // ebx
  HANDLE v14; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  LastError = 0;
  v6 = OpenSCManagerW(0, 0, 1u);
  v7 = v6;
  if ( v6 )
  {
    v8 = OpenServiceW(v6, ServiceName, 4u);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
LABEL_21:
      CloseServiceHandle(v7);
      return LastError;
    }
    v10 = dwControl - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
      {
        if ( !QueryServiceStatus(v8, &ServiceStatus) || ServiceStatus.dwCurrentState - 6 <= 1 )
          goto LABEL_20;
        sub_140004E48(6);
        v14 = qword_140012868;
        goto LABEL_19;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        if ( QueryServiceStatus(v8, &ServiceStatus) && ServiceStatus.dwCurrentState - 4 > 1 )
        {
          sub_140004E48(5);
          SetEvent(qword_140012868);
          dword_140012820 = 0;
        }
        goto LABEL_20;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        sub_140004E48(HIDWORD(qword_140012828));
        goto LABEL_20;
      }
      if ( v13 != 1 )
      {
        LastError = 120;
LABEL_20:
        CloseServiceHandle(v9);
        goto LABEL_21;
      }
    }
    sub_140004E48(3);
    v14 = hEvent;
LABEL_19:
    SetEvent(v14);
    dword_140012820 = 1;
    goto LABEL_20;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x140004eb0  mov     [rsp+arg_0], rbx
0x140004eb5  mov     [rsp+arg_8], rbp
0x140004eba  mov     [rsp+arg_10], rsi
0x140004ebf  push    rdi
0x140004ec0  sub     rsp, 50h
0x140004ec4  mov     rax, cs:__security_cookie
0x140004ecb  xor     rax, rsp
0x140004ece  mov     [rsp+58h+var_18], rax
0x140004ed3  mov     ebx, ecx
0x140004ed5  xor     edi, edi
0x140004ed7  xor     edx, edx; lpDatabaseName
0x140004ed9  xor     ecx, ecx; lpMachineName
0x140004edb  lea     r8d, [rdi+1]; dwDesiredAccess
0x140004edf  call    cs:OpenSCManagerW
0x140004ee5  mov     rbp, rax
0x140004ee8  test    rax, rax
0x140004eeb  jnz     short loc_140004EFA
0x140004eed  call    cs:GetLastError
0x140004ef3  mov     edi, eax
0x140004ef5  jmp     loc_140005001
0x140004efa  mov     r8d, 4; dwDesiredAccess
0x140004f00  lea     rdx, ServiceName; "SPTimerV4"
0x140004f07  mov     rcx, rbp; hSCManager
0x140004f0a  call    cs:OpenServiceW
0x140004f10  mov     rsi, rax
0x140004f13  test    rax, rax
0x140004f16  jnz     short loc_140004F25
0x140004f18  call    cs:GetLastError
0x140004f1e  mov     edi, eax
0x140004f20  jmp     loc_140004FF8
0x140004f25  sub     ebx, 1
0x140004f28  jz      loc_140004FCE
0x140004f2e  sub     ebx, 1
0x140004f31  jz      short loc_140004F9D
0x140004f33  sub     ebx, 1
0x140004f36  jz      short loc_140004F60
0x140004f38  sub     ebx, 1
0x140004f3b  jz      short loc_140004F50
0x140004f3d  cmp     ebx, 1
0x140004f40  jz      loc_140004FCE
0x140004f46  mov     edi, 78h ; 'x'
0x140004f4b  jmp     loc_140004FEF
0x140004f50  mov     ecx, dword ptr cs:qword_140012828+4
0x140004f56  call    sub_140004E48
0x140004f5b  jmp     loc_140004FEF
0x140004f60  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x140004f65  mov     rcx, rsi; hService
0x140004f68  call    cs:QueryServiceStatus
0x140004f6e  test    eax, eax
0x140004f70  jz      short loc_140004FEF
0x140004f72  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x140004f76  add     eax, 0FFFFFFFCh
0x140004f79  cmp     eax, 1
0x140004f7c  jbe     short loc_140004FEF
0x140004f7e  mov     ecx, 5
0x140004f83  call    sub_140004E48
0x140004f88  mov     rcx, cs:qword_140012868; hEvent
0x140004f8f  call    cs:SetEvent
0x140004f95  mov     cs:dword_140012820, edi
0x140004f9b  jmp     short loc_140004FEF
0x140004f9d  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x140004fa2  mov     rcx, rsi; hService
0x140004fa5  call    cs:QueryServiceStatus
0x140004fab  test    eax, eax
0x140004fad  jz      short loc_140004FEF
0x140004faf  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x140004fb3  add     eax, 0FFFFFFFAh
0x140004fb6  cmp     eax, 1
0x140004fb9  jbe     short loc_140004FEF
0x140004fbb  mov     ecx, 6
0x140004fc0  call    sub_140004E48
0x140004fc5  mov     rcx, cs:qword_140012868
0x140004fcc  jmp     short loc_140004FDF
0x140004fce  mov     ecx, 3
0x140004fd3  call    sub_140004E48
0x140004fd8  mov     rcx, cs:hEvent; hEvent
0x140004fdf  call    cs:SetEvent
0x140004fe5  mov     cs:dword_140012820, 1
0x140004fef  mov     rcx, rsi; hSCObject
0x140004ff2  call    cs:CloseServiceHandle
0x140004ff8  mov     rcx, rbp; hSCObject
0x140004ffb  call    cs:CloseServiceHandle
0x140005001  mov     eax, edi
0x140005003  mov     rcx, [rsp+58h+var_18]
0x140005008  xor     rcx, rsp
0x14000500b  call    sub_140007DD0
0x140005010  mov     rbx, [rsp+58h+arg_0]
0x140005015  mov     rbp, [rsp+58h+arg_8]
0x14000501a  mov     rsi, [rsp+58h+arg_10]
0x14000501f  add     rsp, 50h
0x140005023  pop     rdi
0x140005024  retn
```
