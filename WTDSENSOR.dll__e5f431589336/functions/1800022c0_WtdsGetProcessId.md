# WtdsGetProcessId

- ea: `0x1800022c0`
- end: `0x18000237d`
- name: `WtdsGetProcessId`
- size: `189`
- prototype: `__int64 __fastcall(DWORD dwProcessId, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001550`
- `0x1800022c0`
- `0x180002b08`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002335`
- `ntdll!RtlNtStatusToDosError` at `0x180002335`
- `ntdll!NtQueryInformationProcess` at `0x180002329`
- `ntdll!NtQueryInformationProcess` at `0x180002329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000234f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000234f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800022f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800022f6`

## pseudocode

```c
__int64 __fastcall WtdsGetProcessId(DWORD dwProcessId, __int64 a2)
{
  HANDLE v4; // rax
  void *v5; // rdi
  ULONG v6; // ebx
  int v7; // eax
  __int64 ProcessInformation; // [rsp+30h] [rbp-18h] BYREF

  ProcessInformation = 0;
  v4 = OpenProcess(0x1000u, 0, dwProcessId);
  v5 = v4;
  if ( v4 )
  {
    v7 = NtQueryInformationProcess(v4, ProcessLUIDDeviceMapsEnabled|0x40, &ProcessInformation, 8u, 0);
    if ( v7 >= 0 )
    {
      *(_QWORD *)(a2 + 8) = ProcessInformation;
      *(_DWORD *)a2 = dwProcessId;
      v6 = 0;
    }
    else
    {
      v6 = RtlNtStatusToDosError(v7);
    }
    if ( !CloseHandle(v5) )
      sub_180002B08();
  }
  else
  {
    return GetLastError();
  }
  return v6;
}

```

## disassembly

```asm
0x1800022c0  mov     [rsp+arg_10], rbx
0x1800022c5  mov     [rsp+arg_18], rsi
0x1800022ca  push    rdi
0x1800022cb  sub     rsp, 40h
0x1800022cf  mov     rax, cs:__security_cookie
0x1800022d6  xor     rax, rsp
0x1800022d9  mov     [rsp+48h+var_10], rax
0x1800022de  mov     rbx, rdx
0x1800022e1  mov     [rsp+48h+ProcessInformation], 0
0x1800022ea  mov     esi, ecx
0x1800022ec  mov     r8d, ecx; dwProcessId
0x1800022ef  xor     edx, edx; bInheritHandle
0x1800022f1  mov     ecx, 1000h; dwDesiredAccess
0x1800022f6  call    cs:OpenProcess
0x1800022fc  mov     rdi, rax
0x1800022ff  test    rax, rax
0x180002302  jnz     short loc_18000230E
0x180002304  call    cs:GetLastError
0x18000230a  mov     ebx, eax
0x18000230c  jmp     short loc_18000235E
0x18000230e  mov     r9d, 8; ProcessInformationLength
0x180002314  mov     [rsp+48h+ReturnLength], 0; ReturnLength
0x18000231d  lea     r8, [rsp+48h+ProcessInformation]; ProcessInformation
0x180002322  mov     rcx, rdi; ProcessHandle
0x180002325  lea     edx, [r9+54h]; ProcessInformationClass
0x180002329  call    cs:NtQueryInformationProcess
0x18000232f  test    eax, eax
0x180002331  jns     short loc_18000233F
0x180002333  mov     ecx, eax; Status
0x180002335  call    cs:RtlNtStatusToDosError
0x18000233b  mov     ebx, eax
0x18000233d  jmp     short loc_18000234C
0x18000233f  mov     rax, [rsp+48h+ProcessInformation]
0x180002344  mov     [rbx+8], rax
0x180002348  mov     [rbx], esi
0x18000234a  xor     ebx, ebx
0x18000234c  mov     rcx, rdi; hObject
0x18000234f  call    cs:CloseHandle
0x180002355  test    eax, eax
0x180002357  jnz     short loc_18000235E
0x180002359  call    sub_180002B08
0x18000235e  mov     eax, ebx
0x180002360  mov     rcx, [rsp+48h+var_10]
0x180002365  xor     rcx, rsp; StackCookie
0x180002368  call    __security_check_cookie
0x18000236d  mov     rbx, [rsp+48h+arg_10]
0x180002372  mov     rsi, [rsp+48h+arg_18]
0x180002377  add     rsp, 40h
0x18000237b  pop     rdi
0x18000237c  retn
```
