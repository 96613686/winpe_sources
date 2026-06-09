# AppReadiness::Trace::ApiExit

- ea: `0x180012910`
- end: `0x180012a53`
- name: `AppReadiness::Trace::ApiExit`
- size: `323`
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
- `0x180012910`
- `0x180015930`
- `0x18003e210`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012a30`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012a30`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001296f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001296f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001298d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001298d`

## pseudocode

```c
void __fastcall AppReadiness::Trace::ApiExit(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2, __int64 a3)
{
  int CallingProcessHandle; // ebx
  __int64 v6; // r8
  char *v7; // rcx
  __int64 v8; // rax
  DWORD ProcessId; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Process; // [rsp+28h] [rbp-D8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD *p_ProcessId; // [rsp+40h] [rbp-C0h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  int *v14; // [rsp+50h] [rbp-B0h]
  __int64 v15; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v16[264]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+2B8h] [rbp+1B8h] BYREF

  v17 = a2;
  if ( (Microsoft_Windows_AppReadinessEnableBits & 8) != 0 )
  {
    ProcessId = 0;
    Process = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(EventDescriptor, a2, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v7 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v7);
    if ( CallingProcessHandle < 0 )
      ProcessId = -1;
    if ( (int)AppReadiness::GetCallingUserSidString(a3, v16, v6) < 0 )
      StringCchCopyW(v16, 0x104u, L"<unknown>");
    UserData.Ptr = (ULONGLONG)v16;
    v8 = -1;
    do
      ++v8;
    while ( v16[v8] );
    UserData.Size = 2 * v8 + 2;
    UserData.Reserved = 0;
    p_ProcessId = &ProcessId;
    v13 = 4;
    v14 = &v17;
    v15 = 4;
    EventWrite(Windows_AppReadiness_Context, EventDescriptor, 3u, &UserData);
  }
}

```

## disassembly

```asm
0x180012910  mov     [rsp-8+arg_8], edx
0x180012914  push    rbp
0x180012915  push    rbx
0x180012916  push    rsi
0x180012917  push    rdi
0x180012918  push    r14
0x18001291a  lea     rbp, [rsp-180h]
0x180012922  sub     rsp, 280h
0x180012929  mov     rax, cs:__security_cookie
0x180012930  xor     rax, rsp
0x180012933  mov     [rbp+1A0h+var_30], rax
0x18001293a  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 8
0x180012941  mov     rdi, r8
0x180012944  mov     rsi, rcx
0x180012947  jz      loc_180012A36
0x18001294d  xor     r14d, r14d
0x180012950  lea     r8, [rsp+2A0h+Process]
0x180012955  mov     [rsp+2A0h+var_280], r14d
0x18001295a  mov     [rsp+2A0h+Process], r14
0x18001295f  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180012964  mov     ebx, eax
0x180012966  test    eax, eax
0x180012968  js      short loc_180012979
0x18001296a  mov     rcx, [rsp+2A0h+Process]; Process
0x18001296f  call    cs:__imp_GetProcessId
0x180012975  mov     [rsp+2A0h+var_280], eax
0x180012979  mov     rcx, [rsp+2A0h+Process]; hObject
0x18001297e  mov     [rsp+2A0h+Process], r14
0x180012983  lea     rdx, [rcx-1]
0x180012987  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001298b  ja      short loc_180012993
0x18001298d  call    cs:__imp_CloseHandle
0x180012993  test    ebx, ebx
0x180012995  jns     short loc_18001299F
0x180012997  mov     [rsp+2A0h+var_280], 0FFFFFFFFh
0x18001299f  lea     rdx, [rsp+2A0h+var_240]
0x1800129a4  mov     rcx, rdi
0x1800129a7  call    AppReadiness__GetCallingUserSidString
0x1800129ac  test    eax, eax
0x1800129ae  jns     short loc_1800129C6
0x1800129b0  lea     r8, aUnknown; "<unknown>"
0x1800129b7  mov     edx, 104h; unsigned __int64
0x1800129bc  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800129c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800129c6  lea     rax, [rsp+2A0h+var_240]
0x1800129cb  mov     [rsp+2A0h+UserData.Ptr], rax
0x1800129d0  lea     rcx, [rsp+2A0h+var_240]
0x1800129d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800129d9  inc     rax
0x1800129dc  cmp     [rcx+rax*2], r14w
0x1800129e1  jnz     short loc_1800129D9
0x1800129e3  mov     rcx, cs:Windows_AppReadiness_Context; RegHandle
0x1800129ea  lea     eax, ds:2[rax*2]
0x1800129f1  mov     [rsp+2A0h+UserData.Size], eax
0x1800129f5  lea     r9, [rsp+2A0h+UserData]; UserData
0x1800129fa  lea     rax, [rsp+2A0h+var_280]
0x1800129ff  mov     dword ptr [rsp+2A0h+UserData.0Ch], r14d
0x180012a04  mov     [rsp+2A0h+var_260], rax
0x180012a09  mov     r8d, 3; UserDataCount
0x180012a0f  lea     rax, [rbp+1A0h+arg_8]
0x180012a16  mov     [rsp+2A0h+var_258], 4
0x180012a1f  mov     rdx, rsi; EventDescriptor
0x180012a22  mov     [rsp+2A0h+var_250], rax
0x180012a27  mov     [rsp+2A0h+var_248], 4
0x180012a30  call    cs:__imp_EventWrite
0x180012a36  mov     rcx, [rbp+1A0h+var_30]
0x180012a3d  xor     rcx, rsp; StackCookie
0x180012a40  call    __security_check_cookie
0x180012a45  add     rsp, 280h
0x180012a4c  pop     r14
0x180012a4e  pop     rdi
0x180012a4f  pop     rsi
0x180012a50  pop     rbx
0x180012a51  pop     rbp
0x180012a52  retn
```
