# CWorkflowSession::CaptureSourcePidAndStartProcessMonitor(void)

- ea: `0x180019290`
- end: `0x180019349`
- name: `?CaptureSourcePidAndStartProcessMonitor@CWorkflowSession@@UEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CWorkflowSession *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010aec`
- `0x180010b0c`
- `0x180019290`
- `0x18001a7c0`
- `0x180021eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019318`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019318`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800192fd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800192fd`

## string_xrefs

- `0x1800192b4`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x180019329`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`

## pseudocode

```c
__int64 __fastcall CWorkflowSession::CaptureSourcePidAndStartProcessMonitor(CWorkflowSession *this)
{
  int CallerProcessId; // eax
  unsigned int v3; // ebx
  HANDLE Thread; // rax
  const char *v6; // r9
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  CallerProcessId = GetCallerProcessId((unsigned int *)this + 61);
  v3 = CallerProcessId;
  if ( CallerProcessId >= 0 )
  {
    if ( *((_QWORD *)this + 29) )
      return 0;
    Thread = CreateThread(0, 0, CWorkflowSession::WatchProcessThread, (char *)this - 24, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 232,
      Thread);
    WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF);
    if ( *((_QWORD *)this + 29) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x16E,
               (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
               v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      (const char *)(unsigned int)CallerProcessId,
      dwCreationFlags);
    return v3;
  }
}

```

## disassembly

```asm
0x180019290  mov     [rsp+arg_0], rbx
0x180019295  push    rdi
0x180019296  sub     rsp, 30h
0x18001929a  mov     rdi, rcx
0x18001929d  add     rcx, 0F4h; unsigned int *
0x1800192a4  call    ?GetCallerProcessId@@YAJPEAK@Z; GetCallerProcessId(ulong *)
0x1800192a9  mov     ebx, eax
0x1800192ab  test    eax, eax
0x1800192ad  jns     short loc_1800192CC
0x1800192af  mov     rcx, [rsp+38h]; this
0x1800192b4  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x1800192bb  mov     r9d, eax; char *
0x1800192be  mov     edx, 168h; void *
0x1800192c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192c8  mov     eax, ebx
0x1800192ca  jmp     short loc_18001933E
0x1800192cc  lea     r9, [rdi-18h]; lpParameter
0x1800192d0  cmp     qword ptr [r9+100h], 0
0x1800192d8  jnz     short loc_18001933C
0x1800192da  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800192e3  lea     r8, ?WatchProcessThread@CWorkflowSession@@SAKPEAX@Z; lpStartAddress
0x1800192ea  xor     edx, edx; dwStackSize
0x1800192ec  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800192f4  xor     ecx, ecx; lpThreadAttributes
0x1800192f6  lea     rbx, [rdi+0E8h]
0x1800192fd  call    cs:__imp_CreateThread
0x180019303  mov     rdx, rax
0x180019306  mov     rcx, rbx
0x180019309  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001930e  mov     rcx, [rdi+80h]; hHandle
0x180019315  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019318  call    cs:__imp_WaitForSingleObject
0x18001931e  cmp     qword ptr [rbx], 0
0x180019322  jnz     short loc_18001933C
0x180019324  mov     rcx, [rsp+38h]; this
0x180019329  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x180019330  mov     edx, 16Eh; void *
0x180019335  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001933a  jmp     short loc_18001933E
0x18001933c  xor     eax, eax
0x18001933e  mov     rbx, [rsp+38h+arg_0]
0x180019343  add     rsp, 30h
0x180019347  pop     rdi
0x180019348  retn
```
