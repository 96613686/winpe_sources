# JobExecution::CreateEnforcementThread(_Job const &)

- ea: `0x14000a2b0`
- end: `0x14000a359`
- name: `?CreateEnforcementThread@JobExecution@@CAJAEBU_Job@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(const struct _Job **lpParameter)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dab4`

## callees

- `0x14000740c`
- `0x14000a2b0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14000a2fe`
- `KERNEL32!CreateThread` at `0x14000a2fe`
- `KERNEL32!CloseHandle` at `0x14000a2d9`
- `KERNEL32!CloseHandle` at `0x14000a2d9`
- `KERNEL32!GetLastError` at `0x14000a310`
- `KERNEL32!GetLastError` at `0x14000a310`

## string_xrefs

- `0x14000a332`: `Failed to create enforcement thread for job %1.  Error = 0x%2!x!.`

## pseudocode

```c
__int64 __fastcall JobExecution::CreateEnforcementThread(const struct _Job **lpParameter)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  if ( JobExecution::m_bIsEnforcementThreadRunning )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    if ( JobExecution::m_hEnforcementThread )
      CloseHandle(JobExecution::m_hEnforcementThread);
    JobExecution::m_hEnforcementThread = CreateThread(
                                           0,
                                           0,
                                           (LPTHREAD_START_ROUTINE)JobExecution::EnforcementMain,
                                           lpParameter,
                                           0,
                                           0);
    if ( JobExecution::m_hEnforcementThread )
    {
      v2 = 0;
      JobExecution::m_bIsEnforcementThreadRunning = 1;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned __int64)lpParameter[3] >= 8 )
        lpParameter = (const struct _Job **)*lpParameter;
      LogError(L"Failed to create enforcement thread for job %1.  Error = 0x%2!x!.", lpParameter, v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000a2b0  mov     [rsp+arg_0], rbx
0x14000a2b5  push    rdi
0x14000a2b6  sub     rsp, 30h
0x14000a2ba  cmp     cs:?m_bIsEnforcementThreadRunning@JobExecution@@0_NA, 0; bool JobExecution::m_bIsEnforcementThreadRunning
0x14000a2c1  mov     rdi, rcx
0x14000a2c4  jz      short loc_14000A2CD
0x14000a2c6  mov     ebx, 80070057h
0x14000a2cb  jmp     short loc_14000A34C
0x14000a2cd  mov     rcx, cs:?m_hEnforcementThread@JobExecution@@0PEAXEA; hObject
0x14000a2d4  test    rcx, rcx
0x14000a2d7  jz      short loc_14000A2DF
0x14000a2d9  call    cs:__imp_CloseHandle
0x14000a2df  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14000a2e8  lea     r8, ?EnforcementMain@JobExecution@@CAKPEAX@Z; lpStartAddress
0x14000a2ef  mov     r9, rdi; lpParameter
0x14000a2f2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000a2fa  xor     edx, edx; dwStackSize
0x14000a2fc  xor     ecx, ecx; lpThreadAttributes
0x14000a2fe  call    cs:__imp_CreateThread
0x14000a304  mov     cs:?m_hEnforcementThread@JobExecution@@0PEAXEA, rax; void * JobExecution::m_hEnforcementThread
0x14000a30b  test    rax, rax
0x14000a30e  jnz     short loc_14000A343
0x14000a310  call    cs:__imp_GetLastError
0x14000a316  mov     ebx, eax
0x14000a318  test    eax, eax
0x14000a31a  jle     short loc_14000A325
0x14000a31c  movzx   ebx, ax
0x14000a31f  or      ebx, 80070000h
0x14000a325  cmp     qword ptr [rdi+18h], 8
0x14000a32a  jb      short loc_14000A32F
0x14000a32c  mov     rdi, [rdi]
0x14000a32f  mov     r8d, ebx
0x14000a332  lea     rcx, aFailedToCreate; "Failed to create enforcement thread for"...
0x14000a339  mov     rdx, rdi
0x14000a33c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000a341  jmp     short loc_14000A34C
0x14000a343  xor     ebx, ebx
0x14000a345  mov     cs:?m_bIsEnforcementThreadRunning@JobExecution@@0_NA, 1; bool JobExecution::m_bIsEnforcementThreadRunning
0x14000a34c  mov     eax, ebx
0x14000a34e  mov     rbx, [rsp+38h+arg_0]
0x14000a353  add     rsp, 30h
0x14000a357  pop     rdi
0x14000a358  retn
```
