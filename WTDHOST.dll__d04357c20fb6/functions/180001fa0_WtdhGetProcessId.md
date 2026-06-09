# WtdhGetProcessId

- ea: `0x180001fa0`
- end: `0x18000205d`
- name: `WtdhGetProcessId`
- size: `189`
- prototype: `__int64 __fastcall(DWORD dwProcessId, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001550`
- `0x180001fa0`
- `0x180002ddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000202f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000202f`
- `ntdll!RtlNtStatusToDosError` at `0x180002015`
- `ntdll!RtlNtStatusToDosError` at `0x180002015`
- `ntdll!NtQueryInformationProcess` at `0x180002009`
- `ntdll!NtQueryInformationProcess` at `0x180002009`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180001fd6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180001fd6`

## pseudocode

```c
__int64 __fastcall WtdhGetProcessId(DWORD dwProcessId, __int64 a2)
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
      sub_180002DDC();
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
0x180001fa0  mov     [rsp+arg_10], rbx
0x180001fa5  mov     [rsp+arg_18], rsi
0x180001faa  push    rdi
0x180001fab  sub     rsp, 40h
0x180001faf  mov     rax, cs:__security_cookie
0x180001fb6  xor     rax, rsp
0x180001fb9  mov     [rsp+48h+var_10], rax
0x180001fbe  mov     rbx, rdx
0x180001fc1  mov     [rsp+48h+ProcessInformation], 0
0x180001fca  mov     esi, ecx
0x180001fcc  mov     r8d, ecx; dwProcessId
0x180001fcf  xor     edx, edx; bInheritHandle
0x180001fd1  mov     ecx, 1000h; dwDesiredAccess
0x180001fd6  call    cs:OpenProcess
0x180001fdc  mov     rdi, rax
0x180001fdf  test    rax, rax
0x180001fe2  jnz     short loc_180001FEE
0x180001fe4  call    cs:GetLastError
0x180001fea  mov     ebx, eax
0x180001fec  jmp     short loc_18000203E
0x180001fee  mov     r9d, 8; ProcessInformationLength
0x180001ff4  mov     [rsp+48h+ReturnLength], 0; ReturnLength
0x180001ffd  lea     r8, [rsp+48h+ProcessInformation]; ProcessInformation
0x180002002  mov     rcx, rdi; ProcessHandle
0x180002005  lea     edx, [r9+54h]; ProcessInformationClass
0x180002009  call    cs:NtQueryInformationProcess
0x18000200f  test    eax, eax
0x180002011  jns     short loc_18000201F
0x180002013  mov     ecx, eax; Status
0x180002015  call    cs:RtlNtStatusToDosError
0x18000201b  mov     ebx, eax
0x18000201d  jmp     short loc_18000202C
0x18000201f  mov     rax, [rsp+48h+ProcessInformation]
0x180002024  mov     [rbx+8], rax
0x180002028  mov     [rbx], esi
0x18000202a  xor     ebx, ebx
0x18000202c  mov     rcx, rdi; hObject
0x18000202f  call    cs:CloseHandle
0x180002035  test    eax, eax
0x180002037  jnz     short loc_18000203E
0x180002039  call    sub_180002DDC
0x18000203e  mov     eax, ebx
0x180002040  mov     rcx, [rsp+48h+var_10]
0x180002045  xor     rcx, rsp; StackCookie
0x180002048  call    __security_check_cookie
0x18000204d  mov     rbx, [rsp+48h+arg_10]
0x180002052  mov     rsi, [rsp+48h+arg_18]
0x180002057  add     rsp, 40h
0x18000205b  pop     rdi
0x18000205c  retn
```
