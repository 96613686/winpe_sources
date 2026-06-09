# __FatalError(char const *,ulong,char const *,ulong)

- ea: `0x14000e1b4`
- end: `0x14000e305`
- name: `?__FatalError@@YAXPEBDK0K@Z`
- size: `337`
- prototype: `void __fastcall(const char *, int, const char *, int)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cf98`
- `0x14000d2c0`
- `0x14000d3c4`
- `0x14000d490`
- `0x14000d5b4`
- `0x14000d6c0`
- `0x14000d744`
- `0x14000d820`
- `0x14000d944`
- `0x14000da74`
- `0x14000dbbc`
- `0x14000ddf0`
- `0x14000dee0`

## callees

- `0x1400016a0`
- `0x14000e1b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000e2ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000e2ae`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000e2bc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000e2bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000e295`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000e295`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000e1f6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000e1f6`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e29f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e29f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14000e2e2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14000e2e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e2c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e2c4`

## pseudocode

```c
void __fastcall __FatalError(const char *a1, int a2, const char *a3, int a4)
{
  __int64 v5; // rax
  unsigned int v6; // eax
  HANDLE CurrentProcess; // rax
  ULONGLONG RegHandle[2]; // [rsp+20h] [rbp-60h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-50h] BYREF
  int *v10; // [rsp+40h] [rbp-40h]
  __int128 v11; // [rsp+48h] [rbp-38h]
  __int128 v12; // [rsp+58h] [rbp-28h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+98h] [rbp+18h] BYREF
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a2;
  RegHandle[0] = 0;
  if ( !EventRegister(&`__FatalError'::`2'::sc_Microsoft_WindowsPhone_Net_Debug_Provider, 0, 0, RegHandle) )
  {
    v13 = 0;
    UserData.Ptr = (ULONGLONG)"onecoreuap\\net\\wphelper\\asyncpipe.cpp";
    v10 = &v14;
    *(_QWORD *)&UserData.Size = 76;
    v11 = 4u;
    v12 = 0;
    if ( a3 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a3[v5] );
      v6 = 2 * v5 + 2;
    }
    else
    {
      v6 = 5;
    }
    *(_QWORD *)&v12 = v6;
    *((_QWORD *)&v12 + 1) = &v15;
    v13 = 4;
    if ( !a3 )
      a3 = "NULL";
    *((_QWORD *)&v11 + 1) = a3;
    EventWrite(RegHandle[0], &`__FatalError'::`2'::NET_FATAL_ERROR, 4u, &UserData);
    EventUnregister(RegHandle[0]);
  }
  if ( `FastFailTestHook::GetTestHookVariable'::`2'::bTestHookVariable )
  {
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 3u);
  }
  else
  {
    if ( !IsDebuggerPresent() && (MEMORY[0x7FFE02D4] & 3) != 3 )
      __fastfail(7u);
    DebugBreak();
  }
}

