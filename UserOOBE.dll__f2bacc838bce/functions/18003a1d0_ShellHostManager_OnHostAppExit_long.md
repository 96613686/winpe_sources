# ShellHostManager::OnHostAppExit(long)

- ea: `0x18003a1d0`
- end: `0x18003a263`
- name: `?OnHostAppExit@ShellHostManager@@AEAAXJ@Z`
- size: `147`
- prototype: `void __fastcall(ShellHostManager *__hidden this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030fe4`
- `0x180037738`
- `0x180039840`

## callees

- `0x180032758`
- `0x1800327e0`
- `0x1800339ec`
- `0x180038ee4`
- `0x18003a1d0`
- `0x18003ef58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a23f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a23f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18003a21a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18003a21a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003a22f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003a22f`

## pseudocode

```c
void __fastcall ShellHostManager::OnHostAppExit(ShellHostManager *this, int a2)
{
  int UserOOBEExitReason; // eax
  HWND WindowW; // rax
  DWORD CurrentThreadId; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  ShellHostManager *v8; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = a2;
  CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[41],unsigned short const (&)[13]>("AppManager-ShellHostManagerOnHostAppExit");
  if ( *((_BYTE *)this + 32) )
    goto LABEL_4;
  UserOOBEExitReason = GetUserOOBEExitReason();
  if ( UserOOBEExitReason )
  {
    if ( (unsigned int)(UserOOBEExitReason - 1) <= 1 )
LABEL_4:
      std::promise<long>::set_value((char *)this + 56, &v9);
  }
  else
  {
    WindowW = FindWindowW(L"Shell_TrayWnd", 0);
    if ( !WindowW || !GetPropW(WindowW, L"IsExplorerShuttingDown") )
    {
      v8 = this;
      CurrentThreadId = GetCurrentThreadId();
      Windows::Internal::ComTaskPool::QueueTask__lambda_3cae3956428f5b09d360bc0dc494ae2d___(
        v7,
        v6,
        CurrentThreadId,
        (__int64)&v8);
    }
  }
  CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[41],unsigned short const (&)[11]>("AppManager-ShellHostManagerOnHostAppExit");
}

```

## disassembly

```asm
0x18003a1d0  mov     [rsp+arg_8], edx
0x18003a1d4  push    rbx
0x18003a1d5  sub     rsp, 20h
0x18003a1d9  mov     rbx, rcx
0x18003a1dc  lea     rcx, aAppmanagerShel_2; "AppManager-ShellHostManagerOnHostAppExi"...
0x18003a1e3  call    ??$CoreEvent1@AEAY0CJ@$$CBDAEAY0N@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CJ@$$CBDAEAY0N@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[41],ushort const (&)[13]>(char const (&)[41],ushort const (&)[13])
0x18003a1e8  cmp     byte ptr [rbx+20h], 0
0x18003a1ec  jnz     short loc_18003A201
0x18003a1ee  call    ?GetUserOOBEExitReason@@YA?AW4UserOOBEExitReason@@XZ; GetUserOOBEExitReason(void)
0x18003a1f3  test    eax, eax
0x18003a1f5  jz      short loc_18003A211
0x18003a1f7  sub     eax, 1
0x18003a1fa  jz      short loc_18003A201
0x18003a1fc  cmp     eax, 1
0x18003a1ff  jnz     short loc_18003A252
0x18003a201  lea     rcx, [rbx+38h]
0x18003a205  lea     rdx, [rsp+28h+arg_8]
0x18003a20a  call    ?set_value@?$promise@J@std@@QEAAX$$QEAJ@Z; std::promise<long>::set_value(long &&)
0x18003a20f  jmp     short loc_18003A252
0x18003a211  xor     edx, edx; lpWindowName
0x18003a213  lea     rcx, ClassName; "Shell_TrayWnd"
0x18003a21a  call    cs:__imp_FindWindowW
0x18003a220  test    rax, rax
0x18003a223  jz      short loc_18003A23A
0x18003a225  lea     rdx, String; "IsExplorerShuttingDown"
0x18003a22c  mov     rcx, rax; hWnd
0x18003a22f  call    cs:__imp_GetPropW
0x18003a235  test    rax, rax
0x18003a238  jnz     short loc_18003A252
0x18003a23a  mov     [rsp+28h+arg_0], rbx
0x18003a23f  call    cs:__imp_GetCurrentThreadId
0x18003a245  mov     r8d, eax
0x18003a248  lea     r9, [rsp+28h+arg_0]
0x18003a24d  call    Windows__Internal__ComTaskPool__QueueTask__lambda_3cae3956428f5b09d360bc0dc494ae2d___
0x18003a252  lea     rcx, aAppmanagerShel_2; "AppManager-ShellHostManagerOnHostAppExi"...
0x18003a259  add     rsp, 20h
0x18003a25d  pop     rbx
0x18003a25e  jmp     ??$CoreEvent1@AEAY0CJ@$$CBDAEAY0L@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CJ@$$CBDAEAY0L@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[41],ushort const (&)[11]>(char const (&)[41],ushort const (&)[11])
```
