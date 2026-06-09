# AppReadiness::Trace::ApiEnter

- ea: `0x180013128`
- end: `0x180013264`
- name: `AppReadiness::Trace::ApiEnter`
- size: `316`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012a60`
- `0x180012b70`
- `0x180036bb0`
- `0x180039c40`
- `0x18003a560`
- `0x18003aa20`
- `0x18003ac10`
- `0x1800472a0`

## callees

- `0x1800122d0`
- `0x1800127f4`
- `0x180013128`
- `0x180015930`
- `0x18003e210`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180013237`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180013237`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001318b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001318b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131a9`

## pseudocode

```c
void __fastcall AppReadiness::Trace::ApiEnter(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2)
{
  int CallingProcessHandle; // ebx
  __int64 v5; // r8
  char *v6; // rcx
  __int64 v7; // rax
  DWORD ProcessId; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Process; // [rsp+28h] [rbp-D8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD *p_ProcessId; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (Microsoft_Windows_AppReadinessEnableBits & 8) != 0 )
  {
    ProcessId = 0;
    Process = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(EventDescriptor, a2, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v6 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    if ( CallingProcessHandle < 0 )
      ProcessId = -1;
    if ( (int)AppReadiness::GetCallingUserSidString(a2, v13, v5) < 0 )
      StringCchCopyW(v13, 0x104u, L"<unknown>");
    UserData.Ptr = (ULONGLONG)v13;
    v7 = -1;
    do
      ++v7;
    while ( v13[v7] );
    UserData.Size = 2 * v7 + 2;
    UserData.Reserved = 0;
    p_ProcessId = &ProcessId;
    v12 = 4;
    EventWrite(Windows_AppReadiness_Context, EventDescriptor, 2u, &UserData);
  }
}

```

## disassembly

```asm
0x180013128  mov     [rsp-8+arg_10], rbx
0x18001312d  mov     [rsp-8+arg_18], rsi
0x180013132  push    rbp
0x180013133  push    rdi
0x180013134  push    r14
0x180013136  lea     rbp, [rsp-170h]
0x18001313e  sub     rsp, 270h
0x180013145  mov     rax, cs:__security_cookie
0x18001314c  xor     rax, rsp
0x18001314f  mov     [rbp+180h+var_20], rax
0x180013156  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 8
0x18001315d  mov     rdi, rdx
0x180013160  mov     rsi, rcx
0x180013163  jz      loc_18001323D
0x180013169  xor     r14d, r14d
0x18001316c  lea     r8, [rsp+280h+Process]
0x180013171  mov     [rsp+280h+var_260], r14d
0x180013176  mov     [rsp+280h+Process], r14
0x18001317b  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180013180  mov     ebx, eax
0x180013182  test    eax, eax
0x180013184  js      short loc_180013195
0x180013186  mov     rcx, [rsp+280h+Process]; Process
0x18001318b  call    cs:__imp_GetProcessId
0x180013191  mov     [rsp+280h+var_260], eax
0x180013195  mov     rcx, [rsp+280h+Process]; hObject
0x18001319a  mov     [rsp+280h+Process], r14
0x18001319f  lea     rdx, [rcx-1]
0x1800131a3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800131a7  ja      short loc_1800131AF
0x1800131a9  call    cs:__imp_CloseHandle
0x1800131af  test    ebx, ebx
0x1800131b1  jns     short loc_1800131BB
0x1800131b3  mov     [rsp+280h+var_260], 0FFFFFFFFh
0x1800131bb  lea     rdx, [rsp+280h+var_230]
0x1800131c0  mov     rcx, rdi
0x1800131c3  call    AppReadiness__GetCallingUserSidString
0x1800131c8  test    eax, eax
0x1800131ca  jns     short loc_1800131E2
0x1800131cc  lea     r8, aUnknown; "<unknown>"
0x1800131d3  mov     edx, 104h; unsigned __int64
0x1800131d8  lea     rcx, [rsp+280h+var_230]; unsigned __int16 *
0x1800131dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800131e2  lea     rax, [rsp+280h+var_230]
0x1800131e7  mov     [rsp+280h+UserData.Ptr], rax
0x1800131ec  lea     rcx, [rsp+280h+var_230]
0x1800131f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800131f5  inc     rax
0x1800131f8  cmp     [rcx+rax*2], r14w
0x1800131fd  jnz     short loc_1800131F5
0x1800131ff  mov     rcx, cs:Windows_AppReadiness_Context; RegHandle
0x180013206  lea     eax, ds:2[rax*2]
0x18001320d  mov     [rsp+280h+UserData.Size], eax
0x180013211  lea     r9, [rsp+280h+UserData]; UserData
0x180013216  lea     rax, [rsp+280h+var_260]
0x18001321b  mov     dword ptr [rsp+280h+UserData.0Ch], r14d
0x180013220  mov     r8d, 2; UserDataCount
0x180013226  mov     [rsp+280h+var_240], rax
0x18001322b  mov     rdx, rsi; EventDescriptor
0x18001322e  mov     [rsp+280h+var_238], 4
0x180013237  call    cs:__imp_EventWrite
0x18001323d  mov     rcx, [rbp+180h+var_20]
0x180013244  xor     rcx, rsp; StackCookie
0x180013247  call    __security_check_cookie
0x18001324c  lea     r11, [rsp+280h+var_10]
0x180013254  mov     rbx, [r11+30h]
0x180013258  mov     rsi, [r11+38h]
0x18001325c  mov     rsp, r11
0x18001325f  pop     r14
0x180013261  pop     rdi
0x180013262  pop     rbp
0x180013263  retn
```