```

## disassembly

```asm
0x14000e1b4  mov     [rsp-8+arg_0], rbx
0x14000e1b9  mov     [rsp-8+arg_18], r9d
0x14000e1be  mov     [rsp-8+arg_8], edx
0x14000e1c2  push    rbp
0x14000e1c3  mov     rbp, rsp
0x14000e1c6  sub     rsp, 80h
0x14000e1cd  mov     rax, cs:__security_cookie
0x14000e1d4  xor     rax, rsp
0x14000e1d7  mov     [rbp+var_10], rax
0x14000e1db  mov     rbx, r8
0x14000e1de  mov     [rbp+RegHandle], 0
0x14000e1e6  xor     r8d, r8d; CallbackContext
0x14000e1e9  lea     r9, [rbp+RegHandle]; RegHandle
0x14000e1ed  xor     edx, edx; EnableCallback
0x14000e1ef  lea     rcx, ?sc_Microsoft_WindowsPhone_Net_Debug_Provider@?1??__FatalError@@YAXPEBDK0K@Z@4U_GUID@@B; ProviderId
0x14000e1f6  call    cs:__imp_EventRegister
0x14000e1fc  test    eax, eax
0x14000e1fe  jnz     loc_14000E2A5
0x14000e204  xor     eax, eax
0x14000e206  xorps   xmm0, xmm0
0x14000e209  mov     [rbp+var_18], rax
0x14000e20d  lea     rax, aOnecoreuapNetW; "onecoreuap\\net\\wphelper\\asyncpipe.cp"...
0x14000e214  mov     [rbp+UserData.Ptr], rax
0x14000e218  lea     rax, [rbp+arg_8]
0x14000e21c  mov     r8d, 4; UserDataCount
0x14000e222  movups  xmmword ptr [rbp+UserData.Size], xmm0
0x14000e226  mov     [rbp+var_40], rax
0x14000e22a  mov     qword ptr [rbp+UserData.Size], 4Ch ; 'L'
0x14000e232  movups  [rbp+var_38], xmm0
0x14000e236  mov     qword ptr [rbp+var_38], r8
0x14000e23a  movups  [rbp+var_28], xmm0
0x14000e23e  test    rbx, rbx
0x14000e241  jz      short loc_14000E259
0x14000e243  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e247  inc     rax
0x14000e24a  cmp     byte ptr [rbx+rax], 0
0x14000e24e  jnz     short loc_14000E247
0x14000e250  lea     eax, ds:2[rax*2]
0x14000e257  jmp     short loc_14000E25E
0x14000e259  mov     eax, 5
0x14000e25e  lea     rcx, aNull; "NULL"
0x14000e265  mov     dword ptr [rbp+var_28], eax
0x14000e268  lea     rax, [rbp+arg_18]
0x14000e26c  mov     dword ptr [rbp+var_28+4], 0
0x14000e273  test    rbx, rbx
0x14000e276  mov     qword ptr [rbp+var_28+8], rax
0x14000e27a  lea     r9, [rbp+UserData]; UserData
0x14000e27e  mov     [rbp+var_18], r8
0x14000e282  cmovz   rbx, rcx
0x14000e286  lea     rdx, ?NET_FATAL_ERROR@?1??__FatalError@@YAXPEBDK0K@Z@4U_EVENT_DESCRIPTOR@@B; EventDescriptor
0x14000e28d  mov     rcx, [rbp+RegHandle]; RegHandle
0x14000e291  mov     qword ptr [rbp+var_38+8], rbx
0x14000e295  call    cs:__imp_EventWrite
0x14000e29b  mov     rcx, [rbp+RegHandle]; RegHandle
0x14000e29f  call    cs:__imp_EventUnregister
0x14000e2a5  cmp     cs:?bTestHookVariable@?1??GetTestHookVariable@FastFailTestHook@@CAPEAHXZ@4HA, 0; int `FastFailTestHook::GetTestHookVariable(void)'::`2'::bTestHookVariable
0x14000e2ac  jz      short loc_14000E2C4
0x14000e2ae  call    cs:__imp_GetCurrentProcess
0x14000e2b4  mov     rcx, rax; hProcess
0x14000e2b7  mov     edx, 3; uExitCode
0x14000e2bc  call    cs:__imp_TerminateProcess
0x14000e2c2  jmp     short loc_14000E2E8
0x14000e2c4  call    cs:__imp_IsDebuggerPresent
0x14000e2ca  test    eax, eax
0x14000e2cc  jnz     short loc_14000E2E2
0x14000e2ce  mov     al, ds:7FFE02D4h
0x14000e2d5  and     al, 3
0x14000e2d7  cmp     al, 3
0x14000e2d9  jz      short loc_14000E2E2
0x14000e2db  mov     ecx, 7
0x14000e2e0  int     29h; Win8: RtlFailFast(ecx)
0x14000e2e2  call    cs:__imp_DebugBreak
0x14000e2e8  mov     rcx, [rbp+var_10]
0x14000e2ec  xor     rcx, rsp; StackCookie
0x14000e2ef  call    __security_check_cookie
0x14000e2f4  mov     rbx, [rsp+80h+arg_0]
0x14000e2fc  add     rsp, 80h
0x14000e303  pop     rbp
0x14000e304  retn
```
