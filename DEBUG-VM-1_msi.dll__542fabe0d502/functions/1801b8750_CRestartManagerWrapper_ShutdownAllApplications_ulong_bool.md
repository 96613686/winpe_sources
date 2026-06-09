# CRestartManagerWrapper::ShutdownAllApplications(ulong,bool)

- ea: `0x1801b8750`
- end: `0x1801b8879`
- name: `?ShutdownAllApplications@CRestartManagerWrapper@@UEAAIK_N@Z`
- size: `297`
- prototype: `unsigned int __fastcall(CRestartManagerWrapper *__hidden this, unsigned int, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1801382a0`
- `0x1801b8750`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1801b878e`
- `KERNEL32!LeaveCriticalSection` at `0x1801b883a`
- `KERNEL32!LeaveCriticalSection` at `0x1801b878e`
- `KERNEL32!LeaveCriticalSection` at `0x1801b883a`
- `KERNEL32!GetExitCodeThread` at `0x1801b8860`
- `KERNEL32!GetExitCodeThread` at `0x1801b8860`
- `KERNEL32!GetLastError` at `0x1801b886e`
- `KERNEL32!GetLastError` at `0x1801b886e`
- `KERNEL32!EnterCriticalSection` at `0x1801b876b`
- `KERNEL32!EnterCriticalSection` at `0x1801b876b`
- `KERNEL32!WaitForSingleObject` at `0x1801b8846`
- `KERNEL32!WaitForSingleObject` at `0x1801b8846`
- `KERNEL32!CreateThread` at `0x1801b8800`
- `KERNEL32!CreateThread` at `0x1801b8800`

## pseudocode

```c
unsigned int __fastcall CRestartManagerWrapper::ShutdownAllApplications(CRestartManagerWrapper *this, int a2, char a3)
{
  bool v6; // zf
  unsigned int result; // eax
  int v8; // esi
  HANDLE *v9; // rdi
  HANDLE v10; // rax
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+68h] [rbp+20h] BYREF

  EnterCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  v6 = *((_BYTE *)this + 84) == 0;
  ExitCode = 0;
  if ( !v6 )
  {
    ExitCode = 5;
LABEL_3:
    LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
    return ExitCode;
  }
  v8 = 1;
  if ( (unsigned int)(*((_DWORD *)this + 20) - 3) > 1 )
  {
    ExitCode = 22;
    goto LABEL_3;
  }
  *((_DWORD *)this + 199) = a2;
  v9 = (HANDLE *)((char *)this + 800);
  v6 = *((_QWORD *)this + 100) == 0;
  *((_DWORD *)this + 20) = 5;
  ThreadId = 0;
  if ( !v6
    || (v10 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ShutdownAppsThreadStart, this, 0, &ThreadId),
        CHandle::operator=((char *)this + 800, v10),
        *v9) )
  {
    *((_BYTE *)this + 788) = a3;
    v8 = 3;
  }
  *((_DWORD *)this + 22) = v8;
  if ( g_scServerContext != 2 )
    goto LABEL_3;
  LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  result = WaitForSingleObject(*v9, 0xFFFFFFFF);
  ExitCode = result;
  if ( !result )
  {
    if ( !GetExitCodeThread(*v9, &ExitCode) )
      return GetLastError();
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x1801b8750  mov     [rsp+arg_8], rbx
0x1801b8755  push    rbp
0x1801b8756  push    rsi
0x1801b8757  push    rdi
0x1801b8758  sub     rsp, 30h
0x1801b875c  mov     rbx, rcx
0x1801b875f  mov     bpl, r8b
0x1801b8762  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b8769  mov     edi, edx
0x1801b876b  call    cs:__imp_EnterCriticalSection
0x1801b8771  cmp     byte ptr [rbx+54h], 0
0x1801b8775  mov     [rsp+48h+ExitCode], 0
0x1801b877d  jz      short loc_1801B87A5
0x1801b877f  mov     [rsp+48h+ExitCode], 5
0x1801b8787  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b878e  call    cs:__imp_LeaveCriticalSection
0x1801b8794  mov     eax, [rsp+48h+ExitCode]
0x1801b8798  mov     rbx, [rsp+48h+arg_8]
0x1801b879d  add     rsp, 30h
0x1801b87a1  pop     rdi
0x1801b87a2  pop     rsi
0x1801b87a3  pop     rbp
0x1801b87a4  retn
0x1801b87a5  mov     eax, [rbx+50h]
0x1801b87a8  mov     esi, 1
0x1801b87ad  sub     eax, 3
0x1801b87b0  cmp     eax, esi
0x1801b87b2  jbe     short loc_1801B87BE
0x1801b87b4  mov     [rsp+48h+ExitCode], 16h
0x1801b87bc  jmp     short loc_1801B8787
0x1801b87be  mov     [rbx+31Ch], edi
0x1801b87c4  lea     rdi, [rbx+320h]
0x1801b87cb  cmp     qword ptr [rdi], 0
0x1801b87cf  mov     dword ptr [rbx+50h], 5
0x1801b87d6  mov     [rsp+48h+ThreadId], 0
0x1801b87de  jnz     short loc_1801B8817
0x1801b87e0  lea     rax, [rsp+48h+ThreadId]
0x1801b87e5  mov     r9, rbx; lpParameter
0x1801b87e8  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1801b87ed  lea     r8, ?ShutdownAppsThreadStart@@YAKPEAX@Z; lpStartAddress
0x1801b87f4  xor     edx, edx; dwStackSize
0x1801b87f6  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1801b87fe  xor     ecx, ecx; lpThreadAttributes
0x1801b8800  call    cs:__imp_CreateThread
0x1801b8806  mov     rdx, rax
0x1801b8809  mov     rcx, rdi
0x1801b880c  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1801b8811  cmp     qword ptr [rdi], 0
0x1801b8815  jz      short loc_1801B8823
0x1801b8817  mov     [rbx+314h], bpl
0x1801b881e  mov     esi, 3
0x1801b8823  mov     [rbx+58h], esi
0x1801b8826  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801b882d  jnz     loc_1801B8787
0x1801b8833  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b883a  call    cs:__imp_LeaveCriticalSection
0x1801b8840  mov     rcx, [rdi]; hHandle
0x1801b8843  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801b8846  call    cs:__imp_WaitForSingleObject
0x1801b884c  mov     [rsp+48h+ExitCode], eax
0x1801b8850  test    eax, eax
0x1801b8852  jnz     loc_1801B8798
0x1801b8858  mov     rcx, [rdi]; hThread
0x1801b885b  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1801b8860  call    cs:__imp_GetExitCodeThread
0x1801b8866  test    eax, eax
0x1801b8868  jnz     loc_1801B8794
0x1801b886e  call    cs:__imp_GetLastError
0x1801b8874  jmp     loc_1801B8798
```
