# UbpmpSetProcessPriorities(void *,ulong,ulong,ulong)

- ea: `0x18001d820`
- end: `0x18001da13`
- name: `?UbpmpSetProcessPriorities@@YAXPEAXKKK@Z`
- size: `499`
- prototype: `void __fastcall(HANDLE Process, DWORD dwPriorityClass, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001da20`

## callees

- `0x18001d820`
- `0x18003f110`
- `0x18003f1ec`

## import_xrefs

- `ntdll!NtSetInformationProcess` at `0x18001d857`
- `ntdll!NtSetInformationProcess` at `0x18001d928`
- `ntdll!NtSetInformationProcess` at `0x18001d857`
- `ntdll!NtSetInformationProcess` at `0x18001d928`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d8e0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d95b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d9a9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d9dd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d8e0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d95b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d9a9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d9dd`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18001d8ad`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18001d8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8cf`

## pseudocode

```c
void __fastcall UbpmpSetProcessPriorities(HANDLE Process, DWORD dwPriorityClass, unsigned int a3, unsigned int a4)
{
  NTSTATUS v8; // ebx
  DWORD LastError; // ebx
  DWORD v10; // eax
  __int64 v11; // r8
  NTSTATUS v12; // ebx
  DWORD v13; // eax
  __int64 v14; // r8
  DWORD ProcessId; // eax
  __int64 v16; // r8
  DWORD v17; // eax
  __int64 v18; // r8
  __int64 v19; // [rsp+28h] [rbp-40h]
  NTSTATUS v20; // [rsp+28h] [rbp-40h]
  unsigned int ProcessInformation; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v22; // [rsp+80h] [rbp+18h] BYREF

  v22 = a3;
  ProcessInformation = 0;
  v8 = NtSetInformationProcess(Process, ProcessIoPriority, &v22, 4u);
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    ProcessId = GetProcessId(Process);
    v20 = v8;
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, v16, a3, ProcessId, v20);
  }
  if ( a4 )
  {
    ProcessInformation = a4;
    v12 = NtSetInformationProcess(Process, ProcessPagePriority, &ProcessInformation, 4u);
    if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = GetProcessId(Process);
      LODWORD(v19) = v12;
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, v14, a4, v13, v19);
    }
  }
  if ( dwPriorityClass && !SetPriorityClass(Process, dwPriorityClass) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v10 = GetProcessId(Process);
      LODWORD(v19) = LastError;
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, v11, a4, v10, v19);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v17 = GetProcessId(Process);
    WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, v18, v17, dwPriorityClass, a3, a4);
  }
}

```

## disassembly

```asm
0x18001d820  mov     rax, rsp
0x18001d823  mov     [rax+8], rbx
0x18001d827  push    rbp
0x18001d828  push    rsi
0x18001d829  push    rdi
0x18001d82a  push    r14
0x18001d82c  push    r15
0x18001d82e  sub     rsp, 40h
0x18001d832  mov     esi, r9d
0x18001d835  mov     [rax+18h], r8d
0x18001d839  mov     r14d, r8d
0x18001d83c  mov     dword ptr [rax+10h], 0
0x18001d843  mov     edi, edx
0x18001d845  lea     r8, [rax+18h]; ProcessInformation
0x18001d849  mov     r9d, 4; ProcessInformationLength
0x18001d84f  mov     edx, 21h ; '!'; ProcessInformationClass
0x18001d854  mov     rbp, rcx
0x18001d857  call    cs:__imp_NtSetInformationProcess
0x18001d85e  nop     dword ptr [rax+rax+00h]
0x18001d863  lea     r15, WPP_GLOBAL_Control
0x18001d86a  mov     ebx, eax
0x18001d86c  test    eax, eax
0x18001d86e  js      loc_18001D98C
0x18001d874  test    esi, esi
0x18001d876  jnz     loc_18001D911
0x18001d87c  test    edi, edi
0x18001d87e  jnz     short loc_18001D8A8
0x18001d880  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d887  cmp     rcx, r15
0x18001d88a  jz      short loc_18001D896
0x18001d88c  test    byte ptr [rcx+1Ch], 80h
0x18001d890  jnz     loc_18001D9DA
0x18001d896  mov     rbx, [rsp+68h+arg_0]
0x18001d89b  add     rsp, 40h
0x18001d89f  pop     r15
0x18001d8a1  pop     r14
0x18001d8a3  pop     rdi
0x18001d8a4  pop     rsi
0x18001d8a5  pop     rbp
0x18001d8a6  retn
0x18001d8a8  mov     edx, edi; dwPriorityClass
0x18001d8aa  mov     rcx, rbp; hProcess
0x18001d8ad  call    cs:__imp_SetPriorityClass
0x18001d8b4  nop     dword ptr [rax+rax+00h]
0x18001d8b9  test    eax, eax
0x18001d8bb  jnz     short loc_18001D880
0x18001d8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8c4  cmp     rcx, r15
0x18001d8c7  jz      short loc_18001D896
0x18001d8c9  test    byte ptr [rcx+1Ch], 1
0x18001d8cd  jz      short loc_18001D880
0x18001d8cf  call    cs:__imp_GetLastError
0x18001d8d6  nop     dword ptr [rax+rax+00h]
0x18001d8db  mov     rcx, rbp; Process
0x18001d8de  mov     ebx, eax
0x18001d8e0  call    cs:__imp_GetProcessId
0x18001d8e7  nop     dword ptr [rax+rax+00h]
0x18001d8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8f3  mov     edx, 0C7h
0x18001d8f8  mov     dword ptr [rsp+68h+var_40], ebx
0x18001d8fc  mov     r9d, esi
0x18001d8ff  mov     [rsp+68h+var_48], eax
0x18001d903  mov     rcx, [rcx+10h]
0x18001d907  call    WPP_SF_ddd
0x18001d90c  jmp     loc_18001D880
0x18001d911  mov     r9d, 4; ProcessInformationLength
0x18001d917  mov     [rsp+68h+ProcessInformation], esi
0x18001d91b  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x18001d920  mov     edx, 27h ; '''; ProcessInformationClass
0x18001d925  mov     rcx, rbp; ProcessHandle
0x18001d928  call    cs:__imp_NtSetInformationProcess
0x18001d92f  nop     dword ptr [rax+rax+00h]
0x18001d934  mov     ebx, eax
0x18001d936  test    eax, eax
0x18001d938  jns     loc_18001D87C
0x18001d93e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d945  cmp     rcx, r15
0x18001d948  jz      loc_18001D87C
0x18001d94e  test    byte ptr [rcx+1Ch], 1
0x18001d952  jz      loc_18001D87C
0x18001d958  mov     rcx, rbp; Process
0x18001d95b  call    cs:__imp_GetProcessId
0x18001d962  nop     dword ptr [rax+rax+00h]
0x18001d967  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d96e  mov     edx, 0C6h
0x18001d973  mov     dword ptr [rsp+68h+var_40], ebx
0x18001d977  mov     r9d, esi
0x18001d97a  mov     [rsp+68h+var_48], eax
0x18001d97e  mov     rcx, [rcx+10h]
0x18001d982  call    WPP_SF_ddd
0x18001d987  jmp     loc_18001D87C
0x18001d98c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d993  cmp     rcx, r15
0x18001d996  jz      loc_18001D874
0x18001d99c  test    byte ptr [rcx+1Ch], 1
0x18001d9a0  jz      loc_18001D874
0x18001d9a6  mov     rcx, rbp; Process
0x18001d9a9  call    cs:__imp_GetProcessId
0x18001d9b0  nop     dword ptr [rax+rax+00h]
0x18001d9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9bc  mov     edx, 0C5h
0x18001d9c1  mov     dword ptr [rsp+68h+var_40], ebx
0x18001d9c5  mov     r9d, r14d
0x18001d9c8  mov     [rsp+68h+var_48], eax
0x18001d9cc  mov     rcx, [rcx+10h]
0x18001d9d0  call    WPP_SF_ddd
0x18001d9d5  jmp     loc_18001D874
0x18001d9da  mov     rcx, rbp; Process
0x18001d9dd  call    cs:__imp_GetProcessId
0x18001d9e4  nop     dword ptr [rax+rax+00h]
0x18001d9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9f0  mov     edx, 0C8h
0x18001d9f5  mov     [rsp+68h+var_38], esi
0x18001d9f9  mov     r9d, eax
0x18001d9fc  mov     dword ptr [rsp+68h+var_40], r14d
0x18001da01  mov     [rsp+68h+var_48], edi
0x18001da05  mov     rcx, [rcx+10h]
0x18001da09  call    WPP_SF_dddd
0x18001da0e  jmp     loc_18001D896
```
